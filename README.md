# The Clock Language

Clock is a simple **compiled** programming language designed for learning and demonstrating the principles of programming language compilation. It uses a stack-based virtual machine to execute intermediate code and supports rich data types, control structures, operators, and built-in functions.

## Main Features

* **Compiled Execution**: A complete compilation chain using a lexer, parser, code generator, and virtual machine.
* **Basic Data Types**: Integer (int), Floating-point (float), String (str), Boolean (bool), Empty (ept).
* **Control Structures**: if-elif-else conditional judgment, while loops.
* **Input/Output**: Supports various formats for keyboard input and console output.
* **Rich Operators**:
  * Arithmetic operators: +, -, *, /
  * Compound assignment operators: +=, -=, *=, /=
  * Increment/decrement operators: ++, --
  * Comparison operators: <, <=, >, >=, ==, !=
  * Logical operators: & (AND), | (OR), ! (NOT)
* **String Operations**: lower(), upper(), titlef()
* **Type Conversion**: setf() for explicit conversion, .= for shorthand conversion assignment.

## Syntax Introduction

### Variable Definition and Assignment

    >> Variable definition and initialization
    int(a = 10);               >> Define integer variable a initialized to 10
    float(b = 3.14);           >> Define float variable b initialized to 3.14
    str(c = "Hello, Clock!");   >> Define string variable c
    bool(d = true);            >> Define boolean variable d
    
    >> Direct assignment
    (a = 20);                  >> Change the value of variable a to 20
    (b = b * 2);               >> Multiply the value of variable b by 2
    
    >> Compound assignment operators
    (a += 5);                  >> Equivalent to (a = a + 5)
    (b -= 1.0);                >> Equivalent to (b = b - 1.0)
    (a *= 2);                  >> Equivalent to (a = a * 2)
    (a /= 3);                  >> Equivalent to (a = a / 3)
    
    >> Increment/Decrement
    (a++);                     >> Increment variable a by 1
    (b--);                     >> Decrement variable b by 1

### Data Types

#### Integer (int)

* Represents integers, supports positive and negative numbers.
* Example: `int(a = 10); int(b = -5);`

#### Floating-point (float)

* Represents numbers with decimal points.
* Example: `float(a = 3.14); float(b = -2.5);`

#### String (str)

* Represents text, enclosed in double quotes.
* Example: `str(a = "Hello"); str(b = "World");`

#### Boolean (bool)

* Represents true or false, only two values: true and false.
* Example: `bool(a = true); bool(b = false);`

#### Empty (ept)

* Represents a null or undefined value.
* Example: `int(a = ept);`

### Operators

#### Arithmetic Operators

| Operator | Description | Example |
| --- | --- | --- |
| +   | Addition | `int(a = 1 + 2);` → 3 |
| -   | Subtraction | `int(a = 5 - 3);` → 2 |
| *   | Multiplication | `int(a = 2 * 3);` → 6 |
| /   | Division | `int(a = 6 / 2);` → 3 |

#### Comparison Operators

| Operator | Description | Example |
| --- | --- | --- |
| <   | Less than | `bool(a = 1 < 2);` → true |
| <=  | Less than or equal to | `bool(a = 2 <= 2);` → true |
| >   | Greater than | `bool(a = 3 > 2);` → true |
| >=  | Greater than or equal to | `bool(a = 2 >= 3);` → false |
| ==  | Equal to | `bool(a = 2 == 2);` → true |
| !=  | Not equal to | `bool(a = 2 != 3);` → true |

#### Logical Operators

| Operator | Description | Example |
| --- | --- | --- |
| &   | AND | `bool(a = true & false);` → false |
| \\  |     | OR  |
| !   | NOT | `bool(a = !true);` → false |

#### Assignment Operators

| Operator | Description | Example |
| --- | --- | --- |
| =   | Assignment | `int(a = 10);` |
| +=  | Addition assignment | `int(a = 5); (a += 3);` → 8 |
| -=  | Subtraction assignment | `int(a = 5); (a -= 3);` → 2 |
| *=  | Multiplication assignment | `int(a = 5); (a *= 3);` → 15 |
| /=  | Division assignment | `int(a = 6); (a /= 3);` → 2 |
| .=  | Type conversion assignment | `int(a = 10); (a .= str);` → "10" |

### Output Statement

    >> Output a single value
    output : 100;
    output : "Hello, Clock!";
    output : true;
    
    >> Output multiple values (separated by colons)
    output : "The value of a is " : a : ".";
    output : "PI = " : 3.14 : "\n";
    output : "Sum: " : (1 + 2 + 3) : "\n";

### Input Statement

    >> Whole line input (input.l)
    input.l : name;
    output : "Your name is " : name;
    
    >> Space-separated input (input.s)
    input.s : age;
    output : "Your age is " : age;
    
    >> Custom delimiter input (input.g)
    input.g : city;
    output : "Your city is " : city;

### Control Structures

#### if-elif-else Conditional Judgment

    int(score = 85);
    
    if (score >= 90) {
        output : "Excellent!";
    } elif (score >= 80) {
        output : "Good!";
    } elif (score >= 70) {
        output : "Average!";
    } else {
        output : "Need to improve!";
    }

#### while Loop

    int(i = 1);
    int(sum = 0);
    
    while (i <= 10) {
        (sum = sum + i);
        (i++);
    }
    
    output : "Sum of 1 to 10 is " : sum;

### String Operations

    str(text = "Hello, Clock!");
    
    >> Convert to lowercase
    str(lower_text = lower(text));
    output : "Lowercase: " : lower_text;
    
    >> Convert to uppercase
    str(upper_text = upper(text));
    output : "Uppercase: " : upper_text;
    
    >> Title case (capitalize first letter of each word)
    str(title_text = titlef("hello, world!"));
    output : "Title case: " : title_text;

### Type Conversion

#### Explicit Type Conversion (setf)

    str(number_str = "123");
    int(number_int = setf.int(number_str));
    float(number_float = setf.float(number_int));
    bool(number_bool = setf.bool(number_int));
    
    output : "String: " : number_str;
    output : "Int: " : number_int;
    output : "Float: " : number_float;
    output : "Bool: " : number_bool;

#### Shorthand Type Conversion Assignment (.=)

    int(a = 10);
    (a .= str); >> Convert a to string
    output : "String: " : a;
    
    (a .= float); >> Convert a to float
    output : "Float: " : a;
    
    (a .= int); >> Convert a to integer
    output : "Int: " : a;
    
    (a .= bool); >> Convert a to boolean
    output : "Bool: " : a;

### Statement Terminator

* **Semicolon Required**: All non-control-structure statements (assignment, output, input, expressions, etc.) must end with a semicolon (`;`).
* **Exceptions**: Control structure statements like if, elif, else, while do not require a semicolon.
* **Error Example**: `output : 10` (Missing semicolon, will cause an error).
* **Correct Example**: `output : 10;` (Has semicolon, correct).

## Compiler Architecture

The Clock compiler uses a classic four-stage architecture:

1. **Lexer**: Breaks source code into lexical units (Tokens).
2. **Parser**: Builds an Abstract Syntax Tree (AST) according to grammar rules.
3. **CodeGenerator**: Converts the AST into stack-based intermediate code.
4. **VirtualMachine**: Executes the intermediate code.

### Intermediate Code Instruction Set

Clock uses a stack-based intermediate code instruction set, mainly including:

* **Stack Operations**: `PUSH_INT`, `PUSH_FLOAT`, `PUSH_STRING`, `PUSH_BOOL`, `POP`, `DUP`
* **Arithmetic Operations**: `ADD`, `SUB`, `MUL`, `DIV`
* **Comparison Operations**: `EQ`, `NE`, `GT`, `LT`, `GE`, `LE`
* **Logical Operations**: `AND`, `OR`, `NOT`
* **Control Flow**: `JMP`, `JMP_IF_FALSE`, `JMP_IF_TRUE`
* **Variable Operations**: `DECL_INT`, `DECL_FLOAT`, `DECL_STRING`, `DECL_BOOL`, `LOAD`, `STORE`, `INC`, `DEC`
* **Input/Output**: `INPUT`, `INPUT_S`, `INPUT_L`, `INPUT_G`, `OUTPUT`
* **Type Conversion**: `CAST_INT`, `CAST_FLOAT`, `CAST_STRING`, `CAST_BOOL`
* **String Operations**: `LOWER`, `UPPER`, `TITLEF`

## IDE Features

The Clock language provides a simple IDE with the following features:

* **Code Editor**: Supports syntax highlighting and basic editing functions.
* **Line Number Display**: Line number display similar to Dev-C++.
* **Default Font**: Uses monospaced fonts like Consolas.
* **Compile & Run**: One-click compilation and execution of Clock programs.
* **Error Messages**: Displays detailed compilation error information and location.

## Usage

1. Write Clock source code files (extension `.clk`).
2. Compile the source code using the Clock compiler.
3. Execute the generated intermediate code.

### Example Programs

#### Calculate Factorial

    int(n = 5);
    int(factorial = 1);
    int(i = 1);
    
    while (i <= n) {
        (factorial = factorial * i);
        (i++);
    }
    
    output : "Factorial of " : n : " is " : factorial;

#### Print Fibonacci Sequence

    int(n = 10);
    int(a = 0);
    int(b = 1);
    int(i = 0);
    
    output : "Fibonacci sequence: ";
    
    while (i < n) {
        output : a : " ";
        int(temp = a + b);
        (a = b);
        (b = temp);
        (i++);
    }

#### String Processing Example

    str(name = "John Doe");
    
    output : "Original: " : name;
    output : "Lowercase: " : lower(name);
    output : "Uppercase: " : upper(name);
    output : "Title case: " : titlef(name);

## Notes

1. **Semicolon Requirement**: All non-control-structure statements must end with a semicolon.
2. **Variable Scope**: Variables have global scope.
3. **Data Type Conversion**:
  * Supports automatic type conversion (e.g., integer to float).
  * Explicit conversion uses the setf() function.
  * Shorthand conversion assignment uses the `.=` operator.
4. **Error Handling**: The compiler provides detailed error messages and locations.
5. **String Concatenation**: Achieved using the colon separator in output statements.
6. **Logical Operators**: Uses & for AND, | for OR, ! for NOT.

## Technical Implementation

* **Development Language**: C++
* **Compilation Environment**: Compiler supporting C++11 and above.
* **Design Patterns**: Singleton, Factory, Visitor patterns.
* **Compilation Architecture**: Lexer → Parser → Code Generator → Virtual Machine.

## Learning Resources

The Clock language is designed for learning compilation principles. You can understand the following by reading the source code:

* Implementation of the Lexer (regular expression matching)
* Implementation of the Parser (recursive descent parsing)
* Construction and traversal of the Abstract Syntax Tree
* Code generation techniques (intermediate code generation)
* Implementation of the Virtual Machine (stack-based interpretation)
* Type system and type checking
* Error handling mechanisms

## Future Plans

* Add function definition and call support.
* Add array and structure types.
* Support modular programming.
* Optimize virtual machine performance.
* Add more built-in functions.
* Support file I/O operations.

## License

MIT License

### Download Link

https://github.com/PigC51/ClockLang


# Clock语言

Clock是一种简单的**编译型**编程语言，设计用于学习和演示编程语言的编译原理。它使用基于栈的虚拟机执行中间代码，支持丰富的数据类型、控制结构、运算符和内置函数。

## 主要功能

* **编译型执行**：使用词法分析器、语法分析器、代码生成器和虚拟机的完整编译链
* **基本数据类型**：整数(int)、浮点数(float)、字符串(str)、布尔值(bool)、空值(ept)
* **控制结构**：if-elif-else条件判断、while循环
* **输入输出**：支持多种格式的键盘输入和控制台输出
* **丰富的运算符**：
  * 算术运算符：+, -, *, /
  * 复合赋值运算符：+=, -=, *=, /=
  * 自增自减运算符：++, --
  * 比较运算符：<, <=, >, >=, ==, !=
  * 逻辑运算符：& (与), | (或), ! (非)
* **字符串操作**：lower(), upper(), titlef()
* **类型转换**：setf()显式转换, .= 简写转换赋值

## 语法介绍

### 变量定义与赋值

    >> 变量定义与初始化  
    int(a = 10);               >> 定义整数变量a并初始化为10  
    float(b = 3.14);           >> 定义浮点数变量b并初始化为3.14  
    str(c = "Hello, Clock!");   >> 定义字符串变量c  
    bool(d = true);            >> 定义布尔变量d  
    
    >> 直接赋值  
    (a = 20);                  >> 将变量a的值改为20  
    (b = b * 2);               >> 将变量b的值乘以2  
    
    >> 复合赋值运算符  
    (a += 5);                  >> 等价于 (a = a + 5)(b -= 1.0);                >> 等价于 (b = b - 1.0)(a *= 2);                  >> 等价于 (a = a * 2)(a /= 3);                  >> 等价于 (a = a / 3)  
    >> 自增自减  
    (a++);                     >> 变量a自增1  
    (b--);                     >> 变量b自减1  

### 数据类型

#### 整数 (int)

* 表示整数，支持正负数
* 示例：`int(a = 10); int(b = -5);`

#### 浮点数 (float)

* 表示带小数的数值
* 示例：`float(a = 3.14); float(b = -2.5);`

#### 字符串 (str)

* 表示文本，使用双引号包围
* 示例：`str(a = "Hello"); str(b = "World");`

#### 布尔值 (bool)

* 表示真或假，只有两个值：true和false
* 示例：`bool(a = true); bool(b = false);`

#### 空值 (ept)

* 表示空值或未定义的值
* 示例：`int(a = ept);`

### 运算符

#### 算术运算符

| 运算符 | 描述  | 示例  |
| --- | --- | --- |
| +   | 加法  | `int(a = 1 + 2);` → 3 |
| -   | 减法  | `int(a = 5 - 3);` → 2 |
| *   | 乘法  | `int(a = 2 * 3);` → 6 |
| /   | 除法  | `int(a = 6 / 2);` → 3 |

#### 比较运算符

| 运算符 | 描述  | 示例  |
| --- | --- | --- |
| <   | 小于  | `bool(a = 1 < 2);` → true |
| <=  | 小于等于 | `bool(a = 2 <= 2);` → true |
| >   | 大于  | `bool(a = 3 > 2);` → true |
| >=  | 大于等于 | `bool(a = 2 >= 3);` → false |
| ==  | 等于  | `bool(a = 2 == 2);` → true |
| !=  | 不等于 | `bool(a = 2 != 3);` → true |

#### 逻辑运算符

| 运算符 | 描述  | 示例  |
| --- | --- | --- |
| &   | 与   | `bool(a = true & false);` → false |
| \\| | 或   | `bool(a = true \\| false);` → true |
| !   | 非   | `bool(a = !true);` → false |

#### 赋值运算符

| 运算符 | 描述  | 示例  |
| --- | --- | --- |
| =   | 赋值  | `int(a = 10);` |
| +=  | 加赋值 | `int(a = 5); (a += 3);` → 8 |
| -=  | 减赋值 | `int(a = 5); (a -= 3);` → 2 |
| *=  | 乘赋值 | `int(a = 5); (a *= 3);` → 15 |
| /=  | 除赋值 | `int(a = 6); (a /= 3);` → 2 |
| .=  | 类型转换赋值 | `int(a = 10); (a .= str);` → "10" |

### 输出语句

    >> 输出单个值  
    output : 100;  
    output : "Hello, Clock!";  
    output : true;  
    
    >> 输出多个值（用冒号分隔）  
    output : "The value of a is " : a : ".";  
    output : "PI = " : 3.14 : "\n";  
    output : "Sum: " : (1 + 2 + 3) : "\n";  

### 输入语句

    >> 整行输入（input.l）  
    input.l : name;  
    output : "Your name is " : name;  
    
    >> 空格分隔输入（input.s）  
    input.s : age;  
    output : "Your age is " : age;  
    
    >> 自定义分隔符输入（input.g）  
    input.g : city;  
    output : "Your city is " : city;  

### 控制结构

#### if-elif-else 条件判断

    int(score = 85);  
    
    if (score >= 90) {  
        output : "Excellent!";} elif (score >= 80) {  
        output : "Good!";} elif (score >= 70) {  
        output : "Average!";} else {  
        output : "Need to improve!";}  

#### while 循环

    int(i = 1);  
    int(sum = 0);  
    
    while (i <= 10) {  
        (sum = sum + i);    (i++);}  
    
    output : "Sum of 1 to 10 is " : sum;  

### 字符串操作

    str(text = "Hello, Clock!");  
    
    >> 转小写  
    str(lower_text = lower(text));  
    output : "Lowercase: " : lower_text;  
    
    >> 转大写  
    str(upper_text = upper(text));  
    output : "Uppercase: " : upper_text;  
    
    >> 首字母大写  
    str(title_text = titlef("hello, world!"));  
    output : "Title case: " : title_text;  

### 类型转换

#### 显式类型转换 (setf)

    str(number_str = "123");  
    int(number_int = setf.int(number_str));  
    float(number_float = setf.float(number_int));  
    bool(number_bool = setf.bool(number_int));  
    
    output : "String: " : number_str;  
    output : "Int: " : number_int;  
    output : "Float: " : number_float;  
    output : "Bool: " : number_bool;  

#### 简写类型转换赋值 (.=)

    int(a = 10);  
    (a .= str); >> 将a转换为字符串  
    output : "String: " : a;  
    
    (a .= float); >> 将a转换为浮点数  
    output : "Float: " : a;  
    
    (a .= int); >> 将a转换为整数  
    output : "Int: " : a;  
    
    (a .= bool); >> 将a转换为布尔值  
    output : "Bool: " : a;  

### 语句结束符

* **分号要求**：所有非控制结构语句（赋值、输出、输入、表达式等）必须以分号(`;`)结尾
* **例外**：if、elif、else、while等控制结构语句不需要分号
* **错误示例**：`output : 10`（缺少分号，会报错）
* **正确示例**：`output : 10;`（有分号，正确）

## 编译器架构

Clock编译器采用经典的四阶段架构：

1. **词法分析器(Lexer)**：将源代码分解为词法单元(Token)
2. **语法分析器(Parser)**：根据语法规则构建抽象语法树(AST)
3. **代码生成器(CodeGenerator)**：将AST转换为基于栈的中间代码
4. **虚拟机(VirtualMachine)**：执行中间代码

### 中间代码指令集

Clock使用基于栈的中间代码指令集，主要包括：

* **栈操作**：`PUSH_INT`, `PUSH_FLOAT`, `PUSH_STRING`, `PUSH_BOOL`, `POP`, `DUP`
* **算术运算**：`ADD`, `SUB`, `MUL`, `DIV`
* **比较运算**：`EQ`, `NE`, `GT`, `LT`, `GE`, `LE`
* **逻辑运算**：`AND`, `OR`, `NOT`
* **控制流**：`JMP`, `JMP_IF_FALSE`, `JMP_IF_TRUE`
* **变量操作**：`DECL_INT`, `DECL_FLOAT`, `DECL_STRING`, `DECL_BOOL`, `LOAD`, `STORE`, `INC`, `DEC`
* **输入输出**：`INPUT`, `INPUT_S`, `INPUT_L`, `INPUT_G`, `OUTPUT`
* **类型转换**：`CAST_INT`, `CAST_FLOAT`, `CAST_STRING`, `CAST_BOOL`
* **字符串操作**：`LOWER`, `UPPER`, `TITLEF`

## IDE功能

Clock语言提供了一个简单的IDE，具有以下功能：

* **代码编辑器**：支持语法高亮和基本编辑功能
* **行号显示**：类似Dev-C++的行号显示
* **默认字体**：使用Consolas等宽字体
* **编译运行**：一键编译和执行Clock程序
* **错误提示**：显示详细的编译错误信息和位置

## 使用方法

1. 编写Clock源代码文件（扩展名为.clk）
2. 使用Clock编译器编译源代码
3. 执行生成的中间代码

### 示例程序

#### 计算阶乘

    int(n = 5);  
    int(factorial = 1);  
    int(i = 1);  
    
    while (i <= n) {  
        (factorial = factorial * i);    (i++);}  
    
    output : "Factorial of " : n : " is " : factorial;  

#### 打印斐波那契数列

    int(n = 10);  
    int(a = 0);  
    int(b = 1);  
    int(i = 0);  
    
    output : "Fibonacci sequence: ";  
    
    while (i < n) {  
        output : a : " ";    int(temp = a + b);    (a = b);    (b = temp);    (i++);}  

#### 字符串处理示例

    str(name = "John Doe");  
    
    output : "Original: " : name;  
    output : "Lowercase: " : lower(name);  
    output : "Uppercase: " : upper(name);  
    output : "Title case: " : titlef(name);  

## 注意事项

1. **分号要求**：所有非控制结构语句必须以分号结尾
2. **变量作用域**：变量具有全局作用域
3. **数据类型转换**：
  * 支持自动类型转换（如整数转浮点数）
  * 显式转换使用setf()函数
  * 简写转换赋值使用.=运算符
4. **错误处理**：编译器会提供详细的错误信息和位置
5. **字符串拼接**：使用output语句的冒号分隔实现
6. **逻辑运算符**：使用&表示与，|表示或，!表示非

## 技术实现

* **开发语言**：C++
* **编译环境**：支持C++11及以上的编译器
* **设计模式**：单例模式、工厂模式、访问者模式
* **编译架构**：词法分析器 → 语法分析器 → 代码生成器 → 虚拟机

## 学习资源

Clock语言设计用于学习编译原理，您可以通过阅读源代码了解：

* 词法分析器的实现（正则表达式匹配）
* 语法分析器的实现（递归下降解析）
* 抽象语法树的构建和遍历
* 代码生成技术（中间代码生成）
* 虚拟机的实现（基于栈的解释执行）
* 类型系统和类型检查
* 错误处理机制

## 未来计划

* 添加函数定义和调用支持
* 增加数组和结构体类型
* 支持模块化编程
* 优化虚拟机性能
* 添加更多内置函数
* 支持文件I/O操作

## 许可证

MIT License

### 下载地址

https://github.com/PigC51/ClockLang
