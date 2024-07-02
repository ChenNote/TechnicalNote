# signature / 签名<br>
### 1 定义 / \*函数的重载解析过程所需要的信息<br>
1.1 函数参数的类型<br>
```void main(int argc, char** argv) // int 和 char** 是签名```<br>
<br>
1.2 函数是类成员时，该成员函数所在的类，和函数本身的CV-限定符（如有）<br>
```class a{```<br>
```public:```<br>
```void AnFunc(int i) const;```<br>
```};```<br>
```void a::AnFunc(int i) const // a，int(见1.1)，const 是签名```<br>
```{```<br>
```// ...```<br>
```}```<br>
<br>
1.3 对于特化的模板函数，模板参数的类型。<br>
```template <class T>```<br>
```bool compare(const T left, const T right)```<br>
```{```<br>
```// ...```<br>
```}```<br>
```template <>```<br>
```bool compare<const char*>(const char* left, const char* right) // const char* 等是签名```<br>
```{```<br>
```// ...```<br>
```}```<br>
<br>
### 2 注意 / 函数签名中不包含返回值类型<br>
<br><p align="right">*最后更新于 2024/6/29 22:46:01*