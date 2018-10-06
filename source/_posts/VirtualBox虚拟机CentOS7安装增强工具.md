---
title: VirtualBox虚拟机CentOS7安装增强工具
date: 2018-10-05 21:32:38
categories:
- 虚拟机技术
tags:
- VirtualBox
- CentOS
---

1. 选择VirtualBox的“设备”->“安装增强工具…”

2. 进入到SHELL模式下，挂载光盘
```
#sudo mount /dev/cdrom /media
```

3. ​安装必要的工具
```
#sudo yum install perl gcc* make kernel kernel-devel -y
```

4. 进行安装
```
#cd /media/
#sudo sh VBoxLinuxAdditions.run
```
