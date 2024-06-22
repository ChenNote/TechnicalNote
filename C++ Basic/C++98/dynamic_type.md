# dynamic type / 动态类型<br>
### 1 定义 / 实际运用的情况<br>
1.1 左值表达式中，左值引用的**最终派生对象**的类型作为左值的动态类型<br>
>```// 没有触发多态的时候，描述与1.1不符，可能是因为后续的标准有所更改```<br>
>```class a{ ```<br>
>```// definition of class a```<br> 
>```};```<br>
>```class a_froma : public a{```<br> 
>```// definition of class a_froma```<br> 
>```};```<br> 
>```a_froma object_a_froma = a_froma();```<br>
>```a* pa = &object_a_froma;```<br>
>```a& ra = object_a_froma;```<br>
>```// 此时 typeid(*pa).name() 和 typeid(ra).name() 仍是a，而1.1期望是a_froma```<br>

>```// 触发多态后，描述与1.1相符```<br>
>```class a{ ```<br>
>**```virtual void FuncForPolymorphism(){}```**<br>
>```// definition of class a```<br> 
>```};```<br>
>```class a_froma : public a{```<br> 
>```// definition of class a_froma```<br> 
>```};```<br> 
>```a_froma object_a_froma = a_froma();```<br>
>```a* pa = &object_a_froma;```<br>
>```a& ra = object_a_froma;```<br>
>```// 此时 typeid(*pa).name() 和 typeid(ra).name() 正如1.1期望的，是a_froma```<br>

1.2 右值表达式中，右值**自身**的静态类型作为右值的动态类型<br>



<br><p align="right">*最后更新于 2024/6/22 21:18:01*