# Android UI开发

## 概述

一个Android应用的界面是由View和ViewGroup对象构成的。View类是Android系统平台上用户界面
表示的基本单元，View类的一些子类被统称为Widgets，它们提供了诸如文本输入框和按钮之类的UI
对象的完整实现。ViewGroup是View的一个扩展，可以容纳多个View。

## 布局文件的创建

Android应用程序中，界面是通过布局文件设定的，布局文件采用xml格式。每个应用默认包含一个
主界面布局文件，该文件位于项目的res/layout目录中。

布局文件创建完成后，在class类中的onCreate()方法中通过setContentView()将指定的布局文件
进行加载。

## 布局的类型

### RelativeLayout

该布局是Android的默认布局，通常有两种形式，一种是相对于容器而言，一种是相对于控件而言，
该布局提供了很多属性，具体参考API。

> 控件单位的使用

出于屏幕适配的考虑，在指定控件和布局宽高时推荐使用`match_parent`或`wrap_content`，尽量避免将控件的宽高设置固定值。

指定宽高的固定值有4种单位可供选择

* px
  * 代表像素，使用px来控制大小的控件，在分辨率不同的手机上控件显示的大小不同
* pt
  * 代表磅数，一般将该单位作为字体的单位，与px类似，在分辨率不同的手机上文字显示的大小不同
* dp
  * 代表密度无关像素，在不同屏幕密度的手机上显示的尺寸一样，推荐控件与布局时使用
* sp
  * 代表可伸缩像素，与dp类似，推荐设置文字大小时使用

### LinerLayout

该布局有两种形式，一种是水平线性布局，一种是垂直线性布局，通过设置`android:orientation`的值来实现

### TableLayout

该布局让控件以表格的形式来排列控件。

在该布局中，行数由TableRow对象控制，列数由最宽的单元格决定，在控件中通过`android:layout_column`指定具体的列数(该属性的值从0开始)

### GridLayout

该布局实现了控件的交错显示，使用一组无限细的直线将绘图区域划分成行、列和单元。该布局为Android4.0开始支持。

### FrameLayout

该布局是Android布局中最简单的一种，该布局为每个加入其中的控件创建一个空白区域。

### AbsoluteLayout

该布局需要通过指定x、y坐标来控制每一个控件的位置，通过`android:layout_x`和`android:layout_y`来指定x、y坐标，该布局以屏幕左上角为坐标原点。

##　样式和主题

样式和CSS作用相似，都是用于为界面元素定义显示风格，它是一个包含一个或多个View控件属性的集合。样式只能作用于单个的View，如EditText、TextView。

主题也是包含一个或多个View控件属性的集合。主题是通过AndroidManifest.xml中的`<application>`和`<activity>`结点影响整个应用或者Activity。

样式的优先级高于主题

## 国际化

Android程序国际化只需要为资源文件提供不同语言国家或地区对应的内容即可。
新建的values文件命名规则如下
> values-语言代码-r国家或地区代码

## 程序调试

通常使用JUnit进行单元测试

在AndroidManifest.xml的<manifest>结点下配置指令集`<instrumentation>`和在<application>结点下配置函数库`<uses-library>`

```
<manifest>
  <application>
    <uses-library android:name="android.test.runner" />
  </application>
  <instrumentation
    android:name="android.test.InstrumentationTestRunner"
    android:targetPackage="xxxxxx"
  />
</manifest>

```
## LogCat的使用

在Android进行信息输出，一般采用android.util.Log类的静态方法，日志内容分为五个级别，由低到高分别是Verbose、Debug、Info、Warning、Error，分别对应Log.v()、Log.d()、Log.i()、Log.w()、Log.e()
