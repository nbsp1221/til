# 패키지 버전 업데이트

`npm outdated` 명령어를 이용하면 버전이 지난 패키지를 점검할 수 있다.
이때 `npm update` 명령어를 사용해 패키지를 업데이트하는데 `package.json` 파일에 적혀 있는 버전은 그대로라 이 버전도 같이 올릴 수 있는 방법은 없는지 찾아보았다.

## npm-check-updates 이용

[npm-check-updates](https://www.npmjs.com/package/npm-check-updates)를 이용하면 `package.json` 파일에 적혀 있는 dependencies를 한방에 최신 버전으로 업데이트할 수 있다.

```shell
npm install -g npm-check-updates
```

설치를 끝낸 다음엔 `ncu` 명령어로 사용할 수 있다. 업데이트는 `-u` 플래그를 추가한다.

```shell
ncu -u
```

업데이트의 경우 실제로 패키지가 업데이트된 것은 아니고 버전만 최신 버전으로 바꾼 것이기 때문에 마지막에 `npm install` 명령어로 계속 진행하면 업데이트가 완료된다.

```shell
npm install
```

## Reference

* https://stories.tistory.com/271
