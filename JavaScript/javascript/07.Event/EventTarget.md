# EventTarget

事件的本质是程序各个组成部分之间的一种通信方式，也是异步编程的一种实现。
## EventTarget接口
DOM 的事件操作（监听和触发），都定义在EventTarget接口。  
所有节点对象都部署了这个接口，其他一些需要事件通信的浏览器内置对象（比如，XMLHttpRequest、AudioNode、AudioContext）也部署了这个接口。  
该接口主要提供三个实例方法。  
* addEventListener：绑定事件的监听函数
* removeEventListener：移除事件的监听函数
* dispatchEvent：触发事件
### EventTarget.addEventListener
用于在当前节点或对象上，定义一个特定事件的监听函数。一旦这个事件发生，就会执行监听函数。该方法没有返回值.监听函数内部的this，指向当前事件所在的那个对象。
* target.addEventListener(type, listener[, useCapture])
  * type：事件名称，大小写敏感。
  * listener：监听函数。事件发生时，会调用该监听函数。第二个参数除了监听函数，还可以是一个具有handleEvent方法的对象。
    *  {handleEvent: function (event) {console.log('click');
    *  如果希望向监听函数传递参数，可以用匿名函数包装一下监听函数。function () { print('Hello'); }, 
  * useCapture：布尔值，表示监听函数是否在捕获阶段（capture）触发，默认为false（监听函数只在冒泡阶段被触发）。该参数可选。还可以是一个属性配置对象。该对象有以下属性。
    * capture：布尔值，表示该事件是否在捕获阶段触发监听函数。
    * once：布尔值，表示监听函数是否只触发一次，然后就自动移除。
    * passive：布尔值，表示监听函数会不会调用事件的preventDefault方法。如果监听函数调用了，浏览器将忽略这个要求，并在监控台输出一行警告。  
  
### EventTarget.dispatch()
EventTarget.dispatchEvent方法在当前节点上触发指定事件，从而触发监听函数的执行。该方法返回一个布尔值，只要有一个监听函数调用了Event.preventDefault()，则返回值为false，否则为true.dispatchEvent方法的参数是一个Event对象的实例。

# 事件模型
## 监听函数
浏览器的事件模型，就是通过监听函数（listener）对事件做出反应。事件发生后，浏览器监听到了这个事件，就会执行对应的监听函数。这是事件驱动编程模式（event-driven）的主要编程方式。
* HTML 的 on- 属性，这些属性的值是将会执行的代码，而不是一个函数。使用这个方法指定的监听代码，只会在冒泡阶段触发。
直接设置on-属性，与通过元素节点的setAttribute方法设置on-属性。
* 元素节点的事件属性，也是只会在冒泡阶段触发。注意，这种方法与 HTML 的on-属性的差异是，它的值是函数名（doSomething）。
* EventTarget.addEventListener()
### 三种方式优缺点
* 上面三种方法，第一种“HTML 的 on- 属性”，违反了 HTML 与 JavaScript 代码相分离的原则，将两者写在一起，不利于代码分工，因此不推荐使用。
* 第二种“元素节点的事件属性”的缺点在于，同一个事件只能定义一个监听函数，也就是说，如果定义两次onclick属性，后一次定义会覆盖前一次。因此，也不推荐使用。
* 第三种EventTarget.addEventListener是推荐的指定监听函数的方法。它有如下优点：
  * 同一个事件可以添加多个监听函数。
  * 能够指定在哪个阶段（捕获阶段还是冒泡阶段）触发监听函数。
  * 除了 DOM 节点，其他对象（比如window、XMLHttpRequest等）也有这个接口，它等于是整个 JavaScript 统一的监听函数接口

## 事件传播  
一个事件发生后，会在子元素和父元素之间传播（propagation）。这种传播分成三个阶段。  
第一阶段：从window对象传导到目标节点（上层传到底层），称为“捕获阶段”（capture phase）。  
第二阶段：在目标节点上触发，称为“目标阶段”（target phase）。  
第三阶段：从目标节点传导回window对象（从底层传回上层），称为“冒泡阶段”（bubbling phase）。  
这种三阶段的传播模型，使得同一个事件会在多个节点上触发。
## 绑定监听函数
JavaScript 有三种方法，可以为事件绑定监听函数。  
* HTML的on-属性：只发生在冒泡
* 元素节点的事件属性：只发生在冒泡  
* addEventListener:false 则只发生在冒泡。
第三种EventTarget.addEventListener是推荐的指定监听函数的方法。它有如下优点：  
* 同一个事件可以添加多个监听函数。
* 能够指定在哪个阶段（捕获阶段还是冒泡阶段）触发监听函数。
* 除了 DOM 节点，其他对象（比如window、XMLHttpRequest等）也有这个接口，它等于是整个 JavaScript 统一的监听函数接口。
## this 指向
监听函数内部的this指向触发事件的那个元素节点。
## 事件传播  
最上层对象是window，接着依次是document，html（document.documentElement）和body（document.body）。  
也就是说，上例的事件传播顺序，在捕获阶段依次为window、document、html、body、div、p，在冒泡阶段依次为p、div、body、html、document、window。
## 事件的代理
由于事件会在冒泡阶段向上传播到父节点，因此可以把子节点的监听函数定义在父节点上，由父节点的监听函数统一处理多个子元素的事件。
这种方法叫做事件的代理（delegation）。  
如果希望事件到某个节点为止，不再传播，可以使用事件对象的stopPropagation方法。  
如果想要彻底取消该事件，不再触发后面所有click的监听函数，可以使用stopImmediatePropagation方法。
