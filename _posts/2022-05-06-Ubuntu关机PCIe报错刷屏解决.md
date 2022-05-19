---
layout: post
title: Ubuntu关机时PCIe刷屏报错问题解决
categories: Ubuntu
description: Ubuntu下PCIe报错
keywords: ubuntu
---



系统： Ubuntu18.04 

在加装固态硬盘之后，关机的时候总是会刷屏报错，并且在使用过程中，会概率性卡死，大多出现在大面积删除文字或大面积粘贴复制文字的情形下。这个时候要么直接卡死到报错刷屏界面，要么强制关机到那个界面：

![](/home/klelee/klbook/images/PCIe_error.jpg)

解决方法：

修改grub配置文件：

```
sudo vim /etc/default/grub
```

在对应行添加：pci=nommconf

![image-20220506090448193](/home/klelee/klbook/images/image-20220506090448193.png)

然后更新grub配置文件：

```
sudo update-grub
reboot
```

下次关机的时候就不会报错了。如果在使用过中还是会概率性卡死的情况，该考虑是固态硬盘的问题。