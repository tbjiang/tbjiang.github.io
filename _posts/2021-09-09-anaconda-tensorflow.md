---
layout:     post
title:      在anaconda环境下配置tensorflow笔记(Linux)
subtitle:   note
date:       2019-09-09
author:     tianbi
header-img: img/brother.jpeg
catalog: true
tags:
    - note
---
#### 下载anaconda
从官网下载anaconda3并安装。
```shell
$ wget https://repo.anaconda.com/archive/Anaconda3-2019.07-Linux-x86_64.sh
$ bash Anaconda3-2019.07-Linux-x86_64.sh
$ conda --version 
```
可能需要将Anaconda安装路径加入到环境变量（.bashrc)中。
```shell
$ export PATH="~/anaconda3/bin:$PATH"
$ source ~/.bashrc 
```

#### 创建虚拟环境
创建虚拟环境后激活，进入环境后再安装tensorflow。
```shell
$ conda create -n tensorflow(env_name) #创建环境
$ #or conda create --name tensorflow(env_name)  python=3.5
$ source activate tensotflow #激活环境
```
如果想返回普通环境或删除环境
```shell
$ source deactivate tensotflow #返回环境
$ conda remove --name tensotflow --all #删除环境
#or
$ conda env remove -n tensorflow
```

#### 安装tensorflow
直接安装指定版本tensorflow
```shell
$ conda install --channel https://conda.anaconda.org/anaconda tensorflow-gpu==1.0.1
###or
$ conda install tensorflow-gpu==1.13.1 #下载指定gpu版本tensorflow 不加参数则下载最新版
$ conda install tensorlfow==1.13.1 #下载指定cpu版本tensorflow
```
or 如果想查看版本再下载对应版本的tensorflow
```shell
$ anaconda search -t conda tensorflow #查看版本
$ anaconda show jjh_ppc64le/tensorflow-gpu #查看版本具体信息
$ conda install --channel https://conda.anaconda.org/nehaljwani tensorflow-gpu=4.7.11 #下载该版本
```