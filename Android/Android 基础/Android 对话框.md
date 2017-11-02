##Android 对话框

[TOC]

对话框的几种实现形式
1. Dialog
2. AlertDialog
3. ProgressDialog
4. DialogFragment
5. Dialog 风格的 Activity

###1. AlertDialog
####说明
AlertDialog是拥有Material风格的Dialog, 
####时间
`Android Support Library v22.1` 开始提供AlertDialog.

####使用
[AlertDialog使用](https://github.com/Qiang3570/Dialog)

###2. DialogFragment
####说明

####时间
DialogFragment在android 3.0时被引入

####使用
DialogFragment + AlertDialog制作对话框
[Android 官方推荐 : DialogFragment 创建对话框](http://blog.csdn.net/lmj623565791/article/details/37815413)

###3. Popupwindow和Dialog的区别
1. Popupwindow在显示之前一定要设置宽高，Dialog无此限制。

2. Popupwindow默认不会响应物理键盘的back，除非显示设置了popup.setFocusable(true);而在点击back的时候，Dialog会消失。

3. Popupwindow不会给页面其他的部分添加蒙层，而Dialog会。

4. Popupwindow没有标题，Dialog默认有标题，可以通过dialog.requestWindowFeature(Window.FEATURE_NO_TITLE);取消标题

5. 二者显示的时候都要设置Gravity。如果不设置，Dialog默认是Gravity.CENTER。

6. 二者都有默认的背景，都可以通过setBackgroundDrawable(new ColorDrawable(android.R.color.transparent));去掉。

其中最本质的差别就是：AlertDialog是非阻塞式对话框：AlertDialog弹出时，后台还可以做事情；而PopupWindow是阻塞式对话框：PopupWindow弹出时，程序会等待，在PopupWindow退出前，程序一直等待，只有当我们调用了dismiss方法的后，PopupWindow退出，程序才会向下执行。这两种区别的表现是：AlertDialog弹出时，背景是黑色的，但是当我们点击背景，AlertDialog会消失，证明程序不仅响应AlertDialog的操作，还响应其他操作，其他程序没有被阻塞，这说明了AlertDialog是非阻塞式对话框；PopupWindow弹出时，背景没有什么变化，但是当我们点击背景的时候，程序没有响应，只允许我们操作PopupWindow，其他操作被阻塞。

###Dialog 风格的 Activity
1. 首先`style.xml`中添加主题.

```
<style name="Theme.ActivityDialogStyle" parent="Theme.AppCompat.Light.NoActionBar">
    <item name="android:windowIsTranslucent">true</item>
    <item name="android:windowBackground">@android:color/transparent</item>
    <item name="android:backgroundDimEnabled">true</item>
    <item name="android:windowContentOverlay">@null</item>
    <item name="android:windowCloseOnTouchOutside">false</item>
    <item name="android:windowIsFloating">true</item>
</style>
```

2. 在 AndroidManifest.xml 中添加 Activity theme

```
android:theme="@style/Theme.ActivityDialogStyle"
```

注意: 在定义Dialog 风格的 Activity 时, 如果Activity继承的是 `AppCompatActivity` , 那theme主题也必须集成`Theme.AppCompat`下的主题.

###参考
[最详细的 Android 对话框介绍](https://juejin.im/entry/58e607cdda2f60005fec9410)
[Android中Popupwindow和Dialog的区别](http://blog.it985.com/6437.html)
