## 其他扩展部分

注意：JavaScript中没有堆和栈的概念，此处我们用堆和栈来讲解，目的方便理解和方便以后的学习。

```javascript
把一个变量赋值给另外一个变量，传递

值传递：把数据复制一份，传递给另外一个变量【两份数据】【简单数据】

引用传递：把数据地址复制一份进行传递【一份数据】【复杂数据】
```

var n = 2;

var m = n;

如果n是简单数据【会把n的数据复制一份给m，此时n和m一人一份数据】

var n = {};

var m = n;

如果n是复杂数据【会把n的地址给m，此时n和m地址指向的是同一份数据】

### 简单数据类型在内存中的存储

![1498288494687](assets\1498288494687.png)

```javascript
 ☞ 简单数据类型（值类型） 存储在内存的 栈 上
  
 ☞ Number  String   Boolean  Null Undefined
  
 ☞ 分析简单数据类型在内存中的存储方式
  var  n1 = 10;
	var  n2 = n1;
	var  n = 3;
```

### 复杂数据类型在内存中的存储

![1498700592589](assets\1498700592589.png)

```javascript
 ☞ 复杂数据类型（引用类型） 存储在内存的 堆 上
  
 ☞ Object | Array | 函数
```

### 简单数据类型作为函数的参数在内存存储

```javascript
 ☞  分析案例代码
 
 function  fn ( a, b ) {
      a = a+1;
      b = b+1;
      console.log( a );
      console.log( b );
 }

 var  x = 10；
 var  y = 5;

 fn(x, y);

 console.log( x, y );   思考：x ， y 的值是多少？
```

### 复杂数据类型作为函数的参数在内存存储

```javascript
  function Person ( name, age ) {
       this.name =  name; 
       this.age = age;
       this.sayHi = function () {
          console.log( "你好" );
       }
  }

   var p1 = new Peron( "张三", 18 );

   function getperson ( person ) {
     
        person.name = "李四";
   }
	getperson( p1 );

  console.log( p1.name );   //思考： p1 的name值是什么？
```

#### 课堂案例

```javascript
function Person ( name, age ) {
    this.name = name;
    this.age = age;
    this.sayHi = function () {
        console.log( "你好" );
    }
}

var p1 = new Person(" 张三 ", 18);

function getperson ( person ) {
    person.name = "李四";  // 把张三变李四
    person = new Person("王五",20); //地址值被换了
    console.log(person.name);  // 新对象的name
}

getperson(p1);
console.log(p1.name);    //思考： p1.name 输出的结果是什么？




☞  数组作为参数

function getary ( ary ) {
    ary[0] = -1;
}

var newary = [1,2,3];

getary( newary );
console.log( newary[0] );
```

## 内置对象介绍

☞  JavaScript组成：   ECMAScript  |   DOM   |  BOM

☞  ECMAScript：  变量 ， 函数， 数据类型 ，流程控制，内置对象。。。

☞  js中的对象： 自定义对象 ， 内置对象 ， 浏览器对象（不属于ECMAScript）

☞  Math对象，Array对象，Date对象。。。。

☞ 通过查文档学习内置对象   MDN  (https://developer.mozilla.org/zh-CN/docs/Web/JavaScript)
对象.属性
对象.方法()
API：执行某件事件的接口

## MDN介绍

```javascript
 MDN: https://developer.mozilla.org/zh-CN/docs/Web/JavaScript
```

## Math对象

```javascript
  ☞ 提供了一系列与数学相关的方法或属性  ( 静态  |  实例)

  ☞ Math.PI          获取圆周率【属性】 
  ☞ Math.random()    返回大于等于0小于1之间的随机数 [灵活使用]

  ☞ Math.floor() 	   向下取整，返回一个小于当前数字的整数
  ☞ Math.ceil()	     向上取整，返回一个大于当前数字的整数

  ☞ Math.round()     四舍五入（小数如果小于0.5,返回小于当前数字的整数，如果小数部分大于0.5返回大于当前数字的一个整数）
  ☞ Math.abs()		取绝对值（返回当前数字的绝对值，正整数）

  ☞ Math.max()       返回一组数中的最大值 （可以设置多个参数，返回其中最大值，参数不可以是数组）
  ☞ Math.min()       返回一组数中的最小值 （可以同时设置多个参数，与最大值效果一样）

  ☞ Math.sin(x)	     返回一个正弦的三角函数 ( 注意： x 是一个以弧度为单位的角度)
  ☞ Math.cos(x)	     返回一个余弦的三角函数 （注意： x 参数是一个以弧度为单位的角度）

  ☞ Math.pow(x,y)	 返回x的y次幂
   求两个数的随机数公式：
  Math.floor( Math.random() * (m - n + 1) + n );
  Math.floor( Math.random() * (大数 - 小数 + 1) + 小数 );
```

## Math课堂案例

```javascript
1、求 1 到 10之间的随机整数[包括1和10]

2、求 20 到 50 之间的随机整数 [包括20 和 50]

3、封装一个生成m到n之间的随机整数 （公式）

   function get_random (min, max) {
     	return	Math.floor(Math.random() * (max - min + 1) + min);
   }
4、随机生成RGB颜色
```

## 静态成员和实例成员

☞ 静态成员：（不需要new）
	 1、不需要通过构造函数创建对象且能访问对象中的属性或方法

☞ 实例成员： 必须new
	 1、首先必须通过构造函数创建对象
	 2、通过构造函数创建对象并访问的属性或方法[实例成员]

# Date对象

```javascript
☞ Date是一个构造函数，必须通过 new Date() 创建一个实例成员才能使用

☞ 用法一：空构造函数
   var d = new Date();		//GMT 格林威治时间（0时区）

☞ 用法二： 传入日期格式的字符串
  var  d = new Date("1988-8-8")

☞ 用法三： 传入数字
  var  d = new Date(year, month,day,time,second]);  //必须设置年和月
  备注： 月份从0 开始， 0 代表1月

☞ 获取当前时间的毫秒值(时间戳)：
  d.valueOf()  
  d.getTime()  // 推荐使用
  Date.now()   //H5 新方法 有兼容信息

通过H5提供的方法操作 多媒体标签
http://www.w3school.com.cn/html5/html5_ref_audio_video_dom.asp
```

### Date中的方法

```javascript
☞ 日期格式化方法
	var d = new Date();
    d.toString();  						//转化成字符串
    d.toDateString();  				//转换成日期字符串
    d.toTimeString();  				//转换成时间字符串
    d.toLocaleDateString();   //返回本地的日期格式  （不同浏览器不同效果）
    d.toLocaleTimeString();   //返回本地的时间格式  （不同浏览器不同效果）

☞ 获取日期其他部分(掌握)
	  d.getSeconds()  //获取秒
    d.getMinutes()  //获取分钟
    d.getHours()    //获取小时
    d.getDay()      //返回周几   （0表示周日）
    d.getDate()     //返回当前月的第几天
    d.getMonth()    //返回月份   （从0开始）
    d.getFullYear()  //返回年份

自学文档
http://www.runoob.com/js/js-obj-date.html
http://www.w3school.com.cn/jsref/jsref_obj_math.asp
```

#### Date案例

 写一个函数，格式化日期对象，返回 yyyy-mm-dd HH:mm：ss 形式

## Array数组对象

### 数组中常用的方法

```javascript
☞ 判断变量是不是一个数组    Array.isArray(ary)  

☞ toString()   				// 把数组转换为字符串，使用逗号分隔
☞ valueOf()   				// 返回数组对象本身

☞ ary.pop() [常用]    //返回数组中最后一个字，且会修改数组的长度 
☞ ary.shift()  				//取出数组中的第一个元素，修改数组的长度

☞ ary.push() [常用]    // 该方法有一个返回值，表示数组最新的长度，该方法中可以设置多个参数
☞ ary.unshift(值)     //在数组中最开始位置添加一个值


☞ 其他方法汇总
	  	 ◆ reverse()  // 翻转数组
   	   ◆ concat()   //把两个数组拼接到一块,返回一个新数组
			 ◆ slice(startindex, endindex)   //从当前数组中截取一个新的数组 
		   	  ✔ 第一个参数表示开始索引位置,第二个参数代表结束索引位置
		 	 ◆ splice(startindex, deletCont, options)  //删除或者替换数组中的某些值
		 	    ✔ 第一个参数代表从哪开始删除
          ✔ 第二个参数代表一共删除几个
          ✔ 第三个参数代表要替换的值(可选)
       ◆ indexOf(content[,index])，lastIndexof()   //没找到返回-1 查找
          ✔ 找数组中的某个值,如果找到返回索引位置,如果没有找到返回-1
          ✔ lastIndexof()  从数组的末尾开始找,如果找到,返回索引位置,如果没有找到返回-1
       ◆ join()   //将数组中的每一个元素通过一个字符链接到一块 , 替换分隔符 
			   sort()   //  排序 (先自行研究)
  
案例部分:
 ☞ 将数组中的元素以 “|”链接的方式输出   var ary = ['张三', '李四', '王五'];

 ☞  将一个数组中的字符串顺序反转  ['a'，'b','c','d'] -> ['d','c','b','a']

 ☞ 将数组中每一个'a' 的位置输出到控制台中 ['a','b','c','d','a','e','f','a','g','h']

// 当明确循环次数的时候,使用for循环
// 无法确定循环次数的用while循环
```

## 字符串string

特性: 不可变性

注意：别大量替换字符串

```js
属性：length，长度
☞ 字符方法
 	 1. charAt(index)  				//获取指定位置处的字符
	 2. str[index]		   			//获取指定位置的字符 （H5中的方法）

☞ 字符串方法
 	 1. concat()   						//拼接字符串  等效于 +
   2. slice(strat,end)       //从指定位置开始，截取字符串到结束位置，end值取不到
   3. substring(start,end)   //从指定位置开始，截取字符串到结束位置， end值取不到
   4. substr(start,length)   //从指定位置开始，截取length长度个字符

☞ 位置方法
   1. indexOf(字符)   //返回字符在字符串中的位置【首次】
	 2. lastIndexOf(字符)  //从后往前找，只找第一个匹配的字符【尾次】

☞ 去除空白
  	trim()      //只能去除字符串前后空白

☞ 大小写转换法
  	toLocaleUpperCase()  //转化为大写
    toLocaleLowerCase()  //转化为小写

☞ 其他
  	replace(a,b)  // 用b替换a
	  split()   //	以一个分割符,将一个字符串串分割成一个数组

案例部分:
  // 截取字符串 “我爱中华人民共和国”  中 '中华' 输出到控制台中
  // 'qweqweoeqweroqweqweodfsfdo' 查找字符串中所有字母 'o'出现的位置
  //  把字符串中的所有字母'o'替换成 '-';
练习：
	//  把字符串中的所有字母'o'替换成 '-';
  //  封装一个函数，获取对应文件的后缀名 https://www.test.com/login/index.html
  //	获取url中 的用户名和密码 https://www.test.com/login?name=zs&pwd=123; 
```
#### 要记住的：

​	 Math对象： Math.floor( Math.random() * (大数 - 小数 + 1) + 小数 );

​	Date对象：创建对象new Date， d.getTime() 

​	Array对象：push，join

​	String对象：indexOf，lastIndexOf，substring，substr，split()