---
layout: post
title: 利用Anaconda安装OpenCV,并在PyCharm中设置
tag: 工具
keyword: Markdown
description:
---

> 最近需要将Opencv2转换为Opencv3,之前安装主要是通过源代码安装,但是安装实在是太慢了...另外,因为我已经用Anaconda配置好了环境,所以想基于Anaconda的环境安装Opencv3.

> 下面,主要记录我安装的过程,并在PyCharm中进行配置.

## 安装Anaconda

### 1.下载Anaconda

按照电脑的配置和python的版本,下载[anaconda][1].

### 2.安装Anaconda

Python 3.5 version

    bash Anaconda3-4.2.0-Linux-x86_64.sh 

Python 2.7 version
 
    bash Anaconda2-4.2.0-Linux-x86_64.sh 

## Anaconda的使用

### 1.搜索软件包

    conda search package-name

    anaconda search -t conda package-name

### 2.安装软件包

    conda install package-name

安装指定软件包:

    conda install package-name=x.x

    conda install -c 发布者 package-name=x.x

### 3.查看已安装的软件包

    conda list

### 4.修改镜像源

    conda config --add channels 'https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/'

    conda config --set show_channel_urls yes

### 5.删除镜像源

    sudo nano ~/.condarc

## 安装OpenCV

选择下列方法之一安装:

### 1.通过Anaconda安装OpenCV

    anaconda search -t conda opencv

    conda install -c 发布者 opencv

### 2.通过源码安装

可以安装该[教程][2]或该[教程][3]进行源码安装.

注: 由于我的python环境是通过anaconda配置的,在使用PyCharm时可能会出现不能识别已安装的opencv(我是使用anaconda安装的opencv).

此时,需要分别找到anaconda安装python和opencv的路径,并将cv.py和cv2.so链接到python的路径中.

    cd /path/to/anaconda2/lib/python2.7/site-packages/

    ln -s /path/to/opencv/cv2.so cv2.so

    ln -s /path/to/opencv/cv.py cv.py

如果找不到cv.py,可以创建cv.py文件,并添加:
 
    from cv2.cv import *




[1]: https://www.continuum.io/downloads
[2]: http://www.pyimagesearch.com/2015/06/22/install-opencv-3-0-and-python-2-7-on-ubuntu/
[3]: https://github.com/jayrambhia/Install-OpenCV
