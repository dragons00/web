节点都是单个对象，有时需要一种数据结构，能够容纳多个节点。DOM 提供两种节点集合，用于容纳多个节点：NodeList和HTMLCollection。  
这两种集合都属于接口规范。许多 DOM 属性和方法，返回的结果是NodeList实例或HTMLCollection实例。  
主要区别是，NodeList可以包含各种类型的节点，HTMLCollection只能包含 HTML 元素节点。  
## NodeList 接口
NodeList实例是一个类似数组的对象，它的成员是节点对象。通过以下方法可以得到NodeList实例。
* Node.childNodes
* document.querySelectorAll()等节点搜索方法  
NodeList实例很像数组，可以使用length属性和forEach方法。但是，它不是数组，不能使用pop或push之类数组特有的方法。  
注意，NodeList 实例可能是动态集合，也可能是静态集合。所谓动态集合就是一个活的集合，DOM 删除或新增一个相关节点，都会立刻反映在 NodeList 实例。目前，只有Node.childNodes返回的是一个动态集合，其他的 NodeList 都是静态集合。  
### NodeList.prototype.length
length属性返回 NodeList 实例包含的节点数量。
### NodeList.prototype.forEach()
forEach方法用于遍历 NodeList 的所有成员。它接受一个回调函数作为参数，每一轮遍历就执行一次这个回调函数，用法与数组实例的forEach方法完全一致。
### NodeList.prototype.item()
item方法接受一个整数值作为参数，表示成员的位置，返回该位置上的成员。
### NodeList.prototype.keys()，NodeList.prototype.values()，NodeList.prototype.entries() 
这三个方法都返回一个 ES6 的遍历器对象，可以通过for...of循环遍历获取每一个成员的信息。区别在于，keys()返回键名的遍历器，values()返回键值的遍历器，entries()返回的遍历器同时包含键名和键值的信息。
## HTMLCollection 接口
HTMLCollection是一个节点对象的集合，只能包含元素节点（element），不能包含其他类型的节点。它的返回值是一个类似数组的对象，但是与NodeList接口不同，HTMLCollection没有forEach方法，只能使用for循环遍历。返回HTMLCollection实例的，主要是一些Document对象的集合属性，比如document.links、document.forms、document.images等。
### HTMLCollection.prototype.length
### HTMLCollection.prototype.item()
### HTMLCollection.prototype.namedItem() 

