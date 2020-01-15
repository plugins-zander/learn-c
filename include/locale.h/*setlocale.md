# char *setlocale(int category, const char locale)

## 描述

C 库函数 **char \*setlocale(int category, const char *locale)** 设置或读取地域化信息。

## 声明

下面是 setlocale() 函数的声明。

```
char *setlocale(int category, const char *locale)
```

 参数
category -- 这是一个已命名的常量，指定了受区域设置影响的函数类别。
LC_ALL 包括下面的所有选项。
LC_COLLATE 字符串比较。参见 strcoll()。
LC_CTYPE 字符分类和转换。例如 strtoupper()。
LC_MONETARY 货币格式，针对 localeconv()。
LC_NUMERIC 小数点分隔符，针对 localeconv()。
LC_TIME 日期和时间格式，针对 strftime()。
LC_MESSAGES 系统响应。
locale -- 如果 locale 是 NULL 或空字符串 ""，则区域名称将根据环境变量值来设置，其名称与上述的类别名称相同。



## 返回值

如果成功调用 setlocale()，则返回一个对应于区域设置的不透明的字符串。如果请求无效，则返回值是 NULL。

## 实例

下面的实例演示了 setlocale() 函数的用法。

```
#include <locale.h>
#include <stdio.h>
#include <time.h>
 
int main ()
{
   time_t currtime;
   struct tm *timer;
   char buffer[80];
 
   time( &currtime );
   timer = localtime( &currtime );
 
   printf("Locale is: %s\n", setlocale(LC_ALL, "en_GB.UTF-8"));
   strftime(buffer,80,"%c", timer );
   printf("Date is: %s\n", buffer);
 
  
   printf("Locale is: %s\n", setlocale(LC_ALL, "de_DE.UTF-8"));
   strftime(buffer,80,"%c", timer );
   printf("Date is: %s\n", buffer);
 
   return(0);
}
/*
Locale is: en_GB
Date is: Thu 23 Aug 2012 06:39:32 MST
Locale is: de_DE
Date is: Do 23 Aug 2012 06:39:32 MST
*/
```

