# 数据结构
## null,undefined区别
区别是这样的：null是一个表示“空”的对象，转为数值时为0；undefined是一个表示"此处无定义"的原始值，转为数值时为NaN。  
`1* 变量声明了，但没有赋值
var i;
i // undefined
2* 调用函数时，应该提供的参数没有提供，该参数等于 undefined
function f(x) {
  return x;
}
f() // undefined
3* 对象没有赋值的属性
var  o = new Object();
o.p // undefined
4* 函数没有返回值时，默认返回 undefined`

## 布尔值
如果 JavaScript 预期某个位置应该是布尔值，会将该位置上现有的值自动转为布尔值。转换规则是除了下面六个值被转为false，其他值都视为true。
undefined,null,false,0,NaN,""或''（空字符串）,注意，空数组（[]）和空对象（{}）对应的布尔值，都是true。
 
