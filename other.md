## 0. scp 用法
  - scp lcp204  root@192.168.0.xxx:/bin
---
## 1. 定义函数指针数组：  
typedef  void(*test_func)(void);  
test_func func_array[10];  
---
## 2. 最小根文件系统
2.1 /dev/console  /dev/null  
2.2 init -> busybox  
2.3 /etc/inittab  
2.4 inittab 中指定的程序或脚本  
2.5 库（C库）  

- /etc/inittab -->::sysinit:/etc/init.d/rcS  

- /etc/init.d/rcS --> mount -a    //此命令依赖 /etc/fatab   用于挂载各种(内核的)虚拟文件系统  
---

## 3. udev -> 自动创建/dev/设备结点  
  3.1 cat /proc/devices  //能够查看到 insmod  xxx.ko  后驱动模块创建的设备的主设备号（创建设备结点是需要用到这个设备号）
  3.2 注意区别 /proc/devices    /dev/  
  3.3 /sys/class(类)/创建的设备名称  
  3.4 为什么 /sys/  下的内容一更改 mdev 就能自动运行创建设备结点呢？  
      - 因为 /etc/init.d/rcS 中又这么一句话  echo /sbin/mdev > /proc/sys/kernel/hotplug  

## 4. Makefile 函数  
4.1 $(foreach val,list,text)  
4.2 $(filter pattern...,text) #在text中取出符合patten格式的值  
    - $(filter-out pattern...,text) #在text中取出不符合patten格式的值  

4.3 $(wildcard pattern)  #取出pattern定义了的文件名格式的文件  
4.4 $(patsubst patttern,replacement,$(val)) #从$(val)列表中取出的每一个值如果符合pattern则替换为replacement。  


## 5. 网络相关
网卡启动方式：
A.通过ifup 命令启动。这种方法会用到/etc/network/interface这个文件。
B.通过udhcpc命令启动。这种方法会用到/usr/share/udhcpc/default.script(这个文件来自于busybox源码目录下example/udhcpc/simple.script)

5.1 wpa_supplicant作用：

5.1.1、读取配置文件(wpa_supplicant.conf)

5.1.2、初始化配置参数，驱动函数

5.1.3、让驱动scan当前所有的bssid

5.1.4、检查扫描的参数是否和用户设置的相符

5.1.5、如果相符，通知驱动进行权限认证操作

5.1.6、连上AP