# Ubuntu 学习笔记

## 远程 SSH 连接

远程 SSH 连接可以借助 MobaXterm 来实现，该客户端可以方便地实现文件上传下载，并执行终端命令控制。

要建立新的连接可以在顶部菜单栏 Sessions-new 打开新的窗口

然后建立 SSH 连接并输入对应的服务器 ip 地址，一般 SSH 的默认端口为 22

对于 AWS 等云平台的 SSH 连接在连接时需要附带私钥 .pem 文件，具体参考对应的服务文档。

## IP 地址配置

推荐将 orangepi 直接用网线连接至路由器，在启动时可以在终端开头查看到当前的 IP 地址。

最方便的方式是直接将终端连接到显示器上进行查看。

配置静态 ip 可以使用 nmtui 的方式来用图形化的方式设置 ip 地址。

但不知为何在设置之后 ssh 连接会失效，但其他端口可以正常访问。

经测试在自家网络中 wifi 网络下设备变动不频繁的情况下一般 ip 地址不会发生改变。

## 包管理器

参考资料： https://linux.cn/article-12713-1.html

简单来说，“包管理器 package manager”（或“软件包管理器”）是一种工具，它允许用户在操作系统上安装、删除、升级、配置和管理软件包。软件包管理器可以是像“软件中心”这样的图形化应用，也可以是像 apt-get 或 pacman 这样的命令行工具。

NPM 和 Pip 也是包管理器。

### 元数据文件

你的系统上的包管理器首先会与元数据进行交互。包管理器在你的系统上创建了一个元数据的本地缓存。当你运行包管理器的更新选项（例如 apt update）时，它会通过引用仓库中的元数据来更新本地元数据缓存。

### 依赖处理

如果软件包有其他的以来，包管理器通常也会处理这些依赖，并在安装时一并进行安装。

### apt 与 apt-get

参考资料： https://zhuanlan.zhihu.com/p/350690109

apt 与 apt-get 事实上是两个不同的包管理器。 apt-get 具有更久的历史，在 Linux 中流行。

apt 在 2014 年推出第一个稳定版，在 Ubuntu 中开始流行。目前越来越多的 Linux 发行版开始鼓励使用 apt 而不是 apt get

![apt 与 apt-get 命令对比](https://pic1.zhimg.com/v2-91aba22874e028e95ba0849ab9d79150_r.jpg)

apt 可以看作 apt-get 和 apt-cache 命令的子集, 可以为包管理提供必要的命令选项。

apt-get 虽然没被弃用，但作为普通用户，还是应该首先使用 apt。

## 用户权限

https://blog.csdn.net/yl19870518/article/details/100776136

待补充

## 文件夹的增删

mkdir 可以在当前路径下建立新的文件夹

`mkdir [folder name]`

### rm

rm 命令可以帮助我们

rm 命令有如下参数

- -i 删除前逐一询问确认。
- -f 即使原档案属性设为唯读，亦直接删除，无需逐一确认。
- -r 将目录及以下之档案亦逐一删除。

因此对于文件夹需要添加 -r 参数

`rm -r [folder path]`
