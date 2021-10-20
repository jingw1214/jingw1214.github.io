## 1.初识JavaScript

### **1.1 JavaScript**历史

-  布兰登·艾奇(Brendan Eich , 1961年~)。
- 在1995年利用10天完成JavaScript 设计。
- 网景公司最初命名为LiveScript，后来在与Sun合作之后将其改名为JavaScript.

 

### 1.2 JavaScript是什么

-  JavaScript是世界上最流行的语言之一，是一种运行在客户端的脚本语言（Script是脚本的意思)
- 脚本语言：不需要编译，运行过程中由js解释器(js 引擎）逐行来进行解释并执行
- 现在也可以基于Node.js技术进行服务器端编程

 

### 1.3 JavaScript的作用

- 表单动态校验(（密码强度检测）(JS产生最初的目的)
- 网页特效
- 服务端开发(Node.js)
- 桌面程序(Electron)
- App(Cordova)
- 控制硬件-物联网(Ruff)
- 游戏开发(cocos2d-js)

 

### 1.4 HTML/CSS/JS的关系

**HTML/CSS 标记语言--描述类语言**

- HTML -- 决定网页结构和内容(决定看到什么)，相当于人的身体
- CSS -- 决定网页呈现给用户的模样(决定好不好看)，相当于给人穿衣服、化妆

**JS脚本语言--编程类语言**

- 实现业务逻辑和页面控制(决定功能)，相当于人的各种动作

 

### 1.5 浏览器执行JS简介

浏览器分成两部分：渲染引擎和JS引擎

·     渲染引擎：用来解析HTML与CSS，俗称内核，比如chrome浏览器的blink，老版本的webkit

·     JS引擎：也称为JS解释器。用来读取网页中的JavaScript代码，对其处理后运行，比如chrome浏览器的V8

 

浏览器本身并不会执行JS代码，而是通过内置JavaScript引擎(解释器)来执行JS代码。JS引擎执行代码时逐行解释每一句源码（转换为机器语言），然后由计算机去执行，所以JavaScript语言归为脚本语言，会逐行解释执行。

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image001.png)

 

### 1.6 JS的组成

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image002.png)

#### 1.6.1 ECMAScript

ECMAScript是由ECMA国际（原欧洲计算机制造商协会)进行标准化的一门编程语言，这种语言在万维网上应用广泛，它往往被称为JavaScript或JScript，但实际上后两者是ECMAScript语言的实现和扩展。

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image003.png)

ECMAScript : ECMAScript规定了JS的编程语法和基础核心知识，是所有浏览器厂商共同遵守的一套JS语法工业标准。

 

更多参看MDN: https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/JlavaScript technologies overview

 

#### 1.6.2 DOM--文档对象模型

文档对象模型(（Document Object Model，简称DOM），是W3C组织推荐的处理可扩展标记语言的标准编程接口。

通过DOM提供的接口可以对**页面上的各种元素进行操作**(大小、位置、颜色等)。

 

#### 1.6.3 BOM--浏览器对象模型

BOM(Browser Object Model，简称BOM)是指浏览器对象模型，它提供了独立于内容的、可以与浏览器窗口进行互动的对象结构。

通过BOM可以**操作浏览器窗口**，比如弹出框、控制浏览器跳转、获取分辨率等。

 

### 1.7 JS书写位置

JS有3种书写位置，分别为行内、内嵌和外部。

#### 1.7.1 行内式

```html
<input type="button" value="唐伯虎" onclick="alert('秋香姐')"> 
```

- 可以将单行或少量JS代码写在HTML标签的事件属性中(以on开头的属性），如:onclick
- 注意单双引号的使用:在HTML中我们推荐使用双引号,JS中我们推荐使用单引号
- 可读性差，在html中编写JS大量代码时，不方便阅读;
- 引号易错，引号多层嵌套匹配时，非常容易弄混;
- 特殊情况下使用

#### 1.7.2 内嵌JS

写在`<head>`标签内部

```html
<script> 
  alert ('Hello world~!'); 
</script>
```

- 可以将多行JS代码写到`<script>`标签中
- 内嵌JS是学习时常用的方式

#### 1.7.3 外部JS文件

html文件中，写在`<head>`标签内部：

```html
<script src="my.js"></script> 
```

my.js 文件

```javascript
alert('如果我是DJ，你还爱我吗？') 
```

 

- 利于HTML页面代码结构化，把大段JS代码独立到HTML页面之外，既美观，也方便文件级别的复用
- 引用外部JS文件的script标签，中间不可以写代码
- 适合于S代码量比较大的情况

 

###  **2.JS注释**

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/7cde3b1114ed41d3923e59856b543966/clipboard.png)

 

 **3.JavaScript输入输出语句**

为了方便信息的输入输出，JS中提供了一些输入输出语句，其常用的语句如下:

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/6f5062c36ef740d4a91ceac475ecd160/clipboard.png)

 

 

## 1.变量

目标 TARGET

- 能够说出变量的主要作用
- 能够写出变量的初始化能够说出变量的命名规范
- 能够画出变量是如何在内存中存储的能够写出交换变量案例

目录 Contents

- 变量概述
- 变量的使用
- 变量语法扩展
- 变量命名规范
- 交换变量案例



### **1.1** **什么是变量**

白话:变量就是一个装东西的盒子。

通俗:变量是用于存放数据的容器。我们通过变量名获取数据，甚至数据可以修改。

![image-20210915102414204](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210915102414204.png)

 

### 1.2 变量在内存中的存储

本质:变量是程序在内存中申请的一块用来存放数据的空间。

类似我们酒店的房间，一个房间就可以看做是一个变量。

![image-20210915102443657](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210915102443657.png)

### **1.3** **变量的使用**

变量在使用时分为两步:1.声明变量2.赋值

**1.****声明变量**

//声明变量 var age;//声明一个名称为age的变量 

·     var是一个JS关键字，用来声明变量( variable变量的意思)。使用该关键字声明变量后，计算机会自动为变量分配内存空间，不需要程序员管

·     age是程序员定义的变量名，我们要通过变量名来访问内存中分配的空间

**2.****赋值**

age = 10;//给age这个变量赋值为10 

·     = 用来把右边的值赋给左边的变量空间中 此处代表赋值的意思

·     变量值是程序员保存到变量空间里的值

**3.****变量的初始化**

var age = 18;//声明变量同时赋值为18 

·     声明一个变量并赋值，我们称之为变量的初始化。

 

案例:变量的使用

有个叫卡卡西的人在旅店登记的时候前台让他填一张表，这张表里的内容要存到电脑上，表中的内容有:姓名、年龄、邮箱、家庭住址和工资，存储之后需要把这些信息显示出来，所显示的内容如下:

我叫旗木卡卡西，我住在火影村，我今年30岁了，我的邮箱是 kakaxi@itcast.cn，我的工资2000

 

### 1.4变量语法扩展

**1.****更新变量**

一个变量被重新复赋值后，它原有的值就会被覆盖，变量值将以最后一次赋的值为准。

var age = 18; age = 81;//最后的结果就是81因为18被覆盖掉了 

 

**2.****同时声明多个变量**

同时声明多个变量时，只需要写一个var，多个变量名之间使用英文逗号隔开。

var age = 10,name = "zs', sex = 2; 

 

![image-20210915102607109](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210915102607109.png)

 

**3.****声明变量特殊情况**

![](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210915102614563.png)

### **1.5** **变量命名规范**

·     由字母(A-Z a-z)、数字(0-9)、下划线（`_`)、美元符号($)组成，如: usrAge, num01, _name

·     严格区分大小写。var app;和var App;是两个变量

·     不能以数字开头。18age是错误的

·     不能是关键字、保留字。例如: var、for、while

·     变量名必须有意义。MMD BBD nl → age

·     遵守驼峰命名法。首字母小写，后面单词的首字母需要大写。myFirstName

·     推荐翻译网站:有道 爱词霸

 

注意：**name** 这个单词 不是关键字和保留字，但是在一些浏览器中有特殊的含义，也不能作为变量名。

（在不赋值的情况下，可以输出）

 

![image-20210915102641427](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210915102641427.png)

 

 

 

## 2.数据类型

> 目标
>
> ·     能够说出5种简单数据类型
>
> ·     能够使用typeof获取变量的类型
>
> ·     能够说出1~2种转换为数值型的方法
>
> ·     能够说出1~2种转换为字符型的方法
>
> ·     能够说出什么是隐式转换

 

![img](../../AppData/Local/Temp/msohtmlclip1/01/clip_image001.png)



### **1.** **数据类型简介**

#### 1.1为什么需要数据类型

在计算机中，不同的数据所需占用的存储空间是不同的，为了便于把数据分成所需内存大小不同的数据，充分利用存储空间,于是定义了不同的数据类型。

简单来说，数据类型就是数据的类别型号。比如姓名“张三”，年龄18、这些数据的类型是不一样的。

 

#### 1.2变量的数据类型

变量是用来存储值的所在处，它们有名字和数据类型。变量的数据类型决定了如何将代表这些值的位存储到计算机的内存中。JavaScript是一种弱类型或者说动态语言。这意味着不用提前声明变量的类型，在程序运行过程中，类型会根据等号右边的值被自动确定。

var age = 10;//这是一个数字型 var areYouOk ='是的';//这是一个字符串 

在代码运行时，变量的数据类型是由JS引擎 根据=右边变量值的数据类型来判断的，运行完毕之后，变量就确定了数据类型。

 

JavaScript拥有动态类型，同时也意味着相同的变量可用作不同的类型:

var x =6; //x为数字 var x = "Bill"; //x为字符串 

 

#### 1.3数据类型的分类

- JS把数据类型分为两类︰
  - 简单数据类型(Number, string, Boolean, Undefined,Null)
  - 复杂数据类型( object)

 

### 2.简单数据类型

#### 2.1简单数据类型（基本数据类型)

JavaScript中的简单数据类型及其说明如下:

![img](../../AppData/Local/Temp/msohtmlclip1/01/clip_image002.png)

#### 2.2 数字型 NUMBER

**1.****数字型进制**

最常见的进制有二进制、八进制、十进制、十六进制。

//1.八进制数字序列范围:0~7 var num1 = 07;//对应十进制的7 var num2 = 023; //对应十进制的19 var num3 = 010;//对应十进制的8 //2.十六进制数字序列范围:0~9以及A~F var num = OxA; 

 

现阶段我们只需要记住，在JS中八进制前面加0，十六进制前面加0x

 

**2****数字型范围**

JavaScript中数值的最大和最小值

alert(Number.MAX_VALUE); // 1.7976931348623157e+308 alert (Number.MIN_VALUE); // 5e-324 

 

**3.****数字型三个特殊值**

alert ( Infinity); //Infinity alert (-Infinity) ; //-Infinity alert (NaN); // NaN 

·     Infinity，代表无穷大，大于任何数值

·     -Infinity，代表无穷小，小于任何数值

·     NaN，Not a number，代表一个非数值

![img](../../AppData/Local/Temp/msohtmlclip1/01/clip_image003.png)

 

 

**4. isNaN()**

用来判断一个变量是否为非数字的类型，返回true或者false

![img](../../AppData/Local/Temp/msohtmlclip1/01/clip_image004.png)

 

 

var usrAge = 21; var isok = isNaN (userAge) ; console.log (isNum ) ; 1/ false , 21 不是一个非数字 var usrName = "andy" ; console.log(isNaN (userName) ) ; ll/ true , "andy"是一个非数字 

 

 

**2.3****字符串型String**

字符串型可以是引号中的任意文本，其语法为双引号""和单引号""

var strMsg ="我爱北京天安门~"; //使用双引号表示字符串 var strMsg2=·我爱吃猪蹄~'; //使用单引号表示字符串 //常见错误 var strMsg3 =我爱大肘子; //报错，没使用引号，会被认为是js代码，但js没有这些语法 

因为 HTML标签里面的属性使用的是双引号，JS这里我们更推荐使用单引号。

 

**1.****字符串引号嵌套**

JS可以用单引号嵌套双引号，或者用双引号嵌套单引号(**外双内单，外单内双**)

var strMsg = '我是"高帅富"程序猿'; //可以用''包含"" var strMsg2 = "我是'高帅富'程序猿";//也可以用""包含'' //常见错误 var badQuotes = ' what on earth?";//报错，不能单双引号搭配 

引号之间有就近原则。

 

**⒉****字符串转义符**

类似HTML里面的特殊字符，字符串中也有特殊字符，我们称之为转义符。

转义符都是\开头的，常用的转义符及其说明如下:

![img](../../AppData/Local/Temp/msohtmlclip1/01/clip_image005.png)

 

**3.****字符串长度**

字符串是由若干字符组成的，这些字符的数量就是字符串的长度。通过字符串的length属性可以获取整个字符串的长度。

var strMsg="我是帅气多金的程序猿!"; alert (strMsg.length);//显示11 

 

**4.****字符串拼接**

·     多个字符串之间可以使用＋进行拼接，其拼接方式为 字符串＋任何类型=拼接之后的新字符串

·     拼接前会把与字符串相加的任何类型转成字符串，再拼接成一个新的字符串

//1.1字符串“相加" alert ('hello'+ '' + 'world' ); /l hellogworld //1.2数值字符串"相加” alert( '100’+ '100'); // 100100 //1.3 数值字符串＋数值 alert ( '11' +12);// 1112 

\+ 号总结口诀：数值相加，字符相连

 

**5.****字符串拼接加强**

console.log ( 'pink老师' + 18) ;// 只要有字符就会相连 var age = 18; //console. log ( 'pink老师age岁啦");// 这样不行哦 console.log ( 'pink老师' + age); // pink老师18 console.log ( 'pink老师+ age + '岁啦');// pink老师18岁啦 

·     我们经常会将字符串和变量来拼接，因为变量可以很方便地修改里面的值

·     变量是不能添加引号的，因为加叼号的变量会变成字符串

·     如果变量两侧都有字符串拼接，口诀“引引加加”，删掉数字，变量写加中间

 

**2.5****布尔型Boolean**

布尔类型有两个值：true和false ，其中 true表示真(对），而false表示假（错）。

布尔型和数字型相加的时候，true的值为1 ,false的值为0。

console. log (true + 1); // 2 console.log (false + 1); // 1 

 

**2.6 Undefined****和Null**

一个声明后没有被赋值的变量会有一个默认值undefined(如果进行相连或者相加时，注意结果)

var variable; console.log (variable) ;//undefined console.log( '你好' + variable) ;//你好undefined console. log(11 + variable);// NaN console. log(true + variable);//NaN 

 

一个声明变量给null值，里面存的值为空（学习对象时，我们继续研究null)

var vari = null; console.log ('你好·+vari); // 你好null console. log (11 + vari); // 11 console.log(true + vari) ; // 1 

 

### 3.获取变量数据类型

**3.1** **获取检测变量的数据类型**

typeof 可用来获取检测变量的数据类型

![img](../../AppData/Local/Temp/msohtmlclip1/01/clip_image006.png)

**3.2****字面量**

字面量是在源代码中一个固定值的表示法，通俗来说，就是字面量表示如何表达这个值。

·     数字字面量:8,9,10

·     字符串字面量:"黑马程序员,"大前端”

·     布尔字面量:true , false

### 4.数据类型转换

使用表单、prompt获取过来的数据默认是字符串类型的，此时就不能直接简单的进行加法运算，而需要转换变量的数据类型。通俗染说，就是把一种数据类型的变量转换成另外一种数据类型。

 

我们通常会实现3种方式的转换:

·     转换为字符串类型

·     转换为数字型

·     转换为布尔型

 

#### 4.1 转换为空符电

![img](../../AppData/Local/Temp/msohtmlclip1/01/clip_image007.png)

| 方式             | 说明                         | 案例                                  |
| ---------------- | ---------------------------- | ------------------------------------- |
| toString()       | 转成字符串                   | var num = 1; alert(num.toString());   |
| String()强制转换 | 转成字符串                   | var num = 1; alert(String(num));      |
| 加号拼接字符串   | 和字符串拼接的结果都是字符串 | var num = 1;allert(num+"我是字符串"); |



 `toString()`和`String()`使用方式不一样。

三种转换方式，我们更喜欢用第三种加号拼接字符串转换方式，这一种方式也称之为隐式转换。

 

#### 4.2 转换为数字型（重点)

![img](../../AppData/Local/Temp/msohtmlclip1/01/clip_image008.png)

注意parselnt和parseFloat单词的大小写，这2个是重点

隐式转换是我们在进行算数运算的时候，JS自动转换了数据类型

![img](../../AppData/Local/Temp/msohtmlclip1/01/clip_image009.png)

 

![img](../../AppData/Local/Temp/msohtmlclip1/01/clip_image010.png)

 

**4.4****转换为布尔型**

![img](../../AppData/Local/Temp/msohtmlclip1/01/clip_image011.png)

·     代表空、否定的值会被转换为false ，如""、0、NaN、 null、undefined

·     其余值都会被转换为true

console. log(Boolean ('')); // false console. log(Boolean(0)); // false console. log(Boolean (NaN)); // false console. log (Boolean (null)); // false console.log (Boolean (undefined)); // false console.log(Boolean ('小白')); // true console. log (Boolean (12)); // true 

## 3.运算符

> 目标 TARGET：
>
> 能够使用常用运算符
>
> 能够说出前置递增和后置递增的区别
>
> 能够说出运算符的优先级
>

运算符(operator )也被称为操作符，是用于实现赋值、比较和执行算数运算等功能的符号。

JavaScript中常用的运算符有:

·     算数运算符

·     递增和递减运算符

·     比较运算符

·     逻辑运算符

·     赋值运算符

### 3.1 算术运算符

概念：算术运算使用的符号，用于执行两个变量或值的算术运算。

![img](../../AppData/Local/Temp/msohtmlclip1/01/clip_image001.png)

浮点数的精度问题

浮点数值的最高精度是17位小数，但在进行算术计算时其精确度远远不如整数。

var result = 0.1 + 0.2;//结果不是0.3，而是:0.3000000o0o0o00004 console.log(0.07 * 100);//结果不是7，而是:7.0000000o0000001

 

![img](../../AppData/Local/Temp/msohtmlclip1/01/clip_image002.png)

表达式和返回值

表达式∶是由数字、运算符、变量等以能求得数值的有意义排列方法所得的组合

简单理解∶是由数字、运算符、变量等组成的式子

 

### 3.2 递增和递减运算符

如果需要反复给数字变量添加或减去1，可以使用递增（++)和递减(--)运算符来完成。

 

在JavaScript中，递增（++）和递减(--）既可以放在变量前面，也可以放在变量后面。放在变量前面时，我们可以称为前置递增（递减）运算符，放在变曩后面时，我们可以称为后置递增（递减）运算符。

注意∶递增和递减运算符必须和变量配合使用。

#### 3.2.1 前置递增运算符

++num 前置递增，就是自加1，类似于num = num + 1，但是＋+num 写起来更简单。

使用口诀:先自加，后返回值

 

#### 3.2.2 后置递增运算符

num++ 后置递增，就是自加1，类似于num = num + 1，但是 num++写起来更简单。

使用口诀:先返回原值，后自加

 

![img](../../AppData/Local/Temp/msohtmlclip1/01/clip_image003.png)

 

#### 3.2.3 前置递增和后置递增小结

前置递增和后置递增运算符可以简化代码的编写，让变量的值+1比以前写法更简单

·     单独使用时，运行结果相同

·     与其他代码联用时，执行结果会不同

·     后置:先原值运算，后自加（先人后己)

·     前置:先自加，后运算(先已后人)

·     开发时，大多使用后置递增/减，并且代码独占一行，例如:num++;或者num--;

### 3.3 比较运算符

概念:比较运算符（关系运算符）是两个数据进行比较时所使用的运算符，比较运算后，会返回一个布尔值( true9 false )作为比较运算的结果。

![image-20210922160047967](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210922160047967.png)

4.2=小结

![image-20210922160117491](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210922160117491.png)

### 3.4 逻辑运算符

概念∶逻辑运算符是用来进行布尔值运算的运算符，其返回值也是布尔值。后面开发中经常用于多个条件的判断

![img](../../AppData/Local/Temp/msohtmlclip1/01/clip_image006.png)

 

#### 3.4.1 逻辑与&&

两边都是true才返回true，否则返回false

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/e69c543b4cd14b989be4be7edd586d2b/clipboard.png)

 

#### 3.4.2 逻辑或（||）

两边都为false 才返回false，否则都为true

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/6e75f45e61494558a166bf9f6039a4c8/clipboard.png)

#### 3.4.3 逻辑非!

逻辑非(!)也叫作取反符，用来取一个布尔值相反的值，如true的相反值是false

```js
var isok = !true; 
console.log(isok);// false 
```

#### 3.4.4 空值合并操作符（??）

​	空值合并操作符（??）是一个逻辑操作符，当左侧的操作数为` null` 或者 `undefined` 时，返回其右侧操作数，否则返回左侧操作数。

　　与逻辑或操作符（||）不同，逻辑或操作符会在左侧操作数为假值时返回右侧操作数。也就是说，如果使用 || 来为某些变量设置默认值，可能会遇到意料之外的行为。比如为假值（例如，`'' `或 0）时。见下面的例子。

#### 可选链操作符( ?. )

　　可选链操作符( ?. )允许读取位于连接对象链深处的属性的值，而不必明确验证链中的每个引用是否有效。?. 操作符的功能类似于 . 链式操作符，不同之处在于，在引用为空(nullish ) (null 或者 undefined) 的情况下不会引起错误，该表达式短路返回值

#### **3.4 **短路运算（逻辑中断)

短路运算的原理︰当有多个表达式(值)时,左边的表达式值可以确定结果时,就不再继续运算右边的表达式的值;

1.逻辑与

语法∶表达式1&&表达式2

如果第一个表达式的值为真，则返回表达式2

如果第一个表达式的值为假，则返回表达式1

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/ef244f6265cc44a5bb797ad368253538/clipboard.png)

### 3.5 赋值送算符

### 3.6 运算符优先级





## 1.数组
### 1.1 数组的概念
数组是指**一组数据的集合**，其中的每个数据被称作**元素**，在数组中可以**存放任意类型的元素****。数组是一种将一组数据存储在单个变量名下**的优雅方式。

数组的作用：数组(Array)可以把一组相关的数据一起存放在单个变量下，并提供方便的访问(获取）方式。

```javascript
//普通变量一次只能存储一个值
var num = 10;
//数组一次可以存储多个值
var arr = [1,2,3,4,5];
```
### 1.2 数组的创建方式
JS中创建数组有两种方式：
- 利用new创建数组
- 利用数组字面量创建数组

#### 1.2.1 利用new创建数组

```javascript
var 数组名 = new Array() ;
var arr = new Array () ;//创建一个新的空数组
```
- 这种方式暂且了解，等学完对象再看
- 注意Array()，A要大写
#### 1.2.2 利用数组字面量创建数组
字面量：看到这个字符，就知道是什么数据类型的。
```javascript
// 1．使用数组字面量方式创建空的数组
var 数组名 = [ ];
// 2．使用数组字面量方式创建带初始值的数组
var 数组名 = ['小白'，'小黑', '大黄','瑞奇'];
```
- 数组的字面量是方括号[]
- 声明数组并赋值称为数组的初始化
- 这种字面量方式也是我们以后最多使用的方式

### 1.3 数组元素的类型
数组中可以存放**任意类型**的数据，例字符串，数字，布尔值等。

```javascript
var arrstus =[ '小白',12,true,28.9];
```
### 1.4 获取数组中的元素
#### 1.4.1 数组的索引
**索引(下标)**∶用来访问数组元素的序号(数组**下标从0开始**)。
![在这里插入图片描述](https://img-blog.csdnimg.cn/845564fa30b749609f917698a417ae65.png)

数组可以通过**索引**来访问、设置、修改对应的数组元素，我们可以通过“数组名[索引]”的形式来获取数组中的元素。
这里的访问就是获取得到的意思

```javascript
//定义数组
var arrStus =[1,2,3];
//获取数组中的第2个元素
alert (arrStus[1]);
```
#### 1.4.2 遍历数组
使用“**数组名.length**”可以访问数组元素的数量（数组长度）。
```javascript
var arrStus =[1,2,3];
for (var i = 0; i < arrStus.length; i++) {
	console.log(arrStus[i]);
}
```

### 1.5 数组中新增元素
可以通过修改length长度以及索引号增加数组元素
#### 1.5.1 通过修改length长度新增数组元素
- 可以通过修改length长度来实现数组扩容的目的
- length属性是可读写的

```javascript
var arr =[ " red' , "green ' , "blue" , "pink " ];
arr.length = 7;
console.log(arr) ;
console.log(arr[4] );
console.log(arr[5]) ;
console. log(arr[6]) ;
```
其中索引号是4，5，6的空间没有给值，就是声明变量未给值，默认值就是undefined.。

#### 1.4.2 通过修改数组索引新增数组元素
- 可以通过修改数组索引的方式追加数组元素
- 不能直接给数组名赋值，否则会覆盖掉以前的数据

```javascript
var arr =['red','green' ,'blue', 'pink' ];
arr[arr.length]= 'hotpink' ;
console.log(arr);

```
### 1.6 数组案例
1.要求︰将数组[2,0,6,1,77,0,52,0,25,7]中的0去掉后，形成一个不包含0的新数组。

```javascript
var arr =[2,0,6,1,77,0,52,0,25,7];
var newArr = [];
for (var i = 0; i <arr.length - 1; i++) {
	if (arr[i] != 0) {
		newArr[newArr.length] = arr[i];
	}
}
```
2.翻转数组
要求:将数组['red' , ' green', 'blue' , 'pink', 'purple']的内容反过来存放。输出:['purple" , ' pink' , "blue" , ' green' , "red”]

```javascript
var arr = ['red' , ' green', 'blue' , 'pink', 'purple'];
var newArr = [];
for (var i = arr.length - 1; i > = 0; i--) {
	newArr[newArr.length] = arr[i];
}
```
3.数组排序（冒泡排序）
冒泡排序:是一种算法，把一系列的数据按照一定的顺序进行排列显示(从小到大或从大到小)。

```javascript
var arr = [12,7,9,1,0,4];
        console.log(arr.length);
        var temp;
        for (var i = 0; i < arr.length - 1; i++) {
            for (var j = 0; j < arr.length- i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
        console.log(arr);
```


- 内层 for 循环，控制的是每一趟中交换对比的次数，应该是本次需要排序的个数 - 1。由于要从左至右排序。故内层 for 循环的计数器，应从0开始计数，对比 arr[0] 和 arr[1]，…，arr[arr.length-2] 和 arr[arr.length - 1]。
- -外层 for 循环，控制的是排序的趟数，应该是 arr.length (元素个数) -1。从0开始计数的话，则应设置< 元素个数 - 1。

# 2.JavaScript 函数
## 2.1 函数的概念
在JS里面，可能会定义非常多的相同代码或者功能相似的代码，这些代码可能需要**大量重复使用**。
虽然 for循环语句也能实现一些简单的重复操作，但是比较具有局限性，此时我们就可以使用**JS中的函数**。
**函数︰**就是封装了一段**可被重复调用执行的代码块**。通过此代码块可以实现大量代码的重复使用。

##  2.2 函数的使用
函数的使用分为两步：声明函数 和调用函数。

### 2.2.1 函数的2种声明方式
**1．利用函数关键字自定义函数(命名函数)**
```javascript
//声明函数
function 函数名() {
	//函数体
}
```
- function 声明函数的关键字，必须全部小写
- 函数一般是为了实现某个功能定义的，所以通常我们将函数名命名为动词，比如sayHi
```javascript
// 1．利用函数关键字自定义函数(命名函数)
function fn() {
}
// 调用语句
fn();
```
**2．函数表达式（匿名函数）**
-  函数表达式声明方式跟声明变量差不多，只不过变量里面存的是值，而函数表达式里面存的是函数
-  函数没有名字，此处的 fun 为变量名，而不是函数名
- 函数表达式也可以传递参数
```javascript
// 2．函数表达式（匿名函数）
// var 变量名 = function() {};
var fun = function() {
	console.log('我是函数表达式");
}
// 调用语句
fun();
```
### 2.2.2 调用函数

```javascript
//函数名();
sayHi();//通过调用函数名来执行函数体代码
```
- 调用函数的时候千万不要忘记加小括号
- 口诀：函数不调用，自己不执行。

注意：声明函数本身并不会执行代码，只有调用函数时才会执行函数体代码。

### 2.2.3 函数的封装
- 函数的封装是把一个或者多个功能通过**函数的方式封装起来**，对外只提供一个简单的函数接口
- 简单理解:封装类似于将电脑配件整合组装到机箱中(类似快递打包)

## 2.3 函数的参数
### 2.3.1 形参和实参
在**声明函数**时，可以在函数名称后面的小括号中添加一些参数，这些参数被称为**形参**；而**在调用该函数时**，同样也需要传递相应的参数，这些参数被称为**实参**。
![在这里插入图片描述](https://img-blog.csdnimg.cn/0a5436385c3b414e814791dabca3faa8.png)
**参数的作用**:在**函数内部**某些值不能固定，我们可以通过参数在**调用函数时传递**不同的值进去。

注意点：
- 多个参数之间用逗号隔开
- 形参可以看做是不用声明的变量
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/6388dbade78e40579448cc876d8b102a.png)
### 2.3.2 函数形参和实参个数不匹配问题
![](https://img-blog.csdnimg.cn/bc176b6ebdd54d169af27016ab98ee50.png)

```javascript
// 函数形参实参个数匹配
function getsum(num1,num2){
console.log(num1 + num2);
}
// 1．如果实参的个数和形参的个数一致,则正常输出结果
getSum(1, 2);
// 2．如果实参的个数多于形参的个数,会取到形参的个数
getsum(1, 2, 3);
// 3．如果实参的个数小于形参的个数，多余的形参定义为 undefined，最终的结果：1 + undefined = NaN
// 形参可以看做是不用声明的变量, num2 是一个变量但是没有接受值,结果就是undefined
getsum(1);
```
**注意**：在JavaScript中，形参的默认值是 **undefined**。

### 2.3.3 小结
- 函数可以带参数也可以不带参数
- 声明函数的时候，函数名括号里面的是形参，形参的默认值为undefined
- 调用函数的时候，函数名括号里面的是实参
- 多个参数中间用逗号分隔
- 形参的个数可以和实参个数不匹配，但是结果不可预计，我们尽量要匹配

## 2.4 函数的返回值
### 2.4.1 return 语句
有的时候，我们会希望函数将值返回给调用者，此时通过使用return语句就可以实现。

### 2.4.2 return 终止函数
return语句之后的代码不被执行。

### 2.4.3 函数没有 return 返回 undefined
函数都是有返回值的:
1. 如果有return，则返回return后面的值
2. 如果没有return，则返回undefined

### 2.4.3 break,continue,return 的区别
- break :结束当前的循环体（如for、while )
- continue :跳出本次循环，继续执行下次循环（如for、while )
- return :不仅可以退出循环，还能够返回return语句中的值，同时还可以**结束当前的函数**体内的代码。

## 2.5 arguments 的使用
当我们不确定有多少个参数传递的时候，可以用**arguments**来获取。在JavaScript中，arguments实际上它是当前函数的一个**内置对象**。所有函数都内置了一个arguments对象，arguments对象中**存储了传递的所有实参**。

**arguments展示形式是一个伪数组**，因此可以进行遍历。伪数组具有以下特点：
- 具有length属性
- 按索引方式储存数据
- 不具有数组的push , pop等方法

```javascript
<script>
// arguments 的使用
	function fn() {
		console.log(arguments);// 里面存储了所有传递过来的实参
		console.log(arguments.length);
		console.log(arguments[0]);	
	}
	fn(1,2,3);
</script>
```
控制台输出的 arguments 如下图：
![在这里插入图片描述](https://img-blog.csdnimg.cn/21a4046f9c034701b1ddd32aa4f95e17.png)
注意：只有函数才有 arguments 对象，而且是每个函数都内置好了这个对象。

## 2.6 函数可以调用另外一个函数
因为每个函数都是独立的代码块，用于完成特殊任务，因此经常会用到函数相互调用的情况。

```javascript
<script>
	//函数是可以相互调用的
	function fn1() i
		console.log(11);
		fn2();// 在fn1 函数里面调用了fn2
	}
	fn1();
	function fn2(){
		console.log(22);
	}
</script>

```


# 3 JavaScript 作用域
## 3.1 作用域
1.1作用域概述
通常来说，一段程序代码中所用到的名字并不总是有效和可用的，而**限定这个名字的可用性的代码范围**就是这个名字的作用域。作用域的使用提高护程序逻辑的局部性，增强了程序的可靠性，减少了名字冲突。
简单来说，就是代码名字（变量）在某个范围内起作用和效果，目的是为了提高程序的可靠性，更重要的是减少命名冲突。

JavaScript 的作用域（es6）之前分为：
全局作用域 局部作用域

全局作用域：
整个script 标签 或者是一个单独的js文件

局部作用域（函数作用域）：
在函数内部就是局部作用域，这个代码的名字只在函数内部起效果和作用
## 3.2 变量的作用域
根据作用域的不同，变量分为全局变量和局部变量。
### 3.2.1 全局变量
在全局作用域下声明的变量叫做**全局变量**(**在函数外部定义的变量**)。
- 全局变量在代码的任何位置都可以使用
- 在全局作用域下var 声明的变量是全局变量
- 特殊情况下，在函数内不使用var声明的变量也是全局变量(不建议使用)
```javascript
// 1．全局变量:在全局作用域下的变量在全局下都可以使用
var num = 10; // num就是一个全局变量
console.log(num); // 打印10
function fn() {
	console.log(num);// 打印10
}
fn();
```
注意：在函数内部，没有声明直接赋值的变量也属于全局变量。

### 3.2.2 局部变量
在局部作用域下声明的变量叫做**局部变量**(**在函数内部定义的变量**)
- 局部变量只能在该函数内部使用
- 在函数内部var声明的变量是局部变量
- 函数的形参实际上就是局部变量

```javascript
// 2．局部变量 在局部作用域下的变量 在函数内部的变量就是局部变量
function fun() {
	var num1 = 10; // num1就是局部变量只能在函数内部使用
}
fun();
console.log(num1);// 报错 num1 is not defined
```
注意：函数的形参也可以看作是局部变量。

### 3.2.3 全局变量和局部变量的区别
- 全局变量:在任何一个地方都可以使用，只有在浏览器关闭时才会被销毁，因此比较占内存
- 局部变量:只在函数内部使用，当其所在的代码块被执行时，会被初始化；当代码块运行结束后，就会被销毁，因此更节省内存空间

### 3.2.4 现阶段在js中没有块级作用域
- 现阶段我们js 没有块级作用域，js的作用域：全局作用域、局部作用域。
- 我们js 也是在es6的时候新增的块级作用域
- 块级作用域{} if {} for {}

```java
// java语言的以下代码，{}外面的是不能调用num的
if(){
	int num = 10;
}
```

```javascript
// JavaScript语言的以下代码，{}外面的是能调用num的
if(3< 5){
	var num = 10;
console.log(num);

```
## 3.3 作用域链
- 只要是代码，就至少有一个作用域
- 写在函数内部的局部作用域
- 如果函数中还有函数，那么在这个作用域中就又可以诞生一个作用域
- 根据**在内部函数可以访问外部函数变量**的这种机制，用**链式查找**决定哪些数据能被内部函数访问，就称作**作用域链**


如果本层没有该变量的值，找离该变量最近的上层，简单来说就是： **就近原则**

```javascript
var num = 456;
function f1() {//外部函数
	var num = 123;
	
	function f2( {//内部函数
		console.log(num); // 123
	}
	f2();
}
f1();

```
![在这里插入图片描述](https://img-blog.csdnimg.cn/895c0a0a9eac45a99f6943b579acfda0.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMzMzkwNzAw,size_16,color_FFFFFF,t_70)
# 4 JavaScript  预解析
# 5 JavaScript 对象
## 5.1 对象
5.1.1 什么是对象？
在JavaScript中，对象是一组无序的相关**属性**和**方法**的集合，所有的事物都是对象，例如字符串、数值、数组、函数等。
对象是由**属性**和**方法**组成的。
- 属性:事物的**特征**，在对象中用**属性**来表示(常用名词)
- 方法:事物的**行为**，在对象中用**方法**来表示(常用动词)

5.1.2 为什么需要对象？
保存一个值时，可以使用**变量**，保存多个值(一组值）时，可以使用**数组**。如果要保存一个人的完整信息呢?
例如，将“张三疯”的个人的信息保存在数组中的方式为︰

```javascript
var arr =[张三疯，‘男'，,128,154];// 会带来歧义
```

JS中的对象表达结构更清晰，更强大。张三疯的个人信息在对象中的表达结构如下:

```javascript
person.name =张三疯';
person.sex ='男';
person.age =128;
person.height = 154;
```
## 5.2 创建对象的三种方式
在JavaScript中，现阶段我们可以采用三种方式创建对象( object ) :
- 利用**字面量**创建对象
- 利用**new Object**创建对象
- 利用**构造函数**创建对象

### 5.2.1 利用字面量创建对象
**对象字面量**∶就是花括号(}里面包含了表达这个具体事物（对象）的属性和方法。

**1.利用对象字面量创建对象{}**
```javascript
// var obj = {}; // 创建了一个空的对象
var obj = {
	uname: ‘张三疯",
	age: 18,
	sex: '男',
	sayHi: function() {
	console.log( ' hi~');
	}
}
```

- 里面的属性或者方法我们采取键值对的形式键属性名﹔值属性值
- 多个属性或者方法中间用逗号隔开的
- 方法冒号后面跟的是一个匿名函数

**2.使用对象**
调用对象的属性：
```javascript
// 方法1.采取对象名.属性名的形式。理解为“的”
console.log(obj.uname);
// 方法2.对象名['属性名']的形式。注意方括号里面的属性必须加引号。
console.log(obj['age']);
```
调用对象的方法：
```javascript
// 对象名.方法名()
obj.sayHi();
```
### ☆ 变量、属性、函数、方法
**1.变量和属性：**

相同点：
- 都是用来存储数据的

不同点：
- 变量：单独声明赋值，使用的时候直接写变量名，单独存在。
- 属性：对象里面的变量，不需要声明，使用的时候必须是 “对象.属性”形式，用来描述该对象的特征。

**2.函数和方法：**

相同点：
- 都是实现某种功能

不同点：
- 函数：单独存在，通过函数名()就可以调用的，
- 方法：对象里面的函数，方法不需要声明，使用“对象.方法”的形式调用，方法用来描述该对象的行为和功能。

### 5.2.2 利用new Object创建对象
跟我们前面学的 new Array() 原理一致，创建空的对象。
利用等号 “=” 赋值的方法，添加对象的属性和方法。
每个属性和方法之间用分号结束。

```javascript
// 创建一个空的对象
var obj = new Object();
// 追加属性 uname
obj.uname = '';
// 追加方法
obj.sayHi = function(){
	console.log('Hi~');
}
```
### 5.2.3 利用构造函数创建对象
前面两种方式一次只能创建一个对象，需要创建多个对象，且里面的很多属性和方法是相同的时候，可以使用构造函数创建对象。
~~构造函数里面封装的是对象。普通函数封装的是~~ 
构造函数︰是一种特殊的函数，主要用来初始化对象，即为对象成员变量赋初始值，它总与new运算符一起使用。我们可以把对象中一些公共的属性和方法抽取出来,然后封装到这个函数里面。

构造函数的语法格式：

```javascript
function 构造函数名() {
	this.属性名 = 值;
	this.方法 = function() {}
}
// 调用构造方法
new 构造函数名();
```
- 通用规范：构造函数名的首字母必须大写。
- 构造函数不需要 return ，就可以返回结果。
- 调用构造函数必须使用 new 关键字。
- 只要 new 构造函数名() 就创建了一个对象。
- 构造函数内的属性和方法前面必须要添加 this。


举例：
```javascript
// 构造函数
function Star(uname,age,sex) {
	this.name = uname;
	this.age = age;
	this.sex = sex;
	this.sing = function(song){
		console.log(song);
	}
}
// 对象
var ldh = new Star('刘德华', 18, '男');
console.log(ldh.name);
ldh.sing('冰雨');

```
**构造函数和对象**
- 构造函数，如Stars()，抽象了对象的公共部分，封装到了函数里面，它泛指某一大类( class )
- 创建对象，如new Stars()，特指某一个具体的事物，通过new关键字创建对象的过程我们也称为对象实例化
## 5.3 new 关键字
**new 关键字执行过程：**
 1. new 构造函数，在内存中创建了一个空的对象；
 2. this 指向刚才创建的空对象
 3. 执行构造函数里面的代码，给这个空对象添加属性和方法
 4. 返回这个对象
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/ffbb83e04e904b389ff8b14b523a4ef4.png)
## 5.4 遍历对象属性
**for...in**语句用于对数组或者对象的属性进行循环操作。

```javascript
//遍历对象
var obj = {
	name: ' pink老师',
	age: 18,
	sex:‘男',
	fn: function() {}
}
console.log(obj.name);
console.log(obj.age);
console.log(obj.sex);

// for in 遍历我们的对象
for(var k in obj）{
	console.log(k);// 输出属性名
	console.log(obj[k]);// 输出属性值
}
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/1117058edfd64c9cbfb3d39274154cbd.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMzMzkwNzAw,size_16,color_FFFFFF,t_70)
# JavaScript 内置对象
JavaScript中的对象分为3种:自定义对象、内置对象、浏览器对象
前面两种对象是JS基础内容，属于ECMAScript;第三个浏览器对象属于我们JS独有的，我们JS API讲解
内置对象就是指JS语言自带的一些对象，这些对象供开发者使用，并提供了一些常用的或是最基本而必要的功能（属性和方法)
JavaScript提供了多个内置对象:Math、 Date . Array、String等
## 查文档
2.1 MDN
学习一个内置对象的使用，只要学会其常用成员的使用即可，我们可以通过查文档学习，可以通过MDN/W3C来查询。
Mozilla开发者网络(MDN)提供了有关开放网络技术(Open Web )的信息，包括HTML、CSS和万维网及HTML5应用的API。
MDN: https://developer.mozilla.org/zh-CN/

2.2如何学习对象中的方法
1．查阅该方法的功能
2．查看里面参数的意义和类型
3．查看返回值的意义和类型
4．通过demo进行测试

## Math 对象
![在这里插入图片描述](https://img-blog.csdnimg.cn/85e1788f42d94c5ba398581363272e6e.png)

```javascript
// Math数学对象不是一个构造函数﹐所以我们不需要new来调用而是直接使用里面的属性和方法即可
console.log(Math.PI);
```
利用对象封装自己的数学对象，有PI属性和获取最大值和最小值的方法。

```javascript
在这里插入代码片
```
4.1 Date 概述
- Date对象和Math对象不一样，他是一个构造函数，所以我们需要实例化后才能使用
- Date实例用来处理曰期和时间

4.2 Date()方法的使用

1.获取当前时间必须实例化
```javascript
var now = new Date() ;
console. log (now) ;
```
2.Date()构造函数的参数
如果括号里面有时间，就返回参数里面的时间。例义日期格式字符串为‘2019-5-1’，可以写成new Date('2019-5-1')或者new Date('2019/5/1')

 

# Web APIs

# 1 Web APIs
## 1.1 APIs 和JS基础关联性
### 1.1.1 JS 的组成
![在这里插入图片描述](https://img-blog.csdnimg.cn/1eefaad130334c159b216e20d76c9090.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMzMzkwNzAw,size_16,color_FFFFFF,t_70)
### 1.1.2 JS 基础阶段以及 Web APIs 阶段
**JS基础阶段**
- 学习的是ECMAscript标准规定的基本语法
- 要求掌握Js 基础语法
- 只学习基本语法,做不了常用的网页交互效果
- 目的是为了Js 后面的课程打基础、做铺垫

**Web APIs阶段**
- web APIs 是w3c组织的标准
- web APIs 我们主要学习DOM和 BOM
- web APIs 是Js 所独有的部分
- 主要学习页面交互功能
- 需要使用Js 基础的课程内容做基础

Js基础学习ECMAScript 基础语法为后面作铺垫，web APIs 是  Js 的应用，大量使用 as 基础语法做交互效果


## 1.2 API 和 Web API
### 1.2.1 API
官方定义：**API** (Application Programming Interface，应用程序编程接口）是一些预先定义的函数，目的是提供应用程序与开发人员基于某软件或硬件得以访问一组例程的能力，而又无需访问源码，或理解内部工作机制的细节。
简单理解︰API是给程序员提供的一种工具，以便能更轻松的实现想要完成的功能。
### 1.2.2 Web API
**Web API**是**浏览器**提供的一套操作**浏览器功能**和**页面元素**的APl( BOM和DOM)。
现阶段我们主要针对于浏览器讲解常用的API，主要针对浏览器做交互效果。
比如我们想要浏览器弹出一个警示框，直接使用alert(‘弹出’)
MDN详细API: https://developer.mozilla.org/zh-CN/docs/Web/API
因为Web API很多，所以我们将这个阶段称为**Web APls**

### 1.2.3 API和Web API总结
1.API是为我们程序员提供的一个接口，帮助我们实现某种功能，我们会使用就可以了，不必纠结内部如何实现2.Web API主要是针对于浏览器提供的接口，主要针对于浏览器做交互效果。
3. Web API一般都有输入和输出（函数的传参和返回值），Web API很多都是方法（函数)
4.学习Web API可以结合前面学习内置对象方法的思路学习

# 2.DOM
## 2.1 DOM简介
### 2.1.1 什么是DOM
**文档对象模型**(Document Object Model，简称DOM)，是W3C组织推荐的处理可扩展标记语言（HTML或者XML)的标准**编程接口**。
w3C已经定义了一系列的DOM接口，通过这些DOM接口可以改变网页的内容、结构和样式。
### 2.1.2 DOM 树
对于HTML，DOM使得HTML形成一棵 DOM 树，包含文档、元素、节点。
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/07e78cb9902a46a09ee6437eb9d266d0.png)
- 文档：一个页面就是一个**文档**，DOM中使用**document**表示。
- 元素：页面中的所有**标签**都是元素，DOM中使用**element**表示
- 节点︰网页中的所有**内容**都是节点（标签、属性、文本、注释等），DOM中使用**node**表示。

**获取的DOM元素是一个对象，故称为 文档对象模型**

## 2.2 获取元素
DOM在我们实际开发中主要用来操作元素。
获取页面中的元素的方式：
- 根据ID获取
- 根据标签名获取
- 通过HTML5新增的方法获取
- 特殊元素获取
### 2.2.1 根据ID获取
使用`getElementByld()`方法可以获取带有ID的元素对象。
语法：
```javascript
var element = document.getElementById(id);
```

参数：
- element是一个Element 对象。如果当前文档中拥有特定ID的元素不存在则返回null.
- id是大小写敏感的字符串，代表了所要查找的元素的唯一ID.

返回值：
返回一个匹配到ID的DOM Element对象。若在当前 Document下没有找到，则返回null.

```javascript
<body>
<div id="time">2019-9-9</div>
<script>
	// 1．因为我们文档页面从上往下加载，所以先得有标签。所以我们script写到标签的下面（有解决方案，以后再说）
	// 2. get获得element元素by 通过驼峰命名法
	// 3．参数id是大小写敏感的字符串
	// 4.返回的是一个元素对象
	var timer = document.getElementById('time'); 
	console.log(timer);
	console.log(typeof timer);
	//5.console.dir 打印我们返回的元素对象，更好的查看里面的属性和方法
	console.dir(timer);
< /script>
</body>
```
### 2.2.2 根据标签名获取
使用`getElementsByTagName()`方法可以返回带有指定标签名的**对象的集合**。

**获取方式1：**
把页面中所有该标签名的元素都获取过来
`document.getElementsByTagName('标签名');`

注意:
 1. 因为得到的是一个对象的集合，所以我们想要操作里面的元素就需要遍历。
 2. 得到元素对象是动态的
 3. 如果页面中只有一个li，返回的还是伪数组的形式
 4. 如果页面中没有这个元素，返回的空的伪数组的形式



```javascript
<body>
	<ul>
		<li>知否知否，应是等你好久1</li>
		<li>知否知否，应是等你好久2</li>
		<li>知否知否，应是等你好久3</li>
		<li>知否知否，应是等你好久4</li>
		<li>知否知否，应是等你好久5</li>
	</ul>
	<script>
	 	// 返回的是，获取过来元素对象的集合，以伪数组的形式存储的
		var lis = document.getElementsByTagName('li');
		console.log(lis);
	</ script>
</ body>

```
**获取方式2：**
获取某个元素(父元素)内部所有指定标签名的子元素
`element.getElementsByTagName ('标签名');`


注意∶父元素必须是**单个对象(必须指明是哪一个元素对象)**。获取的时候不包括父元素自己，只是把子元素获取过来。

### 2.2.3 HTML5 新增的方法
注： ie9版本以上才能使用

#### 2.2.3.1 根据类名返回元素对象集合
`document.getElementsByClassName('类名');`

#### 2.2.3.2 根据指定选择器返回第一个元素对象，里面的选择器需要加符号
`document.querySelector('选择器');`

不同选择器的填写格式示例：

```javascript
// 类选择器
document.querySelector('.box');
// id 选择器
document.querySelector('#box');
// 返回页面中的第一个li标签
document.querySelector('li');
```

#### 2.2.3.3 根据指定选择器返回所有元素集合
`document.querySelectorAll('选择器");`

### 2.2.4 获取特殊元素（body、html）
1.获取 body 元素，返回body元素对象
`document.body `

2.获取 html 元素，返回html元素对象
`document.documentElement `==我觉得这里不对劲==

# DOM 重点核心
关于dom操作，我们主要针对于元素的操作。主要有创建、增、删、改、查、属性操作、事件操作。

2.3 创建
1. document.write
2. innerHTML
3. createElement

2.4 增
1.appendChild
2.insertBefore

6.3删
1.removeChild

6.4改
主要修改dom的元素属性，dom元素的内容、属性,表单的值等
1．修改元素属性: src、href、title等
2．修改普通元素内容:innerHTML、innerText
3.  修改表单元素: value、type、disabled等
4．修改元素样式: style、className

6.5查
主要获取查询dom的元素
 1. DOM提供的API方法: getElementByld、getElementsByTagName 古老用法不太推荐
 2. H5提供的新方法: querySelector、querySelectorAll提倡
3．利用节点操作获取元素:父(parentNode)、子(children)、兄(previousElementSibling,
nextElementSibling)提倡

## 2.3 事件基础
### 2.3.1 事件概述
JavaScript使我们有能力创建动态页面，而事件是可以被JavaScript侦测到的行为。
简单理解∶触发---响应机制。
网页中的每个元素都可以产生某些可以触发JavaScript的事件，例如，我们可以在用户点击某按钮时产生一个事件，然后去执行某些操作。

```javascript
<body>
	<button id="btn">唐伯虎</button>
	<script>
	// 点击一个按钮，弹出对话框
	// 1．事件是有三部分组成：事件源、事件类型、事件处理程序―我们也称为事件三要素
	// (1）事件源事件被触发的对象  谁 按钮
	var btn = document.getElementById( ' btn');
	// (2）事件类型 如何触发 什么事件 比如鼠标点击(onclick) 还是鼠标经过 还是键盘按下
	// (3）事件处理程序  通过一个函数赋值的方式完成
	btn.onclick = function() {
		alert('点秋香');
	}
	</script>
</ body>

```
### 2.3.2 执行事件的步骤
1.获取事件源
2.注册事件（绑定事件)
3.添加事件处理程序（采取函数赋值形式)

```javascript
<body>
	<div>123</div>
	<script>
		// 执行事件步骤
		// 点击div控制台输出我被选中了
		// 1．获取事件源
		var div = document.queryselector( 'div ');
		// 2.绑定事件注册事件
		// div.onclick 
		// 3.添加事件处理程序
		div.onclick = function() {
			console.log('我被选中了');
		}
	</script>
</body>

```

### 2.3.3 常见的鼠标事件
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/176eda3f44214a1e95f0e3b29bea5fc5.png)
### 2.3.4 分析事件三要素
下拉菜单三要素：

 - 事件源：下拉菜单按钮；
 - 事件：鼠标点击
 - 事件处理程序：下拉菜单的显示

关闭广告三要素：
 - 事件源：关闭按钮；
 - 事件：鼠标点击
 - 事件处理程序：广告盒子的隐藏

## 2.4 操作元素
JavaScript的DOM操作可以改变网页内容、结构和样式，我们可以利用DOM操作元素来改变元素里面的内容、属性等。注意以下都是属性。
### 2.4.1改变元素内容
innerText 和 innerHTML 方法

区别在于：
-  innerText 不识别htm1标签，非标准
-  innerHTML 识别htm1标签，W3C标准
```javascript
<body>
	<div></div>
	<script>
		// innerText 和innerHTML的区别
		var div = document.querySelector('div');
		// 1. innerText 不识别htm1标签，非标准
		// 会原样输出单引号内的内容
		div.innerText = '<strong>今天是:</strong> 2019'; 
		// 2. innerHTML 识别htm1标签，W3C标准
		// “今天是”会被html标签<strong></strong>加粗
		div.innerHTML = '<strong>今天是:</strong> 2019';
	</script>
</body>


```
这两个属性是可读写的，可以获取元素里面的内容。
1.从起始位置到终止位置的内容,但它去除 html 标签，同时空格和换行也会去掉
```javascript
element.innerText
```
2.起始位置到终止位置的全部内容，包括html标签，同时保留空格和换行
```javascript
element.innerHTML
```
代码如下：
```javascript
<body>
    <p>
        我是文字
        <span>123</span>
    </p>
	<script>
        var p = document.querySelector('p');
        console.log(p.innerText);
        console.log(p.innerHTML);
    </script>
</body>
```
运行结果如下：
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/05dcb9da75894b0c86416fb6f1378f87.png)
### 2.4.2 常用元素的属性操作
1.  innerText、 innerHTML，改变元素内容
2.  src、 href
3.  id、alt、title

案例：点击按钮，修改图片的url

```javascript
<body>
    <div>
        <button class="btn1">丽娘</button>
        <button class="btn2">镜玄</button>
    </div>
    <img src="" alt="">
    <script>
    	// 获取元素
        var btn1 = document.querySelector('.btn1');
        var btn2 = document.querySelector('.btn2');
        var img = document.querySelector('img');
        // 注册事件 处理程序
        btn1.onclick = function() {
            img.src = 'images/liniang.jpg';
            img.title = '丽娘';
        }
        btn2.onclick = function() {
            img.src = 'images/jingxuan.jfif';
            img.title = '镜玄';
        }
    </script>
</body>
```
案例:分时显示不同图片,显示不同问候语 --206集
根据不同时间，页面显示不同图片，同时显示不同的问候语。
如果上午时间打开页面，显示上午好，显示上午的图片。
如果下午时间打开页面，显示下午好，显示下午的图片。
如果晚上时间打开页面，显示晚上好，显示晚上的图片。

```javascript
在这里插入代码片
```
# 1 事件高级
![在这里插入图片描述](https://img-blog.csdnimg.cn/d1ffea9bdae4436dad278e02b61fec87.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMzMzkwNzAw,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/e7bdfcdd7e1e4fee999e2a7445a26953.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMzMzkwNzAw,size_16,color_FFFFFF,t_70)
## 1.1 注册事件（绑定事件）

给元素添加事件，称为**注册事件**或者**绑定事件**。
注册事件有两种方式:**传统方式**和**方法监听注册方式**

**传统注册方式**
- 利用on开头的事件onclick
- \<button onclick= "alert('hi~)" ></button:
- btn.onclick = function(){}
- 特点：注册事件的**唯一性**
- 同一个元素同一个事件只能设置一个处理函数，最后注册的处理函数将会覆盖前面注册的处理函数

**方法监听注册方式**
- w3c标准推荐方式
- addEventListener()，它是一个方法
- IE9之前的IE不支持此方法，可使用attachEvent()代替
- 特点:同一个元素同一个事件可以注册多个监听器
- 按注册顺序依次执行
## 1.1.1 传统注册方式
>btn.onclick = function(){}

### 1.1.2 addEventListener 事件监听方式
eventTarget.addEventListener()方法将指定的监听器注册到eventTarget(目标对象）上，当该对象触发指定的事件时,就会执行事件处理函数。
> eventTarget .addEventListener(type, listener[,usecapture])

该方法接收三个参数︰
- type：事件类型字符串，比如click、mouseover，注意这里**不要**带on；
- listener：事件处理函数，事件发生时，会调用该监听函数；
- useCapture：可选参数，是一个布尔值，默认是false。学完DOM事件流后，我们再进一步学习。

```javascript
<body>
    <button>传统注册事件</button>
    <button>方法监听注册事件</button>
    <script>
        var btns = document.querySelectorAll('button');
        // 1.传统方式注册事件
        // 同一个元素，同一个事件，可以添加多个监听器。只执行最后注册的处理函数
        btns[0].onclick = function() {
            alert("传统注册事件-1！")
        }
        btns[0].onclick = function() {
            alert("传统注册事件-2！")
        }
        // 2.方法监听注册事件
        // 同一个元素，同一个事件，可以添加多个监听器。按注册顺序依次执行
        btns[1].addEventListener('click',function(){
                alert("方法监听注册事件-1");
            })
        btns[1].addEventListener('click',function(){
                alert("方法监听注册事件-2");
            })
    </script>
</body>
```
### 1.1.3 attachEvent 事件监听方式
☆ 该特性是非标准的,请尽量不要在生产环境中使用它!

> eventTarget.attachEvent (eventNameWithOn,callback)

eventTarget.attachEvent ()方法将指定的监听器注册到eventTarget(目标对象）上，当该对象触发指定的事件时，指定的回调函数就会被执行。
该方法接收两个参数︰
- eventNameWithOn：事件类型字符串，比如onclick、onmouseover ，这里要带on
- callback：事件处理函数，当目标触发事件时回调函数被调用

### 1.1.4 注册事件兼容性解决方案

```javascript
function addEventListener (element, eventName, fn){
	//判断当前浏览器是否支持addEventListener方法
	if (element.addEventListener){
		element.addEventListener(eventName, fn);//第三个参数默认是false
	} else if (element.attachEvent) {
		element.attachEvent ( 'on'+ eventName,fn);
		} else {
		// 相当于element.onclick = fn;
		element["on" + eventName] = fn;
}
```
兼容性处理的原则∶首先照顾大多数浏览器，再处理特殊浏览器

## 1.2 删除事件（解绑事件)
2.1删除事件的方式

1.传统注册方式
>eventTarget.onclick = null;

⒉.方法监听注册方式

>eventTarget.removeEventListener(type，listener [，usecapture]) ;
## 1.3 DOM 事件流
## 1.4 事件对象
### 1.4.1 什么是事件对象：
- 官方解释：event 对象代表事件的状态，比如键盘按键的状态、鼠标的位置、鼠标按钮的状态等。
- 简单理解：事件发生后，**跟事件相关的一系列信息数据的集合**都放到这个对象里面，这个对象就是事件对象 event ，它有很多属性和方法。比如鼠标点击里面就包含了鼠标的相关信息（鼠标坐标等），如果是键盘事件里面就包含的键盘事件的信息（比如判断用户按下了哪个键）

### 1.4.2 使用语法
> eventTarget.onciick = function (event) { } 
> eventTarget.addEventListener ( 'click ', function(event){}
> // 这个event就是事件对象，我们还喜欢的写成e 或者evt


- 这个 event 是个形参，系统帮我们设定为事件对象，不需要传递实参。
- 当我们注册事件时，event 对象就会被系统自动创建，并以此传递给事件监听器（事件处理函数）


```javascript
//传统注册事件的事件对象
var div = document.querySelector('div');
var div = document.querySelector( 'div' );
	div.onclick = function(event){
		console.log(event);
	}
```

```javascript
// 方法监听注册对向的事件对象
var div.addEventListener('click', function(e) {
	console.log(e);
	}
```
### 1.4.3 事件对象的兼容性方案

事件对象本身的获取存在兼容问题:
1.标准浏览器中是浏览器给方法传递的参数，只需要定义形参e就可以获取到。
⒉.在IE6~8中，浏览器不会给方法传递参数，如果需要的话，需要到window.event中获取查找。

```javascript
var div = document.queryselector( 'div ');
div.onclick = function(e){
//console.log(e); // ie678 中是 undefined
//console.loe(window.event);// ie678 中可以返回事件对象
e =e || window.e
console.log(e);
}
```
实际开发里放心使用e，不用 e =e || window.e。
### 1.4.4 事件对象的常见属性和方法
![在这里插入图片描述](https://img-blog.csdnimg.cn/c2e9a05bf2cc4f8c81d2a67b205d81f6.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMzMzkwNzAw,size_16,color_FFFFFF,t_70)
## 1.5 阻止事件冒泡
### 1.5.1阻止事件冒泡的两种方式
事件冒泡:开始时由最具体的元素接收，然后逐级向上传播到到DOM最顶层节点。
事件冒泡本身的特性，会带来的坏处，也会带来的好处，需要我们灵活掌握。

标准写法:利用事件对象里面的stopPropagation ()方法
> e.stopPropagation()

非标准写法： IE 6~8 利用事件对象 cancelBubble 属性
> e.cancelBubble = true;
```javascript
<div class="father">
	<div class="son">son儿子</div>
</div>
<script>
// 常见事件对象的属性和方法
// 阻止冒泡 dom 推荐的标准 stopPropagation()
var son = document.queryselector( '.son ');
son.addEventListener( 'click ' , function(e){
	alert( ' son ' );
	e.stopPropagation();// 停止传播
}, false);
var father = document.queryselector( '.father');
father.addEventListener('click' , function() {
	alert( 'father ' );
}, false);
document.addEventListener('click', function() {
	alert( 'document ' );
}
</script>

```
### 1.5.2 阻止事件默哀跑的兼容性解决方案

```javascript
if(e && e.stopPropagation){
	e.stopPropagation();
} else{
	window .event.cancelBubble = true;
)

```
## 1.6 事件委托（代理、委派）
事件冒泡本身的特性，会带来的坏处，也会带来**好处**，需要我们灵活掌握。

生活中有如下场景∶
咱们班有100个学生，快递员有100个快递，如果一个个的送花费时间较长。同时每个学生领取的时候，也需要排队领取，也花费时间较长，何如?
**解决方案**︰快递员把100个快递，委托给班主任，班主任把这些快递放到办公室，同学们下课自行领取即呵。
优势︰快递员省事，委托给班主任就可以走了。同学们领取也方便，因为相信班主任。

案例：点击每个li，弹出对话框
```html
<ul>
	<li>知否知否，应该有弹框在手</l>
	<li>知否知否，应该有弹框在手</li>
	<li>知否知否，应该有单框在手</li>
	<li>知否知否，应该有单框在手</li>
	<li>知否知否，应该有弹框在手</li>
</ul>

```
以前需要给每个li注册事件，是非常辛苦的，而且访问DOM的次数越多，这就会延长整个页面的交互就绪时间。

**事件委托**
事件委托也称为事件代理，在jQuery里面称为事件委派。

**事件委托的原理**
<font color="red">不是每个子节点单独设置事件监听器，而是事件监听器设置在其父节点上，然后利用冒泡原理影响设置每个子节点。</font>
以上案例∶给ul注册点击事件，然后利用事件对象的target 来找到当前点击的li，因为点击 lü，事件会冒泡到ul上，ul有注册事件，就会触发事件监听器。

**事件委托的作用**
我们只操作了一次DOM，提高了程序的性能。

```html
<script>
//事件委托的核心原理:给父节点添加侦听器，利用事件冒泡影响每一个子节点

var ul = document.querySelector( 'ul ');
ul.addEventListener( 'click ' , function(e){
	alert'知否知否，点我应有弹框在手!'); // 点击li，也会弹框提示
	// e.target 可以获取点击的对象
	// 给点击的 li 设置背景颜色
	e.taget.style.backgroundColor = 'pink';
})
</script>

```

## 1.7 常用的鼠标事件![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/35c097480eaa4de8a325d4f1fbe67173.png)
1.禁止鼠标右键菜单
contextmenu 主要控制应该何时显示上下文菜单，主要用于程序员取消默认的上下文菜单。

```html
document.addEventListener ('contextmenu', function(e){ 		
	e.preventDefault () ; 
})
```

2.禁止鼠标选中（selectstart 开始选中）
```html
document.addEventListener ('selectstart', function(e){ 		
	e.preventDefault () ; 
})
```
## 1.6 常用的键盘事件
# BOM 浏览器对象模型
![在这里插入图片描述](https://img-blog.csdnimg.cn/2be992dbc069435587154a853800db3b.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMzMzkwNzAw,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/d306eafb25e34cb4b557b1b1333110de.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMzMzkwNzAw,size_16,color_FFFFFF,t_70)
## 3.BOM 概述
## 3.1什么是BOM
BOM (Browser Object Model)即**浏览器对象模型**，它提供了独立于内容而**与浏览器窗口进行交互的对象**，其核心对象是window。

BOM由一系列相关的对象构成，并且每个对象都提供了很多方法与属性。
BOM缺乏标准，JavaScript语法的标准化组织是ECMA，DOM的标准化组织是W3C，BOM最初是Netscape浏览器标准的一部分。
![在这里插入图片描述](https://img-blog.csdnimg.cn/f28221195aed4de58ff308259139de7a.png)
## 3.2 BOM的构成
BOM比 DOM更大，它包含DOM。
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/fc6781b19a104e078004d0112e1608b2.png)
**window对象是浏览器的顶级对象**，它具有双重角色。

 1. 它是JS访问浏览器窗口的一个接口。
 2. 它是一个全局对象。定义在全局作用域中的变量、函数，都会变成window对象的属性和方法。

在调用的时候可以省略window，前面学习的对话框都属于window对象方法，如alert)、prompt()等。

注意：window下的一个特殊属性window.name

## 3.2 window 对象的常见事件
### 3.2.1窗口加载事件

> window.onload = function () {}
> 或者
> window.addEventListener( "load", function(){});

window.onload是窗口（页面）加载事件，当**文档内容完全加载完成**会触发该事件(包括图像、脚本文件、CSS文件等)，就调用的处理函数。

```javascript
<script>
window.onload = function() {
	var btn = document.queryselector('button');
	btn.addEventListener( 'click', function() {
		alert( '点击我');
	})
}
</script>
<button></button>
```
注意︰
 1. 有了window.onload就可以把JS代码写到页面元素的上方（甚至是文件外），因为onload是等页面内容全部加载完毕，再去执行处理函数。
 2. window.onload是传统注册事件方式，只能写一次，如果有多个，会以最后一个window.onload为准。
 3. 如果使用 addEventListener 则没有限制

```javascript
window.addEventListener('load', function() {
	var btn = document.queryselectorK('button');
	btn.addEventListener('click',function() {
		alert('点击我');
	})
})
```

> document . addEventListener('DOMContentLoaded',function(){})

- DOMContentLoaded 事件触发时，仅当**DOM加载完成**，不包括样式表，图片 、flash等等。
- le9以上才支持.
- 如果页面的图片很多的话,从用户访问到 onload 触发可能需要较长的时间,交互效果就不能实现，必然影响用户的体验，此时用DOMContentLoaded事件比较合适。

### 3.2.2 调整窗口大小事件

> window.onresize = function (){ }
> window . addEventListener ( "resize" , function(){};

window .onresize 是调整窗口大小加载事件，当触发时就调用的处理函数。
注意︰
1.只要窗口大小发生像素变化，就会触发这个事件。
2.我们经常利用这个事件完成响应式布局。window.innerWidth 当前屏幕的宽度.

```javascript
<body>
	<script>
		window.addEventListener('load', function() {
			var div = document.queryselector( 'div ' );
			window.addEventListener('resize', function() {
				console.log(window.innerwidth);
				console.log('变化了');
				if (window.innerwidth <= 800{
					div.style.display = 'none';
				} else {
					div.style.display = 'bIock;
				}
			})
		})
	</script>
	<div></div>
</body>
```
## 3.3 定时器
window对象给我们提供了2个非常好用的方法-**定时器**。
- setTimeout()
- setInterval()

### 3.3.1 setTimeout() 定时器
setTimeout()方法用于设置一个定时器，该定时器在定时器到期后执行调用函数。
>window .setTimeout (调用函数，[延迟的毫秒数]);

注意：
- 这个window在调用的时候可以省略
- 这个调用函数可以直接写函数，或者写函数名或者采取字符串‘函数名()'三种形式，其中第三种不推荐
- 这个延时时间单位是毫秒，如果省略默认的是0。
- 2000ms = 2s
- 因为页面中定时器可能有很多，所以我们经常给定时器赋值一个标识符(名字)。


1.这个调用函数可以直接写**函数**，代码如下：
```javascript
<script>
	// 语法规范: window.setTimeout(调用函数，延时时间);
	
	setTimeout(function() {
		console.log('时间到了');
	}, 2000);
</script>
```
2.这个调用函数也可以写**函数名**，代码如下：
```javascript
<script>
	// 这个调用函数可以直接写函数，也可以写函数名
	function callback(){
		console.log('哈哈！')
	}
	setTimeout(callback, 2000);
	
	// 还有一种写法，可以写 '函数名()'，不提倡
	setTimeout('callback()', 2000);
</script>
```
3.页面中可能有很多的定时器，我们经常给定时器加标识符(名字)

```javascript
<script>
	var timer1 = setTimeout(callback, 3000);
	var timer2 = setTimeout(callback,5000);
</script>

```
**☆ 回调函数**
setTimeout(这个调用函数我们也称为**回调函数callback**。
普通函数是按照代码顺序直接调用的。
而这个函数需要等待时间，时间到了才会调用这个函数，因此成为回调函数。
简单理解︰回调，就是回头调用的意思。上一件事干完，再**回**头**调**用这个函数。
以前我们讲的 element.onclick= function() {} 或者element.addEventListener(click" ,fn); 里面的函数也是 回调函数。

### 3.3.2 停止 setTimeout() 定时器
clearTimeout() 方法取消了先前通过调用 setTimeout (）建立的定时器。

>window.clearTimeout (timeoutID)

注意：
- window可以省略
- 里面的参数 timeoutID 是定时器的标识符

使用代码如下：
```javascript
<body>
	<button>点击停止定时器</button>
	<script>
		var btn = document.querySelector('button');
		var timer = setTimeout(function() {
			console.log('爆炸了');
		}, 5000);
		btn.addEventListener('click' , function() {
			clearTimeout(timer);
		})
	</script>
</body>
```
### 3.3.3  setInterval() 定时器
setlnterval() 方法重复调用一个函数，每隔这个时间，就去调用一次回调函数。
>window . setInterval(回调函数，[间隔的毫秒数]);

### 3.3.5  this
**this的指向**在函数定义的时候是确定不了的，只有函数**执行**的时候，才能确定this到底指向谁，一般情况下this的最终指向的是那个**调用它的对象**。
现阶段，我们先了解一下几个this指向
1.全局作用域或者普通函数中this指向全局对象window(注意定时器里面的this指向window )

# 4 PC端网页特效
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/a71f03c83f024a10adfbd2caae4ffc5c.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/098ff50d810648a2b5850b479ea91b51.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMzMzkwNzAw,size_16,color_FFFFFF,t_70)
## 4.1 元素偏移量 offset 系列
### 4.1.1 offset 概述
offset翻译过来就是偏移量，我们使用offset系列相关属性可以**动态的**得到该元素的位置（偏移)、大小等。
- 获得元素距离带有定位父元素的位置
- 获得元素自身的大小(宽度高度)
- 注意:返回的数值都不带单位
![在这里插入图片描述](https://img-blog.csdnimg.cn/26a8b72785804744a5f1312e5c52dd46.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMzMzkwNzAw,size_16,color_FFFFFF,t_70)

```javascript
// 1.可以得到元素的偏移位置返回的不带单位的数值
console.log(father.offsetTop);
console.log(father.offsetLeft);
//它以带有定位的父亲为准﹑如果么有父亲或者父亲没有定位则以 body为准
console.log(son.offsetLeft);
var w = document.querySelector('.w');
// 2.可以得到元素的大小宽度和高度是包含padding + border + width
console.log(w.offsetwidth);
console.log(w.offsetHeight);
// 3．返回带有定位的父亲否则返回的是body
console.log(son.offsetParent);
console.log(son.parentNode);//返回父亲是最近一级的父亲亲爸爸不管父亲有没有定位

```
### 4.1.2 offset 与 style 区别
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/96513ef59ad44287a2b0555483bf1ba2.png)
案例：获取鼠标在盒子内的坐标 

 

 # JavaScript 函数进阶

# 1 函数的定义和调用
1.1函数的定义方式
1.函数声明方式function关键字(命名函数)

# 2 this
# 3 严格模式
# 4 高阶函数
# 5 闭包
## 5.1 变量作用域
变量根据作用域的不同分为两种∶全局变量和局部变量。
1.函数内部可以使用全局变量。
2.函数外部不可以使用局部变量。
3.当函数执行完毕，本作用域内的局部变量会销毁。
## 5.2 什么是闭包
**闭包**( closure )指有权访问另一个函数作用域中变量的**函数**。----- JavaScript高级程序设计

简单理解就是，一个作用域可以访问另外一个函数内部的局部变量。

```html
  <script>
    // 闭包（closure）指有权访问另一个函数作用域中变量的函数
    function fn() {
      var num = 10;
      // fun()函数中可以访问fn函数作用域中的局部变量的num
      function fun() {
        console.log(num);// 10
      }
      fun();
    }
    fn();
  </script>
```
利用Chrome浏览器查看有没有闭包的产生。点开“Sources”，在语句`fn();`上打断点后刷新页面。
运行到`fn();`时，fn()还没有被调用，是在最外层，是全局作用域Window
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/15efc0b447be4f91ab12e6f37d639c77.png)
点击F11，执行下一步。进入局部作用域 -- fn的作用域内。在fn的局部作用域里，有fun函数、num变量和this。
![在这里插入图片描述](https://img-blog.csdnimg.cn/606963e040574aeb862c112184505313.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_26,color_FFFFFF,t_70,g_se,x_16)
执行下一步，直到进入fun函数的作用域内（如下图）。Scope里面多了一个参数-- closure，里面有个num变量。
意思是：==fn是一个闭包（待确认，感觉与解释不对应。老师确实说的是，被访问的变量所在的函数是闭包函数）==。可以访问fn函数作用域里的num这个变量。
![在这里插入图片描述](https://img-blog.csdnimg.cn/adbade8b82b04bfa907373217d78a750.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_26,color_FFFFFF,t_70,g_se,x_16)

## 5.3 闭包的作用
闭包的主要作用：延伸了变量的作用范围。
△ num变量不会等函数执行完毕就销毁，只有等所有的函数都执行完了才销毁。
△ fn外面的作用域可以访问fn内部的局部变量。

便于理解的写法：
```html
  <script>
    // 使 fn外面的作用域可以访问fn内部的局部变量
    function fn() {
      var num = 10;
      // fun()函数可以访问fn函数作用域中的局部变量的num
      function fun() {
        console.log(num);// 10
      }
      return fun;
    }
    
    var f = fn(); // 调用fn()：对num进行赋值，并且返回fun，f存储fun()
    // 类似于
    // var f =  function fun() {
    //   console.log(num);
    // }
    
    // f函数一调用就会执行fun函数，因为存的是fun()。
    // fun()函数本身在fn函数中，故可以访问fn函数中的变量。
    f();
  </script>
```
简易写法 -- 将fun函数，写成匿名函数：
```html
  <script>
    // 使 fn外面的作用域可以访问fn内部的局部变量
    function fn() {
      var num = 10;
      // 简易写法：
      return function() {
        console.log(num);// 10
      }
    }
    var f = fn(); // 调用fn()，对num进行复制，并且返回fun，f存储fun()
    // f函数一调用就会执行fun函数，因为存的是fun()。
    // fun()函数本身在fn函数中，故可以访问fn函数中的变量。
    f();
  </script>
```

## 5.4 闭包的应用
应用1：点击li输出对应的索引号
```html
  <ul class="nav">
    <li>草莓</li>
    <li>芒果</li>
    <li>香蕉</li>
    <li>火龙果</li>
  </ul>
  <script>
    // 1.之前的做法：利用动态添加属性的方式
    var lis = document.querySelector('.nav').querySelectorAll('li');
    for (var i = 0; i < lis.length; i++) {
      lis[i].index = i;
      lis[i].onclick = function () {
        console.log(this.index);
      }
    }

    // 2.利用闭包循环注册点击事件
    var lis = document.querySelector('.nav').querySelectorAll('li');
    for (var i = 0; i < lis.length; i++) {
      // 利用for循环创建4个立即执行函数
      // 每次循环都会创建一个立即执行函数
      (function(i) {
        lis[i].onclick = function () {
          console.log(i);
        }
      })(i);
    }

  </script>
```
应用2：循环中的setTimeout()

```javascript
// 2.利用闭包得到li的索引值
    var lis = document.querySelector('.nav').querySelectorAll('li');
    for (var i = 0; i < lis.length; i++) {
      // 利用for循环创建4个立即执行函数
      // 每次循环都会创建一个立即执行函数
      (function(i) {
        setTimeout(() => {
          // console.log(i);
          console.log(lis[i].innerText);
        }, 3000)
      })(i)
    }
```
应用3：计算打车价格

```javascript
  <script>
    //闭包应用-计算打车价格
    //打车起步价13(3公里内)，之后每多一公里增加5块钱．用户输入公里数就可以计算打车价格
    //如果有拥堵情况,总价格多收取10块钱拥堵费
    var car = (function() {
      var start = 13;
      var total = 0;
      return {
        price: function(n) {
          if (n <= 3) {
            total = start;
          } else {
            total = start + (n - 3) * 5;
          }
          return total;
        },
        yd: function(flag) {
          return flag ? total + 10 : total;
        }
      }
    })();
    console.log(car.price(5));//23 = 13 + 5 * 2
    console.log(car.yd(true));//33 = total + 10
    
    console.log(car.price(1));//13
    console.log(car.yd(false));// total
  </script>
```
https://www.bilibili.com/video/BV1Ki4y1T7RF?p=69 待补

# 6 递归

 

 JavaScript进阶面向对象ES6

 #  

# 1.JavaScript 面向对象

> **目标：**
> 能够说出什么是面向对象
> 能够说出类和对象的关系心
> 能够使用class 创建自定义类
> 能够说出什么是继承


## 1.1 面向对象编程介绍
###  1.1.1 两大编程思想
- 面向过程
- 面向对象

### 1.1.2 面向过程编程POP（Process-oriented progrmming）
面向过程就是分析出解决问题所需要的步骤，然后用函数把这些步骤一步一步实现，使用的时候再一个一个的依次调用就可以了。
面向过程，就是按照分析好了的步骤，按照步骤解决问题。

### 1.1.3 面向对象编程OOP(Object Oriented Programming)
<font color=red>**面向对象**是把事务分解成为一个个对象，然后由对象之间分工与合作。</font>
面向对象是以对象功能来划分问题，而不是步骤。

在面向对象程序开发思想中,每一个对象都是功能中心，具有明确分工。
面向对象编程具有灵活、代码可复用、容易维护和开发的优点，更适合多人合作的大型软件项目。

面向对象的特性:
- 封装性
- 继承性
- 多态性

### 1.1.4 面向过程和面向对象的对比
![在这里插入图片描述](https://img-blog.csdnimg.cn/1e03ca8bf3bd4a25ad62337c63ac641c.png)
## 1.2 ES6中的类和对象
面向对象
面向对象更贴近我们的实际生活,可以使用面向对象描述现实世界事物.但是事物分为具体的事物和抽象的事物
手机→						     抽象的(泛指的)
鼠标指向的手机→ 		 具体的(特指的)

面向对象的思维特点:
1．抽取（抽象）对象共用的属性和行为组织(封装)成一个类(模板)
2.对类进行实例化,获取类的对象

面向对象编程我们考虑的是有哪些对象，按照面向对象的思维特点,不断的创建对象,使用对象,指挥对象做事情.

### 1.2.1 对象
现实生活中∶万物皆对象，对象是一个具体的事物，看得见摸得着的实物。例如，一本书、一辆汽车、一个人可以是“对象”，一个数据库、一张网页、一个与远程服务器的连接也可以是“对象”。
**在JavaScript 中，对象是一组无序的相关属性和方法的集合，所有的事物都是对象**，例如字符串、数值、数组、函数等。

对象是由属性和方法组成的:
- 属性：事物的特征，在对象中用属性来表示(常用名词)
- 方法：事物的行为，在对象中用方法来表示(常用动词)

### 1.2.2 类class
在ES6中新增加了类的概念，可以使用class关键字声明一个类，之后以这个类来实例化对象。

**类**抽象了对象的公共部分，它**泛指**某一大类( class )
**对象特指**某一个，通过类实例化一个具体的对象

面向对象的思维特点:
1.抽取(抽象）对象共用的属性和行为组织(封装)成一个类(模板)
2．对类进行实例化,获取类的对象

### 1.2.3 创建类
语法：

```javascript
// 类名习惯性定义首字母大写
class ClassName {
	// class body
}
```

创建实例

```javascript
var xx = new name();
```
注意：类必须使用 new 实例化对象。

### 1.2.4 类 constructor 构造函数
**constructor()方法**是类的构造函数(默认方法)，用于**传递参数,返回实例对象**，通过 new 命令生成对象实例时，自动调用该方法。如果没有显示定义,类内部会自动给我们创建一个constructor()

```javascript
// 1. 通过 class 关键字创建类，类名习惯性定义首字母大写
class Star {
	// 2.类里面有个constructor函数,可以接受传递过来的参数,同时返回实例对象
	// 3.constructor函数只要new生成实例时,就会自动调用这个函数，如果我们不写这个函数,类也会自动生成这个函数
	constructor(uname, age) {
		this.uname = uname;
		this.age = age;
	}
}
// 2.生成实例 new 不能省略
var ldh = new Star('刘德华', 18);
var zxy = new Star('张学友',20);
console.log(ldh);
console.log(zxy);
```
注意语法规范，创建类类名后面不要加小括号,生成实例类名后面加小括号，构造函数不需要加function

### 1.2.5  类添加方法
语法∶

```javascript
class Person {
	constructor(name, age){  // constructor构造器或者构造函数
		this.name = name;
		this.age = age;
	}
	// 类里面所有的函数不需要写 function
	// 类里面，多个函数方法之间不需要逗号分隔
	say () {
		console.log (this.name + '你好');
	}
}
```

## 1.3.类的继承
### 1.3.1 继承
继承：子类可以继承父类的一些属性和方法。
语法：

```javascript
class Father{   // 父类
}
class Son extends Father {  //子类继承父类
}

```
### 1.3.2 super
**super关键字**用于访问和调用对象父类上的函数。可以调用父类的构造函数，也可以调用父类的普通函数。

**1.调用父类的构造函数**
super 关键字可以调用父类的构造方法，可以写在子类的构造方法中，从而给父类的属性赋值。
避免出现通过子类构造方法，赋值给的是子类的属性，导致父类的方法无法使用的情况。

以下是这种情况的说明：

父类 Father 如下：
```javascript
class Father {
	constructor(×,y) {
		this.x =X;
		this.y = y;
	}
	sum() {
		console.log(this.x + this.y);
	}
}
```
想要子类 Son 继承它的 sum 方法。按照如下代码写的话，会出现问题。
```javascript
class Son extends Father {
	// 这个地方这样写的话，子类实例化的时候是赋值给了子类的属性 x和y
	constructor(×,y) {
		this.x = X;
		this.y = y;
	}
}
// 这个Son类的实例的属性x和y分别是1和2
var son = new Son(1,2);
// son 类继承的sun 方法，算的是父类的属性x和y的和，无法得到结果。
son.sum();
```
正确的写法应该是：
```javascript
class Son {
	constructor(x,y) {
		super(x,y);//调用了父类的构造函数
	}
}
// new 命令生成子类的实例时，自动调用构造函数，把 1和2 传给了子类的构造函数的 x和y
// 执行super(x,y)语句,调用了父类的构造函数
// 父类中的x和y 赋了值，分别是 1和2
var son = new Son(1,2); 
// 计算父类的属性：x和y 的和。结果是3.
son.sum();
```
**2.super关键字调用父类的普通函数**

```javascript
class Father {
	say() {
		return "我是爸爸';
	}
}
class Son extends Father {
	say() {
		console.log('我是儿子');
		// super.say()就是调用父类中的普通函数say()
		console.log(super.say() + '的儿子');
	}
}
var son = new Son();
son.say();

```

☆ 继承中的属性或者方法查找原则（就近原则）：
- 如果实例化子类输出一个方法,先看子类有没有这个方法,如果有就先执行子类的。
- 如果子类里面没有,就去查找父类有没有这个方法,如果有,就执行父类的这个方法(就近原则）

**3.子类继承父类方法，同时扩展自己方法**
在子类的构造函数中：
- 使用 super关键字，在子类实例化时给父类的构造函数传值
- 使用 this 关键字，在子类实例化时给子类的属性赋值
- 
注意:子类在构造函数中使用super,必须放到this 前面(必须先调用父类的构造方法,再使用子类构造方法)

```javascript
class Father {
	constructor(×,y){
	// 构造函数里面的 this 指的是 创建的实例对象
	this.x = X;
	this.y = y;
}
	sum() {
		console.log(this.× + this.y);
	}
}
//子类继承父类加法方法同时扩展减法方法
class Son extends Father {
	constructor(x,y) {
		// 利用super 调用父类的构造函数
		// super 必须在子类this 之前
		super(x,y);
		
		this.x = x;
		this.y = y;
		
	}
	// subtract 中的this，指的是 实例对象son，因为son 调用了这个函数
	subtract() {
		console.log(this.x - this.y);
	}
}
var son = new Son(5,3);
son.subtract();
```
☆ 三个注意点；

 1. 在ES6中类没有变量提升，所以必须先定义类，才能通过类实例化对象
 2. 类里面的共有的属性和方法，一定要加 this 使用
 3. 类里面的this指向问题.
 4.  constructor里面的this指向实例对象,方法里面的this指向这个方法的调用者


## 1.4.面向对象案例
案例：面向对象版tab栏切换
功能需求:
1．点击 tab栏,可以切换效果.
2．点击＋号,可以添加tab项和内容项.
3．点击x号,可以删除当前的tab项和内容项.
4．双击tab项文字或者内容项文字可以修改里面的文字内容.

抽象对象: 
Tab 对象
1．该对象具有切换功能
2．该对象具有添加功能
3．该对象具有删除功能
4．该对象具有修改功能


# 2.构造函数和原型
> **目标：**
> - 能够使用构造函数创建对象
> - 能够说出原型的作用
> - 能够说出访问对象成员的规则
> -  能够使用ES5新增的一些方法

## 2.1 构造函数和原型
### 2.1.1 概述
在典型的OOP的语言中( 如Java )，都存在类的概念，类就是对象的模板，对象就是类的实例，但在ES6之前，JS中并没有引入类的概念。
ES6，全称ECMAScript 6.0 ，2015.06发版。但是目前浏览器的JavaScript是 ES5 版本，大多数高版本的浏览器也支持ES6，不过只实现了5S6的部分特性和功能。
在ES6之前，对象不是基于类创建的，而是用一种称为**构建函数**的特殊函数来定义对象和它们的特征。

创建对象可以通过以下三种方式：
1.对象字面量
2.new Object()
3.自定义构造函数

```javascript
// 方法一：对象字面量
var obj1 = {};

// 方法二： new Object()
var obj2 = new Object();

// 方法三：自定义构造函数
function Star(uname, age) {
	this.uname = uname;
	this.age = age;
	this.sing = function(){
		console.log('会唱歌')
	}
}
var ldh = new Star('刘德华',18);
ldh.sing();
```
### 2.1.2 构造函数
**构造函数**是一种特殊的函数，主要用来初始化对象，即为对象成员变量赋初始值，它总与new一起使用。我们可以把对象中一些公共的属性和方法抽取出来，然后封装到这个函数里面。
在JS中，使用构造函数时要注意以下两点︰
1．构造函数用于创建某一类对象，其**首字母要大写**
2．构造函数要**和 new 一起使用**才有意义

new 在执行时会做四件事情：

 1. 在内存中创建一个新的空对象。
 2. 让 this指向这个新的对象。 
 3. 执行构造函数里面的代码，给这个新对象添加属性和方法。
 4. 返回这个新对象（所以构造函数里面不需要return ).

JavaScript的构造函数中可以添加一些成员，可以在构造函数本身上添加，也可以在构造函数内部的this上添加。通过这两种方式添加的成员，就分别称为**静态成员**和**实例成员**。

**静态成员**︰在构造函数本身上添加的成员称为静态成员，只能由构造函数本身来访问。如sex。
**实例成员**∶在构造函数内部通过 this 添加的对象成员称为实例成员，只能由实例化的对象来访问。如uname、age、sing。

```javascript
function Star(uname, age) {
	// 1.在构造函数内部通过 this 添加的对象成员称为实例成员
	this.uname = uname;
	this.age = age;
	this.sing = function(){
		console.log('会唱歌')
	}
}
var ldh = new Star('刘德华',18);
// 实例成员 只能由实例化的对象来访问
ldh.sing();
// 2.在构造函数本身上添加的成员称为静态成员
Star.sex = '男';
// 静态成员 只能由构造函数本身来访问
console.log(Star.sex)
```

### 2.1.3 构造函数的问题
构造函数方法很好用，但是存在浪费内存的问题。
![在这里插入图片描述](https://img-blog.csdnimg.cn/7d7cd956c0284f9eaa798116d6f7c142.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMzMzkwNzAw,size_16,color_FFFFFF,t_70)
我们希望所有的对象使用同一个函数，这样就比较节省内存，那么我们就要使用到原型。

### 2.1.4 构造函数原型 prototype
构造函数通过原型分配的函数是所有对象所**共享的**。

JavaScript规定，**每一个构造函数都有一个prototype属性**，指向另一个对象。注意这个prototype就是一个对象，这个对象的所有属性和方法，都会被构造函数所据有。

**我们可以把那些不变的方法，直接定义在prototype对象上，这样所有对象的实例就可以共享这些方法。**

```javascript
Star.prototype.sing = function(){
	console.log('会唱歌')
}
```
1. Q：原型是什么？
    A：一个对象，我们也称prototype 为原型对象
2. Q：原型的作用是什么？
    A：共享方法。

一般情况下，公共属性定义到构造函数里面，公共的方法放到原型对象上。

### 2.1.5 对象原型 \_\_proto\_\_
**对象都会有一个属性\_\_proto\_\_**，指向构造函数的prototype原型对象，之所以我们对象可以使用构造函数prototype原型对象的属性和方法，就是因为对象有__proto__原型的存在。
- proto 对象原型和原型对象 prototype是等价的
- __proto__对象原型的意义就在于，为对象的查找机制提供一个方向，或者说一条路线，但是它是一个非标准属性，因此实际开发中，不可以使用这个属性，它只是内部指向原型对象prototype
![在这里插入图片描述](https://img-blog.csdnimg.cn/9ec6cdf6be9c4bc9a508713b48e6cc1a.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMzMzkwNzAw,size_16,color_FFFFFF,t_70)
方法的查找规则:
首先看ldh对象身上是否有sing方法,如果有就执行这个对象上的sing
如果没有sing 这个方法,因为有__proto__的存在,就去构造函数原型对象prototype身上去查找sing这个方法

### 2.1.6 constructor 属性
对象原型(\_\_proto\_\_)和构造函数（ prototype ) 原型对象里面都有一个属性constructor属性，constructor我们称为构浩函数，因为它指回构造函教本身。

constructor主要用于记录该对象引用于哪个构造函数，它可以让原型对象重新指向原来的构造函数。
很多情况下,我们需要手动的利用constructor这个属性指回原来的构造函数

```javascript
Star.prototype = {
	// 如果我们修改了原来的原型对象,给原型对象赋值的是一个对象,则必须手动的利用constructor指回原来的构造函数
	constructor: star;
	sing: function() f
	console.log('我会唱歌');
	},
	movie: function() {
	console.log('我会演电影');
	}
}
```
### 2.1.7构造函数、实例、原型对象三者之间的关系
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/735a9c1dc4364ddda648f62dd5b1994b.png)
### 2.1.8原型链




## 2.2 继承
## 2.3 ES5 中的新增方法

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 