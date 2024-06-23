# parameter / 参数<br>
### 1 定义 / 实际运用的情况<br>
1.1 作为函数声明或定义的一部分<br>
```void main(int argc, char** argv) // 其中的 argc 与 argv 为参数```<br>
<br>
1.2 在异常处理器的catch子句中声明的，用于在函数或异常处理器的入口点接收值的对象或引用<br>
```try```<br>
```{```<br>
```// ...```<br>
```}```<br>
```catch(ExceptionType a) // a为参数```<br>
```{```<br>
```// ...```<br>
```}```<br>
<br>
1.3 函数式宏定义紧跟宏名字的圆括号中，逗号分隔的列表中的标识符<br>
```#define max(a,b) (a>b?a:b) // max(a,b)里的a与b为参数```<br>
<br>
1.4 模板参数<br>
```template <typename T> // T为参数```<br>
<br>
### 2 参数的其他常用称呼<br>
2.1 形式自变量 *formal argument* <br>
<br>
2.2 形式参数 *formal parameter* <br>
<br>
<br><p align="right">*最后更新于 2024/6/23 22:28:16*