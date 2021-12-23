
#### 构建镜像

> 以下执行操作基于`Apple M1 Max`芯片的`macOS Monterey`。

```bash
# pip3 install flask uwsgi
# pip3 freeze > requirements.txt
$ cd ..
$ docker build -t dosgames-web:0.0.1 --file docker/Dockerfile .
$ docker run --rm -it --entrypoint bash dosgames-web:0.0.1

# 使用本地已经下载的游戏资源
$ docker run --rm -p 8080:8080 -v `pwd`/static/games/bin/:/app/static/games/bin/ --name dosgames dosgames-web:0.0.1
# 使用已有的游戏库
$ docker run --rm -p 8080:8080 -e GAME_LOAD_PATH=https://dl.zizhizhan.com/games --name dosgames dosgames-web:0.0.1
# docker exec -it dosgames bash
$ open http://localhost:8080

$ docker tag dosgames-web:0.0.1 jameszhan/dosgames-web:0.0.1-aarch64
$ docker push jameszhan/dosgames-web:0.0.1-aarch64
```