### DOM基本操作
#### 对节点增删改查
- 节点nodeType，元素节点——1，文本节点——3,注释节点——8
- 节点的四个属性
```
  nodeName 元素的标签名，以大写形式表示，只读。
  nodeValue Text节点或Comment节点的文本内容，可读写
  nodeType 该节点的类型，只读
  attributes Element 节点的属性集合
```
##### 查看元素节点
* document 代表整个文档
* document.getElementById() 元素id在 IE8 一下的浏览器，不区分 id 大小写，而且也返回匹配的 name 属性的元素。
* documentsByTagName() 标签名
* getElementsByName() 只有部分标签 name 可生效（表单、表单元素、img、iframe）
* getElementsByClassName() ie8 和ie8 以下版本中没有，可以多个class一起
* .querySelector() css选择器，在ie7和ie7以下版本中没有
* .querySelectorAll() css选择器 在ie7和ie7以下版本中没有
##### 遍历节点树
+ parentNode -> 父节点（最顶层的parentNode为#document）
+ childNodes -> 子节点们
+ firstChild -> 第一个子节点
+ lastChild  -> 最后一个子节点
+ nextSibling -> 后一个兄弟节点 previousSibling -> 前一个兄弟节点
##### 遍历元素节点树
- parentElement  -> 返回当前元素的父元素节点（IE不兼容）
- child  ->   只返回当前元素的元素子节点
- node.childElementCount === node.children.length 当前元素节点的子元素节点个数（IE不兼容）
- firstElementChild  -> 返回的是第一个元素节点（IE不兼容）
- lastElementChild  -> 返回的是最后一个元素接节点（IE不兼容）
- nextElementSibling/previousElementSibling  -> 返回后一个/前一个兄弟元素节点（IE不兼容）
