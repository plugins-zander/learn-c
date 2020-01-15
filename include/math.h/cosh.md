# double cosh(double x)

## 描述

C 库函数 **double cosh(double x)** 返回 **x** 的双曲余弦。

## 声明

下面是 cosh() 函数的声明。

```
double cosh(double x)
```

## 参数

- **x** -- 浮点值。

## 返回值

该函数返回 x 的双曲余弦。

## 实例

下面的实例演示了 cosh() 函数的用法。

```
#include <stdio.h>
#include <math.h>

int main ()
{
   double x;

   x = 0.5;
   printf("%lf 的双曲余弦是 %lf\n", x, cosh(x));

   x = 1.0;
   printf("%lf 的双曲余弦是 %lf\n", x, cosh(x));

   x = 1.5;
   printf("%lf 的双曲余弦是 %lf\n", x, cosh(x));

   return(0);
}
```

让我们编译并运行上面的程序，这将产生以下结果：

```
0.500000 的双曲余弦是 1.127626
1.000000 的双曲余弦是 1.543081
1.500000 的双曲余弦是 2.352410
```

 