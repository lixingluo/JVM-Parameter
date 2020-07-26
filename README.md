# JAVA JVM
## _Java Object & Monitor Structure_
![](https://github.com/lixingluo/JVM-Parameter/blob/master/Res/%E5%AF%B9%E8%B1%A1%E4%B8%8EMonitor%E5%85%B3%E8%81%94%E7%BB%93%E6%9E%84%E5%9B%BE.jpeg "对象与Monitor关联结构图")
对象是如何跟monitor有关联的呢？
一个Java对象在堆内存中包括对象头，对象头有Mark word，Mark word存储着锁状态，锁指针指向monitor地址。这其实是**Synchronized的底层**哦~
