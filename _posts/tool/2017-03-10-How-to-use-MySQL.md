---
layout: post
title: MySQL使用教程
tag: 工具
keyword: MySQL
description:
---

## 1.使用MySQL Client(MySQL客户端)连接MySQL服务器

    mysql -u root -p
    Enter password:
    
输入密码后,输出```mysql>```的提示符, 说明已经成功连接到MySQL服务器上.

## 2.显示数据库列表

    show databases;
    +--------------------+
    | Database           |
    +--------------------+
    | information_schema |
    | mysql              |
    | performance_schema |
    | testdb             |
    +--------------------+
    
## 3.创建数据库

    create database db_image_label;
    
## 4.选择数据库

    use db_image_label;
    
## 5.显示数据表

    show tables;
    
## 6.从本地文件导入数据库

    source /path/to/local/file
    
## 7.远程导出数据

    mysqldump -P [port] -u [IP] -u [user] -p databasename > /path/to/file
    
