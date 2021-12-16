1 介绍JavaScript的基本数据类型

Number、String 、Boolean 、Null、Undefined
Object 是 JavaScript 中所有对象的父对象
数据封装类对象：Object、Array、Boolean、Number 和 String
其他对象：Function、Arguments、Math、Date、RegExp、Error
新类型：Symbol

1.js中let和const有什么用？
在现代js中，let＆const是创建变量的不同方式。 在早期的js中，咱们使用var关键字来创建变量。 let＆const关键字是在ES6版本中引入的，其目的是在js中创建两种不同类型的变量，一种是不可变的，另一种是可变的。

const:它用于创建一个不可变变量。不可变变量是指其值在程序的整个生命周期中永不改变的变量。

let: let用于创建一个可变变量，可变变量是像var这样的普通变量，可以任意次数地更改。

2. JS 中的主要有哪几类错误
   JS有三类的错误:

加载时错误：加载web页面时出现的错误(如语法错误)称为加载时错误，它会动态生成错误。

运行时错误：由于滥用html语言中的命令而导致的错误。

逻辑错误：这些错误是由于对具有不同操作的函数执行了错误的逻辑而导致的

3. 如何通过类别名获取 dom 元素
   在 JS 中使用document.getElementsByClassName() 方法来获取具有类名的元素。



4.JS的作用域链是什么及其作用
一般情况下，变量取值到创建这个变量的函数的作用域中取值。但是如果在当前作用域中没有查到值，就会向上级作用域去查，直到查到全局作用域，这么一个查找过程形成的链条就叫做作用域链。

JS中的作用域链主要用于解析变量的值。 如果没有这个，在不同的作用域内定义了许多变量，JS很难为变量选择某个值。

5.解释JS中的MUL函数
MUL表示数的简单乘法。在这种技术中，将一个值作为参数传递给一个函数，而该函数将返回另一个函数，将第二个值传递给该函数，然后重复继续。例如:x*y*z可以表示为

function mul (x) {  
return function (y) {
return function (z) {   
return x * y * z;
}
}
}
6.用纯JS编写一个程序来反转字符串
使用内置函数：内置函数reverse()直接反转字符串。

str="jQuery";
str = str.split("")
str = str.reverse()
str = str.join("")
alert(str);
首先将字符串拆分为数组，然后反转数组，最近将字符连接起来形成字符串。

使用循环:首先，计算字符串中的字符数，然后对原始字符串应用递减循环，该循环从最后一个字符开始，打印每个字符，直到count变为零。

7.JS中如何将页面重定向到另一个页面？
东莞vi设计https://www.houdianzi.com/dgvi/ 豌豆资源网站大全https://55wd.com

使用 location.href：window.location.href =“https://www.onlineinterviewquestions.com/”

使用 location.replace： window.location.replace(" https://www.onlineinterviewquestions.com/;");



8. 列出JS中的一些设计模式:
   设计模式是软件设计中常见问题的通用可重用解决方案，以下是一些设计模式是：

创建模式：该模式抽象了对象实例化过程。

结构型模式：这些模式处理不同的类和对象以提供新功能。

行为模式：也称发布-订阅模式，定义了一个被观察者和多个观察者的、一对多的对象关系。

并行设计模式：这些模式处理多线程编程范例。

架构设计模式：这些模式用于处理架构设计。

9. JS中的Array.splice()和Array.slice()方法有什么区别
   话不多说，来看第一个例子：

var arr=[0,1,2,3,4,5,6,7,8,9];//设置一个数组
console.log(arr.slice(2,7));//2,3,4,5,6
console.log(arr.splice(2,7));//2,3,4,5,6,7,8
//由此我们简单推测数量两个函数参数的意义,
slice(start,end)第一个参数表示开始位置,第二个表示截取到的位置(不包含该位置)
splice(start,length)第一个参数开始位置,第二个参数截取长度
接着看第二个：

var x=y=[0,1,2,3,4,5,6,7,8,9]
console.log(x.slice(2,5));//2,3,4
console.log(x);[0,1,2,3,4,5,6,7,8,9]原数组并未改变
//接下来用同样方式测试splice
console.log(y.splice(2,5));//2,3,4,5,6
console.log(y);//[0,1,7,8,9]显示原数组中的数值被剔除掉了
slice和splice虽然都是对于数组对象进行截取,但是二者还是存在明显区别,函数参数上slice和splice第一个参数都是截取开始位置,slice第二个参数是截取的结束位置(不包含),而splice第二个参数(表示这个从开始位置截取的长度),slice不会对原数组产生变化,而splice会直接剔除原数组中的截取数据!

10.如何在JS中动态添加/删除对象的属性？
咱们可以使用object.property_name = value向对象添加属性，delete object.property_name 用于删除属性。

例如：

let user = new Object();
// adding a property
user.name='Anil';
user.age  =25;
console.log(user);
delete user.age;
console.log(user);
11.解释一下什么是 promise ？
promise是js中的一个对象，用于生成可能在将来产生结果的值。 值可以是已解析的值，也可以是说明为什么未解析该值的原因。

promise 可以有三种状态:

pending：初始状态，既不是成功也不是失败

fulfilled：意味着操作完全成功

rejected：意味着操作失败

一个等待状态的promise对象能够成功后返回一个值，也能失败后带回一个错误
当这两种情况发生的时候，处理函数会排队执行通过then方法会被调用。

12. 数组去重复的方法有哪些
    1.使用 set

function uniquearray(array) {
let unique_array= Array.from(set(array))
return unique_array;
}
2.使用 filter

function unque_array (arr) {
let unique_array = arr.filter(function(elem, index, self) {
return index == self.indexOf(elem);
})
return unique_array;
}

console.log(unique_array(array_with_duplicates));
3.使用 for 循环

Array dups_names = ['Ron', 'Pal', 'Fred', 'Rongo', 'Ron'];
function dups_array(dups_names) {
let unique = {};
names.forEach(function(i) {
If (!unique[i]) {
unique[i] = true;    }
});
return Object.keys(unique);}   // Ron, Pal, Fred, Rongo
Dups_array(names);
13. undefined，null 和 undeclared 有什么区别？
    1.null表示"没有对象"，即该处不应该有值，转为数值时为0。典型用法是：

（1） 作为函数的参数，表示该函数的参数不是对象。

（2） 作为对象原型链的终点。

2.undefined表示"缺少值"，就是此处应该有一个值，但是还没有定义，转为数值时为NaN。典型用法是：

（1）变量被声明了，但没有赋值时，就等于undefined。

（2) 调用函数时，应该提供的参数没有提供，该参数等于undefined。

（3）对象没有赋值的属性，该属性的值为undefined。

（4）函数没有返回值时，默认返回undefined。

3.undeclared：js语法错误，没有申明直接使用，js无法找到对应的上下文。

14.列出JS基本和非基本数据类型之间的一些区别？
1.目前JS中有6种基本数据类型: Undefined、Null、Boolean、Number、Symbol 和 String。还有1种复杂的数据类型————Object，Object本质上是由一组无序的名值对组成的。Object、Array和Function则属于引用类型。

2.基本数据类型是不可变的，而非基本数据类型是可变的。

3.基本数据类型是不可变的，因为它们一旦创建就无法更改，但非基本数据类型刚可更改，意味着一旦创建了对象，就可以更改它。

4.将基本数据类型与其值进行比较，这意味着如果两个值具有相同的数据类型并具有相同的值，那么它们是严格相等的。

5.非基本数据类型不与值进行比较。例如，如果两个对象具有相同的属性和值，则它们严格不相等。

15. 如何在现有函数中添加新属性
    只需给现有函数赋值，就可以很容易地在现有函数中添加新属性。例如，现有一个对象person，通过下面的代码来为 person 添加新的属性：

person.country= “India”;
16. JS中的深拷贝与浅拷贝的区别？
    深拷贝递归地复制新对象中的所有值或属性，而拷贝只复制引用。

在深拷贝中，新对象中的更改不会影响原始对象，而在浅拷贝中，新对象中的更改，原始对象中也会跟着改。

在深拷贝中，原始对象不与新对象共享相同的属性，而在浅拷贝中，它们具有相同的属性。

17. 如何在JavaScript中每x秒调用一个函数
    在JS中，咱们使用函数 setInterval() 在每x秒内调用函数。如：

setInterval(function (){ alert("Hello"); }, 3000);
18. 解释一下JS的展开操作符？
    展开运算符在需要多个参数/变量/元素的位置展开表达式，它用三个点（...）。如：

var mid = [3, 4];

var newarray = [1, 2, ...mid, 5, 6];

console.log(newarray);

// [1, 2, 3, 4, 5, 6]
19. JS中的宿主对象与原生对象有何不同？
    宿主对象:这些是运行环境提供的对象。这意味着它们在不同的环境下是不同的。例如，浏览器包含像windows这样的对象，但是Node.js环境提供像Node List这样的对象。

原生对象:这些是JS中的内置对象。它们也被称为全局对象，因为如果使用JS，内置对象不受是运行环境影响。

20. 解释JS中的高阶函数？
    高阶函数是JS函数式编程的最佳特性。它是以函数为参数并返回函数作为结果的函数。一些内置的高阶函数是map、filter、reduce 等等。

21. JS 中 == 和 === 区别是什么？
    1、对于string,number等基础类型，==和===有区别

1）不同类型间比较，==之比较“转化成同一类型后的值”看“值”是否相等，===如果类型不同，其结果就是不等。
2）同类型比较，直接进行“值”比较，两者结果一样。

2、对于Array,Object等高级类型，==和===没有区别

进行“指针地址”比较。

3、基础类型与高级类型，==和===有区别

1）对于==，将高级转化为基础类型，进行“值”比较。
2）因为类型不同，===结果为false。

22. JS中的匿名函数是什么？
    匿名函数：就是没有函数名的函数，如：

(function(x, y){
alert(x + y);  
})(2, 3);
这里创建了一个匿名函数(在第一个括号内)，第二个括号用于调用该匿名函数，并传入参数。

23. 是否可以在JS中执行301重定向？
    JS完全运行在客户端上。301是服务器作为响应发送的响应代码。因此，在JS中不可能执行301重定向。

24. 解释JS中的事件冒泡和事件捕获
    事件捕获和冒泡: 在html DOM API中，有两种事件传播方法，它们决定了接收事件的顺序。两种方法是事件冒泡和事件捕获。第一个方法事件冒泡将事件指向其预期的目标，第二个方法称为事件捕获，其中事件向下到达元素。

事件捕获

捕获过程很少被使用，但是当它被使用时，它被证明是非常有用的。这个过程也称为滴流模式。在这个过程中，事件首先由最外层的元素捕获，然后传播到最内部的元素。例如:

<div>
  <ul>
    <li></li>
  </ul>
</div>
从上面的示例中，假设单击事件发生在li元素中，在这种情况下，捕获事件将首先处理div，然后处理ul，最后命中目标元素li。

事件冒泡

冒泡的工作原理与冒泡类似，事件由最内部的元素处理，然后传播到外部元素。

<div>
  <ul>
    <li></li>
  </ul>
</div>
从上面的例子中，假设click事件确实发生在冒泡模型中的li元素中，该事件将首先由li处理，然后由ul处理，最后由div元素处理。

24. 如何将文件的所有导出作为一个对象？
    import * as objectname from ‘./file.js’用于将所有导出的成员导入为对象。 可以使用对象的点（.）运算符来访问导出的变量或方法，如：

objectname.member1;
objectname.member2;
objectname.memberfunc();
25. 解释一下什么是箭头函数？
    箭头函数是在es6或更高版本中编写函数表达式的简明方法。箭头函数不能用作构造函数，也不支持this，arguments，super或new.target关键字，它最适合非方法函数。 通常，箭头函数看起来像 const function_name =（）=> {}。

const greet=()=>{console.log('hello');}
greet();
25 解释 JS 中的函数提升
JS允许将声明移动到顶部的默认行为称为提升。JS中创建函数的两种方法是函数声明和函数表达式。

函数声明

具有特定参数的函数称为函数声明，在JS中创建变量称为声明。如：

hoisted(); // logs "foo"

function hoisted() {
console.log('foo');
}
函数表达式

当使用表达式创建函数时，称为函数表达式。如：

notHoisted(); // TypeError: notHoisted is not a function

var notHoisted = function() {
console.log('bar');
};
26. module.exports 和 exports 之间有什么区别？
    module和exports是Node.js给每个js文件内置的两个对象。可以通过console.log(module)和console.log(exports)打印出来。如果你在main.js中写入下面两行，然后运行$ node main.js:

console.log(exports);//输出：{}
console.log(module);//输出：Module {..., exports: {}, ...} （注：...代表省略了其他一些属性）
从打印咱们可以看出，module.exports和exports一开始都是一个空对象{}，实际上，这两个对象指向同一块内存。这也就是说module.exports和exports是等价的（有个前提：不去改变它们指向的内存地址）。

例如：exports.age = 18和module.export.age = 18，这两种写法是一致的（都相当于给最初的空对象{}添加了一个属性，通过require得到的就是{age: 18}）。

27. import 和 exports 是什么？
    import和exports 帮助咱们编写模块化的JS代码。使用import和exports，咱们可以将代码分割成多个文件。import只允许获取文件的某些特定变量或方法。可以导入模块导出的方法或变量。

//index.js

import name,age from './person';

console.log(name);
console.log(age);

//person.js

let name ='Sharad', occupation='developer', age =26;

export { name, age};
28. 列出一些单元测试框架
    下面是一些最流行的JS单元测试框架:

Unit.js

Jasmine

Karma

Chai

AVA

Mocha

JSUnit

QUnit

Jest

29. JS中有哪些不同类型的弹出框可用
    在JS中有三种类型的弹出框可用，分别是：

Alert

Confirm

Prompt

30. 如何将 JS 日期转换为ISO标准
    toISOString() 方法用于将js日期转换为ISO标准。 它使用ISO标准将js Date对象转换为字符串。如：

var date = new Date();
var n = date.toISOString();
console.log(n);
// YYYY-MM-DDTHH:mm:ss.sssZ
31. 如何在JS中克隆对象
    Object.assign() 方法用于在JS中克隆对象。如：

var x = {myProp: "value"};
var y = Object.assign({}, x);
32. 如何在JS中编码和解码 URL
    encodeURI() 函数用于在JS中对URL进行编码。它将url字符串作为参数并返回编码的字符串。

注意： encodeURI()不会编码类似这样字符： / ? : @ & = + $ #，如果需要编码这些字符，请使用encodeURIComponent()。 用法：

var uri = "my profile.php?name=sammer&occupation=pāntiNG";
var encoded_uri = encodeURI(uri);
decodeURI() 函数用于解码js中的URL。它将编码的url字符串作为参数并返回已解码的字符串，用法：

var uri = "my profile.php?name=sammer&occupation=pāntiNG";
var encoded_uri = encodeURI(uri);
decodeURI(encoded_uri);
33. BOM 和 DOM 的关系
    BOM全称Browser Object Model，即浏览器对象模型，主要处理浏览器窗口和框架。

DOM全称Document Object Model，即文档对象模型，是 HTML 和XML 的应用程序接口（API），遵循W3C 的标准，所有浏览器公共遵守的标准。

JS是通过访问BOM（Browser Object Model）对象来访问、控制、修改客户端(浏览器)，由于BOM的window包含了document，window对象的属性和方法是直接可以使用而且被感知的，因此可以直接使用window对象的document属性，通过document属性就可以访问、检索、修改XHTML文档内容与结构。因为document对象又是DOM的根节点。

可以说，BOM包含了DOM(对象)，浏览器提供出来给予访问的是BOM对象，从BOM对象再访问到DOM对象，从而js可以操作浏览器以及浏览器读取到的文档。

34. JS中的substr()和substring()函数有什么区别
    substr() 函数的形式为substr(startIndex,length)。 它从startIndex返回子字符串并返回'length'个字符数。

var s = "hello";
( s.substr(1,4) == "ello" ) // true
substring() 函数的形式为substring(startIndex,endIndex)。 它返回从startIndex到endIndex - 1的子字符串。

var s = "hello";
( s.substring(1,4) == "ell" ) // true
35. 解释一下 "use strict" ?
    “use strict”是Es5中引入的js指令。 使用“use strict”指令的目的是强制执行严格模式下的代码。 在严格模式下，咱们不能在不声明变量的情况下使用变量。 早期版本的js忽略了“use strict”。

36.解释 JS 事件委托模型？
在JS中，有一些很酷的东西。其中之一是委托模型。当捕获和冒泡时，允许函数在一个特定的时间实现一个处理程序到多个元素，这称为事件委托。事件委托允许将事件侦听器添加到父节点而不是指定的节点。这个特定的侦听器分析冒泡事件，以找到子元素上的匹配项。'

2 说说写JavaScript的基本规范？
1) 不要在同一行声明多个变量
2) 使用 ===或!==来比较true/false或者数值
3) switch必须带有default分支
4) 函数应该有返回值
5) for if else 必须使用大括号
6) 语句结束加分号
7) 命名要有意义，使用驼峰命名法

3 jQuery使用建议
1) 尽量减少对dom元素的访问和操作
2) 尽量避免给dom元素绑定多个相同类型的事件处理函数，可以将多个相同类型事件
   处理函数合并到一个处理函数，通过数据状态来处理分支
3) 尽量避免使用toggle事件

4 Ajax使用
全称 ： Asynchronous Javascript And XML
所谓异步，就是向服务器发送请求的时候，我们不必等待结果，而是可以同时做其他的事情，等到有了结果它自己会根据设定进行后续操作，与此同时，页面是不会发生整页刷新的，提高了用户体验。
创建Ajax的过程：
1) 创建XMLHttpRequest对象（异步调用对象）

var xhr = new XMLHttpRequest();
2) 创建新的Http请求（方法、URL、是否异步）

xhr.open(‘get’,’example.php’,false);
3) 设置响应HTTP请求状态变化的函数。
   onreadystatechange事件中readyState属性等于4。响应的HTTP状态为200(OK)或者304(Not Modified)。
4) 发送http请求

xhr.send(data);
5) 获取异步调用返回的数据
   注意：
1) 页面初次加载时，尽量在web服务器一次性输出所有相关的数据，只在页面加载完成之后，用户进行操作时采用ajax进行交互。
2) 同步ajax在IE上会产生页面假死的问题。所以建议采用异步ajax。
3) 尽量减少ajax请求次数
4) ajax安全问题，对于敏感数据在服务器端处理，避免在客户端处理过滤。对于关键业务逻辑代码也必须放在服务器端处理。

5 JavaScript有几种类型的值？你能画一下他们的内存图吗？
基本数据类型存储在栈中，引用数据类型（对象）存储在堆中，指针放在栈中。
两种类型的区别是：存储位置不同；原始数据类型直接存储在栈中的简单数据段，占据空间小、大小固定，属于被频繁使用数据，所以放入栈中存储；引用数据类型存储在堆中的对象,占据空间大、大小不固定,如果存储在栈中，将会影响程序运行的性能
引用数据类型在栈中存储了指针，该指针指向堆中该实体的起始地址。当解释器寻找引用值时，会首先检索其在栈中的地址，取得地址后从堆中获得实体。

6 栈和堆的区别？
栈（stack）：由编译器自动分配释放，存放函数的参数值，局部变量等；
堆（heap）：一般由程序员分配释放，若程序员不释放，程序结束时可能由操作系统释放。

7 Javascript实现继承的几种方式
可以参考我的另一篇文章JavaScript实现类与继承的方法（全面整理）

8 Javascript创建对象的几种方式？
可以参考我的另一篇文章JavaScript实现类与继承的方法（全面整理）

9 Javascript作用链域
作用域链的原理和原型链很类似，如果这个变量在自己的作用域中没有，那么它会寻找父级的，直到最顶层。
注意：JS没有块级作用域，若要形成块级作用域，可通过（function（）｛｝）（）；立即执行的形式实现。

10 谈谈this的理解
1) this总是指向函数的直接调用者（而非间接调用者）
2) 如果有new关键字，this指向new出来的那个对象
3) 在事件中，this指向目标元素，特殊的是IE的attachEvent中的this总是指向全局对象window。

11 eval是做什么的？
它的功能是把对应的字符串解析成JS代码并运行；应该避免使用eval，不安全，非常耗性能（2次，一次解析成js语句，一次执行）。

12 什么是window对象? 什么是document对象?
window对象代表浏览器中打开的一个窗口。document对象代表整个html文档。实际上，document对象是window对象的一个属性。

13 null，undefined的区别？
null表示一个对象被定义了，但存放了空指针，转换为数值时为0。
undefined表示声明的变量未初始化，转换为数值时为NAN。
typeof(null) -- object;
typeof(undefined) -- undefined

14 写一个通用的事件侦听器函数(机试题)

15 ["1", "2", "3"].map(parseInt) 答案是多少？
[1,NaN,NaN]

解析：
Array.prototype.map()
array.map(callback[, thisArg])
callback函数的执行规则
参数：自动传入三个参数
currentValue（当前被传递的元素）；
index（当前被传递的元素的索引）；
array（调用map方法的数组）

parseInt方法接收两个参数
第三个参数["1", "2", "3"]将被忽略。parseInt方法将会通过以下方式被调用
parseInt("1", 0)
parseInt("2", 1)
parseInt("3", 2)

parseInt的第二个参数radix为0时，ECMAScript5将string作为十进制数字的字符串解析；
parseInt的第二个参数radix为1时，解析结果为NaN；
parseInt的第二个参数radix在2—36之间时，如果string参数的第一个字符（除空白以外），不属于radix指定进制下的字符，解析结果为NaN。
parseInt("3", 2)执行时，由于"3"不属于二进制字符，解析结果为NaN。

16 关于事件，IE与火狐的事件机制有什么区别？ 如何阻止冒泡？
IE为事件冒泡，Firefox同时支持事件捕获和事件冒泡。但并非所有浏览器都支持事件捕获。jQuery中使用event.stopPropagation()方法可阻止冒泡;（旧IE的方法 ev.cancelBubble = true;）

17 什么是闭包（closure），为什么要用它？
闭包指的是一个函数可以访问另一个函数作用域中变量。常见的构造方法，是在一个函数内部定义另外一个函数。内部函数可以引用外层的变量；外层变量不会被垃圾回收机制回收。
注意，闭包的原理是作用域链，所以闭包访问的上级作用域中的变量是个对象，其值为其运算结束后的最后一个值。
优点：避免全局变量污染。缺点：容易造成内存泄漏。
例子：


function makeFunc() {

    var name = "Mozilla";
 
    function displayName() {
 
        console.log(name); 
 
    }
 
    return displayName;

}

var myFunc = makeFunc();

myFunc();   //输出Mozilla


myFunc 变成一个 闭包。闭包是一种特殊的对象。它由两部分构成：函数，以及创建该函数的环境。环境由闭包创建时在作用域中的任何局部变量组成。在我们的例子中，myFunc 是一个闭包，由 displayName 函数和闭包创建时存在的 "Mozilla" 字符串形成。

18 javascript 代码中的"use strict";是什么意思 ? 使用它区别是什么？
除了正常模式运行外，ECMAscript添加了第二种运行模式：“严格模式”。
作用：
1) 消除js不合理，不严谨地方，减少怪异行为
2) 消除代码运行的不安全之处，
3) 提高编译器的效率，增加运行速度
4) 为未来的js新版本做铺垫。

19 如何判断一个对象是否属于某个类？
使用instanceof 即if(a instanceof Person){alert('yes');}

20 new操作符具体干了什么呢?
1) 创建一个空对象，并且 this 变量引用该对象，同时还继承了该函数的原型。
2) 属性和方法被加入到 this 引用的对象中。
3) 新创建的对象由 this 所引用，并且最后隐式的返回 this 。

21 Javascript中，执行时对象查找时，永远不会去查找原型的函数？
Object.hasOwnProperty(proName)：是用来判断一个对象是否有你给出名称的属性。不过需要注意的是，此方法无法检查该对象的原型链中是否具有该属性，该属性必须是对象本身的一个成员。

22 对JSON的了解？
全称：JavaScript Object Notation
JSON中对象通过“{}”来标识，一个“{}”代表一个对象，如{“AreaId”:”123”}，对象的值是键值对的形式（key：value）。JSON是JS的一个严格的子集，一种轻量级的数据交换格式，类似于xml。数据格式简单，易于读写，占用带宽小。
两个函数：
JSON.parse(str)
解析JSON字符串 把JSON字符串变成JavaScript值或对象
JSON.stringify(obj)
将一个JavaScript值(对象或者数组)转换为一个 JSON字符串
eval('('＋json＋')')
用eval方法注意加括号 而且这种方式更容易被攻击

23 JS延迟加载的方式有哪些？
JS的延迟加载有助与提高页面的加载速度。
defer和async、动态创建DOM方式（用得最多）、按需异步载入JS
defer：延迟脚本。立即下载，但延迟执行（延迟到整个页面都解析完毕后再运行），按照脚本出现的先后顺序执行。
async：异步脚本。下载完立即执行，但不保证按照脚本出现的先后顺序执行。

24 同步和异步的区别?
同步的概念在操作系统中：不同进程协同完成某项工作而先后次序调整（通过阻塞、唤醒等方式），同步强调的是顺序性，谁先谁后。异步不存在顺序性。
同步：浏览器访问服务器，用户看到页面刷新，重新发请求，等请求完，页面刷新，新内容出现，用户看到新内容之后进行下一步操作。
异步：浏览器访问服务器请求，用户正常操作，浏览器在后端进行请求。等请求完，页面不刷新，新内容也会出现，用户看到新内容。

25 什么是跨域问题 ，如何解决跨域问题?
可以参考我的另一篇文章什么是跨域以及几种简单解决方案

26 页面编码和被请求的资源编码如果不一致如何处理？
若请求的资源编码，如外引js文件编码与页面编码不同。可根据外引资源编码方式定义为 charset="utf-8"或"gbk"。
比如：http://www.yyy.com/a.html 中嵌入了一个http://www.xxx.com/test.js
a.html 的编码是gbk或gb2312的。 而引入的js编码为utf-8的 ，那就需要在引入的时候
<script src="http://www.xxx.com/test.js&quot; charset="utf-8"></script>

27 模块化开发怎么做？
模块化开发指的是在解决某一个复杂问题或者一系列问题时，依照一种分类的思维把问题进行系统性的分解。模块化是一种将复杂系统分解为代码结构更合理，可维护性更高的可管理的模块方式。对于软件行业：系统被分解为一组高内聚，低耦合的模块。
（1）定义封装的模块
（2）定义新模块对其他模块的依赖
（3）可对其他模块的引入支持。在JavaScript中出现了一些非传统模块开发方式的规范。 CommonJS的模块规范，AMD（Asynchronous Module Definition），CMD（Common Module Definition）等。AMD是异步模块定义，所有的模块将被异步加载，模块加载不影响后边语句运行。

28 AMD（Modules/Asynchronous-Definition）、CMD（Common Module Definition）规范区别？
AMD 是 RequireJS 在推广过程中对模块定义的规范化产出。CMD 是 SeaJS 在推广过程中对模块定义的规范化产出。
区别：
1) 对于依赖的模块，AMD 是提前执行，CMD 是延迟执行。不过 RequireJS 从 2.0 开始，也改成可以延迟执行（根据写法不同，处理方式不同）。
2) CMD 推崇依赖就近，AMD 推崇依赖前置。
3) AMD 的 API 默认是一个当多个用，CMD 的 API 严格区分，推崇职责单一。


// CMD

define(function(require, exports, module) {

    var a = require('./a')
 
    a.doSomething()
 
    // 此处略去 100 行
 
    var b = require('./b') // 依赖可以就近书写
 
    b.doSomething()

})

// AMD 默认推荐

define(['./a', './b'], function(a, b) { // 依赖必须一开始就写好

    a.doSomething();
 
    // 此处略去 100 行
 
    b.doSomething();

})


29 requireJS的核心原理是什么？（如何动态加载的？如何避免多次加载的？如何缓存的？）
核心是js的加载模块，通过正则匹配模块以及模块的依赖关系，保证文件加载的先后顺序，根据文件的路径对加载过的文件做了缓存。

30 call和apply
call（）方法和apply（）方法的作用相同，动态改变某个类的某个方法的运行环境。他们的区别在于接收参数的方式不同。在使用call（）方法时，传递给函数的参数必须逐个列举出来。使用apply（）时，传递给函数的是参数数组。

31 谈一谈你对ECMAScript6的了解

32 documen.write和 innerHTML的区别
document.write()只能重绘整个页面


setTimeout(function(){

       document.write('<p>5 secs later</p>');

}, 5000);


或


window.onload = function() { document.write("HI");


innerHTML可以重绘页面的一部分

33 回流与重绘
当渲染树中的一部分(或全部)因为元素的规模尺寸，布局，隐藏等改变而需要重新构建。这就称为回流(reflow)。每个页面至少需要一次回流，就是在页面第一次加载的时候。在回流的时候，浏览器会使渲染树中受到影响的部分失效，并重新构造这部分渲染树。完成回流后，浏览器会重新绘制受影响的部分到屏幕中，该过程成为重绘

34 DOM操作
（1）创建新节点
createDocumentFragment() //创建一个DOM片段
createElement() //创建一个具体的元素
createTextNode() //创建一个文本节点
（2）添加、移除、替换、插入
appendChild()
removeChild()
replaceChild()
insertBefore() //在已有的子节点前插入一个新的子节点
（3）查找
getElementsByTagName() //通过标签名称
getElementsByName() //通过元素的Name属性的值(IE容错能力较强，会得到一个数组，其中包括id等于name值的)
getElementById() //通过元素Id，唯一性

35 数组对象有哪些原生方法，列举一下
pop、push、shift、unshift、splice、reverse、sort、concat、join、slice、toString、indexOf、lastIndexOf、reduce、reduceRight
forEach、map、filter、every、some

36 那些操作会造成内存泄漏
全局变量、闭包、DOM清空或删除时，事件未清除、子元素存在引用

37 什么是Cookie 隔离？（或者：请求资源的时候不要带cookie怎么做）
通过使用多个非主要域名来请求静态文件，如果静态文件都放在主域名下，那静态文件请求的时候带有的cookie的数据提交给server是非常浪费的，还不如隔离开。因为cookie有域的限制，因此不能跨域提交请求，故使用非主要域名的时候，请求头中就不会带有cookie数据，这样可以降低请求头的大小，降低请求时间，从而达到降低整体请求延时的目的。同时这种方式不会将cookie传入server，也减少了server对cookie的处理分析环节，提高了server的http请求的解析速度。

38 响应事件
onclick鼠标点击某个对象；onfocus获取焦点；onblur失去焦点；onmousedown鼠标被按下

39 flash和js通过什么类如何交互?
Flash提供了ExternalInterface接口与JavaScript通信，ExternalInterface有两个方法，call和addCallback，call的作用是让Flash调用js里的方法，addCallback是用来注册flash函数让js调用。

40 Flash与Ajax各自的优缺点？
Flash：适合处理多媒体、矢量图形、访问机器。但对css、处理文本不足，不容易被搜索。
Ajax：对css、文本支持很好，但对多媒体、矢量图形、访问机器不足。

41 有效的javascript变量定义规则
第一个字符必须是一个字母、下划线（_）或一个美元符号（$）；其他字符可以是字母、下划线、美元符号或数字。

42 XML与JSON的区别？
1) 数据体积方面。JSON相对于XML来讲，数据的体积小，传递的速度更快些。
2) 数据交互方面。JSON与JavaScript的交互更加方便，更容易解析处理，更好的数据交互。
3) 数据描述方面。JSON对数据的描述性比XML较差。
4) 传输速度方面。JSON的速度要远远快于XML。

43 HTML与XML的区别？
（1）XML用来传输和存储数据，HTML用来显示数据；
（2）XML使用的标签不用预先定义
（3）XML标签必须成对出现
（4）XML对大小写敏感
（5）XML中空格不会被删减
（6）XML中所有特殊符号必须用编码表示
（7）XML中的图片必须有文字说明

44 渐进增强与优雅降级
渐进增强：针对低版本浏览器进行构建页面，保证最基本的功能，然后再针对高级浏览器进行效果、交互等改进，达到更好的用户体验。
优雅降级：一开始就构建完整的功能，然后再针对低版本浏览器进行兼容。

45 Web Worker和Web Socket？
web socket：在一个单独的持久连接上提供全双工、双向的通信。使用自定义的协议（ws://、wss://），同源策略对web socket不适用。
web worker：运行在后台的JavaScript，不影响页面的性能。
创建worker：var worker = new Worker(url);
向worker发送数据：worker.postMessage(data);
接收worker返回的数据：worker.onmessage
终止一个worker的执行：worker.terminate();

46 JS垃圾回收机制？
1) 标记清除：
   这个算法把“对象是否不再需要”简化定义为“对象是否可以获得”。
   这个算法假定设置一个叫做根（root）的对象（在Javascript里，根是全局对象）。定期的，垃圾回收器将从根开始，找所有从根开始引用的对象，然后找这些对象引用的对象。从根开始，垃圾回收器将找到所有可以获得的对象和所有不能获得的对象。

2) 引用计数：
   这是最简单的垃圾收集算法。此算法把“对象是否不再需要”简化定义为“对象有没有其他对象引用到它”。如果没有引用指向该对象（零引用），对象将被垃圾回收机制回收。
   该算法有个限制：无法处理循环引用。两个对象被创建，并互相引用，形成了一个循环。它们被调用之后不会离开函数作用域，所以它们已经没有用了，可以被回收了。然而，引用计数算法考虑到它们互相都有至少一次引用，所以它们不会被回收。

47 web应用从服务器主动推送data到客户端的方式？
JavaScript数据推送：commet（基于http长连接的服务器推送技术）。
基于web socket的推送：SSE（server-send Event）

48 如何删除一个cookie？
1） 将cookie的失效时间设置为过去的时间（expires）


document.cookie = ‘user=’+ encodeURIComponent(‘name’) + ';

expires=’+ new Date(0);
2） 将系统时间设置为当前时间往前一点时间


var data = new Date();

date.setDate(date.getDate()-1);
49 attribute与property的区别？
attribute是dom元素在文档中作为html标签拥有的属性
property是dom元素在js中作为对象拥有的属性。
所以，对于html的标准属性来说，attribute和property是同步的，是会自动更新的。但对于自定义属性，他们不同步。

50 Ajax请求的页面历史记录状态问题？
（1）通过location.hash记录状态，让浏览器记录Ajax请求时页面状态的变化。
（2）通过HTML5的history.pushstate，来实现浏览器地址栏的无刷新改变。