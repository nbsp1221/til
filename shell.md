## git pull all repositories

```shell
for NAME in $(ls); do cd $NAME; git pull; cd ..; done
```

## backquote

```shell
if ! [ -f ~/Library/KeyBindings/DefaultkeyBinding.dict ]; then mkdir -p ~/Library/KeyBindings && echo '{"₩" = ("insertText:", "\`");}' > ~/Library/KeyBindings/DefaultkeyBinding.dict; fi
```
