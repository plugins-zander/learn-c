# div_t div(int numer, int denom)

## 描述

C 库函数 **div_t div(int numer, int denom)** 把 **numer（分子）**除以 **denom（分母）**。

## 声明

下面是 div() 函数的声明。

```
div_t div(int numer, int denom)
```

## 参数

- **numer** -- 分子。
- **denom** -- 分母。

## 返回值

该函数返回定义在 <cstdlib> 中的结构中的值，该结构有两个成员，如 div_t:*int quot; int rem;*。

## 实例

下面的实例演示了 div() 函数的用法。

```
#include <stdio.h>
#include <stdlib.h>

int main()
{
   div_t output;

   output = div(27, 4);
   printf("(27/ 4) 的商  = %d\n", output.quot);
   printf("(27/4) 的余数 = %d\n", output.rem);

   output = div(27, 3);
   printf("(27/ 3) 的商 = %d\n", output.quot);
   printf("(27/3) 的余数 = %d\n", output.rem);

   return(0);
}
```

让我们编译并运行上面的程序，这将产生以下结果：

```
(27/ 4) 的商 = 6
(27/4) 的余数 = 3
(27/ 3) 的商 = 9
(27/3) 的余数 = 0
```