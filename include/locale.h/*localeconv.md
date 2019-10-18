# struct lconv *localeconv(void)

## 描述

C 库函数 **struct lconv \*localeconv(void)** 设置或读取地域化信息。它会返回一个 **lconv** 结构类型的对象。

## 声明

下面是 localeconv() 函数的声明。

```
struct lconv *localeconv(void)
```

## 参数

- **NA**

## 返回值

该函数返回一个指向当前区域 **struct lconv** 的指针，它的结构如下：

```
typedef struct {
   char *decimal_point;
   char *thousands_sep;
   char *grouping;    
   char *int_curr_symbol;
   char *currency_symbol;
   char *mon_decimal_point;
   char *mon_thousands_sep;
   char *mon_grouping;
   char *positive_sign;
   char *negative_sign;
   char int_frac_digits;
   char frac_digits;
   char p_cs_precedes;
   char p_sep_by_space;
   char n_cs_precedes;
   char n_sep_by_space;
   char p_sign_posn;
   char n_sign_posn;
} lconv
```

## 实例

下面的实例演示了 localeconv() 函数的用法。

```
#include <locale.h>
#include <stdio.h>

int main ()
{
   struct lconv * lc;

   setlocale(LC_MONETARY, "it_IT");
   lc = localeconv();
   printf("Local Currency Symbol: %s\n",lc->currency_symbol);
   printf("International Currency Symbol: %s\n",lc->int_curr_symbol);

   setlocale(LC_MONETARY, "en_US");
   lc = localeconv();
   printf("Local Currency Symbol: %s\n",lc->currency_symbol);
   printf("International Currency Symbol: %s\n",lc->int_curr_symbol);

   setlocale(LC_MONETARY, "en_GB");
   lc = localeconv();
   printf ("Local Currency Symbol: %s\n",lc->currency_symbol);
   printf ("International Currency Symbol: %s\n",lc->int_curr_symbol);

   printf("Decimal Point = %s\n", lc->decimal_point);
   
   return 0;
}
```

让我们编译并运行上面的程序，这将产生以下结果：

```
Local Currency Symbol: EUR
International Currency Symbol: EUR
Local Currency Symbol: $
International Currency Symbol: USD
Local Currency Symbol: £
International Currency Symbol: GBP
Decimal Point = .
```