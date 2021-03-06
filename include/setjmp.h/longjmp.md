# void longjmp(jmp_buf environment, int value)

## 描述

C 库函数 **void longjmp(jmp_buf environment, int value)** 恢复最近一次调用 **setjmp()** 宏时保存的环境，**jmp_buf** 参数的设置是由之前调用 setjmp() 生成的。

## 声明

下面是 longjmp() 函数的声明。

```
void longjmp(jmp_buf environment, int value)
```

## 参数

- **environment** -- 这是一个类型为 **jmp_buf** 的对象，包含了调用 setjmp 时存储的环境信息。
- **value** -- 这是 **setjmp** 表达式要判断的值。

## 返回值

该函数不返回任何值。

## 实例

下面的实例演示了 longjmp() 函数的用法。

```
#include <stdio.h>
#include <setjmp.h>

static jmp_buf buf;

void second(void) {
    printf("second\n");         // 打印
    longjmp(buf,1);             // 跳回setjmp的调用处 - 使得setjmp返回值为1
}

void first(void) {
    second();
    printf("first\n");          // 不可能执行到此行
}

int main() {   
    if ( ! setjmp(buf) ) {
        first();                // 进入此行前，setjmp返回0
    } else {                    // 当longjmp跳转回，setjmp返回1，因此进入此行
        printf("main\n");       // 打印
    }

    return 0;
}
```

让我们编译并运行上面的程序，这将产生以下结果：

```
second
main
```