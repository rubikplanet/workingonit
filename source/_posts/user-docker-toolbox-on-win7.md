---
title: 在 Windonws 7上使用 Docker Toolbox
---
在 Windows 7 上使用 Docker Toolbox 运行 Docker 本地环境。

## 安装 scoop
本文需要使用 scoop 完成软件的安装，假设你已经安装好 scoop，如果未安装请参考 https://scoop.sh/ 自行完成。

### 安装 Virtual Box

```
scoop add bucket nonportable
scoop install virtualbox-np
```

### 安装Docker

```
scoop install docker
```

### 环境配置
设置环境变量，把虚拟机保存在E盘上。
```
setx MACHINE_STORAGE_PATH E:\DockerMachine
```
设置后需要关闭命令行工具重新打开才会生效。

打开VirtualBox，在菜单【管理->全局设定->常规】中配置VirtualBox虚拟机存放位置

### 创建名称为 default 的虚拟机
```
docker-machine create --engine-registry-mirror=Docker加速器地址 -d virtualbox default
```
关于Docker加速器地址，可以使用阿里云的自行解决。

查看虚拟机信息
```
docker-machine env default
```
根据提示运用命令，具体视你的 docker-machine env default 命令的信息，可能有差异。
```
@FOR /f "tokens=*" %i IN ('"C:\Users\Administrator\scoop\apps\docker\current\docker-machine.exe" env default') DO @%i
```

### 使用 Docker
完成以上步骤后，就可以使用 Docker 命令来管理容器了。

比如我们拉取一个Reids镜像
```
docker pull redis:3.2
```
运行redis镜像
```
docker run --name redis -p 6379:6379 -v /data:/data -d redis:3.2 redis-server --appendonly yes
```
注意：这里的 -v /data:/data，需要你打开 Virtual Box，在 default 虚拟机上做/data目录映射到你的宿主机上。

