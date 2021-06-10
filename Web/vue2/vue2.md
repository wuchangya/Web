# vue续

## vuecli3创建项目和目录结构

![1617632101555](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617632101555.png)

![1617632198555](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617632198555.png)

vue-cli3是基于 **==webpack4==**打造，vue-cli2还是 **webapck3**

vue-cli3的设计原则是"0配置”，**==移除的配置文件根目录下的build和 config等目录==**，开发者从目录里面看不到相关的配置文件

vue-cli3**==提供了 vue ui 命令，提供了可视化配置，更加人性化==**

**==移除了 static文件夹，新增了 public文件夹（此文件夹功能和static一样，同样是静态文件不作处理直接放到dist文件夹中）==**，并且 **==index. html移动到 public中==**



创建vuecli3命令行：==**vue create 项目名称**== 



![1617669159518](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617669159518.png)

保存自己的配置作为预设后，如果想删除，在c盘users中administrator中.vuerc文件夹中删除

(很多文件名结尾都是rc：run command里面都是和终端命令相关的)

![1617673146874](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617673146874.png)



打开main.js文件

![1617672215724](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617672215724.png)

vue.config.productionTip = false，意思是项目构建过程中，会给出构建过程中的一些提示信息，提示构建了什么东西，开发阶段一般是false

跟cli2中不同的是，vue实例中并没有用el来挂载相应的标签id值，而是使用了$mount来挂载，实现的功能是一样的，通过el来挂载源码和mount是一样的

## vuecli3配置文件的查看和修改

修改配置有三种方案

**<font color='red'>①</font>**

启动vue ui服务器（用edge打开，谷歌打开报错）

在任何一个目录下面的命令行呼入输入：**==vue ui==**

不用指定目录，因为启动的是一个服务器，并不是专门定位于哪一个目录下面的文件

![1617693579289](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617693579289.png)

**<font color='red'>②</font>**

之前说vuecli3设计原则是0配置，根目录下的build、config文件夹被移除，但是可以在项目的**==node_modules->@vue->cli-service==**里面有一些具体的配置

![1617693227774](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617693227774.png)

**<font color='red'>③</font>**

如果真的想修改vue的具体配置，可以自己添加一个文件放在项目的根目录下面

文件的名字是**==固定的==**：**==vue.config.js==**，在文件中，将配置用**==module.exports导出==**的方法进行导出

到时候vue项目会自动在文件中找名为vue.config.js的配置文件，导入到上面提到的cli-service文件夹中的相关配置文件中，**==进行合并==**

![1617694038878](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617694038878.png)



## 路由

### 路由简介

![1617699234098](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617699234098.png)

### 前端渲染后端渲染/前端路由后端路由

#### 后端路由阶段

早期的网站开发整个HTML页面是由**==服务器来渲染==**的

服务器**==通过jsp或者Java等等直接生产渲染好对应的HTML页面==**，返回给客户端进行展示

但是，一个网站，这么多页面服务器如何处理呢？

一个页面有自己对应的网址，也就是**==URL==**.

URL请求会发送到服务器，服务器会通过**==正则==**对该URL进行匹配，并且最后交给一个 **==Controller==**进行处理

Controller进行各种处理最终生成HTML或者数据，返回给前端，这就完成了一个IO操作

网页和url这种映射关系由后端处理和保存，这就是**==后端路由：==**

​	==**当我们页面中需要请求不同的路径内容时，交给服务器来进行处理，服务器渲染好整个页面，并且将页面返回给客户端**==

​	==**这种情况下渲染好的页面，不需要单独加载任何的js和css可以直接交给浏览器展示，这样也有利于SEO的优化**==

**==后端路由的缺点==**

种情况是整个页面的模块由后端人员来编写和维护的

另一种情况是前端开发人员如果要开发页面，需要通过PHP和Java等语言来编写页面代码

而且通常情況下HTML代码和数据以及对应的逻辑会混在一起，编写和维护都是非常糟糕的事情。



#### 前后端分离阶段



随着**==ajax==**的出现，有了前后端分离的开发模式

后端只提供API来返回数据，**==前端通过ajax获取数据==**，并且可以通过 Javascript将数据渲染到页面中

这样做最大的优点就是前后端责任的清晰，**后端专注于数据上**，**前端专注于交互和可视化上**

**并且当移动端(iOS/ Android)出现后，后端不需要进行任何处理依然使用之前的一套API即可。**

目前很多的网站依然采用这种模式开发。

![1617702117764](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617702117764.png)



#### 前端路由阶段

spa：单页面富应用，整个网页只有一个页面

其实SPA最主要的特点就是**==在前后端分离的基础上加了一层前端路由==**

也就是**==前端来维护一套路由规则==**

![1617702901022](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617702901022.png)

前端路由阶段和前后端分离阶段不同点在于

前端同样是从静态资源服务器上请求html、css、js，不同的是，**==前端路由阶段html+css+js只有一套==**

浏览器一次性从服务器上下载下来所有的资源，浏览器再次发起当前网站的不同url时，**==就不会向服务器请求数据了==**，而是通过**==前端路由==**来调用不同的页面（在vue中就是一个个vue组件）

**<font color='red'>前端路由的核心</font>**是：==**改变url，页面不会进行整体的刷新，不会重新向服务器发出请求**==



### url的hash和html5的history

#### url的hash

以vue的主页为例，在控制台通过输入：location.hash = 'aaa'将网页的url进行修改，在URL后面加上一条记录，但是网页并不会进行刷新

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617705034050.png" alt="1617705034050" style="zoom:80%;" />

通过查看network中加载项，发现并没有进行新的内容请求，即网页并没有刷新





#### html5的history

pushState()、replaceState()、go()、forward()这四个方法个都属于js中的BOM

后面三个在之前讲过

> pushState()与replaceState()对比详解：https://blog.csdn.net/yexudengzhidao/article/details/101448168



**==history.pushState()方法==**

用于修改url，同样是在URL后面加上一条记录

该方法接受三个参数，依次为：

​	state：一个与添加的记录相关联的**==状态对象==**，主要用于**==popstate事件==**。该事件触发时，该对象会传入回调函数。也就是说，浏览器会将这个对象序列化以后保留在本地，重新载入这个页面的时候，可以拿到这个对象。如果不需要这个对象，此处可以填null。

​	title：新页面的标题。但是，现在所有浏览器都忽视这个参数，所以这里可以填空字符串。

​	url：新的网址，必须与当前页面**==处在同一个域==**。浏览器的地址栏将显示这个网址。

![1617710865908](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617710865908.png)

pushState()方法的原理是每修改一次url就将当前的url参数进行入栈，多次调用就多次入栈

使用**==history.back()方法==**会将浏览器的页面进行**回退**，同时进行**==出栈操作==**，url会按照pushState方法入栈的url参数，先进后出





**==history.replaceState()方法==**

History.replaceState()方法用来修改 History 对象的当前记录，而**==不是对url参数值进行入栈操作==**，是**==直接将url进行替换==**，并且**==不能回退==**

其他都与pushState()方法一模一样。



**==go()方法==**，可以用来跳转到指定的页面

它需要一个**整数**作为**参数**：

​	**1**：表示向前跳转一个页面相当于 forward()

​	**2**：表示向前跳转两个页面

​	**-1**：表示向后跳转一个页面

​	**-2**：表示向后跳转两个页面



**==forward()方法==**

可以跳转下一个页面，作用和浏览器的前进按钮一样



#### popstate

每当活动历史记录条目在同一文档的两个历史记录条目之间更改时，就会在窗口上调度 `popstate` 事件。如果要激活的历史记录条目是通过调用 `history.pushState()` 创建的，或者受到了调用 `history.replaceState()` 的影响，**==则 `popstate` 事件的 `state` 属性包含历史记录条目的 `state` 对象的副本。==**

> **<font color='red'>注意</font>**：仅调用 **==history.pushState()==**或 **==history.replaceState()==** **不会触发 popstate 事件**。**==仅通过执行浏览器操作（例如单击后退按钮（或在 JavaScript 中调用 history.back()）才能触发 popstate 事件。==**并且仅当用户在同一文档的两个历史记录条目之间导航时才触发该事件。

> **注意**：浏览器过去在页面加载时处理 `popstate` 事件的方式不同，但是现在它们的行为相同。 Firefox 从不在页面加载时发出 `popstate` 事件。而 Chrome 一直到 34 版，Safari 直到 10.0 版之前都会。

## 语法

```javascript
window.onpopstate = funcRef;
```

- `funcRef` 是一个处理函数。





<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617711585426.png" alt="1617711585426" style="zoom: 67%;" />



## ==vue-router的安装与配置==

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617711668842.png" alt="1617711668842" style="zoom:67%;" />



<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617711721839.png" alt="1617711721839" style="zoom:67%;" />



步骤一：安装vue- router

​	命令行：**==npm install vue-router--save==**

步骤二：在模块化工程中使用它(因为是一个插件，所以可以**==通过Vue.use()来安装路由功能==**)

​	第一步：**导入**路由对象，并且调用**<font color='red'>Vue.use( Vue Router)</font>**

​	第二步：**创建路由实例**，并且传入路由**映射配置**

​	第三步：在Vue实例中**挂载**创建的路由实例



路由的配置：

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617713320952.png" alt="1617713320952" style="zoom:80%;" />

vue实例中进行挂载：

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617713349388.png" alt="1617713349388" style="zoom:80%;" />

以上这些步骤在安装脚手架时选择安装路由的话会默认安装好，**==到时候只需要配置路由与组件之间 的映射关系就行了==**



## 路由通过< router-link>和< router-view>进行跳转

**==使用vue- router的步骤==**

第一步：创建路由组件，即编写vue文件，创建组件（因为一个页面就是一个组件）

第二步：配置路由映射：组件和路径映射关系

第三步：使用路由：通过< router-link>和< router-view>

下面是具体如何写两个路由组件并且显示在页面上

例子：

在router文件中的index.js文件中重新配置两个路由与组件的对应关系

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617716061571.png" alt="1617716061571" style="zoom:80%;" />

两个组件放在components文件夹中，组件具体内容如下

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617716337492.png" alt="1617716337492" style="zoom:80%;" />

首页显示的组件为App.vue，在这个组件中引入创建的两个路由

用**==router-link标签==**来引入 （**<font color='red'>被渲染成一个a标签，查看网页代码就是一个a标签</font>**），用**==to属性==**来标识路由的名称

用**==router-view标签==**表示路由放置的位置，放在那里就在哪里像是路由组件，相当于站位

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617717749668.png" alt="1617717749668" style="zoom:80%;" />





![1617717838156](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617717838156.png)

![1617717849441](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617717849441.png)

![1617717859392](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617717859392.png)





![1617717909867](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617717909867.png)

![1617717926194](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617717926194.png)

![1617717948878](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617717948878.png)



## 路由的默认值和修改为history

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617718177408.png" alt="1617718177408" style="zoom:67%;" />

为主页设置一个默认显示的路由组件

在index.js文件中的创建vuerouter对象的地方

再添加一个路由与组件的映射关系

使用**==redirect属性==**进行重定向，**==当相对地址path为空时，将地址重定向到Home==**

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617718529230.png" alt="1617718529230" style="zoom: 80%;" />





以上对路径的修改**==默认都是通过url的hash值来进行修改的==**，总是地址的地方总是有一个#号

![1617718750635](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617718750635.png)

如果想改为history模式

**==在index.js文件中创建vuerouter对象的地方==**

之前只有routers数组这一个属性

现在在传一个**==mode属性==**，将mod属性命名为history即可

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617719061908.png" alt="1617719061908" style="zoom:80%;" />

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617719034193.png" alt="1617719034193" style="zoom:80%;" />

## router-link的其他属性的补充

### tag属性

：tag可以**==指定< router-link>之后演染成什么组件==**，即使查看网页源码也会显示被渲染的标签，比如上面的代码会被渲染成一个<li>元素，而不是<a>

![1617719375544](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617719375544.png)

![1617719351465](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617719351465.png)

### replace属性

 replace不会留下 history记录，所以指定 replace的情况下，**==后退键返回不能返回到上一个页面中==**，该属性不用赋值

![1617719400064](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617719400064.png)

### active-class属性

1、正常写router-link标签的时候，如果该标签设置了默认路由或者点击了某个路由，就会自动添加一些样式，如下图

![image-20210519110949493](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210519110949493.png)

![image-20210519110941864](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210519110941864.png)


可以通过这个样式，来改变路由标签的样式

![image-20210519110923822](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210519110923822.png)

2、如果不想用默认的router-link-active类名，可以在router-link中写上**==active-class="自定义的类名"==**，即可

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210519110901145.png" alt="image-20210519110901145" style="zoom:80%;" />

![image-20210519110911414](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210519110911414.png)

但是这么写，如果路由增多了，会导致在router-link标签中的active-class也会增多，冗余代码就会出现，所以有个简便写法，在你**==路由配置的文件中==**，找到如下图的代码块，加上**==linkActiveClass:"自定义的类名"==**，即可

![image-20210519110847712](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210519110847712.png)

同时，页面中的router-link标签中的active-class就不需要了，恢复到最初的样子即可

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210519110817374.png" alt="image-20210519110817374" style="zoom:80%;" />

## 通过代码跳转路由

上面方法是通过==路由组件==+==router-link==+==router-view==标签来实现路由跳转

还有一种方法是通过代码跳转路由，同样要用到**==router-view==**

仅仅在app组件中添加两个按钮，为按钮绑定两个点击事件

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617766090308.png" alt="1617766090308" style="zoom:80%;" />

**==vue-router模块往所有的组件里面==**添加了一个**==$router属性==**

通过**==this.$router.push('')==**来进行路由的跳转

push内部使用的方法其实是**==history.pushState()==**，**==浏览器可以返回==**

![1617766156642](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617766156642.png)

对应的还有一个**==this.$router.replace('')==**方法来跳转路由，

该方法使用的是**==history.replaceState()==**，**==浏览器不能返回==**

![1617766172252](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617766172252.png)





## ==动态路由的使用==



![1617783206382](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617783206382.png)

某些情况下一个页面的path路径是不确定的，比如：不同用户登录时，大致的url路径是一样的，但是不同用户的url路径最后面可能是不一样的，张三:user/zhangsan，李四:user/lisi

也就是**path部分的路径不同**，这种**==path（相对路径）和component（组件）的匹配关系==**，称之为**==动态路由==**



创建动态路由的过程：

**<font color='red'>①</font>**

在router对象中添加一个路由与组件的映射关系

只不过这个映射关系的path的值最后添加一个**==冒号+变量		:变量==**

冒号标明这个是个变量，可以被替换

![1617786324599](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617786324599.png)



**<font color='red'>②</font>**

在App组件中，在使用User路由组件的时候，来为动态路由中的变量赋值

在APP组件的**==data中定义一个变量（当然可以从数据库中调用）==**，在router-link的**==to属性==**中引用这个变量

引用变量的时候，因为是在标签里面，所以要使用**==v-bind==**，并使用**==+加号==**与/user/来进行路径拼接

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617789110371.png" alt="1617789110371" style="zoom:80%;" />

**<font color='red'>③</font>**

上面几部将动态路由地址修改好了，还没有相应的路由组件，新建一个User组件，

不同的用户应该有不同的内容，要想在User组件中显示App组件从data中引入的用户名的名字

这就用到了之前在**==绑定路由与组件时用到的冒号后面的变量==**

![1617789345725](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617789345725.png)

这个值在App组件中已经被赋值，所以User组件中可以使用这个变量来获取数据

router对象中有一个**==$route属性==**（**<font color='red'>注意与$router属性区别开</font>**），此属性指的是当前活跃的路由组件（就是当前页面显示的是哪一个路由组件，$router指的是哪一个路由组件）

**==this.$route.params==**：指的是活跃路由组件的参数，在参数中可以引用uname变量，即**==this.$route.params.uname==**

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617789151530.png" alt="1617789151530" style="zoom:80%;" />



## 打包文件的解析

在之前使用webpack进行打包的时候，将所有打包的文件，除了HTML文件时另外打包的，**==所有的js与css文件都是打包到了bundle.js文件中==**，并进行了**==压缩==**



但是在vue中，将文件进行打包后，上传到**==dist文件夹==**中，**==js和css文件进行了分离==**，并且**==index.html文件也进行了压缩==**

其中js文件也并不是一整个，而是进行了划分，**==分为三个js文件==**，三个文件代表三个层次

**==第一个==**：当前应用**程序开发的所有代码**，即我们自己写的所有代码

**==第二个==**：**manifest**为我们打包的代码作**底层支撑**的，比如我们代码中使用的commonJS或ES6的语法规范，或者其他的一些复杂的处理，为这些做低层支撑

**==第三个==**：**vendor第三方/提供商**，我们在编写程序时使用的框架、引用的第三方的内容：vue、vue-router、axios、bs等等

![1617792717073](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617792717073.png)



## 路由懒加载的使用

如果项目多的话，页面第一次进行加载，从服务器一次性会把所有的文件进行下载

如果文件过大，页面第一次加载会很卡顿



我们希望的是，每次加载页面，用到了那个路由组件，就从服务器上加载过来，没用到了路由组件先不从服务器上加载过来，之后用到哪个在加载哪个，这就叫**==路由懒加载==**

之前打包的话，所有我们自己写的代码都打包到了一个js文件，也就是所有的路由组件都打包到了一个文件，现在要实现懒加载，就需要将每个路由组件从这一个js文件中分离出来

![1617794104786](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617794104786.png)

![1617795961313](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617795961313.png)





在router的index.js文件中，将所有的路由组件进行懒加载   

而App.vue 是不需要懒加载的，因为一开始App就是我们主页面的内容

**==es6中懒加载的代码如下==**

![image-20210519171558546](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210519171558546.png)

所以打包后，除了**manifest**和**vendor**这两个文件，还有四个：一个App.vue文件，三个懒加载的文件

![1617796752468](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617796752468.png)

## 路由的嵌套使用

![1617796869341](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617796869341.png)



步骤跟之前创建路由组件大致相同

**<font color='red'>①</font>**

先创建两个子组件放在components文件夹中

![1617798331180](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617798331180.png)

**<font color='red'>②</font>**

在router文件夹中的index.js文件中进行路由子组件的映射绑定

**==子组件的映射绑定添加在在父组件的映射对象中就行==**

在父组件的映射对象中添加一个children数组，数组中就是子组件的路由与组件的映射绑定

跟之前讲的一样，同样可以为子组件指定默认显示的组件

**<font color='red'>注意：在子组件中，无论是path中的地址，还是redirect中的地址，都不要在前面加/斜杠</font>**

![1617798530434](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617798530434.png)



**<font color='red'>③</font>**

在父组件中导入子路由组件，也就是子组件路由标签的使用放在Home父组件中

同样使用router-link标签和to属性来导入

使用router-view标签来占位

**<font color='red'>注意：  to属性中不能只写子路由组件的path，应当带上父组件的</font>**，这样才表明嵌套关系，不然直接就用子路由路径替换了父路由路径，**<font color='red'>同时注意一定在最前面加/斜杠</font>**

![1617798880984](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617798880984.png)



## ==参数传递==

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617799756181.png" alt="1617799756181" style="zoom:67%;" />



![1617801174362](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617801174362.png)

![1617801141632](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617801141632.png)

==**统一资源定位符	协议://主机:端口/路径?查询#哈希片段**==

==**url	scheme://host:port/path?query#fragment**==



### **<font color='red'>关于path、url、params</font>**

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617802669145.png" alt="1617802669145" style="zoom:67%;" />

url就指的是整个的网址

path就指的是网址后面几个/斜杠中的内容，包括多个路由嵌套

params指的是



### query传递参数

参数传递主要有两种类型：**==params==**、**==query==**

**==params类型之前已经使用过了==**

使用query方法的话，想从App组件中向子组件传递参数，下面通过router-link标签来跳转路由

同样先在App组件中子组件标签的to属性中写入需要传的参数

同样为to属性绑定**==v-bind==**，**==to属性双引号中的内容变成了一个对象==**

对象有**==两个属性==**

​	==**path属性**==：子组件的地址

​	==**query属性**==：属性值是一个对象，里面是需要传递的各种数据

![1617802320762](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617802320762.png)

添加query后，url如下，query部分是问号后面的部分

![1617801888787](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617801888787.png)

**==路由子组件收到数值时通过$route.query.变量来接收==**

![1617803166275](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617803166275.png)



**==例子==**：通过**==代码的方式进行路由跳转==**，并用query传递参数

**app.vue**

![1617805118197](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617805118197.png)

![1617805193602](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617805193602.png)

**profile.vue**

![1617805257416](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617805257416.png)



## router和route的由来

**==$router==**

在index.js文件中导出的整个export default new Router

这和组件中使用的$router拿到的对象是一样的

这个router对象跟$router所指的对象是一个东西

这个对象有go、back、forward、replace等方法



==**$route**==

$route指的是当前活跃的路由，也就是在index.js文件中配置的一个个路由



==上面这两个属性，都属于**vue原型里面的属性**==



## ==导航守卫==

在几个路由之间进行跳转时，如果想做一些监听，在监听函数中做一些事情，就用到了导航守卫

### **==几个生命周期钩子函数==**

create()：在组件一被创建出来就回调这个函数，函数内容自定义，可以做一些操作

mounted()：在组件一被挂载到dom中，就会回调这个函数中的内容，同样函数的内容是自定义的

updated()：在页面发生刷新的时候，就调用一次这个函数



扩展：

<img src="https://img-blog.csdn.net/20180811182143658?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NsZWVwd2Fsa2VyXzE5OTI=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" alt="img" style="zoom: 50%;" />

下面解释一一对应图中的数字

1、var vm = new Vue({}) 表示开始创建一个Vue的实例对象

2、刚初始化一个空的Vue实例对象，此时，在这个对象上，只有一些默认的生命周期函数和默认的事件，其他的都未创建

3、**==beforeCreate==**生命周期函数执行时，**data和methods中的数据和方法都还没有初始化**

4、初始化data和methods

5、在**==created==**中，**data和methods都已经初始化好了**，<font color='red'>**如果要操作data中的数据或是调用methods中的方法，最早只能在created中操作**</font>

6、这个绿框中内容表示Vue开始编辑模板，把Vue代码中的那些指令进行执行，最终，在内存中生成一个编译好的最终的模板字符串对象，然后把这个字符串对象，渲染为内存中的DOM，此时，**只是在内存中渲染好了模板，并没有把模板挂载到真正的页面中去**

7、**==beforeMount==**函数执行时，**模板已经在内存中编译好了**，**但尚未挂载到页面中去，此时，页面还是旧的**

8、将内存中编译好的模板，真实的替换到浏览器的页面中区

9、**==mounted==**是在**页面加载完成后执行的函数**，<font color='red'>**如果要通过某些插件操作页面上的DOM节点，最早是在mounted中进行**</font>

10、只要执行完了mounted，就表示整个Vue实例对象已经初始化完毕了，此时组件已经**脱离创建阶段**，进入运行阶段。

11、蓝框中是组件的运行阶段，运行阶段的生命周期函数只有两个：beforeUpdate和updated，这两个事件会根据data数据的改变，有选择的触发0次到多次

12、当执行**==beforeUpdate==**时，页面中显示的数据还是旧的，此时data中的数据是最新的，页面尚未和最新数据同步

13、这一步，先根据data中最新的数据，在内存中，重新渲染出一份最新的内存DOM树，当内存DOM树被更新之后，会把最新的的内存DOM树，重新渲染到真实的页面当中，这时，就完成数据从data（Model层）->view（视图层）的更新

14、**==updated==**执行时，页面和data数据已经保持同步，都是最新的

15、当执行**==beforeDestroy==**钩子函数时，Vue实例就已经从运行阶段进入销毁阶段，此时，组建中所有data、methods、以及过滤器，指令等，都处于可用状态，此时还未真正执行销毁过程

16、当执行**==destroyed==**函数时，组件已经被完全销毁，此时组建中所有data、methods、以及过滤器，指令等，都已经不可用了



### 导航守卫

![1617884895070](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617884895070.png)

**==情景==**

比如，如果想在每次切换页面的时候，页面的title也发生改变，切换到User界面，title就变成用户，切换到About界面title就变成关于......

在每个路由组件中添加create()函数，在函数中将document.title改成对应的值

create函数是在组件data和methods都已经初始化好了之后调用

![1617881353548](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617881353548.png)

这样每个路由的title都被改掉了

但是这么做效率太低，每个路由都需要调用一次create钩子函数

改进方法就是**==全局导航守卫==**



**==全局导航守卫==**：

在router的index.js文件中，在每个路由项中添加**==meta属性（名字不能错）==**，属性中可以添加一些**==元数据（描述数据的数据）==**，在所有的路由项中添加相应的title标题名

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617881545693.png" alt="1617881545693" style="zoom:67%;" />

在index.js文件下面拿到**router对象**，router对象有一个**==beforeEach函数==**

beforeEach是一个前置钩子

这个beforeEach函数的**参数**是一个函数

这个**==作为参数的函数==**本身有三个参数：to，from，next

​	**==to==**：跳转到的路由

​	**==from==**：从哪个路由进行跳转，也就是要离开的路由对象

​	**==next==**：是一个函数，这个函数必须在函数中进行调用，否则所有的路由都不会跳转,本来这个方法时router对象自动调用的，这里自定义话，**==这个函数必须写上==**



在这个函数中将document.title=to.meta.title，函数可以写成箭头函数

![1617882305970](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617882305970.png)



但是这样做有一个问题，**<font color='red'>当有路由嵌套的时候，title不能正常显示</font>**

因为有路由嵌套和没有路由嵌套的to对象不太一样

无路由嵌套：

![1617882550720](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617882550720.png)

有路由嵌套：

![1617882559584](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617882559584.png)

**==发现有路由嵌套的to对象中的meta中没有title属性==**

但是无论有没有嵌套路由，在to对象中有一个**==matched数组==**，数组中的第一个对象中，都会有meta属性，并且有定义的title值

![1617883011884](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617883011884.png)

于是路由都从**==to对象的matched数组中的第一个对象==**获取meta就可以了

![1617883201011](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617883201011.png)



### 导航守卫补充

前面讲到的beforeEach是一个前置钩子，官方更愿称之为**==守卫==**（guard）

对应的也有后置钩子（hook）：afterEach

afterEach的参数也是一个函数，这个函数的参数只有两个：to、from

因为这是已经跳转完了，并不需要做其他的操作，也就不需要next()函数了



关于next()函数的补充

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617885953527.png" alt="1617885953527" style="zoom:80%;" />



上面我们使用的守卫是全局守卫

除此之外还有路由独享守卫、组件内的守卫

https://router.vuejs.org/zh/guide/advanced/navigation-guards.html

**==路由独享守卫==**

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617886017142.png" alt="1617886017142" style="zoom:80%;" />

在组件中添加beforeEnter属性，属性的内容是一个函数，内容、参数和之前的全局守卫一样

同样需要在这个箭头函数中添加一个next()函数



**==组件内的守卫==**

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617886386535.png" alt="1617886386535" style="zoom:80%;" />

















### ==PS： 网上资料补充==

#### **1.导航守卫是什么**

官方这么说：

> *正如其名，`vue-router`提供的导航守卫主要用来通过跳转或取消的方式守卫导航。*

好吧，看不懂，就好（当）好（废）理（话）解（吧）下。其实，导航守卫就是路由跳转过程中的一些钩子函数，再直白点路由跳转是一个大的过程，这个大的过程分为跳转前中后等等细小的过程，在每一个过程中都有一函数，这个函数能让你操作一些其他的事儿的时机，这就是导航守卫。

#### **2.导航守卫全解析**

先看一个钩子函数执行后输出的顺序截图吧，一般讲解都会在之后呈现，给大家换种思路（也就是先预习再学习最后复习）

<img src="https://pic4.zhimg.com/80/v2-c3a67a5eb0b8da4936a6b57ef8c48783_720w.jpg" alt="img" style="zoom:80%;" />

好吧不知道的估计看不懂吧！不过我希望你能看到一个点能多倒回来看看这个顺序，前方干货预警

------

**导航守卫分为**：全局的、单个路由独享的、组件内的三种。分别来看一下：



##### 全局的

【全局的】：是指路由实例上直接操作的钩子函数，他的特点是所有路由配置的组件都会触发，直白点就是触发路由就会触发这些钩子函数，如下的写法。钩子函数按执行顺序包括**==beforeEach、beforeResolve（2.5+）、afterEach==**三个（以下的钩子函数都是按执行顺序讲解的）：

```js
const router = new VueRouter({ ... })

router.beforeEach((to, from, next) => {
  // ...
})
```

**[beforeEach]**：**==在路由跳转前触发==**，参数包括to,from,next（参数会单独介绍）三个，这个钩子作用主要是用于登录验证，也就是路由还没跳转提前告知，以免跳转了再通知就为时已晚。

**[beforeResolve]**（2.5+）：这个钩子和beforeEach类似，也是路由跳转前触发，参数也是to,from,next三个，和beforeEach区别官方解释为：

> 区别是在导航被确认之前，**==同时在所有组件内守卫和异步路由组件被解析之后==**，解析守卫就被调用。

即在 beforeEach 和 组件内beforeRouteEnter 之后，afterEach之前调用。

**[afterEach]**：和beforeEach相反，他是**==在路由跳转完成后触发==**，参数包括to,from没有了next（参数会单独介绍）,他发生在beforeEach和beforeResolve之后，beforeRouteEnter（组件内守卫，后讲）之前。



##### 路由独享的

【路由独享的】是指在单个路由配置的时候也可以设置的钩子函数，其位置就是下面示例中的位置，也就是像Foo这样的组件都存在这样的钩子函数。**==目前他只有一个钩子函数beforeEnter：==**

```js
const router = new VueRouter({
  routes: [
    {
      path: '/foo',
      component: Foo,
      beforeEnter: (to, from, next) => {
        // ...
      }
    }
  ]
})
```

[beforeEnter]：**==和beforeEach完全相同==**，如果都设置则在beforeEach之后紧随执行，参数to、from、next



##### 组件内的

【组件内的】：是指在组件内执行的钩子函数，**==类似于组件内的生命周期，相当于为配置路由的组件添加的生命周期钩子函数==**。钩子函数按执行顺序包括**==beforeRouteEnter、beforeRouteUpdate (2.2+)、beforeRouteLeave==**三个，执行位置如下：

```js
<template>
  ...
</template>
export default{
  data(){
    //...
  },
  beforeRouteEnter (to, from, next) {
    // 在渲染该组件的对应路由被 confirm 前调用
    // 不！能！获取组件实例 `this`
    // 因为当守卫执行前，组件实例还没被创建
  },
  beforeRouteUpdate (to, from, next) {
    // 在当前路由改变，但是该组件被复用时调用
    // 举例来说，对于一个带有动态参数的路径 /foo/:id，在 /foo/1 和 /foo/2 之间跳转的时候，
    // 由于会渲染同样的 Foo 组件，因此组件实例会被复用。而这个钩子就会在这个情况下被调用。
    // 可以访问组件实例 `this`
  },
  beforeRouteLeave (to, from, next) {
    // 导航离开该组件的对应路由时调用
    // 可以访问组件实例 `this`
  }
}
<style>
  ...
</style>
```

**[beforeRouteEnter]**：路由进入之前调用，参数包括to，from，next。该钩子在全局守卫beforeEach和独享守卫beforeEnter之后，全局beforeResolve和全局afterEach之前调用，要注意的是**==该守卫内访问不到组件的实例，也就是this为undefined==**，也就是他**在beforeCreate生命周期前触发**。

在这个钩子函数中，可以通过传一个回调给 next来访问组件实例。在导航被确认的时候执行回调，并且把组件实例作为回调方法的参数，可以在这个守卫中请求服务端获取数据，当成功获取并能进入路由时，调用next并在回调中通过 vm访问组件实例进行赋值等操作，（next中函数的调用在mounted之后：为了确保能对组件实例的完整访问）。

```js
 beforeRouteEnter (to, from, next) {
  // 这里还无法访问到组件实例，this === undefined
  next( vm => {
    // 通过 `vm` 访问组件实例
  })
}
```

**[beforeRouteUpdate]** (v 2.2+)：在当前**==路由改变==**时，并且该**==组件被复用==**时调用，可以通过this访问实例。参数包括to，from，next。可能有的同学会疑问，what is 路由改变 or what is 组件被复用？

- 对于一个带有动态参数的路径 /foo/:id，**==在 /foo/1 和 /foo/2 之间跳转的时候==**，组件实例会被复用，该守卫会被调用
- 当前路由**==query变更==**时，该守卫会被调用

**[beforeRouteLeave]**：导航离开该组件的对应路由时调用，可以访问组件实例`this`，参数包括to，from，next。



至此，所有钩子函数介绍完毕。

屡一下哈：

**全局路由钩子：beforeEach(to,from, next)、beforeResolve(to,from, next)、afterEach(to,from)；**

**独享路由钩子：beforeEnter(to,from, next)；**

**组件内路由钩子：beforeRouteEnter(to,from, next)、beforeRouteUpdate(to,from, next)、beforeRouteLeave(to,from, next)**

不知道你是否还记得to、from、next这三个参数

下面请重头把这几个钩子函数的参数看一遍，细心的同学可以看见在afterEach钩子中参数没有next，为什么呢？

#### **3.导航守卫回调参数**

to：目标路由对象；

from：即将要离开的路由对象；

next：他是最重要的一个参数，他相当于佛珠的线，把一个一个珠子逐个串起来。以下注意点务必牢记：

1.但凡涉及到有next参数的钩子，必须调用next() 才能继续往下执行下一个钩子，否则路由跳转等会停止。

2.如果要中断当前的导航要调用next(false)。如果浏览器的 URL 改变了 (可能是用户手动或者浏览器后退按钮)，那么 URL 地址会重置到`from`路由对应的地址。（主要用于登录验证不通过的处理）

3.当然next可以这样使用，next('/') 或者 next({ path: '/' }): 跳转到一个不同的地址。意思是当前的导航被中断，然后进行一个新的导航。可传递的参数与[router.push](https://link.zhihu.com/?target=https%3A//router.vuejs.org/zh/guide/essentials/navigation.html)中选项一致。

4.在beforeRouteEnter钩子中next((vm)=>{})内接收的回调函数参数为当前组件的实例vm，这个回调函数在生命周期mounted之后调用，也就是，他是所有导航守卫和生命周期函数最后执行的那个钩子。

5.next(error): (v2.4.0+) 如果传入 `next` 的参数是一个 `Error` 实例，则导航会被终止且该错误会被传递给 `router.onError()` 注册过的回调。

#### **4.总结**

好了，还记得那个截图吗，我们再看一遍

<img src="https://pic4.zhimg.com/80/v2-c3a67a5eb0b8da4936a6b57ef8c48783_720w.jpg" alt="img" style="zoom:67%;" />

我们最后屡一下顺序：

**当点击切换路由时：beforeRouterLeave-->beforeEach-->beforeEnter-->beforeRouteEnter-->beforeResolve-->afterEach-->beforeCreate-->created-->beforeMount-->mounted-->beforeRouteEnter的next的回调**

**当路由更新时：beforeRouteUpdate**













### keep-alive及其其他问题

**==情景==**

如下的首页

![1617886579022](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617886579022.png)



首页中子组件设定默认显示的是新闻，当我们在首页中点击了消息页面，点击用户或者档案路由组件后，再次返回首页，这时候子组件又变成了新闻，不会保留我们之前的状态

keep-alive就是用来保留我们网页状态的一个组件

因为之前的每一个路由组件的打开与关闭都是一个生命周期

每次都会经历create()创建一个新的路由，在经过destroy()函数销毁，每次都是一个新的过程

keep-alive就相当于保持存活的意思 



**==keep- alive==**是**==Vue==**内置的一个组件，可以使被包含的组件保留状态，或避免重新渲染。

**==router-view==**是**==vue-router==**内置的一个组件，**如果直接被包在 keep- alive里面，所有路径匹配到的视图组件都会被存**



①

在App组件之前的router-view标签前后套上一个keep-alive标签

​	![1617889745701](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617889745701.png)

②

在index.js文件中之前设置的home路由默认指定的子路由路径取消

![1617889811268](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617889811268.png)



③

将指定默认子路由的步骤放在Home.vue文件中来做

在组件的data中放一个path变量，用来保存/home/news

使用**==activated()函数==**（此函数是==当前页面活跃时的钩子函数==）

（对应的还有一个deactivaed函数，即为失去活跃，

**<font color='red'>注意：这两个函数，只有该组件被保持了状态使用了keep- alive时，才是有效的</font>**）



使用**==this.$router.push方法==**将当前地址进行修改

修改为data中存放的path变量

![1617890180830](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617890180830.png)

④

然后在使用一个上面提到的组件内的导航守卫beforeRouteLeave函数

```javascript
beforeRouteLeave(to, from, next) {
    // 导航离开该组件的对应路由时调用
    // 可以访问组件实例 `this`
    ....
    next()
  }
```

当在home组件中点击任意一个子路由组件，离开时会调用beforeRouteLeave函数

在函数中将path重新赋值为当前的路径

![1617890847720](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617890847720.png)

因为此时路由已经处于keep-alive 所以，这个值还会被保留下来

再次打开home页面时，由于activated钩子函数又一次调用

地址会被绑定到已经赋过值的path



### keep-alive属性介绍

它们有两个非常重要的属性：

 **==include==**：**字符串或正则表达**，只有匹配的组件会被缓存

**==exclude==**：**字符串或正则表达式**，任何匹配的组件都不会被缓存

之前在组件的**==export default{}中习惯性的写了name属性==**

但是之前一直没用过，现在可以用于include/exclude属性来匹配路由组件

![1617892752785](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617892752785.png)

在**==keep-alive标签==**中添加include/exclude属性，属性值就是**==name值==**

![1617893057055](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617893057055.png)



多个路由组件用**==,逗号==**分开，**<font color='red'>注意逗号后面不能加空格</font>**

![1617893143976](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617893143976.png)





## 文件别名

找到**==webpack.base.config.js文件==**

在文件的**==resolve对象==**中找到**==alias属性==**进行文件别名的设置

之前讲过resolve对象，是专门用来解决文件路径问题的一个对象

​	之前讲过这里面用来**省略文件后缀** 的一个属性：**extensions**

**alias（别名）属性中设置文件的别名，使用时可以简化路径书写**

**并且之后在复制代码时，不用担心路径问题**

![1617970418113](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617970418113.png)

![1617969561396](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617969561396.png)

**<font color='red'>注意：这种修改路径的方法在js代码中（基本上就是import）可以直接使用</font>**

**<font color='red'>在HTML代码中（像src）就不能直接使用了，需要在路径前面加上波浪符号~</font>**

在**<font color='red'>cli2中</font>**定义路径别名，**<font color='red'>后面定义的不能利用之前定义的别名</font>**，也就是上面这个例子，后面别名定义时，不能利用@这个上面定义过的别名

**<font color='red'>cli3中可以用</font>**

![1617970155931](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617970155931.png)





## Vuex

![1618032579791](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618032579791.png)





![1618043049555](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618043049555.png)

![1618043068783](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618043068783.png)

![1618043101377](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618043101377.png)

### Vuex安装配置

**==Vuex就是一个提供多个组件间共享状态的插件==**

表明各种状态一般就是通过变量来记录，也就是将多个组件共享的变量放在一个对象中进行存储，并且可以做到**==响应式==**

![1618033277064](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618033277064.png)

像用**户登录状态、用户名称，头像、地理位置、商品的收藏，购物车中的物品**，都可以放到vuex中

在命令行中输入：**==npm install vuex --save==** 进行安装

然后进行模块的导入（import）和使用（Vue.use）

但是配置的工作**一般不放**在main.js 文件中

像router一样，重新创建一个文件夹，然在**==str文件夹==**下面

一般这个文件夹约定俗成都叫**==store==**，在store文件夹中创建**==index.js文件==**

在**==index.js文件==**中进行**安装插件、创建对象、导出对象**

**<font color='red'>注意这里创建的对象不是Vuex，而是Vuex.store</font>**,使用的时候使用的也是store

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618041239608.png" alt="1618041239608" style="zoom:80%;" />

然后再**==main.js文件==**中进行挂载，在vue构造函数中添加store

这样相当于在**==Vue的原型中添加了$store==**，这样早其他组件中就可以使用store的相关东西

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618042026068.png" alt="1618042026068" style="zoom:80%;" />

Vuex对象中一般有图中几个对象

state：记录各个组件中状态的一些变量

 



配置好后，在各个组件中就可以通过**==$store.state来访问vuex中的变量==**，当然也可以直接进行修改，如图：

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618043294893.png" alt="1618043294893" style="zoom:80%;" />

单数官方不建议这样修改，因为官方建议按照制定好的规定来修改state

下面是官方对于修改state操作的一个流程图

![1618044558315](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618044558315.png)

### devtools和mutations

devtools时Chrome浏览器上的一个插件，安装上就可以使用devtools工具来查看vue项目的一些情况

之前说过在创建的Vuex.store对象中有几个对象，其中有一个mutations

 以后定义方法就可以在mutations中**==定义一些方法==**

以后只要是想修改state，都**==至少通过mutations==**来修改的，有**==异步操作==**在**==通过actions==**

定义的方法默认有一个**==参数state==**，就是上面**<font color='red'>表示状态的对象</font>**

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618055779999.png" alt="1618055779999" style="zoom:80%;" />



然后在**==App组件==**中调用mutations方法时，**==通过this.$store拿到score对象==**，然后**==通过commit==**（对应上面流程图中提交这一步）**==来调用score对象的mutations中定义的方法==**

 **==this.$store.commit("方法")==**

![1618056256892](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618056256892.png)

打开**==devtools==**插件后，也能看到**==状态state中的变量的实时变化==**

**而上一节中绑定click事件的方法state并没有实时变化**

![1618055681985](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618055681985.png)



### state单一状态树的理解

**==即一个项目只用一个store==**

![1618056947496](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618056947496.png)



### Getters使用详解

store中的getters跟组件中的computed很像

可以将他理解为计算属性

**==功能是将state中的一些数据做一些变化、操作再进行返回==**

跟mutations一样，getters定义的函数默认有一个**==参数state==**，就是上面**<font color='red'>表示状态的对象</font>**

下图例子， 获取学生年龄大于20的人数

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618058067196.png" alt="1618058067196" style="zoom:80%;" />

之前要是在computed中写的话

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618058126975.png" alt="1618058126975" style="zoom:80%;" />

现在是利用store中的getters来定义函数，整合数据

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618058337207.png" alt="1618058337207" style="zoom:80%;" />



在APP.vue 中要调用getters中的函数的话，需要通过**==$score.getters.函数名==**，**<font color='red'>函数名后面不需要加括号</font>**

上面这个函数还可以改写一下，在getters对象中的函数中可以传递一个**==getters参数==**，**==这个getters就是当前的getters对象本身==**，也就意味着在getters中的函数中可以调用**==上面定义过的函数作为参数==**，方便后面函数的编写，如图

![1618058653442](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618058653442.png)

**<font color='red'>也就是说getters有两个参数，state、getters这两个，别的参数不会接收，要想传入参数，就在函数内部调用state就行了，不能将多余的参数传入</font>**



**==但是如果想传入参数呢？==**

可以在getters函数中**==返回一个函数==**，返回的函数中可以传入一个参数

App组件中在调用getters中函数时，可以传入一个参数，**==这个参数会被传入到函数返回的函数中去==**，这样就可以利用传过来的参数进行计算了

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618059167508.png" alt="1618059167508" style="zoom:80%;" />

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618059183848.png" alt="1618059183848" style="zoom: 80%;" />



### mutations的携带参数

vuex的store状态更新的唯一方式：提交Mutations（其实就是调用Mutations中方法的过程）

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618105592246.png" alt="1618105592246" style="zoom:67%;" />

之前讲过mutations的基本用法，现在讲组件调用mutations中函数时，同时传入参数

在score中的**==index.js中==**的mutations中定义函数，除了参数state，另外的参数一同写到函数的括号中

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618105751102.png" alt="1618105751102" style="zoom:80%;" />

在App.vue中的methods中调用index.js中定义的函数，将参数作为commit的第二个参数传入就行，不是放在引用的函数中，语法： **==this.$store.commit("函数",参数)==**

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618106122184.png" alt="1618106122184" style="zoom:80%;" />

参数被称为mutations的**==载荷（payload）==**

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618106700289.png" alt="1618106700289" style="zoom:67%;" />

### mutations的提交风格

在App组件中，上面通过commit提交是一种普通的方式

还有一种方式，commit提交的就不是函数和参数了

commit提交的是一个对象，对象里**第一个属性**	**==type==**是函数名，**第二个属性**是**==参数==**

![1618107796434](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618107796434.png)



但是这时候count就不再是一个数字了，**==而是一个对象，==**可打印出来进行查看

![1618108538705](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618108538705.png)

在mutations中使用参数的时候，就**==要将对象中的count取出来在进行计算==**，这时候第二个参数再用count就不合适了，可以改一下

![1618108580169](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618108580169.png)

### Vuex数据响应式原理

**<font color='red'>（注意：以下提到的不能进行响应式的方法，在vuecli4中，进行了更新，部分内容变得可以了，根据实际情况进行判断）</font>**

在之前的mutations中修改state中的属性，vue会发生响应式更新

但是响应式需要遵守一些规则

所有响应式的**==前提是所有的属性在store中已经初始化好了==**

**==不能像这样下面这样，添加属性进行赋值==**

![1618109166475](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618109166475.png)

虽然查看动态state中的属性，info中确实新增了address属性，但是**==不会实时进行响应，页面不会发生变化==**

![1618109136292](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618109136292.png)



前面vue关于**==数组响应式==**的讲解中提到过，通过**==索引值修改数组元素的方法不是响应式的==**

数组修改要做到响应式，应该用**==Vue.set方法==**或者**==splice方法==**

![1618109787142](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618109787142.png)



在这里，set方法同样适用于对象

语法：**==Vue.set(要修改的对象,索引值/属性名,修改后的值)==**

![1618110024969](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618110024969.png)

**<font color='red'>这样就是响应式的了，set内部会将新增的属性添加到响应式系统里面</font>**









同样，想要删除某个属性直接用**==delete 对象.属性==**是删不掉的

![1618110279350](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618110279350.png)

同样需要用到Vue中的方法：**==Vue.delete方法==**

![1618110494345](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618110494345.png)



### mutations的类型常量

官方推荐了一种方法，为了防止在mutations中定义的函数在组件中使用提交commit时这些函数名或变量写错，如下

![1618123572430](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618123572430.png)



### actions使用详解

上面使用mutations时进行的都是**==同步操作==**，在满足响应式操作时，所有的修改都会实时地体现在state中

**==但是如果在mutations中使用的是异步操作，devtools工具不会实时地跟踪状态的变化==**

异步操作的函数将state中的变量进行修改，页面中发生变化，但是**==devtools中监测的值并不改变==**

![1618124169921](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618124169921.png)

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618123746605.png" alt="1618123746605" style="zoom:67%;" />





所以异步操作官方要求我们放到**==actions==**中去做

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618124895673.png" alt="1618124895673" style="zoom:80%;" />

**==注意：==**

​	**之前只用mutations时（中间横着这条红线），相当于<font color='red'>组件中使用commit提交</font>到mutations中，mutations中函数完成对state中变量的修改**

​	**==现在相当于中间加上一个actions==，<font color='red'>组件中使用dispatch来发布给actions，actions中的函数通过commit进行提交给mutations，然后mutations中的函数进行state的修改</font>**



在score中的index.js文件中定义actions

actions中定义异步操作的函数

跟mutations中函数默认参数state相似，**==actions==**中函数也有一个**==默认参数：context==**(上下文)

**==在这里context代表的是score==**，然后**==在actions中的函数中进行commit提交==**



#### 异步操作的流程

**<font color='red'>（这里为了理解将这一步放在前面，实际上流程是先dispatch在commit）</font>**

在mutations中定义好修改state的一个函数

![1618127958239](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618127958239.png)

然后在actions中将上面mutations中定义的函数进行commit提交（即调用mutations中的函数）

![1618124433177](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618124433177.png)

在**==组件中如果调用这个函数的话，需要使用dispatch进行发布==**（之前是commit提交）（相当于调用actions中的异步操作）

![1618124547839](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618124547839.png)

#### 参数传递



同样，actions也可以携带参数，

在组件中调用函数传实参时，**==将函数名和实参作为dispatch的两个参数（类似于commit传参的方法）==**，这样来传参

在actions中定义函数，可以像正常函数接收形参在括号里接收就行

同样可以传一个对象作为参数

![1618125807251](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618125807251.png)

![1618125685227](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618125685227.png)







#### 修改state成功的提示

组件在使用dispatch将state进行修改，如果修改成功，我们希望可以得到一个告知

**==一般我们认为只要调用index.js文件中mutations中的函数，在actions中执行了commit就算修改成功了==**

可以这么做：

在组件中除了函数名，再往dispatch中传递一个对象作为参数

对象中有message属性作为数据，还有一个函数方法

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618126652698.png" alt="1618126652698" style="zoom:80%;" />

在index.js中的actions中的函数中进行如下定义

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618126910493.png" alt="1618126910493" style="zoom:80%;" />

这样在组件中调用actions中函数，actions中再通过commit调用mutations中函数，完成这一步，就会打印相关信息，即可得到通知



**==更加优雅的写法：利用Promise==**

这里先不要管mutations，否则容易乱

在actions中将异步操作放到**==Promise==**中，并且通过**==return将Promise对象作为函数返回值返回==**。

> Promise中有一个执行成功后的操作，通过resolve()函数和then()函数完成

在setTimeout内部前几行，先commit给mutations，然后写**==resolve()函数==**表示执行成功，执行成功后的操作放在**==then()函数==**中去做

**==但是then函数在这里并不是写在index中的==**，**==而是写在App组件中，在用dispatch调用actions后==**，就可以跟上.then()，then函数中进行执行成功消息的打印

**<font color='red'>为什么then可以写在这里呢？</font>**

**<font color='red'>因为actions中的这个函数是有返回值的，在App组件中调用了这个函数，自然获得了这个Promise对象作为返回值，原本then()就是接在Promise对象后面的</font>**



**==actions中==**

![1618129702387](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618129702387.png)



**==vue组件中==**

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618130467193.png" alt="1618130467193" style="zoom:80%;" />







### modules使用详解

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618130878133.png" alt="1618130878133" style="zoom:67%;" />



一般就两层就可以了，多了反倒太复杂

像实例中那样，一般不会在modules中详细定义各个模块，一般都将模块对象抽离出来，在外面定义

然后这些模块通过**==属性名:模块名==**，作为modules的属性放到modules里面

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618132929533.png" alt="1618132929533" style="zoom:80%;" />

#### 模块中的state的使用

上图中，要想拿某个模块中的state，不是通过store.a.state，而是**==通过store.state.a==**来拿到不同模块中的state

**<font color='red'>为什么呢</font>**？**==因为modules在封装state时，其实是将他们都放在里一个state当中==**（**<font color='red'>仍然保持了单一状态树</font>**）

state中多了几个对象，每个对象就代表不同模块，每个对象里面是不同模块中的状态变量

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618133290881.png" alt="1618133290881" style="zoom:80%;" />

**==但是除了state，在mutations和actions中的方法直接使用名字就可以了，因为这两个当中的方法名是不能重复的==**



#### 模块的mutations中函数的调用

mutations中定义的函数，在组件通过commit调用时，**==就按正常调用就可以了，不用区分模块==**，因为函数名是不允许一样的，他只是**==优先在store外层找，找不到就去模块中找==**

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618133454196.png" alt="1618133454196" style="zoom:80%;" />

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618133685348.png" alt="1618133685348" style="zoom:80%;" />



#### 模块中getters的使用

getters也没有模块的特殊用法，和mutations一样，正常使用就可以了，不同模板中getters中函数名也不重复就行 

**<font color='red'>特殊的地方在于</font>**，在模块的getters函数中，还可以有**==第三个参数==**：**==rootState==**

这个参数是用来在getters函数中使用store外层state中变量，**==rootState代表的时外层的state==**

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618134194794.png" alt="1618134194794" style="zoom:80%;" />



#### 模块中actions的使用

在模块中的actions中定义函数，默认的参数context，这是**==context就不是store对象了==**

**==而是本模块对象==**，**==就比如通过context.commit调用的mutations中的函数不是外层的mutations，而是模板本身的mutations==**

下面是模板中context打印出来

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618135059235.png" alt="1618135059235" style="zoom:80%;" />

**==context.rootGetters==**拿的时外层的getters对象

**==context.rootState==**拿的时外层state对象



**ps：一个例子**

默认actions中的函数参数是==**context**==，将函数参数的地方==**用{state,commit,rootState}来代替**==，就相当于将context进行**==解构==**，取出里面的三个属性

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618140227716.png" alt="1618140227716" style="zoom:67%;" />



### store文件夹的目录组织

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618140541494.png" alt="1618140541494" style="zoom: 67%;" />



如果以后代码量多了后，所有的js代码全写到score中的index.js文件中有点太乱

官方建议将各个部分进行抽离

**==state在store对象外面进行定义==**，然后将定义的对象放到store中，不要在store对象中定义state中的内容，但是并**==不用抽离到另一个文件中去==**

modules、actions、getters、mutations这些部分都抽离成单独的文件

其中modules做成文件夹，文件夹里面每个模块一个js文件

![1618141268249](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618141268249.png)

![1618141515086](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618141515086.png)



## 网络模块的封装

![1618142765561](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618142765561.png)

![1618142831881](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618142831881.png)

![1618142882310](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618142882310.png)

![1618143033568](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618143033568.png)

![1618143097623](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618143097623.png)



### axios的基本使用

axios框架的安装：**==npm install axios --save==**

安装好后main.js中import导入

然后就可以在axios中直接使用了

在axios中传入相关的配置即网络请求（config）

相关的配置和网络请求是一个对象

```javascript
// axios内部支持promise，可以使用resolve、then等等
// 内部的resolve封装好了
// 可以直接在拿到数据后执行then()函数
axios({
  url: 'http://123.207.32.32:8000/home/multidata',
  // 请求的类型
  methods:'get'
}).then(res => {
  console.log(res);
})

axios({
  url:'http://123.207.32.32:8000/home/data',
  // 专门针对get请求的参数拼接
  params:{
    type:'pop',
    page:'1'
  }
}).then(res => {
  console.log(res);
})
```

### axios发送并发请求

之前讲到过，如果有多次网络请求，想要在多次网络请求都收到后在进行后续操作

使用promise可以完成这一要求：Promise.all

**==axios框架==**已经提供了发送并发请求并且都到达后进行相应处理的**==API==**

使用**==axios.all方法==**，在方法中传入两个（或多个）axios请求

然后在最后使用then()函数进行完成请求后的操作

**==返回的结果是一个数组==**

```javascript
axios.all([
    //第一次请求
  axios({
    url:'http://123.207.32.32:8000/home/multidata',
  }),
    //第二次请求
  axios({
    url:'http://123.207.32.32:8000/home/data',
    params:{
      type:'sell',
      page:'5'
    }
  })
]).then(result => {
  console.log(result);
})
```



上面返回的结果是一个数组，将网络请求的结果写在了一起

如果想在收到返回结果时**==将数组中的内容分开==**，可以在then中使用**==axios.spread方法==**



```javascript
axios.all([
  axios({
      //路径拼接
    baseURL: 'http://123.207.32.32:8000',
    url:'/home/multidata',
  }),
  axios({
      //路径拼接
    baseURL: 'http://123.207.32.32:8000',
    url:'/home/data',
    params:{
      type:'sell',
      page:'5'
    }
  })
]).then(axios.spread((res1,res2) => {
    console.log(res1);
    console.log(res2);
    }))

```



### 配置信息相关

在下面的示例中，我们的 baseURL、timeout是固定的

事实上，在开发中可能很多参数都是固定的

这个时候我们可以进行些抽取也可以利用 **==axios的全局配置==**

```javascript
axios.all([
  axios({
    baseURL: 'http://123.207.32.32:8000',
    timeout:5000,
    url:'/home/multidata',
  }),
  axios({
    baseURL: 'http://123.207.32.32:8000',
    timeout:5000,
    url:'/home/data',
    params:{
      type:'sell',
      page:'5'
    }
  })
]).then(axios.spread((res1,res2) => {
    console.log(res1);
    console.log(res2);
    }))

```

axios中可以用**==axios.defaults对象==**来定义全局配置

往axios.defaults中添加属性就可

```javascript
//添加全局变量
axios.defaults.baseURL='http://123.207.32.32:8000';
axios.defaults.timeout=5000;
axios.all([
  axios({
    url:'/home/multidata',
  }),
  axios({
    url:'/home/data',
    params:{
      type:'sell',
      page:'5'
    }
  })
]).then(axios.spread((res1,res2) => {
    console.log(res1);
    console.log(res2);
    }))

```

**==常见的全局配置选项==**

![1618150860112](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618150860112.png)



### axios实例

上面的例子使用的都是**全局的axios对应的配置进行网络请求**

但很多时候，不同的axios请求要求的配置不一样，只用同一个全局配置就不合适了

这时候需要**==创建多个axios实例==**

axios中有一个**==create方法==**可以创建实例

在每一个实例中传入属于这个实例统一的**==配置对象==**

每次使用这个实例时都传入其他具体的配置

具体操作如下：

```javascript
// 创建实例1
const instance1 = axios.create({
  baseURL:'http://123.207.32.32:8000',
  timeout: 5000
})
// 使用实例
instance1({
  url:'/home/multidata'
}).then(res => {
  console.log(res)
})
instance1({
  url:'/home/data',
  params:{
    type:'pop',
    page:1
  }
}).then(res => {
  console.log(res)
})
// 创建实例2
const instance2 = axios.create({
  baseURL:'http://222.111.33.33:8000',
  timeout: 1000
})
```



### axios模块封装

下面一个简单的例子，也就是我们以后进行网络请求的简陋雏形，只不过没有进行封装

App组件的进行网络请求

使用**==生命周期函数create()函数==**，在组件被创建出来出来，且data和methods初始化好了，在这个钩子函数中进行网络请求，并在请求成功后在**==then函数==**中将返回的数据赋值给data中的变量，即可完成一个简单的网络请求

![1618190943556](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618190943556.png)

来子组件中同样进行网络请求和相关操作

![1618191492101](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618191492101.png)

将子组件引用到父组件中

![1618190921311](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618190921311.png)



但是这样做有很大问题，以后组件多了，每个组件需要进行网络请求，每次都要引入axios框架

以后框架如果不再进行支持，项目重构的时候变得异常艰难

==**所以建议将axios进行一个封装**==



可以在src文件夹中创建**==network文件夹==**，在network中创建js文件：**==request.js文件==**

在request.js文件中**==导入axios模块==**

然后**==创建一个函数并导出==**，在这个**==函数里面创建axios实例==**，然后**==使用创建的实例进行真正的网络请求==**，通过函数参数传递过来的配置信息，来配置网络请求

![1618196376850](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618196376850.png)

为了在请求成功后进行进一步的操作，将请求结果回调回去，这里有几种方法，**==①、②不经常用，③是标准做法==**

**<font color='red'>①</font>**

上面这个图就是第一种方法，在函数中再传进来两个参数，**==两个参数是两个函数，分别是请求成功时执行的函数，和请求失败时执行的函数==**

此**==函数内容在App父组件的mian.js文件中进行定义==**，当然前提是要**==导入封装的request模块==**，这样才可以使用导出的request函数

![1618197181052](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618197181052.png)



**<font color='red'>②</font>**

或者函数值传过来一个config参数，组件调用函数的时候**==将执行成功与失败的函数放在config对象==**里面传进来就行

配置信息再单独放到对象的baseConfig属性中

在request.js文件中进行网络请求时，**函数中参数**是config，**网络请求的参数**是config.baseConfig

![image-20210412111816468](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210412111816468.png)

![image-20210412111602613](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210412111602613.png)



**<font color='red'>③</font>**

**==上面两个操作不太常用，真正标准做法，还是使用Promise来将请求结果返回给组件中==**（之前也使用过这个方式）

在request.js文件中，在导出的函数中，**==将网络请求的异步操作放在Promise对象中，通过函数的返回值返回==**

![image-20210412112554195](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210412112554195.png)

​	然后在父组件的main.js文件中导入模块并调用request函数，传入config参数，并且会有返回值，**==可以在request函数后面紧接着then()函数和catch()函数==**，

**<font color='red'>但教程中这种方法我觉得有个问题，instance中的then里面还有一个resolve，catch里面还有一个reject，这明显混乱了</font>**

![image-20210412113507559](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210412113507559.png)

**<font color='red'>改进</font>**：

发现一个问题，前面已经讲过了，通过axios.create创建的axios实例本身就支持Promise

前面使用实例时也用到了，也就是说instance实例对象一直作为一个函数来使用的，其返回值就是一个Promise对象

所以上面这种将网络请求放在Promise中太多此一举了

request函数直接返回instance就行了



![image-20210412114422867](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210412114422867.png)



在main.js文件中发送网络请求时，直接如下图：

![image-20210412114856311](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210412114856311.png)





### axios拦截器

有四个拦截器，**==请求成功、请求失败、响应成功、响应失败==**

拦截器就是在这些过程中做一个拦截，每个阶段可以做一些额外的操作

![image-20210412120028003](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210412120028003.png)



拦截器可以**==拦截全局的axios==**，直接**==axios.interceptors==**

但一般是使用**==实例的拦截器==**，上面创建的实例instance，**==instance.interceptors==**

**==语法：==**

​	**请求拦截**：**==实例.interceptors.request.use(config =>{},err =>{})==**

​	**响应拦截**：**==实例.interceptors.response.use(response =>{},err =>{})==**



#### **==请求拦截==**

其中箭头函数的这些变量名称都是可以自己命名的

第一个箭头函数表示**==请求成功的返回函数==**，**==默认参数==**就是一些详细的配置信息，所以 参数一般写config，打印config如下

第二个函数表示**==请求失败的返回函数==**，默认参数是**==错误信息==**

![image-20210412121310539](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210412121310539.png)

但是请求拦截器使用时，**==一定要记得将拦截到的config在通过函数返回出去==**，不然就没有响应，网络请求没有真正拿到结果

**==响应拦截==**获取的响应结果一直是**==undefined==**

**<font color='red'>所以拦截器第一个箭头函数一定记得返回config</font>**

下面图就是最基本的一个做法

![image-20210412121941826](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210412121941826.png)

下面是拦截器的基本具体应用场景：

config中的一些信息不符合服务器要求，要做一些修改

每次发送网络请求时，希望在界面显示一个请求图标，等响应成功时再将其隐藏起来

某些网络请求必须携带一些特殊的信息，比如登录（携带token令牌），如果没有携带token就跳转到登录页面



#### **==响应拦截==**

第一个箭头函数表示**==响应成功的返回函数==**，**==默认参数==**是相应的结果，所以 参数一般写response或result，下面时打印的结果。

![image-20210412123227336](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210412123227336.png)

但axios框架还会将一些其他的信息放进返回结果，所以使用时可以**==response/result.data==**来获取真正的数据

**==或者再请求拦截的时候return时，直接returnconfig.data==**，这样也可以



第二个函数表示**==请求失败的返回函数==**，默认参数是**==错误信息==**















































































































































































