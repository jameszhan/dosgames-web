# `Kubernetes`部署`DOSGames`

## 部署`DOSGames`

### 利用`NAS`挂载游戏资源文件

打开`deploy-with-nas.yaml`文件，替换如下内容。

```yaml
nfs:
  path: /volume1/shared/kickstart/games
  server: 192.168.1.6
```

执行部署

```bash
$ kubectl apply -f deploy-with-nas.yaml
```

### 利用`CORS`挂载游戏资源文件

打开`deploy-with-cors.yaml`文件，替换如下内容。

```yaml
env:
  - name: GAME_LOAD_PATH
    value: https://dl.zizhizhan.com/games
```

执行部署

```bash
$ kubectl apply -f deploy-with-cors.yaml
```

## 配置`Ingress`

打开`ingress.yaml`文件，按需调整域名及TLS信息。

```bash
$ kubectl apply -f ingress.yaml
```

