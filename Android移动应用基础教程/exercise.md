
## 第二章

### 一、填空题

1.Android的布局有6种，分别是\_\_、\_\_、\_\_、\_\_、\_\_和\__。

2.Adnroid相对布局中，表示“是否跟父布局左对齐的”的属性是\_\_\_。

3.线性布局主要有两种形式，一种\_\_线性布局，另一种是\_\_线性布局。

4.创建Android程序时，默认使用的布局是\_\_。

5.LogCat区域中有V、D、I、W和E，其中V代表\_\_，D代表\_\_，I代表\_\_，W代表\_\_，E代表\_\_。

### 二、判断题

1.相对布局中android:layout_alignRight表示“与指定控件右对齐”

2.Toast的作用是显示一些提示信息

3.TableRow必须要设置layout_width和layout_height属性

4.帧布局中可以添加多个控件，这些控件会重叠的在屏幕左上角显式

5.Adnroid是不支持国际化的

### 三、选择题

1.以下属性中，()属性可以"在指定控件左边"

A.android:layout_alignLeft

B.android:layout_alignParentLeft

C.android:layout_left

D.android:layout_toLeftOf

2.表格布局中android:layout_column属性的作用是指定()

A.行数

B.列数

C.总行数

D.总列数

3.实际开发中刮刮乐游戏的布局是按照()写的

A.相对布局

B.线性布局

C.帧布局

D.绝对布局

4.网络布局是Adnroid()新增的布局

A.3.0

B.3.1

C.3.2

D.4.0

5.相对布局中，"是否跟父布局底部对齐"属性是

A.android：layout_alignBottom

B.android:layput_alignParentBottom

C.android:layout_alignBaseline

D.android:alyout_below

### 四、简答题

1.请简述如何在程序中使用Toast

2.请说明布局有几种类型，以及每种类型的作用

### 五、编程题

1.编写一个用户登录界面，界面中必须要有文本提示信息、编辑框、按钮，分别用于显示用户名、密码，输入用户名、密码，登录功能

2.自定义一个样式，使用这个样式修改界面中的背景色，并且美化界面中的文字信息

-------------------------------------
## 第三章

### 一、填空题

1.Android生命周期的三种状态分别是\_\_、\_\_、\_\_

2.Adnroid的四种启动模式是\_\_、\_\_、\_\_、\_\_

3.Adnroid中Intent寻找目标组件的方式有两种：\_\_和\_\_

4.Activity生命周期中"回到前台，再次可见时执行"时调用的方法是\_\_

5.Android中提供了一个\_\_方法实现回传数据

### 二、判断题

1.Activity是Android应用程序的四大组件之一

2.Intent一般只用于启动Activity，不能开启广播和服务

3.Intent可以用来开启Activity，同样它也可以用来在Activity之间传递数据

4.Activity默认的启动模式是singleTop模式

5.在数据传递时，如果需要获取返回的数据，需要使用onActivityResult()方法

### 三、选择题

1.一个应用程序默认会包含()个Activity

A. 1

B. 5

C. 10

D. 若干

2.下列方法中，Activity从启动到关闭不会执行的是()

A. onCreate()

B. onStart()

C. onResume()

D. onRestart()

3.下列组件中，不能使用Intent启动的是()

A. Activity

B. 启动服务

C. 广播

D. 内容提供者

4.startActivityForResult()方法接收两个参数，第一个是Intent，第二个是()

A. resultCode

B. requestCode

C. 请求码

D. data

5.下列关于Activity的描述，错误的是()

A. Activity是Android的四大组件之一

B. Activity有四种启动模式

C. Activity通常用于开启一个广播事件

D. Activity就像一个界面管理员，用户在界面上的操作是通过Activity来管理

### 四、简答题

1.简要说明Activity的四种启动模式的区别

2.简要说明Activity的三种状态以及不同状态使用的方法


-------------
## 第四章

### 一、填空题

1.序列化是将对象状态转换为\_\_的过程

2.Android中的文件可以存储在\_\_和\_\_中

3.通常情况下，解析XML文件有三种方式：\_\_、\_\_和\_\_

4.SharedPrteferences是一个轻量级的存储类，主要用于存储一些应用程序的\_\_

5.Adnroid中的数据存储方式有5种，分别是\_\_、\_\_、\_\_、\_\_和\_\_

### 二、判断题

1.SharedPrteferences本质上是一个XML文件，以Map<key,value>形式存入文件中

2.文件存储是通过I/O流的形式把数据原封不动的存储到文档中

3.XML文件只能用来保存本地数据，不能在网络中传输

4.ContentProvider表示内容提供者，用于显示程序中的数据

5.当用户文件保存到SD卡时，需要在清单文件中添加权限"android:permission.WRITE_EXTERNAL_STORAGE"

### 三、选择题

1.下列文件操作权限中，指定文件内容可以追加的是

A.MODE_PRIVATE

B.MODE_WORLD_READABLE

C.MODE_APPEND

D.MODE_WORLD_WRITEABLE

2.下列代码中，用于获取SD卡路径的是

A.Environment.getSD()

B.Environment.getExternalStorageState()

C.Environment.getSDDirectory()

D.Environment.getExternalStorageDirectory()

3.下列选项中，关于文件存储数据的说法错误的是

A.文件存储是以流的形式来操作数据的

B.文件存储可以将数据存储到SD卡

C.文件存储可以将数据存储到内存中

D.Android中只能使用文件存储数据

4.下列选项中，关于XML序列化和解析描述合理的是

A.DOM解析会将XML文件的所有内容以文档树形式存放在内存中

B.在序列化对象使，需要使用XmlSerialize序列化器，即XmlSerializer类

C.XmlSerializer类的startDocument()方法用于写入序列号的开始结点

D.XmlSerializer类的setOutput()方法用于设置文件的编码方式

5.如果要将程序中的私有数据分享给其他应用程序，可以使用的是

A.文件存储

B.SharedPrteferences

C.ContentProvider

D.SQLite

### 四、简答题

1.请简述Android中5种数据存储方式各自的特点

2.请简述SharedPrteferences如何存储数据

### 五、编程题

1.请自定义一个XMl文件，并将XML文件中的内容解析出来

2.请编写一个短信草稿箱的程序，要求用户在文本编辑框中输入短信内容后，单击"保存短信"按钮，
将短信保存在SharedPrteferences中

----------------------------------
## 第五章

### 一、填空题

1.ListView的适配器有三种，分别是\_\_、\_\_和\_\_

2.创建数据库以及数据库版本更新需要继承\_\_

3.SQLite创建时调用\_\_方法，升级时调用\_\_方法

4.要查询SQLite数据库中的信息需要使用\_\_接口，接口完毕后调用\_\_关闭

5.创建ListView的布局界面必须通过\_\_属性才能使数据显示在界面上

### 二、判断题

1.SQLite数据库使用完后不需要关闭，不影响程序性能

2.使用ListView显示较为复杂的数据时最好用ArrayAdapter适配器

3.SQLite既支持Android的API又支持SQL语句进行增、删、改、查操作

4.使用BaseAdapter控制ListView显示多少条数据是通过getView()方法设置

5.SQLite只支持NULL、INTEGER、REAL、TEXT和BLOB等5种数据类型

### 三、选择题

1.使用SQLite数据库进行查询后， 必须要做的操作的是

A.关闭数据库

B.直接退出

C.关闭cursor

D.使用quit函数退出

2.关于适配器的说法正确的是

A.它主要用来存储数据

B.它主要用来把数据绑定在组件上

C.它主要用来存储XML数据

D.它主要用来解析数据

3.使用SQLiteOpenHelper类可以生成一个数据库并可以对数据库版本进行管理的方法

A.getDatabase()

B.getWriteableDatabase()

C.getReadableDatabase()

D.getAbleDatabase()

4.下列命令中，属于SQLite下的命令是

A.shell

B.push

C.quit

D.keytool

5.下列关于ListView使用的描述中，不正确的是

A.要使用ListView，必须为该ListView使用Adapter方式传递数据

B.要使用ListView，该布局文件对应的Activity必须继承ListActivity

C.ListView中每一项的视图布局既可以使用内置的布局，也可以使用自定义的布局方式

D.ListView中每一项被选中时，将会触发ListView对象的ItemClick事件

### 四、简答题

1.请简要说明SQLite数据库创建的过程

2.请简要说明BaseAdapter适配器4个抽象方法以及它们的具体作用

### 五、编程题

1.请使用ListView显示10行数据在界面上，分别用三种适配器实现

2.请创建一个fruit.db表，在表中存入5种水果信息，并将这些信息显示到ListView控件中

----------------------
## 第六章

### 一、填空题

1.ContentProvider匹配Uri需要使用的类是\_\_

2.使用内容观察者时，调用\_\_方法可以得到数据变化的信息

3.ContentProvider提供了对数据增、删、改、查的方法，分别为\_\_、\_\_、\_\_和\_\_

4.ContentProvider用于\_\_和\_\_数据，是Android中不同应用程序之间共享数据的接口

5.在应用程序中，使用ContentProvider暴露自己的数据，通过\_\_对暴露的数据进行操作

###　二、判断题

1.ContentProvider所提供的Uri可以随便定义

2.ContentResolver可以通过ContentProvider提供的Uri进行数据操作

3.ContentObserver观察指定Uri数据发生变化时调用ContentProvider的是onChange()方法

4.使用ContentResolver操作数据时，必须在清单文件进行注册

5.ContentProvider与Activity一样，创建时首先会调用onCreate()方法

### 三、选择题

1.下列选项中，属于Android四大组件的是

A.Activity

B.ContentReceiver

C.Service

D.ContentObserver

2.下列关于ContentResolver的描述，错误的是

A.可以操作数据库数据

B.操作其他应用数据必须知道包名

C.只能操作ContentProvider暴露的数据

D.可以操作ContentProvider的任意数据

3.下列关于ContentProvider的描述正确的是

A.提供的Uri必须符合规范

B.可以提供本应用所有数据供别人访问

C.必须在清单文件注册

D.authorities属性必须和包名一致

4.继承ContentProvider类必须重写它的

A.delete()

B.insert()

C.onStart()

D.onUpdate()

5.下列关于ContentObserver的说法正确的是

A.可以观察任何数据

B.观察其他应用数据需要权限

C.只能观察到指定的Uri的数据

D.观察其他应用数据必须在清单文件注册

### 四、简答题

1.请简要说明ContentProvider对外共享数据的好处

2.请简要说明ContentProvider、ContentResolver和ContentObserver之间的联系

### 五、编程题

1.使用ContentProvider管理联系人信息，将联系人信息展示在界面上

2.获取系统图库的信息，使用ContentProvider制作本地图片查看器
-------------

## 第七章

### 一、填空题

1.广播接收者可以在清单文件使用\_\_注册

2.停止广播需要使用\_\_方法

3.广播的发送有两种形式，分别为\_\_和\_\_

4.代码注册广播需要使用\_\_方法，解除广播需要使用\_\_方法

5.指定接收广播类型的函数是\_\_

### 二、判断题

1.每一个广播只能有一个广播接收者

2.广播接收者是四大组件之一，必须在清单文件中注册

3.广播接收者的注册信息必须要保持唯一性

4.可以在BroadcastReceiver和onReceive方法中处理耗时负责的业务

5.广播接收者在注册后必须手动关闭

### 三、选择题

1.继承BroadcastReceiver需要重写的方法是

A.onReceive()

B.onUpdate()

C.onCreate()

D.onStart()

2.关于广播的作用，说法正确是

A.它主要用于接收系统发出的一些消息

B.它可以进行耗时的操作

C.它可以启动一个Activity

D.它可以帮助Activity修改用户界面

3.下列方法中，用于发送一条有序广播的是

A.startBroadcastReceiver()

B.sendOrderdedBroadcast()

C.sendBroadcast()

D.sendReceiver()

4.在清单文件中，注册广播时使用的结点是

A.\<activity\>

B.\<broadcast\>

C.\<receiver\>

D.\<broadcastreceiver\>

5.关于BroadcastReceiver说法不正确的是

A.是用来接收广播Intent的

B.一个广播Intent只能被一个订阅了此广播的BroadcastReceiver接收

C.对有序广播，系统会根据接受者声明的优先级别按顺序逐个执行接收者

D.接收者生命的优先级别在android:priority属性中声明，数值越大优先级别高

### 四、简答题

1.说明注册广播有几种方式，以及这些方式有何优缺点

2.简要说明接收系统广播时哪些功能需要使用权限

### 五、编程题

1.编写程序，监控手机电量，当电量小于15%时进行提示

2.编写程序，根据关键词过滤经常接收到的骚扰短信



-------------

## 第八章

### 一、填空题

1.在创建服务时，必须要继承\_\_类

2.绑定服务时，必须要实现服务的\_\_方法

3.在清单文件中，注册服务时应该使用的结点是\_\_

4.服务的开启方式有两种，分别是\_\_和\_\_

5.在进行远程服务通信时，需要使用\_\_接口

### 二、判断题

1.以绑定方式开启服务后，服务与调用者没有关系

2.服务的界面可以设置的很美观

3.以绑定方式开启服务后，当界面不可见时服务就会被关闭

4.在服务中可以处理长时间的耗时操作

5.服务不是Android中的四大组件之一，因此不需要在清单文件中注册

### 三、选择题

1.每一次启动服务都会调用的方法是

A.onCreate()

B.onStart()

C.onResume()

D.onStartCommand()

2.下列选项中，属于绑定服务特点的是

A.以bindService()方法开启

B.调用者关闭后服务关闭

C.必须实现ServiceConnection

D.使用stopService()方法关闭服务

3.Service与Activity的共同点是

A.都是四大组件之一

B.都有onResume()方法

C.都可以被远程调用

D.都可以自定义美观界面

4.下列方法中，不属于Service生命周期的是

A.onResume()

B.onStart()

C.onStop()

D.onDestory()

5.关于Service生命周期的onCreate()和onStart()方法，说法正确的是

A.如果Service已经启动，将先后调用onCreate()方法和onStart()方法

B.当第一次启动的时候先后调用onCreate()和onStart()方法

C.当第一次启动的时候只会调用onCreate()方法

D.如果Service已经启动，只会执行onStart()方法，不再执行onCreat()方法

### 四、简答题

1.请简要说明AIDL访问远程服务的步骤

2.请简要说明Service的几种启动方式及其特点

### 五、编程题

1.请编写程序，要求程序关闭10秒后重启改程序

2.请编写两个程序，一个作为服务端，一个作为客户端，在客户端中访问服务端程序时传入int参数，
参数必须大于100时才能访问

---------------

## 第九章

### 一、填空题

1.Android系统提供了多种网络通信方式，包括\_\_、\_\_、\_\_和\_\_

2.当客户端与服务器端建立连接后，向服务器端发送的请求，被称为\_\_

3.Android客户端访问网络发送HTTP请求的方式有两种，分别是\_\_和\_\_

4.与服务器交互过程中，最常用的两种数据提交方式是\_\_和\_\_

5.为了根据下载进度实时更新UI界面，需要用到Handle消息机制来实现\_\_

### 二、判断题

1.HttpURLConnection是一个标准的Java类。

2.使用HttpClient访问网络时，不需要创建HttpClient对象。

3.GET方式是以实体的方式得到由请求URL所指向的资源信息

4.HttpClient是对AsyncHttpClient的再次包装

5.在多线程下载中，每个线程必须要下载对应的模块，然后将这些模块顺序序组组合

### 三、选择题

1.下列选项中，不属于Handler机制中的关键对象是

A.Content

B.Handler

C.MessageQueue

D.Looper

2.下列通信方式中，不是Android系统提供的是

A.Socket通信

B.HTTP通信

C.URL通信

D.以太网通信

3.关于HttpURLConnection访问网络的基本用法，描述错误的是

A.HttpURLConnection对象需要设置请求网络的方式

B.HttpURLConnection对象需要设置超时时间

C.需要通过new关键字来创建HttpURLConnection对象

D.访问网络完毕需要关闭HTTP链接

4.下列选项中，不属于AsyncHttpClient特点的是

A.发送异步HTTP请求

B.HTTP请求发生在UI线程之外

C.内部采用了线程池来处理并发请求

D.自动垃圾回收

5.下列选项中，关于GET和POST请求方式，描述错误的是

A.使用GET方式访问网络URL的长度是有限制的

B.HTTP协议规定GET方式请求URL的长度不超过2K

C.POST方式对URL的长度是没有限制的

D.GET请求方式向服务器提交的参数跟在请求URL后面

### 四、简答题

1.  请简述使用HTTPClient访问网络的步骤

2.请简述Handler机制4个关键对象的作用


### 五、编程题

1.请使用AsyncHttpClient和SmartImageView实现一个新闻客户端，并且要求界面美观、至少
展示10条数据

2.请编写程序，通过多线程的形式下载Tomact服务器中的指定文件，要求下载的文件不能损坏
