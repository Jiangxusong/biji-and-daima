<center>NOde.JS   学习笔记</center>
**node.js** 不是一门语言  不是库  也不是框架   ``node.js 是一个 JavaScritp 运行是环境  可以解析和执行 JavaScript 代码  可以完全脱离浏览器来运行 一切归功于 Nodejs` 

### 模块系统
Node.js 中的 JavaScript     没有 BOM和 DOM
在  Node  中没有全局作用域的概念
在 Node   中只能通过   require  方法来加载执行多个   	JavaScript   脚本文件
require  加载只能是执行其中的 代码   文件与文件之间由于是模块作用域   所以不会有污染的问题
   -  模块完全是封闭的
   -  外部无法访问内部
   -  内部也无法访问外部
 模块作用域固然带来了一些好处   可以加载执行多个文件   可以完全避免变量命名冲突污染的问题
但是某些情况下  模块与模块是需要进行通信的
在每个模块中  都提供了一个对象       `exports`
该对象默认是一个空对象
你需要做的就是把需要被外部访问使用的成员手动的挂载到  `exports`  接口对象中
然后谁来  `require` 这个模块   谁就可以得到模块内部的   `exports` 接口对象

###  核心模块
核心模块是由  Node   提供的 一个个的具名的模块   它们都有自己特殊的名称标识   例如
-  fs  文件操作模块
-  http 网络服务构建模块
-  os    操作系统信息模块
-  path     路径处理模块
所以核心模块在使用的时候都必须手动的先使用  `require`   方法来加载  然后才可以使用
-`var   fs  =  require ( 'fs' )`

-http
+ require  
+ 端口号
       *  ip  地址定位计算机
       *  端口号定位具体的应用程序
+ Content-Type
       * 服务器最好把每次响应的数据是什么内容类型都告诉客户端  而且要正确的告诉
+  通过网络发送文件
    * 发送的并不是文件   本质上来讲发送的是文件内容
    * 当浏览器收到服务器响应内容之后  就会根据你的  Content-Type  进行对应的解析处理
    * 不同的资源对应的 Content -Type  是不一样  具体参考: https://tool.oschina.net/commons
    * 对于文本类型的数据 最好都加上编码  目的是为了防止中文乱码问题

