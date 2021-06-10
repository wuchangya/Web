# 渐进式解释

渐进式意味着你可以将Vue作为你应用的一部分应用入其中，分阶段的将几部分应用vue，带来简更丰富的交互体验。（或者说由浅及深，一点点了解）

# 安装

![1617022257948](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617022257948.png)

# 杂乱简介

#### 范式

vue编程范式：==声明式编程==

原来js变成范式：==命令式编程==

声明式编程会将数据和页面完全分离

#### el、data、methods

示例：

![1617024630749](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617024630749.png)

创建Vue类的一个实例app

==el属性==：该属性決定了这个Vue对象挂载到哪一个元素上，很明显，这里挂载到了id为app的元素上

==data属性==：该属性中通常会存储一些数据

​	这些数据可以是我们直接定义出来的，比如像上面这样。

​	也可能是来自网络，从服务器加载的。

==methods属性==：将vue对象的一些方法定义到methods属性中去

​		可以直接写一个方法（相当于**方法名:匿名函数**）

![1617106718251](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617106718251.png)

​		也可以直接写一个函数，连function也不写，之前没这么写过（这是es6的函数增强写法）

![1617106746038](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617106746038.png)

#### 响应式的意思

vue的==响应式==的意思就是，比如上面定义的Vue类的一个实例app，修改data里面的属性值，界面就会自动进行修改

#### v-for简单示例：

v-for后面的双引号中格式：**=="(数组项,数组下标) in 数组名"==**

或者**=="数组项 in 数组名"==**

后面在data中追加元素的时候，**==追加的也可以在列表中渲染出来==**

![1617025468035](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617025468035.png)





#### 语法糖的意思

@click就相当于v-on:click，@click是v-on:click的语法糖，（语法糖就是一种语法的简写形式，因为简写，相当于尝到了甜头，取名为语法糖

v-on:click=""，引号之间直接写methods里面方法的名字（也就相当于函数）

计数器例子

![1617027310618](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617027310618.png)



# ==vue中的MVVM==

*MVVM*是Model-View-ViewModel的简写。它本质上就是MVC 的改进版，这两个都属于架构模式的一种

*mvc*一般指MVC框架。经典*MVC*模式中，M是指业务模型（数据层），V是指用户界面，C则是控制器



**==MVC：==**

1）V"视图层"（View）。它是提供给用户的操作界面，是程序的外壳。

2）M"数据层"（Model），也就是程序需要操作的数据或信息。

3）C"控制层"（Controller），它负责根据用户从"视图层"输入的指令，选取"数据层"中的数据，然后对其进行相应的操作，产生最终结果。

**==vue中的MVVM：==**



![1617027723563](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617027723563.png)

![1617027736067](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617027736067.png)

上面计数器的例子MVVM解释

![1617028110145](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617028110145.png)

![1617028367508](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617028367508.png)





# Vue中的options

目前来讲，Vue实例对象中有以下三种属性

![1617086148110](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617086148110.png)

el属性中使用==document.querySelector()==方法是一样的，此方法相当于el挂载的底层实现

![1617086429773](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617086429773.png)

组件中的data必须是一个函数

# Vue的生命周期



一个vue示例对象创建的过程中，，vue会做很多操作，会有很多回调函数

#  插值操作

## mustache语法

插值操作：将data中的文本数据插入到HTML中

可以通过Mustache语法：双大括号语法（胡子语法）

 Mustache语法中，不仅仅可以直接写变量，也可以写一些简单的表达式

一个双括号中可以使用多个变量，用+加号加起来，也可以在两个变量之间添加空格' '

也可以在双括号中进行简单地算数表达式

![1617089893894](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617089893894.png)

![1617089861501](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617089861501.png)

## v-once

v-once用来阻断vue对页面某个数据的响应式的改变

v-once只是一个指令，后面没有赋值

该指令表示元素和组件（组件后面オ会学习）==只渲染一次，不会随着data中数据的改变而改变==

![1617090222674](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617090222674.png)

![1617090206048](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617090206048.png)

## v-html

当data中从服务器中获取的数据是HTML代码，用变量呈现在页面上，想解析这个HTML代码，获取最后的样子，就需要到v-html属性

v-html属性的值就是服务器返回的这个HTML代码变量

![1617091143159](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617091143159.png)

## v-text

想在页面中展示data中的文本时，除了使用双括号语法，还可以使用v-text属性

用法像v-html，变量作为v-text属性的值

![1617091351641](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617091351641.png)

但是这种写法一般不用，**因为不灵活**，==比如要做文本的拼接，v-text就做不了==，下图这种写法就直接将v-text中属性的内容**覆盖**了，不会进行文本拼接

![1617091462282](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617091462282.png)

## v-pre

v-pre属性用来将标签中的双括号语法及其内容原封不动的进行展示，而不进行解析，使用的时候直接用v-pre，没有属性值

![1617091741206](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617091741206.png)

![1617091751571](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617091751571.png)

## v-cloak

cloak：斗篷

如果浏览器在加载页面的时候，vue实例的部分卡住了，页面中的数据会短暂的出现==未渲染之前的变量值（就比如出现了双括号语法这种源码）==，这种情况叫做插值表达式闪烁问题

**==v-cloak==**就是用来解决这种情况

将v-cloak属性添加到标签中，当vue对HTML代码进行解析，就**==会自动删除这个v-cloak属性==**，==在css中可以利用属性中有没有这个属性，来判断标签加载不加载==

有v-cloak则不进行展示，没有则进行展示

![1617092807050](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617092807050.png)

这里v-bloak用的是属性选择器

但是在以后这个方法也用不上了

# 绑定属性

## v-bind

![1617094546025](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617094546025.png)

mustache语法==不能用于a标签中href属性值的绑定==、==也不能用于img标签src属性值的绑定==，是没有用的

![1617094832815](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617094832815.png)

这时使用v-bind属性

**==语法：v-bind:href/src/....="data中的变量"==**

使用了v-bind浏览器就知道href和src属性值的内容是一个变量

![1617095126030](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617095126030.png)

像value、title、class这样需要赋值的属性都可以使用

**==v-bind的语法糖==**

直接使用**==:==**来代替**==v-bind:==**

## v-bind动态绑定class

 在使用v-bind:class=""时，可以想class传入一个==对象==，或者==数组==

### 对象方式绑定

对象的格式如下

**=={类名1:布尔值, 类名2:布尔值,......}==**

==布尔值为true==，如果在这个对象内联样式表中没有类名1或者类名2，浏览器渲染页面后直接在该元素的==内联样式表class==中==添加相应的类名==

如果==布尔值为false==的话，在该元素的==内联样式表class中删除相应类名==

一般class传入的对象中的==类名都是事先在css中定义好的==，方便动态的添加或者删除相应类名，达到删除或者添加某种样式的效果

![1617100481672](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617100481672.png)



例子：

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617099325806.png" alt="1617099325806" style="zoom:67%;" />

如果==class属性值中的对象太长==，可以将这种方法改写为把class属性值中的对象==**放到methods中**==

将此对象放到一个函数中去，**==返回值是这个对象==**就行，**==class的属性值==**就改为这个**==函数名()==**，记得要有括号，表示函数执行，才能有返回值

ps：像之前讲的点击事件的**响应函数**（下面的btnClick函数）就没有写括号，是因为**省略了**，其实是有的

![1617100135523](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617100135523.png)

### 数组方式绑定

 **==用的比较少==**

**==没有对象方式绑定那种可以动态增减类名的功能==**

数组里面可以使用==带双引号==的字符串，==表示类名==

![1617100710506](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617100710506.png)

也可以使用==不带双引号==的字符串，表示的是==data中的变量==，这时候就可以从服务器中读取实时的变量

![1617100687644](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617100687644.png)

同样也可以写到**==methods==**中去

![1617100924047](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617100924047.png)



## v-bind绑定style

绑定dass有两种方式：**==对象语法==**、**==数组语法==**

![1617106124440](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617106124440.png)

css的属性名或者class属性的值中如果有**==-==**作为连接符，比如：font-size，top-bar...，要么用**==驼峰式命名==**修改一下，要么用**==单引号引起来==**



### 对象方式绑定

跟绑定class相似，可以直接绑定样式名与属性值，作为一个对象传给style，此时样式的**==属性值必须要有双引号==**，**==样式名要么有单引号，要么不加单引号用驼峰命名法。==**

![1617105605676](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617105605676.png)



也可以绑定样式名与变量，变量从data中读取，**==变量不要加双引号==**

语法**=={样式名1:变量, 样式名2:变量,......}==**

![1617105742458](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617105742458.png)

（像font-size这样的有单位的属性值，data中的变量值可以是纯数字，单位放到绑定时再加）

同样，对象太长的话，可以放到methods中的函数中去，作为函数返回值调用

![1617105957579](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617105957579.png)



### 数组方式绑定

将每一个样式名:属性值  作为一个对象存到data中，一个样式，一个对象，把这些对象的名字放到数组中去

但这种方法很少用

![1617106207933](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617106207933.png)





# 计算属性的基本使用

![1617106404510](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617106404510.png)



在模板中通过差值法在页面中展示一些属性时，有时候需要将几个数值进行结合、组合在进行展示，==这种转换的操作就用到了**计算属性**==

就比如想要拼接字符串时

可以在HTML中使用的时候进行拼接

![1617107123832](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617107123832.png)

也可以在methods中写一个方法，到时候在**双括号中调用这个方法**

![1617107160596](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617107160596.png)

再或者就用**==计算属性==**来实现

vue对象中还有一个属性，**==computed属性==**

这个属性中保存着一些**==函数对象==**，专门用来进行计算，**==并且返回结果值的==**

**<font color='red'>本质是函数，为什么叫计算属性</font>**，因为vue是把它当做属性来用的，调用的时候**==不能使用括号==**，就跟属性一样

（所以命名习惯也跟函数不太一样，一般**函数命名时习惯上开头用动词**，比如getFullName，而**计算属性习惯上就直接用一个名词**就行了，比如fullName，因为属性也是名词）

![1617107734580](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617107734580.png)

**==methods每调用一次就执行一次，而计算属性调用多次，只执行一次，有缓存，效率更高==**

 ![1617108143196](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617108143196.png)



# 计算属性详解

## setter和getter

承接上面讲的fullName计算属性

![1617110543644](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617110543644.png)

上面这种写法其实是计算属性封装简写之后的样子，其内部实现比这复杂

每一个computed的属性都是一个对象，对象当中都会有两个属性：**==set和get==**，这两个属性里都是函数，（也就相当于两个方法）

其中**==get属性==**中函数中保存着我们在computed中自定义的函数，所以返回值是通过get属性里面的函数来实现的

==绝大多数set属性中的函数是空着的 ，不写也行==，所以每次都调用get方法，为了简便，就改成了我们常用的样子

![1617110517533](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617110517533.png)







set方法当中可以接受一个参数，当在控制台为computed中的fullName属性赋值时，就会调用set方法

在set中编写函数，根据参数值修改data中的值，data中的数据就会发生改变，get方法输出值也会发生改变

![1617111550073](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617111550073.png)

![1617111580280](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617111580280.png)



## 计算属性与methods对比

**==methods每调用一次就执行一次，而计算属性如果输入参数一样，浏览器会有computed的缓存，调用多次，只执行一次，效率更高==**

 当页面的数据变化时, methods中的方法会被重新调用(产生不必要的性能消耗), 而methods内的方法只有和自身有关的数据变化时才会被调用

computed只在初始化时被调用

methods会在数据变化时被调用, 即使变动的数据与自身无关

# 事件的监听

在前端开发中，我们需要经常和用于交互。

这个时候，我们就必须监听用户发生的时间，比如点击、拖拽、键盘事件等等

在Vue中使用**==v-on指令==**如何监听事件

![1617119886293](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617119886293.png)

为事件绑定的内容可以是函数、表达式、对象

​	表达式：

![1617119982770](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617119982770.png)

​	函数：

![1617120217097](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617120217097.png)



**==语法糖：@==**

## ==v-on参数的传递==

**<font color='red'>①</font>** ==**在事件监听的时候**==，**==如果不需要传递参数==**，事件绑定的方法**==可以不写括号==**（写与不写没影响。注意，只能是事件监听的时候，如果方法用在别的地方，可能就不能省略括号）



**<font color='red'>②</font>**如果函数需要参数，但是没有传入，**==但写了小括号==**，那么函数的形参为 **==undefined==**

**<font color='red'>③</font>**如果函数需要参数，但是没有传入，**==也没有写小括号==**，这时浏览器会默认将浏览器产生的**==event事件对象作为参数传进函数==**

**<font color='red'>④</font>**在调用方法时，在传入参数的时候如果想传入到浏览器产生的**event事件对象**，使用**==$event==**

![1617150069411](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617150069411.png)

![1617150205441](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617150205441.png)



## v-on修饰符

![1617150366857](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617150366857.png)

### .stop

阻止事件冒泡

在之前的js中使用：**==事件.cancelBubble=true==**，来阻止事件冒泡

![1615979925938](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615979925938.png)

在vue中使用**==.stop==**修饰符来阻止冒泡

![1617150706944](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617150706944.png)

### .prevent

阻止事件的默认行为

![1617150978533](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617150978533.png)

![1617151015970](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617151015970.png)

### .{keyCode|keyAlias}

在绑定的事件后面加上.{}，中括号里面写键盘按键的==Unicode编码==或者==按键缩写==，表明事件只是从特定按键触发时才回调，一般绑定在**键盘事件上**

![1617151473867](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617151473867.png)

### .native

监听**==组件==**根元素的元原生事件，直接用一般的事件绑定对于自定义组件是没有用的，需要加上.native

![1617152644858](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617152644858.png)

### .once

只触发一次回调

![1617152771335](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617152771335.png)

只在第一次点击时触发回调函数

# 条件判断

## v-if

在元素中添加v-if元素，为v-if属性赋值为布尔值

true，此元素及其子元素都会正常显示

false，此元素及其子元素都不会显示

![1617153034120](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617153034120.png)

布尔值也可以用变量来代替，变量写不写在双引号中都可以

![1617153148335](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617153148335.png)

## v-if和v-else结合使用

有v-if和v-else属性的两个标签必须**==相邻==**

![1617153572048](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617153572048.png)

## v-if和v-else-if和v-else结合使用

![1617153734852](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617153734852.png)

但一般这样写太复杂，阅读性不强，一般还是写在计算方法中

![1617154504529](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617154504529.png)

![1617154526603](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617154526603.png)

## 登录案例

![1617161574692](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617161574692.png)

![1617161607072](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617161607072.png)

上面这个问题在原生的js中就不会存在

当将vue应用到某个元素时，vue会自动将**创建虚拟dom**，作用是将创建的这些子元素通过虚拟dom放到**内存**中，然后再将虚拟dom渲染到浏览器上面，这是处于性能的考虑，**会尽可能复用已经存在的元素**

也就是说上面中if和else中的两个table和input标签**都是在用一个**，只不过else使用时将if中的标签进行修改就使用了，**并没有创建新的**。**input中的value值也保存下来了**

**==解决方法==**

可以在input标签中添加**==key属性==**，两个input标签key属性如果相同，表示可以复用，key不相同表示不可以复用

![1617163107165](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617163107165.png)



## v-show

v-show决定一个元素是否进行渲染

和v-if用法非常相似，为v-show属性赋予布尔值或者变量

但是**v-if**的false是将整个元素==从HTML标签中删去==

**v-show**是在元素标签中==添加一个行内元素display:none==，==HTML代码中还是有这个元素的==

![1617163785467](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617163785467.png)

![1617163951464](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617163951464.png)



当需要在显示与隐藏之间切换**==很频繁==**，使用show

当只有**==一次切换==**时，使用v-if（用的比较多）



# v-for

## 遍历数组

v-for是元素中的一个属性，遍历的时候，这个**元素就会进行多次遍历**

但是**标签写一次**就行

v-for后面的双引号中格式：**=="(数组项,数组下标) in 数组名"==**

或者**=="数组项 in 数组名"==**

后面在data中追加元素的时候，**==追加的也可以在列表中渲染出来==**

![1617164458659](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617164458659.png)

name是data中的一个数组数据

## 遍历对象

**<font color='red'>①</font>**在追历对象的过程中，如果只是获取一个值，那么获取到的是**==value==**

格式：**==value in 对象名==**

![1617164775622](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617164775622.png)

**<font color='red'>②</font>**获取key和value的值，格式：**==(value,key) in 对象名==**

value在前面

![1617164838578](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617164838578.png)

**<font color='red'>③</font>** 获取key、value、index的值，格式：**==(value,key，index) in 对象名==**

![1617165024692](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617165024692.png)

## v-for绑定key和非绑定key的区别

官方推荐我们在使用v-for时，给对应的元素或组件添加上一个：**==key属性==**。，key属性内容是每次遍历时的**==数组项==**

key属性的作用在于，当要往数组中插入新的内容时（使用的是**==diff的算法==**）

默认情况下是从插入的地方，将索引和数组项的对象关系往后移一位，效率很低

加上了key属性时，Diff算法就可以正确的识别此节点，**==直接找到正确的位置区插入新的节点。==**

![1617181216733](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617181216733.png)

![1617181573858](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617181573858.png)

有key内存里实际就是链表了，所以插入操作效率高了

**==但是这样的话，数组中的数据如果有重复，key属性的值也会重复，浏览器就会报错==**



<font color='red'>**另外vue中在使用相同标签名元素的过渡切换时，也会使用到key属性，其目的也是为了让vue可以区分它们，否则vue只会替换其内部属性而不会触发过渡效果。**</font>

# 数组中哪些方法是响应式的

像平时我们修改了data中的数据时，页面会自动进行实时的刷新

这是因为数据是响应式的，vue的内部会监听数据的变化，vue会根据新的数据，重新渲染出一个虚拟的dom

虚拟的dom把我们的真实dom进行修改



**数组中有的方法和操作是可以将页面进行响应式改变，但有的却不能**

比如，**==通过索引值修改数组中的元素，此操作并不是响应式的==**。data中的数据是被修改了，但是页面中渲染的结果不能被修改，还是之前的值

![1617184580663](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617184580663.png)

如果想修改数组中的元素，可以使用**<font color='red'>①</font>** **==splice()方法==**，此方法是响应式的

**<font color='red'>②</font>**或者使用**==vue中==**有一个方法：**==set()==**

**三个参数**：

​		要修改的对象

​		索引值

​		修改后的值

![1617184480356](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617184480356.png)









**==以下的数组的方法是响应式的==**：

push() ：在数组最后添加**==一个或多个==**元素

pop()：删除数组中的最后一个元素

shift()：删除数组中的第一个元素

unshift()：在数组最前面添加**==一个或多个==**元素

splic():删除元素、插入元素、替换元素

sort()：排序

reverse()：翻转数组





# vue中的过滤器

简单介绍一下过滤器，顾名思义，**==过滤就是一个数据经过了这个过滤之后出来另一样东西，可以是从中取得你想要的，或者给那个数据添加点什么装饰，那么过滤器则是过滤的工具。==**例如，从['abc','abd','ade']数组中取得包含‘ab’的值，那么可通过过滤器筛选出来‘abc’和‘abd’；把‘Hello’变成‘Hello World’，那么可用过滤器给值‘Hello’后面添加上‘ World’；或者把时间节点改为时间戳等等都可以使用过滤器。

## 过滤器定义

首先，过滤器可在new Vue实例前注册全局的，也可以在组件上写局部。

**全局过滤器：**

```javascript
Vue.filter('globalFilter', function (value) {

  return value + "!!!"

})
```



**组件过滤器（局部）：**

```javascript
filters:{

    componentFilter:function(value){

          return value + "!!!"

    }

  },
```

**上面有种写法有个需要注意的问题：==全局注册时是filter，没有s的。而组件过滤器是filters，是有s的==，这要注意了，==虽然你写的时候没有s不报错，但是过滤器是没有效果的==**

**==过滤器调用的时候不用写括号==**



## 过滤器的使用方法

用法有二：

**一，在双花括号插值**

**=={{ 'ok' | globalFilter }}==**

**二，在v-bind表达式中使用**

<div v-bind:data="'ok' | globalFilter" ></div>

上面简单介绍了一下过滤器的调用，那么接下来我们讲解一下过滤器的参数写法

> ==**一、{{ message | filterA | filterB }}**==

上述代码中，message是作为参数传给filterA 函数，而filterA 函数的返回值作为参数传给filterB函数，最终结果显示是由filterB返回的。



![img](https://upload-images.jianshu.io/upload_images/13172338-0c1252932ee2dad7.png?imageMogr2/auto-orient/strip|imageView2/2/w/493/format/webp)

> **==二、 {{ message | filterA('arg1', arg2) }}==**

上述代码中，filterA的第一个参数是message，依次是‘arg1’,arg2



![img](https://upload-images.jianshu.io/upload_images/13172338-f2738df4bed6df51.png?imageMogr2/auto-orient/strip|imageView2/2/w/548/format/webp)

> **==三、 {{ 'a','b' | filterB }}==**

上述代码表示'a'和'b'分别作为参数传给filterB



![img](https://upload-images.jianshu.io/upload_images/13172338-978a8a5f8d5d5ad3.png?imageMogr2/auto-orient/strip|imageView2/2/w/541/format/webp)



# js中的高阶函数

filter、map、reduce这三个函数，其实可以看成三个方法

为了理解这三个方法的高级性，引入下面这个例子，这个例子可以用这三个函数进行优化



![1617196387041](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617196387041.png)





## filter



**==filter方法==**，是**==数组==**的一个方法（**<font color='red'>注意区别上面的过滤器</font>**）

**==语法：数组.filter(function(变量){........, return ....})==**

==参数==：一个回调函数

​	**回调函数的形参**是遍历的数组项

​	**回调函数的返回值**是布尔值

==作用==：将数组的**各个值进行遍历**，并且**每次遍历都执行一次回调函数**，此回调函数作用是进行某种判断，得出一个**布尔值**，==**通过函数来返回**==，通过返回的布尔值来决定是否将遍历的数组项添加到一个新的数组中去，作为==方法的返回值==**用一个新的变量来接受**。从而**达到过滤数组的目的**

==返回值==：一个新的数组

​	true：当返回true时，函数内部会自动将这次回调的**数组项**加入到**新的数组**中

​	false：当返回 false时，函数内部会过**滤掉这次的数组项**

![1617197168062](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617197168062.png)

## map

**==map方法==**（本质上是一种映射）

==语法==：变量=数组.map(function(形参){.......return 返回值})

==作用==：跟filter方法类似，也会**遍历数组的数组项**，将数组的每一项传入操作后添加到**新数组**

==参数==：参数是一个**回调函数**

​	**回调函数的形参**是遍历的数组项

​	**回调函数的返回值**是将数组项进行某种操作后的值

==返回值==：函数的返回值会添加到**新数组**

​	新数组作为方法的返回值，可以用一个**变量来接收**

![1617197772330](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617197772330.png)



## reduce

**==reduce方法==**（相当于一个递归操作）也是**数组**的一个方法

==作用==：对数组中所有数组项进行汇总计算，每次遍历都会使用**上次返回函数的返回值**和**此次遍历的数组项**，相当于**递归操作**（比如逐项累加...等等一些操作）

==语法==：

变量=数组.reduce(function(preValue,数组项)

{

​	.....,return 返回值

},preValue的初始值)

==参数==：**两个**

​	①递归函数，其中，preValue：**上一个函数的返回值**，当第一次遍历时，preValue就自定义的值，也就是此方法的第二个参数，n：**本次的数组项**

​	②preValue的初始值

==返回值==：递归操作后的**一个值**

![1617198758750](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617198758750.png)



至此，上面例子的优化写法如下：

![1617199447352](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617199447352.png)

使用箭头函数进一步优化：

![1617199533646](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617199533646.png)



# 表单绑定

## v-model基本使用

v-model实现表单的**==双向绑定==**，比如在**input标签、textarea标签**中等

在表单中使用了v-model属性后，如下图

**<font color='red'>双向绑定体现在</font>**：

​	data中的值可以作为文本框的默认值，**==data中的值改变，文本框中的值也会改变==**

​	如果直接在文本框中输入内容（value）也修改data中的数据值，**==value中的值改变，会影响到data中的数据改变==**

![1617200618294](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617200618294.png)

![1617200634889](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617200634889.png)



## ==v-model的原理==

v-model具体背后的原理如下：

![1617206051454](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617206051454.png)

原理实现例子：

![1617203922603](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617203922603.png)

文本框中的内容通过:value="message"来动态绑定data中的数据

文本框通过设置对input事件的监听，通过监听事件的返回函数来改变改data中的数据

其中input事件监听的改进

![1617204789927](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617204789927.png)



## v-model结合radio类型使用

radio可选按钮

![1617236472634](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617236472634.png)

![1617236499373](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617236499373.png)

如果使用v-model**绑定的是data中同一个变量**

之前用于将几个可选按钮相互互斥分为一组的==name属性就可以省略不写==

==由于v-model属性相同，这几个可选按钮仍是互斥的==

![1617236706324](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617236706324.png)

此时定义可选按钮的**==默认按钮==**时，之前使用value，现在就==直接指定data中绑定的变量值就行==就设置了默认按钮





## ==v-model结合checkbox类型使用==

checkbox复选框

分两种情况：单个勾选框和多个勾选框

**==单个勾选框==**：

![1617237288861](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617237288861.png)

![1617237309173](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617237309173.png)

单选框时v-model绑定的变量是一个**==布尔值==**

**==多个勾选框==**：

![1617237710084](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617237710084.png)

![1617237650231](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617237650231.png)

复选框的话，v-model绑定的变量就是一个**==数组==**，多选的value会被添加到数组中去



## v-model结合select类型的使用

**==select下拉列表==**

> select标签中还有**==option子标签==**，用来表示下拉选项
>
> ![1616503103746](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616503103746.png)
>
> ![1616503109786](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616503109786.png)

**<font color='red'>注意</font>**：select使用v-model时绑定在**==select标签中==**

和 checkbox一样， select也分单选和多选两种情况。

==单选==：只能选中一个值。 

v- model:绑定的是一个**==值==**。

当我们选中 option中的一个时，会将它对应的 ==value赋值到 data的变量中==

![1617239120824](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617239120824.png)



==多选==：可以选中多个值。

v-mode绑定的是一个**==数组==**

**==按住ctrl键==**，选中多个值时，就会将选中的 option对应的 ==value添加到data的变量的数组中==

![1617239434377](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617239434377.png)

![1617239383718](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617239383718.png)



## v-model修饰符

### .lazy修饰符

默认情況下，**v-model**默认是在input事件中根据输入框的数据**实时改变**data的数据。

lazy修饰符可以让数据在**==失去焦点==**或者**==回车==**时才会更新



### .number修饰符

默认情况下，v-model双向绑定时，通过v-model修改data中的数据时，传入的数据默认是**==字符串==**

哪怕使用的是**number输入框**，传入的也是字符串

即使data中的数据初始值是数字，不进行修改确实一直是number值，一旦修改又成了**string类型**

![1617261826155](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617261826155.png)

![1617261844413](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617261844413.png)

此时使用.number修饰符进行类型的指定

![1617261936814](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617261936814.png)

![1617261923067](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617261923067.png)



### .trim修饰符

去除字符串两边的空格

当在文本框中输入的字符串有很多空格时，绑定的data中的数据也会有很多空格

![1617262034232](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617262034232.png)

![1617262006400](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617262006400.png)

![1617262001486](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617262001486.png)



通过.trim来去除字符串两边的空格

![1617262127901](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617262127901.png)





# vue中watch的详细用法

在vue中，使用watch来响应数据的变化。watch的用法大致有三种。

## 1. 常用用法

```html
<input type="text" v-model="name"/>
```

```javascript
new Vue({
  el: '#app',
  data: {
    name: '咸鱼'
  },
  watch: {
    name(newVal,oldVal) {
      // ...
    }
  } 
})
```



直接写一个监听处理函数，当每次监听到 name 值**==发生改变==**时，执行函数。函数有两个参数，==**第一个：新的值，第二个：旧的值**==，两个参数可选，只写一个代表新的值

**也可以在所监听的数据后面直接加字符串形式的==方法名==：**

```javascript
watch: {
    name: 'nameChange'
 } 
```

## 2 .==立即执行(immediate和handler)==

第一种用法watch有一个特点，就是当值**==第一次绑定的时候，不会执行监听函数，只有值发生改变才会执行==**。

如果我们需要在**==最初绑定值的时候也执行函数==**，则就需要用到**==immediate属性。==**

比如当父组件向子组件动态传值时，子组件props首次获取到父组件传来的默认值时，也需要执行函数，此时就需要将immediate设为true。

```javascript
new Vue({
  el: '#app',
  data: {
    name: ''
  },
  watch: {
    name: {
    　　handler(newVal,oldVal) {
      　　// ...
    　　},
    　　immediate: true
    }
  } 
})
```



监听的数据后面写成对象形式，包含**==handler方法==**和**==immediate==**，**之前我们写的函数其实就是在写这个handler方法**；

immediate表示在watch中首次绑定的时候，是否执行handler，值为true则表示在watch中声明的时候，就立即执行handler方法，值为false，则和一般使用watch一样，在数据发生变化的时候才执行handler。

## 3 .深度监听

当需要监听复杂数据类型(对象)的改变时，**==普通的watch方法无法监听到对象内部属性的改变==**，只有data中的数据才能够监听到变化，此时就需要deep属性对对象进行深度监听。

```html
<input type="text" v-model="person.name"/>
```



```javascript
new Vue({
  el: '#app',
  data: {
    person: {id: 1, name: '咸鱼'}
  },
  watch: {
    person: {
      handler(newVal,oldVal) {
      // ...
    },
    deep: true,
    immediate: true
    }
  } 
})
```



设置deep: true 则可以监听到person.name的变化，此时会给person的所有属性都加上这个监听器，当对象属性较多时，每个属性值的变化都会执行handler。**==如果只需要监听对象中的一个属性值==**，则可以做以下优化：**==使用字符串的形式监听对象属性==**：



```javascript
watch: {
    'person.name': {
      handler(newVal,oldVal) {
      // ...
      },
      deep: true,
      immediate: true
    }
  }
```



这样只会给对象的某个特定的属性加监听器。

**==数组（一维、多维）的变化不需要通过深度监听，对象数组中对象的属性变化则需要deep深度监听。==**

















# 组件

## 实现和使用步骤

我们将一个完整的页面分成很多个组件。

每个组件都用于实现页面的一个功能块。

而每一个组件又可以进行细分。

![1617265522498](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617265522498.png)



组件的使用分成三个步骤

​	1.创建组件构造器

​	2.注册组件

​	3.使用组件。

![1617265961419](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617265961419.png)



## vue组件化的基本使用

```html
<div id ="app">
    <!-- 组件的使用 -->
	<my-cpn></my-cpn>
</div>	
<script src="./js/vue.js"></script>
<script>
	/* 创建组件构造器对象 */
	const cpnC = Vue.extend({
        /* 模板 */
		template:`
		<div>
			<h2>标题</h2>
			<p>内容</p>
			<p>内容</p>
		</div>`
	})
	/* 注册组件 */
	Vue.component('my-cpn',cpnC)
    
	const app = new Vue({
		el:'#app',
		data:{
		},
		methods:{
		}
	})
</script>
```

**==1.Vue.extend():==**

调用Vue. extend()创建的是一个**==组件构造器==**。

通常在创建组件构造器时，传入 **==templated()==**代表我们自定义组件的**==模板==**。

该模板就是在使用到组件的地方，要显示的HTML代码。

事实上，这种写法在**Vue2x的文档中几乎已经看不到了**，会直接使用下面讲到的**==语法糖==**，但是在很多资料还是会提到这种方式

**==2.Vue. component():==**

调用vue. component()是将刚才的组件构造器**==注册为一个组件==**，并目给它起一个组件的标签名称

所以需要传递**==两个参数==**：

​	1、注册组件的==标签名==

​	2、==组件构造器==

**==3.组件的使用==**

组件使用时必须在vue实例中使用，通过引入自己自定义的标签名使用



## 全局组件和局部组件

### 全局组件

上面在**==vue构造函数外面==**，通过Vue. component()注册的组件是全局组件

**==全局组件意味着可以在多个Vue的实例中使用==**



### 局部组件

一个网页中可以创建多个vue实例

不同vue构造函数挂载的的**==el属性值不同==**

当id不同时，就属于不同的vue实例

只能在同一个vue实例（id相同）中的组件叫**==局部组件==**



在**==vue构造函数当中注册组件==**

**==构造器==**还是在**==构造函数的外面==**

通过**==components属性==**

components属性中可以注册多个组件

属性内容是一个对象，对象的**属性值**是自定义的**标签名**，**属性值**是**构造器**

![1617269052861](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617269052861.png)



## 父组件和子组件



![1617269861630](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617269861630.png)

![1617269911246](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617269911246.png)

父组件和子组件的**构造器没有包含关系**，都放在vue构造函数外面就行。

**子组件的注册**(components属性)放在了**父组件的构造器**里面

**父组件的注册**放在了**vue构造函数**中

(这样看来，也可以将vue构造函数看成一个特殊的组件构造器，最顶层的组件，是所有组件的父组件，只不过目前template模板没用到)

上面这个例子中的子组件并**不能直接应用到vue实例中**去，如果想用，需要**再次在vue构造函数中注册一遍**





## 注册组件的语法糖

### 全局组件的语法糖

将组件的**构造器具体**内容当做参数，替换掉原来注册时**构造器变量**的位置

将注册和构造器写在一起

这样其实==构造器本质上还是使用的vue的extend方法==，只不过简写了，就不写extend了

![1617282935077](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617282935077.png)

### 局部组件的语法糖

局部组件同样可以将**构造器的具体内容**替换掉原来**构造器代表的变量**的位置

**extend方法**也可以**省略不写**

![1617283291983](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617283291983.png)



**==主要是省去了调用Vue. extend的步骤，而是可以直接使用一个对象来代替。==**



## ==组件模板抽离的写法==

之前在构造、注册组件时，在编写组件的模板时，每次都在js代码中使用字符串编写

这样格式混乱，且书写效率不高

**抽离方法：**

**<font color='red'>①通过script标签</font>**

可以将组件的模板标签抽离到另一个script标签中，==全局、局部==组件都可以用

**==script标签中嵌套HTML代码==**

script标签的**==type属==**性值为：**==text/x-template==**

并为script标签指定一个**==id属性==**，构造注册组件时，**==template属性==**的值为：**==#id属性值==**

**<font color='red'>注意：</font>**

组件的模板**==script标签应该只能包含一个根元素==**，也就是是说作为元素script的直系儿子的元素只能有一个

**<font color='red'>解决办法</font>**发是**==将script的子元素用一个div包裹起来==**

![1617283718409](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617283718409.png)



**<font color='red'>②使用template标签</font>**

直接新建一个template标签，不用写在script标签中

同样绑定一个**id属性**，将构造注册时的**template属性值**等于**#id属性值**

==全局、局部==组件都可以用

**<font color='red'>注意：</font>**（同script方法）

组件的模板**==template标签应该只能包含一个根元素==**，也就是是说作为元素<template>的直系儿子的元素只能有一个

**<font color='red'>解决办法</font>**发是**==将template的子元素用一个div包裹起来==**

![1617284465319](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617284465319.png)







## 组件中数据的存放问题

组件内部是**==不能访问vue构造函数的数据==**

组件是一个单独功能模块的封装

这个模块有属于自己的HTML模板，**也应该有属性自己的数据data**

这个**==data属性==**必须是一个**==函数==**

函数**==返回值==**是一个**==对象==**，对象里面保存着数据

![1617285769551](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617285769551.png)

 ![1617285945017](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617285945017.png)



**<font color='red'>为什么data这里必须是一个函数：</font>**

多个相同的组件在调用时，使用的data中的数据并不是同一个对象，**==相互之间没有影响==**

多个地方引用data数据时，引用的而并不是一个，**==每次都是一个新的函数返回值==**，相当于每个地方重新调用函数，返回值相互之间没有关系



如果data直接是一个对象的话，每次使用的话都是同一个对象（访问的是同一个内存地址），这样就会产生错误

**所以data函数返回值千万不能返回一个在全局声明的一个obj对象**



## 父子间通信



**==先说结论==**

父传子：

子组件中用props声明自定义的名称后，在子组件的模板中用自定义的名称进行双括号引用

父组件中在子组件实例中具体使用的时候，使用v-bind来动态绑定自定义名称和父元素中data中的数据名

子传父：

在子组件中，通过$emit()来触发事件。

在父组件中，通过v-on来监听子组件事件。

### 父传子props

子组件是不能引用父组件或者vue实例的数据的。

但是，在开发中，往往一些数据确实需要从上层传递到下层

比如在一个页面中，我们从服务器请求到了很多的数据。

其中一部分数据，并非是我们整个页面的大组件来展示的，而是需要下面的子组件进行展示。

这个时候，并不会让子组件再次发送一个网络请求，而是直接**大组件（父组件）将数据传递给小组件（子组件**）。

如何进行父子组件间的通信呢：

​	==**通过 props向子组件传递数据**==

​	==**通过事件向父组件发送消息**==

![1617290150137](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617290150137.png)



真实的开发中，==vue实例和子组件的通信==和==父组件和子组件的通信==过程是一样的。

#### props属性

在子组件中，**==使用 props属性来声明需要从父级接收到的数据==**。

**==props属性==**的值有两种：

方式一：**==字符串数组==**，数组中的字符串就是传递时的名称

方式二：**==对象==**（**使用的比较多**），对象可以==设置传递时的**类型**==，变量名称就为属性了，格式为   **==变量名称:类型==**

​	也可以设置默认值，设置默认值的时候变量名称就为一个**==对象==**，对象指明了**各种默认值：**

type：类型

default：父元素没有参数传过来时的默认值（写入默认值）

required：某数值在传值时是否是必要的true、false，**为true不传会报错**

==注意==：类型是对象或者数组时，==默认值default==必须是一个==函数==，通过函数的==返回值==返回数组或者对象

**<font color='red'> 具体见下图:</font>**

![1617295427308](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617295427308.png)

props中的type属性可以进行**数据验证**

![1617295985734](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617295985734.png)

#### **<font color='red'>完整过程：</font>**

从父元素中接收数据，**<font color='orange'>子组件构造器</font>**中先用**==props属性==**自定义好接收时使用的变量

用props声明自定义的名称后，在**<font color='orange'>子组件的模板中</font>**用**==自定义的名称==**进行双括号引用

父组件中在**<font color='orange'>子组件实例中</font>**具体使用的时候，使用**==v-bind==**来动态绑定**==自定义名称==**和**==父元素中data中的数据名==**，如此就能做到父元素向子元素通信







我们先来看一个最简单的 props'传递（**<font color='red'>注意这里为了方便起见，将vue构造对象作为了父元素，其实vue构造对象本来就可以这么看，这里是为了结构清晰</font>**）

```html
<!-- 父组件中子组件的调用 -->
<div id ="app">
	<cpn v-bind:cmovies="movies" :cmessage="message"></cpn>
</div>
<!-- 子元素的模板 -->
<template id="cpn">
	<div>
		<ul>
			<li v-for="item in cmovies">{{item}}</li>
		</ul>
		<h2>{{cmessage}}</h2>
	</div>
</template>
<script src="./js/vue.js"></script>
<script>
/* 子组件的构造器  这里是简写形式，
在父组件中将这个对象作为了构造器引入，这里可以省略Vue.extend */
	const cpn = {
		template:'#cpn',
        /* 使用 props属性来声明需要从父级接收到的数据 */
		props:['cmovies','cmessage'],
		data(){
			return {}
		},
		methods:{
		}
	}
    /* vue构造函数，在这里看成是父组件 */
	const app = new Vue({
		el:'#app',
		data:{
			message:'你好',
			movies:['海王','海贼王','海尔兄弟']
		},
		methods:{
		},
        /* 在父组件中注册子组件
		 这里没有使用语法糖
		 使用了es6中属性的增强写法*/
		components:{
			cpn
		}
	})
</script>
```



#### ==props驼峰标识==

props中声明的变量名不能使用驼峰标识

使用驼峰标识时，**==vue实例中v-bind不能识别驼峰标识==**

**一般变量名字都用小写就可以了**，不按照驼峰标识使用大写字母

如果真想用，可以**在==props声明==中使用驼峰标识，在==子组件模板==中也可以使用驼峰标识，唯独在==vue实例==的v-bind中换成小写，原来大写的地方用==-==连接**

==也就是==只需要在vue实例中的v-bind后面做一下转换就行，因为这里v-bind不识别驼峰标识

![1617322910978](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617322910978.png)

比如上面这样，**==props中使用cInfo==**，**==子组件的模板==**时也可以使用cInfo，**==v-bind中使用c-info==**，这样也当做是一个变量



### 子传父$emit

```html
<!-- 父组件的使用，且调用子组件 -->
<div id ="app">
	<cpn @itemclick="cpnClick"></cpn><!-- 监听自定义事件 -->
</div>

<!-- 子组件模板 -->
<template id="cpn">
	<div>
		<button type="button" v-for="item in categories"
		@click="btnClick(item)"><!-- 监听点击事件，返回函数是子组件中的方法，用来向父组件发射事件 -->
			{{item.name}}
		</button>
	</div>
</template>

<script src="./js/vue.js"></script>
<script>
	
	/* 子组件构造 */
	const cpn = {
		template: '#cpn',
		data(){
			return{
				categories:[
					{id:'aaa', name:'热门手机'},
					{id:'aaa', name:'电脑办公'},
					{id:'aaa', name:'家用家电'},
					{id:'aaa', name:'数码手机'}
				]
			}
		},
		methods:{
			btnClick(item){
				/* 向父组件发射事件 */
				this.$emit('itemclick',item)
			}
		}
	}
	/* 父组件（vue构造函数） */
	const app = new Vue({
		el:'#app',
		data:{
			message:0
		},
		methods:{
			cpnClick(item){
				console.log(item.name)
			}
		},
		components:{
			cpn
		}
	})
</script>
```

在子组件中，通过$emit()来触发事件。

在父组件中，通过v-on来监听子组件事件。

**<font color='red'>具体步骤：</font>**

**<font color='red'>①</font>**在子组件的模板中遍历子组件中要给父组件传的data中的数据

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617328954753.png" alt="1617328954753" style="zoom: 80%;" />

**<font color='red'>②</font>** **模板中**同时为按钮击事件**==绑定返回函数（此函数在子组件构造器中定义）==**，将遍历的**数据**作为**函数的参数**

![1617355137040](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617355137040.png)

**<font color='red'>③</font>**在**子组件构造器**的methods中**==编写返回函数==**，向父组件中发射自定义事件

格式：**==this.$emit('自定义事件名',数据参数)==**

**数据参数**是上一步返回函数调用时传入的参数

![1617328832981](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617328832981.png)

**<font color='red'>④</font>**父组件在**==使用实例的时候==**监听自定义事件，并为监听函数绑定返回函数

自定义事件的返回函数比较特殊，不指明函数的参数时，**==默认函数返回值==**传的是上一步中的**==数据参数==**（其他监听事件的返回函数不写参数，默认的参数是**event事件对象**）

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617332122415.png" alt="1617332122415" style="zoom:80%;" />

**<font color='red'>⑤</font>**自定义事件的监听函数在父组件（这里指的是vue构造函数）的methods中定义，并可以使用上一步默认传入的数据参数

这样子元素中的数据在父元素中就得到了使用

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617332207090.png" alt="1617332207090" style="zoom:80%;" />



另一个完整的例子：

![1617333349863](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617333349863.png)



#### 总结：

**<font color='red'>①</font>**

在子组件的模板中，设置一个监听事件（click、input）

子组件将需要传给父组件的数据作为参数，传给监听事件的返回函数

监听事件的返回函数在子组件构造器中定义，用this.$emit('自定义事件名',数据参数)来向父组件发射事件

**<font color='red'>②</font>**

父组件在使用实例的时候监听上面的自定义事件，这里的监听事件的返回函数在父组件的构造器中定义

父组件的监听事件的返回函数中，默认传过来的参数就是$emit方法中的数据，这里就可以使用了



**==两个监听事件与返回函数：==**

​	**子组件模板中**==常规的监听事件==和==返回函数==（==参数：数据==， ==功能：发射自定义事件和数据==）

​	**父元素实例中**的==自定义事件的监听==和==返回函数==（==参数：数据==，==功能：可以使用子组件的数据了==）





如果父组件和子组件中数据需要双向绑定：

https://www.bilibili.com/video/BV15741177Eh?p=64&spm_id_from=pageDriver

要点：双向绑定时vue官方建议不要修改props中的数据，而是利用子组件中的data

​	在子组件中也可以通过this来获取props中的属性 



## 父子组件的访问

有时候我们需要父组件直接访问子组件，在父组件可以直接操作子组件的内容，比如中拿到子组件中的方法、属性来使用

或者子组件直接访问父组件，或者是子组件访问根组件。

父组件访问子组件：使用 $children或$refs

子组件访问父组件：使用$parent

### 父访问子

#### $children

在父组件可以直接操作子组件的内容，比如中拿到子组件中的方法、属性来使用

在父组件中通过**==this.$children==**来获取子组件

返回的是一个**==数组==**

数组中包括多个**==子组件对象==**（**多个同种类型的子组件在数组中也不是一个对象，是多个对象**）

各个子组件对象中**==包含各种属性、方法、数据==**

通过**==数组索引==**来读取子组件对象，在通过子组件对象调用各种方法和属性



![1617359677580](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617359677580.png) 

==ps:==因为要是用数组索引，索引值并不是一成不变，这种方法不太好

​	实际开发很少用，一般都是用$refs

#### ==$refs==

使用方法：

需要获取哪个子组件实例，就在子组件实例的标签上加一个**==ref属性==**

可以在==多个==子组件实例上面添加ref属性

**==属性值为自定义的名字==**，用来区分有ref属性的子组件实例

在父组件中通过**==this.$refs.名字.属性==**

**==this.$refs==**中返回的是一个**对象**，对象里是所有有ref属性的子组件

不添加ref属性时，默认是一个**空的对象**

![1617360578521](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617360578521.png)

![1617360643009](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617360643009.png)



### 子访问父

#### $parent访问父组件

跟前面的属性类似，子组件通过**==this.$parent==**来获取父组件，返回的是一个对象

对象里面是父组件里面各种属性、方法、数据

![1617364406840](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617364406840.png)

但是这个属性==很少用==，因为此属性用在子组件构造器中

如果要访问父组件的属性，这个子组件在多个地方使用过，==所有的父组件都会被访问==，但有的父组件没有相关属性，就会报错

如果真想用，父组件一般就一个或少数个，==复用性很差==



#### ==$root访问根组件==

子组件通过**==this.$root==**来访问**根组件**

返回值是一个对象，即vue实例，对象里面是vue实例的各个属性、方法、数据

![1617364928239](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617364928239.png)



## 插槽slot

![1617365217076](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617365217076.png)



组件的插槽是为了让我们封装的组件**==更加具有扩展性==**

==**让使用者可以決定组件内部的一些内容到底展示什么。**==

就比如写好的组件，想在组件的**指定位置放置新的内容**，或者组件多次复用的时候，组件相应位置想放入新的内容不同，这时候就需要组件的插槽

### 插槽的基本使用

在组件模板的指定位置放置一个**==slot标签==**

在调用组件实例的时候在**==组件的标签里面==**直接写入新的HTML代码就行了

![1617365974462](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617365974462.png)

![1617366084832](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617366084832.png)



还可以为插槽中**==指定默认内容==**

**==在组件的模板中，放置插槽时，在slot标签里面编写内容==**

如果调用组件实例时，没有往组件标签中写任何东西，默认内容就会在组件实例中显示出来

如果调用组件实例时写入了新的东西，默认内容不会显现



![1617366330440](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617366330440.png)

![1617366355732](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617366355732.png)

 如果组件中有多个匿名插槽，当在组件实例的slot标签中写入内容时，会将所有的插槽都写入

如果想有所区分，就用到了下面讲到的具名插槽



### 具名插槽

如果想在组建中放置多个插槽，且插槽之间要有区分，以便在调用组件的时候可以在多个地方放置不同内容

可以为多个插槽添加**==name属性==**，属性值可以不同

调用组件时，在组件标签中添加新的标签时，为新的标签添加**==slot属性==**，属性值是插槽的name属性值

**==不指定slot属性的标签只会放到匿名插槽的位置，具名插槽还是默认值==**

![1617367170798](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617367170798.png)

![1617367151370](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617367151370.png)



### 编译作用域

调用实例的时候，使用的数据都是父组件里面的

在子组件的模板，使用的数据都是子组件里面的

这里面就是作用域的概念

### 作用域插槽

![1617371873263](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617371873263.png)

需求情景，子组件中通过v-for获得了子组件的数组中的数据，放在子组件中的模板中进行列表展示

父组件中使用子组件的时候，不想用列表展示了，想用水平方式展示，或者很多其他方式展示

但是在父组件中修改不了子组件中数据的排列方式，因为编译作用域不同

所以父组件还是得获取到子组件的数据，除了之前讲的父子组件传值，现在利用插槽来实现





**==子组件中模板中==**的插槽可以用v-bind绑定子组件中data中的数据，属性的名字自己定义

格式**==v-bind:属性名="子组件data中的数据对象"==**

父组件的实例中，在父组件标签中放一个template根标签（在新的版本中不再要求，使用div也可以，为了兼容可以继续用template），template标签添加一个slot-scope属性，属性的值自定义，

然后使用子组件中的数据时，用**==自定义的slot-scope属性值.自定义的v-bind的属性名==**来获取数据对象



**<font color='red'>注意：两个自定义的名称：</font>**

​	一个是**子组件模板中**在slot中==用v-bind绑定的属性名==

​	一个是**父组件实例中**template标签中==slot-scope属性值==

![1617373283932](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617373283932.png)



### ==vue2.6以后的具名插槽和作用域插槽==

详情：

https://cn.vuejs.org/v2/guide/components-slots.html

#### **==具名插槽：==**

在子组件的模板中放置多个插槽，插槽添加**==name属性==**来互相区分

不写name的插槽默认有一个==隐含的名字：default==

![1617416533154](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617416533154.png)

在使用组件实例时，**==使用template标签来标明往插槽中放置的内容==**

多个插槽的位置在实例中使用多个template标签

为template标签添加v-solt属性，用**==:冒号==**绑定名字就是模板中name的值

**==语法：v-slot:名字==**

![1617416554293](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617416554293.png)





#### **==作用域插槽：==**

想要在父组件中使用到子组件中的数据，可以利用作用域插槽

在子组件的模板中，插槽添加==v-bind绑定属性==，属性名自定义（这个属性被称为**==插槽 prop==**，由于插槽的特性，**==只要绑定了，此属性就会自动发送给父组件==**），属性值为子组件中的数据对象（**此步骤就是子组件利用v-bind调用子组件中data的数据**）

![1617416672759](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617416672759.png)

ps：这个例子是一个非具名插槽



在父组件的实例中，在v-slot:名字后面新增一个属性值，内容是自定义的接受过来的自定义对象的名字

**==语法：v-slot:名字="自定义数据对象名字"==**

在父组件的实例中即可用自定义数据子组件数据对象的名字来调用数据

![1617416694203](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617416694203.png)

（上图例子中的default是没有指明name值的插槽，有具体name值就可以用具体的名字来代替default）



#### ==插槽全是非具名插槽，父组件实例中的简便写法==

==v-slot 只能添加在 template 标签上== ，唯独一个例外，当最组件模板全是默认插槽（非具名插槽），在父组件实例中就**不用指定名字**了，**就不用template标签**了，但是这个时候父组件还想访问子组件数据，仍然需要v-slot属性，这时==可以直接绑定在父组件标签上==，

![1617417553616](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617417553616.png)

因为是非具名插槽，default也可以省略

![1617417592976](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617417592976.png)



# 模块化开发

## 简介

![1617419050038](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617419050038.png)

![1617419520259](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617419520259.png)

**==上面的例子中是一种模块化的解决思路：==**

定义一个**立即执行函数**，并且将立即执行函数的返回值使用一个**变量接收**

这个用于接收的变量可以在所有的文件中进行使用，使用的时候调用变量的属性、方法、数据即可

不会发生变量名冲突、文件先后顺序影响等等问题



**==前端模块化开发已经有了很多既有的规范，以及对应的实现方案==**

**==常见的模块化规范==**：

**==CommonJS、AMD、CMD,也有ES6的 Modules==**



**==模块化有两个核心，导出和导入==**



## CommonJS

要实现 CommonJS的规范的使用，需要底层支持这种语法结构，底层解析后才能使用CommonJS的语法

node环境就可以支持CommonJS，没有环境支持是不可以写的



**==导出：==**

model.exports{需要导出的内容}

![1617420387577](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617420387577.png)

**==导入：==**

**==let/var/const 接收变量 =require('外部js文件的地址')==**



![1617420292020](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617420292020.png)

​	**==对对象的解构，可以简写成如下==**（一般都这么写）

![1617420330122](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617420330122.png)



## ES6中的模块化

在HTML标签中通过script引入js文件

为script标签添加**==type="module"==**属性，即表明相应的js文件使用模块化规范，多个导入的js文件之间的变量、方法、类等不能互相访问，

![1617421306256](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617421306256.png)



如果想实现模块化js文件之间的变量访问，需要导出和导入

### 导出export

**<font color='red'>①</font>**

在js文件中，要想别的文件使用本文件中的某些变量、方法、类，将需要导出的方法和变量通过export导出

语法：**==export{变量,函数,类名.......}==**

![1617421450102](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617421450102.png)

**<font color='red'>②</font>**

导出变量、函数的另一种方法：在定义变量、函数、类的时候就将其导出

语法：**==export let 变量名=...==**

​	**==export function 函数名(){}==**

​	==**export class 类名 {}**==

![1617421879097](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617421879097.png)

![1617422099451](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617422099451.png)



### 导入import

**<font color='red'>①</font>**

如果需要使用别的文件中的变量、方法等等，需要将这些东西用import导入

**==语法：import {变量,方法......} from "外部js文件地址"==**

多次引入可能会导致重名，在重名的方法或属性后**==as 重命名==**就可

![1617421382735](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617421382735.png)

![image-20210421183114290](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421183114290.png)

**<font color='red'>②</font>**

将外部某个js文件中导出的东西全部导入

**==语法：import * as 对象名 from '外部js文件地址'==**

需要**==自定义一个对象名==**来接收某个js文件导出的全部东西

使用的时候通过调用对象属性方法的方式来使用

![1617439371280](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617439371280.png)









### export default

想如果想**==导入的js文件在导入时自定义命名==**

导出js文件时就用到了**==export default==**

**==语法：export default 变量/方法/类==**

**<font color='red'>注意</font>**：export default**==一次只能导出一个东西==**，不能导出多个，并且**==只能有一个export default==**

![1617438784472](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617438784472.png)

导出函数时，还可以直接导出匿名函数，相当于定义的时候就将其导出，只不过多了default

![1617439140516](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617439140516.png)



导入时，原来名称需要中括号引起来，**==现在不要加中括号==**，名称自主命名就行

![1617438828384](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617438828384.png)







# webpack详解

![1617440005702](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617440005702.png)

webpack为前端模块化提供了底层的制支撑

在使用AMD、CMD、CommonJS、ES6等	模块化规范时，webpack会自动为我们的代码做一些转换

转换成大部分浏览器支持的模块化的方案



![1617440468359](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617440468359.png)

![1617440627227](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617440627227.png)

**==webpack和gulp的对比==**

![1617440967141](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617440967141.png)



webpack本身依赖于node环境

而node环境为了正常执行很多代码，必须其中包含很多依赖的包

所以一般安装node的时候，会自动安装一个**==npm工具==**（node packages manager），帮助我们管理node环境下的各种包



## webpack安装

![1617441773605](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617441773605.png)



## webpack基本使用过程

src：源码（开发用的）

dist：打包后的文件（发布的时候，此文件夹放到服务器上）

main.js/index.js：程序的入口，放在src文件夹中的最外层，其他功能相关的js文件，可以在src文件夹下新建一个js文件夹，专门放其他的js

![1617450463429](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617450463429.png)

**==打包过程==**

在**src文件夹**中写入js文件，文件之间存在模块依赖

需要使用哪个，就直接将用到的js文件进行webpack打包

**打包时只用打包用到的文件就行了**，不用把所有模块依赖的文件都打包，webpack会进行解析，这个不用担心

webpack打包的文件放在**dist文件夹**中

在终端或者cmd中，语法：==webpack 要打包的文件地址 打包后的文件地址==

如图：

![1617450440246](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617450440246.png)







## webpack.config.js配置和package.json配置



为了简化打包操作，让webpack事先知道我们要对哪个文件进行打包，并且放到哪里

需要配置webpack.config.js文件

在**==项目的根目路==**下创建**==webpack.config.js文件==**



![1617452272085](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617452272085.png)

其中，path是从node中对应的path包中找的，这里就依赖了node环境，于是需要先配置好相应的包

在命令行中输入：**==npm init==**	进行初始化

初始化会遇到配置的相关问题，目前就包的名字和入口文件需要注意，包的名字一些符号或者中文不能使用，注意一下。入口文件现在用不到，一般指定index.js，其他的都默认就行了，

之后会在项目中生成**==package.json文件==**，项目如果要依赖node的话，都会有这个文件，文件的内容当前项目的一些信息

如果package里面还要依赖一些别的东西，还要通过**npm install命**令，帮助我们在当前文件夹中安装一些东西



![1617451636691](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617451636691.png)



一般来讲，我们还会用npm run build命令来打包，

npm run xxx	这个命令是执行刚才生成package.json文件中的脚本，好处是如果以后打包操作复杂了，上面这种方法也不够简便，使用npm run xxx命令执行脚本文件就变得简单。

build是我们自定义的一个命令，添加在package.json文件的scripts对象中

就目前来讲build命令就是"webpack"

![1617453625130](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617453625130.png)

这样直接在命令行中输入npm run build就行



**<font color='red'>注意</font>**：这样做和直接在命令行中执行webpack还有点不一样，npm run build会**==优先在本地里面找webpack包==**，找不到再去全局里面找，我们这里只安装了全局webpack，**==而直接执行webpack是直接在全局里面找==**，所以有时候还必须用npm run build

但是以后大项目中，很多都是有局部的webpack，**因为具体的项目依赖的webpack包版本很有可能和全局的不一样**

要**==安装局部的webpack==**，可以在当前目录下，使用**==npm install webpack@3.6.0 --save-dev==**

**==ps==**：此时的依赖都是**开发时依赖**，也就是在开发阶段时对webpack包的依赖，当打包好后，传给服务器项目运行是就不再需要了，所以在上面的命令后面加上了--save-dev。对应的还有一个**运行依赖**

安装好局部webpack包后，再次打开package.json文件就会看到相较于之前有一个**devDependencies对象**，里面放的都是我们项目**开发时的依赖**

除此之外，以后会见到**dependencies对象**，里面是我们项目**运行时候的依赖**



![1617454735685](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617454735685.png)

安装后局部依赖后，当前项目中会出现一个node_modules文件夹，里面是默认装的一些包

其中就包括webpack包

所以说如果说非要使用webpack命令，必须到**node_modules文件夹下执行**，这样使用的才是本地的webpack包

![1617455012057](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617455012057.png)







## webpack中css文件的配置

 ![1617457365203](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617457365203.png)

在开发中我们不仅仅有基本的js代码处理，我们也需要加载css、图片，也包括一些高级的将ES6转成
ES5代码，将 Typescript转成ES5代码，将 scss. less转转成css,将jsx、,vue文件转成s文件等等

对于 **webpack本身的能力**来说，对于这些转化是**不支持**的。

**==这时候就需要给webpack扩展对应的loader就行了==**

不同的文件处理会用到不同的loader

**==loader使用过程==**

​	步骤一：通过**npm**安装需要使用的 loader

​	步骤二：在 **webpack.config. js**中的 **modules**关健字下进行配置



**==css模块化：==**

将外部css文件导入js文件，产生依赖

例如使用commonJS规范

![1617458297142](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617458297142.png)

直接**==require('css文件地址')==**

不用像以前一样写变量来接收，因为css只是使用，并没有进行引用，这里不用写变量



但是这时webpack并没有处理css文件的能力

需要下载处理css文件对应的loader



**<font color='red'>步骤一</font>**：通过**npm**安装需要使用的 loader

目前使用的话，与css有关的有两个loader，

-  **==css-loader==**解析 CSS 文件后，使用 import 加载，并且返回 CSS 代码（**==负责加载==**）

- **==style-loader==**将模块的导出作为样式添加到 DOM 中（**==负责渲染==**）

命令行中使用：**==cnpm install --save-dev css-loader==**、**==cnpm install style-loader --save-dev==**



**<font color='red'>步骤二</font>**：在 **webpack.config. js**中的 **modules**关健字下进行配置

**==注意看注释==**

![1617459886130](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617459886130.png)



## less处理文件工作

如果我们希望在项目中使用less、scss、 stylus来写样式，webpack也可以帮助我们处理

这里以less为例，其他也是一样的。



webpack并没有自带处理less文件的功能，所以还需**==安装相应的loader==**，并**==进行相关配置==**

这里了关于less有**==两个功能==**：

​	webpack对于less文件的**加载功能**

​	webpack对于less文件**转化为css的功能**（就不需要之前下载的插件了）

**==所以不仅要安装less-loader，还要安装less这个包==**，来对less文件进行处理

**<font color='red'>①</font>**命令行命令：**==npm install --save-dev less-loader@4.1.0 less@3.9.0==**



**<font color='red'>②</font>**安装完后在**==webpack.config.js==**中进行相关的配置

![1617498477240](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617498477240.png)

ps：

​	配置中，对loader应用的use数组，之前里面是**字符串**，现在是**对象**

​	用对象的好处是可以**传一些其他的参数**，配置一些其他的东西

​	use数组中的对象仍然是按照从右向左进行加载

**<font color='red'>③</font>**

创建一个less文件，放在css文件夹中

在**main.js**文件中进行lesss文件的引入

并在文件中利用dom写入往index.htmlHTML代码，已检查是生效

![1617500126089](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617500126089.png)





## webpack图片文件的处理

 当在css中引入图片后，构建项目时，webpack查看到文件需要依赖相关的css文件，css文件有需要依赖相关的图片，**==webpack会将图片也当成模块去加载==**

这是又需要安装相应的loader，并且进行相关配置

**<font color='red'>①</font>**

使用url-loader，因为图片是用url来引入的，可以使用url-loader来进行加载

在命令行中输入：**==cnpm install --save-dev url-loader@1.1.2==**

**<font color='red'>②</font>**

然后在webpack.config.js中进行相关的配置

仍继续往module的rules中继续添加规则

![1617502631859](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617502631859.png)

这里的use数组中都是**对象**，因为url-loader需要进行一些其他配置

**==options里面是一些选项设置，其中limit是设置文件最小的大小==**

**==当文件小于limit时==**，文件就会被解析成base64格式，在浏览器中直接从服务器中请求base64格式的字符

![1617502356898](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617502356898.png)串，来将图片显示出来

**==但是当文件大于limit时==**，webpack在加载图片的时候，会使用**==file-loader==**进行加载

file-loader不需要配置，直接安装就行了

​	命令：**==cnpm install --save-dev file-loader@3.0.1==**

​	使用file-loader后，构建项目后，之前指定的存放打包后bundle.js文件的同一目录里**多了一个图片**

​	此图片就是我们进行加载的图片，并且文件名进行了重命名，文件名是自动生成的哈希值

​	哈希值目的是为了防止重复

![1617503420967](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617503420967.png)

这时有一个问题，我们将文件打包到了dist文件夹中，但是**==浏览器加载打包后的图片文件的时候默认加载的路径是index.html 文件的同一目录==**，加载的**图片名是对的**（就是那个哈希值），**但是路径不对**



**<font color='red'>③</font>**

这时就需要修改**==webpack.config.js==**文件进行配置

将file-loader引入的图片地址改为dist文件夹的地址

![1617503782418](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617503782418.png)



在output对象中添加**==publicPath属性==**，属性的值为**=='dist/'==**

**==以后任何涉及到url引入文件的地方，都会自动在前面拼接dist/==**

**<font color='red'>注意：在以后开发的时候，index.html文件也会导入到dist文件夹中，到时候就又不需要修改路径了</font>**



**<font color='red'>④补充</font>**

![1617504312545](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617504312545.png)

**直实开发中，我们可能对打包的图片名字有一定的要求**

比如，打包到dist文件夹下的img文件夹，并且统一命名为：原来名+8位哈希值

这就需要我们在webpack.config.js文件中进行配置

仍然在url-loader规则下面的potions中，添加name属性，指定打包后文件的地址和命名规范

![1617504997271](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617504997271.png)

指定打包后文件的地址和命名规范

 []中括号中依次是：使用原来文件名、8位哈希值、使用原来文件扩展名

 .小数点的作用是将命名规范连接起来

再次构建项目，文件就在指定文件夹下面并且统一命名好了

![1617505112964](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617505112964.png)



## ES6转ES5的babel

![1617506345807](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617506345807.png)



我们打包后的loader仍然是ES6的语法，要转换为ES5语法还要下载相应的loader，然后进行相关配置

**<font color='red'>①</font>**

此时安装的是**==babel-loader==**

除此之外还需要用到**babel-core**（babel核心）、**babel-preset-es2015**（es2015代表的是**es6配置文件**，如果是不同的语法转换，比如TS，就要安装ts相应的配置文件）

> 下面是官网推荐的安装：
>
> ![1617506761344](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617506761344.png)
>
> 其中==env（environment环境）==，官网推荐安装的是一个babel配置环境，安装这个之后还需要配置一个文件：**babelrc文件**，在这个文件中对多种语法转换进行一些相应的配置
>
> 但是我们这里只用到了es6，就只进行简单的配制就行了，不安官网配置

命令行命令：

**==cnpm install --save-dev babel-loader@7.1.5 babel-core@6.26.3 babel-preset-es2015@6.24.1==**



**<font color='red'>②</font>**

配置webpack.config.js文件

在rules中添加babel-loader的规则

![1617507920617](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617507920617.png)

**exclude**：是排除的意思， 因为我们打包的时候用到了node_modules文件

![1617508013935](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617508013935.png)

 这时之前安装**本地局部的webpack**时候创建的， 这些文件是不需要做打包的，也不会发布，需要排除在外

use中如果只用一个loader时，可以直接写成对象，不用写成数组

options（选项）中配置preset，这里写需要转换的语法：**es2015**（如果是按照官网安装环境，需要写相应的环境）



这时候删除原来的bundle.js文件，再次构建项目，新的bundle.js里面就是es5的语法了



## webpack中vue的配置



首先需要配置vue的一些环境

在当前的项目中安装vue的依赖

命令行：npm install vue@2.5.21 --save

因为vue是在项目运行过程中使用到的依赖，并不是开发依赖，而是运行依赖

![1617516144469](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617516144469.png)

安装好vue依赖后，在main.js中导入vue依赖（**<font color='red'>后面讲为什么这么导</font>**），但是构建项目仍然会报错

因为vue在发布的时候有**两个版本**：==runtime-only==和==runtime-compiler==

1. runtime-only->代码中，==不可以有任的 template==
2. runtime-compiler>代码中，==可以有 template==,因为有 compiler可以用于编译 template

我这两个版本我们都下载了，但是**默认使用**的是==runtime-only==，不能有template。浏览器会将组件的使用当成template，进而报错

![1617514527065](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617514527065.png)

在webpack.config.js 文件中进行配置，指定vue的版本

在module.exports对象中添加alias属性，alias意思是别名

意思是在上面导入vue时：**import Vue from 'vue'**，为vue指明文件的具体地址

![1617515617894](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617515617894.png)

$符号是正则表达式，代表以vue结尾 

将默认导入时指定的文件改为**vue.esm.js**，这里面有==runtime-compiler==

之前默认的是vue.runtime.js，这里面是runtime-only

再用**==import Vue from 'vue'==**导入vue是使用的是这个文件





## 创建vue时template和el的关系

SPA（Single Page Application）**==单页面富应用==**

在单页面富应用里面只有一个HTML代码

多个HTML代码是通过**==路由==**（vue-router这是前端的路由）跳转

所以这个时候index.html 中的代码很简单，详细的HTML代码、vue实例、对vue中方法数据的引用等等这些操作都不会放到index.html文件中去做

只保留**==<div id="app">==**这一个标签就行了

![1617516903248](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617516903248.png)

其他的内容定义到**==js文件中vue实例的template属性中==**去

![1617516964937](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617516964937.png)

项目运行时，浏览器会将template中的代码==替换==掉之前的那个div标签，**直接替换，并不是放到那个标签里面**，el里面保存了指定div的id属性的值

![1617517061132](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617517061132.png)

但是这种方案，在之前就讲过要把template抽离出来，现在又放回去了

下面就来将进一步处理方案



## vue的终极使用方案

**<font color='red'>①</font>**

我们**==将vue实例中的template中的代码用子组件替换==**，相当于在子组件中进行HTML的编写

在vue实例中的components属性中进行子组件的注册，

**==vue实例的template只有一个子组件的标签==**

![1617520140612](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617520140612.png)

**<font color='red'>②</font>**

**==再将子组件从main.js文件中提取出来==**，放到一个专门放vue相关代码的文件夹

然后在src文件夹中创建vue的文件夹，里面放的都是vue相关代码

在vue中创建app.js文件

将刚才的子组件的构造器部分截取出来，放到app.js文件中

然后利用export default将构造器里所有的内容导出

![1617520641828](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617520641828.png)

然后在main.js当中做一个简单地引入就行

![1617520726340](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617520726340.png)



**<font color='red'>③</font>**

在app.js的子组件中仍然没有做到**==模板中的HTML代码==**没有和**==构造器中js代码==**分离

在vue文件夹中创建**<font color='red'>App.vue文件</font>**

此文件中固定有三部分，分别是三个子标签：template、script、style

分别对应HTML、js、css三种代码

​	之前的子组件的**模板**放到**template标签**中

​	之前子组件**构造器中剩余的部分**放到**script标签**，并且添加**==name属性==**，属性的名字就是子组件自定义标签名

![1617522562939](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617522562939.png)

这样之前的app.js文件整个就不用了，也不用引入了

在main.js文件中导入App.vue文件

![1617522577457](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617522577457.png)

但是这个时候webpack还不能识别vue文件，还需要下载相应的loader，并且进行相应的配置

**<font color='red'>④</font>**

需要用到：

​	vue-loader：用来加载vue

​	vue-template-compiler：vue模板的编译



命令行：**==npm install vue-loader@15.4.2 vue-template-compiler@2.5.21 --save-dev==**

此外还要配置webpack.config.js文件

![1617525065612](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617525065612.png)

除此之外还对遇到别的问题，需要再配置一个插件，这是vue-loader从14版本往上才需要

解决方法如下

> vue官网：loader--（导航栏）--如何从V14迁移--Vue Loader v15 
>
> 现在需要配合一个 webpack 插件才能正确使用：
>
> 按照图片提示分别添加 const VueLoaderPlugin = require('vue-loader/lib/plugin') 和  plugins: 【new VueLoaderPlugin()】，然后在package.json里面找到"vue-loader": "^15.4.2",并更改为"vue-loader": "^15.0.0",
> 然后在控制终端npm install即可完成





















这样就可以创建多个vue组件，然后相互之间可以引用

ps：vue文件一般开头字母大写

还可以往组件当中引入组件

子组件

![1617526584356](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617526584356.png)

父组件：

![1617526609947](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617526609947.png)



导入文件时vue文件的后缀名不能省略

如果想省略的话，可以来webpack.config.js文件中进行配置

在module.exports中的resolve属性中添加**==属性extensions:['.js','.css','.vue']==**

将需要简写 文件后缀写进去

![1617527034354](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617527034354.png)

然后就能简写了





## plugin的使用

![1617527284568](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617527284568.png)



**==plugin==**： plugin是插件的意思，通常是用于对某个现有的架构进行扩展。

 webpack中的插件，就是对 webpack现有功能的各种扩展，比如**打包优化**，**文件压缩**等等。

**==loader和 plugin区别==**

​	 loader：主要用于**转换**某些类型的模块，它是一个==转换器==。

​	 plugin：是插件，它是对 webpack本身的扩展，是一个==扩展器==。

**==plugin的使用过程：==**

​	步骤一：通过npm安装需要使用的 plugins(某些 webpack已经内置的插件不需要安装)

​	步骤二：在 webpack. config. js中的 plugins中配置插件。



### 添加版权的plugin（横幅Plugin）

![1617527742715](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617527742715.png)

**==BannerPlugin版权声明插件==**（**横幅plugin**）是webpack自带的一个插件

在webpack.config.js文件中进行设置

导入webpack包：**==const webpack = require('webpack')==**

![1617528031056](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617528031056.png)

并且进行一些配置，在module.exports中添加plugins属性

![1617529441341](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617529441341.png)



最后导出的bundle.js文件中最上面一行多了版权声明

![1617528567289](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617528567289.png)





### HtmlWebpackPlugin的使用打包index.html

![1617529650230](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617529650230.png)

**==之前我们的index.html文件都没有放到dist文件夹中==**，为此我们需要插件来完成

HtmlWebpackPlugin插件可以为我们做这些事情：

​	自动生成一个 index.htm文件（可以指定模板来生成

 	 将打包的js文件，自动通过 script标签插入到body中



进行安装

命令行：**==npm install html-webpack-plugin@3.2.0 --save--dev==**

进行配置

在webpack,config.js文件汇中进行配置

 导入html-webpack-plugin包

![1617529972439](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617529972439.png)

同样，将插件放进plugins数组中，这里面可以放一些参数（后面用得到）

![1617530062884](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617530062884.png)



然后重新构建项目，dist文件夹中出现了index.html文件

![1617530283891](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617530283891.png)



**<font color='red'>这时还有两个问题：</font>**

**<font color='red'>①</font>**vue实例还没有进行引入，也就是div id="app"这个标签没有引入

**<font color='red'>②</font>**这个时候script标签中引入的bundle.js文件地址有问题，这时候还是用的之前dist进行的路径拼接，这时候也不再需要了  



**==解决方法：==**

**<font color='red'>①</font>**

将webpack.config,js文件中拼接路径操作删去

![1617531014671](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617531014671.png)

**<font color='red'>②</font>**

在根目录下的index.html文件中**==删去==**<script src="./dist/bundle.js"></script>

因为最后生成的文件**==有插件帮我们导入==**，不用我们自己再写了

在plugins数组中对应的**==HtmlWebpackPlugin插件==**中传入一些参数

这里传入的是一个**==模板==**，根目录原来的index.html文件现在直接用来当模板

![1617531433838](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617531433838.png)



再次重新构建项目，dist文件夹中就出现了符合要求的index.html，**==原来的index.html文件就不能打开了==**



### Uglifyjs-webpack-plugin插件压缩JS代码

![1617532745653](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617532745653.png)



Uglifyjs-webpack-plugin插件会将我们的js代码进行压缩

将没用的空格删去、将所有变量用简单的变量代替、将注释删掉

此插件是第三方插件，同样需要下载，并且进行配置

命令行：

**==cnpm install uglifyjs-webpack-plugin@1.1.1 --save-dev==**

webpack.config.js文件的配置：

导入uglifyjs-webpack-plugin的包

![1617533580046](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617533580046.png)

将插件放进plugins数组中

![1617533567520](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617533567520.png)

之后重新构建项目，得到的bundle.js文件如下：

![1617533799886](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617533799886.png)

==**这个时候版权声明就没有用了，因为所有的注释全都去掉了**==

**<font color='red'>但是在开发阶段不建议使用，不方便调试</font>**



## webpack-dev-server搭建本地服务器

![1617534717211](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617534717211.png)





webpack提供了一个可选的本地开发服务器，这个本地服务器**==基于 node.js==**搭建，内部使用 **==express框架==**，可以实现我们想要的让浏览器**==自动刷新显示我们修改后的结果==**

express框架**服务与某个具体的文件**，监听文件的变化，**但服务器并不是实时的将我们的代码写进最后导出的文件**，而是**先写到内存中**，**并没有放进磁盘中**，测试好后准备发布后再进行相应文件的生成，因为磁盘的读取速度**远远小于**内存的速度

使用webpack-dev-server来搭建本地服务器，安装对应的模块，并且进行相应的配置

命令行：**==npm install --save-dev webpack-dev-server@2.9.3==**

webpack.config.js文件中的配置：

![1617535569250](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617535569250.png)

contentBase：服务器**==为一个文件夹==**提供本地服务，**默认是根文件夹**，我们这里要填写。/dist
​	inline：是否需要**实时的进行监听**
​	**<font color='red'>上面devServer属性里面的设置只是在开发阶段需要，真正运行打包时并不需要，到时候要去掉</font>**

**==然后开启本地服务器：==**

在命令行中输入：webpack-dev-server开启本地服务器

但是这样并不能生效，因为我们默认在命令行输入的命令是在全局里面查找命令

但是我们的模块是安装在局部的

这就需要我们之前讲过的设置脚本来执行命令，**==因为脚本执行优先在本地里面找==**

打开**==package.json文件==**，设置script属性

![1617536236192](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617536236192.png)

**==再json文件中不要写注释、不要乱填空格，否则报错==**



然后在命令行使用**==npm run dev==**开启本地服务器

但这是需要手动打开网页，如果想自动打开网页，将上面的script脚本添加上open

**==webpack-dev-server --open==**

![1617537219301](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617537219301.png)

即可自动打开网页

此时修改代码页面会实时变化，但是dist中文件并没有实时更新

当修改完后，在命令行输入==**npm run build**==，**==才真正将文件上传dist文件夹==**





## webpack配置文件的分离

将webpack的配置文件进行一些抽离

将开发时和编译发布时这两个阶段的配置文件进行抽离



新一个项目根目录下创建文件夹build

build里面新建三个配置文件：

​	==**base.config.js**==：**公共**的配置文件，开发和运行阶段都需要的

​	==**dev.config.js**==：**开发**阶段需要的

​	==**prod.config.js**==：**生产**运行时需要的





prod文件中的内容

![1617597674847](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617597674847.png)

dev文件中的内容

![1617597664847](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617597664847.png)

base文件里面只删除了DevServer中的东西

![1617597757072](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617597757072.png)

现在将prod和base两个个文件之间进行合并





需要安装webpack-merge插件进行文件合并，并且进行相关配置

命令行：**==npm install webpack-merge@4.1.5 --save-dev	==**

在**<font color='red'>prod.config.js</font>**文件中进行配置

导入相关模块

![1617598256766](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617598256766.png)

然后再**==导入base文件==**

然后利用**==webpackMarge方法==**将**bese文件**和**当前文件中的内容**进行合并，合并后利用module.exports导出

![1617598589211](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617598589211.png)

同样，在dev.config.js文件中将**base文件**与**dev文件**进行合并

![1617598911999](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617598911999.png)

**<font color='red'>dev、prod文件分别与base文件进行了合并</font>**

**<font color='red'>这样，开发时的相关配置、运行时相关配置做到真正的分离</font>**



之后在进行项目的构建时，需要**重新指定我们的配置文件**

==**在之前build命令和dev命令配置script脚本文件的地方加上具体目录的指向**==

为build命令指定为prod.congfig.js文件

为dev命令指定为dev.config.js文件



但是这个时候index.html和bundle.js等相关的文件夹并没有被打包到之前的dist文件夹，而是在build 文件夹下面新创建了一个dist文件夹，把东西放在了新的文件夹里面

![1617604310533](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617604310533.png)

因为配置文件分离后，**三个配置文件都放在build文件夹下面**，配置文件中有进行**路径拼接**的操作，是在**当前文件目录下进行**拼接的

当前配置文件目录已经变成了build，所以打包后的文件夹都放在了build文件夹中的dist文件夹中

这时候将拼接的地址改为**==../dist==**就行

![1617605641391](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617605641391.png)



# vue cli脚手架

## 脚手架的介绍和安装

![1617606260676](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617606260676.png)

使用 Vue. js开发大型应用时，我们需要考虑**代码目录结构**、**项目结构和部署**、**热加载**、**代码单元测试**等事情

如果每个项目都要手动完成这些工作，那无疑效率比较低效，所以通常我们会使用一些脚手架工具来帮助完成这些事情。

**==CLI是什么意思：==**

​	CLI是 **Command- Line Interface**,**翻译为==命令行界面==**，但是**俗称脚手架**

​	Vue CLI是一个官方发布 vue.js项目脚手架

​	使用vue-cli可以**快速搭建Vue开发环境**以及对应的 **webpack配置**

![1617606629480](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617606629480.png)

使用脚手架必须安装Node，版本要求8.9或者更高的版本

一般默认会下载Node和NPM

**==什么是NPM呢：==**

​	NPM的全称是 ==Node Package Manager==

​	是个NodejS**==包管理和分发工具==**，已经成为了非官方的发布Node模块（包）的标准

​	后续我们会经常**使用NPM来安装一些开发过程中依赖包**

**==cnpm安装：==**

![1617606866589](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617606866589.png)

一般vuecli的安装是**==全局安装（-g）==**

现在大部分安装的是cli3，如果想按照cli2的方式初始化项目是不行的

这时需要**==拉取cli2的模板==**（vuecli3的安装就省略）

​	在命令行输入**==npm install @vue/cli-init -g==**

**==vue cli2初始化项目==**

​	命令行输入==**vue init webpack 项目名称**==

**==vue cli3初始化项目==**

​	命令行输入==**vue create 项目名称**== 



## cli2初始化项目过程

![1617610293018](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617610293018.png)



## cli2目录结构解析

扩展：

node为js提供了运行环境

以前，js如果想执行，必须依托于HTML代码和浏览器来执行

想要使用js开发一些其他的东西的话，困难重重

这时候就出现了node

node是使用c++开发的，里面有一个核心的东西：V8引擎

​	v8引擎是谷歌开发的，最一开始js代码在浏览器上运行先生成字节码，再让浏览器进行解析

​	使用v8引擎后，直接将js代码转换为二进制，然后交给浏览器解析（自谷歌后很多浏览器都转换成了二进制）

 有了node，电脑就可以通过node直接执行js文件

![1617611719059](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617611719059.png)



![1617619944596](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617619944596.png)



## ESLint规范

在创建项目时选择使用了ESLint规范

再编写代码时，空格、分号、缩进等等会有严格要求

如果不想用了，可以在config文件夹下面的index.js文件中，**==将useEslint属性改为false ，就将语法检查关闭了==**

![1617624459930](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617624459930.png)



## ==runtime-only和runtime-compiler的区别==

在用脚手架创建项目的时候，会有两种vue项目选择：**==runtime-only==**和**==runtime-compiler==**

二者的区别只在**==main.js文件==**中



**==下图是vue程序的执行过程==**

**==template模板->ast抽象语法树->render箭头函数->虚拟dom->真实dom==**

![1617625461384](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617625461384.png)

**==runtime-only的main.js文件==**

![1617625543097](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617625543097.png)

**==runtime-compiler的main.js 文件==**

![1617625559335](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617625559335.png)

由上面这两张图可知：

**==runtime-only模式下vue项目运行过程为：==**

​	**render箭头函数->虚拟dom->真实dom**

**==runtime-compiler模式下vue项目运行的过程为：==**

​	**template模板->ast抽象语法树->render箭头函数->虚拟dom->真实dom**



因为**runtime-only模式**不允许使用template模板，vue项目运行的过程更少，**==性能更好，代码量更少，==**构建项目时比runtime-compiler模式大小少6kb

所以在后期开发时，**==建议使用runtime-only模式==**



### render函数的理解：



上面runtime-only模式中的render函数为：**==render: function(h){renturn h(App)}==**

这函数里面的参数==h==其实是另一个函数：**==createElement==**，用h做替换是vue中的一个规范



**<font color='red'>createElement函数普通用法：</font>**

**==将createElement函数作为render函数的返回值返回==**

createElement函数有三个参数：

​	第一个：标签（自定义的名字，通过函数创建最后的标签）此标签会将vue实例通过el:'#app'挂载的的那个标签替换掉，也就是如果index.html 文件中div的id="app"，最后这个div标签完全被自定义的标签替换掉

​	第二个：一个对象，对象的内容代表了新建标签的属性

​	第三个：一个数组，数组里面是新建标签里面的具体内容

将render函数中createElement函数的写完整后如下图

![1617628172838](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617628172838.png)

构建项目后，原本index.html 文件中有如下div

![1617629416362](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617629416362.png)

实际页面中响应为位置是createElement函数新建的标签

![1617629498703](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617629498703.png)

此外，还可以在第三个标签中在放入一个createElement函数，再新建一个标签，再传入相应的参数

![1617629615415](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617629615415.png)

![1617629632067](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617629632067.png)





**<font color='red'>createElement函数另一个用法就不用传入上面三个参数，可以传入一个组件对象：</font>**

这种用法也就是我们runtime-only模式下此文件中使用的方法

同样，**==将createElement函数作为render函数的返回值返回==**

可以尝试在index.html文件中用**==构造器创建一个组件==**，在将其**==传入createElement函数中==**，页面中仍能生效

![1617630129518](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617630129518.png)

![1617630152464](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617630152464.png)

我理解的是createElement就**<font color='red'>代替了原来vue实例中的components属性省去了注册步骤</font>**，

**<font color='red'>传入的组件对象是文件开头从App.vue中导入的组件，template模板的编辑也不用再此文件夹中</font>**

**==但是还有一个疑惑，App.vue文件中仍然有template不是仍然需要转化到ast语法树吗？==**

其实不用，vue文件中的template会自动被编译成render函数，这步操作是有vue-template-compiler完成的

**==vue-template-compile在webpack配置过程中提到过，第一次引入.vue文件时需要下载的依赖==**，脚手架这里也被默认装上了

从而彻底不用从template到ast语法树的转化，更高效



### npm run build/dev执行过程图



![1617631485096](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617631485096.png)

![1617631507666](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617631507666.png)



vuecli3创建项目和目录结构



































































# ==PS==

## 属性选择器

### 简单属性选择

如果希望选择有某个属性的元素，而不论属性值是什么，可以使用简单属性选择器。

![1617093398534](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617093398534.png)

### 根据具体属性值选择

除了选择拥有某些属性的元素，还可以进一步缩小选择范围，只选择有特定属性值的元素。

这种格式要求必须与属性值==完全匹配==。

如果属性值包含用空格分隔的值列表，匹配就可能出问题。

![1617093460617](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617093460617.png)

### 根据部分属性值选择

如果需要根据属性值中的**==词列表的某个词==**进行选择，则需要使用波浪号（~）。

![1617093576915](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617093576915.png)

**==补充：==**

p.important 和 p[class="important"] 应用到 HTML 文档时是等价的。

那么，为什么还要有 "~=" 属性选择器呢？因为它**==能用于任何属性==**，而不只是 class。

### 子串匹配属性选择器

| 类型         | 描述                                       |
| ------------ | ------------------------------------------ |
| [abc^="def"] | 选择 abc 属性值以 "def" 开头的所有元素     |
| [abc$="def"] | 选择 abc 属性值以 "def" 结尾的所有元素     |
| [abc*="def"] | 选择 abc 属性值中包含子串 "def" 的所有元素 |

![1617093802613](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617093802613.png)

### 特定属性选择类型

![1617093911563](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617093911563.png)



## vue中的this

在vue中的methods中的函数使用this，**==this==**指的是这个**==vue的实例对象==**，实例对象中**==data中的属性==**都可以通过this来获取

错误案例：

![1617098651006](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617098651006.png)

button标签放在了<div id ="app">标签外面，不属于vue实例，应该将button放在div标签里面才能生效



## lable标签

<label> 标签**==为 input 元素定义标注（标记）==**。

label 元素不会向用户呈现任何特殊效果。

不过，它为鼠标用户改进了可用性。如果您在 label 元素内点击文本，就会触发此控件，**==就是说点击按钮前面的文本也就相当于点击了按钮==**

### lable位于表单里面

一般label同样是写在**==form表单标签里面==**的

将表单与label标签联系起来有两种方式：显式、隐式

**==隐式形式==**：将表单控件作为标记标签的内容，

![1617158746702](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617158746702.png)



**==显式形式==**：或者为 <label> 标签下的 for 属性命名一个目标表单 id

<label> 标签的 **==for 属性==**应当与**==相关元素的 id 属性==**相同。

![1617158756616](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617158756616.png)

### lable位于表单外面

 **==label 也可以位于 form 元素之外==**，但仍然是表单的一部分。

label中添加一个**==form 属性==**规定 label 所属的一个或多个表单。

**==form 属性的值==**必须是其所属的**==表单的 id==**。

![1617160632731](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617160632731.png)

**<font color='red'>ps</font>**：实际使用这个的时候有问题，多个表单时，form属性绑定几乎没有用，不知道为什么





## input标中的placeholder属性

placeholder 属性提供可描述输入==**字段预期值的提示信息**==（hint）。

该提示会在输入字段为空时显示，并会在==字段获得焦点时消失==。

![1617161052757](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617161052757.png)

注意：placeholder 属性适用于以下的 <input> 类型：text, search, url, telephone, email 以及 password。





## 可变参数

当往函数中传入的实参不确定个数时，可以将形参写成：**==...变量==**，这样可以传入数量不确定的参数

![1617183472397](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617183472397.png)





## JavaScript的 toFixed() 方法

toFixed() 方法可把 Number 四舍五入为**==指定小数位数的数字==**。

参数：规定小数的位数，是 **==0 ~ 20 之间的值==**，**==包括 0 和 20==**，有些实现可以支持更大的数值范围。如果**==省略了该参数，将用 0 代替==**。

![1617191160885](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617191160885.png)



还可以用指定小数位数的方法来进行**==四舍五入==**

## input标签的input事件

用来监听用户是否在输入框输入东西

一旦输入东西就触发了这个事件

**点击一次键盘就触发一次，包括空格**





## event.target属性

target 事件属性可返回事件的目标节点（触发该事件的节点），如生成事件的元素、文档或窗口。

**==获得触发事件的元素==**

![1617203922603](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617203922603.png)





## textarea标签

textarea标签定义一个多行的**文本输入控件**。

文本区域中可容纳**无限数量的文本**，其中的文本的默认字体是等宽字体（通常是 Courier）。

**实现多行文本的输入**

可以通过 cols 和 rows 属性来规定 textarea 的尺寸大小，不过更好的办法是使用 CSS 的 height 和 width 属性。

![1617205532519](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617205532519.png)



















































































# ==ES6==

### let、const、var的区别



1. var是ES5提出的，let和const是ES6提出的。
2. const声明的是常量，必须赋值
   1）一旦声明必须赋值,不能使用null占位。
   2）声明后不能再修改
   3）如果声明的是复合类型数据，可以修改其属性
3. let和var声明的是变量，声明之后可以更改，声明时可以不赋值

4. var允许重复声明变量，后一个变量会覆盖前一个变量。let和const在同一作用域不允许重复声明变量，会报错。

5. var声明的变量存在变量提升（将变量提升到当前作用域的顶部）。即变量可以在声明之前调用，值为undefined。
   let和const不存在变量提升。即它们所声明的变量一定要在声明后使用，否则报ReferenceError错。

6. var不存在块级作用域。let和const存在块级作用域。
   ES5中作用域有：全局作用域、函数作用域。没有块作用域的概念。
   ES6(简称ES6)中新增了块级作用域。块作用域由 { } 包括，if语句和for语句里面的{ }也属于块作用域。



### for循环

之前的for循环

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617108420753.png" alt="1617108420753" style="zoom:80%;" />

或者用foreach方法也行

==es6中==，遍历**索引**的简便方法

![1617108481845](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617108481845.png)

遍历**数组中的内容**的简便方法（这个例子是个对象）

![1617108559829](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617108559829.png)





### let/var

var没有块级作用域

单纯的大括号{}对于var定义的变量没有任何影响，在括号内外都可以使用

没有块级作用域引起的问题：



![1617113164368](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617113164368.png)

这个问题在js笔记中讲过

for在一开始已经遍历过了，i已经变成了5，，并且var没有块级作用域，再次触发点击事件，这里面的i仍然是变量，循环时并没有被具体数字替换，现在i就是循环结束的那个值

上面这种解决方法是使用闭包，原理是函数有函数作用域，将整个for循环里面的内容写成一个将i作为参数的立即执行函数

![1617113792667](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617113792667.png)

​	

let有块级作用域

ES5之前因为if和for都没有块级作用域的概念，所以在很多时候，我们都必须借助于 function的作用域来解决应用外面变量的问题

ES6中，加入了let,let它是有if和for的块级作用域，即{}括号的块级作用域

![1617114502781](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617114502781.png)





### const的使用

在很多语言中已经存在，比如CC++中，主要的作用是将某个变量修饰为常量

在 Javascript中也是如此，使用 const修饰的标识符为==常量==，==不可以再次值==

**建议**：在ES6开发中，优先使用 const,只有需要改变某一个标识符的时候才使用let

**注意：**

1.一旦给 const修饰的标识符被赋值之后，==不能修改==

2.在使用 const定义标识符，==必须进行赋值==

3.常量的含义是指向的==对象==不能修改，但是==可以改变对象内部的属性==

​		（结合js中对象在内存地址中的存储方式）



### 对象增强写法

#### 属性的增强写法

对于对象外部的一些变量（const和let不影响），想写到对象里面成为对象的属性

在es5中

![1617118808176](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617118808176.png)

在es6中

![1617118830267](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617118830267.png)

#### 函数的增强写法

es5中的写法

![1617118905377](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617118905377.png)

es6中的写法

![1617119162775](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617119162775.png)



### ``模板字符串的使用

在es6中有一个新的引号：**==``==**（即键盘上的破浪号）

``引号使用时字符串**==可以换行==**





**==ES6模板字符串之标签模板==**

首先，模板字符串和标签模板是两个东西。

> 标签模板不是模板，而是函数调用的一种特殊形式。“标签”指的就是函数，紧跟在后面的模板字符串就是它的参数。
>
> 但是，如果模板字符串中有变量，就不再是简单的调用了，而是要将模板字符串先处理成多个参数，再调用函数。([ES6标准入门-阮一峰 4.12标签模板](http://es6.ruanyifeng.com/#docs/string#标签模板))

 

由此引出此文，先上代码：



```javascript
var a = 5;
var b = 10;
 
tag`Hello ${ a + b } world ${ a * b }`;
//等同于
tag(['Hello ', ' world ', ''], 15, 50);
```

 

这里我产生了疑问，为什么数组第三个参数是空字符串，书中也未曾讲到，很是疑惑。

然后再看下一段代码：

 

```javascript
var total = 30;
var msg = passthru`The total is ${total} (${total * 1.05} with tax)`;
...
//由此可以得出 上面的方法等同于
var msg = passthru(['The total is ', ' (', ' with tax'], 30, 31.5)
```

 

在这段代码中数组参数并没有产生空字符串，原因我也不知道，百度了一番，然后懂了。

 

模板字符串由变量和非变量组成，什么是变量，${}就是变量。模板标签函数调用的第一个参数是数组，是由模板字符串中那些非变量部分组成，包括空格。

 

那么不难理解，假设模板字符串中的变量为A，非变量为B，那么模板字符串的组成可能就是:

```javascript
tpl1 = ABABA; -> ['', B, B, '']
tpl2 = BAB;   -> [B, B]
tpl3 = ABAB   -> ['', B, B]
...
```

 

可以解读到：模板字符串中变量必须是由非变量包含着的，如果变量在开始位置或者结束位置且没有非变量包含，那么该位置就是空字符串。





### Object.assign()

#### 基本用法

`Object.assign`方法用于**==对象的合并==**，将源对象（source）的所有可枚举属性，**==复制到目标对象==**（target）。

```dart
const target = { a: 1 };

const source1 = { b: 2 };
const source2 = { c: 3 };

Object.assign(target, source1, source2);
target // {a:1, b:2, c:3}
```

`Object.assign`方法的**第一个参数是目标对象**，**后面的参数都是源对象**。

注意，如果目标对象与源对象有同名属性，或多个源对象有同名属性，则**==后面的属性会覆盖前面的属性==**。

```dart
const target = { a: 1, b: 1 };

const source1 = { b: 2, c: 2 };
const source2 = { c: 3 };

Object.assign(target, source1, source2);
target // {a:1, b:2, c:3}
```





如果只有一个参数，`Object.assign`会直接返回该参数。

```dart
const obj = {a: 1};
Object.assign(obj) === obj // true
```

**==如果该参数不是对象，则会先转成对象，然后返回。==**

```jsx
typeof Object.assign(2) // "object"
```

**==由于`undefined`和`null`无法转成对象==**，所以如果它们作为参数，就会报错。

```jsx
Object.assign(undefined) // 报错
Object.assign(null) // 报错
```





**==如果非对象参数出现在源对象的位置（即非首参数）==**，那么处理规则有所不同。首先，这些参数都会转成对象，**==如果无法转成对象，就会跳过==**。这意味着，如果`undefined`和`null`不在首参数，就==不会报错==。

```jsx
let obj = {a: 1};
Object.assign(obj, undefined) === obj // true
Object.assign(obj, null) === obj // true
```

其他类型的值（即**==数值、字符串和布尔值==**）不在首参数，也不会报错。但是，除了==字符串==会以**==数组形式==**，拷贝入目标对象，**==其他值都不会产生效果。==**

```jsx
const v1 = 'abc';
const v2 = true;
const v3 = 10;

const obj = Object.assign({}, v1, v2, v3);
console.log(obj); // { "0": "a", "1": "b", "2": "c" }
```

上面代码中，`v1`、`v2`、`v3`分别是字符串、布尔值和数值，结果只有字符串合入目标对象（以字符数组的形式），数值和布尔值都会被忽略。这是因为只有字符串的包装对象，**会产生可枚举属性**。

```dart
Object(true) // {[[PrimitiveValue]]: true}
Object(10)  //  {[[PrimitiveValue]]: 10}
Object('abc') // {0: "a", 1: "b", 2: "c", length: 3, [[PrimitiveValue]]: "abc"}
```

上面代码中，布尔值、数值、字符串分别转成对应的包装对象，可以看到它们的原始值都在包装对象的内部属性 `[[PrimitiveValue]]`上面，这个属性是不会被`Object.assign`拷贝的。只有字符串的包装对象，会产生可枚举的实义属性，那些属性则会被拷贝。





`Object.assign`拷贝的属性是有限制的，只拷贝源对象的自身属性（**==不拷贝继承属性==**），也**==不拷贝不可枚举的属性==**（`enumerable: false`）。

```dart
Object.assign({b: 'c'},
  Object.defineProperty({}, 'invisible', {
    enumerable: false,
    value: 'hello'
  })
)
// { b: 'c' }
```

上面代码中，`Object.assign`要拷贝的对象只有一个不可枚举属性`invisible`，这个属性并没有被拷贝进去。

属性名为 Symbol 值的属性，也会被`Object.assign`拷贝。

```dart
Object.assign({ a: 'b' }, { [Symbol('c')]: 'd' })
// { a: 'b', Symbol(c): 'd' }
```

------



#### 注意点

##### （1）浅拷贝

`Object.assign`方法实行的是**==浅拷贝==**，而不是深拷贝。也就是说，如果源对象某个属性的值是对象，**==那么目标对象拷贝得到的是这个对象的引用。==**，并不是实际的对象内容

```dart
const obj1 = {a: {b: 1}};
const obj2 = Object.assign({}, obj1);

obj1.a.b = 2;
obj2.a.b // 2
```

上面代码中，源对象`obj1`的`a`属性的值是一个对象，`Object.assign`拷贝得到的是这个对象的引用。**==这个对象的任何变化，都会反映到目标对象上面。==**

##### （2）同名属性的替换

对于这种嵌套的对象，一旦遇到**==同名属性==**，`Object.assign`的处理方法是**==替换==**，而不是添加。

```dart
const target = { a: { b: 'c', d: 'e' } }
const source = { a: { b: 'hello' } }
Object.assign(target, source)
// { a: { b: 'hello' } }
```

上面代码中，`target`对象的`a`属性被`source`对象的`a`属性整个替换掉了，而不会得到`{ a: { b: 'hello', d: 'e' } }`的结果。这通常不是开发者想要的，需要特别小心。

一些函数库提供 `Object.assign`的定制版本（比如 Lodash 的`_.defaultsDeep`方法），可以得到深拷贝的合并。

##### （3）数组的处理

`Object.assign`可以用来处理数组，但是会把**==数组视为对象==**。

```dart
Object.assign([1, 2, 3], [4, 5])
// [4, 5, 3]
```

上面代码中，`Object.assign`把数组视为属性名为 0、1、2 的对象，**因此源数组的 0 号属性`4`覆盖了目标数组的 0 号属性`1`。**

##### （4）取值函数的处理

`Object.assign`只能进行值的复制，如果要复制的值是一个取值函数，那么将求值后再复制。

```jsx
const source = {
  get foo() { return 1 }
};
const target = {};

Object.assign(target, source)
// { foo: 1 }
```

上面代码中， `source`对象的`foo`属性是一个取值函数，`Object.assign`不会复制这个取值函数，**==只会拿到值以后，将这个值复制过去。==**

#### 常见用途

`Object.assign`方法有很多用处。

##### （1）为对象添加属性

```jsx
class Point {
  constructor(x, y) {
    Object.assign(this, {x, y});
  }
}
```

上面方法通过`Object.assign`方法，将`x`属性和`y`属性添加到`Point`类的对象实例。

##### （2）为对象添加方法

```javascript
Object.assign(SomeClass.prototype, {
  someMethod(arg1, arg2) {
    ···
  },
  anotherMethod() {
    ···
  }
});

// 等同于下面的写法
SomeClass.prototype.someMethod = function (arg1, arg2) {
  ···
};
SomeClass.prototype.anotherMethod = function () {
  ···
};
```

上面代码使用了对象属性的简洁表示法，直接将两个函数放在大括号中，再使用`assign`方法添加到`SomeClass.prototype`之中。

##### （3）克隆对象

```jsx
function clone(origin) {
  return Object.assign({}, origin);
}
```

上面代码将原始对象**==拷贝到一个空对象==**，就得到了原始对象的克隆。

不过，采用这种方法克隆，**==只能克隆原始对象自身的值，不能克隆它继承的值==**。

**==如果想要保持继承链，可以采用下面的代码。==**

```jsx
function clone(origin) {
  let originProto = Object.getPrototypeOf(origin);
  return Object.assign(Object.create(originProto), origin);
}
```

##### （4）合并多个对象

将多个对象合并到某个对象。

```jsx
const merge = (target, ...sources) => Object.assign(target, ...sources);
```

如果希望合并后返回一个新对象，可以改写上面函数，对一个空对象合并。

```jsx
const merge = (...sources) => Object.assign({}, ...sources);
```

##### （5）为属性指定默认值

```jsx
const DEFAULTS = {
  logLevel: 0,
  outputFormat: 'html'
};

function processContent(options) {
  options = Object.assign({}, DEFAULTS, options);
  console.log(options);
  // ...
}
```

上面代码中，`DEFAULTS`对象是默认值，`options`对象是用户提供的参数。`Object.assign`方法将`DEFAULTS`和`options`合并成一个新对象，如果两者有同名属性，则`option`的属性值会覆盖`DEFAULTS`的属性值。

注意，由于存在浅拷贝的问题，`DEFAULTS`对象和`options`对象的所有属性的值，最好都是简单类型，不要指向另一个对象。否则，`DEFAULTS`对象的该属性很可能不起作用。

```csharp
const DEFAULTS = {
  url: {
    host: 'example.com',
    port: 7070
  },
};

processContent({ url: {port: 8000} })
// {
//   url: {port: 8000}
// }
```

上面代码的原意是将 `url.port`改成 8000，`url.host`不变。实际结果却是`options.url`覆盖掉`DEFAULTS.url`，所以`url.host`就不存在了。



### es6中class类

#### 基础

传统的javascript中只有对象，没有类的概念。它是基于原型的面向对象语言。原型对象特点就是将自身的属性共享给新对象。这样的写法相对于其它传统面向对象语言来讲，很有一种独树一帜的感脚！非常容易让人困惑！
 如果要生成一个**==对象实例==**，需要先定义一个**==构造函数==**，然后通过new操作符来完成。构造函数示例：

**<font color='red'>方法一般定义在原型上，属性一般直接定义在构造函数里面</font>**

```jsx
//函数名和实例化构造名相同且大写（非强制，但这么写有助于区分构造函数和普通函数）
function Person(name,age) {
    this.name = name;
    this.age=age;
}
Person.prototype.say = function(){
    return "我的名字叫" + this.name+"今年"+this.age+"岁了";
}
var obj=new Person("laotie",88);//通过构造函数创建对象，必须使用new 运算符
console.log(obj.say());//我的名字叫laotie今年88岁了
```

**构造函数生成实例的执行过程：**

```dart
1.当使用了构造函数，并且new 构造函数(),后台会隐式执行new Object()创建对象;
2.将构造函数的作用域给新对象，（即new Object()创建出的对象），而函数体内的this就代表new Object()出来的对象。
3.执行构造函数的代码。
4.返回新对象（后台直接返回）;
```

ES6引入了**==Class（类）==**这个概念，通过class关键字可以定义类。该关键字的出现使得其在对象**==写法上更加清晰，更像是一种面向对象的语言==**。如果将之前的代码改为ES6的写法就会是这个样子：



```kotlin
class Person{//定义了一个名字为Person的类
    constructor(name,age){//constructor是一个构造方法，用来接收参数
        this.name = name;//this代表的是实例对象
        this.age=age;
    }
    say(){//这是一个类的方法，注意千万不要加上function，写在class里面其实相当于Person.prototype.say定义在原型上面
        return "我的名字叫" + this.name+"今年"+this.age+"岁了";
    }
}
var obj=new Person("laotie",88);
console.log(obj.say());//我的名字叫laotie今年88岁了
```

**==注意项==**

1.在类中声明方法的时候，千万**<font color='red'>不要给该方法加上function关键字</font>**

2.**<font color='red'>方法之间不要用逗号分隔</font>**，否则会报错



由下面代码可以看出类实质上就是一个函数。类自身指向的就是构造函数。所以可以认为ES6中的**==类其实就是构造函数的另外一种写法==**！

```tsx
console.log(typeof Person);//function
console.log(Person===Person.prototype.constructor);//true
```

以下代码说明构造函数的prototype属性，在ES6的类中依然存在着。
 `console.log(Person.prototype);//输出的结果是一个对象`
 实际上**==类的所有方法都定义在类的prototype属性上==**。代码证明下：

```jsx
Person.prototype.say=function(){//定义与类中相同名字的方法。成功实现了覆盖！
    return "我是来证明的，你叫" + this.name+"今年"+this.age+"岁了";
}
var obj=new Person("laotie",88);
console.log(obj.say());//我是来证明的，你叫laotie今年88岁了
```

当然也可以通过prototype属性对类添加方法。如下：

```jsx
Person.prototype.addFn=function(){
    return "我是通过prototype新增加的方法,名字叫addFn";
}
var obj=new Person("laotie",88);
console.log(obj.addFn());//我是通过prototype新增加的方法,名字叫addFn
```

还可以通过**==Object.assign方法==**来为对象动态增加方法

```jsx
Object.assign(Person.prototype,{
    getName:function(){
        return this.name;
    },
    getAge:function(){
        return this.age;
    }
})
var obj=new Person("laotie",88);
console.log(obj.getName());//laotie
console.log(obj.getAge());//88
```

**==constructor方法是类的构造函数的默认方法==**，**==通过new命令生成对象实例时，自动调用该方法==**。

```jsx
class Box{
    constructor(){
        console.log("啦啦啦，今天天气好晴朗");//当实例化对象时该行代码会执行。
    }
}
var obj=new Box();
```

constructor方法如果没有显式定义，会隐式生成一个constructor方法。**==所以即使你没有添加构造函数，构造函数也是存在的==**。constructor方法**==默认返回实例对象this==**，但是**==也可以指定constructor方法返回一个全新的对象==**，让返回的实例对象不是该类的实例。

```jsx
class Desk{
    constructor(){
        this.xixi="我是一只小小小小鸟！哦";
    }
}
class Box{
    constructor(){
       return new Desk();// 这里没有用this哦，直接返回一个全新的对象
    }
}
var obj=new Box();
console.log(obj.xixi);//我是一只小小小小鸟！哦
```

constructor中定义的属性可以称为**==实例属性==**（即定义在**==this对象上==**），constructor外声明的属性都是定义在原型上的，可以称为**==原型属性==**（即定义在**==class上==**)。

**==hasOwnProperty()函数==**用于判断属性是否是**==实例属性==**。其结果是一个布尔值， true说明是实例属性，false说明不是实例属性。

ps：**==in操作符==**会在通过对象能够访问给定属性时返回true，**==无论该属性存在于实例中还是原型中。==**

```jsx
class Box{
    constructor(num1,num2){
        this.num1 = num1;
        this.num2=num2;
    }
    sum(){
        return num1+num2;
    }
}
var box=new Box(12,88);
console.log(box.hasOwnProperty("num1"));//true
console.log(box.hasOwnProperty("num2"));//true
console.log(box.hasOwnProperty("sum"));//false
console.log("num1" in box);//true
console.log("num2" in box);//true
console.log("sum" in box);//true
console.log("say" in box);//false
```

类的所有实例共享一个原型对象，它们的原型都是**Person.prototype**，**==所以实例的proto属性是相等的==**

```jsx
class Box{
    constructor(num1,num2){
        this.num1 = num1;
        this.num2=num2;
    }
    sum(){
        return num1+num2;
    }
}
//box1与box2都是Box的实例。它们的__proto__都指向Box的prototype
var box1=new Box(12,88);
var box2=new Box(40,60);
console.log(box1.__proto__===box2.__proto__);//true
```

由此，也可以通过**proto**来为类增加方法。使用实例的**proto**属性改写原型，会改变Class的原始定义，**==影响到所有实例，所以不推荐使用==**！

```jsx
class Box{
    constructor(num1,num2){
        this.num1 = num1;
        this.num2=num2;
    }
    sum(){
        return num1+num2;
    }
}
var box1=new Box(12,88);
var box2=new Box(40,60);
box1.__proto__.sub=function(){
    return this.num2-this.num1;
}
console.log(box1.sub());//76
console.log(box2.sub());//20
```

**==class不存在变量提升==**，所以需要先定义再使用。因为ES6不会把类的声明提升到代码头部，但是ES5就不一样,**ES5存在变量提升**,可以先使用，然后再定义。

```jsx
//ES5可以先使用再定义,存在变量提升
new A();
function A(){

}
//ES6不能先使用再定义,不存在变量提升 会报错
new B();//B is not defined
class B{

}
```



#### ==继承==

继承是面向对象中一个比较核心的概念。ES6 class的继承与java的继承大同小异，如果学过java的小伙伴应该很容易理解，都是通过==**extends关键字**==继承。相较于ES5当中通过原型链继承要清晰和方便许多。先上代码：

```jsx
class Cucurbit{
    constructor(name,color){
        console.log("farther")
        this.name=name;
        this.color=color;
    }
    say(){
        console.log("我的名字叫"+this.name+"我是"+this.color+"颜色的");
    }
}
class First extends Cucurbit{
    constructor(name,color){
        super(name,color);// 调用父类的constructor(name,color)
    }
    say(){
        console.log("我是child");
        super.say();
    }
}
var wa=new First("大娃","红色");
wa.say();
```

输出：

```undefined
farther
我是child
我的名字叫大娃我是红色颜色的
```

上面代码中，子类的constructor方法和say方法中，都出现了==super关键字==，它在这里表示父类的构造函数，用来新建父类的this对象。

 **==子类必须在constructor方法中调用super方法，之后才能使用this关键字==**，否则新建实例时会报错。这是因为子类没有自己的this对象，而是继承父类的this对象。**==如果不调用super方法，子类就得不到this对象==**。

**<font color='red'>在这一点上ES5的继承与ES6正好相反</font>**，**==ES5先创建自己的this对象然后再将父类的属性方法添加到自己的this当中==**。

 **==如果子类First没有显式的定义constructor，那么下面的代码将被默认添加==**(不信可以尝试下，哈)。换言之，如果constructor函数中只有super的话，该constructor函数可以省略。

```tsx
constructor(name,color){
        super(name,color);// 调用父类的constructor(name,color)
}
```

**==总结super在子类中一般有三种作用==**

```undefined
 1.作为父类的构造函数调用(已说明）
 2.在普通方法中，作为父类的实例调用（已说明）
 3.在静态方法中，作为父类调用（下篇文章会做介绍）
```

##### 实例

> 创建一个tab切换，页面中有三个按钮内容分别为“中”，“日”，“韩”。要求点击按钮，按钮以及切换的内容的背景颜色分别会变为红，黄，绿。

首先创建一个tab.html页面，内容为：

```xml
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>切换</title>
    <style>
        #country input{
            margin:10px;
            padding:10px;
        }
        #country div{
           width:300px;
            height:300px;
        }
    </style>
</head>
<body>
<div id="country">
    <input type="button" value="中">
    <input type="button" value="日">
    <input type="button" value="韩">
    <div>中国</div>
    <div>日本</div>
    <div>韩国</div>
</div>
</body>
<script src="tag.js"></script>
<script>
    new Tag("#country");
</script>
</html>
```

然后创建一个tag.js,内容为：

```kotlin
class Tag{
    constructor(id){
        this.id=document.querySelector(id);
        this.btn=this.id.querySelectorAll("input");
        this.div=this.id.querySelectorAll("div");
        this.colorArr=["red","yellow","green"];
        this.index=0;//显示元素的下标。
        this.init();
    }
    init(){//初始化
        this.hide();
        this.show();
        //给按钮增加事件
        for(let i=0;i<this.btn.length;i++){
            this.btn[i].onclick=function(){
                this.index=i;
                this.hide();
                this.show();
            }.bind(this)
        }
    }
    hide(){//隐藏DIV,去除按钮背景色
        for(var i=0;i<this.btn.length;i++){
            this.btn[i].style.background=null;
            this.div[i].style.display="none";
        }
    }
    show(){//显示指定的DIV,按钮与DIV的背景颜色进行设置
        this.div[this.index].style.display="block";//将DIV进行显示
       //按钮与DIV的背景颜色进行设置
        this.div[this.index].style.background=this.btn[this.index].style.background=this.colorArr[this.index];
    }
}
```

> 示例到现在还没有用到ES6的继承啊，别急！咱们再加个需求，在上面的切换示例基础上，再加一个内容为“娱乐”，“体育"，"财经"的切换。该切换需要在原来可点击的基础上实现自动切换功能，以及点击页面空白区域也可实现切换。

将tag.html页面修改为：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>切换</title>
    <style>
        #country input,#news input{
            margin:10px;
            padding:10px;
        }
        #country div,#news div{
            width:300px;
            height:300px;
        }
    </style>
</head>
<body>
<div id="country">
    <input type="button" value="中">
    <input type="button" value="日">
    <input type="button" value="韩">
    <div>中国</div>
    <div>日本</div>
    <div>韩国</div>
</div>
<div id="news">
    <input type="button" value="娱乐">
    <input type="button" value="财经">
    <input type="button" value="体育">
    <div>娱乐</div>
    <div>财经</div>
    <div>体育</div>
</div>

</body>
<script src="tag.js"></script>
<script>
    new Tag({
        id:"#country",
        index:1,
        colorArr:["red","green","blue"]
    });
    new autoTag({
        id:"#news",
        index:2,
        colorArr:["black","pink","purple"]
    });
</script>
</html>
```

将tag.js修改为：

```kotlin
class Tag{
    constructor(obj){
        this.id=document.querySelector(obj.id);
        this.btn=this.id.querySelectorAll("input");
        this.div=this.id.querySelectorAll("div");
        this.colorArr=obj.colorArr;
        this.index=obj.index;//显示元素的下标。
        this.init();
    }
    init(){//初始化
        this.hide();
        this.show();
        var that=this;
        //给按钮增加事件
        for(let i=0;i<this.btn.length;i++){
            this.btn[i].onclick=function(ev){
                this.index=i;
                this.hide();
                this.show();
                ev.cancelBubble=true;
            }.bind(this)
        }
    }
    hide(){//隐藏DIV,去除按钮背景色
        for(var i=0;i<this.btn.length;i++){
            this.btn[i].style.background=null;
            this.div[i].style.display="none";
        }
    }
    show(){//显示指定的DIV,按钮与DIV的背景颜色进行设置
        this.div[this.index].style.display="block";//将DIV进行显示
        //按钮与DIV的背景颜色进行设置
        this.div[this.index].style.background=this.btn[this.index].style.background=this.colorArr[this.index];
    }

}
class autoTag extends Tag{
    constructor(id){
        super(id);
        this.autoInit();
    }
    autoInit(){
        document.body.onclick=this.change.bind(this);
        setInterval(this.change.bind(this),5000)
    }
    change(){
        this.index+=1;
        if(this.index>=this.btn.length)
            this.index=0;
        this.hide();
        this.show();
    }

}
```





#### ==静态方法==

**==不需要实例化类，即可直接通过该类来调用的方法，即称之为“静态方法”==**。将类中的方法设为静态方法也很简单，在**==方法前==**加上**==static关键字==**即可。**<font color='red'>这样该方法就不会被实例继承！</font>**

```cpp
class Box{
    static a(){
        return "我是Box类中的，实例方法，无须实例化，可直接调用！"
    }
}
//通过类名直接调用
console.log(Box.a());//我是Box类中的，实例方法，无须实例化，可直接调用！
```

上面的代码一，类Box的a方法前有static关键字， 表明该方法是一个静态方法， 可以直接在Box类上调用。**==静态方法只能在静态方法中调用,不能在实例方法中调用==**。

**<font color='red'>静态方法属于类，而不属于实例对象</font>**

**<font color='red'>类似于在es5中往构造函数中添加属性和对象，这些属性和对象只能通过构造函数来调用，不能通过实例对象来调用</font>**

![image-20210421090112419](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421090112419.png)

```javascript
class Box{
    static a(){
        return "我只允许被静态方法调用哦！"
    }
    static b(){
        //通过静态方法b来调用静态方法a
        console.log(this.a());
    }
}
Box.b();//输出：我只允许被静态方法调用 哦
```

**==通过实例方法来调静态方法会报错：==**

```javascript
class Box{
    static a(){
        return "我只允许被静态方法调用哦！"
    }
    b(){
        console.log(this.a());//TypeError: this.a is not a function
    }
}
var obj=new Box();
obj.b();
```

**==父类的静态方法， 可以被子类继承：==**

```javascript
class Box {
    static a() {//父类Box的静态方法
        return '我是父类的静态方法a';
    }
}
class Desk extends Box {}
//子类Desk可以直接调用父类的静态方法a
console.log(Desk.a()); 
```

倘若想**==通过子类的静态方法调用父类的静态方法==**，需要从**==super对象==**上调用:

```javascript
class Box {
    static a() {
        return '我是通过super来调取出来的';
    }
}
class Desk extends Box {
    static a(){
        return super.a();
    }
}
console.log(Desk.a()); 
```

##### 静态属性

**==静态属性==**指的是 **==Class 本身的属性==**， 即Class.propname， 而不是定义在实例对象（ this） 上的属性。

```jsx
class Box{
   constructor(){
       this.name="实例属性"
   }
}
Box.prop1="静态属性1";//在外部定义的即为静态属性
Box.prop2="静态属性2";
console.log(Box.prop1,Box.prop2);//静态属性1  静态属性2
```

















### 箭头函数

#### 基本使用

箭头函数也是一种定义函数的方式，可以用于立即执行函数，或者回调函数中

es5中两种定义函数的方法

**==普通定义：==**

const fun = function(){}

**==对象字面量中定义函数：==**

const obj = {

bbb:function(){},

ccc(){}

}

**==es6中箭头函数的方式定义：==**

**没有参数：**

```js
const ccc = () => {
    
}
```

**有两个参数：**

```javascript
const sum = (num1,num2) => {
    return num1+num2
}
```

**有一个参数：**一个参数时，括号可以省掉

```javascript
const power = (num) => {
    return num*num
}
const power = num => {
    return num*num
}
```

**函数代码块中只有一行代码：**可以将中括号和return都省掉（一起省掉）

​	**这样也会将这一行代码进行执行，并且返回出去**

```javascript
const sum (num1,num2) => num1+num2
```

像下面这种没有返回值，但是**只有一行代码**的也可以使用，这一行代码会执行，**返回值为undefined**

```javascript
const demo () =>console.log('hello world')
```



#### 箭头函数中的this的使用

问题：箭头函数中的this是如何查找的了？

答案：**==向外层作用域中，一层层查找this,直到有this的定义==**

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617697901646.png" alt="1617697901646" style="zoom:67%;" />

 

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617698186613.png" alt="1617698186613" style="zoom:67%;" />







### promise

![1617970737603](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617970737603.png)

#### 异步和同步

一般的操作都是**==同步（sync）==**的，像对一个便变量进行赋值然后打印出来，等等这样的基本操作都是同步操作

**==异步操作（async）==**一个很常见的应用场景是在发送网络请求的时候：一般网络请求是需要一定时间的，这时候代码执行到网络请求的地方会发生阻塞，其他操作不会有任何的作用，b必须等网络请求结束后才能进行其他操作，这时候就需要异步操作了。

为网络请求开启一个异步任务，让异步任务单独去处理这个网络请求，代码后面的地方继续对用户进行交互

当网络请求任务结束，网络请求数据回来后，我们灰顶以一个回调函数，在回调函数中拿到我们网络请求的数据

#### promise

![1618016611611](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618016611611.png)

![1618016686327](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618016686327.png)

**==Promise就是用来封装异步操作的==**，可以**==帮助我们以一种更加优雅的方式来处理多层嵌套异步操作==**

通过new新建一个Promise对象，这个构造函数需要一个参数

这个参数是一个函数，函数需要两个参数

这两个参数也是两个函数

​	

**==体会resolve作用例子:==**

将setTimeout延迟函数看成网络请求，收到数据后，进行相关操作，相关操作中再次发球网络请求，多次嵌套

```javascript
setTimeout(()=>{
	console.log('hello world');
	console.log('hello world');
	console.log('hello world');
	
	setTimeout(()=>{
		console.log('hello vue');
		console.log('hello vue');
		console.log('hello vue');
		console.log('hello vue');
		
		setTimeout(()=>{
			console.log('hello pyhton');
			console.log('hello pyhton');
			console.log('hello pyhton');
			console.log('hello pyhton');
		},1000)
	},1000)
},1000)
```

使用Promise，新建一个Promise对象，将网络请求操作放到Promise中实现

**==网络请求收到后的进行的操作使用resolve函数进行代替==**，**==网络请求失败后的操作放到reject函数中去==**，下面会讲到

**==将具体的操作放到Promise对象后的then方法中，作为返回函数==**



```javascript
new Promise((resolve,reject) => {
    //第一次网络请求代码
	setTimeout(()=>{
		resolve();
	},1000)
}).then(()=>{
    //第一次拿到结果处理的代码
	console.log('hello world');
	console.log('hello world');
	console.log('hello world');
	
	return new Promise((resolve,reject) => {
        //第二次网络请求代码
		setTimeout(()=>{
			resolve();
		},1000)
	}).then(() => {
        //第二次拿到结果处理的代码
		console.log('hello vue');
		console.log('hello vue');
		console.log('hello vue');
		console.log('hello vue');
		
		return new Promise((resolve,reject) => {
            //第三次网络请求代码
			setTimeout(()=>{
				resolve();
			},1000)
		}).then(() => {
            //第三次拿到结果处理的代码
			console.log('hello pyhton');
			console.log('hello pyhton');
			console.log('hello pyhton');
			console.log('hello pyhton');
		})
	})
})
```

网络请求一般是有返回值返回的，就比如例子中的setTimeout中返回函数应该是有参数的，或者这个返回函数中会会有变量传入到之后的参数

**==这些参数是可以通过resolve来传递==**的

就比如下这两个例子：

![1618020154554](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618020154554.png)

![1618020190179](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618020190179.png)

将之前的**<font color='red'>多层包含嵌套</font>**变成了**<font color='red'>链式</font>**，结构更清晰

实现**==链式编程==**



上面讲到的resolve是网请求成功时调用的

**==网络请求失败时调用reject==**，**==reject函数作为参数，可选可不选==**，可以只写一个resolve函数作为参数。用reject()函数来替换相应操作，具体操作放到catch函数中去

**==catch函数作为方法补到then方法后面==**

用法跟resolve和then是一样的，reject中的变量、字符串也会作为数据传递到catch中的**==返回函数去==**，**==直接用参数接受就行==**

![1618020895134](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618020895134.png)



无论成功与失败还可以为Promise最后面（在then和catch最后面）跟上一个**==.finally(()=>{})==**，**==表示无论成功或失败都要执行==**

#### promise的三种状态和另外一种处理方式

![1618021324000](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618021324000.png)

另一种处理方式，异步操作成功后，会调用resolve函数，失败会调用reject函数

具体的操作步骤放在then()函数和catch()函数中去执行

之前对于then()和catch()这两个函数写法如下：

```javascript
new Promise((resolve,reject) => {
	setTimeout(()=>{
		resolve();
		reject();
	},1000)
}).then().catch()
```

还有一种写法是**==只写一个then==**，then里面可以传**==两个返回函数作为参数==**，**==分别对应异步操作成功与失败的返回函数==**

![1618021785296](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618021785296.png)



<font color='red'>**一个例子：**</font>往页面中加载图片时，使用Promise进行异步操作

![image-20210511183003592](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210511183003592.png)







#### promise的链式调用

![1618023274610](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618023274610.png)





**<font color='red'>①</font>**

假设一个场景，网络请求得来的数据，先处理10行，然后在将数据传给下面的异步操作进行封装，后面的异步操做没有setTimeout延迟函数

没有用到reject函数的话就可以省略，绝具体操作如下

![1618025289522](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618025289522.png)

**<font color='red'>②</font>**

每次return时都要新建一个Promise对象，将这个对象进行返回，每次返回都是Promise对象，官方用法就提供了一个简便写法，直接return的是**==Promise.resolve(传到then函数的数据)==**

![1618025226205](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618025226205.png)

**<font color='red'>③</font>**

再次基础上还有一个简便写法，在return中还可以**==直接省略掉Promise.resolve==**，**==直接返回要传到下一个then函数的数据==**

![1618026499882](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618026499882.png)

**<font color='red'>④</font>**

当上面这种链式操作中**有一步执行失败**了，**后面的内容就不会进行执行**，如果想在某一步加上reject函数，**第③步中省略掉Promise.resolve的操作就不能用了**，在最末尾加上一个catch()函数，会执行操作失败后的内容，中间的resolve的步骤就省略了

![1618026795257](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618026795257.png)

其中如果不写return reject函数，写**==throw（抛出异常）==**也可以

![1618027076630](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618027076630.png)





#### Promise的all方法的使用

在没有使用promise的时候，如果遇到一种情况：某种操作需要两个网络请求的结果拿到之后，在进行相应的操作

这两个网络请求也不知道是谁先拿到，如果想完成这个要求，下面代码是一种方案：

![1618030854426](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618030854426.png)

![1618030867842](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618030867842.png)



为此Promise中有一个**==all方法==**来解决这个问题

Promise.all()参数是一个**==数组==**，数组里面放的是**==多个Promise异步操作==**，**==Promise.all()后面只跟着一个.then()==**（**<font color='red'>而不是跟在两个Promise对象后面</font>**），参数是一个返回函数，返回函数的参数只一个数组，数组的内容是上面多个异步操作的结果

下面是JQuery中的ajax操作：

![1618031274231](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618031274231.png)

为了更方便理解，使用setTimeout函数来代替网络请求等异步操作

![1618031773118](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618031773118.png)

![1618031753823](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618031753823.png)

**==这就完成了拿到多次网络请求结果==**



ES2020 新增Promise.allSettled 弥补了Promise.all的缺陷  可以百度学习



#### Promise优缺点

**==---Promise 优点：==**

有了 Promise 对象，就可以将异步操作以同步操作的流程表达出来，避免了层层嵌套的回调函数。此外，Promise 对象提供统一的接口，使得控制异步操作更加容易。

**==---Promise 缺点：==**

首先，无法取消 Promise，一旦新建它就会立即执行，无法中途取消。其次，如果不设置回调函数，Promise 内部抛出的错误，不会反应到外部。第三，当处于 Pending 状态时，无法得知目前进展到哪一个阶段（刚刚开始还是即将完成）。





### 对象/数组的解构

![1618139599253](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618139599253.png)

将一个对象里面的属性拿出来，除了依次为每个属性赋值外，还可以直接利用对象的解构

像上面这样**==const {属性名1,属性名2,属性名3} = obj==**

其中属性名都是对象中的真实属性名，这样就可以一次性地将对象中多个属性取出来

**==vuex中的一个例子==**，默认actions中的函数参数是**context**，将函数参数的地方**用{state,commit,rootState}来代替**，就相当于将context进行解构，取出里面的三个属性

![1618140227716](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618140227716.png)

同样，数组也有解构

![1618149729726](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618149729726.png)











































































































































