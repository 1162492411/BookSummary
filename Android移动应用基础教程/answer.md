
## 第二章

### 一、填空题

1.Android的布局有6种，分别是(RelativeLayout)、(LinerLayout)、(GridLayout)、
(TableLayout)、(FrameLayout)和(AbsoluteLayout)。

2.Adnroid相对布局中，表示“是否跟父布局左对齐的”的属性是(android:layout_alignParentLeft)。

3.线性布局主要有两种形式，一种(垂直)线性布局，另一种是(水平)线性布局。

4.创建Android程序时，默认使用的布局是(RelativeLayout)。

5.LogCat区域中有V、D、I、W和E，其中V代表(Verbose)，D代表(Debug)，I代表(Info)，
W代表(Warning)，E代表(Error)。

### 二、判断题

1.相对布局中android:layout_alignRight表示“与指定控件右对齐”(T)

2.Toast的作用是显示一些提示信息(T)

3.TableRow必须要设置layout_width和layout_height属性(F)

4.帧布局中可以添加多个控件，这些控件会重叠的在屏幕左上角显式(T)

5.Adnroid是不支持国际化的(F)

### 三、选择题

1.以下属性中，(D)属性可以"在指定控件左边"

A.android:layout_alignLeft

B.android:layout_alignParentLeft

C.android:layout_left

D.android:layout_toLeftOf

2.表格布局中android:layout_column属性的作用是指定(B)

A.行数

B.列数

C.总行数

D.总列数

3.实际开发中刮刮乐游戏的布局是按照(A)写的

A.相对布局

B.线性布局

C.帧布局

D.绝对布局

4.网络布局是Adnroid(D)新增的布局

A.3.0

B.3.1

C.3.2

D.4.0

5.相对布局中，"是否跟父布局底部对齐"属性是(B)

A.android：layout_alignBottom

B.android:layput_alignParentBottom

C.android:layout_alignBaseline

D.android:alyout_below

### 四、简答题

1.请简述如何在程序中使用Toast

  * new Toast.makeText(context,text,duration).show();

2.请说明布局有几种类型，以及每种类型的作用
  * RelativeLayout : 以组件按相对位置显示
  * LinerLayout : 将组件按水平或垂直方式显示
  * GridLayout : 将组件按表格排列显示
  * TableLayout : 将组件用细线分割的方式显示
  * FrameLayout : 将组件按帧显示
  * AbsoluteLayout : 将组件按设置的绝对位置来显示

### 五、编程题

1.编写一个用户登录界面，界面中必须要有文本提示信息、编辑框、按钮，分别用于显示用户名、密码，输入用户名、密码，登录功能

2.自定义一个样式，使用这个样式修改界面中的背景色，并且美化界面中的文字信息

-------------------------------------
## 第三章

### 一、填空题

1.Android生命周期的三种状态分别是(运行状态)、(暂停状态)、(停止状态)

2.Adnroid的四种启动模式是(standard)、(singleTop)、(singleTask)和(singleInstance)

3.Adnroid中Intent寻找目标组件的方式有两种：(显式)和(隐式)

4.Activity生命周期中"回到前台，再次可见时执行"时调用的方法是(onRestart())

5.Android中提供了一个(startActivityForResult())方法实现回传数据

### 二、判断题

1.Activity是Android应用程序的四大组件之一(T)

2.Intent一般只用于启动Activity，不能开启广播和服务(F)

3.Intent可以用来开启Activity，同样它也可以用来在Activity之间传递数据(T)

4.Activity默认的启动模式是singleTop模式(F)

5.在数据传递时，如果需要获取返回的数据，需要使用onActivityResult()方法(T)

### 三、选择题

1.一个应用程序默认会包含(A)个Activity

A. 1

B. 5

C. 10

D. 若干

2.下列方法中，Activity从启动到关闭不会执行的是(D)

A. onCreate()

B. onStart()

C. onResume()

D. onRestart()

3.下列组件中，不能使用Intent启动的是(D)

A. Activity

B. 启动服务

C. 广播

D. 内容提供者

4.startActivityForResult()方法接收两个参数，第一个是Intent，第二个是(C)

A. resultCode

B. requestCode

C. 请求码

D. data

5.下列关于Activity的描述，错误的是(C)

A. Activity是Android的四大组件之一

B. Activity有四种启动模式

C. Activity通常用于开启一个广播事件

D. Activity就像一个界面管理员，用户在界面上的操作是通过Activity来管理

### 四、简答题

1.简要说明Activity的四种启动模式的区别
  * Standard : 启动的Activity直接进入运行栈
  * SingleTop : 启动一个Activity时，若栈顶是该Activity，则直接使用它；否则将其入栈
  * SingleTask : 启动一个Activity时，若栈中存在该Activity，则使其处于栈顶位置；
  否则将该Activity入栈
  * singleInstance : 每启动一个Activity，新建一个栈将该Activity入栈

2.简要说明Activity的三种状态以及不同状态使用的方法
  * 运行状态 : Activity处于前台，响应用户操作；使用onCreate()、onStart()、onResume()方法
  * 暂停状态 : Activity转入后台，不再具有焦点；使用onPause()方法
  * 停止状态  : Activity完全不可见;使用onStop()方法

-------------
## 第四章

### 一、填空题

1.序列化是将对象状态转换为(可传输)的过程

2.Android中的文件可以存储在(内存)和(SD卡)中

3.通常情况下，解析XML文件有三种方式：(DOM)、(SAX)和(PULL)

4.SharedPrteferences是一个轻量级的存储类，主要用于存储一些应用程序的(配置参数)

5.Adnroid中的数据存储方式有5种，分别是(文件)、(SQLite)、(SharedPrteferences)、(ContentProvider)和(网络)

### 二、判断题

1.SharedPrteferences本质上是一个XML文件，以Map<key,value>形式存入文件中 (T)

2.文件存储是通过I/O流的形式把数据原封不动的存储到文档中 (T)

3.XML文件只能用来保存本地数据，不能在网络中传输 (F)

4.ContentProvider表示内容提供者，用于显示程序中的数据 (F)

5.当用户文件保存到SD卡时，需要在清单文件中添加权限"android:permission.WRITE_EXTERNAL_STORAGE" (T)

### 三、选择题

1.下列文件操作权限中，指定文件内容可以追加的是( C )

A.MODE_PRIVATE

B.MODE_WORLD_READABLE

C.MODE_APPEND

D.MODE_WORLD_WRITEABLE

2.下列代码中，用于获取SD卡路径的是( D )

A.Environment.getSD()

B.Environment.getExternalStorageState()

C.Environment.getSDDirectory()

D.Environment.getExternalStorageDirectory()

3.下列选项中，关于文件存储数据的说法错误的是( D )

A.文件存储是以流的形式来操作数据的

B.文件存储可以将数据存储到SD卡

C.文件存储可以将数据存储到内存中

D.Android中只能使用文件存储数据

4.下列选项中，关于XML序列化和解析描述合理的是 ( BD )

A.DOM解析会将XML文件的所有内容以文档树形式存放在内存中

B.在序列化对象使，需要使用XmlSerialize序列化器，即XmlSerializer类

C.XmlSerializer类的startDocument()方法用于写入序列号的开始结点

D.XmlSerializer类的setOutput()方法用于设置文件的编码方式

5.如果要将程序中的私有数据分享给其他应用程序，可以使用的是( C )

A.文件存储

B.SharedPrteferences

C.ContentProvider

D.SQLite

### 四、简答题

1.请简述Android中5种数据存储方式各自的特点
  * 文件存储 : 可以存储大量数据到本地文件中
  * SQLite : 占用内存小，所有文件都存放在数据库中
  * SharedPrteferences : 一般用于存储用户配置，使用方便，以键值对形式存在于内存中
  * ContentProvider : 提供统一的规范，使数据可以被第三方应用程序访问
  * 网络 : 将数据存储在服务器，安全

2.请简述SharedPrteferences如何存储数据

```
  SharedPrteferences sp = getSharedPreferences(String filename, int mode);
  Editor edit = sp.Edit();
  edit.putString(key,value);
  edit.commit();
```


### 五、编程题

1.请自定义一个XMl文件，并将XML文件中的内容解析出来

2.请编写一个短信草稿箱的程序，要求用户在文本编辑框中输入短信内容后，单击"保存短信"按钮，
将短信保存在SharedPrteferences中

----------------------------------
## 第五章

### 一、填空题

1.ListView的适配器有三种，分别是(BaseAdapter)、(SimpleAdapter)和(ArrayAdapter)

2.创建数据库以及数据库版本更新需要继承(SQLiteOpenHelper)

3.SQLite创建时调用( onCreate() )方法，升级时调用( onUpgrade() )方法

4.要查询SQLite数据库中的信息需要使用( Cursor )接口，接口完毕后调用( close )关闭

5.创建ListView的布局界面必须通过( id )属性才能使数据显示在界面上

### 二、判断题

1.SQLite数据库使用完后不需要关闭，不影响程序性能 ( F )

2.使用ListView显示较为复杂的数据时最好用ArrayAdapter适配器 ( F )

3.SQLite既支持Android的API又支持SQL语句进行增、删、改、查操作 ( T )

4.使用BaseAdapter控制ListView显示多少条数据是通过getView()方法设置 ( F )

5.SQLite只支持NULL、INTEGER、REAL、TEXT和BLOB等5种数据类型 ( F )

### 三、选择题

1.使用SQLite数据库进行查询后， 必须要做的操作的是 ( C )

A.关闭数据库

B.直接退出

C.关闭cursor

D.使用quit函数退出

2.关于适配器的说法正确的是 ( B )

A.它主要用来存储数据

B.它主要用来把数据绑定在组件上

C.它主要用来存储XML数据

D.它主要用来解析数据

3.使用SQLiteOpenHelper类可以生成一个数据库并可以对数据库版本进行管理的方法 ( B )

A.getDatabase()

B.getWriteableDatabase()

C.getReadableDatabase()

D.getAbleDatabase()

4.下列命令中，属于SQLite下的命令是 ( C )

A.shell

B.push

C.quit

D.keytool

5.下列关于ListView使用的描述中，不正确的是 ( B )

A.要使用ListView，必须为该ListView使用Adapter方式传递数据

B.要使用ListView，该布局文件对应的Activity必须继承ListActivity

C.ListView中每一项的视图布局既可以使用内置的布局，也可以使用自定义的布局方式

D.ListView中每一项被选中时，将会触发ListView对象的ItemClick事件

### 四、简答题

1.请简要说明SQLite数据库创建的过程
  * 创建一个类继承SQLiteOpenHelper，重写其onCreate()方法，创建数据表
  * 调用该类的getWriteableDatabase获取可读写的数据库对象

2.请简要说明BaseAdapter适配器4个抽象方法以及它们的具体作用
  * getCount() : 获取条目总数
  * getItem() : 获取条目
  * getItemId() : 获取条目的id
  * getView() : 获取条目的视图

### 五、编程题

1.请使用ListView显示10行数据在界面上，分别用三种适配器实现

2.请创建一个fruit.db表，在表中存入5种水果信息，并将这些信息显示到ListView控件中

----------------------
## 第六章

### 一、填空题

1.ContentProvider匹配Uri需要使用的类是( UriMatcher )

2.使用内容观察者时，调用( onChange() )方法可以得到数据变化的信息

3.ContentProvider提供了对数据增、删、改、查的方法，分别为( isnert() )、( delete() )、
( update() )和( query() )

4.ContentProvider用于( 保存 )和( 检索 )数据，是Android中不同应用程序之间共享数据的接口

5.在应用程序中，使用ContentProvider暴露自己的数据，通过( ContentResolver )对暴露的数据进行操作

###　二、判断题

1.ContentProvider所提供的Uri可以随便定义 ( F )

2.ContentResolver可以通过ContentProvider提供的Uri进行数据操作 ( T )

3.ContentObserver观察指定Uri数据发生变化时调用ContentProvider的是onChange()方法 ( T )

4.使用ContentResolver操作数据时，必须在清单文件进行注册 ( F )

5.ContentProvider与Activity一样，创建时首先会调用onCreate()方法  ( T )

### 三、选择题

1.下列选项中，属于Android四大组件的是 ( AC )

A.Activity

B.ContentReceiver

C.Service

D.ContentObserver

2.下列关于ContentResolver的描述，错误的是 ( C )

A.可以操作数据库数据

B.操作其他应用数据必须知道包名

C.只能操作ContentProvider暴露的数据

D.可以操作ContentProvider的任意数据

3.下列关于ContentProvider的描述正确的是 ( ACD )

A.提供的Uri必须符合规范

B.可以提供本应用所有数据供别人访问

C.必须在清单文件注册

D.authorities属性必须和包名一致

4.继承ContentProvider类必须重写它的 ( ABD )

A.delete()

B.insert()

C.onStart()

D.onUpdate()

5.下列关于ContentObserver的说法正确的是 ( C )

A.可以观察任何数据

B.观察其他应用数据需要权限

C.只能观察到指定的Uri的数据

D.观察其他应用数据必须在清单文件注册

### 四、简答题

1.请简要说明ContentProvider对外共享数据的好处
  * 统一数据访问方式，访问起来更加规范
  * 指定了URI，使数据更加安全

2.请简要说明ContentProvider、ContentResolver和ContentObserver之间的联系
  * ContentProvider共享数据给外部应用访问
  * ContentResolver访问ContentProvider暴露的数据
  * ContentObserver用来观察ContentProvider的数据是否发生变化

### 五、编程题

1.使用ContentProvider管理联系人信息，将联系人信息展示在界面上

2.获取系统图库的信息，使用ContentProvider制作本地图片查看器

-------------

## 第七章

### 一、填空题

1.广播接收者可以在清单文件使用(< receiver >)注册

2.停止广播需要使用( abortBroadcast() )方法

3.广播的发送有两种形式，分别为(有序广播)和(无序广播)

4.代码注册广播需要使用( registerBroadcast() )方法，解除广播需要使用( unregisterBroadcast() )方法

5.指定接收广播类型的函数是( setAction() )

### 二、判断题

1.每一个广播只能有一个广播接收者 (F)

2.广播接收者是四大组件之一，必须在清单文件中注册 (T)

3.广播接收者的注册信息必须要保持唯一性 (T)

4.可以在BroadcastReceiver和onReceive方法中处理耗时负责的业务 (F)

5.广播接收者在注册后必须手动关闭 (F)

### 三、选择题

1.继承BroadcastReceiver需要重写的方法是( A )

A.onReceive()

B.onUpdate()

C.onCreate()

D.onStart()

2.关于广播的作用，说法正确是( A )

A.它主要用于接收系统发出的一些消息

B.它可以进行耗时的操作

C.它可以启动一个Activity

D.它可以帮助Activity修改用户界面

3.下列方法中，用于发送一条有序广播的是 ( B )

A.startBroadcastReceiver()

B.sendOrderdedBroadcast()

C.sendBroadcast()

D.sendReceiver()

4.在清单文件中，注册广播时使用的结点是 ( C )

A.< activity >

B.< broadcast >

C.< receiver >

D.< broadcastreceiver >

5.关于BroadcastReceiver说法不正确的是 ( B )

A.是用来接收广播Intent的

B.一个广播Intent只能被一个订阅了此广播的BroadcastReceiver接收

C.对有序广播，系统会根据接受者声明的优先级别按顺序逐个执行接收者

D.接收者生命的优先级别在android:priority属性中声明，数值越大优先级别高

### 四、简答题

1.说明注册广播有几种方式，以及这些方式有何优缺点
  * 非常驻型广播 : 这种方式广播的生命周期依赖于注册广播的组件
  * 常驻型广播 : 应用程序关闭后，如果收到其他应用程序发出的广播，启动该应用程序

2.简要说明接收系统广播时哪些功能需要使用权限
  * 拨打电话 : < uses-permission android:name="android.permission.CALL_PHONE" />
  * 发送短信 : < uses-permission android:name="android.permission.SEND_SMS" />
  * 设备开机 : < uses-permission android:name=android.permission.RECEIVE_BOOT_COMPLETED />
  * 电池电量低 : < action android:name="android.intent.action.ACTION_BATTERY_LOW" />


### 五、编程题

1.编写程序，监控手机电量，当电量小于15%时进行提示

2.编写程序，根据关键词过滤经常接收到的骚扰短信



-------------

## 第八章

### 一、填空题

1.在创建服务时，必须要继承( Service )类

2.绑定服务时，必须要实现服务的( onBind() )方法

3.在清单文件中，注册服务时应该使用的结点是( < service > )

4.服务的开启方式有两种，分别是( startService() )和( bindService() )

5.在进行远程服务通信时，需要使用( AIDL )接口

### 二、判断题

1.以绑定方式开启服务后，服务与调用者没有关系 ( F )

2.服务的界面可以设置的很美观 ( F )

3.以绑定方式开启服务后，当界面不可见时服务就会被关闭 ( F )

4.在服务中可以处理长时间的耗时操作 ( T )

5.服务不是Android中的四大组件之一，因此不需要在清单文件中注册 ( F )

### 三、选择题

1.每一次启动服务都会调用的方法是 ( B )

A.onCreate()

B.onStart()

C.onResume()

D.onStartCommand()

2.下列选项中，属于绑定服务特点的是 ( AC )

A.以bindService()方法开启

B.调用者关闭后服务关闭

C.必须实现ServiceConnection

D.使用stopService()方法关闭服务

3.Service与Activity的共同点是 ( A )

A.都是四大组件之一

B.都有onResume()方法

C.都可以被远程调用

D.都可以自定义美观界面

4.下列方法中，不属于Service生命周期的是 ( A )

A.onResume()

B.onStart()

C.onStop()

D.onDestory()

5.关于Service生命周期的onCreate()和onStart()方法，说法正确的是 ( BD )

A.如果Service已经启动，将先后调用onCreate()方法和onStart()方法

B.当第一次启动的时候先后调用onCreate()和onStart()方法

C.当第一次启动的时候只会调用onCreate()方法

D.如果Service已经启动，只会执行onStart()方法，不再执行onCreat()方法

### 四、简答题

1.请简要说明AIDL访问远程服务的步骤
  * 在需要被调用的服务的项目中创建AIDL接口
  * 创建相应的服务
  * 创建第二个项目用于调用服务，将服务中的AIDL接口拷贝到第二个项目中

2.请简要说明Service的几种启动方式及其特点
  * start方式 : 服务与调用者没有关系，调用者关闭后服务仍然运行
  * bind方式 : 服务者与调用者的生命周期关联，调用者关闭后服务也关闭

### 五、编程题

1.请编写程序，要求程序关闭10秒后重启改程序

2.请编写两个程序，一个作为服务端，一个作为客户端，在客户端中访问服务端程序时传入int参数，
参数必须大于100时才能访问

---------------

## 第九章

### 一、填空题

1.Android系统提供了多种网络通信方式，包括(Socket通信)、(URL通信)、(HTTP通信)和(WebView)

2.当客户端与服务器端建立连接后，向服务器端发送的请求，被称为( HTTP请求 )

3.Android客户端访问网络发送HTTP请求的方式有两种，分别是( HTTPURLConnection )和( HTTPClient )

4.与服务器交互过程中，最常用的两种数据提交方式是( get )和( post )

5.为了根据下载进度实时更新UI界面，需要用到Handle消息机制来实现( 线程间通信 )

### 二、判断题

1.HttpURLConnection是一个标准的Java类 ( T )

2.使用HttpClient访问网络时，不需要创建HttpClient对象 ( F )

3.GET方式是以实体的方式得到由请求URL所指向的资源信息 ( T )

4.HttpClient是对AsyncHttpClient的再次包装 ( F )

5.在多线程下载中，每个线程必须要下载对应的模块，然后将这些模块顺序序组组合 ( T )

### 三、选择题

1.下列选项中，不属于Handler机制中的关键对象是 ( A )

A.Content

B.Handler

C.MessageQueue

D.Looper

2.下列通信方式中，不是Android系统提供的是 ( D )

A.Socket通信

B.HTTP通信

C.URL通信

D.以太网通信

3.关于HttpURLConnection访问网络的基本用法，描述错误的是 ( C )

A.HttpURLConnection对象需要设置请求网络的方式

B.HttpURLConnection对象需要设置超时时间

C.需要通过new关键字来创建HttpURLConnection对象

D.访问网络完毕需要关闭HTTP链接

4.下列选项中，不属于AsyncHttpClient特点的是 ( D )

A.发送异步HTTP请求

B.HTTP请求发生在UI线程之外

C.内部采用了线程池来处理并发请求

D.自动垃圾回收

5.下列选项中，关于GET和POST请求方式，描述错误的是 ( B )

A.使用GET方式访问网络URL的长度是有限制的

B.HTTP协议规定GET方式请求URL的长度不超过2K

C.POST方式对URL的长度是没有限制的

D.GET请求方式向服务器提交的参数跟在请求URL后面

### 四、简答题

1.请简述使用HTTPClient访问网络的步骤
  * 创建HTTPClient对象
  * 指定访问网络的方式
  * 如果需要设置方法参数，可以使用setParams()/setEntity()
  * 调用HTTPClient对象的execute()方法访问网络，并获取HTTPResponse对象
  * 调用HTTPResponse对象的getEntity()方法获取响应内容

2.请简述Handler机制4个关键对象的作用
  * Message ：携带待交换的数据
  * Handler : 用于发送消息和处理消息
  * MessageQueue : 存放通过handler发送的信息
  * Looper : 调用loop()方法后进入死循环，每当发现MessageQueue中存在消息时就处理消息


### 五、编程题

1.请使用AsyncHttpClient和SmartImageView实现一个新闻客户端，并且要求界面美观、至少
展示10条数据

2.请编写程序，通过多线程的形式下载Tomact服务器中的指定文件，要求下载的文件不能损坏
