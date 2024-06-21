# argument / 自变量<br>
### 1 实际运用的情况<br>
1.1 函数调用表达式 *function call expression* 中，由圆括号()包围的逗号分隔列表中的**表达式**<br>
``` AnyFunc(a) 里的 a 是个自变量```<br>
``` AnyFunc(a+b) 里的 a+b 是个自变量```<br>
<br>
1.2 函数式宏的调用 *function-like macro invocation* 中，由圆括号()包围的逗号分隔列表中的**预处理记号序列**<br>
``` AnyFuncMacro(a) 里的 a 是个自变量```<br>
``` AnyFuncMacro(a+b) 里的 a+b 是个自变量```<br>
``` AnyFuncMacro(a+b,c) 里的 a+b 和 c 各自作为自变量```<br>
``` AnyFuncMacro(a+AnyFuncMacro(b+c)) 里的 a+AnyFuncMacro(b+c) 整体是个自变量```<br>
<br>
1.3 throw的操作数<br>
<br>
1.4 模板实例化中，由角括号<>包围的逗号分隔列表中的**表达式**，**类型标识** *type-id* ，**模板名** *template-name* <br>
>疑问? type-id指的是typeid()的返回值的类型吗？<br>

>疑问? template-name能如何出现在模板实例化的逗号分隔列表里？实际例子？<br>
### 2 自变量的其他常用称呼<br>
2.1 实际自变量 *actual argument* <br>
<br>
2.2 实际参数 *actual parameter* <br>
<br>
<br><p align="right">*最后更新于 2024/6/21 22:33:37*