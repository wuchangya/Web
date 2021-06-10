# let变量

①

变量不能重复声明

var可以重复声明

②

let有块级作用域

var没有块级作用域

![1618879782943](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618879782943.png)

![1618879751488](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618879751488.png)

③

不存在变量提升

var有变量提升

④

不影作用域链



# const

一定要**==赋初始值==**

**==一般常量大写==**

常量的值不能修改

存在块级作用域

对于**==数组元素的修改不算对常量的修改==**，因为数组指向的地址始终没有改变



# 变量的解构赋值

数组的解构

![1618880067816](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618880067816.png)

方法的解构

![1618880129856](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618880129856.png)





# 模板字符串

在es6中有一个新的引号：**==``==**（即键盘上的破浪号）

``引号使用时字符串**==可以换行==**





**==ES6模板字符串之标签模板==**

首先，**模板字符串**和**标签模板**是两个东西。

**<font color='red'>标签模板：</font>**它不是模板，而是**==函数调用的一种特殊形式==**。**==“标签”指的就是函数==**，紧跟在后面的**==模板字符串==**就是它的**==参数==**。

但是，如果**==模板字符串中有变量==**，就不再是简单的调用了，而是要**==将模板字符串先处理成多个参数，再调用函数。==**

**拆分方法**： 将模板字符串以其中的变量为分割（变量在最后，要多出来一个空格），拆分成多个字符串，并合并成一个数组，作为函数一个参数，那些变量则计算后分写作为函数的参数

由此引出此文，先上代码：

```javascript
var a = 5;
var b = 10;
 //tag这里相当于一个函数
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





# 对象的简化写法

![1618880966158](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618880966158.png)

函数可以省略function



# 箭头函数

①**==this是静态的==**，**==始指向行函数声明时所在的作用域下的this值==**

并不会像之前构造函数，谁调用this就指向哪个实例对象

②箭头函数并**==不能作为构造函数==**实例化对象

③箭头函数**==没有原型对象prototype==**

④**==不能使用arguments变量==**



例子：

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618882369069.png" alt="1618882369069" style="zoom:80%;" />

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618882416013.png" alt="1618882416013" style="zoom:80%;" />



例子：

![1618882569282](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618882569282.png)



箭头函数适合于this无关的回调，定时器、数组方法的回调

箭头函数不适合与this有关的回调，事件的回调函数、对象的方法



# 参数默认值设置

es6允许给函数参数赋初始值

①形参初始值

具有默认值的参数，一般位置要靠后（放在前面不会报错，但是使用不了，想要省略某一个参数的赋值，参数传进去后，被省略的总是最后一个形参，前面的都被赋值了，所以放前面说意义不大）

![1618883013266](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618883013266.png)

②与解构赋值结合

![1618883280095](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\1618883280095.png)





# rest参数

es6中引入rest参数，用来获取函数的实参，用来代替arguments









# 扩展运算符



扩展运算符（ spread ）是三个点（...），可以将一个数组转为用逗号分隔的参数序列。

说的通俗易懂点，有点像化骨绵掌，**==把一个大元素给打散成一个个单独的小元素。==**



基本用法：拆解字符串与数组

```js
var array = [1,2,3,4];
console.log(...array);//1 2 3 4 
var str = "String";
console.log(...str);//S t r i n g
```



**==扩展运算符应用==**

**2.1 某些场景可以替代apply**

在使用Math.max()求数组的最大值时，ES5可以通过 apply 做到（用一种不友好且繁琐的方式）

```js
// ES5 apply 写法
var array = [1,2,3,4,3];
var max1 = Math.max.apply(null,array);
console.log(max1);//4
```

幸运的是JavaScript的世界在不断改变，扩展运算符可用于数组的析构，优雅的解决了这个问题。

```js
// ES6 扩展运算符 写法
var array = [1,2,3,4,3];
var max2 = Math.max(...array);  
console.log(max2);//4
```

先把 array 打散成 1 2 3 4 3，再在里面找最大的那一个，就显而易见了。

**2.2 代替数组的push、concat 等方法**

实现把 arr2 塞到 arr1 中

```js
// ES5 apply 写法
var arr1 = [0, 1, 2];
var arr2 = [3, 4, 5];
Array.prototype.push.apply(arr1, arr2);
//arr1   [0, 1, 2, 3, 4, 5]
```

扩展运算符又要施展化骨大法了

```js
// ES6 扩展运算符 写法
var arr1 = [0, 1, 2];
var arr2 = [3, 4, 5];
arr1.push(...arr2);
//arr1   [0, 1, 2, 3, 4, 5]
```

通俗的解释下， 扩展运算符先把 arr2 打散成 3 4 5 ， 之后再往arr1里push，就轻松多了。



同理可推，**==concat==** 合并数组的时候：

```js
var arr1 = ['a', 'b'];
var arr2 = ['c'];
var arr3 = ['d', 'e'];

// ES5的合并数组
arr1.concat(arr2, arr3)  // [ 'a', 'b', 'c', 'd', 'e' ]

// ES6的合并数组
[...arr1, ...arr2, ...arr3]  // [ 'a', 'b', 'c', 'd', 'e' ]

```

ES5的合并数组写法，像是 arr1 把 arr2，arr3 给吸收了。

而ES6的合并数组写法，则是先把 arr1，arr2， arr3 拆解，之后塞到新的数组中。

**2.3 拷贝数组或对象**

```js
//拷贝数组
var array0 = [1,2,3];
var array1 = [...array0];
console.log(array1);//[1, 2, 3]

//拷贝对象
var obj = {
    age:1,
    name:"lis",
    arr:{
        a1:[1,2]
    }
}
var obj2  = {...obj};
console.log(obj2);//{age: 1, name: "lis", arr: {…}}
```

无论是像克隆数组还是对象，先用化骨绵掌之扩展运算符，将其打散，之后再拼装的到一起就可以了，多么简单易用。



**2.4 将伪数组转化为数组**

```js
//伪数组转换为数组
var nodeList = document.querySelectorAll('div');
console.log([...nodeList]);  // [div, div, div ... ]
```

上面代码中，querySelectorAll 方法返回的是一个 nodeList 对象。它不是数组，而是一个类似数组的对象。

这时，**==扩展运算符可以将其转为真正的数组==**，原因就在于 NodeList 对象实现了 Iterator。

注意：使用扩展运算符将伪数组转换为数组有局限性，这个类数组必须得有默认的迭代器且伪可遍历的。

# rest 运算符

**==剩余运算符（the rest operator）==**，它的样子看起来和展开操作符一样，但是它是用于**==解构数组和对象==**。在某种程度上，剩余元素和展开元素相反，展开元素会“展开”数组变成多个元素，**==剩余元素会收集多个元素和“压缩”成一个单一的元素。==**

说的通俗点，有点像吸星大法，收集多个元素，压缩成单一的元素 。

rest参数用于获取函数的多余参数，这样就不需要使用**==arguments对象==**了。rest参数搭配的变量是一个数组，该变量将多余的参数放入数组中。

如果函数有实参，rest参数要接收多余的实参，**==它必须放在最后==**



例如实现计算传入所有参数的和

使用arguments参数：

```js
function sumArgu () {
     var result = 0;
     for (var i = 0; i < arguments.length; i++) {
        result += arguments[i];
    }
    return result
}
console.log(sumArgu(1,2,3));//6
```

使用rest参数：

```js
function sumRest (...m) {
    var total = 0; 
    for(var i of m){
        total += i;
    }
    return total;
}
console.log(sumRest(1,2,3));//6
```

上面代码利用 rest 参数，可以向该函数传入任意数目的参数。传递给 sumRest 函数的一组参数值，被整合成了数组 m。

就像是吸星大法，把分散的元素收集到一起。

所以在某些场景中，**==无需将arguments转为真正的数组，可以直接使用rest参数代替==**。

## rest 运算符应用

**4.1 rest 参数代替arguments变量**

```javascript
// arguments变量的写法,将arguments转化为数组，然后用sort进行排序
function sortNumbers() {
  return Array.prototype.slice.call(arguments).sort();
}

// rest参数的写法，将arguments转化为数组，并进行排序
const sortNumbers = (...numbers) => numbers.sort();
```

上面的两种写法，比较后可以发现，rest 参数的写法更自然也更简洁。

**<font color='red'>不过，rest参数和arguments对象有一定的区别：</font>**

![img](https://pic3.zhimg.com/80/v2-d44e609a9f48a562bc2a3fef260a7fc2_720w.jpg)

**4.2 与解构赋值组合使用**

```js
var array = [1,2,3,4,5,6];
var [a,b,...c] = array;
console.log(a);//1
console.log(b);//2
console.log(c);//[3, 4, 5, 6]
```

备注：rest参数可理解为剩余的参数，所以必须在最后一位定义，如果定义在中间会报错。

```js
var array = [1,2,3,4,5,6];
var [a,b,...c,d,e] = array;
//  Uncaught SyntaxError: Rest element must be last element
```



## 总结

**5.1 扩展运算符和rest运算符是逆运算**

扩展运算符：数组=>分割序列

rest运算符：分割序列=>数组



**5.2 扩展运算符应用场景**

由于其繁琐的语法，apply 方法使用起来并不是很方便。当需要拿一个数组的元素作为函数调用的参数时，

扩展运算符是一个不错的选择。

扩展运算符还改善了数组字面量的操作，你可以更方便的初始化、连接、复制数组了。

使用析构赋值你可以提取数组的一部分。通过与迭代器协议的组合，你可以以一种更灵活的方式使用该表达式。

**5.3 rest运算符应用场景**

rest运算符主要是处理不定数量参数，rest参数使得收集参数变得非常简单。它是类数组对象arguments一个合理的替代品。

**rest参数还可以与解构赋值组合使用。**

**在实际项目中灵活应用扩展运算符、rest运算符，能写出更精简、易读性高的代码。**





# Symbol

ES6引入了一种新的原始数据类型 Symbol**==表示独一无二的值==**。

它是Javascript语言的第七种数据类型，是一种**==类似于字符串的数据类型==**。



## Symbol特点

1) Symbol的值是**唯一**的，用来解决命名冲突的问题

2) Symbol 值**不能与其他数据进行运算**

3) Symbol定义的对象属性**不能使用for...in循坏遍历**，但是可以使用**==Reflect. own Keys==**来获取对象的所有键名

## 创建方法

**<font color='red'>①</font>**

![image-20210420153736458](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420153736458.png)

**==Symbol创建==**：通过**==Symbol()函数调用==**，来返回一个Symbol值

Symbol创建的是唯一的一个值，但是通过console.log打印出来仍是Symbol()，在这里是观测不到的



还可以往Symbol()函数中**==传入一个参数==**，这个参数**==只是用来描述Symbol值而已==**，并不是随机因子的作用，**==参数相同的Symbol函数得到的Symbol值也是不一样的==**

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420154358731.png" alt="image-20210420154358731"  />

**<font color='red'>②</font>**

可以通过**==Symbol.for([参数])==**，这种方式来创建SYmbol值，同样，里面的参数可选

但不同的是：1.这种方法不是通过函数创建的了，而是一个**==函数对象==**

​						2.这种方法传入的参数，**==相同参数得到的Symbol值是一样的==**

**首先会在全局搜索被登记的 Symbol 中是否有该字符串参数作为名称的 Symbol 值，如果有即返回该 Symbol 值**，若没有则新建并返回一个以该字符串参数为名称的 Symbol 值，并登记在全局环境中供搜索。

![image-20210420154900683](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420154900683.png)

## 应用

给对象添加属性和方法

当想向一个对象中添加方法时，不确定这个对象中有没有已经存在相应的方法名，担心方法名重复，使得新加的方法覆盖了原来的方法

这时就可以使用Symbol值，使用方法如下，将方法名通过Symbol值来进行命名

**<font color='red'>Symbol 作为对象属性名时不能用.运算符，要用方括号。</font>**

![image-20210420155353542](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420155353542.png)



**<font color='red'>哪怕在对象里面创建方法的时候也要用中括号</font>**

![image-20210420160041332](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420160041332.png)



Symbol 值作为属性名时，该属性是**==公有属性==**不是私有属性，可以在类的外部访问。但是不会出现在 for...in 、 for...of 的循环中，也不会被 Object.keys() 、 Object.getOwnPropertyNames() 返回。如果要读取到一个对象的 Symbol 属性，可以通过 **==Object.getOwnPropertySymbols() 和 Reflect.ownKeys()==** 取到。

## Symbol的内置属性

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420172943492.png" alt="image-20210420172943492" style="zoom:80%;" />

这些内置属性是控制对象在特定场景下的一个表现，

举个例子，Symbol.hasInstance方法决定了使用instanceof方法判断某个对象是否是某个构造函数或者类的实例，相当于重写静态方法，**==参数是实例==**，其实可以在里面做一些判断，来动态决定结果，字啊面这个例子并没有详细操作

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210510083609947.png" alt="image-20210510083609947" style="zoom:67%;" />

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210510083829805.png" alt="image-20210510083829805" style="zoom:80%;" />

再例如

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420173545803.png" alt="image-20210420173545803" style="zoom:80%;" />



# 迭代器（Iterator）

**==作用==**：可以自定义遍历数据

es6中创造了一种新的遍历命令 for...of循环

for...of和for...in作用有区别

==**for...of循环的是数组值/对象的属性值**==

==**for...in循环的时数组索引/对象的属性名**==

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420180201140.png" alt="image-20210420180201140" style="zoom:80%;" />



只要对象中提供了Iterator接口就可以使用for...of循环

Iterator接口就是对象中**==Symbol.Iterator属性==**，它的值是一个**==函数==**

下面这些数据都具备Iterator接口，上面的例子中的**数组**就是其中之一

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420180058276.png" alt="image-20210420180058276" style="zoom:80%;" />

## 工作原理

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420180420413.png" alt="image-20210420180420413" style="zoom:80%;" />



下面是查看对象中的next方法，**==next是Symbol.Iterator属性中的一个方法==**，根据Symbol的特点，Symbol.Iterator只能用**<font color='red'>中括号</font>**括起来

![image-20210420180604156](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420180604156.png)

![image-20210420180732758](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420180732758.png)



## 迭代器的编程实现

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420183817422.png" alt="image-20210420183817422" style="zoom:80%;" />

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420183827874.png" alt="image-20210420183827874" style="zoom:80%;" />

![image-20210420183838946](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420183838946.png)

**==也就是我们使用for...of的时候，内部调用的是Symbol.iterator()方法，该方法的内部执行代码如上==**

# 生成器（Generator）

生成器其实是一种特殊的函数

用来进行异步编程

生成器是一种可以用来控制迭代器（iterator）的函数，它可以随时暂停，并可以在任意时候恢复。

## 声明与调用

生成器在声明上面和执行上面都跟一般的函数不一样

声明时，**==function * 函数名(){}==**，需要在function和函数名之间加一个**==*星号==**，*星号两边哪怕没有空格也行，

执行时直接执行函数并不会得到函数执行结果，如图

![image-20210420184733144](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420184733144.png)

打印出来这个函数，发现是一个迭代器对象，对象里面有一个**==next方法==**

==**只有执行这个迭代器对象中的next方法后，才会得到函数执行结果**==

![image-20210420185040375](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420185040375.png)



生成器中还有一个**==yield语句==**，yield语句用来**==分割生成器函数==**

如下图。三个yield语句将生成器分为四个部分

**==每执行一次next方法，生成器函数就往下执行一步==**

![image-20210420185857327](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420185857327.png)



也可以用for...of来进行遍历

![image-20210420190449296](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420190449296.png)

netx方法也有返回值，就是之前讲过的value，done（迭代器中讲过）

**==value==**就是yield后后面的值，**==done==**表示迭代器结束没结束

![image-20210420190609952](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420190609952.png)



## 参数传递



<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420191813233.png" alt="image-20210420191813233" style="zoom:80%;" />

生成器还可以进行赋值

yield也可以进行赋值，只不过yield的赋值是在调用next方法时，往next中进行赋值

如图，**==第二个next方法==**中进行赋值，传入到迭代器中**==第一个yield==**中，作为第一个yield的**==返回结果==**。可以console.log查看

以此类推，**==第三个next方法==**传入的参数作为**==第二个yield语句的返回结果==**



## ==生成器函数实例==

用来解决异步编程中**==回调地狱==**的现象：异步操作中还嵌套着好几层异步操作（在promise中讲过）

回调地狱：

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420193456587.png" alt="image-20210420193456587" style="zoom:80%;" />



**==例子：==**

首先模拟三个异步操作，将三个异步操作函数在外部定义，然后**==将三个异步函数放在生成器中的yield语句后面==**

然后可以**==调用生成器函数==**，并且**==执行一次next方法==**

![image-20210420194700330](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420194700330.png)

将执行的结果停留到第一次yield语句后，第一次异步操作执行结束后就不动了

然后将几个异步操作连起来，**==将三个next方法，放到三个异步函数中去==**。完整代码如下

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420194142817.png" alt="image-20210420194142817" style="zoom:80%;" />

这样整体代码结构就比较清楚了



**==实例2：==**

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420200206611.png" alt="image-20210420200206611" style="zoom:67%;" />

![image-20210420200533410](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420200533410.png)

之前讲的**==第二个next方法==**中传入的参数是**==第一个yield语句返回结果==**（第一个next在调用生成器函数就使用了），并且第二个next方法放在了第一个异步函数中，以此类推，

在生成器中yield返回结果使用变量进行接收，可以打印来

**<font color='red'>这样next与异步函数直接的关系比之前讲的更加直观</font>**

**<font color='red'>哪一个异步函数中next传入的参数，就是这个异步函数所在的yield语句返回值</font>**



# Promise

使用方法之前详细讲过，这里不再叙述

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420201213586.png" alt="image-20210420201213586" style="zoom:80%;" />





**==例子==**：利用node.js中的fs模块读取文件，读取文件本身就是一个异步操作

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420202108265.png" alt="image-20210420202108265" style="zoom:80%;" />

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420202036817.png" alt="image-20210420202036817" style="zoom:80%;" />

一个**==ajax数据请求==**的真实例子：（只不过这里没有成功，因为发生了口跨域问题）

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420204912371.png" alt="image-20210420204912371" style="zoom:67%;" />



## Promise的then方法

调用then方法**==then方法的返回结果==**是 **==Promise对象==**，**==Promise对象状态由回调函数的执行结果决定==**

①如果回调函数中返回的结果是**==非 promise类型==**的属性，数字、字符串等等，**==then方法的返回结果状态为成功==**，**==返回值为这个Promise对象的成功的值==**

![image-20210420211530594](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420211530594.png)

②如果then的回调函数中return返回的是一个Promise对象

则**==返回的这个Promise对象状态==**就决定了**==then返回的Promise对象状态==**

并且**==return返回的Promise对象成功/失败的值==**就是**==then返回的Promise对象成功/失败的值==**

![image-20210420211857809](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420211857809.png)

![image-20210420212149148](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420212149148.png)

③如果then函数中的回调函数中直接抛出错误，则then返回的Promise对象状态为失败，失败的值就是抛出错误的值

![image-20210420212353605](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420212353605.png)



因为then方法返回的是Promise对象由这种特性，所以可以在then中链式调用异步操作

## catch

catch是用来捕捉错误的

使用catch可以做到**==只指定一个回调函数==**，并且这个回调函数是执行错误的回调函数，可以免于指定成功的回调函数

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420214210255.png" alt="image-20210420214210255" style="zoom: 80%;" />





# set

ES6提供了新的数据结构**==Set（集合）==**。它类似于数组，**<font color='red'>但成员的值都是唯一的</font>**，

集合实现了 Iterator接口，所以可以使用**==扩展运算符==**和**==for...of==**进行遍历，

集合的属性和方法：

​	1)**==size==**返回集合的元素个数

​	2)**==add==**增加一个新元素，返回当前集合

​	3)**==delete==**删除元素，返回 boolean值

​	4)**==has==**检测集合中是否包含某个元素，返回 boolean值





通过new Set()构造函数来创建一个set

同时可以在创建set的时候附初始值，初始值是一个可迭代数据，一般的是一个数组，并且会**==自动为数组去重==**

![image-20210420215147284](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420215147284.png)



set的一些方法

**==size==**：得到set中数组长度

![image-20210420215528273](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420215528273.png)

**==add==**：往数组中添加一个元素

![image-20210420215609282](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420215609282.png)

**==has==**：检测集合中有没有相应的元素，存在的话就返回一个true，不存在true

![image-20210420215737461](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420215737461.png)

**==clear==**：清空集合

![image-20210420215839434](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420215839434.png)



## set实践

**<font color='red'>下面这些例子为什么在new Set前面再用一个扩展运算符呢？</font>**

因为一般求得是一个数组，而Set并不是一个数组，需要通过扩展运算符将其转换为数组

**==数组去重==**

![image-20210420220123827](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420220123827.png)

==**取交集**==

这里着重使用了集合 的知识，其实也可以使用数组的知识解决

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420220821122.png" alt="image-20210420220821122" style="zoom:80%;" />

简化

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420220948690.png" alt="image-20210420220948690" style="zoom:80%;" />

**==求并集==**

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420221054045.png" alt="image-20210420221054045" style="zoom:80%;" />

**==求差集==**

差集跟交集操作相反，在filter中选择后一个数组不存在的值

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420221916960.png" alt="image-20210420221916960" style="zoom:80%;" />

这两个数组谁在前面谁在后面，对于结果有影响



# map

ES6提供了Map数据结构。它**==类似于对象==**，也是键值对的集合。

**==但是“键”的范围不限于字符串==**，**==各种类型的值（包括对象）都可以当作键。==**

Map也实现了 Iterator接口，所以所以可以使用**==扩展运算符==**和**==for...of==**进行遍历，

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210420222328080.png" alt="image-20210420222328080" style="zoom:80%;" />

创建方法：通过new Map()构造函数来创建

Map的属性和方法：

**==set==**：添加元素，此方法有两个参数，即键值对，键的类型可以是各种类型

![image-20210421083659644](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421083659644.png)

**==size==**：返回Map元素的个数

![image-20210421083813144](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421083813144.png)

**==delete==**：删除某个元素，参数是删除元素的键名

![image-20210421083923607](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421083923607.png)

**==get==**：获取，参数是元素的键名

![image-20210421084050745](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421084050745.png)

**==clear==**：清空，清空Map中所有的元素

for...of遍历，遍历的结果是一个个数组，每个数组有两个元素，分别时键、值

![image-20210421084215610](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421084215610.png)

![image-20210421084236677](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421084236677.png)

![image-20210421084246674](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421084246674.png)





# class中的setter和getter的设置

**==get：==**

get方法对属性进行绑定，当在一个属性前使用get时，**==将属性写成函数形式==**，**==属性值通过返回值来定义==** ，此函数中含可以定义一些操作，当此**==属性被读取==**后，就会执行此函数中的操作

**==set：==**

在一个属性前面使用set方法，同样将属性写成函数的样子，但是**==必须为函数传入一个形参==**，可以**==不用返回值==**，在**==修改属性值==**的时候，就会执行set函数中的操作

<img src="C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421170124181.png" alt="image-20210421170124181" style="zoom:80%;" />

**==使用场景：==**

get可以用在动态变化的数据上，比如求平均值、总和，数据在变化，这时候使用get可以动态的读取实时的数据

set可以用在可以在修改属性时添加一些控制和判断，比如对数值类型的限定，在set函数中可以做判断，符合要求可以赋值，不符合就不赋值





# 数值方法的扩展

## Number. EPSILON

Number. EPSILON是 javascript表示的**==最小精度==**

EPSILON属性的值接近于2.228468492563136808472633361816E-16

我们斗志到编程语言中0.1+0.2不等于0.3

可以利用Number. EPSILON来编写以下函数，两值相差小于Number. EPSILON，就认为相等

![image-20210421171744109](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421171744109.png)

## 二进制和八进制

二进制以0b开头

八进制以0o开头

十六进制之前就有，以0x开头



## Number.isFinite

Number.isFinite检测一个数值是否是有限数

![image-20210421172300937](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421172300937.png)



**==ps:js中的Infinity属性==**

> Infinity(无穷大)在 JS 中是一个特殊的数字，它的特性是：它比任何有限的数字都大，如果不知道 Infinity， 我们在一些运算操作遇到时，就会觉得很有意思。
>
> 现在我们来看看 JS 中的Infinity 属性，了解用例并解决一些常见的陷阱。
>
> **1.Infinity(无穷)的定义
> **
>
> 无穷可以分为两种，正无穷和负无穷，JS 中对应的表示方式为：+Infinity(或者Infinity) 和 -Infinity。
>
> 这意味着Infinity和-Infinity（小于任何有限数的数字）都是number类型的特殊值：
>
> ```javascript
> typeof Infinity; // => 'number'
> typeof -Infinity; // => 'number'
> 
> ```
>
> Infinity 是全局对象的属性：
>
> window.Infinity; // => Infinity
>
> 另外，Number函数也有两个属性来表示正负无穷大：
>
> ```javascript
> Number.POSITIVE_INFINITY; // => Infinity
> 
> Number.NEGATIVE_INFINITY; // => -Infinity
> ```
>
> 
>
> **2. Infinity 的特性**
>
> Infinity比任何有限数都大。
>
> 举几个例子 Look Look:
>
> ```javascript
> Infinity > 100;           // => true
> 
> Infinity > Number.MAX_SAFE_INTEGER; // => true
> 
> Infinity > Number.MAX_VALUE;    // => true
> ```
>
> 
>
> Infinity 在加法、乘法和除法等算术运算中用作操作数时会产生有趣的效果：
>
> ```javascript
> Infinity + 1;    // => Infinity
> 
> Infinity + Infinity; // => Infinity
> 
> Infinity * 2;    // => Infinity
> 
> Infinity * Infinity; // => Infinity
> 
> Infinity / 2;    // => Infinity
> ```
>
> 
>
> 一些Infinity 的运算得到有限的数：
>
> ```javascript
> 10 / Infinity; // => 0
> ```
>
> 
>
> 一个有限的数除以0得到 Infinity 结果：
>
> ```javascript
> 2 / 0; // => Infinity
> ```
>
> 
>
> 对无穷数进行概念上不正确的运算会得到NaN。 例如，不能除以无限数，也无法确定无限数是奇数还是偶数：
>
> ```javascript
> > Infinity / Infinity; // => NaN
> >
> > Infinity % 2;    // => NaN
> 
> ```
>
> **2.1 负无穷**
>
> 负无穷小于任何有限数。
>
> 将-Infinity 与一些有限数字进行比较：
>
> ```javascript
> -Infinity < 100;           // => true
> 
> -Infinity < -Number.MAX_SAFE_INTEGER; // => true
> 
> -Infinity < -Number.MAX_VALUE;    // => true
> ```
>
> 
>
> 同时，负无穷小于正无穷：
>
> ```javascript
> -Infinity < Infinity; // => true
> ```
>
> 
>
> 当使用不同操作符操作数时，也可能会得到负无穷：
>
> ```javascript
> Infinity * -1; // => -Infinity
> 
> Infinity / -2; // => -Infinity
> 
> -2 / 0;    // => -Infinity
> ```
>
> 
>
> **3.判断无穷**
>
> 幸运的是，Infinity等于相同符号的Infinity：
>
> > ```javascript
> > Infinity === Infinity; // => true
> > 
> > -Infinity === -Infinity; // => true
> > ```
>
> 但前面的符号不一样就不相等，就也很好理解：
>
> ```javascript
> Infinity === -Infinity; // => false
> ```
>
> JSt有一个特殊的函数Number.isFinite(value)，用于检查提供的值是否有限数：
>
> ```javascript
> Number.isFinite(Infinity); // => false
> Number.isFinite(-Infinity); // => false
> Number.isFinite(999);    // => true
> ```
>
> \4. 无穷的的使用情况
> 当我们需要初始化涉及数字比较的计算时，无穷值就非常方便。例如，在数组中搜索最小值时：
>
> ```javascript
> function findMin(array) {
>  let min = Infinity;
>  for (const item of array) {
>   min = Math.min(min, item);
>  }
>  return min;
> }
> 
> findMin([5, 2, 1, 4]); // => 1
> ```
>
> 
>
> min变量使用Infinity初始化。 在第一次for()迭代中，最小值成为第一项。
>
> **5. Infinity 的的一些坑**
>
> 我们很可能不会经常使用Infinity值。 但是，值得知道何时会出现Infinity值。
>
> **5.1. 解析数据**
>
> 假设 JS 使用一个输入(POST请求、输入字段的值等)来解析一个数字。在简单的情况下，它会工作得很好:
>
> ```javascript
> parseFloat('10.5'); // => 10.5
> 
> parseFloat('ZZZ'); // => NaN
> ```
>
> 
>
> 这里需要小心的，parseFloat()将'Infinity'字符串解析为实际的Infinity数：
>
> ```javascript
> parseFloat('Infinity'); // => Infinity
> ```
>
> 
>
> 另一个是使用parseInt()来解析整数，它无法将'Infinity'识别为整数：
>
> ```javascript
> parseInt('10', 10); // => 10
> 
> parseInt('Infinity', 10); // => NaN
> ```
>
> 
>
> **5.2 JSON 序列化
> **
>
> JSON.stringify()将Infinity数字序列化为null。
>
> ```javascript
> const worker = {
>  salary: Infinity
> };
> 
> JSON.stringify(worker); // => '{ "salary": null }'
> ```
>
> salary 属性值为Infinity但是当字符串化为JSON时，"salary"值将变为null。
>
> **5.3 最大数溢出**
>
> Number.MAX_VALUE是 JS 中最大的浮点数。
>
> 为了使用甚至大于Number.MAX_VALUE的数字，JS 将该数字转换为Infinity：
>
> ```javascript
> 2 * Number.MAX_VALUE; // => Infinity
> Math.pow(10, 1000);  // => Infinity
> ```
>
> 
>
> 5.4 Math 函数
>
> JS 中Math命名空间的某些函数可以返回Infinity:
>
> ```javascript
> const numbers = [1, 2];
> const empty = [];
> Math.max(...numbers); // => 2
> Math.max(...empty); // => -Infinity
> Math.min(...numbers);// => 1
> Math.min(...empty); ``// => Infinity
> ```
>
> 在不带参数的情况下调用Math.max()时，返回-Infinity，而Math.min()则相应地返回Infinity。 如果尝试确定一个空数组的最大值或最小值，那结果后面人感到意外。
>
> **总结**
>
> JS中的Infinity表示无穷数的概念。 任何有限数均小于Infinity，而任何有限数均大于-Infinity。
>
> 比较 JS 中的无穷值很容易:Infinity === Infinity 为 true。特殊的函数Number.isFinite()确定提供的参数是否是一个有限的数字。
>
> 在涉及数字比较的算法时，可以使用Infinite初始化变量，用例是寻找数组的最小值。
>
> 解析来自输入的数字时，必须小心Infinity：Number('Infinity')，parseFloat('Infinity')返回实际的Infinity。 当使用JSON.stringify()序列化时，Infinity变为null。

## Number.isNaN()

Number.isNaN()检测一个数值是否为NaN

在es5中isNaN作为一个单独的函数，在es6中作为Number的一个方法

![image-20210421174149792](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421174149792.png)



## Number.parseInt()和Number.parseFloat()

Number.parseInt Number.parseFloat字符串转整数

parseInt和parseFloat在es5里面也是单独的方法，现在作为Number的方法

![image-20210421174953102](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421174953102.png)



## Number.isInteger()

判断一个数是否为整数

![image-20210421175051652](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421175051652.png)

## Math.trunc()

将小数部分抹掉

![image-20210421175117190](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421175117190.png)

## Math.sign()

检测一个数是正数、负数、零

![image-20210421175314843](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421175314843.png)

正数返回1

负数返回-1

零返回0



# 对象方法的扩展

## Object.is()

判断两个值是否相等，**==参数==**是要判断的两个值，相等返回true，不相等返回false

跟等号很像，但是有区别

Object.is判断两个NaN，结果是true，而等于号为false

![image-20210421175945086](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421175945086.png)



## Object.assign()

之前讲过这里不再讲



## Object.setPrototypeOf()

设置原型对象，两个参数，**==后面的对象设置为前面对象的原型==**

![image-20210421180728123](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421180728123.png)



## Object.getPrototypeOf()

获取对象的原型对象

![image-20210421180912156](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421180912156.png)



# 模块化

![image-20210421181849148](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421181849148.png)

基本的已经讲过了，这里只介绍一点

在导入的模块多的时候，直接新建一个js文件，一般都是**==app.js入口文件==**，在app.js文件中将所有文件中都会用到的模块统一引入

然后在**==入口index.html文件==**中引入app.js文件即可

通过**==script标签==**，**==type必须是module==**

![image-20210421183708626](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421183708626.png)



# babel对es6模块化代码的转换

上面写的es6模块化语法并不能对所有的浏览器实现兼容

这时候需要babel来对es6转化到es5

babel可以通过打包工具browserify或者webpack来进行下载

下面例子时使用browserify来下载的依赖（之前使用过webpack）

例子只是一个简单地示例，手动实现的文件的转换

然后进行打包上传

![image-20210421184954619](C:\Users\无常\AppData\Roaming\Typora\typora-user-images\image-20210421184954619.png)



































































































