### uniapp目录结构

![image-20210412214321077](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210412214321077.png)



### HTML标签和uniapp标签的对应关系

虽然不推荐使用HTML标签，但实际上如果开发者写了**==div==**等标签，在编译到非H5平台时也会被编译器转换为**==view标签==**，类似的还有**==span==**转**==text==**、**==a==**转**==navigator==**等

**==包括css里的元素选择器也会转==**。但为了管理方便、策略统一，新写代码时仍然建议使用view等组件。



### animate

Vue 官网引用的是 animate.css 3.5 版本!!!!

<font color='red'>**注意：3.5版本到3.7版本都可以使用，不过在3.7版本及以上才有faster、fast、slow、slower等等调节动画速度的样式**</font>

如果你直接采用

**npm install animate.css ;**


在引入：

```javascript
import animated from "animate.css" ;

Vue.use(animated);
```

结果就是没有作用!!!
原因：两者版本兼容性问题导致动画不起作用！！！

处理方法：
就是安装对应低版本的动画插件，比如官网引入的3.x的animate.css

**==npm install animate.css@3.5.1 --save==**

或者

yarn add animate.css@3.5.1 

Vue文件中全局引入：

```javascript
import animated from "animate.css"
Vue.use(animated)
```



 番外：（动画库的css类名展示）

```javascript
fade: {
        title: '淡入淡出',
        fadeIn: '淡入',
        fadeInDown: '向下淡入',
        fadeInDownBig: '向下快速淡入',
        fadeInLeft: '向右淡入',
        fadeInLeftBig: '向右快速淡入',
        fadeInRight: '向左淡入',
        fadeInRightBig: '向左快速淡入',
        fadeInUp: '向上淡入',
        fadeInUpBig: '向上快速淡入',
        fadeOut: '淡出',
        fadeOutDown: '向下淡出',
        fadeOutDownBig: '向下快速淡出',
        fadeOutLeft: '向左淡出',
        fadeOutLeftBig: '向左快速淡出',
        adeOutRight: '向右淡出',
        fadeOutRightBig: '向右快速淡出',
        fadeOutUp: '向上淡出',
        fadeOutUpBig: '向上快速淡出'
      },
      bounce: {
        title: '弹跳类',
        bounceIn: '弹跳进入',
        bounceInDown: '向下弹跳进入',
        bounceInLeft: '向右弹跳进入',
        bounceInRight: '向左弹跳进入',
        bounceInUp: '向上弹跳进入',
        bounceOut: '弹跳退出',
        bounceOutDown: '向下弹跳退出',
        bounceOutLeft: '向左弹跳退出',
        bounceOutRight: '向右弹跳退出',
        bounceOutUp: '向上弹跳退出'
      },
      zoom: {
        title: '缩放类',
        zoomIn: '放大进入',
        zoomInDown: '向下放大进入',
        zoomInLeft: '向右放大进入',
        zoomInRight: '向左放大进入',
        zoomInUp: '向上放大进入',
        zoomOut: '缩小退出',
        zoomOutDown: '向下缩小退出',
        zoomOutLeft: '向左缩小退出',
        zoomOutRight: '向右缩小退出',
        zoomOutUp: '向上缩小退出'
      },
      rotate: {
        title: '旋转类',
        rotateIn: '顺时针旋转进入',
        rotateInDownLeft: '从左往下旋入',
        rotateInDownRight: '从右往下旋入',
        rotateInUpLeft: '从左往上旋入',
        rotateInUpRight: '从右往上旋入',
        rotateOut: '顺时针旋转退出',
        rotateOutDownLeft: '向左下旋出',
        rotateOutDownRight: '向右下旋出',
        rotateOutUpLeft: '向左上旋出',
        rotateOutUpRight: '向右上旋出'
      },
      flip: {
        title: '翻转类',
        flipInX: '水平翻转进入',
        flipInY: '垂直翻转进入',
        flipOutX: '水平翻转退出',
        flipOutY: '垂直翻转退出'
      },
      strong: {
        title: '强调类',
        bounce: '弹跳',
        flash: '闪烁',
        pulse: '脉冲',
        rubberBand: '橡皮筋',
        shake: '左右弱晃动',
        swing: '上下摆动',
        tada: '缩放摆动',
        wobble: '左右强晃动',
        jello: '拉伸抖动'
      }
```





v-for、v-if使用时标签要求

==**循环v-for放在block标签中**==

==**判断v-if放在template标签中**==



### scroll-view滚动不了错误原因

scroll-view标签的导航滚动条

如果滚动不了，可能是因为没有为滚动条加下边线



### onBackPress函数

onBackPress函数return非true以外的值都会执行默认的返回行为，只有return true才不会执行返回事件，所以在执行自定义事件时一定要返回true





### 语法提示问题

遇到没有语法提示的问题，关闭代码页面，重新打开













### user-space 动画效果设置有问题

v-for循环和animate.css一起用有问题









### 数据库报错

ERROR 1045 (28000): Access denied for user root@localhost (using password: YES怎么回事)

原因是是端口占用问题

解决方法：

开始-运行-cmd， 输入 netstat -ano， 看第一列，后面的就是端口,找到3306 ,记住对应的PID!! 

然后打开任务管理器，打开详细信息，找到刚才的PID的进程，查看是什么程序占用了端口，把它关闭!!!





### navicat for mysql和UPUPWANK里边的mysql数据库只能开一个问题

是两个端口冲突问题，将upupw ank的数据库端口改成别的，不要两个都是3306



### request:fail abort statusCode:-1 Chain vaildation faild

在uni.request中加上sslVerify: false，设定不验证ssl证书，有时候手机会报错request:fail abort statusCode:-1 Chain vaildation faild，加上这个跳过验证ssl，就可以请求到服务器了



# 项目



。



。

。

。。

。

。

。

。

。



。

### 权限验证的操作

**评论、关注、顶踩**之前需要进行检查是否登录，需要进行权限验证，将权限验证checkAuth方法写到vue的原型中，直接在列表这个组件中执行判断权限验证的方法

如果通过vuex中的状态发现没有登录，就用uni-ap中跳转页面的接口进行跳转，跳转到登录页面

**发布帖子**也需要权限验证，这个和上面的有稍微区别，上面那几步操作是不需要页面跳转的，发布帖子本来就需要页面跳转的，这里为了省略几个步骤（算是代码的优化），直接在vue原型中写了一个navigateTo方法，这个方法本身就可以实现跳转，将方法的参数 做为跳转的配置项，这样页面跳转就不用uni.navigateTo，直接用vue里的navigateTo方法就行

### 权限验证的跳转



## 前后端交互

### 封装请求模块

封装request.js模块，为了方便数据请求，将相关操作进行了封装

并将模块挂载到main.js上

数据请求其实使用的是uni-app框架自带的uni.request接口

到具体的组件中应用时，官网提供了三种方式，我们用到了两种，一种返回的是一个promise对象，一种利用的是async和await

#### 请求错误处理

官方规定，要是uni.request参数里面有success和fail成功和失败的回调，返回的就不是一个promise对象，我们仍然想要返回一个promise，但是又需要success和fail，所以我们自己return一个promise

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210529110148966.png" alt="image-20210529110148966" style="zoom:67%;" />



应用地方：**获取分类**、**获取不同分类下的数据**

![image-20210528153744163](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210528153744163.png)

### 首页交互实现

#### 获取顶部导航条分类

从数据库获取分类数据，然后写到data中的数据中

#### 获取不同分类下的数据

顶部分类导航条需要从服务器进行数据请求

将返回的数据进行一下转化（服务器和前端定义的数据，在格式名称上等有一些问题）

然后设定默认显示第一个分类下的数据

然后写一个**获取指定分类数据的函数**，也是利用上面定义的请求模块进行数据请求

遍历循环请求到的分类列表，在切换顶部选项卡的回调函数中进行不同分类下的内容请求，利用的就是上面定义的**获取指定分类数据的函数**

一个分类里面的数据是分好几页的，上拉加载才会显示后面页数的内容

所以在第一页加载时，数据就正常进行请求，后面几页应当在原来的内容上进行追加，而不是更新掉

==当我们在几个分类之间切换时，会有重复加载的现象，推荐分类已经加载完，结果再次打开，还要加载一遍，==

==这时候就可以进行优化==，我们每个分类每页加载完后，page就会自增1，也就是只要是加载过page就不会是1，利用这个判断还需不需要再次进行加载

#### 上拉加载更多

上拉加载更多功能仍然放在了**获取指定分类数据的函数**中，上拉就调用这个函数，

函数中判断是否是第一页，是第一页的话，就更新，不是的话就在后面进行拼接，而不是单纯的更新

我们规定的一页有10条内容，如果请求来的数据列表少于十条，代表没有更多了，最下面就显示没有更多了，不然显示上拉加载更多

==上拉加载更多这里也有防抖的优化==

#### 首次加载分类列表显示加载中

之前在没有列表内容的地方，导入了**没有更多的组件**，现在在前面再加上一个**加载中**

不然每次加载的时候，都显示没有更多了，然后才显示内容

大概思路还是判断page是不是等于1，不等于1的话就显示

![image-20210528194048257](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210528194048257.png)

因为列表是v-for渲染出来的，是根据数据实时进行更新的

所以会有一个效果，当数据进行加载的时候，第一个v-if是false的，这时候执行下面的加载中的template，当数据加载完成后，v-for也会实时更新列表，这时候第一个v-for就会为true，就会加载出来列表内容了



#### 人性化时间转换

在common-list组件中添加一个过滤器

将时间戳转化为人性化时间，利用的是之前的一个函数库 将时间戳转化为人性化时间，利用的是之前的一个函数库 



### 文章详情交互页实现

在common-list组件中，在点击事件的回调函数中，会打开detail.vue页面

在进入详情页的方法中已经将帖子的数据通过JSON压缩，并添加在url后面，通过这种方式将参数传过来了

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210529111718963.png" alt="image-20210529111718963" style="zoom:67%;" />

在detail.vue页面中进行前后端交互，同样使用request.js数据请求模块，因为有一些内容还需要请求一下，从上一个页面中传过来的参数当中是没有的

### 评论功能实现



### 分享功能实现

利用uni.share的接口进行分享

uni.share()方法的参数是一些分享时的配置，官网有介绍

在详情页使用$ref来访问子组件的属性，给子组件的属性进行赋值

分享组件中的一些参数、内容通过父组件进行设置后，就可以用来转发了



### 搜索文章功能实现

在search.vue组件中请求后端搜索文章详情api

请求过来的数据类型跟首页数据请求非常相似

同样是将数据放到一个列表，利用之前写好的一个组件common-list，然后循环遍历加载

同时引入上拉加载的组件，完成上拉加载功能



### 话题专题页交互实现

通过数据请求获取热门分类、话题、轮播图，然后将数据进行整合呈现到页面上（一般整合这些数据可以使用自定义的工具函数、也可以使用map函数）

### 话题分类交互实现

实现的很多步骤都跟主页一模一样

从服务器获取分类

根据分类从服务器获取对应列表内容

之前从返回的promise对象后面只追加过一个请求成功后的then，现在为主页和话题页添加一个catch请求失败的操作，如果请求失败，还将page减去1，不然请求失败后，page仍然自动增加了1

默认呈现第一个分类的内容

上拉加载

实现避免重复加载

滑动顶部导航条切换分类时加载对应分类下的内容

跟主页一样添加一个加载中的效果

点击动态页的话题分类标签跳转到话题分类列表



### 话题详情交互实现



### 搜索话题交互实现

仍然在search页面进行搜索

通过不同类型的type：帖子、话题、用户，将type作为参数调用后端不同的api

根据返回的不同类型的数据整理格式

然后进行展示

### 账号邮箱手机登录功能实现

#### 登录界面

先编写一个未登录的个人界面的样式

引入第三方登录的组件

利用vuex中的状态，判断是否是登录的状态

如果是登录则显示登录的样式

如果没有登陆则显示第三方登录的样式

#### 登录操作

##### 手机邮箱昵称登录

在login.vue组件中，进行登录的请求

使用post请求，向服务端发送登录信息

根据status的布尔值，来判断是手机号登录还是账号密码登录

true为手机号邮箱登录，false为账号密码登录，默认false

然后进行post请求

在vuex的index.js中的state中存储用户的一些状态值，存储到一个state对象里面

发送一个用户请求信息，返回来的用户内容有以下：

​		例子：

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210530150811432.png" alt="image-20210530150811432" style="zoom: 67%;" />

收到服务器发来的消息后，接下来需要进行以下操作：**<font color='red'>修改vuex的store、持久化存储、提示和跳转</font>**

**<font color='red'>修改vuex的store：、持久化存储</font>**

在store中的mutation中写登录的方法，

将登录状态设置为true

将拿到的个人信息的值赋值给state中的user对象

使用uni.setStorageSync方法将user对象添加到本地的缓存



**<font color='red'>提示和跳转</font>**

在login.vue组件中，使用uni.navigateBack({delta: 1});	返回一个页面，上一个页面就是my.vue个人信息页

然后uni.showToast提示登陆成功



为了防止重复登录，设定一个布尔值，默认为false











手机号登录还需要通过正则表达式来判断一下格式





##### 验证码登录

login.vue切换登录方式就修改了status，通过if判断status来判断登录方式，从而通过不同的api进行数据请求

##### 保持登录状态

现在这种情况下，app退回桌面后，再重新打开

登录状态就消失了

这时候我们可以在打开app的时候就初始化一下登录状态

在App.vue中commit调用store中的index.js中的mutation中的方法进行初始化登录状态

在这个方法中使用uni.getStorageSync来拿到缓存中的数据

并且将登录状态改为true



##### 渲染个人信息





#### 退出登录

在user-set.vue组件中的退出登录按钮绑定点击事件

在回调函数中先调用一个弹窗提示

然后在弹窗api的点击确认的回调函数中执行this.$store.commit('logout')，来调用vuex中mutations中的方法

在store的index.js文件中写logout退出登录方法

该方法中：**将登陆状态设为false，将个人信息的user对象置空，调用接口清除用户缓存**

然后调用接口自动返回上一页

调用接口提示退出成功



然后优化一下个人设置界面，在不登录的状态只能显示清除缓存和关于社区，其他的个人设置和退出登录按钮不显示

在user-set界面调用vuex，拿到state中的判断用户是否登录的变量

利用v-if来动态的渲染相关元素



#### 第三方登录

在other-login组件中编写**登录的方法**，参数是v-for中循环遍历得来的**item**

​			item是通过官方的uni.getProvider接口得到了服务商列表的每一项（即**具体的某个服务商**）

在登录方法中调用uni.login官方的api接口

官方文档中提供请求成功、失败、完成的回调函数，

在成功回调函数前先拿到某个服务商的id（上面定义的这个**item.id**就是**服务商的名字**）作为对应属性的值。在成功的回调函数中，参数是XXXXX

在这个成功回调函数中调用获取用户信息的api，将请求得到的信息进行整理保存在一个对象中，然后使用这些信息进行用户登录后的初始化（利用一个自定义函数）



### 修改账号安全页面



### 绑定手机功能实现

先优化一下我们的数据请求过程

在vuex中的state增添token，默认为false

> （后面提到的有两个token，一个是state中的token：是个布尔值，用来记录请求中有没有token值。另一个是数据请求过来的对象中的token值：就是我们常说的token值。。。。。。。进行post数据请求的时候，可以传过来一个token:true/false，request.js文件中来判断需不需要进行用户token的判断）

在mutation中登录、初始化登录状态的方法中添加获取token的步骤，在退出登录的方法中将token重新修改为false

在request.js中引入vuex来读取state中的token，请求的时候判断有没有token，没有的话就登录失败

然后在user.phone 中进行post请求，调用绑定手机的api，然后通过commit调用store中的方法修改电话号码

然后在user-safe.vue中进行动态的修改手机号绑定状态，绑定了就改成绑定的手机号，没绑定就显示没绑定，这也需要引入vuex

并且将相关的用户配置写进缓存里（手机、邮箱、密码都会放进缓存中）

邮箱设置、和密码设置同理



### 登录密码的修改

如果还没有设置过密码，就不用显示旧密码，需要在user-passworld组件中引入vuex，通过state中的password有无来动态显示

然后调用修改密码的接口，进行post请求，后端进行密码的修改

### 绑定邮箱功能的实现

先调用vuex，通过state中user对象中的email，如果已经有了，就使绑定邮箱的元素变为不可用

然后调用api进行post请求，来修改邮箱

然后调用vuex中的mutation中的方法，进行state中用户数据的修改 



### 第三方登录

对于第三方登录，在后端有两个相关的表，一个就是user主表，里面有各种相关的信息，一个是user_bind表，里面是第三方登录的一些信息（比如第三方类型、头像、昵称等等）

通过第三方登录的用户在主表中的数据都是没有的，所以不能进行很多操作



通过api进行get请求获取绑定状态，然后将这个状态写进vuex中，通过不同第三方中的状态值，在界面中动态的显示绑定状态，如果已经绑定就显示第三方的昵称，没有就显示未绑定



未绑定的就进行绑定，绑定的过程跟第三方登录的过程很像：**调用官方接口进行第三方登录、调用官方接口得到第三方用户数据、将用户数据进行整理作为参数进行第三方账号绑定的后端api请求**



### 修改用户头像

在之前写的从本地选择用户头像的官方接口中，在成功的回调函数中，再调用往服务器上传文件的官方接口，在修改vuex中的状态和缓存的内容，这个请求过程可以再在request.js中封装一个upload方法

在user-userinfo文件中引入vuex，将界面的头像显示进行实时的变动





### 修改资料的功能实现

























### 聊天模块的封装

后端聊天功能是使用websocket来实现的

开启socket服务端分配客户端的id，客户端发起请求，将用户id和客户端id进行绑定，之后发给服务器用户id就可以了（其实这一步还有很多的功能，比如防止一些用户进行恶意连接，占用我们的资源，我们在一定的时间段进行检查，看用户id和客户端id有没有进行绑定，没有就断开连接，节约服务器的资源）

完成绑定就代表我们的客户端已经上线了



①首先在vuex的state中写一些状态变量

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210530202635774.png" alt="image-20210530202635774" style="zoom:80%;" />

​		**socket是否连接**，**有没有获取到socketTask对象**，**用户是否上线**

②然后在action中编写一些异步的方法

打开socket的方法：

​	先判断是否连接，避免重复连接

​	调用uni.connectSocket方法，方法两个参数：**websocket地址，complete请求结束的回调函数**

​	创建几个监听的回调函数，**监听开启，监听关闭，监听错误，监听接收信息**

```js
actions:{
    // 打开socket
    openSocket({ state,dispatch }){
        // 防止重复连接
        if(state.IsOpen) return
        // 连接
        state.SocketTask = uni.connectSocket({
            url: $C.websocketUrl,
            complete: ()=> {}
        });
        if (!state.SocketTask) return;
        // 监听开启
        state.SocketTask.onOpen(()=>{
            // 将连接状态设为已连接
            console.log('将连接状态设为已连接');
            state.IsOpen = true
        })
        // 监听关闭
        state.SocketTask.onClose(()=>{
            console.log('连接已关闭');
            state.IsOpen = false;
            state.SocketTask = false;
            // 清空会话列表
            // 更新未读数提示
        })
        // 监听错误
        state.SocketTask.onError(()=>{
            console.log('连接错误');
            state.IsOpen = false;
            state.SocketTask = false;
        })
        // 监听接收信息
        state.SocketTask.onMessage((e)=>{
            console.log('接收消息',e);
        })
    },
}
```

③在App.vue中通过dispatch来调用action中的方法，来开启socket

④将用户id和客户端id进行绑定，通过state.SocketTask.onMessage接收到的消息（一般都是字符串）转成JSON对象

































































































