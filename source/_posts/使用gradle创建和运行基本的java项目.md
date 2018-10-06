---
title: 使用gradle创建和运行基本的java项目
date: 2018-10-06 21:59:23
categories:
- Java
tags:
- Java
- Gradle
---

# 开发环境
- jdk1.8
- gradle4.10.2
- windows7

# 创建Java项目
```
gradle init --type java-application
```
这样就建好了一个基本的Java项目。

如果对 gradle init 不熟悉可以用下面命令查看帮助：
```
gradle help --task init
```

# 运行项目
```
gradle run
```

# 运行测试
```
gradle test
```
