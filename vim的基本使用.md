## 教学目的

1.让你掌握linux下路径的切换或访问

2.让你掌握基本的linux文件和目录操作

3.让你掌握vim编辑器的基本使用

## 打开终端操作

1.右键操作

2. crtl+alt+t

## 路径操作

1.切换目录 cd xxx

2.列出文件名 ls

2.获得当前绝对路径 pwd

## 文件操作

1.创建文件 touch xxx

2.拷贝文件 cp xxx yyy

3.移动或者重命名文件 mv xxx yyy

4.删除文件rm xxx

## 目录操作

1.创建目录 mkdir

2.拷贝目录 cp -a

3.移动或重命名文件 mv xxx -r

## vim的基本使用
```sh
$ sudo apt-get install vim
```
1.进入插入模式 a ， i

2.进入命令模式:Esc

3.进入底行模式:wq

4.复制命令 yy

5.粘贴 p

6.剪切 dd

7.移动 h,j,k,l

8.撤换 u

9.替换 r

## 文件的归档和压缩

* 使用gzip和gunzip对文件进行压缩和解压缩

* 使用bzip和bunzip2对文件进行压缩和解压缩

* 使用tar对文件和目录进行压缩和解压缩

## 比如：
```sh
gzip filename 
bzip2 filename
gunzip filename
bunzip2 filename 
tar czvf file.tar.gz dir
tar cjvf file.tar.bz2 dir
tar cJvf file.tar.xz dir 
tar xvf file.tar.gz
tar xvf file.tar.xz
可用 man tar 查看指令功能c为create一个新文件z为创建.gz类型v为创建步骤f为文件名
```
## linux下的两种软件包管理机制
软件包管理机制其实就是对操作系统上的应用软件进行管理的一种机制。为什么需要有软件包管理机制呢？因为影响用户对操作系统评价的决定性因素之一就是安装，升级和卸载应用软件了。对于日渐流行的 GNU/Linux 操作系统，必须得拥有简洁强大的软件包管理机制才可以。
## linux下常见的两种软件包管理机制
* RPM，是RPM Package Manager（RPM软件包管理器）的缩写，算是公认的行业标准。常用命令rpm， yum。

* Deb软件包机制， 常用命令dpkg，apt。
## Deb软件包机制的讲解

### 本地安装包管理

用于本地deb软件包的安装、卸载和查询软件包相关的信息，操作方便快捷，但是如果安装的软件包和其他软件包之间具有依赖关系，那么本地软件包管理不能很好的解决这种依赖问题。
### 在线安装包管理

用于在线安装、卸载以及查询软件包的相关信息，只要配置正确就可以通过网络来进行软件包的在线安装，这种方式就可以很好的解决软件包之间的依赖关系。
## 相关的配置文件

* /etc/apt/sources.list，包含deb软件包源的文件

* /var/lib/apt/list/* 对软件源进行更新之后的本地文件

* /var/cache/apt/archive，在线安装时软件包的下载目录

* /var/log/dpkg.log，本地软件包管理的日志文件

* /var/log/apt/*.log,在线软件包管理的日志文件

## Deb软件包的基本操作
### Deb软件包名称的组成
**比如： sl_3.03-17_amd64.deb**
```sh
sl, 表示软件包名称
3.03-17， 表示版本号和修订版本号
amd64, 表示运行机器的平台架构
deb， 表示deb软件包的后缀名
```
### 本地deb包操作命令

* 软件包安装 dpkg -i sl_3.03-17_amd64.deb

* 软件包卸载 dpkg -r sl

* 软件包彻底卸载，移除所有配置文件 dpkg -P sl

* 查看软件包的安装状态 dpkg -s sl

* 查看软件包的安装路径 dpkg -L sl

* 列出所有安装的软件包 dpkg –get-selections

### 在线管理操作命令

* 更新本地软件源 apt-get update

* 软件包安装 apt-get install sl

* 软件包卸载 apt-get remove sl

* 软件包彻底卸载 apt-get remove - -purge sl

* 二进制软件包下载 apt-get download sl

* 软件包源码下载 apt-get source sl

* 查看软件包的安装状态 apt-cache policy sl

* 查看软件包的信息 apt-cache show sl （无论是否安装）

* 升级软件包 apt-get upgrade

### 安装对应的开发工具

* atom 编辑器

* chrome浏览器

* gimp图形处理工具

* shutter 截图工具

* openssh-client 

* openssh-server
```sh
1.ssh linux@192.168.1.164(对方的ip地址)//可以控制对方用户
2.scp linux@192.168.1.164:/home/linux/文件名  . //将对方文件拷贝到当前目录下
  scp 文件名 linux@192.168.1.164:/home/linux/文件名 //把自己的文件拷贝给对方
3. sudo apt-get install  tasksel 选中 lamp
  在自己的地址栏输入127.0.0.1
```
## VNC install
```sh
$ sudo dpkg -i vnc-5.3.3.deb
```

## 安装git下载运行需要安装软件的sh
```s
$ sudo apt-get install git -y
$ git clone http://github.com/xiaojinhong2017/software.git
$ cd software
$ chmod 755 software.sh
$./software.sh
```
## 配置vim
$ chmod 755 install.sh
$ ./install.sh
```
## ktouch 
$ sudo apt-get install ktouch
$ sudo apt-get update --fix-missing //install is error, try its.
$ sudo apt-get install ktouch
$ ktouch
```
## 查看ip地址
```sh
$ ifcinfig
```
## install openssh-server
```sh
$ sudo apt-ger install openssh-server
```
## 常用命令
```sh
ls                 显示文件或目录
     -l                 列出文件详细信息（list）
     -a                 列出当前目录下所有文件及目录，包括隐藏的a（all）
     
mkdir              创建目录
     -p                 创建目录，若无父目录，则创建p（parent）
cd                 切换目录
touch              创建空文件
echo               创建带有内容的空文件
cat                查看文件内容
cp                 拷贝
mv                 移动或重命名
rm                 删除文件
      -r                递归删除，可删除子目录及文件
      -f                强制删除
```
## 课程总结

1.文件和目录操作命令作为后续课程的基础

2. vim编辑器作为后续主要代码编辑器

## 课后作业

1.不用使用上下左右键，熟练敲hello.c代码

2.会编译hello.c文件，并能运行程序。正确输出文本

3.建一个3c目录, 进入3c目录, 生成一个4a.c的文件.

4.复制上面的3c目录, 为 5d目录.

5.将5d目录改名为8b.

6.删除3c目录

## 结束
