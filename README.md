参考官方文档，基本上可以没有问题
https://github.com/gpac/gpac/wiki/GPAC-Build-Guide-for-Android
当前仅仅包含deps_android源码和编译结果，基于节点
```
bc66f46 - add nghttp2 for android (2021-02-23 18:03:22) <buildworker-ubuntu64>
```
##一、用ubuntu的源不能下载jdk，需要使用阿里源
###1、备份原有源
```
sudo mv /etc/apt/sources.list /etc/apt/sources.list.bak
sudo vi /etc/apt/sources.list
```
###2、使用阿里源内容
```
deb http://mirrors.aliyun.com/ubuntu/ xenial main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ xenial-proposed main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ xenial main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse
```
###3、更新源
```
sudo apt update
```
###4、设置当且需要的jdk
```
sudo update-alternatives --config java
```
##二、同步代码最好要文明上网，不然很多内容不能同步

使用Windows客户端推流或者播放
客户端地址：https://gpac.wp.imt.fr/downloads/
推流方法：
```
./gpac.exe httpout:rdirs="E:/Videos/dashTest/dashSRD360":dlist=true:maxc=0:maxp=0:port=8080
```
播放方法：
```
./gpac.exe -gui http://localhost:8080/srd_360.mpd#VR
```
