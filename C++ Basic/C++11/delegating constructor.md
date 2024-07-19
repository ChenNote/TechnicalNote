# delegating constructor / 委托构造 / 新增构造函数定义办法
### 1 定义 / 实际运用的情况
#### 1.1 构造函数的重载中，代码通常有着高度的重用性。因此，在书写上会显得啰嗦。更重要的是，修改逻辑时代码的维护性也低，极易出错。
#### 1.2 委托构造功能使得类中定义构造函数时，可以将多个构造函数重载委托给一个参数最充分的构造函数，减少重复代码的冗余。
### 2 语法 / 示例
```class rectangle {```<br>
```public:```<br>
```	rectangle() : rectangle(0, 0) {}```<br>
```	rectangle(float side) :rectangle(side, side) {}```<br>
```	rectangle(float width, float length) : width(width), length(length) {}```<br>
``` ```<br>
```private:```<br>
```	float width;```<br>
```	float length;```<br>
```};```<br>
<br><p align="right">*最后更新于 2024/7/18 22:00:09*