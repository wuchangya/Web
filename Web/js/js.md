### js中的helloworld

document.write()可以行body中输出一个内容

console.log()向控制台输出一个内容

### js代码编写的位置

**①可以写在标签的属性中**，比如：onclick、herf中，但是他们属于结构与行为耦合，不方便维护，不推荐使用。

![1615011350932](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615011350932.png)

![1615011367355](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615011367355.png)

**②写在script标签中写**

![1615011451974](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615011451974.png)

**③写在外部的js文件中**，通过script标签引入，将文件的路径写在src后面

![1615011561727](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615011561727.png)

某个script标签已经引入外部文件后，就不能再在标签中编写js代码了，即使编写了浏览器也会忽略，如果想写，就在编写一个script标签

### js基本语法

①注释

/*   */多行注释

//单行注释

②js严格区分大小写

③每一句以分号结尾

​		如果不写分号，浏览器会自动添加，但是会消耗一些系统资源，而且有时候会加错分号

### 字面量和变量

js中用**var**来声明一个变量

![1615012542928](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615012542928.png)

### 标识符

驼峰法命名：首字母 小写，每个单词的开头字母大写，其余小写

![1615012846361](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615012846361.png)

js底层保存标识符采用的是Unicode编码，理论上讲所有utf-8中的内容都可以作为标识符

### 数据类型

String字符串

Number数值

Boolean布尔值

Null空值

Undefined未定义

Object对象

---------------------------------------------------------------------

前5种属于**基本数据类型**，Object属于**引用数据类型**

typeof检查一个变量类型

![1615014103798](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615014103798.png)

#### **强制的类型转换**

**string的转换**

①调用被转换数据类型的**tostring()方法**，该方法不会影响原变量，只会将结果返回，null和undefined这两个值没有tostring方法

![1615015455088](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615015455088.png)

②调用string()函数来将参数转换为字符串

对于number和Boolean底层就是调用tostring

**number的准换**

①使用number()函数

​		纯数字的字符串可准换为number

​		非纯数字准换为NaN

​		空串转换为0

​		布尔准换为1/0

​		null准换为0

​		undefined准换为NaN

②**parseInt()函数**把一个字符串准换为整数，从左到右的整数部分保存下来

  **parseFloat()函数**把一个字符串转换为浮点数，从左到右的浮点数部分保存下来

![1615016497419](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615016497419.png)

![1615016536418](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615016536418.png)

对于非字符串值先转换为字符串然后进行操作

![1615016677853](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615016677853.png)

可以在parseInt()中传递第二个参数，来指定数字的**进制**

![1615016980894](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615016980894.png)

**Boolean值的准换**

Boolean()函数

​	数字：除了0和NaN，其他的都是true

​	字符串：除了空串，其他的都是true

​	null、undefined：转为false

​	对象：true





------------------------------------------------------------------------

**String字符串**

一些特殊符号可以使用\进行转义

![1615013631638](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615013631638.png)

![1615013709494](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615013709494.png)

**Number数值**

js中可以表示的数字最大值 Number.MAX_VARLUE，超过之后会返回一个Infinity（无穷）

Number.NIN_VARLUE  零以上的最小值

NaN 特殊的数字，Not a Number,typeof也是一个数字

使用js进行浮点数运算，可能得到一个不精确的结果，这是所有语言的通病

0x表示16进制的数字

0开头表示8进制的数字

0b开头表示2进制的数字，但并不是所有的浏览器支持

**Boolean布尔值**

**Null空值**

**Undefined未定义**

**Object对象**

### 运算符

也叫操作符

①无引号的非number值进行算数运算，先将值转换为number再运算，任何值与NaN做运算都得NaN

②对两个字符串加法操作，进行拼串操作

③任何值对字符串进行**加法**操作，先准换为字符串，再做拼串操作**（利用这一特殊点，可以将任意数据类型准换为空串）**

![1615018204020](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615018204020.png)

​	**==常见输出==**：

![1615018250378](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615018250378.png)

![1615018261099](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615018261099.png)

④若是- / *操作，将两个值都转为number进行操作即可（**利用这一特点看可以做隐式的类型准换：-0  *1  /1**）





### 一元运算符 

​    -   +  对于非number类型的值，先将其准换为number然后在运算（**利用这一特性，可以在其他数据类型前面用+将其转换为number**）



### 非布尔值的与或运算

会先将其转换为布尔值，然后在运算，然后再返回==**原值**==

**&&与运算**：第一个值为true，直接返回第二个值

​		     第一个值为false，直接返回第一个值（结合串联电路）

**||或运算**：第一个值为true，直接返回第一个值

​		    第一个值为false，直接返回第二个值（结合并联电路）



### 关系运算符

关系运算符比较两个值之间的大小关系，关系成立会返回true，不成立返回false

有非数值的话会先将其化为数字，然后再运算。

==如果符号两侧都是字符串==，不会转化为数字，直接比较两个字符串的**字符编码Unicode**，一位一位进行比较，如果两位一样则直接比较下一位（可以借此用来对英文进行排序）

如果想要比较两个字符串型的数字时，一定要转型（如利用加号进行转型）（==想利用用户输入值进行大小比较的情景==）

![1615087484950](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615087484950.png)

**==任何值和NaN作比较都是false==**



### 编码输出

\u四位Unicode编码（默认16进制）：代表此Unicode编码表示的字符

（html中用的是&#Unicode编码，但此处编码需要转为十进制）

### 相等运算符

如果值的类型不同，会自动转换为相同的类型然后比较，**大部分**是转换为数字

**==undefined\=\=null==**

**==NaN不和任何值相等==**

检查一个值是不是NaN用**isNaN()函数**来判断

==全等运算符==   

===：    和  ==  类似，但是**不会做类型的转换**，如果**类型不一样，直接返回false**

 !==  : 和!=类似，**不会做类型的转换，类型不一样，直接返回true**

### 条件表达式

也叫三元运算符

**==语法：条件表达式?语句1:语句2==**

条件表达式为true，执行语句1，返回执行结果

条件表达式为false，执行语句1，返回执行结果

**条件表达式的结果为一个非布尔值，先转换为布尔值，然后在运算**

![1615092913630](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615092913630.png)

![1615093010118](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615093010118.png)

![1615093152546](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615093152546.png)



### 运算符优先级

![1615093424015](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615093424015.png)



### 代码块

用{ }来表示代码块，他只具有分组功能，代码块中的内容对外完全可见



### 条件分支语句

也叫switch语句，switch条件表达式和case 表达式如果匹配，从当前的case==**开始执行，后面的case也会跟着执行**==

语法：switch（条件表达式）{

​		case 表达式：

​			语句

​			break；

​		case 表达式：

​			语句

​			break；

​		default：

​			语句

​	 		break；

​	}	

![1615096642535](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615096642535.png)

==js中除法会得到一个浮点数（与其他语言不同），要**得到整数商还要进行取整操作**==



### break和continue



**break**

**==只有一个break会立即终止离他最近的那个循环语句==**

可以为循环语句创建一个label，来标识当前的循环

语法为label:循环语句，这样可以结束指定循环

![1615104485135](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615104485135.png)



continue**==终止当次的循环==**，也可以像break一样使用标签







### 对象

对象分类：

**内建对象**：ES标准定义的对象，在任何的ES的实现中都可以使用，如**==Math, String, Number, Boolean, Function, Object==**

**宿主对象**：==JS运行环境提供的对象，主要是指浏览器中的对象== ，如BOM（**浏览器对象模型**） 和DOM（**文档对象模型**）这两组对象，像console和document

**自定义对象**：由开发人员定义	



#### 自定义对象

使用**new关键字**调用的函数，是构造函数constructor，==构造函数是专门用来创建对象的函数==。如var obj =new Object{}

也可以直接使用字面量来创建一个对象：var obj ={}

![1615275025610](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615275025610.png)



向对象中添加属性，语法：对象.属性名:属性值

![1615272545627](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615272545627.png)

读取对象中的属性，语法：对象.属性名

修改对象中的属性，语法：对象.属性名:新值

删除对象的属性，语法：delete 对象.属性名

### 属性名和属性值

**属性名**不强制要求遵守标识符的规范，想用啥用啥，按使用时尽量按照规范

如果需要特殊的属性名，创建和读取都要采用另一种方式：

​	**语法：对象["属性名"]=属性值**

使用[]这种方式读属性时更加灵活，==[]中的属性名可以用一个变量表示==，

![1615273250207](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615273250207.png)



**属性值**可以使任一种数据类型，也可以是另外一个对象、函数

![1615273483101](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615273483101.png)

![1615282417756](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615282417756.png)

==如果一个函数作为一个对象的属性保存，那么我们称这个函数是这个对象的方法==



**in运算符**：通过该运算符可以检查一个对象中是否含有指定的属性，有则返回true，没有返回false

语法："属性名" in 对象

![1615282226260](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615282226260.png)



### 基本数据类型和引用数据类型

 基本数据类型：

![1615273941243](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615273941243.png)

引用数据类型：

![1615273914528](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615273914528.png)



js中的变量都是保存在==栈内存==中

**基本数据类型**的值直接在栈内存汇总存储，值与值之间是独立存在，修改一个不会影响另一个

![1615274511540](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615274511540.png)

对象是保存在==堆内存==中，每创建一个新的对象，就会在堆内存中开辟一个新的内存空间，这时变量保存的是对象的地址（对象的引用）

![1615274391816](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615274391816.png)

当修改变量值的时候，对其他变量不会产生影响，只会使当前对象的引用断开

![1615274662773](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615274662773.png)





当比较两个基本类型数据时，是比较值

当比较两个引用数据类型值，是比较对象的**内存地址**，哪怕值是一样的，地址不同，也会返回false



### 对象字面量

![1615275160617](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615275160617.png)

![1615277369062](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615277369062.png)

定义的时候就可以指定属性

属性名可以加引号也可以不加，**如果想使用特殊的属性名，则必须加引号**



### 函数

函数也是一个对象，函数中可以封装一些功能，**也具有普通对象的功能，也可以进行属性的定义等功能。**

**<font color='orange'>①</font>**

var fun =new Function("代码");//代码需要用双引	号括起来

调用函数：fun();

==但是，实际开发中很少使用到构造函数来创建一个函数。除非你需要创建实例对象==



**<font color='orange'>②</font>**

一般使用**函数声明**来创建函数

语法：

​	function 函数名([形参1,,形参2,...]){

​		语句

​	}//最后不用写分号

![1615278023753](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615278023753.png)



**<font color='orange'>③</font>**

或者，用**函数表达式**来创建一个函数

语法：

​	var 函数名 = function([形参1,形参2,....]){

​		语句

​	};

![1615278490974](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615278490974.png)

/**/就相当于使用一个匿名函数，然后在赋予一个函数名，与函数声明法没太大区别，但是在函数提升上有区别**





### 函数的参数

函数的解析器不会检查实参的类型，可以是任意类型，可以是对象、函数 

![1615279970360](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615279970360.png)

参数过多时，可以将所有参数封装 成一个对象传进去

![1615279699052](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615279699052.png)



也不会检查实参的数量，多余的实参不会被赋值

如果实参的数量少于形参的数量，则没有实参对应的形参将会是undefined

### 函数的返回值

![1615279042376](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615279042376.png)

return后的语句都不会执行



例子：

![1615279405027](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615279405027.png)

返回值可以是任意一个数据类型，可以是一个对象、函数

###  立即执行函数

![1615281977418](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615281977418.png)

![1615282093577](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615282093577.png)

将**匿名函数**用括号括起来表示一个整体，然后**后面再加一个括号进行立即使用**

立即执行函数只会使用一次



### 方法

如果一个**函数**作为一个**对象的属性**保存，那么我们称这个函数是这个对象的方法

（只是名称上的区别，没有本质区别）

![1615282649064](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615282649064.png)



### 对象中属性的枚举

==**语法：**==

==**for(var 变量 in 对象){**==

==**}**==

对象中有几次就循环几次，每次循环就会将对象中的一个属性赋值给变量

![1615283274567](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615283274567.png)



### 全局作用域

全局作用域：

-  直接编写在script标签中的js代码，都在全局作用域

-  它在页面打开时创建，页面关闭时销毁

-  全局作用域中有一个全局对象window，它代表的是一个浏览器的窗口，他由浏览器创建我们可以直接使用

-  在==全局作用域中，创建的变量都会作为**window的属性**保存，创建的函数都会作为**window的方法**保存==

-  全局作用域中定义的变量是全局变量，在页面的任意位置都可以访问到

​		 ![1615283722135](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615283722135.png)

 

### **变量的声明提前**

使用var关键字的变量，会在所有的代码执行之前被声明

![1615284029759](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615284029759.png)

==a会被指明undefined，但不会被报错==

如果声明变量没用var，就会报错



### 函数的声明提前

**（形式上感觉跟变量的声明提前刚好相反）**



使用==函数声明==形式创建的函数**function 函数名(){}**，他会在所有的代码执行之前就被创建，此种形式的函数想在哪调用在哪调用

使用==函数表达式==创建的函数不会被声明提前 ，不能提前调用 

函数声明：

![1615285249301](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615285249301.png)

函数表达式：

![1615285267074](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615285267074.png)



### 函数作用域

在函数作用域中操作一个变量时，现在自身作用域中找，没有则在上一级作用域中找，直到找到全局作用域中。

​	如果想直接访问全局作用域的变量，可以直接==window.变量==

函数作用域中也存在**变量的声明提前**和**函数声明的提前**



**==在函数中，不使用var声明的变量都会成为全局变量，同样相当于window.变量  的省略形式，变成window中的属性==**



==**例子：**==

![1615292464266](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615292464266.png)

**例子：**

![1615292956456](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615292956456.png)

undefined

456

![1615292963762](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615292963762.png)

undefined

123



### this

 解析器在调用函数每次都会想函数内部传递一个隐含的参数，这个隐含的参数就是this，this指向的是一个对象，我们称为函数执行的上下文对象

根据函数==**调用方式**==的不同，this会指向不同的对象

1.以**函数形式**调用时，this就是window（其实也就是window.fun()的省略形式）

2.以**方法的形式**调用，this就是使用这个调用方法的对象（**下面这个图的注释反了**）

![1615367280961](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615367280961.png)

3.在**构造函数**中可以使用this来引用**新建的对象**（在vue中经常用到）







补充：==在响应函数中，响应函数是给谁绑定的，this就是指谁== 并且极个别有一些例外，不用太在意，如IE8中为事件绑定响应函数的方法attachEvent()中this就代表的window

补充例子：

![1615986304446](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615986304446.png)

![1615986329176](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615986329176.png)

注意：例子中第一种形式，就是在定义一个对象的方法，以**方法的形式**调用，this就是使用这个调用方法的对象

教程<https://www.bilibili.com/video/BV1YW411T7GX?p=62&spm_id_from=pageDriver>



### 使用工厂方法创建对象

工厂法：

![1615367995439](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615367995439.png)

![1615368004123](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615368004123.png)





### 创建构造函数

构造函数就是一个专门创建某一类对象的函数，创建方式和普通函数没有区别

==构造函数习惯上**首字母大写**==

构造函数和普通函数区别在于**==调用方式==**的不同，普通函数直接调用，构造函数用new关键字调用（==也就是当一个函数别调用的时候用的是new调用的，那么此时他就成为了一个构造函数==）



**调用构造函数执行流程**：

​	立即创建一个新的对象

​	将新建的**==对象设置为函数中的this==**，在构造函数中可以使用this来引用新建的对象

​	逐行执行函数中的代码

​	将新建的对象作为返回值返回（==所以**一般构造函数不像普通函数需要return**==）





使用同一个构造函数创建的对象，我们称之为==**一类对象**==，也将一个构造函数成为一个类，通过创建函数创建的对象成为==该类的**实例**==



![1615369574652](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615369574652.png)



**==instanceof==：使用instanceof可一检查一个对象是否是一个类的实例**

![1615371067936](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615371067936.png)

















==this的情况总结==

![1615371027442](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615371027442.png)



### 构造函数的修改

![1615375993948](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615375993948.png)

创建一个person构造函数，函数中有一个sayname方法，一开始是在函数内部创建，但是这样的话每次调用构造函数都会产生一个新的对象、新的实例、新的方法，==所有实例的sayname都是不同的==

改进：

![1615376100952](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615376100952.png)

==**将方法放到全局变量中去定义**，这样所有实例的方法只用创建一次，不用每次都创建==













### 原型对象

上面讲到的，在全局作用域中定义sayname方法，这么做有不足：①污染了全局作用域的命名空间（**就是可能出现命名冲突的情况**）②放在全局作用域中很不安全



**原型prototype:**

我们创建每一个函数（无论是函数还是构造函数），解析器都会向函数中添加一个**==属性prototype==**，这个属性对应一个对象——**原型对象**



如果函数作为普通函数调用，prototype没用任何作用

如果函数作为构造函数调用，所创建的对象都会用一个**==隐含的属性==**，指向该构造函数的原型对象，可以通过==**\__proto__**==来访问

原型对象相当于一个公共的区域，所有同一个类的实例都可以访问这个原型对象（==同一个类的实例包括那个构造函数的prototype就是同一个==）

![1615377430240](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615377430240.png)

![1615377407406](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615377407406.png)





当我们访问一个对象的**==属性或方法==**时，他先会在自身中找，没找到去**==原型对象==**中找，==如下图==

![1615377590493](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615377590493.png)

![1615377606961](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615377606961.png)

![1615377626985](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615377626985.png)



上一节中的例子可以修改为下面：

![1615377819434](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615377819434.png)



==我们可以将公共的内容，添加到原型对象中==这样也不会影响到全局作用域	





**检查原型中是否有某个属性：**

​	==**用in检查**==：**对象中没有，原型中有**，也会返回true

![1615378170278](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615378170278.png)

​	用**==hasOwnProperty()方法==**来检查对象中有没有该属性：**对象本身**中有才会返回true，只有原型中有返回false

![1615378332582](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615378332582.png)



















hasOwnProperty()方法没有放在对象的原型中，而是放在==**这个对象的原型对象的 原型**== 中

![1615378487380](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615378487380.png)

![1615378547142](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615378547142.png)



**原型对象也是对象，所以它也有原型**

**使用一个对象的属性或方法时，会现在自身中寻找**

**如果没有则去原型对象中寻找，如果原型对象中没有**

**则去原型的原型中寻找**

==没有原型的原型的原型==

如下图：

![1615378797512](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615378797512.png)





### tostring

当我们直接在页面中打印一个对象时，实际上是输出的对象的 ==tostring()方法的返回值==，他保存在**原型的原型**中



![1615379199156](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615379199156.png)



如果我们希望在输出对象时不输出[ object object],可以修改原型的原型的toString()方法



![1615379890093](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615379890093.png)

![1615379917336](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615379917336.png)



### 垃圾回收

程序运行过程中会产生垃圾

垃圾积攒过多，会导致程序运行的速度过慢，

当一个对象没有任何的变量或属性对它进行引用，此时我们将永远无法操作该对象

这种对象就是一个**垃圾**，这种对象过多会占用大量的内存空间，导致程序运行变慢



![1615381488308](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615381488308.png)

当一个对象如：obj=null，代表上图对象名与分配的堆内存空间断开连接





在JS中拥有自动的拉圾回收机制，会自动将这些垃极对象从内存中销毁，我们不需要也不能进行垃圾回收的操作

==当我们不再需要对一个对象进行操作后，可以用**obj=null**，标明此对象没用了，浏览器自动会清理==



### 数组

创建一个数组，数组都用数字索引来替代普通对象的属性值，

![1615540044533](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615540044533.png)

数组中的值可以是任意的数据类型，也可以是对象、数组（二维数组、三位数组.....）

![1615542684613](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615542684613.png)

**length属性**

![1615540188669](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615540188669.png)

![1615383692262](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615383692262.png)



**数组的创建**

**<font color='orange'>①</font>**创建数组对象

![1615540044533](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615540044533.png)

创建时可以指定元素

![1615541224829](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615541224829.png)

**<font color='orange'>②</font>**使用字面量来创建数组

![1615540913712](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615540913712.png)

创建时也可以指定元素

![1615541144570](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615541144570.png)



==二者均可创建时指定元素，但是区别如下：==

![1615542559109](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615542559109.png)





### 数组的方法

#### push方法

![1615542980551](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615542980551.png)

#### pop方法

![1615543065958](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615543065958.png)

#### unshift方法

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615543116730.png" alt="1615543116730" style="zoom:80%;" />

#### shift方法

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615543160108.png" alt="1615543160108" style="zoom:80%;" />

#### foreach方法

一般是用for来遍历数组，js提供一个**方法**来**遍历数组**：**foreach**

foreach只支持==IE8==以上的浏览器

foreach需要一个函数作为参数

像这种函数，由我们创建但是不由我们调用的，我们称为==**回调函数**==

数组中有几个元素**函数就会执行几次**，每次执行时，浏览器会将遍历到的元素**以实参的形式传递进来**，我们可以来定义形参，来读取这些内容



![1615547003505](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615547003505.png)

浏览器会在回调函数中传递==三个参数==：

​	第一个参数，就是当前正在遍历的**元素**

​	第二个参数，就是当前正在遍历的元素的**素引**

​	第三个参数，就是正在遍历的**数组**



![1615547511032](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615547511032.png)

![1615547537970](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615547537970.png)

![1615547571763](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615547571763.png)





#### slice方法

可以用来从数组提取指定元素，**<font color='orange'>该方法不会改变元素数组</font>**，而是将截取到的元素封装到一个**新数组中返回**

​	两个参数：

​	1,截取开始的位置的素引，==包含开始索引==

​	2.截取结束的位置的索引，==不包含结束索引==，第二个可以省略不写，此时会截取从开始素引往后的所有元素

​	素引可以传递一个负值，如果传递一个负值，则从后往前计算

![1615547978323](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615547978323.png)

![1615547962539](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615547962539.png)



#### splice方法

可以用于删除数组中的指定元素

使用splice（）**==会影响到原数组==**，**<font color='orange'>会将指定元素从原数组中删除</font>**，并将**被删除的元素**作为**返回值**返回

参数：

​	第一个，表示开始位置的索引

​	第二个，表示删除的数量

​	第三个及以后，可以传递一些新的元素，这些元素将会自动插入到==开始位置索引==（即**==第一个参数==**）前边（**==可以利用此特点往指定位置添加元素==**）

![1615548171657](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615548171657.png)

![1615548424627](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615548424627.png)





#### concat方法

**==可以连接两个或多个数组，也可以直接输入元素进行连接==**，并将**新的数组返回**，该方法**不会对原数组产生影响**



![1615548828321](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615548828321.png)

![1615548963525](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615548963525.png)



#### join方法

该方法可以**==将数组转换为一个字符串==**

该方法不会对原数组产生影响，而是将**转换后的字符串作为结果返回**

在join（）中可以指定一个字符串作为参数，这个字符串将会成为数组中元素的**==连接符==**，如果不指定连接符，则**==默认用逗号==**

![1615549042390](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615549042390.png)

![1615549155382](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615549155382.png)



#### revorse方法

该方法用来反转数组(前边的去后边，后边的去前边)

该方法==会直接修改原数组==





#### sort方法

可以用来对数组中的元素进行排序

也会==影响原数组==，默认会按照Unlcode编码进行排序

对**数字**进行编排时，按照Unlcode编码可能会得到错误的结果

![1615549430074](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615549430074.png)



我们可以自己指定排序的结果，在sort()添加一个**回调函数**，来指定排序规则

回调函数中需要定义==两个形参==，如图

使用哪个元素调用不确定，但是肯定的是在**==数组中a一定在b前边==**

浏览器会根据回调函数的返回值来定元素的顺序：

​	如果**返回一个大于0的值**，则元素会**交换位置**

​	如果返回一个**小于0的值**，则元素**位置不变**

​	如果返回一个0,则认为两个元素相等，也不交换位置

![1615549953475](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615549953475.png)



==改进：==

如果需要升序排列，则返回a-b

如果需要降序排列，则返回b-a

![1615550333468](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615550333468.png)





#### indexOf() 方法

indexOf() 方法可返回某个指定的字符串值在字符串中首次出现的位置。**<font color='red'>没有就返回-1</font>**

**==语法==**：**==stringObject.indexOf(需要检索的字符串的值,起始位置)==**









### 函数的方法

call和apply都是**函数对象**的方法，需要通过函数对象来调用（==函数对象是函数名，不能在函数后面加括号==）

当对函数调用call（）和 apply（）都会调用**函数执行**

在调用call()和 apply()可以将一个**对象**指定为**第一个参数**，此时这个对象将会成为函数执行时的==this==





如图，正常调用函数时，函数内的this都会指定为**Window**，但是将某个对象作为参数后，**this就变成了这个对象**。==用这种方法可以修改函数内this的指向==

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615599250042.png" alt="1615599250042" style="zoom:80%;" />

![1615599262261](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615599262261.png)

例子2：

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615599930918.png" alt="1615599930918" style="zoom:80%;" />

![1615599956935](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615599956935.png)





==apply和call不同点是==：

二者可以在对象的这个参数后面再加上**函数需要的实参**，==call将参数直接放到对象之后，apply需要将实参封装到一个数组汇总统一传递==

如图：

![1615600429898](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615600429898.png)

![1615600439440](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615600439440.png)







### arguments

在调用函数时，浏览器每次都会传递进两个==隐含的参==数：

1.函数的上下文对象this

2.封装实参的对象 arguments



**arguments**是一个类数组对象，它也可以通过索引来操作数据，也可以获取长度,在调用函数时，==我们所传的实参都会在 arguments中保存==

arguments.length可以用来获取实参的长度

![1615600981305](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615600981305.png)



根据arguments特性，即使不定义形参我们也可以通过arguments来使用实参

![1615601110146](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615601110146.png)



arguements里边有一个属性叫做**==callee==**

这个属性对应一个函数对象，**就是当前正在指向的函数的对象的内容**

![1615601243921](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615601243921.png)





### Date对象

使用Date对象来表示一个时间



**创建一个默认的时间对象**

如果直接使用**==构造函数==**创建一个Date对象，则会封装为当前代码执行的时间

![1615601319929](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615601319929.png)



**创建一个指定的时间对象**

需要在构造函数中传递一个表示时间的字符串作为参数

日期的格式：月份/日/年 时:分:秒

![1615601479783](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615601479783.png)







#### Date的一些方法

getDate获取当前日期是当月的第几日

![1615601633086](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615601633086.png)

getDay获取当前日期是周几，返回0-6，周日-周六

![1615601794988](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615601794988.png)

getMonth获取当前的月份，返回0-11，代表1-12月

getFullYear获取当前日期对象的年份



**==getTime==**获取当前**时间对象**的==时间戳==：指的是从格林威治标准时间的1970年1月1日，0时0分0秒到当前日期所花费的**毫秒**数

计算机在底层保存的都是时间戳



**==now()方法==** 获取当前的时间戳

利用时间戳来测试代码的执行的性能（之前用过一个**==console.time 和 console.timeEnd==**来计算）





### Math

Math和其他的对象不同，==它不是一个构造函数==

它属于一个工具类，==不用创建对象==，直接用就行了 它里边封装了数学运算相关的属性（一些常量）和方法



例子：

![1615602850527](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615602850527.png)

![1615602906989](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615602906989.png)



![1615603001240](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615603001240.png)

![1615603043874](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615603043874.png)

![1615603087307](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615603087307.png)



### 包装类

 ![1615605531145](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615605531145.png)



例子：

![1615605570111](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615605570111.png)

![1615605603675](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615605603675.png)

![1615605624669](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615605624669.png)

**但是在开发中我们绝对不会像上面这么用**（就比如创建一个bool对象，他类型为object，用它来做判断，首先进行类型转换，object转换为布尔值true，就没有意义了）



==我们平时再用.tostring()等等这些方法时，直接用在基本数据类型上面，但是基本数据类型本来不能调用方法和属性==

对一些基本数据类型的值去调用属性和方法时，浏览器会临时使用**==包装类==**将其转换为**对象**，然后在调用对象的属性和方法。调用完以后，自动将其转换为**基本数据类型**（所以像str.hello="你好"   这种向字符串中添加属性的操作==并不会报错==，但是没有作用）



### string对象的方法

字符串在**底层**是以**==字符数组==**的形式保存的

![1615607092692](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615607092692.png)



也能使用数组的一些方法，也能使用索引

![1615607130097](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615607130097.png)





#### **charAt()方法**

返回字符串指定位置字符，当然也可以直接用中括号

![1615612944700](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615612944700.png)

![1615612959883](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615612959883.png)

#### **charCodeAt()方法**

返回字符串指定位置字符的Unicode编码

![1615613059010](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615613059010.png)

#### **fromCharCode()方法**

String.fromCharCode（编码）根据Unicode字符编码去获取字符

**==这的String是内建对象==**

![1615613252814](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615613252814.png)



#### **concat()**

用来连接两个或者多个字符串，作用和+号一样

![1615613610576](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615613610576.png)



#### **indexOf()方法**

该方法可以检素一个字符串中是否含有指定内容

如果字符串中含有该内容，则会返回其==第一次==出现的索引

如果没有找到指定的内容，则返回==-1==

可以指定==第二个参数==，指定==开始查找的位置==

![1615613677433](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615613677433.png)

![1615613853096](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615613853096.png)



#### **lastIndexOf()方法**

该方法的用法和 indexOf（）一样，也能指定查找位置

不同的是indexOf是从前往后找，

而lastIndexOf是从后往前找

![1615613952377](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615613952377.png)



#### **slice()方法**

可以从字符串中截取指定的内容，不会影响原字符串，而是将截取到内容返回(数组的方法中也有同样的方法)

参数：

​	第一个，开始位置的索引（==包括开始位置==）

​	第二个，结束位置的索引（==不包括结東位置==）省略第二个参数，则表明会截取后面所有的

传递负数的话标明从后面开始计算

![1615614099645](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615614099645.png)



#### **substring()方法**

基本上跟slice一样，不同的是这个方法==不能接受负值==作为参数，如果传遇了一个负值，则默认使用0

而且他还自动调整参数的位置，==如果第二个参数小于第一个，则自动交换==





#### **substr()方法**

![1615614449042](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615614449042.png)







#### **split()方法**

可以将一个字符串拆分成一个数组

 需要一个字符串作为参数，将会**==根据该字符串去拆分数组==**

![1615614603785](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615614603785.png)





### 正则表达式简介



创建正则表达式对象

**构造函数创建语法：**

![1615614949066](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615614949066.png)

**字面量创建语法：**

![1615615295063](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615615295063.png)

​	以下两种写法等同

![1615615325398](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615615325398.png)

==但是构造函数方法更加灵活，因为参数可以使用变量==

**==两种匹配模式==**：**i**：忽略大小写模式

​			   **g**：全局匹配模式

**==test()方法==**

此方法是**正则表达式对象的方法**

使用这个方法可以用来检查一个字符串是否符合正则表达式的规则，如果符合则返回true，否则返回fase



![1615615138596](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615615138596.png)





#### **支持正则表达式的string对象**



==split()方法==：将字符串拆分成一个数组，可以利用正则表达式

![1615622260929](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615622260929.png)



==search()方法==：搜索字符串中是否有指定内容，可以接受正则表达式作为索引，**返回第一次出现的索引**

 ![1615622430832](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615622430832.png)



==match()方法==：可以根据正则表达式，从一个字符串中将符合条件的内容提取出来 ，**会将匹配到的内容封装到一个数组中返回，即使只查询到一个结果**

**默认情况**下match只会找到**第一个**符合条件的内容然后就会停止检索，可以设置正则表达式为**全局匹配模式**，这样就会**匹配到所有内容**

可以为一个正则表达式设置多个匹配模式，且顺序无所谓

![1615622812543](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615622812543.png)

（i g这两个先后顺序不要求	）

==replace()方法==：可以将字符串中指定内容替换为新的内容，**默认只会替换第一个**，可以设置正则表达式为**全局匹配模式**，匹配到所有内容（单个字符一个个的相匹配）

两个参数：

​		1.被替换的内容，可以接受一个正则表达式作为参数

​		2.新的内容

![1615623177160](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615623177160.png)



### 正则表达式

例子：

![1615626129287](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615626129287.png)



**==[ ]的使用==**

[ ] 是定义匹配的字符范围，单个字符进行匹配

比如[a-zA-Z0-9]表示相应位置的字符要匹配英文字符和数字。

==**^的使用**==

​	**<font color='orange'>^在[]中表示除了，^在[]之外表示以什么什么开头</font>**



==**\  的使用**==

![1615627003202](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615627003202.png)

**字面量创建**正则表达式，使用转义符\ ，直接用就可以了，因为字面量这种方法不带双引号

使用**构造函数**创建正则表达式，使用转义符\ ，==需要用\\\来代替==，因为这种方法有**双引号**，\ 也是字符串中的转义符



#### 非打印字符

非打印字符也可以是正则表达式的组成部分。下表列出了表示非打印字符的转义序列：

| 字符 | 描述                                                         |
| ---- | ------------------------------------------------------------ |
| \cx  | 匹配由x指明的控制字符。例如， \cM 匹配一个 Control-M 或回车符。x 的值必须为 A-Z 或 a-z 之一。否则，将 c 视为一个原义的 'c' 字符。 |
| \f   | 匹配一个换页符。等价于 \x0c 和 \cL。                         |
| \n   | 匹配一个换行符。等价于 \x0a 和 \cJ。                         |
| \r   | 匹配一个回车符。等价于 \x0d 和 \cM。                         |
| \s   | ==匹配任何空白字符，包括空格、制表符、换页符等等==。等价于 [ \f\n\r\t\v]。注意 Unicode 正则表达式会匹配全角空格符。 |
| \S   | ==匹配任何非空白字符==。等价于 \[^ \f\n\r\t\v]。             |
| \t   | 匹配一个制表符。等价于 \x09 和 \cI。                         |
| \v   | 匹配一个垂直制表符。等价于 \x0b 和 \cK。                     |

**==\s的例子==**：

去掉所有的空格：

![1615629217512](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615629217512.png)

去掉开头结尾的空格：

![1615629407062](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615629407062.png)

==|代表或，只用|就可能只去掉开头的空格，后面加上g，就全局模式匹配，前后空格都去掉了==



#### 特殊字符

所谓特殊字符，就是一些有特殊含义的字符，如上面说的 runoo*b 中的 *，简单的说就是表示任何字符串的意思。如果要查找字符串中的 * 符号，则需要对 * 进行转义，即在其前加一个 \: runo\*ob 匹配 runo*ob。

许多元字符要求在试图匹配它们时特别对待。若要匹配这些特殊字符，必须首先使字符"转义"，即，将反斜杠字符\ 放在它们前面。下表列出了正则表达式中的特殊字符：

| 特别字符 | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| $        | 匹配输入字符串的==结尾位置==。如果设置了 RegExp 对象的 Multiline 属性，则 $ 也匹配 '\n' 或 '\r'。要匹配 $ 字符本身，请使用 \\$。 |
| ( )      | 标记一个==子表达式==的开始和结束位置。子表达式可以获取供以后使用。要匹配这些字符，请使用 \( 和 \)。 |
| *        | 匹配前面的子表达式零次或多次。要匹配 * 字符，请使用 \\*。    |
| +        | 匹配前面的子表达式一次或多次。要匹配 + 字符，请使用 \\+。    |
| .        | 匹配==除换行符 \n 之外的任何单字符==。要匹配 . ，请使用 \\. 。 |
| [        | 标记一个中括号表达式的开始。要匹配 [，请使用 \\[。           |
| ?        | 匹配前面的子表达式零次或一次，或指明一个非贪婪限定符。要匹配 ? 字符，请使用 \?。 |
| \        | 将下一个字符标记为或特殊字符、或原义字符、或向后引用、或八进制转义符。例如， 'n' 匹配字符 'n'。'\n' 匹配换行符。序列 '\\' 匹配 "\"，而 '\(' 则匹配 "("。==转义符== |
| ^        | 匹配输入字符串的==开始位置==，除非在方括号表达式中使用，当该符号在方括号表达式中使用时，表示不接受该方括号表达式中的字符集合。要匹配 ^ 字符本身，请使用 \^。 |
| {        | 标记限定符表达式的开始。要匹配 {，请使用 \\{。               |
| \|       | 指明两项之间的一个选择。要匹配 \|，请使用 \\|。              |

------

^a$符合的条件只有一个a（a它自己即使开头又是结尾）

![1615625599833](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615625599833.png)



#### 限定符

限定符用来指定正则表达式的一个给定组件必须要出现多少次才能满足匹配。有 * 或 + 或 ? 或 {n} 或 {n,} 或 {n,m} 共6种。

正则表达式的限定符有：

| 字符  | 描述                                                         |
| ----- | ------------------------------------------------------------ |
| *     | 匹配前面的子表达式==零次或多次==。例如，zo* 能匹配 "z" 以及 "zoo"。* 等价于{0,}。 |
| +     | 匹配前面的子表达式==一次或多次==。例如，'zo+' 能匹配 "zo" 以及 "zoo"，但不能匹配 "z"。+ 等价于 {1,}。 |
| ?     | 匹配前面的子表达式==零次或一次==。例如，"do(es)?" 可以匹配 "do" 、 "does" 中的 "does" 、 "doxy" 中的 "do" 。? 等价于 {0,1}。 |
| {n}   | n 是一个非负整数。==匹配确定的 n 次==。例如，'o{2}' 不能匹配 "Bob" 中的 'o'，但是能匹配 "food" 中的两个 o。 |
| {n,}  | n 是一个非负整数。==至少匹配n 次==。例如，'o{2,}' 不能匹配 "Bob" 中的 'o'，但能匹配 "foooood" 中的所有 o。'o{1,}' 等价于 'o+'。'o{0,}' 则等价于 'o*'。 |
| {n,m} | m 和 n 均为非负整数，其中n <= m。==最少匹配 n 次且最多匹配 m 次==。例如，"o{1,3}" 将匹配 "fooooood" 中的前三个 o。'o{0,1}' 等价于 'o?'。请注意在逗号和两个数之间==不能有空格==。 |
| \w    | ==任意字母、数字、_（下划线）==，相当于[A-z0-9\_]            |
| \W    | ==除了任意字母、数字、_（下划线）==,相当于\[^A-z0-9\_]       |
| \d    | ==任意数字==[0-9]                                            |
| \D    | ==除了数字==\[^0-9]                                          |

#### 定位符

定位符使您能够将正则表达式固定到行首或行尾。它们还使您能够创建这样的正则表达式，这些正则表达式出现在一个单词内、在一个单词的开头或者一个单词的结尾。

定位符用来描述字符串或单词的边界，^ 和 $ 分别指字符串的开始与结束，\b 描述单词的前或后边界，\B 表示非单词边界。

正则表达式的定位符有：

| 字符 | 描述                                                         |
| ---- | ------------------------------------------------------------ |
| ^    | 匹配输入==字符串开始的位置==。如果设置了 RegExp 对象的 Multiline 属性，^ 还会与 \n 或 \r 之后的位置匹配。 |
| $    | 匹配输入==字符串结尾的位置==。如果设置了 RegExp 对象的 Multiline 属性，$ 还会与 \n 或 \r 之前的位置匹配。 |
| \b   | 匹配一个==单词边界==，即匹配一个单词，单词前或者后不能有别的字符，必须是空格。 |
| \B   | ==非单词边界==匹配，单词前面或者后面不能是空格，在单词的前或者后面用，相应位置不能是空格，必须连起来 |



![1615628620364](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615628620364.png)



**注意**：不能将限定符与定位符一起使用。由于在紧靠换行或者单词边界的前面或后面不能有一个以上位置，因此不允许诸如 ^*之类的表达式。



例子：

![1615633682215](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615633682215.png)

![1615633701080](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615633701080.png)

**==（此例有错误，A-z包括下划线）==**

​	

### 宿主对象

**==对象一共分三种：内建对象、宿主对象、自定义对象==**

宿主对象：由浏览器，或者说有运行环境给我们提供的对象

#### DOM（文档对象模型）

![1615634518377](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615634518377.png)



![1615635568719](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615635568719.png)



##### **==节点==**

![1615635757453](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615635757453.png)

节点：Node——构成html文档最基本的单元

常用的节点分为==四类==：

​	**文档节点**：整个html文档

​	**元素节点**：HTML文档中的标签

​	**属性节点**：元素的属性

​	**文本节点**：html标签中的文本内容

![1615635907656](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615635907656.png)



**==节点的属性==**

每一个节点都有**nodeName、nodeType、nodeValue**三个属性 

![1615635998109](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615635998109.png)

##### **==文档节点对象==**

浏览器已经为我们提供==文档节点对象==这个对象是 window的属性——==**document**==

可以在页面中直接使用，文档节点代表的是整个网页

**例子**：document对象的getElementById()方法来寻找元素节点（文档节点->元素节点）

![1615636648164](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615636648164.png)

**innerHTML属性**，btn.innerHTML代表btn元素（也就是button标签）的内容

![1615637021604](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615637021604.png)



##### 事件的简介

![1615637200972](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615637200972.png)

我们可以在**==事件对应的属性==**中设置一些了js代码，

这样当事件被触发时，这些代码将会执行





**js书写位置：**

![1615637471041](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615637471041.png)

可以直接在其他的标签中当做属性写，**但是这种称为结构与行为耦合，不方便维护不推荐使用**

==<font color='cornflowerblue'>应该写在body 标签中，并且靠下面的位置</font>==

浏览器在加载一个页面时，是按照**自上向下**的顺序加载的，读取到一行就运行一行，==如果将 script标签写到页面的上边，在代码执行时，页面还没有加载==

如果非要写在 body标签前面，则需要用到onload事件，**window.onload**代表等到页面加载完成之后在执行

![1615720132626](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615720132626.png)

然后**把代码都写到这个事件中去**，**确保相应的js代码执行时，所有的DOM对象都应经加载完毕**

![1615719883050](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615719883050.png)

**<font color='orange'>但是这种方法属于先加载后执行，效率不高</font>**，但用的比较常见











**事件绑定的基本操作：**

因此，将js代码写在script标签中，然后通过document.getElementById()方法进行对象的获取，然后在进行事件的绑定（已经定义好了很多事件）

==事件相当于属性，属性等于的是一个函数，函数当事件被触发的时候执行。如下图==

![1615719060186](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615719060186.png)







##### DOM查询

######  获取元素节点

document下获取**元素节点**对象的方法

![1615720463681](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615720463681.png)

**getElementEyId()**

通过==id属性==获取==一个==元素节点对象

**getElementsByTagName()**

通过==标签名==获取==一组==元素节点对象（比如div标签，通过div来获取**所有的**div标签）

**getElementsByName()**

通过==name属性==获取==一组==元素节点对象



**==（id和name的区别：id唯一，只能具体某个标签使用，而name则可以重复多个标签使用，但都属于标签的属性）==**

**innerHTML属性**：通过这个属性可以获取元素内部的html代码





==**以上三个方法的实践：**==

**通过id属性来获取某个标签**

![1615721224548](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615721224548.png)

**通过标签名来获取所有指定标签：**

![1615721417823](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615721417823.png)

**通过name属性来获取所有指定的标签：**

![1615722476800](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615722476800.png)

![1615722417025](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615722417025.png)

例子：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<style type="text/css">
			*{
				margin:0;
				padding:0;
			}
			#outer{
				width: 500px;
				margin: 50px auto;
				padding: 10px;
				background-color: yellowgreen;
				text-align: center;
			} 
		</style>
		
		<script type="text/javascript">
			window.onload =function(){
				// 点击按钮切换图片
				var prev =document.getElementById("prev");
				var next =document.getElementById("next");
				var imgArr=["1.jpg","2.jpg","3.jpg","4.jpg"];
				var img=document.getElementsByTagName("img")[0];
				var index = 0;
				prev.onclick = function(){
					index--;
					if(index<0){
						index = 0;
						}
					img.src=imgArr[index];
					
				};
				next.onclick = function(){
					
					 index++;
					 if(index>imgArr.length-1){
						 index =imgArr.length-1;
						 }
					 img.src=imgArr[index];
				};
			};
		</script>
		
	</head>	
	<body>
		<div id="outer">
			<img src="1.jpg" alt="haha"/>
			<button id="prev">上一张</button>
			<button id="next">下一张</button>			
		</div>
		
		
		<script type="text/javascript" >
		
		</script> 
	</body>
</html>

```

###### ==ps:一点小问题==

某个例子：在for循环中绑定一个单击响应函数，这是for循环中的**i**使用就出现了问题



![1615886696056](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615886696056.png)

for循环在页面加载结束一开始就执行完了，所有的响应函数也绑定完了，之后再点击超链接，再次执行==allA[i]==，这里面的i仍然是变量，循环时并没有被具体数字替换，这时候==i已经是循环结束后的那个值==，且一直是那个值

用**==this==**代替allA[i]就没有问题了





###### 获取元素节点的子节点

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615726805938.png" alt="1615726805938" style="zoom:80%;" />



getElementsByTagName()方法在**文档对象**（document）和**元素对象**（标签）都有



**通过标签名来获取当前标签后代节点（后代标签）**

getElementsByTagName()方法

![1615769112408](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615769112408.png)



**返回当前节点的所有子节点**

childNodes属性

![1615769478981](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615769478981.png)

所有子节点也包括文本节点，一处标签间的空白也会作为一个文本节点（但是在==IE8==中不会将空白当成文本节点）



**返回当前节点的所有子元素**

children属性

![1615769851459](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615769851459.png)

此时返回的内容中就不包括了空白文本节点

==只会返回标签==



 **返回当前节点的第一个子节点**

firstChild

![1615770221378](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615770221378.png)

返回节点也包括文本节点



**返回当前节点的第一个子元素**

firstElementChild

![1615770288572](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615770288572.png)

不包括空白文本等等文本节点（但是不支持==IE8==及以下的浏览器）





###### 获取元素节点的父亲节点和兄弟节点

*PS: 前后这几节教程，每次都要获取事件，绑定参数，为方便，直接定义一个函数来简化步骤*

![1615770843215](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615770843215.png)

==innerText属性==，该属性可以获取元素内部的文本内容，他和innerHTML类似，不同的是他会自动地将HTML标签去除，只保留文本内容.

![1615772069391](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615772069391.png)



**返回当前节点的父节点**

parentNode属性

![1615771908787](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615771908787.png)

某个元素的父节点是唯一的，就不可能是空白之类的文本节点了

 

**返回当前节点的前一个兄弟节点**

previousSibling属性

![1615772203127](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615772203127.png)

也会获取空白、换行之类的文本节点



**返回当前节点的前一个兄弟元素**

previousElementSibing

![1615772330060](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615772330060.png)

不会返回文本节点，返回的只能是元素（==IE8==及以下版本不支持）



**读取当前节点的value属性值**

就相当于某个对象的属性，文本框里面写的什么独到的就是什么

![1615772526700](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615772526700.png)



==nodeValue属性==

获取某个节点的文本内容，大部分情况下做到的效果跟innerText一样，**但是比innerText麻烦**

![1615772837363](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615772837363.png)









##### DOM查询的剩余方法

**<font color='orange'>①</font>**

要查询body标签的话，可以用getElementsByTagName()方法

![1615876686126](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615876686126.png)

document中也有一个==属性body==，专门用来引用body标签的，==返回的就不是类数组了，返回的就直接是body标签==

![1615876780511](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615876780511.png)



**<font color='orange'>②</font>**

document中有一个==属性documentElement==，用来获取\<html>根标签

![1615876904221](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615876904221.png)



**<font color='orange'>③</font>**

==document.all==代表页面中所有的元素（即所有的标签）

![1615877055008](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615877055008.png)





**<font color='orange'>④</font>**

==document.getElementsByTagName("*");==这样代表的也是页面中的所有元素，作用跟document.all一样

![1615877195306](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615877195306.png)

**<font color='orange'>⑤</font>**

==document.getElementsByClassName()==方法用来根据class属性值来获取**一组**元素节点对象，==但是IE8及以下不支持==

**<font color='orange'>⑥</font>**

==document. queryselector()==

需要一个**css选择器**的字符串作为参数，可以根据一个CSS选择器来查询一个元素节点对象， 使用该方法总会返回==唯一的一个元素==，如果满足条件的元素有多个，==那么它只会返回第一个==

**虽然工E8中没有 getElmentsByClassName（）但是可以使用 querySelector()代替**

![1615878103783](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615878103783.png)

<font color='orange'>**⑦**</font>

==document. querySelectorAll()==

该方法和 querySelector()用法类似，不同的是它会将符合条件的元素封装到==一个数组==中返回

即使符合条件的元素只有一个，它也会返回数组

![1615878116999](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615878116999.png)

**ps：**<font color='orange'>例子中的.box1查找的是class名</font>

​	<font color='orange'>#box2查找的是id名</font>



##### DOM增删改

==创建元素节点（即创建标签）==

document.createElement()方法

![1615880519149](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615880519149.png)



==创建文本节点==

document.createTextNode()方法

![1615880579917](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615880579917.png)



==把子节点添加到指定节点中==

父节点.appendChild()方法

![1615880648237](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615880648237.png)



==在指定的子节点前插入新的子节点==

父节点.insertBefore(新节点,旧节点)

![1615880889355](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615880889355.png)



==使用指定节点替换已有的节点==

父节点.replaceChild(新节点,旧节点)

![1615881073530](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615881073530.png)



==删除指定节点的子节点==

父节点.removeChild(子节点)

![1615881161946](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615881161946.png)

但有时候不知道父节点是谁，所以==常用操作==：

**<font color='orange'>子节点.parentNode.removeChild(子节点)</font>**

![1615881390387](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615881390387.png)





==读取或设置元素内的HTML代码==

节点.innerHTML 

![1615881646449](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615881646449.png)

用innerHTML也能实现**指定节点添加到已有节点**、**把子节点添加到指定节点中去**等操作

![1615881877504](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615881877504.png)

但这种方法动静太大，**修改了父节点所有的子节点，如果之前的子节点中绑定了事件，修改后就没了**

一般使用折中的方式：

==按原来的方法，有以下操作：==

​	创建一个元素节点

​	创建一个文本节点

​	将文本节点添加到创建的元素节点中去

​	将这个创建的元素节点再添加到指定的父节点中去

==折中后的操作如下：==

![1615882082189](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615882082189.png)





##### 使用DOM操作css

###### 修改或者读取元素的内联样式

语法：

​	==元素.style.样式名=样式值==

注意：如果css的样式名中含有"-"（减号），这样写是不合法的，需要将样式名修改为**==驼峰命名法==**

**如:background-color改为backgroundColor**

![1615890827805](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615890827805.png)

![1615891218560](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615891218560.png)



我们通过style属性设置的样式都是**内联样式（直接在相应标签中修改的属性）**，==修改和读取都是内联样式，无法读取修改样式表中的样式。==

他有较高的优先级，所以通过js修改的样式往往会立即显示

![1615891087385](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615891087385.png)

但是如果在样式中写了**! important**，则此时样式会有最高的优先级，

即使通过]S也不能覆盖该样式，此时将会**导致]S修改样式失效**，所以尽量不要为样式添加!Important



###### 读取元素当前显示的样式

==**currentStyle**==

<font color='orange'>**缺点是只有IE支持**</font>

语法：

元素.currentStyle.样式名

==**内联表或者样式表 **==中都可以读取，谁生效获取谁

如果当前元素没有设置样式值，则获取他的默认值	

![1615892557815](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615892557815.png)





==**getComputerdStyle()方法**==

**<font color='orange'>IE8以上支持</font>**

getComputedStyle()这个**方法**来获取元素当前的样式，效果和currentStyle一样

但**<font color='orange'>①</font>**返回的样式参数的格式不太一样，**<font color='orange'>②</font>**并且获取的样式如果没有设置，不会获取默认值，而是真实的值，比如，没有设置 width,它不会获取到auto,而是一个长度

​		==这个方法是 **window**的方法，可以直接使用==

需要两个参数:

​	第一个要获取样式的==元素==

​	第二个可以传递一个**伪元素**，一般都传==nu11==

该方法会返回一个**对象**，对象中封装了当前元素对应的样式,读取需要像读取属性一样读取

![1615892300836](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615892300836.png)



==**currentStyle和getComputerStyle()读取到的样式都只是可读的，只有style属性才能修改样式**==



为了能在所有的浏览器上面运行，可以自己写一个函数

定义一个函数，用来获取指定元素的当前的样式

**参数**

obj：要获取样式的元素

name：要获取的样式名

![1615896023878](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615896023878.png)

**ps:**

**<font color='orange'>①</font>**name的时使用，不能在函数中直接用**.name**，因为.name就直接在样式里面找名字为name的样式了，根本不会替换成实参来使用，要使用**==[name]==**

**<font color='orange'>②</font>**if当中必须写成==window.getComputerStyle==，如果只写getComputerStyle的话，在函数作用域和全局作用域中寻找getComputerStyle，没找到就直接报错了，写成window的方法的形式，返回的是未定义，判断为false



###### 其他样式相关属性

==**clientWidth属性**==

==**clientHeight属性**==

这两个属性可以获取元素的==可见宽度和高度==

这些属性都是不带px的，返回都是一个==数字==，可以直接进行计算

会获取元素宽度和高度，**包括内容区和内边距，==不包括边框border，有滚动条的还要减去滚动条==**

这些属性都是只读的



==**offsetWidth属性**==

==**offsetHeigh属性**==

获取元素的整个宽度和高度，包括内容区和内边距，==包括边框border==





**==offsetParent属性==**

可以用来获取当前元素的定位父元素

会获取到离当前元素最近的开启了定位的祖先元素

如果所有的祖先元素都没有开启定位，则返回body

​	PS:position值默认static，relative相对定位，absolute绝对定位,fixed固定定位,sticky粘滞定位。position值不是static就开启了定位



**==offsetleft==**

当前元素相对于其定位父元素（即offsetParent）的水平偏移量

==**offsettop**==

当前元素相对于其定位父元素的垂直偏移量



==**scrollWidth**==

==**scrollHeight**==

可以获取元素整个滚动区域的宽度和高度

有的子元素大小超过了父元素，overflow设置的为auto，会出现滚动条。



![1615898575521](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615898575521.png)

如果用clientWidth属性、clientHeight属性这两个属性读取**==父元素==**的长度和宽度的话，只会读取可见宽度，如果用scrollWidth、scrollHeight这两个属性的话，则会返回滚动宽度，**==返回子元素的实际占的大小==**



**==scrollLeft==**

可以获取水平滚动条滚动的距离

**==scrollTop==**

可以获取垂直滚动条滚动的距离



![1615898906489](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615898906489.png)





##### 事件对象

事件对象

当事件的响应函数**==被触发==**时，测览器每次都会将一个**==事件对象==**作为实参**==传递进响应函数==**，平时写响应函数，都是不写参数的，传进去的参数就可以作为事件对象

在事件对象中封装了==当前事件相关的一切信息==，比如：鼠标的坐标、键盘哪个按键被按下、鼠标滚轮滚动的方向。。。等等



![1615899795665](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615899795665.png)







事件对象的==**cllentX属性**==可以获取鼠标指针的水平坐标

事件对象的==**cllentY属性**==可以获取鼠标指针的垂直坐标

![1615900077576](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615900077576.png)

在IE8中，响应函数被触发时，浏览器不会传事件对象

在==IE8及以下==的浏览器中，是将事件对象作为 window对象的属性保存的

用==window.event.clientX==便可以读取

![1615900428552](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615900428552.png)



==**用下面这两种方法可以解决不同浏览器事件对象的兼容性问题**==

![1615900616327](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615900616327.png)





##### 事件的冒泡

事件的冒泡(Bubble)

所谓的冒泡指的就是事件的向上传导，当后代元素上的事件被触发时，其祖先元素的**相同事件**也会被触发

大部分情况冒泡都是有用的，也是自然而然可以理解的

如果不希望发生事件冒泡，可以用**事件对象**来取消冒泡

取消冒泡：**==cancelBubble属性==**

语法：

​	**==事件.cancelBubble=true==**

![1615979925938](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615979925938.png)



##### 事件的委派

事件的委派

指将事件统一定给元素的**共同的祖先元素**，这样当后代元素上的事件触发时，会一直冒泡到祖先元素

**从而通过祖先元素的响应函数来处理事件**。

事件委派是利用了冒泡，**==通过委派可以减少事件绑定的次数，提高程序的性能==**





**==事件的target属性==**，表示触发事件所在的那个**元素对象**，并不是响应函数绑定的对象，比如响应事件绑定在ul中，ul中还有li等标签，响应事件是在li中触发的，就会返回li

语法：事件.target

![1615981438316](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615981438316.png)



##### 事件的绑定



一个事件绑定多个响应函数

**==addEventListener()方法。==**通过这个方法可以同时为一个元素的相同事同时定多个响应函数，但是**==IE8==**及以下浏览器不支持，**<font color='orange'>此方法中this指向的是元素</font>**

这样当事件被触发时，响应函数将会==按照函数的绑定顺序执行==

==**三个参数**==

1.事件的字符串，**==不要on==**

2.回调函数，**当事件触发时该函数会被调用**

3.是否在捕获阶段触发事件，需要一个布尔值，**一般都传 False**

例子：

![1615984472976](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615984472976.png)



attachEvent()方法  

在**==IE5-10==**中可以使用 attachEvent（）来定多个事件

不同的是，**==他是后绑定先执行==**，和addEventListener()方法顺序相反，**<font color='orange'>且此方法中this指向的是window</font>**

**==两个参数：==**

1.事件的字符串，**==要加上on==**

2.回调函数

![1615984708848](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615984708848.png)



上面这两中方法，为了实现兼容，自定义一个**==bind函数==**

![1615985503444](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615985503444.png)

**虽然能用了，但是上面所说的两种方法的差异还是存在**

 	

**==改进：==**消除this的差异，改成都指向元素

![1615986591261](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615986591261.png)

attachEvent()方法中，**<font color='orange'>this返回的是window，说明它底层采用的是函数型调用</font>**，函数有个方法是：函数.call(obj)，来修改函数的this指向。

==直接添加callback.call(obj)不行。因为call特点是函数就直接将相应的函数运行，例子中不允许这么做==







##### 事件的传播

![1615990822091](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615990822091.png)

![1615990854299](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615990854299.png)

##### 滚轮事件

**==onmousewheel==**滚轮事件，此事件在**==火狐==**中不兼容

在火狐中，使用**==DOMMouseScroll==**

**<font color='orange'>但是，火狐中该事件的绑定必须使用addEventListener</font>**

**==ps：更新，现在火狐、谷歌都可以用onwheel，ie用onmousewheel==**



==**事件.wheelDelta**==,鼠标滚动方向，**==火狐==**中不支持

![1616051545827](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616051545827.png)

在火狐中，用**==事件.detail==**获取鼠标滚动事件

![1616051697516](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616051697516.png)



实现兼容

![1616051741721](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616051741721.png)





有时候自定义的div块中定义的鼠标滚动响应事件，浏览器也在页面滚动

**==取消默认行为==**，要**==写在相应的元素中的滚动事件的响应函数中去==**

![1616052046107](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616052046107.png)

使用 addeventlistener()方法绑定响应函数，**==取消默认行为时不能使用 return false==**

此时，可以用事件对象的preventDefault()方法来取消默认行为，但是ie8不支持

例子中的event.preventDefault()&&event.preventDefault()作用是让IE浏览器来判断，ie两个都不能用，就相当于相与为假，执行下面的代码，不会报错，单写一个event.preventDefault()就报错了



##### 键盘事件

**==onkeydown==**键盘按下

​	如果一直按着某个事件不松手，会连续触发

​	当连续触发时，第一次和第二次会有一个小的停顿，之后的会非常快，这是为了**==防止误操作==**

**==onkeyup==**键盘松开

键盘事件一般都绑定给可以==获取焦点==的事件，或者==document==



**==按键事件.keyCode==**获取按键的Unicode编码

![1616052868118](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616052868118.png)

判断哪个键被按下

==**altKey**==

==**ctrlKey**==

==**shiftKey**==

![1616053090575](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616053090575.png)

例子

![1616053285651](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616053285651.png)

在文本框中不允许输入数字：

![1616053440652](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616053440652.png)









#### BOM（浏览器对象模型）



BOM可以使我们通过]S来操作浏览器

BOM对象  调用时**首字母都小写**

**==window==**

代表的是**整个浏览器的窗口**，同时 window也是网页中的**全局对象**

**==navigator==**

代表的当前浏览器的信息，通过该对象可以来**识别不同的浏览器**

**==location==**

代表当前浏览器的地址栏信息，通过 Location可以**获取地址栏信息**，或者**操作浏览器跳转页面**

**==history==**

代表浏览器的**历史记录**，可以通过该对象来操作浏览器的历史记录

由于隐私原因，该对象不能获取到具体的历史记录，只能**操作浏览器向前或向后翻页**

而且该操作只在**当次访回时有效**

**==screen==**

代表用户的屏幕的信息，通过该对象可以获取到用户的**显示器的相关的信息**



这些BOM对象在浏览器中都是作为 **==window对象的属性保存的，==**

**可以通过 window对象来使用**，**也可以直接使用**

![1616065327637](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616065327637.png)





##### navigator

代表的当前浏览器的信息，通过该对象可以来识别不同的浏览器

**由于历史原因， Navigator对象中的大部分属性都已经不能帮助我们识别浏览器了**

一般我们只会使用 **==useragent==**来判断浏览器的信息，

useragent是一个字符串，这个字符串中包含有用来描述浏览器信息的内容，不同的浏览器会有不同的 useragent





![1616066135341](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616066135341.png)

如图所示，如果通过 userAgent不能判断IE11，还可以通过一些浏览器中特有的对象，来判断浏览器的信息

比如： **Activexobiect**是IE中独有的，通过判断**Activexobiect in window**真假来判断是否是IE浏览器（但不能用if(window.ActiveXobject)，因为IE鸡贼的把这个值强行改为false）

**==通过usrAgent的信息来区分浏览器==**：

![1616066567492](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616066567492.png)



##### history  

**==history.length属性==**获取当前访问的链接数量

**==back()方法==**

可以用来回退到上一个页面，作用和测览器的回退按钮一样

**==forward()方法==**

可以跳转下一个页面，作用和浏览器的前进按钮一样

**ps：back和forward这两个是方法，作用到点击事件的响应函数中的话，就会==直接跳转==**



**==go()方法==**，可以用来跳转到指定的页面

它需要一个**整数**作为**参数**：

​	**1**：表示向前跳转一个页面相当于 forward()

​	**2**：表示向前跳转两个页面

​	**-1**：表示向后跳转一个页面

​	**-2**：表示向后跳转两个页面



##### location

如果直接打印location,则可以获取到地址栏的信息（当前页面的完整路径

如果直接将location属性修改为一个完整的路径，或相对路径，**则页面会自动跳转到该路径，放到onclick的响应函数中去，点击就跳转了**。并且会生成相应的历史记录

![1616068985837](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616068985837.png)

==**location. assign()方法**==，作用和location一样，只不过**将地址作为参数传给方法**

![1616069010466](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616069010466.png)



**==location. reload()方法==**

用于重新加载当前页面，作用和刷新按钮一样

如果在方法中传通一个true,作为参数，则会**强制清空缓存刷新页面**

![1616069222143](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616069222143.png)



**==location.replace()方法==**

可以使用一个新的页面替换当前页面，调用完毕也会跳转页面

==不会生成历史记录，不能使用回退按钮==

![1616069319573](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616069319573.png)



#####  window

 很多window方法前面已经讲过了，并且window可以省略

**==setInterval()方法==**

**定时调用**

可以将一个函数，每隔一段时间执行一次

**参数：**

​	1.回调函数，该函数会每隔一段时间被调用一次

​	2.每次调用间隔的时间，单位是**毫秒**

![1616069702338](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616069702338.png)

该方法会返回一个**==返回值==**：Number类型的数据

这个数字用来作为**==定时器的唯一标识==**

将方法赋值给变量就是将**返回值赋值给变量**的过程，**==此时这个定时器仍然开启，响应函数仍然运行==**





**==clearInterval()方法==**

可以用来关闭一个定时器

方法中需要一个定时器的**标识作为参数**，也就是上面说的返回值，  这样将关闭标识对应的定时器

clearInterval()可以接收任意参数，

如果参数是一个有效的定时器的标识，则停止对应的定时器

如果参数是一个**无效的标识，则什么也不做，不会报错**

 例子：

![1616070059796](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616070059796.png)



如果将定时器绑定到一个按钮上，点一下就开启一个定时器，**==点多次就开启多个定时器==**，如果定时器赋值给某一个变量，后来的定时器**==返回值就会覆盖之前==**的，用clearInterval(变量)关闭定时器也**==只能关掉最后一个==**，之前的就再也关不了了，看上去定时器也会越来越快

解决方法：**==在开始定时器之前就将要开始的定时器关闭，根据clearInterval()的特点，也不会报错==**

![1616071412606](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616071412606.png)







**==setTimeout()方法==**

**延时调用**

延时调用，和定时调用类似，也是有**两个参数**

延时调用一个函数不马上执行，而是隔一段时间以后再执行，**并且只会执行一次**

![1616073028618](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616073028618.png)

有一个返回值，用来标识延时调用，==可以将方法赋给一个变量==

![1616073289318](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616073289318.png)





==**clearTimeout()方法**==

用来关闭一个延时调用，**参数**是延时调用的**返回值**

![1616073205724](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1616073205724.png)



### 类的操作

之前修改元素的样式是直接通过js来修改元素的style属性，如下图：

![1617005848083](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617005848083.png)

这样修改的样式是直接在标签中修改的，**==属于内联样式，结构与行为耦合==**

并且**==每修改一个样式，浏览器就需要重新渲染一次页面==**

这样的执行的**==性能是比较差==**的，而且这种形式当我们要修改多个样式时，也不太方便

所以不推荐使用

可以通过**==className属性==**修改元素的类名，更新过的样式写到**新的类的css选择器**中，这样只用**改一下类名**，同时修改多个样式，**行为与表现也分离**了，**浏览器也只用执行一次就行**

![1617006107582](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617006107582.png)

![1617006117552](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617006117552.png)



如果只是想更新一些属性，并不想完全覆盖，可以将类名 + “ 另一个类名”，将类名进行拼串操作，新的类名前面要有空格，这样元素就有两个类名了，新的类名选择器中写要更新的样式

![1617006391084](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617006391084.png)

![1617006416390](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617006416390.png)



改进解决方法：

可以创建一个下面的函数，进行**==属性的添加==**

![1617006893217](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617006893217.png)

但是这样有一个缺点，添加之前不仅行类名检查，这样同一个类可以添加多次

![1617007089422](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617007089422.png)

可以添加一个**==类名检查的函数==**，函数两个参数：元素、类名

因为要用到正则表达式，类名作为变量传入，就不能使用字面量来创建正则表达式（不能使用变量），只能用构造函数创建法

![1617007304737](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617007304737.png)



将上面创建的两个addClass和hasClass函数结合起来，整合成一个**==addClass函数==**

![1617007338361](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617007338361.png)



还可以写一个**==删除指定类选择器的函数==**，函数中使用replace方法，将指定类名替换为空串

![1617007496261](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617007496261.png)



除此之外，还可以创建一个切换类的函数toggleClass:

​	如果元素中具有该类，则删除

​	如果元素中没有该类，则添加

![1617007773201](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617007773201.png)



### JSON

js中的对象只有]S自己认识，其他的语言都不认识

JS0N就是一个**==特殊格式的字符串==**，这个字符串**==可以被任意的语言所识别==**，

并且**==可以转换为任意语言中的对象==**，JSON在开发中主要用来**==数据的交互==**



javascript object notation（js对象表示法）

JSON和JS对象的格式一样，只不过JSON字符串中的**==属性名必须加双引号==**，其他的而语法和js一样

json分类	：1.对象，使用{}

​		    2.数组，使用[]



JSON中只允许的值：

1.字符串

2.数值

3.布尔值

4.null

5.对象（只是普通的对象，不包括函数）

6.数组

下面的都是json对象

![1617012656558](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617012656558.png)



在JS中，为我们提供了一个工具类，就叫JSON

这个对象可以帮助啊我们将一个JSON对象转化为一个JS对象，也可以将一个JS对象转化为一个JSON对象



**JSON-->JS对象**

**==JSON.parse(JSON字符串)==**

可以将一个JSON字符串转化为JS对象（同样，如果在java中，也可以转换为Java对象）

它需要一个JSON字符串作为参数，会将该字符串转换为**==J5对象并返回==**

![1617013146393](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617013146393.png)

![1617013243480](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617013243480.png)



**JS对象-->JSON字符串**

**==JSON.stringify()==**

可以将一个JS对象转化为一个JSON字符串

需要一个js对象作为参数，会返回一个JSON字符

![1617013485897](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617013485897.png)

真整个变成了字符串，并且属性名也加上了双引号



JSON这个对象在**==IE7及以下的浏览器==**不能使用，会报错



**==eval()函数==**

这个函数可以用来执行一段==字符串形式的JS代码==，并==将执行结果返回==

![1617013878232](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617013878232.png)

加果使用**eval()**执行的字符串中含有**=={}==**,它会将{}当成是**==代码块==**
如果不希望将其当成代码块解析，则需要在字符串前后各加一个**==()==**

![1617014073932](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1617014073932.png)

eval()这个函数的功能很强大，可以直接执行一个字符串中的JS代码

但是在开发中尽量不要使用，首先它的==执行性能比较差==，然后它还具有==安全隐患==











### PS

--------------------------------------------------------------------



**prompt** ：prompt() 弹出一个文本框，可以在文本框中输入内容，可以将提示文字作为函数的参数。函数的返回值是**string**类型的

```javascript
var name=prompt("Please enter your name","")
```



需要利用输入的值进行运算时，先进行==类型的转换==（比如在返回值前面加上加号）

![1615095634545](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615095634545.png)









····················································

document.write()是向网页里面输出，换行的话不能用\n，而应该用标签==<br />==

![1615096891289](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615096891289.png)











...............................................................

**在html代码中&nbsp和空格的区别**：

在html代码中每输入一个转义字符&nbsp就表示一个空格，输入十个&nbsp，页面中就显示10个空格位置。

而在html代码中输入空格，不管输入多少个空格，最终在页面中显示的空格位置只有一个。









..........................................................................

html-css:

- **inline:**
  1. 使元素变成行内元素，拥有行内元素的特性，即可以与其他行内元素共享一行，不会独占一行. 
  2. 不能更改元素的height，width的值，大小由内容撑开. 
  3. 可以使用padding，margin的left和right产生边距效果，但是top和bottom就不行.
- **block:**
  1. 使元素变成块级元素，独占一行，在不设置自己的宽度的情况下，块级元素会默认填满父级元素的宽度. 
  2. *能够改变元素的height，width的值.* 
  3. *可以设置padding，margin的各个属性值，top，left，bottom，right都能够产生边距效果.*
-  **inline-block:**
  1. 结合了inline与block的一些特点，结合了上述inline的第1个特点和block的第2,3个特点.
  2. 用通俗的话讲，就是不独占一行的块级元素。



..........................................................................

**console.time()**来创建一个计时器，括号里面写计时器的名字

**console.timeEnd()**来终止一个计时器，括号里面写计时器的名字，并且输出脚本执行的时间









..........................................................................

**Math.sqrt()**对一个数进行开方











...........................................................................

**HTML页面的 \<script type="text/javascript">含义。**

在老的HTML版本，如果需要在HTML页面中声明一段js脚本，需要做\<script type="text/javascript">的声明，表明在\<script type="text/javascript">和\</script>中添加的文本是js脚本；

在HTML5以后，HTML5的默认脚本语言就是javascript即js，所以无需显示声明 type="text/javascript"

，直接使用\<script>  \</script>即可。



...........................................................................







 \<meta> 标签是 HTML 语言头部的一个辅助性标签，我们可以定义页面编码语言、搜索引擎优化、自动刷新并指向新的页面、控制页面缓冲、响应式视窗等！

 ![1615371167331](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615371167331.png)







................................................................................................

**instanceof：使用instanceof可一检查一个对象是否是一个类的实例**

![1615371067936](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615371067936.png)









....................................................................................................

isArray()方法：判断一个对象是不是数组

语法：

​	Array.isArray(对象);









...................................................................................................

==innerHTML属性==，该属性可以获取某个元素内的HTML代码

==innerText属性==，该属性可以获取元素内部的文本内容，他和innerHTML类似，不同的是他会自动地将HTML标签去除，只保留文本内容

==nodeValue属性==

获取某个节点的文本内容，大部分情况下做到的效果跟innerText一样，**但是比innerText麻烦**

![1615772837363](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615772837363.png)









.................................................................................................

==checked属性==，返回或者设置HTML中\<checkbox>类型的标签是否被选中

![1615797670248](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615797670248.png)







................................................................................................

HTML的超链接默认点击后都会跳转

不希望出现跳转行为的话，如果为超链接绑定了响应事件，==可以在点击事件的响应函数最后return false==，来取消默认行为

![1615882790966](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615882790966.png)





或者，可以直接在标签中==herf属性中将内容改为javascript:;==   也可以取消跳转

![1615882933698](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615882933698.png)





















...............................................................................................

==confirm==是window下的方法，跟alert相似

==只不过confirm有确认和取消两个按钮，alert只有确认==



如果用户点击确认，则返回true，如果用户点击取消，则返回false



可以可以在某些操作（如删除操作）的响应函数中使用confirm，==来进行行为的确认==

![1615883732596](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615883732596.png)

![1615883332265](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615883332265.png)













........................................................................................................

如果为表单项添加 **==disabled="disabled"==**则表单项将变成不可用的状态，相应按钮或者选项将变成不可用的 

![1615899109318](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615899109318.png)

![1615899133912](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615899133912.png)



元素中也有disable属性

![1615899408819](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615899408819.png)





......................................................................................................

获取滚动条距离顶端的距离，通过**==scrollTop属性==**

chrome认为浏览器的滚动条是**==body==**的，可以通过document.body.scrollTop来获取

火狐等浏览器认为滚动条是**==HTML==**的。可以通过document.documentElement.scrollTop

![1615977829430](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615977829430.png)

**<font color='orange'>注意 : 现在document.documentElement.scrollTop都可以用了</font>**









...........................................................................................................

clientX和clientY获取鼠标相对于当前可见的页面坐标

div块的偏移量一般都是用的相对于整个原始页面的偏移量

pageX和PageY获取鼠标相对于整个原始页面的偏移量，但是在IE8中不支持



........................................................................................................

**==元素.className==**，此属性可以返回标签的class属性的内容







......................................................................................................

**==事件的target属性==**，表示触发事件所在的那个元素对象

语法：事件.target

![1615981438316](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615981438316.png)











..........................................................................................................



**==bind()方法==**

二个作用：

​	用来修改函数的this指向

​	用来向调用的函数传递参数



**与call和apply的联系：**

作用和==call==和==apply==相似

bind参数的传递规则和call一样，一个个传递，apply参数无论几个都要封装成数组

call() 和apply()，都是立马就调用了对应的函数，而 bind() 不会， bind() 会生成一个新的函数(下面实例)



例子:

![1615989961609](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1615989961609.png)



详解，看这个就明白了：https://blog.csdn.net/qiqingjin/article/details/50706087





### 末尾处 