# void *malloc(size_t size)

## 描述

C 库函数 **void \*malloc(size_t size)** 分配所需的内存空间，并返回一个指向它的指针。

## 声明

下面是 malloc() 函数的声明。

```
void *malloc(size_t size)
```

## 参数

- **size** -- 内存块的大小，以字节为单位。

## 返回值

该函数返回一个指针 ，指向已分配大小的内存。如果请求失败，则返回 NULL。

## 实例

下面的实例演示了 malloc() 函数的用法。

```
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
 
int main()
{
   char *str;
 
   /* 最初的内存分配 */
   str = (char *) malloc(15);
   strcpy(str, "runoob");
   printf("String = %s,  Address = %u\n", str, str);
 
   /* 重新分配内存 */
   str = (char *) realloc(str, 25);
   strcat(str, ".com");
   printf("String = %s,  Address = %u\n", str, str);
 
   free(str);
 
   return(0);
}
/*
String = runoob,  Address = 3662685808
String = runoob.com,  Address = 3662685808
*/
```

