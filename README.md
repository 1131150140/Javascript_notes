4.什么是语义化的HTML?
直观的认识标签 对于搜索引擎的抓取有好处，用正确的标签做正确的事情！
html语义化就是让页面的内容结构化，便于对浏览器、搜索引擎解析；
在没有样式CCS情况下也以一种文档格式显示，并且是容易阅读的。搜索引擎的爬虫依赖于标记来确定上下文和各个关键字的权重，利于 SEO。
使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。

9.如何实现浏览器内多个标签页之间的通信?
调用localstorge、cookies等本地存储方式

“原型链”的作用是，读取对象的某个属性时，JavaScript 引擎先寻找对象本身的属性，如果找不到，就到它的原型去找，如果还是找不到，就到原型的原型去找。如果直到最顶层的Object.prototype还是找不到，则返回undefined。

例举3种强制类型转换和2种隐式类型转换?
强制（parseInt,parseFloat,number）隐式（== – ===）

构造函数的特点有两个
1.函数体内部使用了this关键字，代表了所要生成的对象实例。
2.生成对象的时候，必需用new命令，调用Vehicle函数。

具体来说，AJAX包括以下几个步骤。
创建AJAX对象
发出HTTP请求
接收服务器传回的数据
更新网页数据


5.谈谈This对象的理解。
this的四种使用场景：
1.new 调用 。绑定到新创建的对象上
2.call。apply（或者bind）调用，绑定到指定的对象 供爷法则
3.对象调用，绑定到对象
4.普通函数调用，非严格模式绑定到全局对象window 严格模式绑定到underfined

4.ajax请求时，如何解释json数据
使用parse更靠谱;

跨域分为两种，一种是跨域请求，另一种访问跨域的页面，跨域请求可以通过CORS/JSONP等方法进行访问，跨域的页面主要通过postMesssage的方式。


2.前端页面有哪三层构成，分别是什么?作用是什么?
结构层 Html 表示层 CSS 行为层 js;

闭包是指有权访问另一个
函数作用域中的变量的函数。
闭包主要与变量的作用域和变量的生命周期息息相关 
作用域之的是：闭包能够访问别的函数中的局部变量
声明周期指：函数执行完后，局部变量内存会被销魂，用了必要之后之后。就不会被销毁
闭包的更多作用： 1.可以减少声明全局变量 2.延长局部变量的生命周期
作用域链的配置机制导致了一个副作用，闭包只能取得包含函数中任何变量的最后一个值

单独使用原型链继承的问题：
1.包含引用类型的原型属性会被所有实例共享
2.在创建子类型的实例时，不能向超类型的构造函数传递参数

借用构造函数的优势：
1.可以在子类型构造函数中向父类构造函数传递参数
借用构造函数的劣势
方法都在构建函数里面编写，因此函数复用就无从说起了

组合继承:指的是将原型链和借用构造函数的技术组合到一块，从而发挥二者之长的一种继承模式，其背后的思路是使用原型链实现对原型属性和方法的继承，而通过借用构造函数来实现对实例属性的继承。

我们把有权访问私有变量和私有函数的共有方法称为特权方法

原型对象的问题在于当原型中存在引用类型的变量，会被所有实例共享。
构造函数创建对象的问题在于每个方法都要在实例中重新创建一遍，占内存，代码不复用
组合使用构造模式与原型模式的优点：构造函数模式用于定义实例属性，而原型模式用于定义方法和共享的属性

1.typeof null === 'object'
2.维数组转换成真数组的方法  Array.prototype.slice.call(arguments)  Array.from()
3.null指空值 undefined指没有值
4.object.preventExtensions(..)禁止扩展
5.密封：密封之后不能添加新属性，不能重新配置或者删除现有属性（可以修改属性的值）
6.冻结：在密封的前提下属性还不可修改
7.object.keys()会返回一个数组，包括所有可枚举属性。
8.Object.getOwnpropertyNames()会返回一个数组，包括所有属性，无论他们是否可枚举
9.in和hasOwnproperty（）的区别在于是否查找原型链，然而object.keys 和object.getOwnPropertyNames()都只会查找直接包含的属性


es5通过object.create()方法规范了原型式继承。这个方法接受两个参数；1个用作新对象原型的对象和一个为新对象定义额外属性的对象。在传入一个参数的情况下，object.create（）和object（）方法的行为相同

严格模式下，不能通过脚本访问arguments.call，访问这个属性会导致错误。不过，可以使用命名函数表示来达成相同的结果。
例如：
var factorial = {function f(num) {
	if (num <= 1) {
		return 1;
	} else {
		return num * f(num-1);
	}
}}


要注意有一个小小的例外：即便属性是 configurable:false，我们还是可以
把 writable 的状态由 true 改为 false，但是无法由 false 改为 true。

禁止扩展使用object.preventExtensions()
密封：Object.seal()  密封之后不仅不能添加新属性，也不能重新配置或者删除任何现有属性，虽然可以修改属性的值
冻结：冻结后属性的值都不能修改了

高阶函数
高阶函数是指至少满足下列条件之1的函数
1.函数可以作为参数被传递
2.函数可以作为返回值返回

单一职责原则  原则体现:1个方法只做一件事情
SRP原则的优缺点
SRP原则的有点事降低了单个类或者对象的复杂度，按照职业把对象分解成更小的粒度，这有助于代码的复用，也有利于进行单元测试。当一个职业需要变更的时候，不会影响到其他的职责。
单SRP原则也有一些缺点，最明显的是会增加编写代码的复杂度。当我们按照职责把对象分解成更小的粒度之后。实际上也增大了这些对象之间相互联系的难度。

最小知识原则 最小知识原则要求我们在设计程序时，应当尽量禁烧对象之间的交互，如果两个对象之间不必彼此通信，那么这两个对象句不要发生直接的相互联系。常见的做法是引入一个第三者对象，来承担这些对象之间的通信作用。如果一些对象需要向另一些对象发起请求，可以通过第三者对象来转发这些请求。

开放和封闭原则：
当需要改变一个程序的功能或者给这个程序添加新功能的时候，可以使用添加代码的方式，但是不允许改动程序的源代码


代码重构：
1.提炼函数  1.避免出现超大函数 2独立出来的函数有助于代码复用  3独立出来的函数更容易被复写  4.独立出来的函数如果拥有一个良好的命名。他本身就起到了注释的作用
2.合并重复的条件片段
3.把条件分支语句提炼成函数
4.合理使用循环
5.提前让函数退出代替嵌套条件分支
6.传递对象参数代替过长的参数列表
7.尽量减少参数数量
8.少用三目运算符
9.合理的使用链式调用
10.分解大型类
11.用return 退出多重循环

函数节流
分时函数
惰性加载函数

http://caibaojian.com/javascript-api-collection.html  常用dom操作



性能方面：
1、避免全局查找
2、避免with语句
3.避免不必要的属性查找
4.优化循环
5.避免双重解释  eval（alert('hello world')）;  var sayHi = new Function(alert('hello world')); setTimeout(alert('hello world'),400)
6.switch语句较快
7.最小化语句数 多个变量声明  插入迭代值 使用数组和对象字面量
8.最小化现场更新 使用代码片段拼接  innerHTML插入

Nan与任何值都不相等，包括NaN自身  isNan字符串会返回true

isPrototypeOf(object)；用于检查传入的对象是否是传入对象的原型

propertyIsEnumerable()用于检查给定的属性是否能够使用for-in语句来枚举

toString()返回对象的字符串表示

延长作用域链：try-catch语句的catch块  with语句

基本数据类型保存在栈内存中。引用类型保存在堆内存中  从一个变量向另一个变量赋值引用类型的值，赋值的其实是指针，因此两个变量最终都指向同一个对象

确认基本数据类型用typeof  确定引用类型用instanceof

垃圾收集： 1.标记清除2.引用计数

【】代表是使用变量来访问属性

push()方法可以接收任意数量的参数，把它们逐个添加到数组末尾，并返回修改后数组的长度

pop()方法则从数组末尾移除最后一项，减少数组的length 值，然后返回移除的项。

因此要模拟队列只需一个从数组前端取得项的方法。实现这一操作的数组方法就是shift()，它能够移
除数组中的第一个项并返回该项，同时将数组长度减1。

unshift它能在数组前端添加任意个项并返回新数组的长度。

迭代方法：
every（）:对数组的每一项运行给定函数，返回该函数对每一项都返回true，则返回true
filter（）:对数组中的每一项运行给定函数，返回该函数会返回true的数组
forEach（）：对数组中国的每一项运行给定函数，这个方法没有返回值
map()：对数组中国的每一项运行给定函数，返回每次函数调用的结果组成的数组
some（）对数组中国的每一项运行给定函数，如果该函数对任一项返回true，则会返回true

归并方法：reduce 和 reduceRight

属性修饰符：
configurable:表示能否通过delete删除属性从而重新定义属性，能否修改属性的特性，或者能否把属性修改为访问器属性。
enumerable：表示能否通过for-in循环返回属性。像前面例子中那样直接在对象还是那个定义的属性。它们的这个特性默认值为true
writable:表示能否修改属性的值，像前面例子中那样直接在对象上定义的属性
value：包含这个属性的数据值，读取属性值的时候，从这个位置读取值的时候。

读取属性的特性：使用Object.getOwnPropertyDescriptor()方法。可以取得给定属性的描述符，这个方法接受2个参数
Object.getOwnPropertyDescriptor('book', '_year');

使用hasOwnProperty()方法可以检测一个属性是存在于实例中，还是存在于原型中

in 操作符只要通过对象能够访问到属性就返回true

如何判断属性是在原型中in返回true hasownProperty为false

要取得对象上所有可枚举的实例属性，可以使用Object.keys（）方法

如果你想要得到所有实例属性，无论它是否可枚举，都可以使用Object.getOwnPropertyNames();

全局变量不能通过delete操作符删除，而直接在window对象上的定义的属性可以：

使用location.replace（）之后，用户不能回到前一个页面。也不会生成新的历史记录

我们要编写的脚本将主要检测五大呈现引擎：IE、Gecko、WebKit、KHTML 和Opera。
客户端检测方法：能力检测   怪癖检测  用户代理检测

IE4 最早为document 对象引入了readyState 属性。然后，其他浏览器也都陆续添加这个属性，
最终HTML5 把这个属性纳入了标准当中。Document 的readyState 属性有两个可能的值：
? loading，正在加载文档；
? complete，已经加载完文档。

XDM指的是在来自不同域的页面间传递消息.XDM 的核心是postMessage()方法。
能够在不加载新页面的情况下改变浏览器的URL 。为此， 需要使用
history.pushState()方法，该方法可以接收三个参数：状态对象、新状态的标题和可选的相对URL。

其他跨域技术：1.图片ping 2jsonp 3.comet 4cors

单向通信：使用sse  双向通信：websockets

不可扩展的对象，不允许给对象添加新的属性或方法。
密封的对象，也是不可扩展的对象，不允许删除已有的属性和方法。
冻结的对象，也是密封的对象，不允许重写对象的成员


四、关于worker
我们可以做什么：
　　1.可以加载一个JS进行大量的复杂计算而不挂起主进程，并通过postMessage，onmessage进行通信
　　2.可以在worker中通过importScripts(url)加载另外的脚本文件
　　3.可以使用 setTimeout(), clearTimeout(), setInterval(), and clearInterval()
　　4.可以使用XMLHttpRequest来发送请求
　　5.可以访问navigator的部分属性
局限性：
　　1.不能跨域加载JS
　　2.worker内代码不能访问DOM
　　3.各个浏览器对Worker的实现不大一致，例如FF里允许worker中创建新的worker,而Chrome中就不行
　　4.IE这个新特性

词法作用域是在写代码或者定义时确定的，而动态作用域是在运行时确定的（this也是！）。
词法作用域关注函数在何处声明，而动态作用域关注函数从何处调用。


http://caibaojian.com/css3/css3-quicksearch.htm css文档

严格模式下，arguments对象是一个只读对象，修改它是无效的，但不会报错。

在构建静态版本时 *不要使用 *state ** 。state 只用于交互，也就是说，数据可以随时被改变。
让我们仔细分析每一个数据，弄清楚哪一个是 state(状态) 。请简单地提出有关每个数据的 3 个问题：
1.是否通过 props(属性) 从父级传入？ 如果是这样，它可能不是 state(状态) 。
2.是否永远不会发生变化？ 如果是这样，它可能不是 state(状态)。
3.是否可以由组件中其他的 state(状态) 或 props(属性) 计算得出？如果是这样，则它不是 state(状态)。

总结与 rem 差异 em
1.rem 单位翻译为像素值是由 html 元素的字体大小决定的。 此字体大小会被浏览器中字体大小的设置影响，除非显式重写一个具体单位。

2.em 单位转为像素值，取决于他们使用的字体大小。 此字体大小受从父元素继承过来的字体大小，除非显式重写与一个具体单位。

state 的主要作用是用于组件保存、控制、修改自己的可变状态。state 在组件内部初始化，可以被组件自身修改，而外部不能访问也不能修改。你可以认为 state 是一个局部的、只能被组件自身控制的数据源。state 中状态可以通过 this.setState 方法进行更新，setState 会导致组件的重新渲染。

props 的主要作用是让使用该组件的父组件可以传入参数来配置该组件。它是外部传进来的配置参数，组件内部无法控制也无法修改。除非外部组件主动传入新的 props，否则组件的 props 永远保持不变。

state 和 props 有着千丝万缕的关系。它们都可以决定组件的行为和显示形态。一个组件的 state 中的数据可以通过 props 传给子组件，一个组件可以使用外部传入的 props 来初始化自己的 state。但是它们的职责其实非常明晰分明：state 是让组件控制自己的状态，props 是让外部对组件自己进行配置。

如果你觉得还是搞不清 state 和 props 的使用场景，那么请记住一个简单的规则：尽量少地用 state，尽量多地用 props。

new后的流程
1.创建一个空对象，作为将要返回的对象实例
2.将这个空对象的原型，指向构造函数的prototype属性
3.将这个空对象赋值给函数内部的this关键字
4.开始执行构造函数内部的代码


让我们来看看每一条，找出哪一个是 state。每个数据只要考虑三个问题：

它是通过 props 从父级传来的吗？如果是，他可能不是 state。
它随着时间推移不变吗？如果是，它可能不是 state。
你能够根据组件中任何其他的 state 或 props 把它计算出来吗？如果是，它不是 state。


词法作用域是在写代码或者定义时确定的，而动态作用域是在运行时确定的（this也是！）。
词法作用域关注函数在何处声明，而动态作用域关注函数从何处调用。

当父元素没有边框border时，设置第一个子元素的margin-top值的时候，会出现margin-top值加在父元素上的现象，解决方法有四个：
（4）父元素加前置内容生成。（推荐）
.parent {
     width : 500px;
     height : 500px;
     background-color : red;       
}
.parent : before {
     content : " ";
     display : table;
}

标准盒子模型与IE模型之间的差异：

　　标准的盒子模型就是上述介绍的那种，而IE模型更像是 box-sizing : border-box; 其内容宽度还包含了border和padding。解决办法就是：在html模板中加doctype声明。


父元素与子元素之间的margin-top问题
1、修改父元素的高度，增加padding-top样式模拟（padding-top：1px；常用） 
2、为父元素添加overflow：hidden；样式即可（完美） 
3、为父元素或者子元素声明浮动（float：left；可用） 
4、为父元素添加border（border:1px solid transparent可用） 
5、为父元素或者子元素声明绝对定位



