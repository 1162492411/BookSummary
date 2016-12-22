# SQLite数据库

## 简介

SQLi特色遵循ACID关联式的数据库管理系统，支持SQL语句、事务处理等功能

SQLite支持`null`、`integer`、`real`、`text`、`blob`5种数据类型。实际上也接收varchar(n)、char(n)、decimal(p,s)等数据类型，但运算或保存时仍然转换成对应的5种数据类型

## 使用

Android SDK提供了一系列对数据库进行操作的类和接口

** SQLiteOpenHelper类 **

该类是一个抽象类，用于创建数据库和数据库版本更新，下面列出其常用方法
* public SQLiteOpenHelper(Context context, String name, CursorFactory cursorFactory, int version)
  * 构造方法
* public void OnCreate(SQLiteDatabase db)
  * 创建数据库
* public void onUpgrade(SQLiteDatabase db, int oldVersion, int newVersion)
  * 更新数据库版本
* public SQLiteDatabase getReadableDatabase()
  * 创建或打开一个只读的数据库
* public SQLiteDatabase getWriteableDatabase()
  * 创建或打开一个读写的数据库

** SQLiteDatabase类 **

该类是一个数据库访问类，封装了一系列数据库操作的API，下面列出其常用方法
* public long insert(String table, String nullColumnHack, ContentValues values)
  * 添加记录
* public Cursor query(String table, String[] columns, String selection, String[] selectionArgs, String groupBy, String having, String orderBy)
  * 查询数据
* public Cursor rawQuery(String sql, String[] selectionArgs)
  * 执行带占位符的SQL查询
* public int update(String talble, ContentValues values, String whereClause, String[] whereArgs)
  * 修改特定数据
* public int delete(String table, String whereClause, String[] whereArgs)
  * 删除指定数据
* public void execSQL(String sql, Object[] bindArgs)
  * 执行带占位符的SQL语句
* public void close()
  * 关闭数据库

**　Cursor接口 **

Curosr是一个游标接口，在数据库操作中作为返回值，相当于结果集ResultSet，下面列出其常用方法
* boolean moveToNext()
  * 移动光标到下一行
* int getInt(int columnIndex)
  * 获取指定列的整形值
* int getColumnIndex(String columnName)
  * 返回指定索引列下标，返回值为-1表示不存在
* String getString(int columnIndex)
  * 获取指定列的字符串

## ListView控件

该控件以列表的形式展示具体数据内容，且能根据数据的长度自适应屏幕显式。它是一个列表视图，由许多的Item组成。

## 数据适配器
使用ListView时需要使用数据适配器，以使数据显示在界面。可以将数据适配器理解成数据绑定

** BaseAdapter **

这是一个抽象类，提供了四个方法用以数据适配
* public int getCount()
  * 获取Item总数
* public Object getItem(int position)
  * 根据position获取对应的对象
* public long getItemId(int position)
  * 根据position获取对应的id
* public View getView(int position, View contentView, ViewGroup parent)
  * 根据position获取对应的Item视图

** SimpleAdapter **

该类继承了BaseAdapter，实现了其抽象方法，因此使用时只需调用构造器即可，构造器如下

> public SimpleAdapter(Context context, List <? extends Map< String,? > > data, int resource, String[] from, int[] to)

该控件只能适配CheckAble、TextView、ImageView

** ArrayAdapter **

该类继承了BaseAdapter，实现了其抽象方法，因此使用时只需调用构造器即可，构造器如下

> public ArrayAdapter(Contetxt context, int resource, int textViewResourceId, T[] objects)

该类通常适配TextView
