# double fabs(double x)

## 描述

C 库函数 **double fabs(double x)** 返回 **x** 的绝对值。

## 声明

下面是 fabs() 函数的声明。

```
double fabs(double x)
```

## 参数

- **x** -- 浮点值。

## 返回值

该函数返回 x 的绝对值。

## 实例

下面的实例演示了 fabs() 函数的用法。

```
#include <stdio.h>
#include <math.h>

int main ()
{
   int a, b;
   a = 1234;
   b = -344;
  
   printf("%d 的绝对值是 %lf\n", a, fabs(a));
   printf("%d 的绝对值是 %lf\n", b, fabs(b));
   
   return(0);
}
```

让我们编译并运行上面的程序，这将产生以下结果：

```
1234 的绝对值是 1234.000000
-344 的绝对值是 344.000000
```

 