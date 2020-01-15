# char *strcpy(char *dest, const char *src)

## 描述

C 库函数 **char \*strcpy(char *dest, const char *src)** 把 **src** 所指向的字符串复制到 **dest**。

需要注意的是如果目标数组 dest 不够大，而源字符串的长度又太长，可能会造成缓冲溢出的情况。

## 声明

下面是 strcpy() 函数的声明。

```
char *strcpy(char *dest, const char *src)
```

## 参数

- **dest** -- 指向用于存储复制内容的目标数组。
- **src** -- 要复制的字符串。

## 返回值

该函数返回一个指向最终的目标字符串 dest 的指针。

## 实例

下面的实例演示了 strcpy() 函数的用法。

```
#include <stdio.h>
#include <string.h>
 
int main()
{
   char src[40];
   char dest[100];
  
   memset(dest, '\0', sizeof(dest));
   strcpy(src, "This is runoob.com");
   strcpy(dest, src);
 
   printf("最终的目标字符串： %s\n", dest);
   
   return(0);
}
```

让我们编译并运行上面的程序，这将产生以下结果：

```
最终的目标字符串： This is runoob.com
```

```
#include <stdio.h>
#include <string.h>
 
int main ()
{
  char str1[]="Sample string";
  char str2[40];
  char str3[40];
  strcpy (str2,str1);
  strcpy (str3,"copy successful");
  printf ("str1: %s\nstr2: %s\nstr3: %s\n",str1,str2,str3);
  return 0;
}
```

让我们编译并运行上面的程序，这将产生以下结果：

```
str1: Sample string
str2: Sample string
str3: copy successful
```