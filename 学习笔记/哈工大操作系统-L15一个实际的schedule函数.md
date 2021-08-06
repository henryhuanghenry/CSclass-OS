# 哈工大操作系统-L15一个实际的schedule函数

[TOC]

讲述Linux 0.11的调度函数schedule()

## counter时间片+SFJ调度(几何级数更新counter保证最长为2P)

<img src="E:\AAAAAAAuniPPT\4_1PPT\CSclass-OS(git)\学习笔记\${图片}\image-20210806163810232.png" alt="image-20210806163810232" style="zoom:50%;" />

### 时间片的作用

<img src="E:\AAAAAAAuniPPT\4_1PPT\CSclass-OS(git)\学习笔记\${图片}\image-20210806164013306.png" alt="image-20210806164013306" style="zoom:50%;" />

### 优先级的作用

优先级使得IO的程序优先调度

<img src="E:\AAAAAAAuniPPT\4_1PPT\CSclass-OS(git)\学习笔记\${图片}\image-20210806164300594.png" alt="image-20210806164300594" style="zoom:50%;" />

### 几何级数保证了时间片最长为2P

- 一直按照时间片轮转，且时间片长度有界这样能保证后台程序不会饥饿
- 不断的短时间片轮转，也使得短作业优先完事，这样也近似了SJF
- IO的优先级高也照顾了前台进程
- 只使用了一个counter就能维护

<img src="E:\AAAAAAAuniPPT\4_1PPT\CSclass-OS(git)\学习笔记\${图片}\image-20210806164639097.png" alt="image-20210806164639097" style="zoom:50%;" />