## 概述
浏览器里面，window对象（注意，w为小写）指当前的浏览器窗口。它也是当前页面的顶层对象，即最高一层的对象，所有其他对象都是它的下属。  
这种设计使得编译阶段无法检测出未声明变量，但到了今天已经没有办法纠正了。
## windows对象的属性
### window.name
window.name属性是一个字符串（自动转换），表示当前浏览器窗口的名字。窗口不一定需要名字，这个属性主要配合超链接和表单的target属性使用。
### window.closed，window.opener
window.closed属性返回一个布尔值，表示窗口是否关闭。window.opener属性表示打开当前窗口的父窗口。如果当前窗口没有父窗口（即直接在地址栏输入打开），则返回null。  
### window.self，window.window 
window.self和window.window属性都指向窗口本身。这两个属性只读。
### window.frames，window.length 
window.frames属性返回一个类似数组的对象，成员为页面内所有框架窗口，包括frame元素（是不是废除了？）和iframe元素。window.frames[0]表示页面中第一个框架窗口。indow.length属性返回当前网页包含的框架总数。  
如果iframe元素设置了id或name属性，那么就可以用属性值，引用这个iframe窗口。比如<iframe name="myIFrame">可以用frames['myIFrame']或者frames.myIFrame来引用。frames属性实际上是window对象的别名。   
  
### window.frameElement
window.frameElement属性主要用于当前窗口嵌在另一个网页的情况（嵌入<object>、<iframe>或<embed>元素），返回当前窗口所在的那个元素节点。如果当前窗口是顶层窗口，或者所嵌入的那个网页不是同源的，该属性返回null。
  
### window.top，window.parent
window.top属性指向最顶层窗口，主要用于在框架窗口（frame）里面获取顶层窗口。window.parent属性指向父窗口。如果当前窗口没有父窗口，window.parent指向自身。对于不包含框架的网页，这两个属性等同于window对象。

### window.status
用于读写浏览器状态栏的文本。但是，现在很多浏览器都不允许改写状态栏文本，所以使用这个方法不一定有效。

### window.devicePixelRatio
属性返回一个数值，表示一个 CSS 像素的大小与一个物理像素的大小之间的比率。也就是说，它表示一个 CSS 像素由多少个物理像素组成。它可以用于判断用户的显示环境，如果这个比率较大，就表示用户正在使用高清屏幕，因此可以显示较大像素的图片。

### 位置大小属性
* window.screenX，window.screenY  
window.screenX和window.screenY属性，返回浏览器窗口左上角相对于当前屏幕左上角的水平距离和垂直距离（单位像素）。这两个属性只读。
* window.innerHeight，window.innerWidth
window.innerHeight和window.innerWidth属性，返回网页在当前窗口中可见部分的高度和宽度，即“视口”（viewport）的大小（单位像素）。这两个属性只读。注意，这两个属性值包括滚动条的高度和宽度
* window.outerHeight，window.outerWidth  
window.outerHeight和window.outerWidth属性返回浏览器窗口的高度和宽度，包括浏览器菜单和边框（单位像素）。这两个属性只读  
* window.scrollX，window.scrollY  
window.scrollX属性返回页面的水平滚动距离，window.scrollY属性返回页面的垂直滚动距离，单位都为像素。这两个属性只读。注意，这两个属性的返回值不是整数，而是双精度浮点数。如果页面没有滚动，它们的值就是0。  
* window.pageXOffset，window.pageYOffset  
window.pageXOffset属性和window.pageYOffset属性，是window.scrollX和window.scrollY别名。  

============================  
  
### 组件属性
组件属性返回浏览器的组件对象。这样的属性有下面几个。
* window.locationbar：地址栏对象
* window.menubar：菜单栏对象
* window.scrollbars：窗口的滚动条对象
* window.toolbar：工具栏对象
* window.statusbar：状态栏对象
* window.personalbar：用户安装的个人工具栏对象  
这些对象的visible属性是一个布尔值，表示这些组件是否可见。这些属性只读  
  
============================  

全局对象属性指向一些浏览器原生的全局对象。
* window.document：指向document对象，详见《document 对象》一章。注意，这个属性有同源限制。只有来自同源的脚本才能读取这个属性。
* window.location：指向Location对象，用于获取当前窗口的 URL 信息。它等同于document.location属性，详见《Location 对象》一章。
* window.navigator：指向Navigator对象，用于获取环境信息，详见《Navigator 对象》一章。
* window.history：指向History对象，表示浏览器的浏览历史，详见《History 对象》一章。
* window.localStorage：指向本地储存的 localStorage 数据，详见《Storage 接口》一章。
* window.sessionStorage：指向本地储存的 sessionStorage 数据，详见《Storage 接口》一章。
* window.console：指向console对象，用于操作控制台，详见《console 对象》一章。
* window.screen：指向Screen对象，表示屏幕信息，详见《Screen 对象》一章  

### window.isSecureContext
window.isSecureContext属性返回一个布尔值，表示当前窗口是否处在加密环境。如果是 HTTPS 协议，就是true，否则就是false。

## window对象的方法

### window.alert()，window.prompt()，window.confirm()
### window.open(), window.close()，window.stop()
### window.moveTo()，window.moveBy()
### window.resizeTo()，window.resizeBy()
### window.scrollTo()，window.scroll()，window.scrollBy()
### window.print()
### window.focus()，window.blur()
### window.getSelection()
### window.getComputedStyle()，window.matchMedia()
### window.requestAnimationFrame()
### window.requestIdleCallback()

## window 接收事件
### load 事件和 onload 属性
### error 事件和 onerror 属性
### window 对象的事件监听属性

## 多窗口操作
### iframe 元素
### window.frames 属性

