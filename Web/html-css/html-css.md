### 文档声明

![1616120238876](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616120238876.png)





### 字符实体

语法：&实体的名字

&nbsp：一个空格

&gt：大于号

&lt：小于号

&copy：版权符号

等等还有很多字符实体



### meta

表示网页的元数据

**==meta有哪些属性==**

charset：指定网页的字符集

name：指定的数据的名称

content：指定的数据的内容（**一般content和name配合使用，一个表示元数据的名字，一个表示元素数据的内容**）



**==有哪些元数据==**：

keywords：表示**网页的关键字**，便于搜索一宁搜索时使用，可以使用多个关键字，关键字放在content中，关键字之间用**逗号隔开**

![1616122222285](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616122222285.png)

description：用于指定网站的描述，描述的内容会出现在搜索引擎的结果中

http-equiv：用于页面的重定向，content中两个参数，用分号隔开，第一个写重定向的延迟事件（秒），第二个是一个重定向地址



### 标签



h标签

![1616122721507](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616122721507.png)

hgroup标签

![1616122869463](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616122869463.png)



em标签

​	表示语音语调的一个加重

![1616122998006](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616122998006.png)

​	真这个字体会变斜 

strong标签

​	表示强调重要的内容



blockqoute标签

​	表示长引用，是块元素，该行会缩进

![1616123247275](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616123247275.png)



q标签

​	表示短引用，是行内元素，该段文字会用双引号引起来

![1616123347047](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616123347047.png)

br标签 

​	自结束标签，用来换行

p标签

​	在p标签中的内容就属于一个段落

span标签

​	**==行内元素==**，没有任何语义，一般用于网页中选中文字，行内元素现在最主要使用的就是行内元素





**块级元素**

div标签

​	没有语义，表示一个区块，目前还是我们的一个主要的布局元素，div可以代替下面所讲的任何标签，只不过div有点违反了h5的思想：**用html标签来确定各个内容的语义**



h5新增header、main、footer、nav、aside、article、section

header标签

​	网页的头部

main标签

​	网页的主体部分，一个页面一个main

footer

​	网页的底部

nav标签

​	网页的导航

aside标签

​	和主题相关的其他部分（侧边栏）

article标签

​	表示一个独立的文章

section标签

​	表示一个独立的区块，上面的标签都不能使用时可以用section

### 块和行内元素

网页中通过块元素进行页面布局，行内元素一般用来包裹文字

一般情况不会往行内元素中放块元素，块元素中基本上什么都能放

 p元素中不能放任何块元素



浏览器在解析网页时，会自动对网页中不符含规范的内容进行修正，并不会报错：

​	标签写在了根元素的外部

​	p元素中套了块元素

​	根元素中出现了 head和abody以外的子元素

​	.......

### id属性

id属性（唯一不重复的属性）

每一个标签都可以添加一个id属性

id属性就是元素的唯一标识，同一个页面中不能出现重复的id属性

### 列表

#### 有序列表

使用**ul标签**创建有序列表

在ul中使用li标签来创建列表项

![1616143579357](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616143579357.png)

![1616143666615](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616143666615.png)

#### 无序列表

使用**ol标签**创建有序列表

在ol中使用**li标签**来创建列表项

![1616143653987](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616143653987.png)

![1616143675563](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616143675563.png)



#### 定义列表

使用**dl标签**创建有序列表

在dl中使用**dt标签**来表示定义的内容

使用**dd标签**来对内容进行解释说明

![1616143913599](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616143913599.png)

![1616143919648](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616143919648.png)





列表之间可以互相嵌套

![1616143983138](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616143983138.png)![1616143988814](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616143988814.png)

### 超连接

**a标签**

​	超链接也是一个**行内元素**，特殊的是，**a标签中可以放出它自身以外的任何的标签**，包括**块元素**如div



#### a标签的属性

超链接可以让我们跳转到其他页面，**==或者当前页面的其他位置==**



##### href属性

来指明跳转的地址：

或者将href的值设置为**==#==**，这样超链接就不会发生跳转，而是直接**回到顶部**

可以跳转到页面的**指定位置**，只需将href属性设置**==#目标元素的id属性值==**

![1616204683706](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616204683706.png)



未设置的超链接href属性可以用**#**作为占位符

href属性也可以用==**javascript:;**==来作为占位符，这个是真正的点击什么也不会发生

![1616204911627](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616204911627.png)

##### target属性

用来指明超连接打开的位置

可选值：

​		_self：默认值，默认在当前页面中打开超连接

​		_blank ：在一个新的页面中打开超链接

#### 相对路径

![1616145139977](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616145139977.png)





### img标签

图片标签用于向当前页面中引入一个外部图片

img标签是一个自结東标签

img这种元素属于**替换元素**（块和行内元素之间，具有两种元素的特点

**src属性**：指定的是外部图片的路径（路径规则和超链接是一样的

**alt属性**：图片的描述，这个描述默认情况下不会显示，**有些浏览器会图片无法加载时显示**。  **搜索引擎**会根据alt中的内容来识别图片，如果不写alt属性则图片不会被搜索引擎所识别

**width属性**：图片的宽度（单位是像素）

**height属性**：图片的高度

**宽度和高度中如果只修改了一个，则另一个会等比例缩放**

**注意：**

一般情况在pc端，不建议修改图片的大小，需要多大的图片就裁多大

但是在移动端，经常需要对图片进行缩放（大图缩小）





#### 图片格式

![1616207440331](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616207440331.png)



### 内联框架

**==iframe标签==**

内联框架，用于向当前页面中引入一个其他页面

src：指定要引入的网页的路径

frameborder：指定内联框架的边框，1：有框架，0：没有框架

![1616208676709](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616208676709.png)



### 音视频

#### audio标签

用来向页面中引入一个外部的音频文件的

音视频文件引入时，默认情况下不允许用户自己控制播放停止

属性：

​	**src**：音频文件的地址

​	**controls**：加上controls允许用户控制播放（controls和autoplay都是直接加上就行，**==不用赋值==**）

​	**autoplay**：加上autoplay，音频文件自动播放

​	如果设置了 autoplay则音乐在打开页面时会自动播放

​	但是目前来讲大部分浏览器都不会自动对音乐进行播放

​	**loop**：音乐是否循环播放

![1616209754383](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616209754383.png)



**source标签**

audio标签中可以嵌套一个source标签来指定外部文件路径

使用source标签的话有**两个好处**：

**<font color='orange'>①</font>**里面可以放置多个source标签，可以放置多个音频文件，浏览器根据能否播放，会从上到下播放一个，解决个别浏览器对音频文件的兼容问题

**<font color='orange'>②</font>**audio可以写一些文字，当音频文件加载不出来，浏览器自动修改错误，将audio标签去掉，文字才会显示，这样可以作为错误提示。



**embed标签**

老版本的ie**音视频标签**，**视频音频都可以使用，**不做推荐

#### video标签

属性和audio标签基本一样

也可以使用source标签完成兼容问题

![1616210895160](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616210895160.png)





**==ps：==**

一般视频文件不会放到本地服务器，src不会相对路径，这对带宽要求很大，成本很高，所以一般租用**==第三方的服器==**，放到第三方的服务器上面进行托管

再或者放到腾讯、优酷等视频网站上面，然后==**复制相应视频的通用代码**==，此代码是一个**iframe内联框架**复制到video标签中去

![1616211121084](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616211121084.png)



效果这样：

![1616211201359](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616211201359.png)

此时使用的是腾讯的服务器，对自己的服务器不会产生压力



### CSS

css修改元素样式的方式

**==第一种==**：内联样式/行内样式

通过在标签内部修改style属性来设置元素的样式

![1616220741754](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616220741754.png)

问题：

​	使用内联样式，样式只能对一个标签生效

​	如果希望影响到多个元素必须在每一个元素中都复制一遍

​	样式发生改变的时候需要一个一个修改，不方便维护

​	**<font color='orange'>非常不推荐使用</font>**

**==第二种==**：内部样式表

将样式编写到**head标签中的 stylet标签**里

然后通过**CSS的选择器**来选中元素并为其设置各种样式

可以为多个标签设置样式，并且修改时只需要修改一处即可全部应

内部样式表更加方便对样式进行复用

内部样式表只能对一个网页起作用，不能跨页面进行复用	

![1616221664101](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616221664101.png)



**==第三种==**：外部样式表  最佳实践

可以海将样式表编写到一个外部的CSS文件

然后通过**==link标签==**来引入外部的CSS文件

意味着只要想使用这些样式的网页都可以对其进行引用

使样式可以在不同页面之间进行复用

![1616221687116](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616221687116.png)

#### CSS语法

CSS中的注释：/*  */

​	注释中的内容会自动被浏览器所忽略

CSS的基本语法：

**==选择器==**：

通过选择器可以选中页面中的指定元素

比如p的作用就是选中页面中所有的p元素

**==声明块==**：

通过声明块来指定要为元素设置的样式

声明是一个名值对结构

一个**样式名**对应一个**样式值**，名和值之间以==**：**==连接，以==**；**==结尾

##### 常用选择器

**==元素选择器==**

作用：根据**标签名**来选中指定的元素

语法：标签名{}

例子：p{}   h1{}   div{}

![1616223179520](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616223179520.png)





**==id选择器==**

作用：根据元素的**id属性值**选中一个元素

语法：#id属性值{}

例子：#box{}   #red{}

![1616223387642](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616223387642.png)





**==类选择器==**

作用：根据元素的**clsass属性值**选中一组元素

语法：.class属性值{}

![1616223571837](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616223571837.png)

class是一个标签的属性，和id类似，但是可以重复使用

通过class可以给元素分组

可以同时为**==一个元素分配多个class属性值==**，写到一个class中**==用空格隔开==**就行

![1616223784278](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616223784278.png)





**==通配选择器==**

作用：选中页面中的所有元素

语法：*{}

![1616223895494](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616223895494.png)

##### 复合选择器

**==交集选择器==**

作用：选中**同时复合多个条件的元素**

语法：选择器1选择器2选择器3选择器n{}

注意点：

交集选择器中如果有**元素选择器**，==必须使用元素选择器开头==

![1616224236575](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616224236575.png)

**==分组选择器（并集选择器）==**

作用：**同时选择多个选择器对应的元素**

语法：选择器1,选择器2,选择器3,选择器n{}

注意点：并集选择器可以跟交集选择器一块用

如：**==#b1,.p1,h1,span,div,.red{}==**

![1616224302910](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616224302910.png)



##### 关系选择器

![1616224556039](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616224556039.png)

**==子元素选择器==**

作用：选中指定父元素的**指定子元素**，子元素都符合就选中多个元素

语法：**父元素>子元素**

![1616224767498](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616224767498.png)

可以与之前的**复合选择器配合使用**，**可以使用多个>**

![1616224931487](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616224931487.png)





**==后代元素选择器==**

作用：选中指定元素内的**指定后代元素**，后代符合的有多个就选择多个

语法：**祖先 后代**（中间隔着空格）

![1616224872541](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616224872541.png)

同样也可以多个空格连起来或者与其他配合使用

​	

**==选择下一个兄弟==**

语法：前一个+下一个

![1616225273046](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616225273046.png)

**这两个兄弟元素必须==紧挨着==，中间不能隔着任何标签**





**==选择下面所有兄弟==**

语法：兄 ~ 弟

![1616225280133](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616225280133.png)



##### 属性选择器

![1616225831641](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616225831641.png)



![1616225849532](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616225849532.png)

此例前面有p，是一个复合选择器，也可以不加



##### 伪类选择器

**==伪类==**（不存在的类，特殊的类）

伪类用来描述一个元素的**特殊状态**

​	比如：第一个子元素、被点击的元素、鼠标移入的元素

伪类一般情况下都是使**冒号**开头，==**冒号前面要有选择器，表示在这个选择器下，伪类这种情况**==

==:first-chid==   第一个子元素

==:last- child==   最后一个子元素

==:nth- child()==    选中第n个子元素

​	**括号里面写几，就是第几个子元素，写==n==的话，就代表从0到正无穷，==2n或even==就代表选中偶数位的元素，==2n+1或odd==就代表选中奇数的元素**

![1616227942539](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616227942539.png)

以上这些伪类都是根据**所有的子元素进行排序**，==意思是ul元素名为li的子元素，并且它在所有的子元素中处于第一个位置，就选择它，不是处于第一个位置就不符合要求==

如下并没有效果

![1616228260597](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616228260597.png)

![1616228323872](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616228323872.png)

![1616228269923](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616228269923.png)

相对应有如下几个伪类：

==**:first-of-type**==

==**:last-of-type**==

==**:nth-of-type**==

这几个伪类的功能和上述的类似，不通点是他们是**==在同类型元素中进行排序==**,  如下就没有上面那种问题

![1616228379182](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616228379182.png)

![1616228385544](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616228385544.png)



**==:not()==**   否定伪类

括号里面放伪类

**将符合条件的伪类从前面的选择器中去除**

![1616228938128](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616228938128.png)

![1616228944975](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616228944975.png)



![1616229040237](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616229040237.png)

![1616229046769](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616229046769.png)

**==补充：==**

**==:focus==**获取焦点伪类（比如点击一下文本输入框，文本框就获取了焦点）





###### a元素的伪类

**==链接伪类要想所有伪类均起效果，需要按照一定顺序进行排列：:link>:visited>:hover>:active==**

**==:link==**（链接独有的伪类）只有附上href链接时才生效

用来表示没访问过的链接（所有正常的链接）

![1616232115041](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616232115041.png)

后面这几个伪类只是在link上面做修改，并不是完全替换样式，，比如字体大小没有在:visited或:hover中修改，那么字体大小就不用变化

**==:visited==**（链接独有的伪类）

**用来表示访问过的链接**

由于隐私的原因，这个visited伪类只能改变连接的颜色

![1616232141664](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616232141664.png)

**==:hover==**（**所有元素都有的伪类**）

用来表示<font color='orange'>**鼠标移入**</font>的状态

![1616232150249](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616232150249.png)

例子：

![1616424297419](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616424297419.png)

表示鼠标移入location父元素时，设置子元素的值

**==:active==**（所有元素都有的伪类）

用来表示<font color='orange'>**鼠标点击**</font>的状态

![1616232155516](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616232155516.png)





##### 伪元素选择器

伪元素，表示页面中一些特殊的并不真实的存在的元素（特殊的位置）

伪元素使用**两个冒号::**来开头

**==::first- letter==**表示第一个字母

![1616232946215](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616232946215.png)

**==::first-line==**表示第一行

![1616232952926](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616232952926.png)

**==::selection==**表示选中的内容

![1616232959594](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616232959594.png)

**==::before==**元素的开始，元素内容的最前面，并不是指元素内容本身

**==::after==**元素的最后 

**before和after**必须结合==content属性==来使用，before和after区域用鼠标是选不中的

例子：

![1616233019189](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616233019189.png)

![1616233028886](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616233028886.png)



例子：

![1616310513711](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616310513711.png)

![1616310527917](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616310527917.png)



**ps：p标签，该段文字会用双引号引起来，这个双引号就是用before和after来设置的**





#### 样式的继承

我们为一个元素设置的样式同时也会应用到它的后代元素上

继承是发生在祖先和后代之间的

继承的设计是为了方便我们的开发，利用继承我们可以将一些通用的样式统一设置到共同的祖先元素上

==注意：**并不是所有的样式都会被继承**==

==**如背景、布局相关等的这些样式都不会被继承**==



#### ==选择器的权重==

样式的冲突：当我们通过不同的选择器，选中相同的元素，并且为相同的样式设置不同的值时，此时就发生了样式的冲突

发生样式冲突时，应用哪个样式由选择器的权重（优先级）决定

选择器的权重：

==​	**内联样式				1000**==

==**​	id选择器				100**==

==**​	类和伪类选择器		10**==

==**​	元素选择器			1**==

==​	**通配选择器			0**==

==**​	继承的样式			没有优先级**==



比较优先级时，需要将所有的选择器的优先级进行**==相加计算==**，最后优先级越高，则越优先显示（**==分组选择器是单独计算的==**）

**==但是选择器的累加不会超过其最大的数量级==**，比如，几个类选择器再高也不会超过id选择器

如如果**优先级计算后相同**，此时则优先使用**靠下的样式**

可以在某一个样式的后边添加**==!important==**,则此时该样式会获取到**最高的优先级**，基至**超过内联样式**

![1616239732925](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616239732925.png)

注意：在开发中这个玩意一定要慎用,**==能不用就不用==**



#### 单位

##### 长度单位

**==像素==**

px

屏幕（显示器）实际上是由一个个的小点点构成的

不同屏幕的像素大小是不同的，像素越小的屏幕显示的效果越清晰

所以同样的200px，在不同的设备下显示效果不一样



**==百分比==**

可以将属性值设置为**==相对于其父元素属性的百分比==**

设置百分比可以使子元素**==跟随父元素的改变而改变==**



**==em==**

em是相**对于==元素的字体大小==来计算的**，**==em是相对于它的父级的font-size的倍数==**，**==几em就是几倍的font-size的字体大小==**

**==1em =1font-size==**

**em会根据字体大小的改变而改变**

**<font color='orange'>浏览器默认字体大小为16px</font>**

如下图，这是font-size字体大小设置的就为30px，换算后，长宽就为300px了

![1616240721966](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616240721966.png)

**==rem==**

rem用法和em差不多，**==是相对于根元素（HTML）的字体大小来计算的==**

根元素字体大小默认的是**==16px==**

###### px 与 rem 的选择？

对于只需要适配少部分手机设备，且分辨率对页面影响不大的，**==使用px即可 。==**

对于需要适配各种移动设备，**==使用rem==**，例如只需要适配iPhone和iPad等分辨率差别比较挺大的设备。

###### rpx

**==rpx （ responsive pixel）响应单位==**

rpx是微信小程序独有的、解决屏幕自适应的尺寸单位

可以根据屏幕宽度进行自适应，不论大小屏幕，规定屏幕宽为750rpx

通过 rpx 设置元素和字体的大小，小程序在不同尺寸的屏幕下，可以实现自动适配



==rpx 和 px之间的换算==

在普通网页开发中，最常用的像素单位是px

在小程序开发中，推荐使用rpx这种响应式的像素单位进行开发

以 iPhone6 为例，iPhone6 的屏幕宽度为 375px，共有 750个物理像素，则 750rpx = 375px = 750 物理像素

得出公式：1 rpx = 0.5 px = 1 物理像素

举个例子：在iPhone6上，如果要绘制一个宽为100px，高为30px的盒子，换算成rpx单位，宽高分别为200rpx 和 60rpx



**==rpx 和 iPhone 设计稿的关系==**

官方建议：开发微信小程序时，设计师可以以iPhone6 作为视觉稿的标准，如果要根据iPhone6的设计稿，绘制小程序的页面，可以

直接把单位 px 替换成 rpx 。例如：假设iPhone6设计稿上，要绘制一个宽高为 200px 的盒子，换算为 rpx为200rpx



**==以iPhone6为设计稿标准，单位 px 直接替换成 rpx的原因==**

设计师在出设计稿的时候，出的都是二倍图，也就是说如果在这个设计稿上有一个宽高为200px的盒子，那么它最终画到页面上实际

上是一个宽高为100px的盒子，那么再换算成rpx需要乘以2，就又变成了200rpx，跟设计稿上的数字是一样的，所以我们可以保持数

字不变，直接将单位 px 替换成 rpx


##### 颜色单位

![1616241393061](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616241393061.png)

![1616241400259](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616241400259.png)

hsl值用的不多

![1616241787640](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616241787640.png)

![1616241779995](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616241779995.png)



文档流

![1616242451662](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616242451662.png)



#### 盒子模型box model

![1616245331161](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616245331161.png)

内容区（ content）

内边距（ padding）

边框（ border）

外边距（ margin）

共盒子的**==可见框的大小==**，由**==内容区、内边距、边框==**共同决定，所以在计算盒子大小时，需要将这三个区域加到一起计算

实际占地大小还要考虑外边距

##### 内容区（ content）

**元素中的所有的子元素和文本内容都在内容区中排列**

内容区的大小由 width和 height两个属性来设置

​	**width**设置内容区的宽度

​	**height**设置内容区的高度



##### 边框（ border）

边框属于**盒子边**，边框里边属于盒子内部，出了边框都是盒子的外部，**边框的大小会影响到整个盒子的大小**

要设置边框，==需要**至少**设置以下三个样式：**border- width，border- collor，border- style**==，**<font color='orange'>缺一不可</font>**



==边框的宽度 **border- width**==

​	**只有这一个值不写的话也可以**，宽度也是存在的，**默认值为3px**

​	可以最多用四个值指定四个方向的宽度，值于值之间用**空格隔开**

![1616243669946](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616243669946.png)

![1616243750161](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616243750161.png)

除了用border-width，可以用四个属性代替它，分别是==**border-\*\**-width**==，\*\*\*代表的是**top、right、bottom、left**

这四个代替值同样适用于边框颜色和边框样式



==边框的颜色 **border- collor**==

​	也可以不写，不写的话就会**==默认使用color==**的值，color代表的是前景色，并不只是代表字体颜色 

==边框的样式 **border- style**==

​	solid 实线

​	dotted 点状虚线

​	dashed 虚线

​	double 双线

**边框样式不设置就默认为none，就没有边框了**

**==border属性==**：**<font color='orange'>简写border的各种样式</font>**，就不用写三个了，一个属性三个值，**且没有顺序**

![1616245193367](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616245193367.png)

同样为了方便设置四个边框，有四个分开写的属性：

![1616245251159](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616245251159.png)





##### 内边距（ padding）

内容区和边框之间的距离

内边距的设置会影响到盒子的大小

有四个方向的内边距属性：

​	**padding-top**

**​	padding-right**

**​	padding-bottom**

**​	padding-left**

![1616245653525](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616245653525.png)

**==简写属性：padding==**

![1616245785144](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616245785144.png)



##### 外边距（ margin）

![1616246302378](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616246302378.png)





##### 水平方向的布局

![1616246711400](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616246711400.png)

![1616246980697](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616246980697.png)





一下这七个属性决定子元素在父元素水平方向的位置

**margin-left**

**border-left**

**padding-left**

**width**

**padding-right**

**border-right**

**margin-right**

**<font color='orange'>①</font>**其中**==width、margin-left、margin-right==**可以设定为auto，谁是auto就调整谁

**<font color='orange'>②</font>** **==如果都不设置auto的话，width会首先默认为auto，能调整为最大就调整为最大，其他的先默认为0==**

**==如果都设置为auto的话，width会首先能调整为最大就调整为最大，其他的先默认为0==**

**<font color='orange'>③</font>**如果都设置了具体的值的话，**==margin-right==**无论设置成多少，**==都会自动被修改成符合等式的值==**，哪怕margin-left 和width的值超过了父元素，此时margin-right强项修改为**负数**（但看上去子元素是将父元素顶出来了）。所以margin-right的值设置的是没有意义的

**<font color='orange'>④</font>** **==两个外边距设置为auto,宽度固定值，则会将外边距设置为相同的值==**

![1616248198322](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616248198322.png)



有时会利用上面第④条的特点来**让一个元素在其父元素居中**，**width设置为一个具体的值，左右margin设置为auto就行**

![1616248871595](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616248871595.png)



##### 垂直方向的布局

父元素不设置大小的话，默认会被子元素撑开

父元素最下面的子元素的**==margin-bottom 不会将父元素的大小撑开==**

竖直方向和水平方向如果子元素的大小超过了父元素，则子元素会从父元素中溢出



**==overflow属性==**

使用 overflow属性来设置父元素如何处理溢出的子元素

该属性有==三个可选值==：

​	**visible**：默认值子元素会从父元素中溢出，**在父元素外部的位置显示**

​	**hidden**：溢出内容将会**被裁剪**不会显示

​	**scroll**：**生成==两个==滚动条**，通过滚动条来查看完整的内容

​	**auto**：根据水平和竖直方向需要自动生成滚动条，不需要就不用生成



==**overflow-x**==、==**overflow-y**==这两个属性可以用上述可选值单独处理水平竖直方向的滚动条

*<font color='orange'>ps:hidden和 auto可以来开启元素的BFC</font>*

##### 外边距的折叠

相邻的垂直方向的外边距的会发生折叠现象，指margin-bottom和margin-top这两个属性



**兄弟元素**

​	两个都是正值

![1616296427585](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616296427585.png)

​	两个值中存在负值

![1616296433434](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616296433434.png)

**父元素**

![1616296907011](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616296907011.png)

​	==第一行的意思是，子元素在父元素中设置margin-top 后，调整margin-top的值，相当于也在调整父元素的margin-top，这叫做传递，子元素和父元素margin-top成了一个==

##### 行内元素的盒模型

行内元素**不支持设置宽度width和高度height**

行内元素可以设置 padding,但是垂直方向 padding,不会影响页面的布局

行内元素可以设置 border,垂直方向的 border不会影响页面的布局

行内元素可以设置 margin,垂直方向的 margin/不会影响布局，水平方向的margin就是简单地相加





**==display属性==**用来设置元素显示的类型

可选值：

​	**inline**：将元素设置为**行内元素**

​	**block**：将元素设置为**块元素**

​	**inline- block**：将元素设置为**行内块元素**。既可以设置宽度和高度又不会独占一行

​	**table**：将元素设置为一个表格(在解决高度塌陷的时候会用到)

​	table-cell

​	**none**：**元素不在页面中显示，也不占地方**



**==visibility属性==**用来设置元素的**显示状态**

可选值：

visible：==默认值==，元素在页面中正常显示

hidden：元素在页面中**隐藏不显示**，但是依然**占据页面的位置**



##### 浏览器的默认样式

默认样式

通常情况，浏览器都会为元素设置一些默认样式

​	比如：body默认有外边距

​		    p默认有行间距

​		    ul默认有左内边距，且会有左边会有黑点

通常情况下编写网页时必须要**去除浏览器的默认样式**(PC端的页面)



可以自己手动去除浏览器的默认样式

![1616303824791](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616303824791.png)

其中ul标签的list-sytle:none 可以将默认的那个左边黑点去掉

**==最常用的方式==**

![1616303987695](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616303987695.png)

**==真正做项目常用的方法==**

或者直接上网搜现成·的写好的去除默认样式的css文件，直接link标签引入



#### 盒子的大小

默认情况下，盒子可见框的大小由内容区、内边距和边框共同决定

**==box- sizing属性==**：用来设置**==盒子尺寸的计算方式==**(设置width和 height的作用)

可选值：

​	**content-box**：**默认值**，宽度和高度用来设置内容区的大小，可见框的大小还要加上padding和border

​	**border-box**：**==宽度和高度用来设置整个可见框的大小==**，width和 height指的是内容区和内边距和边框的总大小（怪异模式）





#### 轮廓和圆角

**==outline属性==**

用来设置元素的**轮廓线**，**用法和 border模一样**

轮原和边框不同的点，就是轮廓不会影响到可见框的大小

==就相当于描了一个边，只是显示了一个效果==，不影响元素的盒子，不影响页面的布局

例子：

![1616313221206](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616313221206.png)



**==box-shadow属性==**

用来设置元素的阴影效果，也就是一个效果，不影响元素的盒子和页面的布局

属性由四个值设定

①水平偏移量

​	设置阴影的水平位置，正值向右移动，负值向右

②垂直偏移

​	设置阴影的水平位置，正值向下移动，负值向上

③阴影的模糊半径

④阴影的颜色，一般制成可透明的颜色

![1616313671101](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616313671101.png)

![1616313682267](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616313682267.png)





**==border-radius属性==**

可以分别指定四个角的圆角，也可设置成椭圆

**属性的值**是角的半径大小，或者椭圆的两个半径

![1616314108345](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616314108345.png)

指定椭圆角用**==/==**隔开一个角的两个椭圆半径，==四个角之间的值用空格隔开==

![1616314321245](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616314321245.png)

![1616314467753](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616314467753.png)



也可以用以下四个值**分别去指定四个角**的大小

![1616314238070](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616314238070.png)

分别指定的话，==椭圆半径角用两个值来表示，用空格隔开==，就不用/了



**==直接将border-radius 设置成50%，元素就成了一个圆==**

![1616314560323](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616314560323.png)



![1616314572281](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616314572281.png)



#### ==浮动的简介==  

通过浮动可以使一个元素向**==其父元素==**的左侧或右侧移动

使用**==float属性==**，即将float设置成非none的值，就相当于开启了浮动属性

可选值：

​	**none**：**默认值**，元素不浮动

​	**left**：元素向左浮动

​	**right**：元素向右浮动

**<font color='orange'>注意：</font> ** **==元素设置浮动以后，水平布局的等式便不需要强制成立==**

**==元素设置浮动以后，会完全从文档流中脱离，不再占用文档流的位置==**

**<font color='red'>！！！！！</font>** **==所有元素下边的还在文档流中的元素会自动向上移动==**

**==一行占不下会自动排列到下一行==**

浮动的特点：

![1616315798062](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616315798062.png)

**<font color='red'>！！！！！</font>** ==**第六点是，浮动元素不会超过他代码中的上一个兄弟元素**==



例子：

下面这三个div都设置了浮动，都是兄弟元素，代码中的先后顺序是绿、橙、黄，绿、橙向左浮动，黄向右浮动，页面占不下，橙和黄就换到了下一行，但是这时候**<font color='orange'>黄不会向上移动</font>**，因为上面讲到的**第六点**

![1616315870157](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616315870157.png)





**==浮动对于文字有一个特点==**

​	浮动元素**==不会盖住文字==**，文字会自动环绕在浮动元素的周围，如果是两个div就互相盖住了

​	所以我们可以利用浮动来设置文字环绕图片的效果



#### ==脱离文档流的特点==

元素设置浮动以后，将会从文档流中脱离，，元素的一些特点也会发生改变

**==脱离文档流的特点==**

**块元素：**

​	1、块元素==不再独占页面的一行==

​	2、脱离文档流以后，块元素的==宽度和高度默认都被内容撑开==

**行内元素：**

​	**行内元素**脱离文档流以后会**==变成块元素==**，特点和块元素一样，就可以进行width和height等属性的设定了

​	

**==脱离文档流以后，不需要再区分块和行内了==**





#### 高度塌陷问题和BFC

##### 高度塌陷问题

在浮动布局中，很多情况下，页面布局时**，父元素的高度会故意默认被子元素撑开**，这是为了方便让父元素中的子元素进行增减，并且做到整体布局合理

但是当**子元素浮动后**，子元素从文档流中脱离，将会无法撑起父元素的高度，**导致父元素的高度丢失**

父元素高度丢失以后，其下的元素会自动上移，导致页面的布局混乱



##### ==BFC==

BFC（Block Formatting Context）块级格式化环境

BFC是一个CSS中的一个隐含的属性，可以为一个元素开启BFC

开启BFC该元素会変成一个**==独立的布局区域==**

元素开启BFC后的

​	1.开启BFC的**元素==不会被浮动元素所覆盖==**（开启bfc的元素在浮动元素的下面时不会竖直上移被浮动元素挡住，它会排到浮动元素的右边，右边占不下就放到下面）

​	2.开启BFC的元素**子元素和父元素外边距不会重叠**

​	3.开启BFC的元素**可以包含浮动的子元素（也就是开启bfc的父元素不会高度塌陷）**



可以通过一些==特殊方式==来开启元素的BFC:

1、float的值不是none，设置元素的浮动（不推荐，有一些副作用）

2、display的值是**inline-block**、table-cell、**flex**、table-caption或者inline-flex

3、常用的方式为元素设置 **==overflow中hidden==**开启其BFC以使其可以包含浮动元素（**==常用==**），**也可以用overflow中的auto**（副作用较小）

4、开启元素定位，position的值不是static或者relative。



**==副作用汇总==**

1、display: table 可能引发响应性问题

2、overflow: scroll 可能产生多余的滚动条

3、float: left 将把元素移至左侧，并被其他元素环绕

4、overflow: hidden 将裁切溢出元素



##### clear



作用：**==清除浮动元素对当前元素所产生的影响==**

可选值

​	**left**：清除左侧浮动元素对当前元素的影响

​	**right**：清除右侧浮动元素对当前元素的影响

​	**both**：清除两侧中**==影响最大的那侧==**

原理：设置清除浮动以后，浏览器会自动为元素添加一个上外边距，以使其位置不受其他元素的影响



**==将它写在需要消除影响的那个元素中（不是指父元素），不是写在浮动的元素中==**

![1616323764904](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616323764904.png)

**==例子：==**

![image-20210509105607823](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210509105607823.png)



##### clear解决高度塌陷

一种添加一个div标签的方式来解决高度塌陷问题，但不算太好，应该用css的方法来解决css的问题，不能依靠HTML

![1616324187367](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616324187367.png)



**==最好方案==**

![1616324365570](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616324365570.png)



标准格式：

![1616325232172](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616325232172.png)

在高度塌陷的父元素中，写一个**==伪元素选择器==**，为父元素后面的**==after==**设置属性

**<font color='red'>after默认为行元素</font>**，用display:block转化为块元素

content不能少，after和before必须结合content来使用，只不过不用往content里面写内容

然后在after的伪元素选择器中设定clear:both



*这样父元素的下方有一个不受浮动元素影响的块元素，并且始终在父元素的最后面，父元素里面的所有浮动元素，为了不影响after，就会消除高度塌陷问题*



##### **==终极方案==**

![1616326161861](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616326161861.png)

这是一个很经典的代码，就可以将**==父子顶部外边距重叠的问题解决==**，==也可以将高度塌陷问题解决==

自定义一个类放到需要解决高度塌陷的**==父元素==**，然后设置这个类的after和before伪元素选择器，内容原理和上面基本一样，只不过display值是table，用table不用block**==是因为table既可以解决高度塌陷，又可以解决外边距重叠的问题==**

**<font color='red'>解决外边距重叠原理</font>**：display:table将元素转化为**==块级表格元素==**，也是块级元素，**==同样能完成将after从行内元素转化为块级元素的功能==**，并且before和table结合使用可以解决父子元素顶部外边距折叠，相当于创建一个块级元素放在父元素的内部最前面（**content为空的情况下，block仍会外边距折叠，inline-block的话before会出现高度，只有table合适**），隔开了父子元素，子元素这时设置margin-top就不会和父元素重叠了

（父子元素外边距重叠，意味着成为一体，设置子元素相当于设置父元素，兄弟元素外边距重叠，就只是意味着重叠而已）

标准代码如下：

```css
.clearfix::before,
.clearfix::after{
		content:'';/*使用after、before必须结合content来使用*/
		display: table;/*after、befor默认为行元素，用display:table转化为块元素*/
		clear: both;/*清除after、before伪元素上出现的左右浮动，防止高度塌陷*/
	}	
```





#### 定位

定位( position)：定位是一种更加高级的布局手段，通过定位可以将元素摆放到页面的任意位置

使用 **==position属性==**来设置定位

可选值：

​	**static**：默认值，元素是静止的没有开启定位

​	**relative**：开启元素的==相对定位==

​	**absolute**：开启元素的==绝对定位==

​	**fixed**：开启元素的==固定定位==

​	**sticky**：开启元素的==粘滞定位==

##### 相对定位

相对定位

position属性值为 **relative**

相对定位的特点

1.元素开启相对定位以后，如果不设置偏移量==元素不会发生任何的变化==，任何属性都没变

2.相对定位是参照与**==元素最一开始在文档流中的位置==**，也就是**==定位位置==**

3.相对定位会==提升元素的层级==

4.相对定位==**不会**使元素脱离文档流==

5.相对定位不==会改变元素的性质==，块还是块，行内还是行内



**==偏移量( offset)==**

当元素**==开启了定位以后==**，可以通过偏移量来设置元素的位置

**top**：定位元素和**定位位置**上边的距离

**bottom**：定位元素和**定位位置**下边的距离

**left**：定位元素和定位位置的左侧距离

**right**：定位元素和定位位置的右侧距离

top/bottom、left/right这两组分别用一个就行了



##### 绝对定位

 position属性值为 **absolute**

绝对定位的特点

1.开启绝对定位后，如果**==不设置偏移量，元素的暂且位置不会发生变化==**，**<font color='orange'>但此时变不代表原位就是偏移量为0的位置</font>**

2.绝对定位后，**==元素从文档流中脱离==**，**符合脱离文档流的一切特点**（详见上方脱离文档流的特点）

3.绝对定位会改变元素的性质，**==行内元素变成块==**，**==块的宽高被内容撑开==**，不在独占一行（实际上就是第二点）

4.绝对定位会使元素提升一个层级

5.绝对定位是相对于其**==包含块==**来进行定位的



**==包含块( containing block)==**

**正常情况下：**

​	包含块就是离当前元素最近的**祖先==块元素==**

**绝对定位的包含块：**

​	包含块就是离它最近的**==开启了定位==**（position属性的值非static）的祖先元素

​	如果所有的祖先元素都没有开启定位，则==根元素==HTML标签就是它的包含块





##### 固定定位

**position属性为 fixed**

固定定位也是**一种绝对定位**，所以固定定位==大部分的特点都和绝对定位一样==

==**唯一不同的是**固定定位永远参照于**浏览器的视口进行定位（也就是屏幕左上角，并不是页面左上角，滚动滑轮位置也不会变）**==，不管包含块，也就是固定的意思



##### 粘滞定位

粘滞定位

 position属性为 sticky

**粘滞定位和相对定位的特点基本一致**，定位是按照相对定位的方式

**==不同的是粘滞定位可以在元素到达某个位置时将其固定==**

页面向下滚动时，元素到达指定的位置就会不动了，再滚回去就恢复正常

但是常见的粘滞导航栏一般不用粘滞定位，因为**==兼容性不好（IE就不可用）==**，一般都结合js来达到目的



设置position:sticky同时给一个(top,bottom,right,left)之一即可

使用条件：

1、父元素**不能**overflow:hidden或者overflow:auto属性。

2、必须指定**top、bottom、left、right**4个值之一，否则只会处于相对定位

3、父元素的高度不能低于sticky元素的高度

4、sticky元素仅在其**父元素内**生效



##### 绝对定位的元素布局

###### ==水平方向==

之前讲的水平布局由7个属性来进行设置，如下：

**margin-left**

**border-left**

**padding-left**

**width**

**padding-right**

**border-right**

**margin-right**



开启绝对定位后，在加上**right和left**这两个属性一共9个

这9个值加起来前置等于父元素的宽度





如果9个属性中没有值为auto时，则自动调整 **==right==**值以使等式满足（之前一直是margin-right）

如果有auto,则自动调整auto的值以使等式满足

==**可设置auto值的有以下属性**==

==**margin width left right**==

因为left和 right的值默认是auto,所以如果不知道left和 right

像之前讲的，想设置子元素居中，让**==margin-left和margin-right和auto==**就行了，但是现在不行，**==必须写上right0和left:0==**，这两个值如果不指定的话，会自动调整这两个值

则等式不满足时，会自动调整这两个值

###### ==垂直方向==

==跟之前的不一样，开启绝对定位后，垂直方向也必须满足==

**top**

**margin-top**

**margin-bottom**

**padding-top**

**padding-bottom**

**border-top**

**border-bottom**

**height**

**bottom**

**==这些属性的值加起来也必须满足等于包含块的高度==**

利用这个同样可以实现垂直居中

设定好高和宽，**==让top:0;和bottom:0;，并且将margin-top:0和margin-bottom:0==**，就能垂直居中，原理类似。当然也能垂直水平双居中



#### 元素的层级

对于开启了定位元素，可以通过**==z-index属性==**来指定元素的层级

z- index需要一个==整数作为参数==，**==值越大元素的层级越高==**

==**元素的层级越高越优先显示**==

==如果元素的**层级一样**，则优先显示**靠下**的元素==

==**祖先的元素的层级再高也不会盖住后代元素**==





只要是定位，默认层级就一样高，无论是什么定位，只凭借z-index来比较层级



#### 字体

字体相关的样式属性

**==color==**用来设置字体颜色

**==font-size==**字体大小

和font-size**相关的单位：**

​	**em**相当于当前元素的一个font-size

​	**rem**相对于根元素的一个font-size

##### 字体族

**==font- family==**字体族（字体的格式类别）

可选值：

​	serif村线字体

​	sans- serif非村线字体

​	monospace等宽字体

​	......	

**==指定字体的类别，浏览器会自动使用该类别下的字体==**

font- family可以同时指定多个字体，多个字体间使用==逗号隔开==

字体生效时优先使用第一个，第一个无法使用则使用第二个以此类推

一般==前几个是具体的字体，最后一个是字体族==，前面几个没有了，浏览器就在最后的字体族中随便挑一个就行了

![1616372441537](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616372441537.png)

有的字体之间有空格，**建议将有空格的字体用引号引起来**，避免发生错误



##### font-face

**==@font-face属性==**

语法：

有两个属性：

​		**font-family**：指定字体的名字（和之前的font-family不同，这个是自己指定名字）

​		**src:url("")**    :服务器中字体的路径

实例：

![1616373396674](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616373396674.png)

可以将服务器中的属性直接提供给用户去使用

但是由于是用户从服务器上面去下载的字体，会==影响字体的 加载速度==

次属性涉及到版权的问题，必须使用已授权的字体，而前面讲的文字样式里面设定的==font-family不用考虑版权==，因为那个只是提供一个可选项，真正选哪个由用户的浏览器去选择

实例中的ttf文件是最常用的一个字体文件格式，

==为了防止有的文件格式在浏览器中加载不出来，会指定多个字体文件格式==

![1616374075033](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616374075033.png)

format一般不用写，是用来告诉浏览器这个字体文件是什么格式的，不同字体文件对应不同的格式，一般不写，如下

![1616374207131](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616374207131.png)





##### 图标字体

图标字体

在网页中经常需要使用一些图标，可以通过图片来引入图标

但是图片大小本身比较大，并且非常的不灵活

所以在使用图标时，我们还可以将图标直接设置为字体

然后通过**==@font-face==**的形式来对字体进行引入

这样我们就可以通过使用字体的形式来使用图标



###### fontawsesome

fontawesome使用

1.下载下来后，一般就将css和 webfonts移动到项目中就可以

2..将all.css引入到网页中

![1616375664893](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616375664893.png)

3..使用图标字体：直接通过类名来使用图标字体

下载下来的css里面**已经定义好类名了，css里面也写入了@font-face，并且设定好样式了**，我们只需要为标签绑定类名就行，一般常用的就是**==i标签==**，

类名有**==指定格式==**：**==fas/fab 字体图标的名字==**

一般就fas和fab这两个免费的类型

![1616375795822](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616375795822.png)





###### 字体图标其他使用方式

**<font color='orange'>①</font>**

通过伪元素来设置图标字体

1.找到要设置图标的元素通过 before或 after==伪元素选择器==选中

![1616378400864](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616378400864.png)

2.在**伪元素选择器中**的 ==content中设置字体的**编码**==，需要加上**反斜杠**（==官网上，或者文档中有每个图标对应的编码==）

![1616378422227](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616378422227.png)

3.在**伪元素选择器中**指定字体的**==font-family==**，有时也要设置字体的样式，基本上就分为两种情况，fab和fas类型的不同，下面的格式直接记住就行

![1616378440559](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616378440559.png)

**==fab:==** 

font-family: 'Font Awesome 5 Brands';

**==fas:==** 

font-family: 'Font Awesome 5 Free';

font-weight:900;



完整例子

![1616376368476](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616376368476.png)

![1616376378134](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616376378134.png)



**<font color='orange'>②</font>**

再或者，用之前讲过的**==字符实体==**来设置字体图标

**==字符实体语法：&实体的名字==**

在这里语法：**==&#x图标编码==**

但类名**==只用写fab或者fas==**就行了

![1616377478167](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616377478167.png)



###### iconfont

使用方法：

1.网上打包下载字体项目文件

2.用link标签引入iconfont.css的css文件

![1616378473326](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616378473326.png)

3.为需要的元素添加名为iconfont的类名

![1616378539768](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616378539768.png)

4.在元素中写入文档中指定的图标编码

![1616378637070](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616378637070.png)

5.设置图标的样式需要指明iconfont的类名，选择器只说明标签名不行，因为css文件里面设定了iconfont类的样式，就会覆盖元素本身设置的样式

![1616378819338](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616378819338.png)



ps：图标库中还为每一个图标设置了指定的类名，使用具体的类名，就不用写编码来指定了，如下就可以

![1616378975629](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616378975629.png)

​	同样也可以使用伪元素选择器来设置样式，同之前的方法





##### 字体的简写属性

**==font属性==**可以设置字体的所有相关属性

之前**字体大小**和**字体族**分开写

![1616381013937](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616381013937.png)

现在可以写在一起了

不同内容的值用==空格隔开==，各自的语法还是不变



**==语法：==**

​	==**font:字体大小/行高 字体族**==

![1616381235869](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616381235869.png)

![1616381056004](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616381056004.png)

​	ps：

​		①==/==并不是或的意思

​		②行高是可选值，可写可不写，**==但是不写不意味着没有，有一个具体的默认值==**，之前如果设置了行高的话，**会被覆盖掉**



font属性中在字体大小和字体族前面，还可以**选写==italic（斜体）和bold（加粗）==**，顺序无所谓，不写就是默认值

![1616381752271](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616381752271.png)





##### font-weight和font-style

**==font- weight属性==**：字重（用来设置字体的加粗）

可选值：

​	**normal**：默认值不加粗

​	**bold**：加粗

​	100-900九个级别（**没什么用**）



**==font- style属性==**：字体的风格（用来设置字体的倾斜）

可选值：

​	**normal**：正常的

​	**italic**：斜体

















#### 行高

**==行高(line-height)==**

==行高指的是文字占有的实际高度==

可以通过**==line- height属性==**来设置行高

行高可以直接指定一个大小(px、em)

也可以直接为行高设置一个整数

​	**==如果是一个整数的话，行高将会是字体的指定的倍数==**

多行的行高不会进行重叠

 

**==字体框==**

字体框就是字体存在的格子，使用**==font-size属性==**来设置字体框的高度，即**在调整字体的大小**



如果父元素不设置height高度的话，多余的**行高**会在**字体框**的上下平均分配，这也就是之前将到的**==垂直居中设置方法==**：

①将==行高（line-height）和父元素高度（height）设置成一样的，再将行高和字体框（font-size）的大小设置一样==

②==或者直接不设置父元素的height，直接由行高来撑起来就行==



可以经过换算后得，**==行间距=行高 - 字体大小==**





#### 文本的水平和垂直对齐

##### 水平对齐

**==text- align属性==**：文本的水平对齐

可选值：

left：左侧对齐，默认值

right：右对齐

center：**居中对齐**

justify：两端对齐





##### 垂直对齐

一般适用于一行中不同元素中的文字，这样垂直方向才会有偏差，如图：

![1616383029376](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616383029376.png)

**==vertical- align属性==**：设置元素垂直对齐的方式

**可选值：**

​	baseline：==默认值==，基线对齐，并非元素的最底部

​	top：顶部对齐，元素的顶部

​	bottom：底部对齐，元素的底部

​	middle：居中对齐

​	指定数值，如：100px，他会往基线的上方移动100px的距离

例子：

![1616383062355](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616383062355.png)





元素引入一个图片，这个图片同样也是默认基线对齐，所以图片并没有对准元素的底部，会有一个缝隙

![1616383275140](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616383275140.png)

同样可以用**==垂直对齐的属性vertical- align==**来消除，在图片的样式中添加vertical- align

使vertical- align:bottom或者top，就可以消除缝隙



##### ==ps：==

我们将容器设为display:table，然后他成为一个块级表格元素

子元素设置display:table-cell使子元素成为表格单元格，然后就像在表格里一样，给子元素加个vertical-align: middle就行了，多行文字垂直居中啦。是不是很直接很简洁~

#### 文本的样式



**==text-decoration属性==**：设置文本修饰

可选值：

​	**none**：什么都没有

​	**underline**：下划线

​	**line- through**：删除线

​	**overline**：上划线

![1616400276405](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616400276405.png)

在上面这些值的后面还可以指定==颜色==和==线的样式==，用==空格==隔开，但是颜色和线的样式==IE不支持==

![1616400381326](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616400381326.png)



**==white-space属性==**：设置网页如何处理空白

可选值：

​	**normal**：正常

​	**nowrap**：不换行

​	**pre**：保留空白（==会保留元素内文本的原来格式，换行和空格都会保留==，不会改变）





pre效果：

![1616400814933](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616400814933.png)

![1616400806795](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616400806795.png)

![1616400823313](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616400823313.png)



==**text-overflow属性**==：设置文本溢出的样式

text-overflow:ellipsis	==将溢出的边缘使用省略号==

前提是：==white-space属性的值是nowarp==（不换行）

​		==overflow属性值是hidden==

![1616401215517](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616401215517.png)

![1616401278999](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616401278999.png)



#### 背景

background-color：背景颜色

**==background-image==**：设置背景图片

同时设置背景颜色和背景图片，背景颜色将会成为图片的背景色

**==语法：background-image:url("图片地址");==**

![1616426806124](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616426806124.png)

如果**背景的图片小于元素**，则背景图片会自动在元素中平铺将元素**铺满**，不拉伸

如果背景的**图片大于元素**，将会一个部分背景无法完全显示

如果背景图片和元素一样大，则会直接正常显示



**==background-repeat==**：用来设置背景图片的重复方式

可选值：

​	repeat：默认值，背景会沿着x在曲y双方向重复

​	repeat-x：沿着x方向重复

​	repeat-y：沿着y方向重复

​	no- repeat：背景图片不重复



**==background-position==**：用来设置图片在父元素中的位置

通过 top、left、right、bottom、center几个表示方位的值来组合表示父元素九宫格的九个位置

| 值                                                           | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| top left <br>top center<br/>top right <br/>center left <br/>center center <br/>center right <br/>bottom left <br/>bottom center <br/>bottom right | 如果您仅规定了一个关键词，那么第二个值将是"center"。<br/>默认值：0% 0%。 |
| x% y%                                                        | 第一个值是水平位置，第二个值是垂直位置。<br/>左上角是 0% 0%。右下角是 100% 100%。<br/>如果您仅规定了一个值，另一个值将是 50%。 |
| xpos ypos                                                    | 第一个值是水平位置，第二个值是垂直位置。<br/>如果您仅规定了一个值，另一个值将是50%。 |



background-color

background-image

background-repeat

background-position

background-size







**==background-clip==**：设置背景的范围

可选值：

​	**border-box**：==默认值==，==背景会出现在边框的下边==

​	**padding-box**：背景不会出现在边框，只出现在==内容区和内边距==

​	**content-box**：背景只会出现在==内容区==



**==background- origin==**：**背景图片的偏移量计算的原点**

可选值：

​	**padding-box**：默认值， **==background-position==**从==内边距==处开始计算

​	**content-box**：背景图片的偏移量从==内容区==处计算

​	**border-box**：背景图片的变量从==边框处==开始计算



**==background-size==**：设置背景图片的大小

可选值：

​	第一个值表示**宽度**

​	第二个值表示**高度**

​	**如果只写一个，则第二个值默认是auto**

​	或者写以下两个值：

​		**cover**：图片的比例不变，将元素铺满，能做到铺满就行，不用将图片还原成原来的大小

​		**contain**：图片比例不变，将图片在元素中完整展示，不用将图片过于缩小，能展示完整就可



**==background-attachment==**：背景图片是否跟随元素移动

可选值：

​	**scroll**：==默认值==，背景图片会==跟随元素移动==

​	**fixed**：背景会固定在页面中，==不会随元素移动==

![1616482168850](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616482168850.png)

注意，在这里面父元素的背景不会移动，因为父元素本身就没有动，移动的是子元素





**==background==**：背景相关的简写属性，所有背景相关的样式都可以通过background来设置

注意：

**background-size**必须写在 **background- positione**的**后边**，并且使用==/==隔开：**==background-position/background-size==**

background- origin和background-clip两个样式， orging要在clip的前边，因为这两个属性的值一样，这么做为了区分

![1616482257492](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616482257492.png)



#### 雪碧图

**==网页背景加载的一个实际问题==**：

  一个按钮点击效果，点击前，点击时，点击后三种状态，三个图片

![1616483738140](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616483738140.png)

![1616483825499](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616483825499.png)

图片属于网页中的外部资源，外部资源都需要浏览器单独发送请求加载

浏览器加载外部资源时是按需加载的，用则加载，不用则不加载

像我们上边的练习link会首先加载，而 hover和 active会在指定状态触发时才会加载，用户第一次点击按钮时会有**==卡顿==**的体验



**==解决方案==**

解决图片闪烁的是题

可以将多个小图片统一保存到一个大图片中，然后通过调整 background- position来显示相应的图片

这样图片会同时加载到网页中**就可以有效的避免出现烁的问题**

**==这个技术在css中应用十分广泛，被称为CSS-Sprite（雪碧图）==**

![1616484083832](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616484083832.png)





雪碧图的使用步骤：

先确定要使用的图标

测量图标的大小

根据测量结果创建一个元素

将雪碧图设置为元素的背景图片

设置一个偏移量以显示正确的图片



雪碧图的特点：

次性将多个图片加载进页面，降低请求的次数，加快访回速度，提升用户的体验



#### 渐变

通过渐变可以设置一些复杂的背景颜色，可以实现从一个颜色向其他颜色过度的效果

**==渐变是图片==**，需要通过**==background-image属性==**来设置，对老版本兼容新不好



**==linear-gradient()==**：线性渐变，颜色沿着一条直线发生变化

linear-gradient(red, yellow)，红色在开头，黄色在结尾，中间是过渡区域

![1616486181796](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616486181796.png)

![1616486192531](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616486192531.png)



线性渐变的开头，我们可以指定一个渐变的方向

to left

to right

to bottom

to top

to top left

xxxdeg  		deg表示度数

![1616487269388](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616487269388.png)

![1616487236283](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616487236283.png)

颜色不止两种，也可以指定多种，多种颜色平均分配

![1616487346542](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616487346542.png)

![1616487355631](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616487355631.png)

可以手动指定渐变的分布情况，在每个颜色的后面指定纯色开始的位置，例如，红色从50px开始发生渐变，黄色从100px完成渐变，后面全是纯色

![1616487574825](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616487574825.png)

![1616487584026](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616487584026.png)

**==repeating-linear-gradient()==**可以平铺的线性渐变

![1616487863590](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616487863590.png)

![1616487872049](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616487872049.png)

==设置完repeating-linear-gradient之后，再设置background-repeat:no-repeat就没有用了==





#### 径向渐变

radial-gradient()径向渐变（放射性效果）

设置径向渐变圆的大小，设置径向渐变中心点的位置，语法如下：

![1616488424174](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616488424174.png)

![1616488432509](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616488432509.png)

![1616488524483](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616488524483.png)

![1616488535077](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616488535077.png)

具体某部分语法：

![1616488794612](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616488794612.png)







### 表格

通过**==table标签==**来创建表格

table标签中使用==tr标签代表行==，tr标签中使用==td标签代表列==

![1616496101266](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616496101266.png)

==td标签中的colspan属性==：横向合并单元格

![1616496381399](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616496381399.png)

==td标签中的rowspan属性==：纵向合并单元格

![1616496373148](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616496373148.png)

![1616496394598](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616496394598.png)



#### 长表格

table里面还可以有三个有语义的标签

​	==thead标签==：语义是表格的头部

​	==tbody标签==：语义是表格的主体

​	==tfoot标签==：语义是表格的尾部

这三个可以在表格的第一行、中间所有、最后一行的**==tr标签外面加上==**

加上后，无论thead、tbody、tfoot的先后顺序怎么样，三个部分的位置永远都是头、主体、尾部，**==位置定死了==**。

**==thead中的tr标签中的td标签可以用th来代替==**，代替后头部的文本有==**加粗居中**==的效果

![1616497034193](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616497034193.png)

![1616497041033](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616497041033.png)



#### 表格的样式



table也是**==块元素==**，只不过比较特殊，他默认不是占全屏，而是**==被内容撑开==**

##### **==注意：==**

**<font color='orange'>①</font>**

在**内联样式**中的table中设置border属性，设置边框宽度时，**内部外部全部都设置了**

但是在**样式表**里面设置时，在table中设置只会为**表格外层添加边框**

**<font color='orange'>②</font>**

如果表格中没有使用 tbody而是直接使用tr

么**==浏览器会自动创建一个 tbody==**，并且将tr全都放到 tbody中

tr不是 table的子元素，**==table中通过子元素选择器也选不中tr==**





以下是在==样式表==中设置表格属性：

可以按块元素的样式来设置表格的样式

**==table==**的border设置表格的**==外围边框==**

**==td==**的border设置**==内部的边框==**



##### table中的属性：

**==border-spacing属性==**：指定边框之间的距离

![1616498331452](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616498331452.png)

**==border-collapse:collapse==**   设置边框的合并

​	border-collapse:collapse设置之后**border-spacing属性就没有作用了**

![1616498422660](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616498422660.png)







##### tr中的属性：

让奇数行变颜色：使用**伪类选择器**让奇数行变颜色

**==tr:nth-child(2n+1/even/odd)==**

![1616498658103](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616498658103.png)

![1616498665348](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616498665348.png)



##### td中的属性：

==默认==情况下元素在td中是**==垂直居中==**的

在td中可以设置==vertical- align==（文本的垂直对齐属性）、和==text-align（文本的水平对齐属性）==等属性来设置文本水平和垂直的对齐方式





##### 补充：

在div中可以将元素的元素显示的类型**==display设置成table-cell==**，蒋奇设置成一个单元格，这样能够使用**==vertical- align:middle（这个之前只能在文本和表格中使用）==**来设置子元素的==垂直对齐方式==

元素变成table-cell后，比较特殊，他**==只能跟同是table-cell的元素在一行，其他元素不能跟其同行==**

![1616499671667](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616499671667.png)







### 表单

网页中的表单用于将本地的数据提交给远程的服务器

form标签，form来创建一个表单

​	==action属性==：表单要提交的服务器的地址

![1616502029788](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616502029788.png)

**==form中有以下几种表单项==**：

都是**==input标签（行内元素）==**，只是type属性值不同

但是，==这几个表单中的数据要提交到服务器，必须要为元素指定一个name属性==

**==文本框：==**

type属性为**text**，**value属性**可以为文本框指定默认值

![1616503397362](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616503397362.png)

![1616503409668](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616503409668.png)



**==提交按钮：==**

type的值为**submit**

value属性可以指定提交按钮内的值

![1616503279304](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616503279304.png)





**==密码框：==**

type属性值为**password**

![1616502250994](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616502250994.png)





**==单选按钮框：==**

type属性值为**radio**

![1616502579603](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616502579603.png)

![1616502807363](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616502807363.png)

几个按钮想要==共属于一组==，必须要有一个==相同的name属性==，这几个一组的按钮之间只能选中一个，否则相互之间没有关系

像这种选择按钮，**==还必须指定value属性==**，作为按钮的数据值传递给服务器

按钮框还可以为一个按钮设置**==默认选中==**属性，在input中加上**==checked==**即可，相应按钮一开始就是被选中的状态

![1616502698499](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616502698499.png)





**==颜色选择框==**

type属性值为color，可以选择颜色，兼容性不太好，IE不支持





**==邮件输入框==**

type值为**email**，和文本输入框相似，只不过是用来输入邮件的，输入的格式不符合邮件，会有提示，但提示的内容在不同的浏览器中有时候不一样

![1616505468337](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616505468337.png)

![1616505476578](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616505476578.png)

type还有一个tel值，是用来输入电话号码的，但是email和tel在pc端使用的不多，**==多用在移动端==**，移动端会有相应的不同键盘来配合使用





**==多选按钮框==**

type属性值是**checkbox**

![1616502829034](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616502829034.png)

![1616502834218](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616502834218.png)

可以多选按钮，其他性质和单选框一样，也可以设置checked属性



**==重置按钮==**

type属性的值为**reset**，可以将表单里面写的内容重置，要么清空，要么变成默认的

![1616503653496](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616503653496.png)



**==普通按钮==**

type属性的值为**button**，value属性指定按钮的内容

![1616503539188](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616503539188.png)





**==下拉列表==**

下拉列表就不是input标签了，为**==select标签==**

select标签中还有**==option子标签==**，用来表示下拉选项

![1616503103746](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616503103746.png)

![1616503109786](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616503109786.png)

可以为某一个option标签设置**==select属性==**，表示==默认选中==

![1616503158074](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616503158074.png)

还有另一个属性：**==multiple属性==**

用来表示下拉列表可以多选，按住**==ctrl键==**进行多选

![1617239568100](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617239568100.png)

![1617239590119](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617239590119.png)



**==数字框==** input的type="number"

==<input type="number" />==

![1617261512208](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617261512208.png)

![1617261447814](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617261447814.png)

只能输入数字，可以是小数，右边的小箭头是用来加减整数的





与几个input按钮（提交按钮，重置按钮，普通按钮）相对的也有三个应有**==button标签==**

button标签也有==type属性==，可选值也分别由submit（提交）、reset（重置）、button（普通按钮）

作用跟上面那三个按钮一样，只是写法不一样，**==button不是自结束标签，所所以可以写一些复杂的结构==**

![1616503944973](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616503944973.png)











某些属性的补充

**==autocomplete属性==**：用来控制输入框表单自动补全的功能，之前输入过的内容，可以选择展示，也可以关闭

on默认开启，off关闭

![1616505854091](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616505854091.png)

![1616505860409](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616505860409.png)

如果将autocomplete属性放在input的样式中，也要一个一个设置，==放在form标签的属性中，所有输入框的自动补全提示就全都关闭了==





**==readonly属性==**：将表单项设置为**只读**，不可修改，==但数据会提交到服务器中==

**==disable属性==**：将表单项设置为**禁用**，也用不了，表单项直接变成了灰色，==数据也不能提交了==

**==autofocus属性==**：**自动获取焦点**，页面一加载，焦点就在这个表单项中



#### lable标签

\<label> 标签**==为 input 元素定义标注（标记）==**。

label 元素不会向用户呈现任何特殊效果。

不过，它为鼠标用户改进了可用性。如果您在 label 元素内点击文本，就会触发此控件，**==就是说点击按钮前面的文本也就相当于点击了按钮==**

##### lable位于表单里面

一般label同样是写在**==form表单标签里面==**的

将表单与label标签联系起来有两种方式：显式、隐式

**==隐式形式==**：将表单控件作为标记标签的内容，

![1617158746702](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617158746702.png)



**==显式形式==**：或者为 \<label> 标签下的 for 属性命名一个目标表单 id

\<label> 标签的 **==for 属性==**应当与**==相关元素的 id 属性==**相同。

![1617158756616](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617158756616.png)

##### lable位于表单外面

 **==label 也可以位于 form 元素之外==**，但仍然是表单的一部分。

label中添加一个**==form 属性==**规定 label 所属的一个或多个表单。

**==form 属性的值==**必须是其所属的**==表单的 id==**。

![1617160632731](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617160632731.png)

**<font color='red'>ps</font>**：实际使用这个的时候有问题，多个表单时，form属性绑定几乎没有用，不知道为什么











### 网站的图标

设置**==网站的图标==**（在标题栏和收藏栏）
​	网站的图标一般都存在网站的根目录下面，名字一般都叫做favicon.ico

**==在head标签中，用link标签引入，rel属性值为icon==**

![1616593350356](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616593350356.png)





### 项目代码的压缩

平时写完项目时，为了项目的上线用户体验流畅，应当将项目代码尽可能的压缩，将换行、空格和注释等等全都删去

使用**==插件或者工具==**，来将代码进行压缩，自动删除注释、换行、空格等等



### animation

#### 过渡

**==transition属性==**：过渡效果，哪个元素需要添加过渡效果就在那个元素样式中添加

两个可选值：

​	第一个：需要添加过渡效果的属性的名称。或者，all：所有的属性都添加过渡效果

​	第二个：过渡效果的时间，需要加上时间单位

![1616594650490](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616594650490.png)

![1616594662022](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616594662022.png)





==**transition-property：**==

指定要执行过渡的**属性**

多个属性间使用**逗号**隔开

如果所有属性都需要过渡，则使用**all关键字**

大部分属性都支持过渡效果，只要是可计算的值基本都可以，**颜色、角度**等等都可以过渡

注意过渡时必须是从一个有效数值向另外一个有效数值进行过渡，==不能有auto==



==**transition-duration：**==

指定过渡的持续时间

多个属性也可以分别指定时间，如下图：长宽变化时间不一样

![1616595225032](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616595225032.png)

==**transition-timing-function：**==

指定过渡方式

可选值：

ease：**默认值**，慢速开始，先加速，再减速

linear：匀速运动

ease-in：加速运动

ease-out：减速运动

ease-in-out：先加速后减速（和ease有一点点差别，速度上看加减速比ease猛）

cubic- bezier()：来**指定时序函数**，参数是四个值，上面所有的可选值其实都是由Bezier曲线生成的（一般不用这个）

生成bezier曲线的网站：https://cubic-bezier.com

steps()：分步执行过渡效果

两个可选值：

第一个为**步数**，分几步执行，将指定的过度时间除以这个步数，然后分段执行（效果是突变的）

第二个可选可不选：

​	end：在时间结束时执行过渡（**默认值**）

​	start：在时间开始时执行过渡

![1616596530977](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616596530977.png)



==**transition-delay：**==

过渡效果的延迟，等待一段时间后在执行



**==transition==**简写属性

可以同时设置过渡相关的所有属性，只有一个要求，如果要写延迟，则两个时间中==第一个是持续时间，第二个是延迟==

![1616596649496](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616596649496.png)

![1616596663473](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616596663473.png)





#### 动画

动画和过渡类似，都是可以实现一些动态的效果

过渡需要在某个属性发生变化时才会触发

动画可以自动触发动态效果

设置动画效果，必须先要设置一个**==关键帧==**，**==关键帧设置了动画执行每一个步骤==**





#### 关键帧

**==关键帧==**：（**写在css中**）

**==语法：==**

​	@keyframes 关键帧自定义的名字{

​		from{初始属性值}；

​		......

​		to{结束属性值}；

​	}

from是动画开始的位置，同时动画结束的位置，**from可以写成0%，to可以写成100%**，同样==0~100%之间可以设置任意关键帧==

![1616601040810](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616601040810.png)



设置好关键帧后，可以在元素的样式中指定动画属性，元素的样式位置和关键帧的位置**没有先后顺序要求**

动画有以下几个属性：

==**animation-name**==：要对当前元素生效的**关键帧的名字**

**==animation- duration==**：动画的持续时间

**==animation-delay==**：动画的延时执行

**==animation-timing-function==**：指定过渡方式，和过渡属性设置的一样

**==animation- iteration-count==**：动画执行的次数，每次都从from到to

​	可选值：

​		次数：1/2、...

​		infinite：无限执行	



**==animation-direction==**：指定动画运行的方向

可选值：

​	normal：**默认值**，从from向to运行毎次都是这样

​	reverse：从**to向from**运行每次都是这样

​	alternate：从from向to运行，**重复执行动画时==反向执行==**，来回正放到放

​	alternate-reverse：从**to向from**运行，重复执行动画时反向执行



**==animation-play-state==**：设置动画的执行状态，就是用来控制动画的运行与暂停

可选值：

​	running：默认值，动画执行

​	paused：动画暂停	



**==animation-fill-mode==**：动画的填充模式

可选值：

​	none：默认值，动画执行完毕元素回到原来位置

​	forwards：动画执行完毕元素会停止在动画结東的位置

​	backwards：动画延时等待时，元素就会处于开始位置，（==元素原来的样式可能跟from设定的样式不一样，这里是回到**from设定的状态**，none是元素原来的样式==）

​	both：结合了 forwards和 backwards



**==animation==**：简写属性

以上所有的属性都可以写到简写属性中去，==持续时间放在延迟时间前面==

![1616602626303](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616602626303.png)





**==关键帧的补充：==**

当设置多个关键帧时，可以==关键帧中==修改最一开始在元素样式设置的过渡方式，让几个过程有不同的过渡方式

注意：在关键帧设置的过渡方式是**==从这个位置到下一个关键帧的位置之间的过渡方式==**，而不是过渡到此位置的过渡方式

例子：

![1616672629153](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616672629153.png)

还可以将几个关键帧整合，将具有相同属性的关键帧进行合并，类似于选择器分组

![1616672670325](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616672670325.png)





#### 变形

变形就是指通过CSS来改变元素的**==形状或位置==**

变形**==不会影响到页面的布局==**

**==transform属性==**，用来设置元素的变形效果，可以同时设置多个变形效果，==之间用**空格**隔开==。

**==一个元素只能有一个transform属性==**，一次性将所有需要变形的属性写完，不能写多个，多个会产生覆盖，上一个写的所有属性完全不起作用

**<font color='orange'>此属性是可以作为transition属性的一个值，作为有变化的属性</font>**

有以下几种变形效果

##### 平移

​	translateX()：沿着x方向平移

​	translateY()：沿着y方向平移

​	translateZ()：沿着z轴方向平移

括号里面写平移的位置或者百分比，==百分比是相对于自身计算的==



可以利用此特性来将**==宽度高度不确定的元素==**在页面实现**==居中==**，如图：

![1616673712131](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616673712131.png)

==box3是个div，由于元素被内容撑开，长度不确定，页面居中的话可以使用**left相对包含块的居中**，在**用transform进行左侧移动元素自身的50%**==

此属性可以完成页面中的点击浮动的效果

![1616674233732](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616674233732.png)





##### z轴平移

轴平移，调整元素在z轴的位置，正常情况就是调整元素和人眼之间的距离

轴平移属于立体效果（近大远小），**==默认情况下网页是不支持透视==**，如果需要看见效果，必须要设置**==网页的视距==**

网页的透视一般都设置给html标签，用**==persective属性==**来设置

![1616674803799](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616674803799.png)

设置之后就能开启了透视

![1616674867311](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616674867311.png)

设置了之后，translateZ()参数值为正，视觉上元素就会放大，为负，元素就会缩小，当元素旋转后，就能看到z轴的变化



##### 旋转

通过旋转可以使元素沿着x、y或z旋转指定的角度，同样用**==transform属性==**来设置，有以下几个可选函数：

rotateX()

rotateY()

rotateZ()

==参数是**45deg、90deg等角度**，或者**圈数：0.25turn、1turn**==

开启透视也会有近大远小的效果

![1616675358882](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616675358882.png)



transform属性里面表示变形的函数可以写多个，但是会有变形的先后顺序（**==这个指的不是时间上的，而是效果上的==**）

**如图：**

![1616677534680](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616677534680.png)

旋转后，整个立体坐标轴也发生了旋转，==坐标轴的旋转会影响z轴上的形变==



与旋转有关的一个**==backface-visibility属性==**

可选值：

​	visible：**默认值**，元素的背面显示，相当于镜像反过来

​	hidden：元素的背面隐藏





##### 缩放

对元素进行的缩放

transform属性中可选的函数：

​	scalex()水平方向缩放

​	scaley()垂直方向缩放

​	scale()双方向的缩放

函数里面的参数都是放大的倍数，大于1是放大，小于1是缩小

![1616681837715](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616681837715.png)



**==transform-origin属性==**：用来设置变形的原点

可选值：

​	center：默认值，中心

​	相对于元素左上角的定位，例如20px 20px，中间用空格隔开

![1616682492756](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616682492756.png)



### less

less是一门css的预处理语言

less是一个css的增强版，通过less可以编写更少的代码实现更强大的样式

在原生的css中也可以用一些less中常用到的语法，如下

比如设置变量

在HTM标签的选择器中设置**==变量==**：

​	==**语法：--变量名:变量值**==

​	==**调用：var(--变量名)**==

![1616810681671](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616810681671.png)

比如一些函数，如**==计算函数calc()函数==**，函数值可以是一个计算式

![1616810743922](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616810743922.png)

但是在原生的css中写这些功能兼容性不好，于是有一门新的语言就出现了，不只是这些功能可以兼容，语法也更简化了，增添了许多对css的扩展

**==浏览器不能直接执行less代码，要转化为css再由浏览器支持，转化的过程一般由插件来完成==**



#### 注释

//：单行注释，这种注释内容不会被解析到css中去

/**/：css中的注释，注释的内容会被解析到css中去

#### 变量

在变量中可以存储一个任意的值

并且我们可以在需要时，任意的修改变量中的值

变量的**语法**：==**@变量名:变量值**==

变量的**引用**：

​	**<font color='orange'>①</font>**如果是直接使用，直接使用==**@变量名**==就行

![1616813558885](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616813558885.png)

​	**<font color='orange'>②</font>**如果作为类名，或者一部分值时必须以**==@{变量名}==**的形式使用

![1616813986171](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616813986171.png)



变量的声明和使用**没有先后顺序**，但一般都先声明，后声明的话也能用，同一个变量，**后面的值会覆盖之前定义的**



还有另外一种变量，可以同时将**==属性值==**与**==属性名==**定义变量，使用的时候需要在@变量名后面加**==括号==**

**声明变量**

有点类似于 下面的 混合方法

```css
      - 结构: @name: { 属性: 值 ;};
      - 使用：@name();

      /* Less */
      @background: {background:red;};
      #main{
          @background();
      }
      @Rules:{
          width: 200px;
          height: 200px;
          border: solid 1px red;
      };
      #con{
        @Rules();
      }
    
      /* 生成的 CSS */
      #main{
        background:red;
      }
      #con{
        width: 200px;
        height: 200px;
        border: solid 1px red;
      }
```





**==$的使用==**

同一个选择器如果想引用别的属性里面的值，使用$属性名，就可以作为变量引用别的属性的属性值

![1616814442992](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616814442992.png)







#### 变量作用域

一句话理解就是：**就近原则**，不要跟我提闭包。

*借助官网的Demo*

```css
      /* Less */
      @var: @a;
      @a: 100%;
      #wrap {
        width: @var;
        @a: 9%;
      }
    
      /* 生成的 CSS */
      #wrap {
        width: 9%;
      }
```



#### 父元素



**==后代元素==**直接在父元素的括号里面新建新的选择器（.class名、标签名）就行

如果想指定**==子元素==**，则应当在选择器之前加上**==>==**

![1616814823968](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616814823968.png)



**==&号的使用==**

less的选择器可以嵌套写表示祖先后代关系，用==&可以代表当前这个选择器外面那层的父元素，用&替换此父元素，且不会产生其他的嵌套==

**==例子：==**

![1616827478656](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616827478656.png)

第一个&代表的是.box1>.box3:hover

第二个&代表的是box1:hover

第三个个&代表的是div box1



#### 样式的扩展

**<font color='orange'>①</font>**

##### extend

**==:extend()==**

**==对括号里面的选择器的属性进行扩展==**，既有括号里面的选择器的属性，也可以新增属性，新增的属性写在新建的这个选择器中

括号里面的选择器可以是子元素选择器、分组选择器等等等等

**==语法：==**

选择器2:extend(选择器1){   }

![1616827804333](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616827804333.png)

生成的css文件里面的样式，生成的**==选择器分组==**：

![1616827940658](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616827940658.png)

**==多处使用同一个选择器作为括号里的参数，相关的样式都会写到一个选择器分组里面，，提高效率，节省空间==**









<font color='orange'>**②**</font>

##### 混合mixins

另一种方法直接将样式进行引用，相当于将样式进行了复制

这种方法叫样式的**==mixins混合==**

语法：在新的选择器2中添加  **==选择器1();==**就可以

![1616828303587](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616828303587.png)

生成的css样式：

![1616828396569](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616828396569.png)

**==样式是直接复制过来的，不会生成选择器分组==**

所以这么用效率会比较低





<font color='orange'>**一般应用于以下的场景：**</font>

使用类选择器时可以在选择器后边==添加一个括号==，这时我们实际上就**==创建了一个 mixins混合函数==**，函数中可以加入形参

但是这个**==mixins不会在css中生成==**，这个mixins是专门用来给别的选择器用的，谁需要，谁就将这个带括号的mixins写入属性中

**==例子==**

![1616828792518](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616828792518.png)



**==引用时，如果没有形参，()括号可以不写==**

![1616829207812](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616829207812.png)



**==括号中可以加入形参==**，在调用这个mixins函数的时候在指定一些属性的值，形参用**==@变量==**的形式写到括号里面

![1616830189711](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616830189711.png)



![1616830265673](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616830265673.png)



**==定义形参变量的时候，还可以指定默认值==**

在写实参的时候，==没写的实参就用默认值==

不写默认值，有几个形参就写几个实参

![1616830335662](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616830335662.png)



less还定义了一些**==官方的函数库==**，可以直接调用



#### less的计算

less中的所有数值都可进行直接的运算，像属性里面的数值都可以进行直接的运算

![1616830918243](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616830918243.png)

 - 加减法时 以第一个数据的单位为基准
  - 乘除法时 注意单位一定要统一







#### 补充

less还可以**==用@import来将其他的less文件来导入==**，其他文件中的less样式，在当前的less文件中生效

![1616830990710](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616830990710.png)

这样方便对less文件做模块化的处理

讲不同种类的less写到不同文件中，如mixins、变量、页面布局、动画效果.......然后进行整合





### 弹性盒

flex(弹性盒、伸缩盒)

是css中又一种布局手段，它主要用来代替浮动来完成页面的布局

flex使==元素具有弾性==，让==元素可以跟随页面的大小的改变而改变==



**==弹性容器==**

使用弹性盒，必须先将一个元素设置为弹性容器

我们通过 **==display属性==**来设直弹性容器

**display:flex**：设为**==块级弹性容器==**，独占一行

**display:inline-flex**：设置为**==行内的弹性容器==**，**不会独占一行**



设置弹性盒后，子元素如果浮动后，就不会有高度塌陷的问题，盒子随盒内元素的浮动而变化高度



**==弹性元素==**

==弹性容器的**直接子元素**就会**自动变成弹性元素**==

一个元素可以同时是弹性容器和弹性元素





#### 弹性容器的属性

##### **==flex-direction==**  

指定容器中弹性元素的排列方式

可选值

row：**默认值**，弾性元素在容器中水平排列（左向右）

row-reverse：弹性元素在容器中反向水平排列（右向左）

column：弹性元素纵向排列（自上向下）

column-reverse：弹性元素方向纵向排列（自下向上）



主轴：

**==弾性元素的排列方向==**称为主轴

侧轴（辅轴）：

与主轴垂直方向的称为侧轴（辅轴）





##### ==**flex-wrap属性**==

设置弹性元素是否在弹性容器中自动换行

可选值

**nowrap**：**默认值**，元素不会自动换行

**wrap**：元素沿着==辅轴==方向自动换行

![1616838878115](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616838878115.png)

**wrap-reverse**：元素沿着==辅轴反方向==换行

![1616838886908](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616838886908.png)





##### **==flex-flow属性==**

上面两个属性==flex-direction==和==flex-wrap==的简写属性

![1616839028941](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616839028941.png)

相当于横向排列，并且换行







##### **==justify-content属性==**

如何分配**主轴上的空白空间**（主轴上的元素如何排列）

可选值

flex-start：元素沿着主轴**起边**排列

flex-end：元素沿着主轴**终边**排列

![1616839529069](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616839529069.png)

center：元素**居中**排列

![1616839546256](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616839546256.png)

space-around：空白分布到**元素两侧**

![1616841895130](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616841895130.png)

space-between：空白均匀分布到**元素间**，最两遍不会分布

![1616841974368](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616841974368.png)

space-evenly：空白分布到元素的**单侧**



**==ps==**：有**justify**一般都是主轴上的属性，有**align**一般都是辅轴上面的属性



##### **==aline-items属性：==**

**==元素在辅轴上面如何对齐==**

可选值：

stretch：默认值，将元素的**长度设置为相同的值**

flex-start：元素不会拉伸，**沿着辅轴起边对齐**

![1616842347536](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616842347536.png)

flex-end：沿着辅轴的**终边**对齐

![1616842548277](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616842548277.png)

center：居中对齐

![1616842593536](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616842593536.png)

 baseline：基线对齐

可以利用上面这两个属性：==justify-content和align-items==，来做到**==垂直水平双居中==**

![1616842644962](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616842644962.png)

![1616842656639](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616842656639.png)



##### **==align-content属性==**

**<font color='red'>对单行弹性盒子无效</font>**，辅轴空白空间的分布，跟**justify-content**的属性、用法一样

center：元素**居中**排列

![1616843256084](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616843256084.png)

flax-start：元素沿着辅轴**起边**排列

![1616843352701](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616843352701.png)

flex-end：元素沿着辅轴**终边**排列

![1616843383009](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616843383009.png)

space-around：空白分布到**元素两侧**

![1616843483084](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616843483084.png)

space-between：空白均匀分布到**元素间**，最两遍不会分布

![1616843588256](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616843588256.png)

















 

























#### 弹性元素的属性



##### **==flex-grow属性==** （弹簧拉长）

指定弹性元素的伸展系数

设定的是==当**父元素有多余空间**的时，子元素如何伸展==

父元素的剩余空间，会按照比例进行分配

语法：**==flex-grow:比例数==**;

**flex-grow默认为0**，表示 弹性元素不会分配弹性盒的剩余空间

可以为每个元素分设置flex-grow属性，也可以统一设置

​	**统一设置为1**，表示父元素的剩余空间平均分配

​	如果每个子元素都设置了flex-grow，制定了不同的比例数，剩余空间会**按照比例分配**



例子：弹性容器中，弹性容器分别设置

![1616837584496](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616837584496.png)

![1616837604789](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616837604789.png)

统一设置：

![1616837667289](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616837667289.png)

![1616837676220](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616837676220.png)











##### **==flex-shrink属性==**（弹簧压缩）

指定弹性元素的收缩系数

当**==父元素中的空间不足以容纳所有的子元素==**时，如何对子元素进行收缩

用法和flex-grow类似

比例数统一设置成1时，等比例收缩

当比例系数统一设置成0，就不会收缩

![1616838069503](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616838069503.png)

分别指定比例系数，系数大的收缩的多，弹性元素会比较小

![1616838120378](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616838120378.png)

![1616838129093](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616838129093.png)



##### **==align-self属性==**

用来覆盖当前弹性元素上的**align-items属性**

align-items之前是**弹性容器统一设定**的，这里**单独为每一个弹性元素单独设置**，会覆盖之前统一设置的

![1616843876609](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616843876609.png)

![1616843884706](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616843884706.png)



##### **==flex-basis属性==**（弹簧原长）

flex-basis指定的是元素在**主轴**上的基础长度，==指定具体长度后，会覆盖之前指定的元素的大小==

如如果**主轴是横向**的则该值指定的就是元素的宽度

如果**主轴是纵向**的则该值指定的是就是元素的高度

**==默认值是auto==**，表明参考元素之前设定的自身高度或宽度



##### **==flex属性==**

弹性元素属性的**==简写样式==**，可以同时设定弹性元素的**三个属性（拉伸、压缩、原长）**

可选值：==增长 缩减 基础==，三个值**顺序不能变**，中间用**空格隔开**

同时还提供三个参数值：

​	**initial**相当于flex: 0 1 auto

​	**auto**相当于flex: 1 1 auto

​	**none**相当于flex:0 0 auto"弹性元素没有弹性	



##### **==order属性==**

通过为弹性元素设定order值，来**控制元素的排列顺序**

可选值就是数字

通过一个属性来改变元素的顺序布局

![1616844751801](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616844751801.png)

![1616844760337](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616844760337.png)





### 像素

![1616899103758](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616899103758.png)



### 手机端像素

![1616899849534](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616899849534.png)

智能手机的像素点远远小于计算机的像素点

![1616899887293](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616899887293.png)



默认情况下，**==移动端==**的网页都会将视口设置为**==980像素（css像素）==**

当网页的css像素超过了980px时，为确保移动端的网页能正常显示，**==移动端的浏览器会自动将网页进行缩放==**来完整显示网页（在网页没有专门进行移动端的适配开发时）



所以基本大部分的pc端网站都可以在移动端中正常浏览，但是往在都不会有一个好的体验

为了解决这个题，==大部分网站都会专门为移动端设计网页==



### 完美视口

![1616902141217](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616902141217.png)



每一款移动设备设计时，都会有一个**==最佳的像素比==**

般我们只需要将像素比设置为该值即可得到一个最佳效果

将像素比设置为最佳像素比的视口大小我们称其为**==完美视口==**





可以通过**==meta标签==**来**==设置视口大小==**

建立一个mate标签，**==name属性为viewport，content属性为width=像素值==**，可以为网页指定，在网页占满手机全屏时，页面宽度为多少像素，相当于把网页放大，一个**css像素由几个物理像素来呈现**



当mate标签，**==name属性为viewport，content属性为width=device-width==**

==**这样就是自动适配所有移动端最佳像素比，不用再指定了**==

![1616902920381](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616902920381.png)



此外还有一个initial-scale属性，这是设置网页的**==初始化缩放==**，完美视口的初始化缩放设置为一

所以**<font color='orange'>一般完美视口使用以下的标签</font>**

![1616903009877](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616903009877.png)





### vw单位

不同的设备完美视口的大小是不一样的

​	iphone6 -- 375

​	ihone6plus -- 414

由于不同设备视口和像素比不同，所以同样的375个像素在不同的设备下意义是不一样

​	比如在 iphone6中375就是全屏，而到了plus中375就会缺一块

**==所以在移动端开发时，就不能再使用px来进行布局了==**



vw表示的是视口的宽度( viewport width)

100vw = 1个视口的宽度

1vw = 1%视口宽度

vw这个单位永远**==相对于视口宽度==**进行计算



**==设计图的宽度==**一般都是750px、1125px、**==375的2倍3倍==**....

**==换算：==**

使用vw作为单位，创建一个48px*35px大小的元素

100vw=750px（设计图的像素）0.1333333333vw=1px

6.4vw=48px（设计图像素）



### vw的适配

可以用之前讲过的rem来做适配

**==1rem=html中font-size的值==**

font-size中设定值为vw单位，之后网页中的宽高用rem来作为单位

**==但是大部分浏览器网页中现在规定字体大小最小为12px==**

比如面那个例子，所以还不能用font-size：0.133333333vw

此时font-size的值为1px，太小了

所以有一种常见的解决方案时将**==font-size设置为5.33333vw=40px==**

之后就就可以将设计图上的长度/40得到rem为单位的值

![1616910167878](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616910167878.png)

跟上面那个直接换算没有本质区别，只是方便了换算，可以乘除整数了

### 响应式布局

**==响应式布局==**

网页可以根据不通的设备或窗口大小呈现出不同的效果

使用响应式布局，可以使一个网页适用于所有设备

**==响应布局的关键就是媒体查询==**

通过媒体查询，可以为==不同的设备==，或==设备不同状态==来分别设置样式

#### 媒体查询

使用媒体查询

**==语法==**：@media 查询类型{}

**==查询类型：==**

**<font color='orange'>①</font>**	

**==媒体类型：==**

​	all：所有设备

​	print：打印设备

​	screen：带屏幕的设备

​	speech：屏幕阅读器

可以使用逗号连接多个媒体类型

![1616915379510](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616915379510.png)

ps：也可以在媒体类型前面加上only，这是为了兼容老版本的浏览器，老版本浏览器遇见only直接就忽略，没有only的话就可能报错

![1616915630420](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616915630420.png)

**<font color='orange'>②</font>**

**==媒体特性==**

**width**：视口的宽度（视口等于指定宽度时生效

**height**：视口的高度（视口等于指定高度时生效

**min-width**：视口的最小宽度（视口大于等于指定宽度时生效

**max-width**：视口的最大宽度（视口小于等于指定宽度时生效

上面说的生效的内容是后面大括号里面的符合完整css语法规则的样式

语法：

**==@media(媒体特性){ css样式}==**



![1616916263440](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616916263440.png)



样式切换的分界点，我们称其为**==断点==**，也就是网页的样式会在这个点时发生变化

**==一般比较常用的断点==**

​	小于768**超小屏幕**max-width=768px

​	大于768**小屏幕**min-width=768px

​	大于992**中型屏幕** min-width=992px

​	大于1260**大屏幕**min-width=1260px



可以多个媒体特性一起用

多个媒体特性中间用**==逗号==**隔开，表示**==或==**

![1616917948540](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616917948540.png)

多个媒体特性中间用**==and==**相连，表示**==与==**

![1616917989741](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616917989741.png)

**==同时还可以指定媒体类型==**，也用and连接起来

![1616918087792](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616918087792.png)





























### PS

**==title属性==**

用于将某一段文字设置一个标签，鼠标停留在文字上就会出现文字提示

![1616225564695](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616225564695.png)

![1616225572773](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616225572773.png)





............................................................................................................

**==快捷键==**：**ul>li**，然后点击tab键，直接就生成了如下格式代码

![1616226829310](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616226829310.png)

**ul>li*3**，就会生成带有三行的一个列表

==写完一段字符串，按tab键，就会生成名为这段字符串的一个标签，无论这个标签是否存在==



**==快捷键==**：db按tab，会直接得到display:block

![1616483133216](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616483133216.png)



**==快捷键：==**

.box就创建了

![1616682817886](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616682817886.png)

.box$*3就创建了

![1616682856801](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616682856801.png)

...........................................................................................................

快捷键：输入**==.box1==**,然后按tab键，就自动生成了如下结构

![1616239916510](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616239916510.png)

**==.box1+.box2+.box3==**然后按tab键，就自动生成了三个div块

...........................................................................................................

快捷键：==shift+ctrl+R==代表当前行向下复制一行



快捷键：**==w190==**，然后点击tab，就直接生成了**width: 190px;**

​		h190，然后点击tab，就直接生成了**height: 190px;**



............................................................................................................

**==line-height 属性==**

设置行间的距离（行高）。

注意：不允许使用负值。

**==该属性可以被继承==**



**多用于以下这种情况**：

要让一个**==文字在父元素中垂直居中==**，只需要将父元素的line-height和height设置成相等就行

![1616308106620](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616308106620.png)





...........................................................................................................

去除超链接的下划线

**==text-decoration属性==**，将他设置为none就能去掉下划线

![1616308564020](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616308564020.png)



...........................................................................................................

**==font-weight:bold==**

给font-weight属性设置bold值，代表将文字加粗



...........................................................................................................

**==background-clip属性==**

![1616335144883](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616335144883.png)





............................................................................................................

用fontawesome字体图标，将图标放到==li标签==中

==li原来是块元素==，fontawesome中预设的css的样式就把==li改成了行内元素==，图标就会跟后面的在一行





............................................................................................................

在div中可以将元素的元素显示的类型**==display设置成table-cell==**，将其设置成一个单元格，这样能够使用**==vertical-align:middle（这个之前只能在文本和表格中使用）==**来设置子元素的==垂直对齐方式==

元素变成table-cell后，比较特殊，他**==只能跟同是table-cell的元素在一行，其他元素不能跟其同行==**

![1616499671667](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616499671667.png)





............................................................................................................



**==min-width属性==**：表示元素的最小宽度

一般用于body标签，当浏览器边缘缩放时，**==防止body过小导致子元素出现问题，设置的最小宽度==**，再往小了缩小浏览器，body的大小就不跟着变化了





............................................................................................................

transition：为元素设置过渡效果





............................................................................................................

编写网页时，为元素命名样式，如果是制作广告栏，有时候**class命名ad**，里面的图片有时候会被浏览器自动拦截，可能是当做广告了，**可能跟浏览器的某些插件有关**



............................................................................................................

设置**==网站的图标==**（在标题栏和收藏栏）
​	网站的图标一般都存在网站的根目录下面，名字一般都叫做favicon.ico

**==在head标签中，用link标签引入，rel属性值为icon==**

![1616593350356](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616593350356.png)















### 错误记录

报错parsing error: invalid version tag

和Failed to decode downloaded font

是因为没有吧webfonts导入到项目文件中！！！！



















































