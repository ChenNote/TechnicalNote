# auto / 新增功能<br>
### 1 自动类型推导<br>
#### 1.1 变量 / 自动推导已初始化的变量的类型<br>
```auto x = 5; // x-int```<br>
```const auto *v = &x, u = 6; // v-const int*, u-const int```<br>
```static auto y = 0.0; // y-double```<br>
```// auto int r; // error: auto is not a storage-class-specifier```<br>
#### 1.2 函数 / 自动推导拥有尾置返回类型*trailing return type*的函数的类型<br>
##### 1.2.1 普通函数<br>
```auto test1(int a, int b) -> int```<br>
```{```<br>
```return a + b;```<br>
```}```<br>
##### 1.2.2 模板函数<br>
```template <typename T,typename Y>```<br>
```auto test2(T a, Y b) -> decltype(a * b)```<br>
```{```<br>
```return a * b;```<br>
```}```<br>
##### 1.2.3 lambda函数<br>
```auto test3 = [](int a,int b) -> int```<br>
```{```<br>
```return a+b;```<br>
```};```<br>
<br><p align="right">*最后更新于 2024/7/13 23:31:03*