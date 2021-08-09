# 哈工大操作系统-L26IO与显示器

[TOC]



计算机是如何使用外设的？



## 1.让外设工作的三件事

<img src="E:\AAAAAAAuniPPT\4_1PPT\CSclass-OS(git)\学习笔记\${图片}\image-20210809101241512.png" alt="image-20210809101241512" style="zoom:50%;" />

- 对外设的使用，实际上就是**对外设的控制器发指令**。(可能是一堆out指令)
- 外设工作完成之后，进行中断处理就行。
- **为了让使用外设变得简单，需要提供一个统一的视图--文件视图。**

## 2.一个向屏幕输出的实例

<img src="E:\AAAAAAAuniPPT\4_1PPT\CSclass-OS(git)\学习笔记\${图片}\image-20210809101718795.png" alt="image-20210809101718795" style="zoom:50%;" />

### 2.1文件视图--统一的视图

<img src="E:\AAAAAAAuniPPT\4_1PPT\CSclass-OS(git)\学习笔记\${图片}\image-20210809101804354.png" alt="image-20210809101804354" style="zoom:50%;" />

### 2.2如何知道输出的是什么设备？

<img src="E:\AAAAAAAuniPPT\4_1PPT\CSclass-OS(git)\学习笔记\${图片}\image-20210809102354021.png" alt="image-20210809102354021" style="zoom:50%;" />

<img src="E:\AAAAAAAuniPPT\4_1PPT\CSclass-OS(git)\学习笔记\${图片}\image-20210809102748775.png" alt="image-20210809102748775" style="zoom:50%;" />

<img src="E:\AAAAAAAuniPPT\4_1PPT\CSclass-OS(git)\学习笔记\${图片}\image-20210809102838815.png" alt="image-20210809102838815" style="zoom:50%;" />

### 2.3如何向外部写

<img src="E:\AAAAAAAuniPPT\4_1PPT\CSclass-OS(git)\学习笔记\${图片}\image-20210809103145095.png" alt="image-20210809103145095" style="zoom:50%;" />

<img src="E:\AAAAAAAuniPPT\4_1PPT\CSclass-OS(git)\学习笔记\${图片}\image-20210809103459587.png" alt="image-20210809103459587" style="zoom:50%;" />

<img src="E:\AAAAAAAuniPPT\4_1PPT\CSclass-OS(git)\学习笔记\${图片}\image-20210809103718262.png" alt="image-20210809103718262" style="zoom:50%;" />

<img src="E:\AAAAAAAuniPPT\4_1PPT\CSclass-OS(git)\学习笔记\${图片}\image-20210809104031094.png" alt="image-20210809104031094" style="zoom:50%;" />

因此写设备驱动，就是做好这些读写函数，并且把一些信息注册到注册表里面。

### 2.4输出的位置

<img src="E:\AAAAAAAuniPPT\4_1PPT\CSclass-OS(git)\学习笔记\${图片}\image-20210809104405833.png" alt="image-20210809104405833" style="zoom:50%;" />

<img src="E:\AAAAAAAuniPPT\4_1PPT\CSclass-OS(git)\学习笔记\${图片}\image-20210809104502318.png" alt="image-20210809104502318" style="zoom:50%;" />

## 3.把一系列流程包装成一个统一的视图

<img src="E:\AAAAAAAuniPPT\4_1PPT\CSclass-OS(git)\学习笔记\${图片}\image-20210809104616279.png" alt="image-20210809104616279" style="zoom:50%;" />