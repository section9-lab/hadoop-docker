# hadoop-docker

## 简介
这是一个基于CentOS7、JDK1.8、hadoop2.7.1、kafka2.0.0版本构建的docker镜像，主要用作本地服务器开发测试使用。

比如面向Apache Spark、Apache Flink需要提交到Yarn的分布式任务的场景。


## 使用方法

### 1、获取dockerfile
```sh
git clone https://github.com/section9-lab/hadoop-docker
```
### 2、构建docker image
```sh
> mkdir build-docker-workspace && cd build-docker-workspace
> docker build -t hadoop:2.7.1 .
```
### 3、启动docker
```sh
> docker run -dti --hostname bigdata.host -p 50070:50070 -p 9000:9000 -p 8088:8088 -p 8040:8040 \
-p 8042:8042 -p 49707:49707  -p 50010:50010  -p 50075:50075 -p 50090:50090 -p 2181:2181 -p 9092:9092 \
hadoop:2.7.0-1 /etc/bootstrap.sh -bash --privileged=true
> docker exec -ti xxxxx bash
```
