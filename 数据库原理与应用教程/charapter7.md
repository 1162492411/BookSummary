# 数据库保护

## 事务

`事务`是用户定义的数据操作系列，这些操作可作为一个完整的工作单元，一个事务内的所有语句被看作一个整体，要不全部执行，要不全部不执行

事务具有四个特征
* 原子性
  * 事务是数据库的逻辑工作单位，事务中的操作要么全部执行，要么全部不执行
* 一致性
  * 事务执行的结果必须是使数据库从一个一致性状态到另一个一致性状态
* 隔离性
  * 一个事务的执行不能被其他事务干扰
* 持久性
  * 事务提交后对数据库中数据的改变是永久的

事务有两种类型：`隐式事务`和`显式事务`
* 隐式事务是每一条数据操作语句自动成为一个事务
* 显式事务是有显式的开始和结束标记的事务，显式事务有两种形式
  * ISO事务模型
    * 明尾暗头，即事务的开始是隐式的，事务的结束有明确的标记，即`commmit`
  * T-SQL事务处理模型
    * 每个事务都有显式的开始和结束标记。开始标记是`begin transaction`，可简写为`begin tran`,结束标记的`commmit`

## 并发控制

* 如果事务是顺序执行的，则称这种执行方式为`串行执行`
* 如果DBMS可以同时接收多个事务，且多个事务在时间上可以重叠执行，则称`并行执行`
* 在单CPU系统中，各个事务交叉使用CPU，称为`交叉并发`
* 在多CPU系统中，多个事务同时占据CPU，称为`同时并发`

并发操作可能带来以下几种数据不一致情况
* 丢失数据修改
  * 指两个事务T1和T2读入同一数据并进行修改，T2提交的结果覆盖了T1提交的结果
* 读“脏”数据
  * 指事务T1修改了数据并将结果写到磁盘，事务T2读取T1修改后的数据，但T1又回滚了对该数据的操作，那么T2读取的数据与T1回滚后的数据并不一致
* 不可重复读
  * 指事务T1读取了数据，事务T2对该数据进行了修改，之后T1又读取该数据，那么T1两次读取的数据并不相同
* 产生"幽灵"数据
  * 事务T1读取了数据，事务T2对该数据删除或添加了部分记录，T1再次读取该数据时发现缺失或者增加了某些记录

### 并发控制措施

在数据库中，进行并发控制的主要方式就是加锁。

`加锁`就是事务T在对某数据操作之前，现象系统请求封锁其所要使用的数据，加锁后事务T对其要操作的数据有了一定的控制权，在事务T释放了锁之前，其他事务无法操作这些数据

锁的基本类型分为两种
* 排他锁/X锁
  * 一旦事务获得对某数据的排他锁，则其他任何事务均不能对该数据进行任何锁，其他事务只能等待第一个事务释放锁
* 共享锁/S锁
  * 若事务T给数据A加了S锁，则T可以读A但不能修改A,其他事务可以再给A加S锁，但不能加X锁，直到T释放A的S锁

### 封锁协议

** 一级封锁协议 **
对事务T要修改的数据加X锁，直到事务结束

在一级封锁协议中如果T只是读取数据而不修改，则无需加锁，因此不能保证可重复读和不读"脏"数据

** 二级封锁协议 **

对事务T要修改的数据加X锁，直到事务结束；对T要读取的数据加S锁，读完后立即释放S锁

二级封锁协议可以防止丢失数据修改，防止读"脏"数据，但不能保证可重复读数据

** 三级封锁协议 **

对事务T要修改的数据或要读取的数据加X锁，直到事务结束

### 死锁

目前在数据库中解决死锁问题的方法主要有两类
* 采取一定措施预防死锁的发生
* 允许死锁存在，但定期诊断系统中有无死锁，若有则解除

预防死锁的方法
* 一次封锁法
  * 每个事务一次性将所有要使用数据全部加锁
  * 降低系统并发性
* 顺序封锁法
  * 预先规定封锁顺序，所有事务按照封锁顺序封锁
  * 封锁顺序难以确定，且难以维护

###　两段锁协议

`两段锁协议`指所有事务必须分为两阶段来对数据进行加锁和解锁
* 在对任何数据进行读写操作前，首先要获得对该数据的封锁
* 在释放一个封锁后，事务不再申请和获得其他任何锁

事务遵循两段锁协议是可串行化调度的充分条件

## 数据库的备份与恢复

数据库故障类型
* 事务内部故障
* 系统故障
* 其他故障

### 数据库备份

备份的内容
* 表
* 数据库用户
* 数据库对象和数据库的全部数据

备份频率考虑的因素
* 存储介质出现故障或其他故障时允许丢失的数据量的大小
* 数据库的事务类型中读多还是写多以及事故发生的概率

### 数据库恢复

恢复策略
* 事务故障的恢复
* 系统故障的恢复
* 介质故障的恢复

恢复方法
* 利用备份
* 利用事务日志
* 利用镜像
