# smart pointer / 智能指针 / 新增模板类<br>
#### 1 RAII / Resource Acquisition Is Initialization / 资源获取即初始化<br>
#### 1.1 RAII:  函数中由栈管理的临时对象，在函数结束时会自动析构，从而自动释放资源。-栈资源由 *编译器自动* 分配/释放-堆资源由 *程序员手动* 分配/释放-<br>
#### 因此，利用对象在函数结束时自动执行析构的特性，将 *资源释放* 写入 *析构函数* 从而实现资源自动释放。<br>
####            再将 *资源申请* 写入 *构造函数* ，这就完整实现了由对象(栈)自动管理资源(堆)功能。<br>
#### 2 smart pointer<br>
#### 2.1.1 实践RAII思想的std智能指针，是以 模板类创建智能指针实例 来 包装相应资源的对象[ 资源对象/new实例化返回的指针 ]<br>
#### 2.1.2 头文件<br>
```#include <memory> //(测试时，似乎不包括也可以使用)```<br><br>
```// 以student类为例```<br><br>
#### 2.2 unique_ptr<br>
```// unique_ptr<student> any_up```<br>
#### 2.2.1 资源对应的指针被独占的情景，实践里相当常见<br>
#### 2.2.1.1 独占性：该指针不能拷贝和赋值，对应拷贝构造函数和赋值运算符函数都被 =delete 删除<br>
#### 2.2.2 初始化<br>
#### 2.2.2.1 any_up=make_unique<class_name>(object) ```//make_unique初始化-c++14后支持```<br>
```auto up_0 = make_unique<student>(student("342","bbbb","3"));```<br>
#### 2.2.2.2 any_up(new class_name()) ```//raw pointer初始化-参数为new实例化的返回指针```<br>
```unique_ptr<student> up_1(new student("342","bbbb","3"));```<br>
#### 2.2.3 any_up.release() ```//放弃对指针的控制权，返回raw pointer，并将unique_ptr自身置空。并不会释放内存```<br><br>
#### 2.3 shared_ptr<br>
```// shared_ptr<student> any_sp```<br>
#### 2.3.1 一个资源需要多个指针分别作为副本和处理函数的参数，在最后一个指针销毁时自动释放资源<br>
#### 2.3.2 初始化<br>
#### 2.3.2.1 any_sp=make_shared<class_name>(object) ```//make_shared初始化-参数为资源对象```<br>
```auto sp_0 = make_shared<student>(student("234", "aaaa", "1"));```<br>
#### 2.3.2.2 any_sp(new class_name()) ```//raw pointer初始化-参数为new实例化的返回指针```<br>
```shared_ptr<student> sp_1(new student("234", "aaaa", "1"));```<br>
#### 2.3.3 any_sp.use_count() ```//返回与any_sp指向同一对象的智能指针数目-该函数返回值一旦为0则触发释放内存```<br>
#### 2.3.4 any_sp.unique() ```//use_count()返回为1则为ture，否则返回false```<br><br>
#### 2.4 weak_ptr<br>
#### 2.4.1 配合shared_ptr使用<br>
#### 2.4.1.1 指向shared_ptr所管理的对象<br>
#### 2.4.1.2 不影响所指对象的生命周期，不增加引用计数<br>
#### 2.4.1.3 没有重载 operator-> 和 operator * 操作符，无法访问对象<br>
#### 2.4.2 初始化<br>
#### 2.4.2.1 weak_ptr<class_name> any_wp(any_sp)<br>
#### 2.4.3 any_wp.lock() ```//返回相应shared_ptr```<br>
#### 2.4.4 any_wp.expired() ```//返回bool，等价于use_count()==0，对应对象失效后(内存释放后)返回true```<br>
#### 2.4. 缓存shared_ptr加载的资源<br>
#### 2.4. 解决shared_ptr循环引用的问题<br>
#### 2.5 auto_ptr c++11弃用<br>