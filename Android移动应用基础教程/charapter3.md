# Activity

## Activity简介
Activity是Android四大组件之一，它负责管理Adnroid的应用程序界面。一个应用程序一般包含
多个Activity，Avtivity通过onCreate()的setContentView()方法显示指定组件

## Activity的创建

* 定义一个类继承自adnroid.Activity或其子类
* 在res/layout目录下建立布局文件
* 在Activity中通过onCreate()的setContentView()方法显示指定组件
* 在Android.Manifest.xml中注册Activity

## Activity生命周期

生命周期是一个对象从创建到销毁的过程，每一个对象都有自己的生命周期。
Activity的生命周期包括运行状态、暂停状态、停止状态

* 运行状态
  * 当Activity运行在屏幕最前端时，它是可见的、有焦点的，可以用来处理用户的常见操作，
  如点击、双击、长按事件等。
* 暂停状态
  * 某些情况下，Activity对用户仍然是可见的，但它不再拥有焦点。
* 停止状态
  * Activity完全不可见时就处于停止状态，但仍然保留当前状态和成员信息

当Activity处于运行状态时，Android会尽可能保证它的运行，即使内存不足，Android也会杀死栈底部的Activity来保证其运行

Activity发生状态变化时会触发一些事件，执行一些回调方法来通知状态的变化
* onCreate()创建时执行
* onStart()可见时执行
* onRestart()回到前台，再次可见时执行
* onResume()获取焦点时执行
* onPause()失去焦点时执行
* onStop()用户不可见进入后台时执行
* onDestroy()销毁时执行

## Activity的启动模式

* standard模式
  * 该模式是Android的默认模式
  * 每启动一个Activity时，不判断该Activity在栈中是否存在，就将该Activity入栈并处于栈顶
* singleTop模式
  * 与standard模式类似，但当启动的Activity已经在任务栈的栈顶时，直接使用它，而不是创建新的实例
* singleTask模式
  * 每次启动Activity时，都会先检查该Activity在任务栈中是否存在
  * 若该Activity已存在于任务栈中，则移除该Activity上面的Activity，使其居于栈顶
* singleInstance模式
  * 该模式加载Activity时，若要启动的Activity不存在时，系统会线创建一个新的任务栈，再创建该Activity的实例，将其加入栈顶
  * 该模式加载Activity时，若要启动的Activity存在时，系统会将该Activity所在的任务栈转到前台

## Activity中使用Intent

Intent分为`显式Intent`和`隐式Intent`

** 显式Intent **

显式Intent指在通过Intent启动Activity时，明确指定激活组件的名称

```
Intent intent = new Intent(this, 目标类.class);//创建Intent对象
startActivity(intent);//开启Activity
```

** 隐式Intent **

没有明确指定组件名的Intent称为隐式Intent。系统会根据隐式Intent中设置的action、
category、数据找到最合适的组件

## Activity中的数据传递

Intent不仅可以用来开启Activity，也可以用来在Activity之间传递数据。

> 简单的数据传递

* 在Intent中调用putExtra()方法将数据存入Intent
* 在接收数据的Activity中调用getStringExtra()获取数据

> 使用Bundle传递数据

* 新建Bundle对象，调用Bundle对象的putXxx()方法存储数据
* 新建Intent对象，调用Intent对象的putExtras()绑定Bundle对象
* 在接收数据的Activity中，调用Intent对象的getExtras()获取Bundle对象
* 调用Bundle对象的getXxx()方法获取数据

## 回传数据

一般使用系统提供的startActivityForResult()方法实现回传数据

发送数据的Activity中添加以下代码

```
Intent intent = new Intent(this,目标类.class);//新建Intent用以存储数据
//第一个参数是Intent，第二个参数是requestCode，用于判断数据来源
startActivityForResult(intent,1);

```
接收数据的Activity中添加一下代码

```
Intent intent = new Intent();//新建intent用以存储数据
intent.putExtra("key","value");//绑定数据
//设置回传数据，第一个参数是resultCode，第二个参数是带有回传数据的intent
setResult(1,intent);
finish();//销毁当前Activity
```
