# C_Program-Test.h

This is a library for testing
Using bit fields in C language
Currently implemented functions:
1. Decompose char into 8 bits
2. Decompose variables such as int and float into 32-bit


这是一个用来测试的库
使用C语言的位域
目前实现的功能：
1、将char分解为8位
2、将int、float等变量分解为32位

Usage eg:
使用方法：
```c
#include <stdio.h>
#include "Test.h"

int main()
{
    // 对字符A拆解
    char char_A = 'A';
    printf("%d\n", char_A);
    decode_char(char_A);
    putchar('\n');

    // 对整数114514拆解
    int int_A = 114514;
    printf("%d\n", int_A);

    decode_int(int_A);
    putchar('\n');

    // 测试修改之后的值
    int a = 0;
    decode_int(a);
    putchar('\n');

    data_int_unionTypeDef int_A_union;
    int_A_union.all = a;
    int_A_union.decode.byte0.decode.bit0 = 1;
    int_A_union.decode.byte1.decode.bit1 = 1;
    int_A_union.decode.byte2.decode.bit2 = 1;
    int_A_union.decode.byte3.decode.bit3 = 1;

    decode_int(int_A_union.all);
    putchar('\n');

    float f = 123456789.123456789;
    int_A_union.all = *(int*)&f;
    decode_int(int_A_union.all);

    return 0;
}
```
