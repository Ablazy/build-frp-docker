# build-frp-docker

[README](README.md) | [中文文档](README_zh.md)

[在这](https://github.com/Ablazy/build-frp-docker/blob/dev/README.md)查看如何使用frp

## How to use

克隆仓库并运行

服务端frps

``` shell
docker build -f ./dockerfiles/Dockerfile-for-frps -t frps . 
```

客户端frpc

``` shell
docker build -f ./dockerfiles/Dockerfile-for-frpc -t frpc . 
```

## Run docker image

服务端

``` shell
docker run --name frps \
--restart always \
--network host \
-v /opt/docker/frps/:/frps/ \
-d frps:latest
```

客户端

``` shell
docker run --name frpc \
--restart always \
--network host \
-v /opt/docker/frpc/:/frpc/ \
-d frpc:latest
```



然后，编辑挂载的目录中的 toml 文件并重新启动容器。

