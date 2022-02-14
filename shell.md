## git pull all repositories

```shell
for NAME in $(ls); do cd $NAME; git pull; cd ..; done
```
