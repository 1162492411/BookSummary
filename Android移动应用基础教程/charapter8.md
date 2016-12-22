# 服务

`服务`是Android四大组件之一，它能长期在后台运行且不提供用户界面，即使用户切到另一应用程序，
服务仍可以在后台运行

## 服务的使用

* 创建服务
  * 定义类继承Service，实现onBind()方法
* 在Manifest.xml中注册
  * < service  android：name="xxxx" />

## 服务的生命周期

Service不能主动运行，需要调用相应的方法来启动。启动Service的方法有两种：`Context.startService()`和`Context.bindService()`

组件调用startService方法时，Service会先执行Service的onCreate()方法，接着执行onStartCommond()方法，直到Service自身调用stopSelf方法或者组件调用stopService方法终止该Service，最终被系统销毁

组件调用bindService方法时，服务被创建，接着客户端通过Ibind接口与服务通信，客户端通过unbindService方法关闭连接。多个客户端可同时绑定到同一个Service，当所有客户端都解绑后，该Service会被销毁。当调用者销毁时，Service也会被销毁

## 服务通信

服务通信方式有两种：`本地服务通信`和`远程服务通信`。

本地服务通信指应用程序内部的通信。远程服务通信指两个应用程序之间的通信。使用这两种方式通信时必须满足的前提是服务以绑定方式开启

** 本地服务通信 **

在使用服务进行本地通信时，需要自定义Service类，在该类汇总提供onBind方法，该方法返回IBinder对象，该对象会传递给ServiceConnection作为参数之一，这样访问者就额可以通过IBinder对象与Service对象通信

** 远程服务通信 **

远程服务通信是通过AIDL实现的。`AIDL`是一种接口定义语言，与Java中定义接口类似，但存在以下几点差异
* AIDL定义接口的源代码必须以.aidl结尾
* AIDL接口中用到的数据类型，除基本数据类型、String、List、Map、CharSequence外，其他类型全部需要导入包
* 编写AIDL时不能加上类型修饰符
