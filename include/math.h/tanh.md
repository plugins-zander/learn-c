# double tanh(double x)

## 描述

C 库函数 **double tanh(double x)** 返回 **x** 的双曲正切。

## 声明

下面是 tanh() 函数的声明。

```
double tanh(double x)
```

## 参数

- **x** -- 浮点值。

## 返回值

该函数返回 x 的双曲正切。

## 实例

下面的实例演示了 tanh() 函数的用法。

```
#include <stdio.h>
#include <math.h>

int main ()
{
   double x, ret;
   x = 0.5;

   ret = tanh(x);
   printf("%lf 的双曲正切是 %lf 度", x, ret);
   
   return(0);
}
```

让我们编译并运行上面的程序，这将产生以下结果：

```
0.500000 的双曲正切是 0.462117 度
```