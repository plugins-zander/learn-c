# char *getenv(const char name)

## 描述

C 库函数 **char \*getenv(const char *name)** 搜索 name 所指向的环境字符串，并返回相关的值给字符串。

## 声明

下面是 getenv() 函数的声明。

```
char *getenv(const char *name)
```

## 参数

- **name** -- 包含被请求变量名称的 C 字符串。

## 返回值

该函数返回一个以 null 结尾的字符串，该字符串为被请求环境变量的值。如果该环境变量不存在，则返回 NULL。

## 实例

下面的实例演示了 getenv() 函数的用法。

```
#include <stdio.h>
#include <stdlib.h>

int main ()
{
   printf("PATH : %s\n", getenv("PATH"));
   printf("HOME : %s\n", getenv("HOME"));
   printf("ROOT : %s\n", getenv("ROOT"));

   return(0);
}
```

让我们编译并运行上面的程序，这将产生以下结果：

```
PATH : /sbin:/usr/sbin:/bin:/usr/bin:/usr/local/bin
HOME : /
ROOT : (null)
```