Android-TV
================================================
屏幕适配
----------------------------------------------
</br>
 屏幕适配时文件包可以写成values-160dpi ，dpi为像素密度指的是每英寸距离的像素点数 ，density为屏幕密度指的是每平方英寸的像素点数。</br>
 换算公式：dpi = density * 160;</br>
 我们可以根据以下代码获取到density信息</br>
 DisplayMetrics metrics = new DisplayMetrics();</br>
 getWindowManager().getDefaultDisplay().getMetrics(metrics);</br>
 LogUtil.i(metrics.toString());</br>
 这是谷歌TV端模拟器分率为：1920 * 1080 获取到的信息如下：</br>
 DisplayMetrics{density=2.0, width=1920, height=1080, scaledDensity=2.0, xdpi=320.0, ydpi=320.0}</br>
 density = 2;</br>
 android中像素和密度的关系如下公式：</br>
 px = dpi/160 * dp</br>
 可以得出下面公式：</br>
 px = density * dp</br>
 dp = px/density</br>
 那么该模拟器的宽转化为dp=1920/2 = 960dp。</br>
 在做屏幕适配时，我们可以根据以上这些公式换算成我们需要的dp</br>
 并且生成对应的values包</br>
 例如：</br>
 机顶盒为：1920 * 1080 density =1  那么dpi = 160 图片是一倍图 mipmap-mdpi 对应的values可以写成values-160dpi</br>
 谷歌模拟器为：1920 * 1080 density =2 那么dpi = 320 图片是二倍图 mipmap-xhdpi  对应的values可以写成values-320dpi</br>
 </br>

<2>焦点的处理<br>
-------------------------------------------------


