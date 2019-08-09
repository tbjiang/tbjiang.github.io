---
layout:     post
title:      git 常用命令记录
subtitle:   note
date:       2019-08-09
author:     tianbi
header-img: img/diary1.jpeg
catalog: true
tags:
    - note
---
#### 配置SSH-key
git关联本地仓库和远程仓库需要进行身份识别，通常通过SSH公钥授权。先检查是否有已经生成的公钥，公钥默认存储在`/.ssh`目录下。
```shell
$ cd ~/.ssh
$ ls
id_rsa  id_rsa.pub  known_hosts
```
有`.pub`后缀的文件即为公钥，如`id_rsa.pub`。若没有，用`ssh-keygen`命令生成，再打开文件查看公钥即可。其中生成公钥时需要确认文件目录及密码，密码可以留空。
```shell
$ ssh-keygen
$ cat ~/.ssh/id_rsa.pub
```

#### git设置用户信息
设置好公钥后，需要配置用户名称和email地址，用来标明本次提交的提交者。
```git
$ git config --global user.name "Blair"
$ git config --global user.email Blair@xxx.com
```

#### git初始化及关联远程仓库
初始化本地git仓库，关联远程仓库。例如远程仓库名为`git@github.com:blair/testgit.git`
```git
$ git int
$ git remote add origin git@github.com:blair/testgit.git
```
#### 直接clone远程仓库或分支
```git
$ git clone git@github.com:blair/testgit.git
$ git clone -b 分支名 git@github.com:blair/testgit.git
#本地已有仓库，获取远程分支方式
$ git checkout -b 分支名 origin/分支名
```
#### git 提交代码
```git
$ git add filename.text
$ git commit -m "test git"
$ git push
```

#### 回滚到某一版本
```git
$ git reset --hard HEAD^
$ git reset --hard 83ff2785
$ git push --force
```

#### 强制拉取
```git
$ git fetch --all  
$ git reset --hard origin/master 
$ git pull
```

#### 创建本地分支并关联远程分支
```git
$ git checkout -b new_branch
$ git push origin new_branch
$ git branch –set-upstream 本地新建分支名 origin/远程分支名
```

