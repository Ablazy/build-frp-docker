# build-frp-docker

[README](README.md) | [中文文档](README_zh.md)

See how to use frp on [here](https://github.com/Ablazy/build-frp-docker/blob/dev/README.md).

## How to use

clone and run

For frps

``` shell
docker build -f ./dockerfiles/Dockerfile-for-frps -t frps . 
```

For frpc

``` shell
docker build -f ./dockerfiles/Dockerfile-for-frpc -t frpc . 
```

## Run docker image

For frps

``` shell
docker run --name frps \
--restart always \
--network host \
-v /opt/docker/frps/:/frps/ \
-d frps:latest
```

For frpc

``` shell
docker run --name frpc \
--restart always \
--network host \
-v /opt/docker/frpc/:/frpc/ \
-d frpc:latest
```



Then, edit the toml file in the directory you mounted and restart your container.

