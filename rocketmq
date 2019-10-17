# **rocketmq**

- 安装

```shell
docker pull rocketmqinc/rocketmq
```

- 网桥模式

```shell
docker run -d -p 9876:9876 -v /data/rmq/namesrv/logs:/root/logs -v /data/rmq/namesrv/store:/root/store --name royfang-rmqnamesrv rocketmqinc/rocketmq:latest sh mqnamesrv

docker run -d -p 10911:10911 -p 10909:10909 -v /data/rmq/broker/logs:/root/logs -v /data/rmq/broker/store:/root/store --name royfang-rmqbroker --link royfang-rmqnamesrv:namesrv -e "NAMESRV_ADDR=namesrv:9876" rocketmqinc/rocketmq:latest sh mqbroker
```

- host模式

```shell
docker run -d -v /data/rmq/namesrv/logs:/root/logs -v /data/rmq/namesrv/store:/root/store --name royfang-rmqnamesrv --net="host" rocketmqinc/rocketmq:latest sh mqnamesrv

docker run -d -v /data/rmq/broker/logs:/root/logs -v /data/rmq/broker/store:/root/store --name royfang-rmqbroker --net="host" -e "NAMESRV_ADDR=9.134.5.25:9876" rocketmqinc/rocketmq:latest sh mqbroker
```

> 客户端版本需和服务端版本保持一致



## 前端

- 安装

```shell
docker pull styletang/rocketmq-console-ng
```

- 网桥模式

```shell
docker run -t --name royfang-rmqcsng -e "JAVA_OPTS=-Drocketmq.namesrv.addr=192.168.10.2:9876 -Dcom.rocketmq.sendMessageWithVIPChannel=false" -p 8979:8080 styletang/rocketmq-console-ng:latest
```

- host模式

```shell
docker run -t --name royfang-rmqcsng --net="host" -e "JAVA_OPTS=-Drocketmq.namesrv.addr=9.134.5.25:9876 -Dcom.rocketmq.sendMessageWithVIPChannel=false" styletang/rocketmq-console-ng:latest
```
