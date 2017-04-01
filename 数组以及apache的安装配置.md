## 教学目的

1.让你掌握整型数组以及字符数组的定义以及使用

2.让你掌握冒泡排序和简单选择排序

3.让你掌握apache的安装以及CGI模块的配置

4.让你掌握超级用户的切换

## 数组

数组数据结构，它可以存储一个固定大小的相同类型元素的顺序集合。数组是用来存储一系列数据，但它往往被认为是一系列相同类型的变量。
所有的数组都是由连续的内存位置组成。最低的地址对应第一个元素，最高的地址对应最后一个元素。
```sh
示例代码：

//数组的定义，初始化以及赋值
int  a[5] = {1,2,3,4,5};
int  b[3];
b[0] = 0;
b[1] = 1;
b[2] = 2;

//访问
int i;
for (i = 0 ; i < 5; i++)
{
   printf("a[%d] = %d\n", i,  a[i]);
}
```

## 冒泡排序(902.sort.c)

它重复地走访过要排序的数列，一次比较两个元素，如果他们的顺序错误就把他们交换过来。走访数列的工作是重复地进行直到没有再需要交换，
也就是说该数列已经排序完成。(引自百度百科)

## 简单选择排序(903.sort.c)

设所排序序列的记录个数为n。i取1,2,…,n-1,从所有n-i+1个记录（Ri,Ri+1,…,Rn）中找出排序码最小的记录，与第i个记录交换。执行n-1趟 
后就完成了记录序列的排序。(引自百度百科)

## 字符串数组
```sh
  示例代码：
  
  //定义数组
  char s[5] = {'a', 'b', 'c', 'd', 'e'}; //不是字符串   
  char s1[64] = "helloworld"; //字符串    
  printf("%s\n", s1);
```
注意：**字符串的末尾会被自动填充一个’\0’，因此字符串会多占用一个字节**
## 安装apache web服务器

安装步骤：
```sh
1. sudo apt-get update
```
## tasksel

用tasksel可以方便安装dns server,lamp, kubuntu desktop, ubuntu desktop, xubuntu之类的软件包。
这个软件在server版是预装的，而在桌面版里是不预装的，想用的话需先安装：
```sh
$ sudo apt-get install tasksel
```
使用这个软件的话就用下面命令：
```sh
 $ sudo tasksel
```
选择LAMP server选项， 安装过程中需要设置mysql数据的root密码， 统一设置为123456。

重启Apache服务器。
```sh
sudo /etc/init.d/apache2 restart
```

## CGI

CGI(Common Gateway Interface) 是WWW技术中最重要的技术之一，有着不可替代的重要地位。CGI是外部应用（CGI程序）与Web服务器之间的接口标准，是在CGI程序和Web服务器之间传递信息的过程。(引自百度百科)
配置CGI步骤：
```sh
1.sudo ln -s /etc/apache2/mods-available/cgi.load /etc/apache2/mods-enabled/cgi.load
```
2.重启 apache 服务器
```sh
service apache2 restart 
```
3.需要运行的cgi文件的存放路径为 /usr/lib/cgi-bin

## hello
```sh
#include <stdio.h>
#include <string.h>
int main(void)
{
  printf("Content type: text/html\n\n");
  printf("<html>\n");
  printf("<head><title>An html page from a cgi</title>\n");
  printf("<style type=\"text/css\">");
  printf("h1,h2,h3,h4,h5,h6 {color: blue; text-align: right;}");
  printf("</style></head>");
  printf("<body>\n");
  printf("<h1>Hello world!</h1>\n");
  printf("</body>\n");
  printf("</html>\n");

  fflush(stdout);
  return 0;
}
```
编译完成后 在atom 跟 终端将可执行文件拷贝到 usr/lib/cgi-bin/目录下
插入图片时要把图片保存到/var/www/html下
/localhost/cgi-bin/
local --->/var/www/html
cgi-bin --->usr/lib/cgi-lib/
用浏览器打开:
```sh
http://localhost/cgi-bin/cgi
```
## 进入Linux系统的超级用户(root)
1.激活超级用户
    sudo passwd root
    
2.切换到root用户
    su -
3.退出root用户
    exit

## 浏览器中查看CGI程序的运行结果

浏览器地址栏： 127.0.0.1/cgi-bin/xxx
## 安装atom

1.打开浏览器， 在地址栏中输入： https://atom.io/ 下载atom安装包。

2.使用dpkg进行安装。
```sh
$ sudo dpkg -i atom-64.deb
```

3.需要安装的第三方库
```sh
    activate-power-mode：动感插件 atl + ctrl + o :打开插件
    vim-mode：vim模式
    ex-mode：实现:w功能
    monokai：高亮显示
    platformio-ide-terminal : Terminal
    atom-ternjs：JavaScript 自动补全
    autoprefixer：给 CSS 添加适当的前缀
    color-picker：选颜色
    emmet：写 HTML 的神器
    atom-beautify：美化代码，空格啊什么什么的
    autoclose-html：HTML自动补全闭标签
    file-icons: 增加许多图标,在侧边蓝文件名前面的icon,,很赞
    autocomplete-plus: 自动补全插件, 有HTML, CSS, python 等
    highlight-selected: 高亮当前所选的文字, 双击后全文这个词或变量都会变高亮.
    linter: 检察语法错误, 有less等.
    Nuclide: facebook 开源的开发IDE.
    Open In Browser: 右键打开浏览器.
```
## HTML 语言
```sh
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```
## 作业

    编程： 定义数组并赋值, 计算该数组中所有元素的和。
    编程： 数组的反向输出
    编程： 求数组极值(最大值), 数组值为 {1,23,10,89,35}
    编程： 统计一个文件中字母和数字的个数
    编程： 输出 杨辉三角
    编程： 从数组中找出相同的数， 并输入所有相同数的数组下标量。 例如： a[5] ={1,2,3,1,1}; 输入结果是： a[0], a[3], a[4]。
    编程： 同题增加难度。 例如： a[9] = { 1, 2, 3, 3, 2, 1, 1, 2, 3}
    1 = a[0], a[5], a[6]
    2 = a[1], a[4], a[7]
    3 = a[2], a[3], a[8]

课程总结

    数组的赋值、遍历以及排序作为重点内容
    安装配置apache服务器为后续CGI程序运行作准备
## 参考文献

[HTML语法教程]：（http://www.w3school.com.cn/html/）

[css 语法教程]：（http://www.w3school.com.cn/css/index.asp）

[配色]：(http://www.bootcss.com/p/websafecolors/)
## 代码示例
示例1：
```sh
#include <stdio.h>

int main(void)
{
    printf("content type : text/html\n\n");
    printf("<html lang=en>\n");
    printf("<head><meta charset=\"UTF-8\"><title>An html page from a cgi</title>\n");
    printf("<style type=\"text/css\">\n");
    printf("h2{color: blue; text-align: left;background-color: #CCCCCC}");
    printf("</style></head>\n");
    printf("<body>\n");
    printf("<h2>个人疾病史</h2>\n");
    printf("<p style=font-size:14px;color:red;>问卷填写说明：所有标注！图标为必填项！</p>\n");
    printf("<p>01.您是否患有下列疾病，若有请选择，否则不用填写.</p>\n");
    printf("<table>\n");
    printf("<tr>\n");
    printf("<td><input type = \"checkbox\" name =\"illness\" value = \"0\"/>1型糖尿病</td>\n");
    printf("<td><input type = \"checkbox\" name =\"illness\" value = \"0\"/>2型糖尿病</td>\n");
    printf("<td><input type = \"checkbox\" name =\"illness\" value = \"0\"/>高血压</td>\n");
    printf("<td><input type = \"checkbox\" name =\"illness\" value = \"0\"/>血脂异常</td>\n");
    printf("</tr>\n");
    printf("<tr>\n");
    printf("<td><input type = \"checkbox\" name =\"illness\" value = \"0\"/>痛风/高尿酸血症</td>\n");
    printf("<td><input type = \"checkbox\" name =\"illness\" value = \"0\"/>冠心病/脑卒中</td>\n");
    printf("<td><input type = \"checkbox\" name =\"illness\" value = \"0\"/>慢性支气管炎</td>\n");
    printf("<td><input type = \"checkbox\" name =\"illness\" value = \"0\"/>肺气肿</td>\n");
    printf("</tr>\n");
    printf("<tr>\n");
    printf("<td><input type = \"checkbox\" name =\"illness\" value = \"0\"/>肺癌</td>\n");
    printf("<td><input type = \"checkbox\" name =\"illness\" value = \"0\"/>前列腺疾病史</td>\n");
    printf("<td><input type = \"checkbox\" name =\"illness\" value = \"0\"/>前列腺癌</td>\n");
    printf("<td><input type = \"checkbox\" name =\"illness\" value = \"0\"/>骨质疏松症</td>\n");
    printf("</tr>\n");
    printf("<tr>\n");
    printf("<td><input type = \"checkbox\" name =\"illness\" value = \"0\"/>既往骨折史</td>\n");
    printf("<td><input type = \"checkbox\" name =\"illness\" value = \"0\"/>类风湿性关节炎</td>\n");
    printf("</tr>\n");
    printf("</table>\n");
    printf("<p>02.您是否患有与骨质疏松紧密相关的疾病，包括成年骨不全症，为治疗的长期甲状腺机能抗进，性腺机能减退，慢性营养不良以及慢性肝病等?</p>\n");
    printf("<form>\n");
    printf("<input type=\"radio\" name =\"choose\" value=\"yes\"/>是\n");
    printf("<input type=\"radio\" name =\"choose\" value=\"no\"/>否\n");
    printf("</form>\n");
    printf("<p>03.您是否目前正在服用或曾经服用过肾上腺皮质激素（如强的松，地塞米松等）超过三个月？</p>\n");
    printf("<form>\n");
    printf("<input type=\"radio\" name =\"choose\" value=\"yes\"/>是\n");
    printf("<input type=\"radio\" name =\"choose\" value=\"no\"/>否\n");
    printf("<p align=\"right\"><input type=\"submit\" style=\"color: white;background-color:blue;\" value=\"上一页\"><input type=\"submit\" style=\"color:white; background-color:green;\" value=\"暂存问卷\"><input type=\"submit\" style=\"color:white;background-color:blue;\" value=\"下一页\">\n");
    printf("</form>\n");
    printf("</body>\n");
    printf("</html>\n");
    fflush(stdout);
    return 0;
}
```
示例2：
```sh
#include <stdio.h>

int main(void)
{
  printf("Content type : text/html\n\n");
printf("<html long=en>\n");
    printf("<head><meta charset=\"UTF-8\">\n");
        printf("<title>An html page</title>\n");
        printf("<style type=\"text/css\">\n");
printf("</style></head>\n");
printf("<body>\n");
    printf("<h1>4.H5技术框架</h1>\n");
    printf("<h2>需要基本功</h2>\n");
    printf("<ul>\n");
        printf("<li>linux基本操作</li>\n");
        printf("<li>简单的shell编程能力</li>\n");
        printf("<li>精通javascript</li>\n");
        printf("<li>精通python</li>\n");
    printf("</ul>\n");
    printf("<h2>计算机体系理论基础课</h2>\n");
    printf("<ul>\n");
        printf("<li>操作系统原理</li>\n");
        printf("<li>数据结构与算法</li>\n");
        printf("<li>网络协议与通信</li>\n");
        printf("<li>数据库理论，将会学习到关系型和非关系型数据库。将以Mysql和MongdoDB为代表</li>\n");
    printf("</ul>\n");
    printf("<h2>业界流行的技术与前沿框架</h2>\n");
    printf("<ul>\n");
        printf("<li>Node.js</li>\n");
        printf("<li>Diango</li>\n");
        printf("<li>Docker虚拟化技术</li>\n");
        printf("<li>Meteor</li>\n");
        printf("<li>Bootstrap</li>\n");
        printf("<li>MongDB与H5 API接口应用</li>\n");
    printf("</ul>\n");
    printf("<p>\n");
    printf("<img src=\"../images/1.jpeg\" alt=\"samile face\" align=\"left\" height=\"800\" width=\"1000\">\n");
    printf("</p>\n");
    printf("</body>\n");
    printf("</html>\n");
    fflush(stdout);
    return 0;
}
```
