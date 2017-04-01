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
