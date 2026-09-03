# git

一个用于学习 Git 版本控制的基础示例仓库，示例程序为经典的 C++ "Hello, World!"。

## 项目简介

本仓库用于演示 Git 的基本提交流程，包含：

- 初始化本地仓库
- 添加与提交文件
- 推送到远程仓库（GitHub）

## 项目结构

```
git/
├── README.md       # 项目说明文档
└── HelloWorld.cpp  # 示例 C++ 程序
```

## 使用说明

编译并运行 HelloWorld.cpp：

```bash
# g++ 编译
g++ HelloWorld.cpp -o HelloWorld

# 运行（Windows）
HelloWorld.exe
# 运行（Linux / macOS）
./HelloWorld
```

预期输出：

```
Hello, World!
```

## C++ 发展历史

C++ 是一种通用的、支持多范式（面向过程、面向对象、泛型、函数式等）的编程语言，由丹麦计算机科学家 **比雅尼·斯特劳斯特鲁普（Bjarne Stroustrup）** 于 1979 年在贝尔实验室（Bell Labs）开始设计。其关键发展节点如下：

- **1979–1983 年（诞生期）**：Stroustrup 在 C 语言的基础上加入类（class）、继承、重载等特性，最初被称为 **"C with Classes"（带类的 C）**。1983 年正式更名为 **C++**，"++" 取自 C 语言的自增运算符，寓意"C 语言的进阶"。
- **1985 年（首次发布）**：C++ 首个商业版本发布，同年 Stroustrup 出版经典著作《The C++ Programming Language》。
- **1989–1990 年（演进期）**：引入模板（template）、异常处理（exception）、命名空间（namespace）等现代特性；1990 年发布《The Annotated C++ Reference Manual》，为标准化奠定基础。
- **1998 年（C++98）**：ISO 发布第一个 C++ 国际标准 ISO/IEC 14882:1998，语言进入标准化时代。
- **2003 年（C++03）**：对 C++98 进行小幅修订与勘误，未引入大的语言特性。
- **2011 年（C++11，里程碑）**：被称为"现代 C++"的起点，引入 `auto`、lambda 表达式、右值引用与移动语义、智能指针（`shared_ptr`/`unique_ptr`）、范围 for 循环等大量特性，显著改变 C++ 的编写风格。
- **2014 年（C++14）**：在 C++11 基础上小幅增强，完善泛型 lambda、`auto` 返回类型推导等。
- **2017 年（C++17）**：引入结构化绑定、`std::optional`/`std::variant`、并行算法、`if constexpr` 等特性。
- **2020 年（C++20，又一次飞跃）**：引入**概念（concepts）**、协程（coroutines）、范围库（ranges）、三路比较运算符 `<=>`（太空船运算符）等重量级特性。
- **2023 年（C++23）**：继续完善标准库与语言特性，如 `std::expected`、`std::print`、deducing this 等；后续 C++26 标准亦在制定中。

如今 C++ 凭借高性能与对底层硬件的精细控制，广泛应用于操作系统、游戏引擎、嵌入式系统、高性能计算、金融交易系统等领域，是 TIOBE 等编程语言排行榜中长期位居前列的语言之一。

## HelloWorld.cpp 逐行讲解

源代码如下：

```cpp
#include <iostream>
using namespace std;
int main() {
    cout << "Hello, World!" << std::endl;
    return 0;
}
```

各行作用如下：

| 行号 | 代码 | 作用说明 |
| :-- | :--- | :--- |
| 1 | `#include <iostream>` | **预处理指令**。以 `#` 开头的行会在编译前由预处理器处理，此行将标准输入输出流头文件 `<iostream>` 的内容包含进来，从而可以使用 `cout`（标准输出对象）等输入输出功能。 |
| 2 | `using namespace std;` | **命名空间声明**。标准库中的名称（如 `cout`）都定义在命名空间 `std` 中，该语句声明后续代码直接使用 `std` 命名空间，之后便可简写 `cout` 而不必写 `std::cout`。 |
| 3 | `int main() {` | **主函数定义**。`main` 是 C/C++ 程序的入口函数，程序总是从这里开始执行；`int` 表示该函数返回一个整数（程序退出码），`{` 开始函数体。 |
| 4 | `cout << "Hello, World!" << std::endl;` | **输出语句**。`cout` 是标准输出流对象，通常对应屏幕；`<<` 是**流插入运算符**，把右侧内容送入 `cout` 输出；`"Hello, World!"` 是要打印的字符串字面量；`std::endl` 表示**结束当前行并刷新输出缓冲区**（相当于换行符），此处使用了带 `std::` 前缀的完整限定写法。 |
| 5 | `return 0;` | **返回语句**。向操作系统返回退出码 `0`，习惯上 `0` 表示程序正常结束；随后 `}`（第 6 行）结束 `main` 函数体。 |

> 补充说明：第 2 行已声明 `using namespace std;`，因此第 4 行的 `cout` 未加 `std::` 前缀也可以正常使用；而 `std::endl` 采用了完整限定名写法，二者混用不影响编译结果。实际工程中，为避免命名冲突，通常更推荐显式书写 `std::` 前缀。

## Git 基本流程

查看当前状态

```bash
git status
```

将文件加入暂存区

```bash
git add HelloWorld.cpp
```

提交到本地仓库

```bash
git commit -m "提交说明"
```

推送到远程仓库

```bash
git push
```

## 许可证

MIT License
