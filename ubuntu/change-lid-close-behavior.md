# 노트북 덮개를 닫았을 때 수행하는 작업 변경

안 쓰는 노트북을 이용해 집에서 간단한 우분투 서버를 돌리고 있다. 하지만 노트북 덮개를 닫을 경우 서버가 꺼지는 문제가 있어 해결 방법을 찾아보았다.

## 설정 파일 수정

설정 파일을 수정하는 방법으로 쉽게 해결할 수 있다.

```shell
sudo nano /etc/systemd/logind.conf
```

아래쪽의 `HandleLidSwitch` 주석을 해제한 뒤에 원하는 작업으로 수정한다.

* `ignore`: 아무것도 하지 않음
* `lock`: 모니터 화면만 꺼짐
* `hibernate`: 최대 절전 모드
* `poweroff`: 시스템 종료

설정을 마친 다음 파일을 저장하고 아래 명령어로 바뀐 내용을 적용한다.

```shell
systemctl restart systemd-logind.service
```

## Reference

* http://ubuntuhandbook.org/index.php/2020/05/lid-close-behavior-ubuntu-20-04
* https://labo.lansi.kr/posts/53
