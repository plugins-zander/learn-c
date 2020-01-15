# int isxdigit(int c)

## 描述

C 库函数 **int isxdigit(int c)**检查所传的字符是否是十六进制数字。

十六进制一般用数字 0 到 9 和字母 A 到 F（或 a~f）表示，其中 A~F 表示 10~15: **0 1 2 3 4 5 6 7 8 9 a b c d e f A B C D E F**。

## 声明

下面是 isxdigit() 函数的声明。

```
int isxdigit(int c);
```

## 参数

- **c** -- 这是要检查的字符。

## 返回值

如果 c 是一个十六进制数字，则该函数返回非零值（true），否则返回 0（false）。

## 实例

下面的实例演示了 isxdigit() 函数的用法。

```
#include <stdio.h>
#include <ctype.h>
 
int main()
{
   char var1[] = "tuts";
   char var2[] = "0xE";
  
   if( isxdigit(var1[0]) )
   {
     printf("var1 = |%s| 是十六进制数字\n", var1 );
   }
   else
   {
     printf("var1 = |%s| 不是十六进制数字\n", var1 );
   }
   
   if( isxdigit(var2[0] ))
   {
     printf("var2 = |%s| 是十六进制数字\n", var2 );
   }
   else
   {
     printf("var2 = |%s| 不是十六进制数字\n", var2 );
   }
   
   return(0);
}

/*
var1 = |tuts| 不是十六进制数字
var2 = |0xE| 是十六进制数字


*/
```

