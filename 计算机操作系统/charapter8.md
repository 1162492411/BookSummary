
# 外存的组织方式
常见的外存分配方式有`连续分配`、`链接分配`和`索引分配`三种

## 连续组织方式
一个`连续文件`是由一组分配在磁盘连续区域的物理块组成的

该方式常用于存放系统文件，支持顺序访问和直接访问

## 链接组织方式
链接分配的文件称为`串联文件`，类似数据结构的链表

## FAT技术
FAT表存储每个磁盘的物理块信息，

## NTFS的文件组织方式
* 64位磁盘地址
* 支持长文件名
* 系统容错功能
* 保证系统中的数据一致性

## 索引组织方式
索引结构创建的文件称为`索引文件`，系统为每个文件建立一张索引表，索引文件由索引表和数据文件组成

### 单级索引

### 多重索引

### 混合索引

# 文件存储空间的管理

文件存储空间的管理实质是空闲块的组织和管理问题，常见的空闲块的分配方法包括
* 空闲表法
* 空闲链表法
* 位示图法
* 成组链接法

## 空闲表法
简单的空闲块管理方法就是把文件存储设备中的空闲块块号统一存放在称为`空闲表`的物理块中

## 空闲链表法
空闲链将所有空闲块链接在一起

## 位示图法
系统从内存中分配若干字节，为每个文件存储设备建立一张位示图，`位示图`反映每个文件存储设备的使用情况，0代表未使用，1代表已分配

## 成组链接法

# 提高磁盘IO的途径
* 磁盘高速缓存
* 提前读
* 延迟写
* 优化物理块的分布
* 虚拟盘
* RAID
