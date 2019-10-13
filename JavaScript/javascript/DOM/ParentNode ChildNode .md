节点对象除了继承 Node 接口以外，还会继承其他接口。  
* ParentNode接口表示当前节点是一个父节点，提供一些处理子节点的方法。
* ChildNode接口表示当前节点是一个子节点，提供一些相关方法。   
## ParentNode 接口 
如果当前节点是父节点，就会继承ParentNode接口。由于只有元素节点（element）、文档节点（document）和文档片段节点（documentFragment）拥有子节点，因此只有这三类节点会继承ParentNode接口。
* ParentNode.children  
children属性返回一个HTMLCollection实例，成员是当前节点的所有元素子节点。该属性只读。
* ParentNode.firstElementChild
* ParentNode.lastElementChild
* ParentNode.childElementCount
* ParentNode.append()，ParentNode.prepend()
## ChildNode 接口
* ChildNode.remove()
* ChildNode.before()，ChildNode.after()
* ChildNode.replaceWith()
