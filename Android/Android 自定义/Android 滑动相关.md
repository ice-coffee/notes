##Android 滑动相关

###参考
[滑动速度跟踪类VelocityTracker介绍](http://www.jcodecraeer.com/a/anzhuokaifa/androidkaifa/2012/1117/574.html)
[ViewConfiguration.getScaledTouchSlop () 用法](http://www.jcodecraeer.com/a/anzhuokaifa/androidkaifa/2013/0225/907.html)
[Android 滚动操作Scroller类详解](http://www.jcodecraeer.com/a/anzhuokaifa/androidkaifa/2012/1202/669.html)
[Android Scroller完全解析，关于Scroller你所需知道的一切](http://blog.csdn.net/guolin_blog/article/details/48719871)
[Android Scroller实现View弹性滑动完全解析](http://www.jianshu.com/p/9419262a342a)

###VelocityTracker
>分析MotionEvent 对象在单位时间类发生的位移来计算速度

- addMovement(MotionEvent event) : 添加一个移动事件到跟踪器
- getXVelocity() : 返回值为X轴单位时间内最新的速度.
- getYVelocity() : 返回值为Y轴单位时间内最新的速度.
- computeCurrentVelocity(int units) : 初始化速率的单位
- computeCurrentVelocity(int units, float maxVelocity) : 初始化速率的单位并设置最大速度.

###ViewConfiguration
ViewConfiguration中保存的是Android UI中的一些默认参数, 常用的有: 
- getScaledTouchSlop() : 表示滑动的时候，手的移动要大于这个距离才开始移动控件。
- getScaledMinimumFlingVelocity() : 允许执行一个fling手势动作的最小速度值。
- getScaledMaximumFlingVelocity() : 允许执行一个fling手势动作的最大速度值。

###Scroller