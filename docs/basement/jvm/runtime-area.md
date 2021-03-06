Java虚拟机在执行Java程序的过程中会把他所管理的内存划分为若干个不同的数据区域。《Java虚拟机规范》中规定了JVM所管理的内存需要包括一下几个运行时区域：

![](http://www.hollischuang.com/wp-content/uploads/2019/08/15643074729916.jpg)

主要包含了PC寄存器（程序计数器）、Java虚拟机栈、本地方法栈、Java堆、方法区以及运行时常量池。



1、以上是Java虚拟机规范，不同的虚拟机实现会各有不同，但是一般会遵守规范。

2、规范中定义的方法区，只是一种概念上的区域，并说明了其应该具有什么功能。但是并没有规定这个区域到底应该处于何处。所以，对于不同的虚拟机实现来说，是由一定的自由度的。

3、不同版本的方法区所处位置不同，上图中划分的是逻辑区域，并不是绝对意义上的物理区域。因为某些版本的JDK中方法区其实是在堆中实现的。

4、运行时常量池用于存放编译期生成的各种字面量和符号应用。但是，Java语言并不要求常量只有在编译期才能产生。比如在运行期，String.intern也会把新的常量放入池中。

5、除了以上介绍的JVM运行时内存外，还有一块内存区域可供使用，那就是直接内存。Java虚拟机规范并没有定义这块内存区域，所以他并不由JVM管理，是利用本地方法库直接在堆外申请的内存区域。

6、堆和栈的数据划分也不是绝对的，如HotSpot的JIT会针对对象分配做相应的优化。

如上，做个总结，JVM内存结构，由Java虚拟机规范定义。描述的是Java程序执行过程中，由JVM管理的不同数据区域。各个区域有其特定的功能。


但是，需要注意的是，上面的区域划分只是逻辑区域，对于有些区域的限制是比较松的，所以不同的虚拟机厂商在实现上，甚至是同一款虚拟机的不同版本也是不尽相同的。

