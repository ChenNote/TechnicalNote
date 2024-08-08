# thread / 线程控制 / 新增Header<br>
### 1 定义 / 实际运用的情况<br>
#### 1.1 主线程(main thread)通常是一个程序开始执行时系统自动创建的线程<br>
#### 1.1.1 ```int main(int argc, char** argv)```主函数就是典型的主线程<br>
#### 1.2 子线程(child thread)则是由主线程或其他子线程创建的线程<br>
#### 1.2.1 ```thread thread_name(FUNCTION_NAME, parameters...);```子线程的创建，创建后该函数申请资源并运行于另一 *独立于主线程的* 子线程<br>
### 2 其他常用方法<br>
#### 2.1 ```int number = thread::hardware_concurrency();```//int-显示当前环境的硬件信息(Cpu 内核数目)<br>
#### 2.2 ```thread_object.join();```//使得代码所在的线程进入阻塞，直到该thread_object完成执行。<br>
#### 2.2.1 注意，其他创建了的子线程不受影响继续运行，仅仅阻塞所在的线程<br>
#### 2.3 ```thread_object.joinable();```//bool-该thread_object能不能join，即 没被join过 或者 没被detach过 或者 生命周期未结束<br>
#### 2.4 ```thread_object.detach();```//使得该thread_object与它所关联的线程失去联系，主线程不再需要在乎它是否完毕便可继续执行，主线程结束后它也未必结束<br>
#### 2.4.1 detach()通常用于在创建一个新线程后，不需要等待它执行完毕的情况下使用<br>
<br><p align="right">*最后更新于 2024/8/4 23:28:45*