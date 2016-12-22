# ContentProvider

ContentProvider是Android四大组件之一，用于保存和检索数据，是系统中不同应用程序之间
共享数据的接口。

ContentProvider以URI的形式对外提供资源，其他应用使用ContentResolver操作资源，使用ContentObserver
对资源的变化做出响应

## 创建ContentProvider

ContentProvider是一个抽象类，使用时需要自定义类来继承它，它有几个方法需要子类实现
* public boolean onCreate()
* public int delete(Uri uri, String selection, String[] selectionArgs)
* public Uri insert(Uri uri, ContentValues values)
* public Cursor query(Uri uri, String[] projection, String selection, String[] selectionArgs, String sortOrder)
* punlic int update(Uri uri, String[] projection, String selection, String[] selectionArgs)
* public String getType(Uri uri)

创建后需要在Manifest.xml中进行注册
```
<provider
  android:name="xxxx"//本Provider的位置
  android:authorities="xxx"//访问本Provider的路径
 />
```

## URI简介

URI由`scheme`、`authorities`、`path`三部分组成

## ContentObserver

ContentObserver是用来观察指定URI代表的数据，当数据变化时，就会触发ContentObserver的onChange()方法，该方法里可以查询到变化的数据

如果要使用ContentObserver观察数据变化时需要在ContentProvider的delete、insert、update方法中调用ContentResolver的`notifyChange()`方法
