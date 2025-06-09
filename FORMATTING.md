# 代码规范

此文档记录我的代码规范。

参与他人的项目时，我会视情况舍弃一些个人规范；开发个人项目时则会严格执行。

（本人有强迫症）

## C/C++

文件、类、函数前都要添加 *doxgen-like* 注释。

- 单行注释（放在行尾）首先先加一个空格，再写 `//`，`//` 和注释内容之间也要有空格。

- 英文和中文之间要有空格；英文标点（如 `, . ( ) ;`）后面也有跟一个空格。
- 如果涉及到类的代码，文件名与类名一致。

```cpp
/**
 * @file		main.cpp
 * @brief		这是一个示例代码文件
 *
 * @author		masterLazy
 * @copyright	Copyright (c) 2025 masterLazy
 */
#include <iostream> // #include 后面也要加空格
using namespace std; // 如果编写的是 SDK，则不在全局写 using namespace

// 类用大驼峰命名
class MyClass { // 大括号统一放在行尾，不换行
    // 成员和方法都用小驼峰命名
    // private 成员放在 public 之前，尽量不写 "private:"
    int privateItem;
public:
    MyClass() {} // 函数体为空的折叠大括号；只有一行且不长的也折叠
    
    /**
     * @brief		示例函数
     * @param str	介绍略
     */
    // 成员和方法都用小驼峰命名
    // 尽量用 const 和引用；如果重写了基类的虚函数要写 override
	int myFunction(const string& str) const { return 0; } // 单行代码，大括号和语句之间写空格
    // 形参用蛇形命名
    void anotherFunction(const string& another_str) {}
}

// 全局函数用大驼峰命名
void AnotherFunction() {}

// 枚举和枚举值都用大驼峰
enum class MyEnum {
    EnumA, EnumB
};

int main() {
    // 结构关键字和括号之间有空格；for 循环的分号后面添加空格
	for (int i = 0; i < n; i++) {
        if (not i % 2 == 0 and i > 10 or i == 12) { // 优先用 and or not
            cout << i << endl;
        }
    }
    return 0;
}
```
