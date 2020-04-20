# JavaScript

## JavaScript发展历史(js)

1.  1994年，网景公司(Netscape)发布了Navigator浏览器0.9版，这是世界上第一款比较成熟的网络浏览器，轰动一时。但是这是一款名副其实的浏览器--只能浏览页面，浏览器无法与用户互动,当时解决这个问题有两个办法，一个是采用现有的语言,许它们直接嵌入网页。另一个是发明一种全新的语言。
    liveScript==>javaScript==>ECMAscript
    
2.  1995年Sun公司将Oak语言改名为Java，正式向市场推出。Sun公司大肆宣传，许诺这种语言可以"一次编写，到处运行"(Write Once, Run Anywhere)，它看上去很可能成为未来的主宰。

3.  网景公司动了心，决定与Sun公司结成联盟

4.  34岁的系统程序员Brendan Eich登场了。1995年4月，网景公司录用了他,他只用10天时间就把Javascript设计出来了。  （多态语言）

5. (1)借鉴C语言的基本语法; 

    (2)借鉴Java语言的数据类型和内存管理; 

    (3)借鉴Scheme语言，将函数提升到"第一等公民"(first class)的地位;

    (4)借鉴Self语言，使用基于原型(prototype)的继承机制。

![1532416730978](./assets/1532416730978.png)

### JavaScript是什么？

- JavaScript： 基于对象和事件驱动，运行在浏览器客户端的脚本语言。[js]
- js引擎: 执行js代码
- 渲染引擎: 内核

​     ✔ js的运行环境： 运行在浏览器端的一种语言
​     ✔ 最后将所有的js代码都要以对象的形式去执行，都要通过事件的方式去触发执行【DOM】

-  对象： 
   现实世界中的对象：  将任何一个具体的事物都是一个对象【万事万物皆对象】
   编程中的对象： 对现实中对象的抽象描述

### JavaScript能干什么？

-   常见的网页效果
-   与H5配合实现游戏【水果忍者： http://www.jq22.com/demo/html5-fruit-ninja/】
    canvas  +  JS  ====> 实现手机端游戏
-   实现应用级别的程序【 http://naotu.baidu.com】
-   实现统计效果【http://echarts.baidu.com/examples/】
-   地理定位等功能【http://lbsyun.baidu.com/jsdemo.htm#i4_5】
-   在线学编程【https://codecombat.163.com/play/】
-   js可以实现人工智能  【面部识别】

### JavaScript【JS】组成

![1496912475691](./assets/1496912475691.png)

-  ECMASCRIPT    定义了javascript的语法规范,描述了语言的基本语法和数据类型
-  BOM （Browser Object Model） 即浏览器对象模型。
   浏览器对象模型,通过BOM可以操作浏览器窗口，比如：弹出框、控制浏览器跳转、获取分辨率等
-  DOM (Document Object Model) 文档对象模型,一套操作页面元素的API,DOM可以把HTML看做是文档树，通过DOM提供的API可以对树上的节点进行操作 

## JavaScript书写位置

JS代码往那些，写到哪

### 内嵌式写法

```html
在html页面内部设置
  <script type="text/javascript">
		 js
  </script>

  注意：
  	  该标签可以放到head标签中或者body标签中
```

### 外联式写法[推荐写法]

```html
1. 新建js文件
2. 通过script标签引用到当前页面中
  <script type="text/javascript" src="test.js"></script>

注意：
	1. 不能将代码写到外联式标签中。
  2. 一个网页中可以同时调用多个外部js文件
  <script type="text/javascript" src="test.js"></script>
	<script type="text/javascript" src="test.js"></script>
	<script type="text/javascript" src="test.js"></script>
	<script type="text/javascript" src="test.js"></script>
```

### 行内式写法（不推荐）

```html
将js代码写到标签内部
<div onclick="js代码"></div>

注意：
	 onclick 是一个点击事件： 当点击div的时候，会触发该事件，执行该事件中的代码
```

## 注释

### 单行注释

用来描述下面一个或多行代码的作用

```javascript
// 这是一个变量
var name = 'zs';
```

### 多行注释

用来注释多条代码

```javascript
/*
var age = 18;
var name = 'zs';
console.log(name, age);
*/
```

## JavaScript中输入消息方式

```javascript
alert();//弹出框

document.write('<h1>我是一段文字</h1>');   在网页中输出信息

prompt("请输入姓名","测试");   //接收用户输入的【输入框】

confirm("确定不听课么");//确认框

console				 //在控制台中输出消息
console.log("普通的打印");
console.warn("警告的打印");
console.error("错误的打印");

总结：
	 1. 在js中如果希望输出一个具体的文本信息，必须带引号
   2. 在使用document.write();的时候，可以在方法内输出html标签，加引号。
```

如果我们使用prompt()方法让用户输入了数据，我们又想要把用户输入的数据保存起来，怎么办呢？

在JavaScript中有一种专门用于保存数据的语法：**变量**

## 变量（重点）

### 变量概念

 变量：  变量指的是在程序中保存数据的一个容器
 变量是计算机内存中存储数据的标识符，根据变量名称可以获取到内存中存储的数据
 简单说：用来保存数据

```javascript
 var 变量名 = 值;【值保存变量】
 var n = 2;
```

### 定义变量及赋值

```javascript
 定义变量
 		var  变量名；
 赋值
 		变量名 = 值;
    var 变量名 = 数据;
 总结：
	 1. 一个变量一次只能保存一个值
     2. 最后一次的赋值结果
     3. 变量是区分大小写（js区分大小写）
```

### 变量命名规范

- 规则    必须遵守的，不遵守的话 JS引擎 发现并报错

  1. 由字母(A-Za-z)、数字(0-9)、下划线(_)、美元符号( $ )组成，如：var usrAge, num01, _name
  2. 区分大小写 强调：JS 严格区分大小写 ，var app; 和 var App; 是两个变量
  3. 不能 以数字开头，或者汉字定义变量名
  4. 不能 是关键字、保留字 和 代码符号，例如：var、for、while、&, class
  5. 不能出现空格

- 规范  建议遵守的，不遵守的话 JS引擎 也不会报错

   	1. 变量名必须有意义
      	2. 遵守驼峰命名法。首字母小写，后面单词的首字母需要大写。

![1532417089018](./assets/1532417089018.png)

![1532417108565](./assets/1532417108565.png)

#### 课堂测试

1.下面四个变量声明语句中，哪一个变量的命名是正确的？
    A．var for               							B．var txt_name               

​    C．var myname myval      			  D．var 2s

2. 定义两个变量，求和
3. 交换两个变量的值

思考：如果变量名用汉字可以不可以【郭老师】

## 数据类型（重点）

### 数据类型

数据类型：  数据类型指的是变量的数据类型
数据类型分为：简单数据类型，复杂数据类型

### 简单数据类型【number，string，boolean，null，undefined】

- ##### 数值类型(number)

```javascript
☞ 凡是数字都属于该类型【整数，小数，负数】

☞ 只要变量的值是一个具体的数字，那么当前变量的数据类型就是数值类型

☞ number类型表示的数字大小：
	  最大值是±1.7976931348623157乘以10的308次方     Number.MAX_VALUE
	  最小值是±5 乘以10的-324次方								  	Number.MIN_VALUE

☞ 数值类型表示方式：（了解）

	 ✔ 十进制表示
   
		var  n1=10,n2=9,n3=100;

	 ✔ 十六进制表示
   
		以 0x 开头 0到9之间的数字，a(A)-f(F)之间字母构成。 a-f对应的数字是10-15
		[0,1,2,3,4,5,6,7,8,9，a,b,c,d,e,f]

		var num = 0xA;

	 ✔ 八进制表示
   
		八进制直接以数字0开始，有0-7之间的数字组成。[0,1,2,3,4,5,6,7]
  	var num1 = 07;   
  	var num2 = 06;  
  	var num3 = 05;   

☞ 备注：
	 进行算数计算时，八进制和十六进制表示的数值最终都将被转换成十进制数值。
```

- 字符类型(string)

```javascript
☞ 字符串可以是引号中的任意文本。可以使用单引号或双引号
	如果数据是字母，符号，汉字，这些都是字符串类型，字符串类型的就要加引号
☞ 在js中一般写字符串类型的变量时候，推荐使用单引号。
	字母，汉字，符号作为数据存在必须要用引号包含【var num = "abcdefgabcd""aaaaaaaaa";】

  不管是什么数据如果用引号包含就变成字符串类型

	1、字母，汉字，符号
	2、只要是字符类型都要加引号
	3、字符串和字符串不能直接挨着写

☞ 注意：
	 1. 单引号和双引号之间的嵌套
			例如： 输出    我是"高帅富"程序猿;  
  
   2. 转义字符【\】
	 \n      换行
   \\		   斜杠
   \'		   单引号
	 \"		   双引号
	 \r 	   回车符
  例如：
  var strMsg = 'I'm the GOD of my world ~!';   //输出：I'm the GOD of my world ~!
  var strMsg2 = "I"m the GOD of my world ~!";  //输出：I"m the GOD of my world ~!
  var strMsg3 = '反斜杠是这个 \\，神奇！';  //输出：反斜杠是这个 \，神奇！
```

- 布尔类型(boolean)(bool)

```javascript
☞ true（真）  和 false （假）
只有两种结果（只有两种状态），全都是用布尔值表示
```

- null空类型，undefined类型（了解）

```javascript
//如果一个变量没有赋值，该变量的默认是undefined
var n1;
//如果一个变量的值是undefined，那么该变量的数据类型就是undefined类型
```

### 复杂数据类型（目前不讲）

- object类型【万物皆对象】
- array数组

#### 课堂测试

请说出如下变量分别对应的数据类型是什么？
	var  a1=123;    var a2="123";    var a3=true;  var a4="false";   var a5="1.63";
	var  a6; 	   		var a8="null"
检查数据类型的方法：typeof(变量)

### 字面量

```javascript
在源代码中一个固定值的表示法。【通过看具体的值，就能够知道数据类型】

数值字面量：8, 9, 10

var num = 2;var num2 = 3;

字符串字面量：'布卡教育', "大前端"
var num = "123";var str = 'wahaha';

布尔字面量：true，false
var n = true; var m = false;
```

## 表达式和语句

### 表达式

一个表达式可以产生一个值，有可能是运算、函数调用、有可能是字面量。表达式可以放在任何需要值的地方。

### 语句

语句可以理解为一个行为，循环语句和判断语句就是典型的语句。一个程序有很多个语句组成，一般情况下;分割一个一个的语句

## 数据类型判断

```javascript
 ☞ 使用  typeof 变量  可以得到对应变量的数据类型
 ☞ 例如：
	   var n1 = 123;
		//获取n1的数据类型
		console.log(typeof n1);
		var n2 = '123';
		console.log(typeof n2);
		var n3 = true;
		console.log(typeof n3);
```

## 判断一个变量是不是数字

NaN：not a number【特殊值】
isNaN：is not a number【判断】

​	用来判断一个值是否是数字，如果是数字得到的false，如果不是数字得到的是true

​	isNaN(n)：'aaa' is not a number

​	isNaN：==》is not a number

​	isNaN(n)  ==》 n is not a number

```javascript
isNaN(x) 方法
	==>x是数字{false}
	==>x不是数字{true}
is not a number
isNaN(n)==>3 is not a number

例如：
	var usrAge = 21;
  var isOk = isNaN(usrAge);
  console.log(isNum); // false ，21 不是一个 非数值

  var usrName = "James";
  console.log(isNaN(usrName));//true ，"James"是一个 非数值
```

#### 练习思考题：

计算总工资(总工资 = 基础工资 + 绩效工资)  --> 交互 , 基本工资让用户自己输入.

## 数据类型转换

- ##### 转数值类型【Number，parseInt，parseFloat】

```javascript
 ☞ Number(变量)：
  	 总结：
     	  1. 可以通过该方法将数据类型转换为数值类型
        2. 在转换的过程中可以将原来的值保留，遇到小数直接保留下来，不会舍去
        3. 如果变量无法转换为数值类型，那么返回的结果是NaN； 对应的数据类型依然是数值类
        4. 如果将布尔类型转换为数值类型，true 转化后的结果是 1  false 转化后的结果是0
   
        NaN：not a number【number类型】
          
  ☞ parseInt(变量)	取整
  
  	var num1 = parseInt("12.3abc");  // 返回12，如果第一个字符是数字会解析知道遇到非数字结束
    var num2 = parseInt("abc123");   // 返回NaN，如果第一个字符不是数字或者符号就返回NaN
    备注：
        1  只会保留整数部分，通过该方式进行数据类型转换后得到就是一个整数
        2. 如果一个变量中的值无法转换为具体数字，那么返回的结果是一个 NaN 的值
        3. NaN (not  a  number)   ----NaN对应的数据类型是数值类型
        4. 通过该方法可以将其他数据类型转为数值类型
        
  ☞ parseFloat(变量)	取浮点
		总结：
    	 1. 通过该方法可以将其他数据类型转换为数值类型
         2. 在转换过程中，如果遇到小数，那么会直接将小数部分保留
         3. 如果转化不成功过，返回的结果NaN
    
```

- ##### 转字符串类型【n.toString，String(n)】

```javascript
☞  变量.toString()
 		var num = 5;
		console.log(num.toString());

☞  String(变量)

n.toString();
String(n)
备注：
		String()函数存在的意义：有些值没有toString()，这个时候可以使用String()。
		比如：undefined和null
```

- ##### 转布尔类型Booleab(n)

```javascript
 ☞ Boolean(n) 
 备注：
	 0  |''(空字符串) | null | undefined | NaN  会转换成false  其它都会转换成 true
```

#### 课后练习

```javascript
 1. 让用户输入一个三位数【整数】，使用代码分别获取到这个三位数字百位，十位，个位上的数字。
 例如：
  		用户输入： 456， 最后在浏览中分别弹出 4,5,6

[(678)百位：数字 / 100 ==> 6.78 ==> 取整]
[(678)十位：(数字 - 百位*100) / 10 ==> 取整]
  	 	
 2. 用户任意输入一个三位数，求这个三位数字百位，十位，个位之和。
```
