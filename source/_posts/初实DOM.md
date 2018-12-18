---
title: 初实DOM
date: 2018-12-18 21:49:18
tags:
---
什么是DOM？

文档对象模型 (DOM) 是HTML和XML文档的编程接口。DOM 将文档解析为一个由节点和对象（包含属性和方法的对象）组成的结构集合。Node是一个接口，许多DOM类型从这个接口继承，并允许类似地处理（或测试）这些各种类型。简言之，它会将web页面和脚本或程序语言连接起来。

以下接口都从Node继承其方法和属性：

Document, Element, CharacterData (which Text, Comment, and CDATASection inherit), ProcessingInstruction, DocumentFragment, DocumentType, Notation, Entity, EntityReference

nodeType 属性可用来区分不同类型的节点，比如 元素,文本和 注释。这些Node类型中，我们最常用的就是element，text，attribute，comment，document，document_fragment这几种类型。

常用节点类型
Node.ELEMENT_NODE 1 一个元素节点，例如<p>和<div>。

Node.TEXT_NODE 3 Element或者Attr属性中实际文字Node.PROCESSING_INSTRUCTION_NODE 7 一个用于XML文档ProcessingInstruction，例如 <?xml-stylesheet ... ?>声明。

Node.COMMENT_NODE 8 一个Comment节点。（注释，注解）

Node.DOCUMENT_NODE 9 一个Document节点。（文档）

Node.DOCUMENT_TYPE_NODE 10 描述文档类型的DocumentType节点。例如 <!DOCTYPE html> 就是用于 HTML5 的。

Node.DOCUMENT_FRAGMENT_NODE 11 一个DocumentFragment节点



参考地址：Node.nodeType

例子：检查 document 下第一个节点是不是注释，如果不是，则会提醒。

var node = document.documentElement.firstChild;
if (node.nodeType != Node.COMMENT_NODE)
  console.log("你应该认真编写代码注释！");


nodeType 定义和用法
nodeType 属性返回以数字值返回指定节点的节点类型。

如果节点是元素节点，则 nodeType 属性将返回 1。

如果节点是属性节点，则 nodeType 属性将返回 2。

怎么使用DOM?

API = DOM + JS (脚本语言) 下面是在web和XML页面脚本中使用DOM时，一些常用的API简要列表。

document.getElementById(id) 可返回对拥有指定 ID 的第一个对象的引用。
document.getElementsByTagName(name) 可返回带有指定标签名的对象的集合
document.createElement(name) 可创建元素节点。
parentNode.appendChild(node) 将一个节点添加到指定父节点的子节点列表末尾。
element.innerHTML 设置或获取HTML语法表示的元素的后代。
element.style.left
left 属性设置定位元素左外边距边界与其包含块左边界之间的偏移。Object.style.left=auto|%|length

element.setAttribute() 添加指定的属性，并为其赋指定的值。
例：document.getElementsByTagName("INPUT")[0].setAttribute("type","button");

element.getAttribute() 返回指定属性名的属性值。
element.addEventListener()
将指定的监听器注册到EventTarget 上，当该对象触发指定的事件时，指定的回调函数就会被执行。

window.contentcontent返回一个浏览器中的当前页面的Window对象的引用
window.onload 会在页面或图像加载完成后立即发生
window.dump()
例：window.dump(message); dump(message);

message 是要打印的字符串

window.scrollTo() 把内容滚动到指定的坐标。
Javascript操作DOM常用API总结
原文地址链接：https://zhuanlan.zhihu.com/p/52704918