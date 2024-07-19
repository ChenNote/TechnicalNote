# enum class / 强类型枚举 / 新增枚举类型<br>
### 1 定义 / 实际运用的情况<br>
#### 1.1 为了提高枚举类型 *enum* 的安全性，引入强类型枚举 *enum class* <br>
### 2 语法<br>
#### 2.1 enum class 语法
```enum class enum_name : underlying_type { // underlying_type 可选```<br>
```member_1 = value, // value 可选```<br>
```member_2,```<br>
```member_3,```<br>
``` ... ```<br>
```};```<br>
### 3 特性<br>
#### 3.1 *枚举类型* 可以隐式的转换成整型，而 *强类型枚举* 的转换必须为显式转换<br>
```enum OldColor {```<br>
```    Red, Green, Blue```<br>
```};```<br>
```enum class Color {```<br>
```    Red, Green, Blue```<br>
```};```<br>
```// OldColor oldcolor = 0; // 在最新版本测试下 强弱enum都不可以由整型赋值```<br>
```// Color color = 0;```<br>
<br>
```OldColor oldcolor;```<br>
```Color color;```<br>
<br>
```oldcolor = Red; // enum 的规范的使用方法 , 用 OldColor::Red 也可以```<br>
```color = Color::Red; // enum class 的规范的使用方法```<br>
<br>
```oldcolor == 0; // 这是可以的，因此有意外隐式转换的担忧```<br>
```// color == 0; // 强类型枚举禁止了隐式转换```<br>

#### 3.2 强枚举类型可以指定它的底层类型<br>
```enum class TrafficColor : uint8_t {```<br>
```    Red, Yellow, Green```<br>
```};```<br>

#### 3.3 强类型枚举的作用域限定在类里，必须用类名::访问。而 枚举类型的作用域 就是 它所在的作用域 
这在全局定义枚举的情况下，可以有效地避免命名空间的污染
<br><p align="right">*最后更新于 2024/7/19 8:22:59*