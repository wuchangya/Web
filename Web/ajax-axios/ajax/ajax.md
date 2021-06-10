# AJAX简介

AJAX全称为 Asynchronous JavaScript And XML，就是异步的JS和XML.

通过AJAX可以在浏览器中向服务器发送异步请求，最大的优势：**==无刷新获取数据。==**

AJAX不是新的编程语言，而是一种将现有的标准组合在一起使用的新方式。





# XML简介

XML可扩展标记语言。

XMLT被设计用来传输和存储数据。

XML和HTML类似，不同的是**==HTML中都是预定义标签==**，**==而XML中没有预定义标签==**，全都是自定义标签，用来表示一些数据。

![image-20210428114102151](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210428114102151.png)

# AJAX优缺点

**==AJAX的优点==**

1)可以无需刷新页面而与服务器端进行通信。

2)允许你根据用户事件来更新部分页面内容。

**==AJAX的缺点==**

1)没有浏览历史，不能回退

2)存在跨域问题（同源

3)SEO不友好

SEO的英文全称是Search Engine Optimization,意思是搜索引擎优化

也就是使用AJAX异步请求到的数据不能通过爬虫来搜索到

源代码第一次请求服务器的时候，源代码的结果里面是没有AJAX请求到的信息的，这部分是动态添加到里面的



# AJAX-HTTP协议请求报文与响应文本结构

HTTP协议「超文本传输协议』,协议详细规定了浏览器和万维网服务器之间互相通信的规则。



## 请求报文

这里重点讲请求报文的格式与参数

一个请求报文包括四部分：**==行、头、空行、体==**

**==行：==**

包括三部分：

​	①**请求类型**：GET、POST、HEAD、PUT、DELETE、OPTIONS、TRACE、CONNECT，get和post见得居多

​	②**url**

​	③**HTTP协议的版本**

![image-20210429200738953](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210429200738953.png)

**==头：==**

头部有一些属性配置，，例如

Host:主机

Cookie:cookie数据

Content-type:内容类型 ，用来规定下面**==请求体内容的格式==**

![image-20210428121555340](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210428121555340.png)

**==空行：==**必须要有一个空行

**==体：==**

可以有内容也可以没有

如果是**get请求**，**请求体可以没有内容**，如果是**post请求**，**请求体可以不为空**

请求体的格式可以是**==查询体（urlencoded）==**，也可以是**==json字符串==**

==**username=tom&pwd=123**==

==**{"username": "tom", "pwd": 123}**==





简单的示例：

![image-20210428160940793](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210428160940793.png)

## 响应报文：

一个响应报文同样包括四部分：**==行、头、空行、体==**

**==行：==**

包括三部分：

①协议版本

②响应状态码

③响应状态字符串

![image-20210429195710504](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210429195710504.png)

==**头：**==

跟请求报文一样有一些属性，对响应报文做一些描述

Content-type:**==内容类型==**，规定响应体内容的格式 

Set-Cookie:**==服务器携带cookie到客户端==**，通过响应头中的Set-Cookie来传参

![image-20210428163123363](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210428163123363.png)

==**空行：**== 也是必须得有

==**体：**== 响应体就是我们请求后的主要的返回结果

html 文本/json 文本/js/css/图片..各类内容

简单的示例

![image-20210428163306060](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210428163306060.png)



# 前后端API分类

API 的分类 

REST API: restful 

(1) 发送请求进行 CRUD （增删改查）哪个操作**==由请求方式来决定==**

(2) **==同一个请求路径可以进行多个操作==**

(3) 请求方式会用到 GET/POST/PUT/DELETE 



 非 REST API: restless 

(1) **==请求方式不决定请求的 CRUD 操作==**

(2) **==一个请求路径只对应一个操作==** 

(3) **==一般只有 GET/POST==**



# Chrome浏览器网络控制台查看通信报文

在当前的页面打开控制台，打开network，刷新页面后，会看到下面的一些请求信息

注意这个例子是一个**==get请求==**

![image-20210428163540504](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210428163540504.png)

点击**==左边第一个请求内容==**，**==headers==**代表的是头部信息

![image-20210428163727422](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210428163727422.png)

打开**==请求头==**

![image-20210428163950202](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210428163950202.png)

点击**==view source==**，里面有**==请求行==**和==**请求头**==，这个例子只get请求，所以没有请求体

![image-20210428164049446](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210428164049446.png)



点击**==Query String Parameters==**（查询字符串参数），这里面是对url内的参数做了一个解析，做了一个格式化

![image-20210428164503817](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210428164503817.png)

打开**==响应头==**，里面都是响应头信息

![image-20210428164828750](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210428164828750.png)

点击**==view source==**查看原始的响应报文，里面有**==响应行和响应头==**，响应体在控制台上面导航条的第三个：response

![image-20210428165018493](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210428165018493.png)

打开**==response==**

![image-20210428165140919](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210428165140919.png)

打开**==preview==**，这是对响应体内容解析之后的一个预览

![image-20210428165401507](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210428165401507.png)



下面举一个post请求，利用一个网站的登录过程

打开控制台的network，打开左边第一个请求的内容

在header下的**==from data==**中，就是**==请求体==**内容

再点击**==view source==**，就能看到请求体的原始内容，里面有登录的信息（邮箱，密码等等）

![image-20210428165729089](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210428165729089.png)



# express框架的基本使用

express简单地使用演示

使用**==npm init --yes==**初始化

**==npm i express==**来安装express框架

然后编写如下的js文件

![image-20210428191117310](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210428191117310.png)

在终端执行**==node express-test.js==**,结果如下

![image-20210428191315455](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210428191315455.png)

打开浏览器，输入IP地址==**http://127.0.0.1:8000/ **==，打开

![image-20210428191539866](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210428191539866.png)

# AJAX请求基本操作

编写一个简单地页面，实现点击按钮就向刚才创建的网址发送请求

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
	</head>
	<body>
		<button>点击发送请求</button>
		<div id="result"> </div>
		
		<script>
			// 获取button元素
			const btn = document.getElementsByTagName('button')[0]
			// 绑定事件
			btn.onclick = function(){
				// console.log('test');
				// 进行AJAX操作
				//1. 创建对象
				const xhr = new XMLHttpRequest();
				//2. 初始化设置请求方法和url
				xhr.open('GET', 'http://127.0.0.1:8848/server');
				//3. 发送
				xhr.send();
				//4. 事件绑定 作用是处理服务端返回的结果
				/* readystate是xhr对象中的属性，表示状态0、1、2、3
				0表示未初始化
				1表示open方法已经调用完毕
				2表示send方法已经调用完毕
				3表示服务端返回了部分的结果
				4表示服务端返回了所有的结果
				 */
				xhr.onreadystatechange = function(){
					// 应当在4阶段做服务器返回结果的处理
					// 判断
					if(xhr.readyState === 4){
						// 判断响应的状态码200 404 403 500
						// 响应状态码中2xx开头的都是响应成功的
						/* if(xhr.status === 200){
							
						} */
						if(xhr.status >= 200 && xhr.status < 300){
							// 处理结果
							// 响应行
							console.log(xhr.status);//状态码
							console.log(xhr.statusText);//状态字符串
							console.log(xhr);//状态字符串
							console.log(xhr.getAllResponseHeaders());//所有响应头
							console.log(xhr.response);//响应体
							
						}
					}
				
				}
			}
		</script>
	</body>
	<style>
		#result{
			width: 200px;
			height:100px;
			border: solid 1px #90b;
		}
	</style>
</html>
```

![image-20210428205735275](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210428205735275.png)

点击过后将相关信息进行console.log打印出来



# nodemon

nodemon是一种工具，可以自动检测到目录中的文件更改时通过重新启动应用程序来调试基于node.js的应用程序。

使用了nodemon之后，每次服务端修改了代码，不用再重启，服务端自动就会刷新



# AJAX中IE缓存问题

ie浏览器会对ajax请求结果做一个缓存，下一次再次发送请求的时候，使用的是本地的缓存，并不是服务器的返回的最新数据，**==对于一些时效性比较强的场景，ajax的缓存会影响我们的结果==**，不能够正常去显示

我们上面引入了nodemon可以实时修改服务端的代码，适时进行更新，但是ie浏览器不会进行更新，因为有缓存


​            可以在客户端每次进行请求的时候，在请求的url后面加上一个 Date.now()，Date.now()获取当前的时间戳，加上这个时间戳之后，浏览器就认为每次都是不同的请求，就不会使用缓存了

**==xhr.open('GET', 'http://localhost:8000/ie?t='+Date.now())==**



# AJAX重复请求重复发送的问题

有时候用户会频繁的点击页面，发送相同的请求

服务端压力会很大，在服务端有一些延迟时，会同时进行好几个ajax请求

这个时候服务端可以检测之前有没有发送过相同的请求

如果有，就把之前的取消掉，新建一个，这样客户端向服务器中发送的请求只有一个，服务器的压力就会小一些



**==其他详情见代码==**

# axios

axios是一个ajax请求的一个工具包

**==其他详情见代码==**

# 跨域

## 同源策略

同源策略是网景公司提出的，浏览器的一种安全策略

同源的要求：**==当前网页的url==**和**==ajax请求的目标资源网页的url==**，**==协议、域名、端口==**必须完全相同

ajax就默认遵守同源策略，不满足同源策略就没办法发送ajax

违背同源策略就是**==跨域==**



## 如何解决跨域

### JSONP

 JSONP是什么

JSONP( JSON with Padding),是一个**==非官方的跨域解决方案==**，纯粹凭借程序员的聪明才智开发出来，**==只支持get请求。==**



 JSONP怎么工作的？

**==在网页有一些标签天生具有跨域能力==**，比如： img、link、iframe、script，这些标签可以使用href、src这些属性，这些属性的值可以是任意的网址，不存在跨域问题，只用ajax请求才会存在跨域问题

JSONP就是利用 **==script标签==**的跨域能力来发送请求的。



### CORS

CORS是什么？

CORS( Cross-Origin Resource Sharing),**==跨域资源共享==**。

**==CORS是官方的跨域解决方案==**，它的特点是**==不需要在客户端做任何特殊的操作==**，**==完全在服务器中进行处理==**，支持**==get==**和**==post==**等等请求。

跨域资源共享标准新增了一组HTTP首部字段，允许服务器声明哪些源站通过浏览器有权限访问哪些源



CORS怎么工作的？

CORS是通过设置一个**==响应头==**来告诉浏览器，该请求允许跨域，浏览器收到该响应以后就会对响应放行。

可以指定具体的网页跨域，也可以用**==*==**来允许所有的网站跨域



在服务器的路由规则中添加一个**==响应头==**

**==response.setHeader('Access-Control-Allow-Origin', '*')==**



一般在遇到跨域的问题时，都会使用以下三个响应头设置，分别代表**==任意源页面==**、**==任意头部信息==**、**==任意请求方法==**

==**response.setHeader('Access-Control-Allow-Origin', '*')**==

==**response.setHeader('Access-Control-Allow-Headers', '*')**==

==**response.setHeader('Access-Control-Allow-Methods', '*')**==











































































































































