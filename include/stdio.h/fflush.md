# int fflush(FILE *stream)

## 描述

C 库函数 **int fflush(FILE \*stream)** 刷新流 stream 的输出缓冲区。

## 声明

下面是 fflush() 函数的声明。

```
int fflush(FILE *stream)
```

## 参数

- **stream** -- 这是指向 FILE 对象的指针，该 FILE 对象指定了一个缓冲流。

## 返回值

如果成功，该函数返回零值。如果发生错误，则返回 EOF，且设置错误标识符（即 feof）。

## 实例

下面的实例演示了 fflush() 函数的用法。

```
#include <stdio.h>
#include <string.h>
 
int main()
{
 
   char buff[1024];
 
   memset( buff, '\0', sizeof( buff ));
 
   fprintf(stdout, "启用全缓冲\n");
   setvbuf(stdout, buff, _IOFBF, 1024);
 
   fprintf(stdout, "这里是 runoob.com\n");
   fprintf(stdout, "该输出将保存到 buff\n");
   fflush( stdout );
 
   fprintf(stdout, "这将在编程时出现\n");
   fprintf(stdout, "最后休眠五秒钟\n");
 
   sleep(5);
 
   return(0);
}

/*
让我们编译并运行上面的程序，这将产生以下结果。在这里，程序把缓冲输出保存到 buff，直到首次调用 fflush() 为止，然后开始缓冲输出，最后休眠 5 秒钟。它会在程序结束之前，发送剩余的输出到 STDOUT。

启用全缓冲
这里是 runoob.com
该输出将保存到 buff
这将在编程时出现
最后休眠五秒钟
*/

```

