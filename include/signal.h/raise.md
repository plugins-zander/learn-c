# int raise(int sig)

## 描述

C 库函数 **int raise(int sig)** 会促使生成信号 **sig**。**sig** 参数与 SIG 宏兼容。

## 声明

下面是 raise() 函数的声明。

```
int raise(int sig)
```

## 参数

- **sig** -- 要发送的信号码。下面是一些重要的标准信号常量：

| 宏      | 信号                                                         |
| ------- | ------------------------------------------------------------ |
| SIGABRT | (Signal Abort) 程序异常终止。                                |
| SIGFPE  | (Signal Floating-Point Exception) 算术运算出错，如除数为 0 或溢出（不一定是浮点运算）。 |
| SIGILL  | (Signal Illegal Instruction) 非法函数映象，如非法指令，通常是由于代码中的某个变体或者尝试执行数据导致的。 |
| SIGINT  | (Signal Interrupt) 中断信号，如 ctrl-C，通常由用户生成。     |
| SIGSEGV | (Signal Segmentation Violation) 非法访问存储器，如访问不存在的内存单元。 |
| SIGTERM | (Signal Terminate) 发送给本程序的终止请求信号。              |

## 返回值

如果成功该函数返回零，否则返回非零。

## 实例

下面的实例演示了 raise() 函数的用法。

```
#include <signal.h>
#include <stdio.h>

void signal_catchfunc(int);

int main()
{
    int ret;

   ret = signal(SIGINT, signal_catchfunc);

   if( ret == SIG_ERR) 
   {
      printf("错误：不能设置信号处理程序。\n");
      exit(0);
   }
   printf("开始生成一个信号\n");
   ret = raise(SIGINT);
   if( ret !=0 ) 
   {
      printf("错误：不能生成 SIGINT 信号。\n");
      exit(0);
   }

   printf("退出...\n");
   return(0);
}

void signal_catchfunc(int signal)
{
   printf("!! 信号捕获 !!\n");
}
```

让我们编译并运行上面的程序，这将产生以下结果：

```
开始生成一个信号
!! 信号捕获 !!
退出...
```