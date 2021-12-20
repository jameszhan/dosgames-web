
# dos-games-web

Source code of https://github.com/jameszhan/dosgames-web

## 本地执行

### 下载 Flask

``` sh
$ pip3 install flask
```

### 已有游戏资源

在环境变量中设置`GAME_LOAD_PATH`，如果存在跨域，需要服务端[开启`CORS`服务](https://enable-cors.org/index.html)。

``` sh
$ export GAME_LOAD_PATH=https://dl.zizhizhan.com/games
$ python3 app.py
```

### 下载游戏资源

资源文件比较大，有`33G`左右，默认存放位置为`static/games/bin`

``` sh
$ python3 scripts/download_games.py
$ python3 app.py
```

## Credits

* [dreamlayers/em-dosbox: An Emscripten port of DOSBox](https://github.com/dreamlayers/em-dosbox)
* [db48x/emularity: easily embed emulators](https://github.com/db48x/emularity)
* [caiiiycuk/js-dos: The simpliest API to run DOS games in browser](https://github.com/caiiiycuk/js-dos)
