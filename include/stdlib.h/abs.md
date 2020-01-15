# int abs(int x)

## 描述

C 库函数 **int abs(int x)** 返回 **x** 的绝对值。

## 声明

下面是 abs() 函数的声明。

```
int abs(int x)
```

## 参数

- **x** -- 完整的值。

## 返回值

该函数返回 x 的绝对值。

## 实例

下面的实例演示了 abs() 函数的用法。

```
#include <stdio.h>
#include <stdlib.h>

int main ()
{
   int a, b;

   a = abs(5);
   printf("a 的值 = %d\n", a);

   b = abs(-10);
   printf("b 的值 = %d\n", b);
   
   return(0);
}
```

让我们编译并运行上面的程序，这将产生以下结果：

```
a 的值 = 5
b 的值 = 10
```