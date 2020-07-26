# JAVA JVM
## _Java Object & Monitor Structure_
![](https://github.com/lixingluo/JVM-Parameter/blob/master/Res/%E5%AF%B9%E8%B1%A1%E4%B8%8EMonitor%E5%85%B3%E8%81%94%E7%BB%93%E6%9E%84%E5%9B%BE.jpeg "对象与Monitor关联结构图")
对象是如何跟monitor有关联的呢？
一个Java对象在堆内存中包括对象头，对象头有Mark word，Mark word存储着锁状态，锁指针指向monitor地址。这其实是**Synchronized的底层**哦~
## _Java Class Life Cycle_
![](https://github.com/lixingluo/JVM-Parameter/blob/master/Res/%E7%B1%BB%E7%9A%84%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F.jpeg "类的生命周期")
一个类从被加载到虚拟机内存开始，到卸载出内存为止，这个生命周期经历了七个阶段：加载、验证、准备、解析、初始化、使用、卸载。
### 加载
- 通过一个类的全限定名来获取定义此类的二进制字节流
- 将这个字节流所代表的静态存储结构转化为方法区的运行时数据结构
- 在内存中生成一个代表这个类的java.lang.Class对象，作为方法区这个类的各种数据的访问入口
### 验证
- 验证的目的是确保Class文件的字节流中包含的信息满足约束要求，保证这些代码运行时不会危害虚拟机自身安全
- 验证阶段有：文件格式校验、元数据校验、字节码校验、符号引用校验
### 准备
- 准备阶段是正式为类中定义的变量（静态变量）分配内存并设置类变量初始值的阶段
### 解析
- 解析阶段是虚拟机将常量池内的符号引用替换为直接引用的过程
### 初始化
- 到了初始化阶段，才真正开始执行类中定义的Java字节码
