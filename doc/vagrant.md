# Vagrant快速创建虚拟机器
---
## What
Vagrant 是一款用来构建虚拟开发环境的工具，非常适合 php/python/ruby/java 这类语言开发 web 应用环境快速部署和搭建。

## 安装VirtualBox
虚拟机运行平台：依靠 VirtualBox 来搭建，免费小巧。
下载地址：https://www.virtualbox.org/wiki/Downloads

## 安装Vagrant并添加镜像Box
下载地址：https://www.vagrantup.com/downloads.html 根据提示一步步安装。

## 添加Box
官方box镜像：vagrant box add hashicorp/precise64（将从官网下载名为 hashicorp/precise64 的 box，可能需要等待一段时间。）
本地box镜像：vagrant box add *name*  *path* （name:定义boxname  path:box本地路径）


    $ vagrant box add centos67  centos-6.7.box
    $ vagrant box list

## 初始化开发环境
创建环境目录，使用已添加的box镜像初始化目录环境，操作后会在当前目录生成一个Vagrantfile文件

    $ cd Vagrant/
    $ vim Vagrantfile

Vagrantfile 的配置文件，可以修改配置文件进行个性化的定制。

## 模板化Vagrantfile文件
* Vagrantfile使用ruby的语法进行配置，优化设置使用更加人性化配置方式去实现，即YAML.
	查看：https://github.com/seanly/vagrant-yaml.git

     `$ git clone https://github.com/seanly/vagrant-yaml.git`
	修改配置machines.j2.yaml文件，批量配置虚拟机。

* 本地文件

    `$ git@github.com:wangll1991/salt.git`

## 配置虚拟机

    $ vagrant status
    $ vagrant up [machines_name]
    $ vagrant status

解析vagrantfile文件系统配置，并启动环境，最后查看系统状态。


## 常用命令

    $ vagrant init  # 初始化
    $ vagrant up  # 启动虚拟机
    $ vagrant halt  # 关闭虚拟机
    $ vagrant reload  # 重启虚拟机
    $ vagrant ssh  # SSH 至虚拟机
    $ vagrant status  # 查看虚拟机运行状态
    $ vagrant destroy  # 销毁当前虚拟机

## 技术文档
[vagrant command-line](https://www.vagrantup.com/docs/cli/)

[使用Vagrant打造跨平台开发环境](https://segmentfault.com/a/1190000000264347)

[Vagrant和docker的使用场景和区别](https://www.zhihu.com/question/32324376)

[不一样的docker原理](https://zhuanlan.zhihu.com/p/22382728)