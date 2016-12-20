# 数据存储

## 数据存储方式

* 文件存储
  * 以I/O流形式把数据存入手机内存或者SD卡，
  * 存储大数据，如视频、图片
* SharedPreferences
  * 本质是xml文件，以Map<Object,Object>形式存入手机内存
  * 存储简单的参数设置，如QQ登录帐号密码、窗口功能状态
* SQLite
  * 轻量级、跨平台的数据库
  * 通常存储用户信息
* ContentProvider
  * Android四大组件之一，以数据库形式存入手机内存
  * 提供统一的数据访问形式，共享自己的数据给其他应用使用
* 网络存储
  * 数据存储到服务器
  * 使用时从网络获取

## 文件存储

Android分为`内部存储`和`外部存储`

> 内部存储

内部存储指将应用程序中的数据以文件方式存储到设备的内部存储空间中，存储的文件是私有的，其他应用程序要操作本应用程序中的文件需要设置权限。

内部存储使用的是Contenxt提供的`openFileOutoput()`和`openFileInput()`方法，下面简单介绍这两个方法

* FileOutputStream openFileOutoput(String filename, int mode)
  * 该方法用于打开应用程序中对应的输出流，将数据存储到文件中
* FileInputStream openFileInput(String filename, int mode)
  * 该方法用于打开应用程序对应的输入流，用于从文件中读取数据

两个方法的第二个参数均为文件的操作模式，其取值有4种
* MODE_PRIVATE
  * 该文件只能被当前程序读写(默认模式)
* MODE_APPEND
  * 该文件的内容可以追加
* MODE_WORLD_READABLE
  * 该文件的内容可以被其他程序读取，安全性低
* MODE_WORLD_WRITEABLE
  * 该文件的内容可以被其他程序写入，安全性低

> 外部存储

外部存储是指将文件存储到一些外围设备。外部存储的文件可以被其他应用程序共享

由于外围设备可能被移除、丢失或者处于其他状态，因此在使用外围设备之前必须使用
`Enviroment.getExternalStorageState()`方法来确认外设设备是否可用。
当外围设备可用并具有读写权限时，就可以通过FileInputStream、FileOutputStream或者
FileReader、FileWriter对象来读写外围设备中的文件

读取外围设备时，需要判断外设设备是否可用以及是否具有读写权限

如果程序需要访问系统的一些关键信息，必须要在Android.Manifest.xml中声明权限，添加以下代码
```
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
```

## SharedPreferences

SharedPreferences主要用于存储一些应用程序的配置参数，如用户名、密码、自定义参数的设置等。
它存储的参数位于data/data/<packagename>/shared_prefs文件夹内。它只能存储float、int、long、
boolean、String、StringSet等类型。

调用context的`getSharedPreferences(String filename, int mode)`方法获取SharedPreferences对象，
此处第二个参数的含义和取值与文件存储中openFileInput()/openFileOutoput()方法的mode相同

SharedPreferences对象只能获取数据，存储/修改数据需要通过它的Editor()对象实现，
* 通过该Editor对象的putXxx()方法进行数据的存储
* 通过该Editor对象的remove()删除指定数据
* 通过该Editor对象的clear()删除所有数据
* 通过该Editor对象的commit()方法提交修改
