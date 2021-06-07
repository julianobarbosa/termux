# termux

## Install Python
```console
pkg install Python
```

termux tips


## to use pyenv 
### URL: https://gwangyi.github.io/posts/pyenv-in-termux/

```console
wget -O - "https://api.github.com/repos/termux/termux-packages/contents/packages/python?ref=5cac708d"    | \
         jq '.[]|select(.name|endswith(".patch"))|.download_url' | \
         xarg wget -O - -q | \
         sed "s%@TERMUX_PREFIX@%$PREFIX%g; s%^+++ [^/ ]*%+++ .%" | \
         pyenv install -p -v 3.7.2
```
