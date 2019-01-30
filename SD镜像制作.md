# BPI-M3 SD卡镜像制作
1. 把U盘挂到Ubuntu上  
2. fdisk -l     // /dev/sdx  
3. fdisk /dev/sdx  
4. 分区操作  
  - fdisk d  //删除分区  
  - fdisk n  //新建分区  
5. w  保存退出  
6. 分区格式化  
  - mkfs.vfat /dev/sdb1
  - mkfs.ext4 /dev/sdb2
7. 挂载
8. 拷贝数据

提示信息（分区大小）：
---
make partition table by fdisk command  
reserve part for fex binaries download 0~204799  
partition1 /dev/sdb1 vfat 204800~327679  
partition2 /dev/sdb2 ext4 327680~end  


[参考链接1](https://blog.csdn.net/niotong2014/article/details/78357476)  
[参考链接2](https://www.cnblogs.com/visec479/p/4072754.html)
