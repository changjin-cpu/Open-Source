# C语言的编译
## 预处理（Preprocessing）
预处理是编译过程的第一步，它处理源文件中的预处理指令（以 # 开头的指令）。这些指令包括：

#include：包含（或插入）另一个文件的内容到当前位置。
#define、#undef：定义或取消定义宏。
#if、#ifdef、#ifndef、#else、#elif、#endif：条件编译指令。
#pragma：提供编译器特定的指令。
预处理后的结果是一个纯文本文件，但其中的宏已被展开，#include 指令已被相应的文件内容替换。
## 编译（Compilation）
编译阶段将预处理后的文件转换成汇编语言（Assembly Language）。汇编语言是一种低级语言，比机器代码更易于人类阅读，但更接近机器代码。在这一阶段，编译器会进行词法分析、语法分析、语义分析、优化以及代码生成等复杂任务。

## 汇编（Assembly）
汇编阶段将汇编语言代码转换成机器代码。这通常是由汇编器（Assembler）完成的。机器代码是计算机可以直接执行的指令序列。

## 链接（Linking）
在编译和汇编单个源文件后，我们得到的是目标代码（Object Code），通常是 .o 或 .obj 文件。这些文件包含了程序的机器代码，但可能还包含了对其他文件（如库文件）中函数或变量的引用。链接器的任务是将这些目标代码文件以及所需的库文件合并成一个可执行文件或库文件。

链接过程分为两个主要阶段：

静态链接：在程序执行之前，将程序中引用的所有库函数或变量直接复制到最终的可执行文件中。这样，程序在运行时就不再需要这些库文件。
动态链接：程序在运行时动态地加载所需的库。这种方式可以节省空间，因为多个程序可以共享同一个库文件。
## 写在最后
C 语言的编译过程包括预处理、编译、汇编和链接四个主要阶段。这个过程将人类可读的源代码转换成计算机可以直接执行的机器代码。GCC 是一种广泛使用的 C 语言编译器，