## 教学目的

1.让你掌握循环中break和continue用法
   
2.让你掌握循环嵌套
    
3.让你利用break，continue完成如下作业

## for循环以及break continue

## break

1.当 break 语句出现在一个循环内时，循环会立即终止，且程序流将继续执行紧接着循环的下一条语句

2.使用的是嵌套循环（即一个循环内嵌套另一个循环），break 语句会停止执行最内层的循环，然后开始执行该块之后的下一行代码

注意：

1. **循环中break语句之后的代码不再执行**

2. **循环中break语句只能跳出最近的一层循环**

## continue

一个循环体立刻停止本次循环迭代，并重新开始下次循环迭代

注意：

1.**循环中continue语句之后的代码不再执行**

## 代码示例
```sh
#include <stdio.h>
int main()
{
int i = 0;
int j = 0;
for(j = 0;j < 3;j++)
{
printf("j = %d\n", j);
   for(i = 0; i < 10;j++)
  {
     if(i == 5)
    {
//直接跳出循环，执行之后的代码
//c 语言中只能跳出最近的一层循环
          break;
     }
     printf("i = %d\n", i);

   }
   printf("after i循环 ...\n");

}
printf("after j循环 ...\n");
return 0;
}
```
