# EDOM Domain Error

## 描述

C 库宏 **EDOM** 表示一个域错误，它在输入参数超出数学函数定义的域时发生，errno 被设置为 EDOM。

## 声明

下面是 EDOM 宏的声明。

```
#define EDOM some_value
```

## 参数

- **NA**

## 返回值

- **NA**

## 实例

下面的实例演示了 EDOM 宏的用法。

```
#include <stdio.h>
#include <errno.h>
#include <math.h>

int main()
{
   double val;

   errno = 0;
   val = sqrt(-10);
   if(errno == EDOM) 
   {
      printf("Invalid value \n");
   }
   else 
   {
      printf("Valid value\n");
   }
   
   errno = 0;
   val = sqrt(10);
   if(errno == EDOM) 
   {
      printf("Invalid value\n");
   }
   else 
   {
      printf("Valid value\n");
   }
   
   return(0);
}
```

让我们编译并运行上面的程序，这将产生以下结果：

```
Invalid value
Valid value
```