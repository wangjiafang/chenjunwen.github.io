---
title: CentOS7 Firewall常用命令汇总
date: 2018-10-11 11:27:18
tags: linux
categories: linux 
---
##firewalld的基本使用

​	启动：systemctl start firewalld

​	查看状态： systemctl status firewalld 

​	停止： systemctl disable firewalld

​	禁用： systemctl stop firewalld

​	启动一个服务：systemctl start firewalld.service

​	关闭一个服务：systemctl stop firewalld.service

​	重启一个服务：systemctlrestart firewalld.service

​	显示一个服务的状态：systemctl status firewalld.service

​	在开机时启用一个服务：systemctl enable firewalld.service

​	在开机时禁用一个服务：systemctl disable firewalld.service

​	查看服务是否开机启动：systemctl is-enabled firewalld.service

​	查看已启动的服务列表：systemctl list-unit-files|grep enabled

​	查看启动失败的服务列表：systemctl--failed

​	查看还有哪些服务可以打开:  firewall-cmd --get-services

​	查看当前开了哪些端口: firewall-cmd --list-services

##配置firewalld-cmd

​	查看版本： firewall-cmd --version

​	查看帮助： firewall-cmd --help

​	显示状态： firewall-cmd --state

​	查看所有打开的端口： firewall-cmd--zone=public --list-ports

​	更新防火墙规则： firewall-cmd --reload

​	查看区域信息:  firewall-cmd--get-active-zones

​	查看指定接口所属区域： firewall-cmd--get-zone-of-interface=eth0

​	拒绝所有包：firewall-cmd --panic-on

​	取消拒绝状态： firewall-cmd --panic-off

​	查看是否拒绝： firewall-cmd --query-panic

​	查看所有打开的端口:  firewall-cmd --zone=public --list-ports

 ## 开启一个端口

​	添加:  firewall-cmd --zone=public --add-port=80/tcp --permanent   （--permanent永久生效，没有此参数重启后失效）

​	重新载入:  firewall-cmd --reload

​	查看:  firewall-cmd --zone=public --query-port=80/tcp

​	删除:  firewall-cmd --zone=public --remove-port=80/tcp --permanent




