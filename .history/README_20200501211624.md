---
weight: 1
---

# 简明C++学习笔记

# Basic Concepts 基本概念

本章记录了关于C++文件的初始化，和一些基本概念操作。

### 什么是C++？

C++是一门编程语言，基于C语言扩展而来。一般来说，C++和C语言偏向于更底层原理，价值也很大。它可能不如Python等新语言易上手、效率高，但有助于初学者刨根问底，深入了解计算机原理。

### 你好世界与头部文件初始化

C++语言文件通常以 _*.cpp_ 文件形式出现。我们新建一个 _Helloworld.cpp_ 文件，并在VScode中打开它。

一片空白。因为 _*.cpp_ 和 _.txt_ 及其他众多文件一样，都是**文本文件**的一种。在VScode中输入：

```c++
#include <iostream>
using namespace std;

int main()
{
	cout << "你好，世界！" << endl;
	
	return 0;
}
```

这就是一个最基本的C++编程文件。在终端中执行它，你可以看到有目标字符串显示：

```
你好，世界！
```

这就是一个最基本的C++程序。但是先别着急欢呼雀跃。**当我们写下这一系列代码，并在终端中执行它时，我们究竟做了什么？**

我们输入的代码可以分为两部分：**Header**与**Body**。

{{<  tabs "01">}}

{{< tab "Header" >}}

```c++
#include <iostream>
using namespace std;
```

{{< /tab >}}

{{< tab "Body" >}}

```c++
int main()
{
	cout << "你好，世界！" << endl;
	
	return 0;
}
```

{{< /tab >}}

{{< /tabs >}}

Header定义了程序运行的最基本库与环境，Body则述明了程序运行的主体。int main()是一种最基本的**函数**，在后边的函数部分会有说明。

在这里需要注意：

* **基本的语句需要以分号结尾**
* **作为程序主体的int main()函数需要以"return 0;"结尾。**
* 空白和空行在C++程序中通常被忽略，但为了增强代码可读性和美观，我们仍然应该排版代码。

### 注释

注释分为**多行注释**和**单行注释**。

{{<  tabs "02">}}

{{< tab "单行注释" >}}

```c++
#include <iostream>
using namespace std;
// 这是一行注释……
```

{{< /tab >}}

{{< tab "多行注释" >}}

```c++
int main()
{
	cout << "你好，世界！" << endl;
	/*
	这是很多行
	注释
	而且注释符和注释内容在不在同一行都没有关系*/
	/*你也可以这样来代替单行注释……*/
	
	return 0;
}
```

{{< /tab >}}

{{< /tabs >}}

这就是注释。

### Variables变量

变量储存在本地内存中，具有 **数据类型(Data type)** 和 **值(Value)** 两个基本特征。我们创造一个基本的整数型变量：

```c++
#include <iostream>
using namespace std;

int main()
{
    int x = 10
    cout << x << endl;
    
    return 0;
}
```



变量名称**大小写敏感**。所以变量**x**与变量**X**是两个不同的变量。若多次为同一变量指定不同数据类型，则可能导致程序错误。但是变量的值可以在程序运行中多次赋予。

### cin基本介绍

"cin"语句可以让用户手动为变量赋值。我们看一个简单的案例：

```c++
#include <iostream>
using namespace std;

int main()
{
    cout << "超简易计算器，只能计算两个数字相加" << endl;
    int num1;
    int num2;
    cout << "请输入第一个数字" << endl;
    cin >> num1;
    cout << "请输入第二个数字" << endl ;
    cin >> num2;
    int sum = num1 + num2;
    cout << "结果等于 " << sum << ".";
    system ("pause");
    return 0;
}
```

就是如此。

### Basic Arithmetic Operators 基本数学运算

我们看看C++最基本的五个运算符。

| 操作 | 编程符号 | 数学意义 |
| --- | --- | --- |
| 加法运算 | "+" | x + y |
| 减法运算 | "-" | x - y |
| 乘法运算 | "*" | x * y |
| 除法运算 | "/" | x ÷ y |

只需一个"小小"的案例。

{{< expand "看看这个傻傻的计算器！" >}}
```c++
#include <iostream>
using namespace std;

int main()
{
    cout << "反人类多功能计算器，计算四次加减乘除，只能输入整数。" << endl;
    cout << "加法计算器……" << endl;
    int add1, add2;
    cout << "请输入第一个数字：" << endl;
    cin >> add1;
    cout << "请输入第二个数字：" << endl;
    cin >> add2;
    cout << add1 << " + " << add2 << " = " << add1 + add2 << endl;
    cout << "减法计算器……"  << endl;
    int abs1, abs2;
    cout << "请输入第一个数字：" << endl;
    cin >> abs1;
    cout << "请输入第二个数字：" << endl;
    cin >> abs2;
    cout << abs1 << " - " << abs2 << " = " << abs1 - abs2 << endl;
    cout << "乘法计算器……"  << endl;
    int mul1, mul2;
    cout << "请输入第一个数字：" << endl;
    cin >> mul1;
    cout << "请输入第二个数字：" << endl;
    cin >> mul2;
    cout << mul1 << " x " << mul2 << " = " << mul1 * mul2 << endl;
    cout << "除法计算器……"  << endl;
    int vis1, vis2;
    cout << "请输入第一个数字：" << endl;
    cin >> vis1;
    cout << "请输入第二个数字：" << endl;
    cin >> vis2;
    cout << vis1 << " / " << vis2 << " = " << vis1 / vis2 << "......" << vis1 % vis2 << endl;
    system("pause");
    return 0;
}
```
{{< /expand >}}

不要太难过。等我们学过 **循环(Loop)** 后，就可以写出正常些的计算器了。