# 对象 / object<br>
### 1 定义 / \* 对象是一块存储区域<br>
1.1 C++程序的构造过程，即是“创建，销毁，引用，访问，操作”对象的重复过程<br>
<br>
1.2 对象具有存储期 *storage duration* ，并影响它的生命周期 *lifetime*<br>
<br>
1.3 对象具有类型 *type*<br>
<br>
1.4.1 非子对象的对象称作完整对象 *complete object* ，如果完整对象具有类类型 *class type*，则其类型 *type* 被视作 最终派生类 *most derived class* <br>
<br>
1.4.2 最终派生类的对象称为最终派生对象 *most derived object* ，除非作为位域 *bit_field* ，最终派生对象总是具有非零大小且占有一字节以上的存储空间<br>
<br>
### 2 注意 / 无论函数占用存储的方式和对象是否相同，函数都不是对象<br>
<br>
<br><p align="right">*最后更新于 2024/6/29 22:47:21*