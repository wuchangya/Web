# 判断数据类型的方法

**==typeof==**：返回数据类型的字符串表达



**==instanceof==**：使用instanceof可一检查一个对象是否是一个**类的实例**，返回值是一个布尔值

**==语法console.log(a instanceof b)==**

其中b应当是一个构造函数

注意，这里构造函数可以是自己定义的 ，也可以是**Object、Array、Function**，因为创建对象、数组、函数的时候，有一种方法就是使用构造函数new一个

**所以b是Object、Array、Function时，就是用来判断a是不是数组、对象、函数**

**其中数组、函数都属于对象**



**==\=\=\===**：只有undefined和null可以用三个等号来判断



```javascript
//判断undefined类型
var a;
console.log(typeof a==='undefined',a===undefined);
//判断数值类型
a=3;
console.log(typeof a ==='number');
//判断字符串类型
a='atguigu';
console.log(typeof a ==='string');
//判断布尔值
a= true;
console.log(typeof a ==='boolean');
//判断null类型
a = null;
console.log(a ===null)
//判断对象类型
var b1 = {
    b2: [1,'abc',console.log],
    b3: function(){
        console.log('b3')
    }
}
console.log(b1 instanceof Object)//true
console.log(b1.b2 instanceof Array,b1.b2 instanceof Object)//true true
console.log(b1.b3 instanceof Function,b1.b3 instanceof Object)//true true
console.log(typeof b1.b3)//function
console.log(typeof b1.b2)//object
console.log(typeof b1)//object
```

**<font color='red'>总结：</font>**

Number、String、Boolean、Null、Undefined、Function、Object类型可以用typeof来判断或者查看

但是Array、Data等Object类型的判断不了

使用instanceof来判断各种**==引用类型==**或者**==自己创建的构造函数==**，不能判断基本类型



## instanceof原理

其真正含义是判断一个构造函数的prototype属性所指向的对象是否在另一个被检测对象的原型链上

```javascript
function Animal() {}
var a = new Animal();
function Cat() {}

var c1 = new Cat();
Cat.prototype = a;//改变Cat的原型
var c2 = new Cat();

console.log(c1 instanceof Cat); // false
console.log(c2 instanceof Cat); // true
console.log(c1 instanceof Animal);  // false
console.log(c2 instanceof Animal);  // true
```



# 原型与原型链

## 原型prototype

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





某一个函数的原型对象中有一个属性：**==constructor==**，它**==反过来指向这个自身的函数对象==**

就是形成了一个相互引用的关系

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210503171041311.png" alt="image-20210503171041311" style="zoom:80%;" />

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210503191034117.png" alt="image-20210503191034117" style="zoom:67%;" />

## 显示原型与隐式原型

每个函数 function部有一个 prototype,**==显式原型==**（属性）

每个实例对象部有一个 \__proto__，可称为**==隐式原型==**（属性）

对象的隐式原型的值为其对应构造函数的显式原型的值

![image-20210503180017221](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210503180017221.png)

总结：

函数的 prototype属性：在定义函数时自动添加的，默认值是一个空Object对象

对象的 \__proto__属：创建对象时自动添加的，默认值为构造数的 prototype属性值

**==程序员能直接作显式原型==**，但不能直接作隐式原型(**==ES6之前==**)

 

## 原型链

![image-20210503182527371](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210503182527371.png)

为防止混乱，下面是将构造函数的实例加到图中后的样子

![image-20210503184737765](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210503184737765.png)

图中构造函数的原型对象类型是一个Object，这样就意味着**==原型也会有一个原型\__proto__==**（隐式），指向**==Object构造函数的原型prototype==**（显示），这个Object是本来就有的一个构造函数

之前讲过，在实例对象中调用一个属性，现在实例中找，没有就去原型中找，在没有就去原型的原型中找。最多也就两层，没有原型的原型的原型。

现在看起来就好理解了，**==一个实例的原型的原型==**其实就是指向了**==Object的原型地址==**，图中显示，**==Object原型中也有一个\__proto__，但是这个属性是null空的==**，也就没有第三层原型

这就形成了一个所谓的原型链，从图中可以看出，**==原型链==**本质上是一个**==隐式原型链==**

原型链作用：查找对象的属性

（对比来即记，查找变量通过作用域链）



上面那个图还不全，因为**==每一个函数==**除了有prototype显式原型，还有\__proto__隐式原型，上面那个图隐式原型没画出来

![image-20210505182345447](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210505182345447.png)

任何一个构造函数都是Function的实例，当然有Function对象的原型，**<font color='red'>但是这个Function对象比较难理解</font>**

Function对象的**==隐式原型（作为实例）==**和**==显示原型（作为构造函数）==**指向的都是同一个，看图可以这么理解，**<font color='red'>Function对象是他自己本身的一个实例</font>**，不然没根没源的



## 原型链补充

**<font color='red'>①</font>** **==函数（包括官方的构造函数）的显示原型prototype==**指向的对象默认是一个空的**==Object实例对象==**(但Object不足)	

![image-20210505184417636](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210505184417636.png)

**<font color='red'>②</font>** **==所有函数都是Function的实例（包括Function自身）==**

![image-20210505185059921](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210505185059921.png)

**<font color='red'>③</font>** **==Object的原型对象时原型链的尽头==**

![image-20210505185200010](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210505185200010.png)



ps：

```javascript
console.log(Function.prototype.__proto__===Object.prototype);//true
console.log(Function.prototype===Object.__proto__);//true
console.log(Function.__proto__===Function.prototype);//true
```





## 原型链属性问题

**读取**对象的属性值时：会自动到原型链中查找

**设置**对象的属性值时：**==不会查找原型链==**，如果当前对象中没有此属丝，直接添加此属丝并设置其值

**方法**一般定义在**原型**中，**属性**一般通过**构造函数定义在对象本身上**



## instanceof

instanceof用来判断一个对象是不是另一个对象的实例



**<font color='red'>判断的原理</font>**：

表达式A instanceof B

**<font color='red'>如果B函数的显示原型对象在A对象的原型链上，返回true，否则返回false</font>**

![image-20210506160946379](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210506160946379.png)







**==变量声明提升==**

过var定义（声明）的変量，在定义语句之前就可似访到

值： **undefined**

**==函数声明提升==**

通过 function声明的函数，在之前就可以直接调用

值：函数定义（对象）

![image-20210506162631146](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210506162631146.png)



![image-20210506162930259](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210506162930259.png)

## 执行上下文

![image-20210506165604811](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210506165604811.png)



### 执行上下文栈

![image-20210506170921885](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210506170921885.png)







## 作用域与作用域链

![image-20210506172923676](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210506172923676.png)



### 作用域与上下文的区别

![image-20210506173132051](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210506173132051.png)

![image-20210506175407962](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210506175407962.png)



## 闭包

如何产生闭包？

当一个嵌套的内部子函数引用了嵌套的外部父函数的变量函数时，就产生了闭包

![image-20210506185122736](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210506185122736.png)



**==闭包到底是什么？==** 使用Chrome查看

理解一：闭包是嵌套的内部函数（大部分人这么理解）

理解二：如同上面这个图片，包含外部函数被引用变量的对象（少部分人这么理解）



**==产生闭包条件：==**

产生嵌套

内部函数引用了外部函数的数据（变量/函数）

执行外部函数（**不用执行内部函数**就行）



## 常见的闭包

将函数作为另一个函数的返回值

经函数作为实参传递给另一个函数调用

​	![image-20210506202354623](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210506202354623.png)

![image-20210506205342064](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210506205342064.png)

## 闭包的作用

使函数内部的变量在函数执行完后，仍然活在内存中（延长了局部变量的生命周期）

让函数外部可以操作到函数内部的数据（读写）





## 闭包的缺点及解决

**==缺点==**

函数执行完后，函数内的局部变量没有变化，占用的内存时间变长

容易造成内存泄漏

**==解决==**

能不用闭包就不用闭包

及时释放，在退出函数之前，将不使用的局部变量全部删除。





## 内存溢出与内存泄漏

**==内存溢出==**

一种程序运行出现的错误

当程序运行需要的内存超过了剩余的内存时，就出抛出内存溢出的错误



**==内存泄露==**

占用的内存没有及时择放

内存积累多了就容易导致内存溢出



**<font color='red'>常见的内存泄露</font>**：

​	①意外的全局变量，比如：在函数里面定义全局变量，导致执行环境无法清除

​	②没有及时清理的计时器(**setTimeout setInterval**)或回调函数

​	③对闭包的使用导致无法清除

​	④循环引用，函数中虽然没有全局变量，但是下面这个函数有两个对象互相引用，导致垃圾回收的时候不能清除这种还有引用的对象（解决方法：在函数中手动将其置空）

```javascript
function func() {
    let obj1 = {};
    let obj2 = {};

    obj1.a = obj2; // obj1 引用 obj2
    obj2.a = obj1; // obj2 引用 obj1
}
```





<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210506220309660.png" alt="image-20210506220309660" style="zoom:67%;" />



## 原型链继承（继承属性）

**<font color='red'>关键做法就是</font>**，**==作为子类型的构造函数原型prototype指向父类型的一个实例对象==**

**<font color='red'>只能获得父类型的方法，定义在父类型构造函数中的属性继承不了</font>**

![image-20210507114229916](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210507114229916.png)

![image-20210507115453507](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210507115453507.png)



接着上面的例子讲

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210507144602234.png" alt="image-20210507144602234" style="zoom:67%;" />

constructor查看实例的构造函数，但是Sub继承了 Supper的原型，**==这里 constructon返回的是 Supper==**，本来应该返回Sub

**==所以应该手动修改一下constructor的值，将其指向Sub==**

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210507145505074.png" alt="image-20210507145505074" style="zoom:67%;" />



## 借用构造函数继承（继承方法）

关键操作在于：在子类型构造函数中通过==**call()**==来调用父类型构造函数

但是这种继承是一种**==假的继承==**，就**==相当于代码的简写==**，**==跟把父类型构造函数中的代码复制过来作用一样，==**

**<font color='red'>只能获得父类型的属性，定义在原型上的方法继承不了</font>**

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210507151205508.png" alt="image-20210507151205508" style="zoom:67%;" />



## 组合继承（继承属性和方法）

一般将上面两种继承方式结合起来

在子类型构造函数中使仍然

**<font color='red'>①</font>** **==用call调用父类型构造函数==**，

仍然**<font color='red'>②</font>** **==将子类型的构造函数的prototype原型指向父类型的构造函数的一个实例==**，

**<font color='red'>③</font>**也需要**==修改一下constructor的值==**



之前讲过，按我们的习惯，将**==属性==**放在构造函数中，将==**方法**==放在构造函数的原型中

那么刚才前两步，**==call的使用是为了得到父类型构造函数的属性==**，**==修改prototype是为了得到父类型的方法==**

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210507151600407.png" alt="image-20210507151600407" style="zoom:67%;" />





















































































































