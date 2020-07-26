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
## _Java Memory Model Structure_
![](https://github.com/lixingluo/JVM-Parameter/blob/master/Res/Java%E5%86%85%E5%AD%98%E6%A8%A1%E5%9E%8B%E5%9B%BE.jpeg "Java内存模型图")
- Java内存模型规定了所有的变量都存储在主内存中
- 每条线程还有自己的工作内存
- 线程的工作内存中保存了该线程中是用到的变量的主内存副本拷贝
- 线程对变量的所有操作都必须在工作内存中进行，而不能直接读写主内存。
- 不同的线程之间也无法直接访问对方工作内存中的变量，线程间变量的传递均需要自己的工作内存和主存之间进行数据同步进行
## _Java Thread Status Transfer Relational Structure_
![](https://github.com/lixingluo/JVM-Parameter/blob/master/Res/%E7%BA%BF%E7%A8%8B%E7%8A%B6%E6%80%81%E8%BD%AC%E6%8D%A2%E5%85%B3%E7%B3%BB%E5%9B%BE.jpeg "线程状态转换")
### Java定义了6种线程池状态：
- 新建(New): 创建后尚未启动的线程处于这种状态
- 运行(Running): 线程开启start()方法，会进入该状态。
- 无限等待(Waiting): 处于这种状态的线程不会被分配处理器执行时间，一般LockSupport::park()，没有设置了Timeoout的Object::wait()方法，会让线程陷入无限等待状态
- 限期等待(Timed Waiting): 处于这种状态的线程不会被分配处理器执行时间，在一定时间之后他们会由系统自动唤醒。sleep()方法会进入该状态~
- 阻塞(Blocked): 在程序等待进入同步区域的时候，线程将进入这种状态~
- 结束(Terminated): 已终止线程的线程状态，线程已经结束执行
## _Java Virtual Machine Parameters Settings_
![](https://github.com/lixingluo/JVM-Parameter/blob/master/Res/JVM%E5%8F%82%E6%95%B0%E5%88%97%E8%A1%A8.jpeg "JVM参数列表")
