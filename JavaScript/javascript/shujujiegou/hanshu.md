## 三种声明函数方式
* 函数声明
* 函数表达式
采用函数表达式声明函数时，function命令后面不带有函数名。如果加上函数名，该函数名只在函数体内部有效，在函数体外部无效。  
这种写法的用处有两个，一是可以在函数体内部调用自身，二是方便除错（除错工具显示函数调用栈时，将显示函数名，而不再显示这里是一个匿名函数）
* Function 构造函数
你可以传递任意数量的参数给Function构造函数，只有最后一个参数会被当做函数体，如果只有一个参数，该参数就是函数体。  
## return 
JavaScript 引擎遇到return语句，就直接返回return后面的那个表达式的值，后面即使还有语句，也不会得到执行。  
也就是说，return语句所带的那个表达式，就是函数的返回值。return语句不是必需的，如果没有的话，该函数就不返回任何值，或者说返回undefined。  
## 声明
上面代码第二行，调用f的时候，f只是被声明了，还没有被赋值，等于undefined，所以会报错。  
因此，如果同时采用function命令和赋值语句声明同一个函数，最后总是采用赋值语句的定义。
## 函数属性和方法
### name属性
函数的name属性返回函数的名字
### length属性
函数的length属性返回函数预期传入的参数个数，即函数定义之中的参数个数。  
length属性提供了一种机制，判断定义时和调用时参数的差异，以便实现面向对象编程的“方法重载”（overload）。  
运行时无论提供多少个参数（或者不提供参数），JavaScript 都不会报错。  
省略的参数的值就变为undefined。需要注意的是，函数的length属性与实际传入的参数个数无关，只反映函数预期传入的参数个数。
### toString属性
函数的toString方法返回一个字符串，内容是函数的源码。  
对于那些原生的函数，toString()方法返回function (){[native code]}。函数内部的注释也可以返回。
## 函数作用域
对于var命令来说，局部变量只能在函数内部声明，在其他区块中声明，一律都是全局变量。  
`总之，函数执行时所在的作用域，是定义时的作用域，而不是调用时所在的作用域。`
## 参数
如果有同名的参数，则取最后出现的那个值。
## arguments 对象 
arguments对象包含了函数运行时的所有参数，arguments[0]就是第一个参数，arguments[1]就是第二个参数，以此类推。  
这个对象只有在函数体内部，才可以使用。  
严格模式下，arguments对象与函数参数不具有联动关系。也就是说，修改arguments对象不会影响到实际的函数参数。  
arguments很像数组，但它是一个对象。数组专有的方法（比如slice和forEach），不能在arguments对象上直接使用。  
让arguments对象使用数组方法，真正的解决方法是将arguments转为真正的数组。下面是两种常用的转换方法：slice方法和逐一填入新数组。  
arguments对象带有一个callee属性，返回它所对应的原函数。  
可以通过arguments.callee，达到调用函数自身的目的。这个属性在严格模式里面是禁用的，因此不建议使用。
## 闭包
闭包就是函数，即能够读取其他函数内部变量的函数。  
闭包的最大用处有两个，一个是可以读取函数内部的变量，另一个就是让这些变量始终保持在内存中，即闭包可以使得它诞生环境一直存在。  
外层函数每次运行，都会生成一个新的闭包，而这个闭包又会保留外层函数的内部变量，所以内存消耗很大。因此不能滥用闭包，否则会造成网页的性能问题。  
## 立即调用的函数表达式（IIFE）
(function(){ /* code */ }());
// 或者
(function(){ /* code */ })();  
通常情况下，只对匿名函数使用这种“立即执行的函数表达式”。  
它的目的有两个：一是不必为函数命名，避免了污染全局变量；二是 IIFE 内部形成了一个单独的作用域，可以封装一些外部无法读取的私有变量。  
## eval命令
eval命令接受一个字符串作为参数，并将这个字符串当作语句执行。  
如果参数字符串无法当作语句运行，那么就会报错。如果eval的参数不是字符串，那么会原样返回。  
eval没有自己的作用域，都在当前作用域内执行，因此可能会修改当前作用域的变量的值，造成安全问题。  
为了防止这种风险，JavaScript 规定，如果使用严格模式，eval内部声明的变量，不会影响到外部作用域。  
不过，即使在严格模式下，eval依然可以读写当前作用域的变量  
eval的本质是在当前作用域之中，注入代码。由于安全风险和不利于 JavaScript 引擎优化执行速度，所以一般不推荐使用。  
通常情况下，eval最常见的场合是解析 JSON 数据的字符串，不过正确的做法应该是使用原生的JSON.parse方法。  
### eval别名调用
为了保证eval的别名不影响代码优化，JavaScript 的标准规定，凡是使用别名执行eval，eval内部一律是全局作用域。