## 概述
事件发生以后，会产生一个事件对象，作为参数传给监听函数。浏览器原生提供一个Event对象，所有的事件都是这个对象的实例，或者说继承了Event.prototype对象。  
Event对象本身就是一个构造函数，可以用来生成新的实例。event = new Event(type, options);  
* Event构造函数接受两个参数。第一个参数type是字符串，表示事件的名称；第二个参数options是一个对象，表示事件对象的配置。该对象主要有下面两个属性。
  * bubbles：布尔值，可选，默认为false，表示事件对象是否冒泡。
  * cancelable：布尔值，可选，默认为false，表示事件是否可以被取消，即能否用Event.preventDefault()取消这个事件。一旦事件被取消，就好像从来没有发生过，不会触发浏览器对该事件的默认行为。

## 属性
### Event.bubbles，Event.eventPhase 
Event.bubbles属性返回一个布尔值，表示当前事件是否会冒泡。该属性为只读属性，一般用来了解 Event 实例是否可以冒泡。前面说过，除非显式声明，Event构造函数生成的事件，默认是不冒泡的。  
Event.eventPhase属性返回一个整数常量，表示事件目前所处的阶段。该属性只读。  
* Event.eventPhase的返回值有四种可能。
  * 0，事件目前没有发生。
  * 1，事件目前处于捕获阶段，即处于从祖先节点向目标节点的传播过程中。
  * 2，事件到达目标节点，即Event.target属性指向的那个节点。
  * 3，事件处于冒泡阶段，即处于从目标节点向祖先节点的反向传播过程中。
  
### Event.cancelable，Event.cancelBubble，event.defaultPrevented
Event.cancelable属性返回一个布尔值，表示事件是否可以取消。该属性为只读属性，一般用来了解 Event 实例的特性。大多数浏览器的原生事件是可以取消的。比如，取消click事件，点击链接将无效。但是除非显式声明，Event构造函数生成的事件，默认是不可以取消的  
当Event.cancelable属性为true时，调用Event.preventDefault()就可以取消这个事件，阻止浏览器对该事件的默认行为。  
如果事件不能取消，调用Event.preventDefault()会没有任何效果。所以使用这个方法之前，最好用Event.cancelable属性判断一下是否可以取消。  
Event.cancelBubble属性是一个布尔值，如果设为true，相当于执行Event.stopPropagation()，可以阻止事件的传播。  
Event.defaultPrevented属性返回一个布尔值，表示该事件是否调用过Event.preventDefault方法。该属性只读。  
### Event.currentTarget，Event.target
事件发生以后，会经过捕获和冒泡两个阶段，依次通过多个 DOM 节点。因此，任意时点都有两个与事件相关的节点，一个是事件的原始触发节点（Event.target），另一个是事件当前正在通过的节点（Event.currentTarget）。前者通常是后者的后代节点。
* Event.currentTarget属性返回事件当前所在的节点，即事件当前正在通过的节点，也就是当前正在执行的监听函数所在的那个节点。随着事件的传播，这个属性的值会变。
* Event.target属性返回原始触发事件的那个节点，即事件最初发生的节点。这个属性不会随着事件的传播而改变。
* 事件传播过程中，不同节点的监听函数内部的Event.target与Event.currentTarget属性的值是不一样的。
### Event.type
Event.type属性返回一个字符串，表示事件类型。事件的类型是在生成事件的时候指定的。该属性只读.
### Event.timeStamp
Event.timeStamp属性返回一个毫秒时间戳，表示事件发生的时间。它是相对于网页加载成功开始计算的。
### Event.isTrusted
Event.isTrusted属性返回一个布尔值，表示该事件是否由真实的用户行为产生。比如，用户点击链接会产生一个click事件，该事件是用户产生的；Event构造函数生成的事件，则是脚本产生的  
### Event.detail
Event.detail属性只有浏览器的 UI （用户界面）事件才具有。该属性返回一个数值，表示事件的某种信息。具体含义与事件类型相关。比如，对于click和dblclick事件，Event.detail是鼠标按下的次数（1表示单击，2表示双击，3表示三击）；对于鼠标滚轮事件，Event.detail是滚轮正向滚动的距离，负值就是负向滚动的距离，返回值总是3的倍数。  

## 方法
### Event.preventDefault()
### Event.stopPropagation()
### Event.stopImmediatePropagation()
### Event.composedPath()

