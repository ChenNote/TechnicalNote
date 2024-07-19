# constexpr / 类型说明符 / 新增关键词<br>
### 1 定义 / 实际运用的情况<br>
#### 1.1 用于指定一个变量或函数是“常量表达式”，它的值/返回值在编译时确定<br>

``` constexpr int a = 5;```<br>
#### 1.2 constexpr 与 const 的区别<br>
#### 1.2.1 声明常量的区别<br>
##### 1.2.1.1 const 用于声明运行时常量，编译时无法确定值<br>
```	int a = 0;```<br>
```	cin >> a;```<br>
```	const int b = a;```<br>
```	cout << b;```<br>
#### 1.2.1.2 constexpr 用于声明编译时常量，编译时即可确定值<br>
```	const int a = 0;```<br>
```	constexpr int b = a + 1;```<br>
```	cout << b;```<br>
#### 1.2.2 声明函数的区别<br>
#### 1.2.2.1 const 修饰*函数参数*，函数体内将不能修改该参数<br>
#### 1.2.2.2 const 修饰*函数返回值*，函数返回值将不能修改。更多用于修饰某指针或者引用，可以保护相关数据免受意外修改<br>
#### 1.2.2.3 const 修饰*成员函数*，函数体内将不能修改对象的数据成员，不能调用非const成员函数<br>
#### 1.2.2.4 constexpr 修饰*函数*，函数对应调用的返回值将在编译时确定，这需要满足以下条件:
#### - - - - - - 1.返回值必须是字面类型 *literal type*
#### - - - - - - 2.函数体有至少一条return语句
#### - - - - - - 3.函数使用的变量/函数必须是constexpr的

<br><p align="right">*最后更新于 2024/7/15 12:36:07*