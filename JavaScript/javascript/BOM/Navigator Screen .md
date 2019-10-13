## Navigator对象

==============

### Navigator对象属性
### Navigator.userAgent
### Navigator.plugins
### Navigator.platform 
### Navigator.onLine
### Navigator.language，Navigator.languages 
### Navigator.geolocation
### Navigator.cookieEnabled

===================

### Navigator对象方法
### Navigator.javaEnabled()
### Navigator.sendBeacon()

## Screen 对象
* Screen.height：浏览器窗口所在的屏幕的高度（单位像素）。除非调整显示器的分辨率，否则这个值可以看作常量，不会发生变化。显示器的分辨率与浏览器设置无关，缩放网页并不会改变分辨率。
* Screen.width：浏览器窗口所在的屏幕的宽度（单位像素）。
* Screen.availHeight：浏览器窗口可用的屏幕高度（单位像素）。因为部分空间可能不可用，比如系统的任务栏或者 Mac 系统屏幕底部的 Dock 区，这个属性等于height减去那些被系统组件的高度。
* Screen.availWidth：浏览器窗口可用的屏幕宽度（单位像素）。
* Screen.pixelDepth：整数，表示屏幕的色彩位数，比如24表示屏幕提供24位色彩。
* Screen.colorDepth：Screen.pixelDepth的别名。严格地说，colorDepth 表示应用程序的颜色深度，pixelDepth 表示屏幕的颜色深度，绝大多数情况下，它们都是同一件事。
* Screen.orientation：返回一个对象，表示屏幕的方向。该对象的type属性是一个字符串，表示屏幕的具体方向，landscape-primary表示横放，landscape-secondary表示颠倒的横放，portrait-primary表示竖放，portrait-secondary
