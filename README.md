# 冯诺依曼式计算机CPU模拟器
课题任务概述
模拟一个简易的冯诺依曼式计算机CPU的工作。
该CPU字长为16位，共11个寄存器，其中3个系统寄存器，分别为程序计数器，指令寄存器，标志寄存器；8个通用寄存器，即寄存器1、2、3、4（数据寄存器），寄存器5、6、7、8（地址寄存器）。该CPU至多支持32K内存。内存分两部分，一部分为代码段，从地址0开始。另一部分为数据段，从地址16384开始。
该CPU所支持的指令集见word文档。每条指令固定由32位（编号为0到31）二进制数组成，其中第0到7位为操作码，代表CPU要执行哪种操作；第8到15位为操作对象，如寄存器，内存地址等；第16到31位为立即数。该CPU有一个输入端口和一个输出端口。输入端口的数据由标准输入设备（键盘）输入，输出端口的数据输出到标准输出设备（显示器）上。

程序的大致步骤
程序开始时要从指定文件中读入一段用给定指令集写的程序至内存（从地址0开始顺序保存），程序计数器初始值也为0。此功能为指令加载。
指令加载完成后程序就开始不断重复取指令、分析指令和执行指令的过程。程序每执行一条指令就要输出CPU当前的状态，如各寄存器的值等。当执行到停机指令时，程序按要求输出后就结束了。
取指令：要求读取程序计数器PC内的指令地址，根据这个地址将指令从内存中读入，并保存在指令寄存器中，同时程序计数器内容加4，指向下一个条指令。（因为我们所有的指令长度固定为4个字节，所以加4）。
分析指令：是指对指令寄存器中的指令进行解码，分析出指令的操作码，所需操作数的存放位置等信息等。
执行指令：完成相关计算并将结果写到相应位置。

课题要求
初步要求开发两个版本：单核版本和双核版本。
单核版本：为必须完成的内容，程序的正确性可以通过OJ验证。
双核版本：或者叫多线程版本。

具体格式见样例。
