# ERANGE Range Error

## 描述

C 库宏 **ERANGE** 表示一个范围错误，它在输入参数超出数学函数定义的范围时发生，errno 被设置为 ERANGE。

## 声明

下面是 ERANGE 宏的声明。

```
#define ERANGE some_value
```

## 参数

- **NA**

## 返回值

- **NA**

## 实例

下面的实例演示了 ERANGE 宏的用法。

```
#include <stdio.h>
#include <errno.h>
#include <math.h>
 
int main()
{
   double x;
   double value;
 
   x = 2.000000;
   value = log(x);
   
   if( errno == ERANGE ) 
   {
      printf("Log(%f) is out of range\n", x);
   }
   else 
   {
      printf("Log(%f) = %f\n", x, value);
   }
 
   x = 1.000000;
   value = log(x);
   
   if( errno == ERANGE ) 
   {
      printf("Log(%f) is out of range\n", x);
   }
   else 
   {
      printf("Log(%f) = %f\n", x, value);
   }
   
   x = 0.000000;
   value = log(x);
   
   if( errno == ERANGE ) 
   {
      printf("Log(%f) is out of range\n", x);
   }
   else 
   {
      printf("Log(%f) = %f\n", x, value);
   }
   
   return 0;
}
/*
Log(2.000000) = 0.693147
Log(1.000000) = 0.000000
Log(0.000000) = -inf
*/
```

