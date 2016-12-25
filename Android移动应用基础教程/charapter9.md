# 网络编程

## HTTP协议简介

`HTTP`是超文本传输协议，它规定了浏览器和万维网服务器之间互相通信的规则

当客户端在与服务器建立连接后，向服务器端发送的请求，称为`HTTP`请求

服务器收到请求后做出响应，称为`HTTP响应`

## Handler消息机制原理

Handler机制包括4个关键对象
* Message
  * 它是在线程之间传递的消息
  * 它可以在内部携带少量信息，用于交换数据
* Handler
  * 它主要用于发送消息和处理消息
  * 通过`sendMessage()`方法发送消息，通过`handlerMessage()`方法处理消息
* MessageQueue
  * 它是消息队列，用来存放通过Handler发送的消息
  * 每个线程只有一个MessageQueue对象
* Looper
  * 它是MessageQueue的管家
  * 调用Looper.loop()方法后，就会无限循环。每当发现MessageQueue中存在消息时就将它取出并传递给Handler的handlerMessage()方法
  * 每个线程只有一个Looper
  * 主线程创建对象时自动创建Looper对象
  * 子线程中需要调用Looper.loop()开启消息循环

## AsyncTask

借助于该类可以简单的从子线程切换到主线程

使用该类时需要自定义类继承该类

使用该类时需要重写以下方法
* onPreExcute()
  * 该方法在后台任务执行之前调用
  * 一般用于界面初始化
* doInBackground(Params..)
  * 该方法在子线程中运行
  * 一般用于处理耗时操作
* onProgressUpgrade(Progress...)
  * 在doInBackground方法中调用publishProgress方法后会运行该方法
  * 一般用于操作UI
* onPostExcute(Result)
  * 在doInBackground执行完毕后会运行该方法
  * 接收doInBackground返回的数据作为参数，利用该参数操作UI

## HTTPURLConnection

```
URL url = new URL("xxxxxx");//设置访问资源的路径
//获取对象
HTTPURLConnection conn = (HTTPURLConnection)url.openConnection();
conn.setRequestMethod("GET");//设置请求方式
InputStream is = conn.getInputStream();//获取服务器返回的输入流
//操作服务器返回的输入流
conn.close();//关闭http连接
```
