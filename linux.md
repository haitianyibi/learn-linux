# linux

## 什么是linux

[linux](https://www.kernel.org/)是一个基于posix和纯[unix](https://www.unix.com/)的多用户、多任务multitasking、多线程、多cpu，虚拟内存virtual memory，共享库shared libraries，按需加载demand loading，共享文件读写执行shared copy-on-write executables，内存管理memory management，支持ipv4和ipv6的性能稳定的操作系统，可免费使用和自由传播。

linux继承了unix以网络为核心的设计思想，能运行unix工具软件，应用程序和网络协议。

linux最初由linus torvalds基于unix编写，不受任何商业化软件版本制约。

linux特点：

* 开源，免费
* 多用户支持
* 安全、稳定
* 可移植

linux发行版是指将linux内核和应用软件打包，较知名的linux发行版有，ubuntu,redhat,centos,debian,fedora

LAMP=linux+apache+mysql+php

LNMP=linux+nginx+mysql+psp

linux普遍用于服务器系统，windows多使用为桌面操作系统，windows界面统一，外壳程序固定所有windows程序菜单几乎一致，快捷键一致，linux因不同发行版本界面不同，但基本命令相同，windows驱动程序更新较快，支持度较高，使用简单图形化界面，系统构造复杂，变化快，学习困难，linux相对稳定，学习简单。

# linux下载安装

# linux内核源代码许可证（GPLv2）

根据GNU通用公共许可证版本2（GPLv2）条款提供linux内核

# linux启动过程

* 内核引导：BIOS开机自检，操作系统接管硬件后首先读入/boot目录下的内核文件
* 运行init：init程序读取配置文件/etc/inittab
* 系统初始化：开机启动程序windows称服务，linux称**进程守护**,7个运行级别
* * 0：系统停机状态
  * 1：单用户工作状态，root权限，用于系统维护，禁止远程登录
  * 2：多用户状态，无NFS
  * 3：完全多用户状态，有NFS，登录后进入控制台命令行模式
  * 4：保留
  * 5：x11控制台，登录后进入图形GUI模式
  * 6：系统正常关闭重启
* 建立终端：
* 用户登录系统：命令行登录，ssh登录，图形界面登录

# linux关机

sync数据内存同步硬盘

shutdown：安全的系统关机

power off：立刻关机

halt:立刻关机

reboot：重启

# linux目录结构

ls：显示目录和文件

/bin：存放命令目录

/boot：启动连接文件，镜像文件

/dev：设备文件，访问文件方式访问设备

/etc：系统管理的配置文件

/home：用户主目录，以用户名命名

/lib：动态链接库

/media：U盘挂接目录

/mnt：光驱挂接目录

/proc内存目录

/root系统管理员，超级权限者用户主目录

/sbin：系统管理员的工具

/srv：

/sys

/tmp：临时文件目录

/usr：用户程序，文件目录

/usr/bin：系统用户命令目录

/usr/sbin：超级用户使用高级管理程序和系统守护程序

/usr/src：内核源代码

/var：日志

# 远程登录