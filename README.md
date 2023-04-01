# 天气项目学习笔记

## 项目目标

本项目的目的是在室内放置温湿度传感器，以实时监测室内温湿度，配合室外温湿度信息生成天气 APP 并给生活工作提供指导。

因为目前的天气 APP 较少缺乏室内温湿度信息，而是内外温湿度差距较大，因此能够进行横向比较将会是一件有意义的事情。

本项目还试图引入 AI 助手对气象信息进行解析，并给出更具操作性的建议。

## 硬件搭建

### 服务器环境配置

本项目的服务器采用 OrangePi 3 LTS 版本，运行系统为 `Ubuntu Orangepi3-lts_2.2.2_ubuntu_focal_server_linux5.10.75` 版本

#### Ubuntu 软件安装

Ubuntu 软件安装使用 apt 命令完成。更详细的笔记查看 [Ubuntu Note](./UbuntuNote.md)

首先需要运行 `apt update` 命令来同步与服务器的元数据信息。

必要的 js 软件包括 `nodejs npm`
但通过这种方法安装的 node 版本一般会很老，无法使用部分新特性

在 Linux 中我们可以使用 npm 的 `n` 模块来管理 node 版本

需要注意的是在 linux 中安装全局包都需要使用管理员权限

##### n 的安装及使用

```bash
# 使用以下命令全局安装

sudo npm i -g n

# 使用以下命令安装最新版本
n latest/current
```

##### pm2

pm2 是一个非常好用的进程守护工具，可以对 node 进程进行更方便的后台管理，也可以守护 python 等进程，但需指定编译器。

```bash
# 安装

npm install pm2 -g

# 启动命令

pm2 start [entry-file-path] --name=[custom-name]

# 查看当前进程列表

pm2 list

# 在更新后对应用快速重启

pm2 reload [app-name]

# 停止进程

pm2 stop

# 查看所有应用程序日志

pm2 logs

# 查看特定程序日志

pm2 logs [app-name]

# 保存当前应用列表（为了快速重启）

pm2 save

# 开机自启动

pm2 startup

# 指定编译器，以python3为例

pm2 start [entry-file-path] --interpreter python3

```

### 传感器

### 内网穿透

## 软件配置

### 架构

### 后端

### 前端
