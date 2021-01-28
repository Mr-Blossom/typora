# JavaScript

## 	-简单了解JavaScript

### 		1.定义

​				它是一门运行在浏览器前端的脚本语言。

### 		2.编写位置

#### 			a）编写到标签的指定属性中

```html
<button onclick="alert('hello');">我是按钮</button>
<a href="javascript:alert('aaa');">超链接</a>
```

#### 			b）编写到script标签中

```html
<script type="text/javascript">
				//编写js代码
</script>
```

#### 			c）将代码编写到外部的js文件中，然后通过标签将其引入 

<script type="text/javascript" src="文件路径"></script>

### 		3.输出语句

| 语句             | 输出平台                   |
| ---------------- | -------------------------- |
| alert()          | 浏览器弹窗                 |
| document.write() | 页面body内容中显示         |
| console.log()    | 开发者工具中的控制台中显示 |

![](https://raw.githubusercontent.com/Mr-Blossom/typora/typora/typora_img%E8%BE%93%E5%87%BA%E8%AF%AD%E5%8F%A5.png)

| alert                                                        | document.write                                               | console.log                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![](https://raw.githubusercontent.com/Mr-Blossom/typora/typora/typora_imgalert.png) | ![](https://raw.githubusercontent.com/Mr-Blossom/typora/typora/typora_imgdocument.png) | ![](https://raw.githubusercontent.com/Mr-Blossom/typora/typora/typora_imgconsole.png) |

### 		4.基本语法

#### 			a)注释分为单行注释和多行注释

​					单行注释：

//注释内容

​					多行注释：

```html
/*
	注释内容
*/
```

#### 			b)JS中严格区分大小写

#### 			c)JS中每条语句以分号结尾

#### 			d)JS中会自动忽略多个空格和换行，所以我们可以利用空格和换行对代码进行格式化。

#### 			e)JS中的字面量与变量

- 字面量
  - 字面量实际上就是一些固定的值，比如 1 2 3 4 true false null NaN "hello" ，字面量都是不可以改变的。
  - 由于字面量不是很方便使用，所以在JS中很少直接使用字面量。
- 变量
  - 变量可以用来保存字面量，并且可以保存任意的字面量
  - 一般都是通过变量来使用字面量，而不直接使用字面量，而且也可以通过变量来对字面量进行一个描述
  - 声明变量
    - 使用var关键字来声明一个变量
      var a;
      var b;
      var c;
  - 为变量赋值
    - a = 1;
      b = 2;
      c = 3;
  - 声明和赋值同时进行 
    - var d = 456;
      var e = 789;

- 标识符
	- 在JS中所有的可以自主命名的内容，都可以认为是一个标识符，是标识符就应该遵守标识符的规范。
	- 比如：变量名、函数名、属性名
	- 规范：
		1.标识符中可以含有【字母、数字、_、$】
		2.标识符唯一不能以数字开头
		3.标识符不能是JS中的关键字和保留字
		4.标识符一般采用驼峰命名法（首字母小写，其余单词只有首字母大写）
			xxxYyyZzz

## 	-JavaScript数据类型与转换

### 		1.数据类型

​				数据类型共有6种，其中基本数据类型包含5种，引用数据类型包含1种。

| 数据类型                    | 说明                                                         | 使用typeof运算符检查字符串时的返回值 |
| :-------------------------- | :----------------------------------------------------------- | :----------------------------------- |
| String 字符串               | - JS中的字符串需要使用引号引起来双引号或单引号都<br/>- 在字符串中**使用\作为转义字符**<br/>				\\'  ==> '<br/>				\\"  ==> "<br/>				\n  ==> 换行<br/>				\t  ==> 制表符<br/>				\\\  ==> \ | "string"                             |
| Number 数值                 | - JS中所有的整数和浮点数都是Number类型<br/>			- 特殊的数字<br/>				  Infinity 正无穷<br/>				  -Infinity 负无穷<br/>				  NaN 非法数字（Not A Number）<br/>			- 其他进制的数字的表示：<br/>				  0b 开头表示二进制，但不是所有的浏览器都支持<br/>				  0 开头表示八进制<br/>				  0x 开头表示十六进制 | "number"（包括NaN 和 Infinity）      |
| Boolean 布尔值              | - 布尔值主要用来进行逻辑判断，布尔值只有两个<br/>			- true 逻辑的真<br/>			- false 逻辑的假 | "boolean"                            |
| Null 空值                   | - 空值专门用来表示为空的对象，Null类型的值只有一个null       | "object"                             |
| Undefined 未定义            | - 如果声明一个变量但是没有为变量赋值此时变量的值就是undefined<br/>- 该类型的值只有一个 undefined | "undefined"                          |
| Object 对象（引用数据类型） |                                                              |                                      |

### 		2.数据类型转换

​				所谓类型转换就是指将其他的数据类型，转换为String Number 或 Boolean。

|        | 转换为String                                                 | 转换为Number                                                 | 转换为布尔值                                                 |
| ------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 方式一 | （强制类型转换）：<br/>	- 调用被转换数据的***toString()**方法*<br/>	     - 例子：<br/>					var a = 123;<br/>					a = a.toString();<br/>	- 注意：这个方法不适用于null和undefined<br/>		由于这两个类型的数据中没有方法，所以调用<br/>         toString()时会报错 | （强制类型转换）：<br/>	- 调用***Number()*函数**<br/>		- 例子：<br/>					var s = "123";<br/>					s = Number(s);<br/>- 注意：转换的情况有以下四种<br/>1.字符串 --> 数字<br/>   如果字符串是一个合法的数字，则直接转换为对应的数字<br/>   如果字符串是一个非法的数字，则转换为NaN<br/>   如果是一个空串或纯空格的字符串，则转换为0<br/>2.布尔值 --> 数字<br/>	- true转换为1<br/>	- false转换为0<br/>3.空值 --> 数字<br/>	- null转换为0<br/>4.未定义 --> 数字<br/>	- undefined 转换为NaN | （强制类型转换）：<br/>	- 使用***Boolean()***函数<br/>		- 例子：<br/>			var s = "false";<br/>			s = Boolean(s); //true<br/>- 注意：转换的情况也有4种<br/>1.字符串 --> 布尔<br/>- 除了空串其余全是true<br/>2.数值 --> 布尔<br/>- 除了0和NaN其余的全是true<br/>3.null、undefined ---> 布尔<br/>- 都是false<br/>4.对象 ---> 布尔<br/>- 都是true |
| 方式二 | （强制类型转换）：<br/>	- 调用***String()函数***<br/>		- 例子：<br/>					var a = 123;<br/>					a = String(a);<br/>	- 原理：对于Number Boolean String都会调用<br/>         他们的toString()方法来将其转换为字符串，<br/>		 对于null值，直接转换为字符串"null"。<br/>         对于undefined直接转换为字符串"undefined" | （强制类型转换）：<br/>	- 调用***parseInt()或parseFloat()***<br/>	- 这两个函数专门用来将一个**字符串转换为数字**的<br/>		*- parseInt()*<br/>			- 可以将一个字符串中的有效的整数位提取出来，并转换为Number<br/>			- 例子：<br/>						var a = "123.456px";<br/>						a = parseInt(a); //123<br/>- 如果需要可以在parseInt()中指定一个第二个参数，来指定进制	<br/>		- parseFloat()<br/>			- 可以将一个字符串中的有效的小数位提取出来，并转换为Number<br/>			- 例子：<br/>						var a = "123.456px";<br/>						a = parseFloat(a); //123.456 | （隐式类型转换）：	<br/>- 为任意的数据类型做**两次非运算**，即可将其转换为布尔值<br/>- 例子：	<br/>					var a = "hello";<br/>					a = !!a; //true |
| 方式三 | （隐式的类型转换）: *****<br/>	- 为任意的数据类型 ***+""***<br/>		- 例子：<br/>					var a = true;<br/>					a = a + "";<br/>	- 原理：和String()函数一样 | （隐式的类型转换）：<br/>	- 使用**一元的+**来进行隐式的类型转换<br/>		 - 例子：<br/>					var a = "123";<br/>					a = +a;<br/>	- 原理：和Number()函数一样 |                                                              |



## 	-JavaScript的运算符与优先级

## 	-JavaScript的流程控制语句

## 	-JavaScript的运算符

## 	-JavaScript中的对象与函数

## 	-JavaScript的字符串和正则表达式

# DOM

## 	-简单认识DOM

## 	-DOM查询

## 	-DOM操作样式

## 	-事件&拖拽

# BOM

## 	-简单认识BOM

## 	-定时调用&延时调用

## 	-定时器

## 	-轮播图

# Exercises





