> 基础选择器+字体文本相关样式
>
> ![image-20210915152633317](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210915152633317.png)



![](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210915152700464.png)

# 一、基础认知

> 目标:理解CSS的作用，了解CSS语法规则，知道CSS的引入方式及其区别
>
> 学习路径:
>
> 1. CSS初识
> 2. CSS引入方式

## 1 CSS 初识

### 1.1 CSS的介绍

CSS：层叠样式表( cascading style sheets)的简称。

有时我们也会称之为CSS样式表或级联样式表。
CSS也是一种标记语言。

CSS作用：
给页面中的HTML标签设置样式。

CSS主要用于设置HTML页面中的文本内容（字体、大小、对齐方式等）、图片的外形（宽高、边框样式、边距等）以及版面的布局和外观显示样式。

CSS使用场景：

CSS的主要使用场景就是美化网页、布局页面的。

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/b7348de98768409381f8f0c1ef3983d0/clipboard.png)

### 1.2 CSS语法规范

- CSS写在哪里：
  - CSS写在style标签中，style标签一般写在head标签里面，title标签下面。
- 怎么写：
  - CSS规则由两个主要的部分构成：选择器以及一条或多条声明。
  - 选择器是用于指定CSS样式的HTML标签，花括号内是对该对象设置的具体样式。
  - 属性和属性值以“键值对”的形式出现，属性和属性值之间用英文`:`分开。
  - 属性是对指定的对象设置的样式属性，例如字体大小、文本颜色等。

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/5ca757f6bfb64954871fa8bc4217fcc1/clipboard.png)

### 1.3 CSS初体验

![image-20210915154246522](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210915154246522.png)

## 2 CSS引入方式

CSS常见三种引入方式：

- 内嵌式: CSS写在style标签中

  - 提示: style标签虽然可以写在页面任意位置，但是通常约定写在`head`标签中

- 外联式:CSS写在一个单独的.css文件中

  - 提示:需要通过link标签在网页中引入

- 行内式: CSS写在标签的style属性中

  - 提示:基础班不推荐使用，之后会配合js使用

  

CSS常见三种引入方式的特点区别有哪些（书写位置、作用范围、使用场景)?

| 引入方式 | 书写位置                                 | 作用范围 | 使用场景   |
| -------- | ---------------------------------------- | -------- | ---------- |
| 内嵌式   | CSS写在style标签中                       | 当前页面 | 小案例     |
| 外联式   | CSS写在单独的css文件中，通过link标签引入 | 多个页面 | 项目中     |
| 行内式   | CSS写在标签的style属性中                 | 当前标签 | 配合js使用 |



# 二、基础选择器

> 目标:理解选择器的作用，能够使用基础选择器在HTML，中选择元素
> 学习路径:
>
> 1.标签选择器
>
> 2.类选择器
>
> 3.id选择器
>
> 4.通配符选择器

1.选择器作用:选中页面中对应的标签（找她)，方便后续设置样式（改她)

2.标签选择器:标签名{ css属性名:属性值;}
3.类选择器:.类名{ css属性名:属性值;}

4.id选择器:#id属性值{ css属性名:属性值;}

5.通配符选择器:* { css属性名:属性值;}



## 1.标签选择器

- 结构：标签名 { css属性名: 属性值; }

- 作用：通过标签名，找到页面中所有这类标签，设置样式

- 注意点：

  1.标签选择器选择的是一类标签，而不是单独某一个

  2.标签选择器无论嵌套关系有多深，都能找到对应的标签

![image-20210915155630533](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210915155630533.png)

## 2.类选择器

- 结构：`.类名{ css属性名: 属性值; }`

- 作用：通过类名，找到页面中所有带有这个类名的标签，设置样式

- 注意点：
  1．所有标签上都有class属性，class属性的属性值称为类名（类似于名字)

  2．类名可以由数字、字母、下划线、中划线组成，但不能以数字或者中划线开头

  3.一个标签可以同时有多个类名，类名之间以空格隔开
  4．类名可以重复，一个类选择器可以同时选中多个标签

  ![image-20210915160007816](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210915160007816.png)

## 3.id选择器

- 结构：#id属性值{ css属性名︰属性值;}

- 作用：通过id属性值，找到页面中带有这个id属性值的标签，设置样式

- 注意点:
  1．所有标签上都有id属性

  2.id属性值类似于身份证号码，在一个页面中是唯一的，不可重复的!

  3.一个标签上只能有一个id属性值
  4.一个id选择器只能选中一个标签

  ![image-20210915162449301](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210915162449301.png)

**补充：类与id的区别**

- class类名与id属性值的区别
  - . class类名相当于姓名，可以重复，一个标签可以同时有多个class类名.
  -  id属性值相当于身份证号码，不可重复，一个标签只能有一个id属性值
- 类选择器与id选择器的区别
  - .类选择器以.开头
  - .id选择器以#开头
- 实际开发的情况
  - ·类选择器用的最多
  - . id一般配合js使用，除非特殊情况，否则不要使用id设置样式
  - ·实际开发中会遇到冗余代码的抽取°(可以将一些公共的代码抽取到一个公共的类中去)

## 4.通配符选择器

- 结构：`* { css属性名: 属性值; }`
- 作用:找到页面中所有的标签，设置样式
- 注意点:
  1．开发中使用极少，只会在极特殊情况下才会用到
  2．在基础班小页面中可能会用于去除标签默认的margin和padding(后续讲解)

![image-20210915162638003](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210915162638003.png)

如果是修改样式，类选择器是使用最多的。

# 三、字体和文本样式

>目标:能够使用字体和文本相关样式修改元素外观样式
>
>学习路径:
>
>1.字体样式
>	1.字体大小: font-size
>
>​	2．字体粗细: font-weight
>
>​	3.字体样式: font-style
>
>​	4．字体类型: font-family
>
>​	5．字体类型: font属性连写
>
>2.文本样式
>
>3.line-height行高

## 1.字体样式

### 1.1 字体大小

- 属性名：font-size
- 取值：数字+px
- 注意点：
  - 谷歌浏览器默认文字大小是16px
  - 单位需要设置，否则无效

### 1.2 字体粗细



- 属性名: font-weight

- 取值:

  - 关键字:

    |      |        |
    | ---- | ------ |
    | 正常 | normal |
    | 加粗 | bold   |

  - 纯数字:100~900的整百数:

    |      |      |
    | ---- | ---- |
    | 正常 | 400  |
    | 加粗 | 700  |

- 注意点:

  - 不是所有字体都提供了九种粗细，因此部分取值页面中无变化
  - 实际开发中以:正常、加粗两种取值使用最多。

### 1.3 字体样式（是否倾斜）

- 属性名: font-style
- 取值:
  - 正常（默认值): normal
  - 倾斜：italic  

![image-20210915164923754](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210915164923754.png)



###  1.4 常见字体系列(了解)

- 无衬线字体(sans-serif)
  1.特点:文字笔画粗细均匀，并且首尾无装饰

  2.场景:网页中大多采用无衬线字体
  3.常见该系列字体:黑体、Arial

- 衬线字体( serif)
  1．特点:文字笔画粗细不均，并且首尾有笔锋装饰

  2.场景:报刊书籍中应用广泛
  3.常见该系列字体:宋体、Times New Roman

- 等宽字体( monospace)
  1.特点:每个字母或文字的宽度相等
  2.场景:一般用于程序代码编写，有利于代码的阅读和编写

  3.常见该系列字体:Consolas、courier New

![image-20210915165117199](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210915165117199.png)

### 1.5 字体系列 font-family

- 属性名: `font-family`
- 常见取值：具体字体1,具体字体2,具体字体3,具体字体4,....字体系列
  - 具体字体：`"Microsoft YaHei"`、微软雅黑、黑体、宋体、楷体等.......
  - 字体系列： sans-serif、serif、mondspace等......
- 渲染规则:
  1. 从左往右按照顺序查找，如果电脑中未安装该字体，则显示下一个字体
  2. 如果都不支持，此时会根据操作系统，显示最后字体系列的默认字体
- 注意点:
  - 1.如果字体名称中存在多个单词，推荐使用引号包裹
  - 2.最后一项字体系列不需要引号包裹
  - 3．网页开发时，尽量使用系统常见自带字体，保证不同用户浏览网页都可以正确显示

![image-20210915170302176](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210915170302176.png)



### 1.6 样式的层叠问题

- 问题:
  - 给同一个标签设置了相同的样式，此时浏览器会如何渲染呢?
- 结果:
  - 如果给同一个标签设置了相同的属性，此时样式会层叠（覆盖)，写在最下面的会生效
- TIP：
  - css (cascading style sheets)层叠样式表
  - 所谓的层叠即叠加的意思，表示样式可以一层一层的层叠覆盖

### 1.7 字体font相关属性的连写

- 属性名: font
- 取值:
  - font : style weight size family;
- 顺序要求:
  - swsf（稍微舒服）
- 省略要求:
  - 只能省略前两个，如果省略了相当于设置了默认值
- 注意点:如果需要同时设置单独和连写形式
  - 要么把单独的样式写在连写的下面
  - 要么把单独的样式写在连写的里面

## 2.文本样式

| 样式             | 属性名          | 常见属性值            |
| ---------------- | --------------- | --------------------- |
| 文本缩进         | text-indent     | 数字+px/数字+em       |
| 文本水平对齐芳式 | text-align      | left / center / right |
| 文本修饰         | text-decoration | underline / none      |



### 2.1 文本缩进

- 属性名: text-indent
- 取值:
  - 数字+px
  - 数字+em(推荐:1em =当前标签的font-size的大小)

### 2.2 文本水平对齐方式

- 属性名:text-align

- 取值:

  | 属性值 | 效果     |
  | ------ | -------- |
  | left   | 左对齐   |
  | center | 居中对齐 |
  | right  | 右对齐   |

- 注意点:

  - 如果需要让文本水平居中，text-align属性给文本所在标签（文本的父元素）设置

### 2.3 文本修饰

- 属性名: text-decoration

- 取值:

  | 属性值       | 效果             |
  | ------------ | ---------------- |
  | underline    | 下划线(〔常用)   |
  | line-through | 删除线(不常用)   |
  | overline     | 上划线(几乎不用) |
  | none         | 无装饰线（常用)  |

- 注意点:

  - 开发中会使用`text-decoration : none ;`清除a标签默认的下划线

## 3.行高

- 作用：控制一行的上下行间距

![image-20210915195114044](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210915195114044.png)

- 属性名：line-height
- 取值:
  - 数字+px
  - 倍数（当前标签font-size的倍数)
- 应用:
  1. 网页精准布局时，会设置`line-height: 1` 可以取消上下间距
  2. 让单行文本垂直居中可以设置`line-height: 文字父元素高度`
- 行高与font连写的注意点:
  - 如果同时设置了行高和font连写，注意覆盖问题
  - font : style weight size/line-height family ;![image-20210916001644157](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210916001644157.png)

一个盒子如果没有指定高度，则以行高为默认。

## 2.1 CSS的复合选择器

### 1.1 什么是复合选择器

在CSS中，可以根据选择器的类型把选择器分为基础选择器和复合选择器，复合选择器是建立在基础选择器之上，对基本选择器进行组合形成的。

·     复合选择器可以更准确、更高效的选择目标元素（标签）

·     复合选择器是由两个或多个基础选择器，通过不同的方式组合而成的

·     常用的复合选择器包括：后代选择器、子选择器、并集选择器、伪类选择器等等

### 1.2 后代选择器（重要）

后代选择器又称为包含选择器，可以选择父元素里面子元素。其写法就是把外层标签写在前面，内层标签写在后面，中间用空格分隔。当标签发生嵌套时，内层标签就称为外层标签的后代。

元素1 元素2 {样式声明} 

上述语法表示选择元素1里面的所有元素2（后代元素）

例如：

ul li {样式声明} /* 选择ul里面所有的li标签元素 */ 

·     元素1和元素2 中间用空格隔开

·     元素1是父级，元素2是子级，最终选择的是元素2

·     元素2可以是儿子，也可以是孙子等，只要是元素1的后代即可。

·     元素1和元素2可以是任意基础选择器（标签选择器、类选择器、id选择器、通配符选择器）

### **1.3** **子选择器（重要）**

子元素选择器（子选择器）只能选择作为某元素的最近一级子元素。简单理解就是选亲儿子元素。

语法：

元素1>元素2(样式声明) 

上述语法表示选择元素1里面的所有直接后代（子元素）元素2.

例如：

div>p {样式声明} /* 选择div里面所有最近一级 p 标签元素 */ 

·     元素1和元素2中间用大于号隔开

·     元素1是父级，元素2是子级，最终选择的是元素2

·     元素2必须是亲儿子，其孙子、重孙之类都不归他管。你也可以叫他亲儿子选择器。

### **1.4** **并集选择器（重要）**

并集选择器可以选择多组标签，同时为他们定义相同的样式。通常用于集体声明。

并集选择器是各选择器通过英文逗号（,）连接而成，任何形式的选择器都可以作为并集选择器的一部分。

元素1,元素2 {样式说明} 

上述语法表示选择元素1和元素2.

例如：

ul,div{样式说明} /* 选择 ul 和 div 标签元素 */ 

·     元素1和元素2中间用逗号隔开

·     逗号可以理解为和的意思

·     并集选择器通常用于集体声明

### **1.5** **伪类选择器**

伪类选择器用于向某些选择器添加特殊的效果，比如给链接添加特殊效果，或选择第1个，第n个元素。

伪类选择器书写最大的特点是用冒号（:）表示，比如:hover(悬浮)、first-child。

因为伪类选择器很多，比如有链接伪类、结构伪类等。

### **1.6** **链接伪类选择器**

a:link /* 选择所有未被访问的链接 */ a:visited /* 选择所有已被访问的链接 */ a:hover /* 选择鼠标指针位于其上的链接 */ a:active /* 选择活动链接（鼠标按下未弹起的链接） */ 

·     链接伪类选择器注意事项

\1.   为了确保生效，请按照LVHA的顺序声明：:link、:visited、:hover、:active

\2.   记忆法：love hate 或者LV 好

\3.   因为a链接在浏览器中具有默认样式，所以我们实际工作中都需要给链接单独指定样式。

·     链接伪类选择器实际开发中的写法

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image001.png)

### **1.7 :focus** **伪类选择器**

:focus 伪类选择器用于选取获得焦点的表单元素。

焦点就是光标，一般情况<input>类表单元素才能获取，因此这个选择器也主要针对于表单元素来说。

input:focus { background-color:yellow; } 

### **1.8** **复合选择器总结**

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image002.png)

 

 

1 定位.能解决的问题

2.定位的组成
3.四种定位模式
4.定位案例(土豆)

> position & transform: translate(-50%, -50%)实现居中
> https://blog.csdn.net/qq_46469137/article/details/105921737

# 1.标准流

> 能够认识标准流的默认排布方式及其特点

标准流︰又称文档流，是浏览器在渲染显示网页内容时默认采用的一套排版规则，规定了应该以何种方式排列元素
常见标准流排版规则:

#### 1．块级元素：从上往下，垂直布局，独占一行

2．行内元素或行内块元素：从左往右，水平布局，空间不够自动折行



# 2.页面布局

## 2.1 盒子模型

页面布局要学习三大核心，盒子模型、浮动和定位。学习好盒子模型能非常好的帮助我们布局页面。

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image001.png)

 



### 1.1 看透网页布局的本质

网页布局过程：

1. 先准备好相关的网页元素，网页元素基本都是盒子box

2. 利用CSS设置好盒子样式，然后摆放到相应位置

3. 往盒子里面装内容

**网页布局的核心本质：利用CSS摆盒子**

### 1.2 盒子模型（Box Model）组成

所谓盒子模型：就是把HTML页面中的布局元素看成是一个矩形的盒子，也就是盛放内容的容器。

CSS盒子模型本质上是一个盒子，封装周围的HTML元素。他包括：边框、外边距、内边距和实际内容。

![img](https://gitee.com/jingw1/cloud-image/raw/master/img/clip_image002.png)

 

![img](https://gitee.com/jingw1/cloud-image/raw/master/img/clip_image003.png)

### **1.3** **边框（border）**

![img](https://gitee.com/jingw1/cloud-image/raw/master/img/clip_image004.png)

border可以设置元素的边框。边框有三部分组成：边框宽度（粗细） 边框样式 边框颜色

border : border-width || border-style || border-color 

 

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image005.png)

CSS边框属性允许你指定一个元素边框的样式和颜色

边框简写：

border: 1px solid red;/* 没有顺序*/ 

边框分开写法：

border-top: 1px solid red; 

 

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image006.png)

### **1.4** **表格的细线边框**

border-collapse 属性控制浏览器绘制表格边框的方式。它控制相邻单元格的边框。

语法：

border-collapse:collapse; 

·     collapse单词是合并的意思

·     border-collapse:collapse; 表示相邻边框合并在一起

 

### **1.5** **边框会影响盒子实际大小**

使用width、height设置盒子的高和宽后，如果再设置border，盒子的实际大小会受到影响。

![img](https://gitee.com/jingw1/cloud-image/raw/master/img/clip_image007.png)

### **1.6** **内边距（padding）**

padding 属性用于设置内边距，即边框与内容之间的举例

![img](https://gitee.com/jingw1/cloud-image/raw/master/img/clip_image008.png)

padding属性（简写属性）可以有一到四个值。

![image-20210924100414231](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210924100414231.png)

当我们给盒子指定padding值之后，发生了2件事情：

1. 内容和边框有了距离，添加了内边距。

2. padding影响了盒子实际大小 。

也就是说，如果盒子已经有了宽度和高度，此时再指定内边框，会撑大盒子。

解决方案：

如果保证盒子跟效果图大小保持一致，则让width/height减去多出来的内边距大小即可。

如果盒子本身没有指定width/height属性，则此时padding不会撑开盒子大小。

### **1.7** **外边距（margin）**

margin属性用于设置外边距，即控制盒子和盒子之间的距离。

![img](https://gitee.com/jingw1/cloud-image/raw/master/img/clip_image010.png)

margin简写方式代表的意义跟padding完全一致

 

**外边距典型应用**

外边距可以让块级盒子水平居中，但是必须满足两个条件：

1. 盒子必须制定宽度（width）；

2. 盒子左右的外边距都设置为auto

`.header {width:960px; margin:0 auto;} `

常见的写法，以下三种都可以：

·     margin-left:auto; margin-right:auto;

·     margin:auto;

·     margin:0 auto;

 

注意：以上方法是让块级元素水平居中，行内元素或者行内块元素水平居中给其父元素添加text-align:center 即可。

图片img标签不需要做任何操作就是行内块元素吗？

**1.8** **外边距合并**

使用 margin 定义块元素的垂直外边距时，可能会出现外边距的合并。

**1.**相邻块元素垂直外边距的合并

![image-20210924162350731](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210924162350731.png)

**2.** 嵌套块元素

对于两个嵌套关系（父子关系）的块元素，父元素有上外边距的同时，子元素也有上外边距。此时父元素会塌陷较大的外边距值。

![image-20210924162409192](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210924162409192.png)

还有其他方法，比如浮动、固定、绝对定位的盒子不会有塌陷问题。后面再说。

### 1.9 清除内外边距

网页元素很多都带有默认的内外边距，而且不同浏览器默认的也不一致。因此我们布局前，首先要清除网页元素的内外边距。

自带默认边距显示如下：

![image-20210924162429592](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210924162429592.png)

清除网页元素的内外边距：

也是CSS的第一行代码

\* { padding:0; /*清除内边距*/ margin:0;/*清除外边距*/ } 

 

![img](https://gitee.com/jingw1/cloud-image/raw/master/img/clip_image014.png)

注意：行内元素为了照顾兼容性，尽量只设置左右边距，不要设置上下内外边距（很多时候不起效果），但是转换为块级和行内块元素就可以了。

### 1.10 盒子阴影



CSS3中新增了盒子阴影，用box-shadow属性为盒子添加阴影。

![img](https://gitee.com/jingw1/cloud-image/raw/master/img/clip_image001.png)

 注意:
1.默认的是外阴影(outset),但是不可以写这个单词,否则导致阴影无效
2.盒子阴影不占用空间，不会影响其他盒子排列。



`box-shadow: 10px 10px 10px -4px rgba(0，0， 0， .3); `

### 1.11 文字阴影

在CSS3中，使用text-shadow属性将阴影应用于文本。

![image-20210924162721801](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210924162721801.png)

![image-20210924162735735](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210924162735735.png)

 

 

## 2.2 浮动

### 2.1 浮动的作用

早期作用：图文环绕

现在作用：用于布局，让垂直布局的盒子变成水平布局，如:一个在左，一个在右

### 2.2 浮动的代码

属性名: float属性值:

| 属性名 | 效果   |
| ------ | ------ |
| left   | 左浮动 |
| right  | 右浮动 |

### 2.3 浮动的特点

1.浮动元素会脱离标准流（脱标），在标准流中不占位置。（相当于从地面飘到了空中）

![image-20210915092823187](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210915092823187.png)

2.浮动元素比标准流高半个级别，可以覆盖标准流中的元素。
3.浮动找浮动，下一个浮动元素会在上一个浮动元素后面左右浮动。
4.浮动元素会受到上面元素边界的影响。
5.浮动元素有特殊的显示效果：一行可以显示多个；可以设置宽高。

浮动的元素是互相贴靠在一起的（不会有缝隙），如果父级宽度装不下这些浮动的盒子，多出的盒子会另起一行对齐。

3.浮动元素会具有行内块元素特性
任何元素都可以浮动。不管原先是什么模式的元素，添加浮动之后具有行内块元素相似的特性。
（如果行内元素有了浮动属性，则不需要转换成块级元素或者行内块元素，就可以设置宽高）
span属于行内元素，没有宽高（不能直接设置宽高）。设置浮动后，就可以设置宽高。

```css
/* 以下代码中给span设置宽高后，不会显示 */
span {
    width:20px;
    height:40px;
    background-color:pink;
}
```

加上 float:left;后就可以显示该矩形了。

p属于块级元素。
如果块级盒子没有设置宽度，默认宽度和父级一样宽。但是添加浮动后，它的大小根据内容来决定。
浮动的盒子中间是没有缝隙的，是紧挨着一起的。
行内元素同理。

```css
/* p标签没有设置浮动时，作为标准流元素，宽度为整个屏幕的宽度 */
p {
    height:50px;
    background-color:red;
}
/* p标签设置浮动后，具有了行内块元素的特性，宽度为包含的内容的宽度 */
```

### 2.4 浮动布局注意点

1.浮动和标准流的父盒子搭配。

先用标准流的父元素排列上下位置，之后内部子元素采取浮动排列左右位置。

2.一个元素浮动了，理论上其余的兄弟元素也要浮动。

一个盒子里面有多个子盒子，如果其中的一个子盒子浮动了，那么其他兄弟也应该浮动，以防止引起问题。

浮动的盒子只会影响浮动盒子后面的标准流，不会影响前面的标准流。（浮动后就把位置让出来）

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/37e990a6ccc040b8a801e7119e65d034/clipboard.png)

大毛和三毛浮动，二毛不浮动。效果如下：

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/398fc4fb5cc446c4b2f80b29e54f2f42/clipboard.png)

猜想：二毛不浮动，占了一行，三毛在下面一行。又由于浮动，左侧靠近大毛？？

### 2.5 清除浮动

#### 2.5.1 为什么需要清除浮动？

由于父级盒子很多情况下，不方便给高度，但是子盒子浮动又不占有位置，最后父级盒子高度为0时，就会影响下面你的标准流盒子。

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/a12dcf4207a44cd6a92c34a957441f61/clipboard.png)

- 由于浮动元素不再占用源文档流的位置，所以它会对后面的元素排版产生影响。

#### 2.5.2 清除浮动本质

- 清除浮动的本质是清除浮动元素造成的影响
- 如果父盒子本身有高度，则不需要清除浮动。
- 清除浮动之后，父级就会根据浮动的子盒子自动检测高度，父级有了高度，就不会影响下面的标准流了。

#### 2.5.3  清除浮动

语法：

选择器 {clear:属性值;}

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/3fbc7c04f1a44ac7b97a12230736c7d5/clipboard.png)

实际工作中，几乎只用clear:both;

清除浮动的策略是：闭合浮动。

#### 2.5.4 清除浮动方法

**方法1 额外标签法，也称为隔墙法，是W3C推荐的做法。**

额外标签法会在最后一个浮动的子元素后面，添加一个空的标签。例如<div style=" clear:both"></div>，或者其他标签（如<br/>等）。

优点：通俗易懂，书写方便

缺点：添加许多无意义的标签，结构化较差

注意：要求这个新的空标签必须是块级元素。

实际工作可能会遇到，但是不常用

**方法2 父级添加overflow属性**

给父级添加overflow属性，将其属性值设置为hidden、auto或scroll。可以清除浮动。

- 优点：代码简洁
- 缺点：无法显示溢出的部分

**方法3 父级添加after伪元素**

:after方式是额外标签法的升级版，也是给父元素添加。

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/b515a4a6a4dd41cfaa80825db335837e/clipboard.png)

- 优点：没有增加标签，结构简单
- 缺点：需要照顾低版本浏览器
- 代表网站：百度、淘宝网、网易等

**方法4 父级添加双伪元素**

也是给父元素添加

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/3a25041a44324920b4f26083ddb47ee1/clipboard.png)

给父级盒子（一般是ul）的类名添加上对应的“.clearfix”，并给其添加属性设置。

.clearfix:before,.clearfix:after {   content: "";   display:table; } .clearfix:after {   clear:both; } .clearfix {   *zoom: 1; }

优点：代码更简洁

缺点：需要照顾低版本浏览器

代表网站：小米、腾讯等

#### 2.5.5 清除浮动总结

为什么需要清除浮动？

1. 父级没高度
2. 子盒子浮动了
3. 影响了下面布局了，我们就应该清除浮动了。

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/5c9aae7df0104cc5b88a8578a7e4e5b4/clipboard.png)

### 2.6 浮动的案例

## 2.3  flex布局

是 CSS3 引入的新的布局模式。

具体可查看：https://www.runoob.com/w3cnote/flex-grammar.html

应用：

```css
.btns {
  // 指定 HTML 元素盒子类型:弹性盒子
  display: flex;
  // 	设置弹性盒子元素在主轴（横轴）方向上的对齐方式，设置位于容器的结尾
  justify-content: flex-end;
}
```



# 3.定位

![image-20210915095102079](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210915095102079.png)

### **1.1** **为什么需要定位**

提问：以下情况使用标准流或者浮动能实现吗？

1.某个元素可以自由的在一个盒子内移动位置，并且压住其他盒子。

2.当我们滚动窗口的时候，盒子是固定到屏幕某个位置的。

以上效果，标准流或浮动都无法快速实现，此时需要定位来实现。

所以：

1.浮动可以让多个块级盒子一行没有缝隙排列显示，经常用于横向排列盒子。

2.定位则是可以让盒子自由的在某个盒子内移动位置或者固定到屏幕中某个位置，并且可以压住其他盒子。

### **1.2** **定位组成**

定位：将盒子定在某一个位置，所以定位也是在摆放盒子，按照定位的方式移动盒子。

定位 = 定位模式 + 边偏移

定位模式用于指定一个元素在文档中的定位方式。边偏移则决定了该元素的最终位置。

**1.**定位模式

定位模式决定元素的定位方式，它通过CSS的position属性来设置，其值可以分为四个：

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image001.png)

**2.**边偏移

边偏移就是定位的盒子移动到最终位置。有top、bottom、left和right 4个属性。

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image002.png)

### **1.3** **静态定位 static（了解）**

静态定位是元素的默认定位方式，无定位的意思。

语法：

选择器 { position: static; } 

·     静态定位按照标准流特性摆放位置，它没有边偏移

·     静态定位在布局时很少用到。

### **1.4** **相对定位 relative（重要）**

相对定位是元素在移动位置的时候，是相对于它原来的位置来说的（自恋型）。

语法:
`选择器 { position: relative;} `

相对定位的特点：

1. 它是相对于自己原来的位置来移动的（移动位置的时候参照点是自己原来的位置）。

2. 原来在标准流的位置继续占有，后面的盒子仍然以标准流的方式对待它。（不脱标，继续保留原来位置）

最典型的应用是给绝对定位当爹。

### 1.5 绝对定位 absolute（重要）

绝对定位是元素在移动位置的时候，是相对于它祖先元素来说的（拼爹型）。

语法:
`选择器 { position: absolute;} `

绝对定位的特点（务必记住）：

1. 如果没有祖先元素或者祖先元素没有定位，则以浏览器为准定位（document文档）。

2. 如果祖先元素有定位（相对、绝对、固定定位），则以最近一级的有定位祖先元素为参考点移动位置。

3. 绝对定位不再占有原先的位置（脱标）.

 

![img](https://gitee.com/jingw1/cloud-image/raw/master/img/clip_image005.png)

 

### **1.6** **子绝父相的由来**

弄清楚这个口诀，就明白了绝对定位和相对定位的使用场景。

子级使用绝对定位的话，父级则需要相对定位。

![image-20210924160655727](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210924160655727.png)

用浮动对上图中的粉色盒子，添加3个蓝色盒子。用浮动的话，会出现问题：

1. 浮动只影响后面的标准流盒子，所以要先写浮动的盒子，再写标准流盒子

2. 浮动的多个盒子会在一行中显示，很难布局出上图的效果。

 

解决方法是用绝对定位

①子级绝对定位，不会占有位置，可以放到父盒子里面的任何一个地方，不会影响其他的兄弟盒子。
此时，父级盒子没有定位的话，子盒子以浏览器为准定位，可能会超出父盒子的范围。所以父盒子要加定位，将子盒子限制在父盒子内。

②父盒子需要加定位限制子盒子在父盒子内显示。
父盒子不能加绝对定位，因为绝对定位不占有位置，页面结构就乱套了。

③父盒子布局时，需要占有位置，因此父亲只能是相对定位。
这就是子绝父相的由来，所以相对定位经常用来作为绝对定位的父级。

总结∶因为父级需要占有位置，因此是相对定位，子盒子不需要占有位置，则是绝对定位

当然，子绝父相不是永远不变的，如果父元素不需要占有位置，子绝父绝也会遇到,

### 1.7 固定定位 fixed （重要）

固定定位是元素固定于浏览器可视区的位置。主要使用场景：可以在浏览器页面滚动时元素的位置不会改变。

语法：

选择器 {position: fixed; } 

固定定位的特点：（务必记住）

\1.   以浏览器的可视窗口为参照点移动元素。

a.    跟父元素没有任何关系

b.   不随滚动条的滚动而移动

\2.   固定定位不再占有原先的位置。

 .     固定定位也是脱标的，其实固定定位也可以看作是一种特殊的绝对定位。

固定定位小技巧：固定在版心右侧位置。

小算法：设置left：50% 会固定在距离左边的中心处

设置margin-left：版心宽度的50%。从而固定在版心的旁边。

### **1.8** **粘性定位 sticky（了解）**

![img](https://gitee.com/jingw1/cloud-image/raw/master/img/clip_image012.png)

否则会相当于相对定位。

设置top:0。 则在滚动窗口中，盒子上沿距离可视窗口的距离为0时，固定在该位置。

跟页面滚动搭配使用。兼容性较差，IE不支持。

### **1.9** **定位的总结**

![img](https://gitee.com/jingw1/cloud-image/raw/master/img/clip_image013.png)

 

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image014.png)

### **1.10** **定位叠放次序 z-index**

在使用定位布局时，可能会出现盒子充电的情况。此时，可以使用 z-index 来控制盒子的前后次序（z轴）

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image015.png)

### **1.11** **定位的拓展**

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image016.png)

 

![img](https://gitee.com/jingw1/cloud-image/raw/master/img/clip_image017.png)

span标签加上绝对定位，就可以直接设置宽高了。这里注意哦 ~

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image018.png)

 

 4.绝对定位(固定定位)会完全压住盒子
浮动元素不同，只会压住它下面标准流的盒子，但是不会压住下面标准流盒子里面的文字(图片)
但是绝对定位(固定定位）会压住下面标准流所有的内容。
浮动之所以不会压住文字，因为浮动产生的目的最初是为了做文字环绕效果的。文字会围绕浮动元素

 

 



## CSS 语法

justify-content: flex-start|flex-end|center|space-between|space-around|initial|inherit;

## 属性值

| 值            | 描述                                                         | 测试                                                         |
| :------------ | :----------------------------------------------------------- | :----------------------------------------------------------- |
| flex-start    | 默认值。项目位于容器的开头。                                 | [测试 »](https://www.runoob.com/try/playit.php?f=playcss_justify-content&preval=flex-start) |
| flex-end      | 项目位于容器的结尾。                                         | [测试 »](https://www.runoob.com/try/playit.php?f=playcss_justify-content&preval=flex-end) |
| center        | 项目位于容器的中心。                                         | [测试 »](https://www.runoob.com/try/playit.php?f=playcss_justify-content&preval=center) |
| space-between | 项目位于各行之间留有空白的容器内。                           | [测试 »](https://www.runoob.com/try/playit.php?f=playcss_justify-content&preval=space-between) |
| space-around  | 项目位于各行之前、之间、之后都留有空白的容器内。             | [测试 »](https://www.runoob.com/try/playit.php?f=playcss_justify-content&preval=space-around) |
| initial       | 设置该属性为它的默认值。请参阅 [*initial*](https://www.runoob.com/cssref/css-initial.html)。 | [测试 »](https://www.runoob.com/try/playit.php?f=playcss_justify-content&preval=initial) |
| inherit       | 从父元素继承该属性。请参阅 [*inherit*](https://www.runoob.com/cssref/css-inherit.html)。 |                                                              |





# 4 **元素的显示与隐藏**

类似网站广告，当我们点击关闭就不见了，但是我们重新刷新页面，会重新出现!

本质:让一个元素在页面中隐藏或者显示出来。

\1. display 显示隐藏元素 但是不保留位置

\2. visibility 显示隐藏元素 但是保留原来的位置

\3. overflow 溢出显示隐藏 但是只是对于溢出的部分处理

 

**1.display****属性 重点**

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image001.png)

display属性用于设置一个元素应如何显示。

·     display: none ;隐藏对象

·     display : block;除了转换为块级元素之外，同时还有显示元素的意思

display隐藏元素后，**不再**占有原来的位置。

后面应用及其广泛，搭配JS可以做很多的网页特效。

**2 visibility** **可见性**

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image002.png)

visibility属性用于指定一个元素应可见还是隐藏。

visibility : visible; 元素可视

visibility : hidden; 元素隐藏

visibility隐藏元素后，**继续**占有原来的位置。

如果隐藏元素想要原来位置，就用visibility : hidden

如果隐藏元素不想要原来位置，就用display : none(用处更多重点)

**3 overflow** **溢出**

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image003.png)

overflow 属性指定了如果内容溢出一个元素的框（超过其指定高度及宽度）时，会发生什么。

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image004.png)

一般情况下，我们都不想让溢出的内容显示出来，因为溢出的部分会影响布局。

但是如果有定位的盒子，请慎用overflow:hidden因为它会隐藏多余的部分。

 

综合案例

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image005.png)

 

 

# 4.属性



## **3.CSS**的背景

通过CSS背景属性，可以给页面元素添加背景样式。

背景属性可以设置背景颜色、背景图片、背景平铺、背景图片位置、背景图像固定等

### **3.2** **背景图片**

background-image:url(路径) 

默认平铺铺满

 

### **3.3** **背景平铺**

如果需要在HTML页面上对背景图像进行平铺，可以使用background-repeat属性。

background-repeat:repeat | no-repeat | repeat-x | repeat-y 

 

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image001.png)

### **3.4** **背景图片位置**

利用background-position属性可以改变图片在背景中的位置。

background-position: x y; 

参数代表的意思是：x坐标和y坐标，可以使用方位名词或者精确单位。

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image002.png)

\1.   参数是方位名词

a.    如果指定的两个值都是方位名词，则两个值前后顺序无关，比如left top 和 top left 效果一致

b.   如果只指定了一个方位名词，另一个值省略，则第二个值默认居中对齐。

\2.   参数是精确单位

 .     如果参数值是精确单位，那么第一个肯定是x坐标，第二个肯定是y坐标。

a.    如果只指定一个数值，那该数值一定是x坐标，另一个默认垂直居中。

\3.   参数是混合单位

 .     如果指定的两个值时精确单位和方位名词混合使用，则第一个值是x坐标，第二个值是y坐标。

### **3.5** **背景图像固定（背景附着）**

background-attachment 属性设置背景图像是否固定或者随着页面的其余部分滚动。

background-attachment 后期可以制作视差滚动的效果。

background-attachment : scroll | fixed 

 

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image003.png)

### **3.6** **背景复合写法**

为了简化背景属性的代码，我们可以将这些属性合并简写在同一个属性background中，从而节约代码量。

当使用简写属性时，没有特定的书写顺序，一般习惯约定顺序为：

background: 背景颜色 背景图片地址 背景平铺 背景图像滚动 背景图片位置 

这是实际开发中，我们更提倡的写法。

### 3.7 背景色半透明

CSS3 提供了背景半透明的效果。

background: rgba(0,0,0,0.3) /*alpha 透明度 */ 

·     最后一个参数是alpha透明度，取值范围是0~1之间

·     我们习惯把0.3的0省略掉，写为background:rgba(0,0,0,.3)

·     注意：背景半透明是指盒子**背景**半透明，盒子里面的内容不受影响。

·     CSS3 新增属性，是IE 9+ 版本浏览器才支持的。

·     但是现在实际开发，我们不太关注兼容性写法了，可以放心使用。

### **3.8** **背景总结**

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image004.png)

背景图片：实际开发常见于logo或者一些装饰性的小图片或者是超大的背景图片，优点是**非常便于控制位置**。（精灵图也是一种运用场景）

background-size 属性

| length     | 设置背景图片高度和宽度。第一个值设置宽度，第二个值设置的高度。如果只给出一个值，第二个是设置为 **auto**(自动) |
| ---------- | ------------------------------------------------------------ |
| percentage | 将计算相对于背景定位区域的百分比。第一个值设置宽度，第二个值设置的高度。如果只给出一个值，第二个是设置为"auto(自动)" |
| cover      | 此时会保持图像的纵横比并将图像缩放成将完全覆盖背景定位区域的最小大小。 |
| contain    | 此时会保持图像的纵横比并将图像缩放成将适合背景定位区域的最大大小。 |









## 4.2 字体

 **3.****CSS字体属性**

CSS fonts（字体）属性用于定义字体系列、大小、粗细和文字样式（如斜体）

**3.1 字体系列**

css使用font-family属性定义文本的字体系列

```
p {font-family: "微软雅黑";} 
div {font-family: Arial,"Microsoft Yahei","微软雅黑";}
```

**3.2 字体大小**

CSSFonts（字体）属性定义字体大小

p {    font-size: 20px; }

- px（像素）大小是我们网页最常用的单位
- 谷歌浏览器默认的文字大小为16px
- 不同浏览器可能默认显示的字号大小不一致，我们尽量给一个明确值大小，不要默认大小
- 可以给body指定整个页面文字的大小
- 标题标签比较特殊，需要单独指定文字大小

3.3 字体粗细

CSS 使用font-weight属性设置文字的

### 4.3 文本属性

**4.CSS文本属性**

CSS Text（文本）属性可定义文本的外观，比如文本的颜色、对齐文本、装饰文本、文本缩进、行间距等。

**4.6 文本属性总结**

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/0d9fb994cf944fdc8e20e0e01d325644/clipboard.png)

行高=文字本身的高度+上间距+下间距

### 4.4 CSS属性书写顺序

5.3 CSS属性书写顺序

编程中如何衡量一个人的代码能力？

规范标准 优雅高质量 等等 一个词形容 专业 从代码中看出是否有经验。

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image001.png)

 

![img](C:/Users/12141/AppData/Local/Temp/msohtmlclip1/01/clip_image002.png)

页面布局整体思路：

\1.   必须确定页面的版心（可视区），我们测量可得知。

\2.   分析页面中的行模块，以及每个行模块中的列模块，其实是页面布局第一准则。

\3.   一行中的列模块经常浮动布局，先确定每个列的大小，之后确定列的位置，页面布局第二准则。

\4.   制作HTML结构。我们还是遵循，先有结构，后又样式的原则。结构永远最重要。

\5.   所以，先理清楚布局结构，再写代码尤为重要，这需要我们多写多积累。

\6.  

 

### 1.4 CSS的三大特性

1.CSS 的三大特性

CSS有三个非常重要的特性：层叠性、继承性、优先级。

1.1 层叠性

**相同选择器**给设置**相同的样式**，此时一个样式就会覆盖（层叠）另一个冲突的样式。层叠性主要解决样式冲突的问题。

层叠性原则：

- 样式冲突，遵循的原则是就近原则，哪个样式离结构近，就执行哪个样式
- 样式不冲突，不会层叠

1.2 继承性

子标签会继承父标签的某些样式，如文本颜色和字号。

> 目标:能够说出四种定位的应用场景，能够使用子绝父相，实现淘宝轮播图（焦点图）案例





# 高级技巧



## **1.精灵图**

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/4f5103ab86374f9fbc95bd6fec401e74/clipboard.png)

### **1.1 为什么需要精灵图**

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/7d14028404ce475bb1503039ad283afb/clipboard.png)

一个网页中往往会应用很多小的背景图像作为修饰，当网页中的图像过多时，服务器就会频繁地接收和发送请求图片，造成服务器请求压力过大，这将大大降低页面的加载速度。

因此，为了有效地减少服务器接收和发送请求的次数，提高页面的加载速度，出现了CSS精灵技术(也称css Sprites、CSS雪碧)。

核心原理∶将网页中的一些小背景图像整合到一张大图中，这样服务器只需要一次请求就可以了.

精灵技术目的:

为了有效地减少服务器接收和发送请求的次数，提高页面的加载速度

### **1.2 精灵图（sprites）的使用**

使用精灵图核心:

1.精灵技术主要针对于（小的）背景图片使用，就是把多个小背景图片整合到一张大图片中。

2.这个大图片也称为sprites，精灵图或者雪碧图

3.主要借助于移动背景图片的位置来实现---使用background-position.

4.移动的距离就是这个目标图片的 x 和 y 坐标。注意网页中的坐标有所不同(x轴右边走是正值，左边走是负值，y轴下边走是正值，上边走是负值)。

5.因为一般情况下都是往上往左移动，所以—般情况下精灵图都是负值。

6.使用精灵图的时候需要精确测量，每个小背景图片的大小和位置。

设置精灵图的图标代码：

/* 设置显示的宽高 */ height: 60px; width: 60px; /* 设置精灵图的 url 和移动的距离 */ background: ulr(images/sprites.png); background-position:-182px 0;

复合写法：

background-position 属性的值可以写在 background 属性里面，写在 background 属性中的 ulr 值和 重复模式 后面。

background: ulr(images/sprites.png) no-repeat -182px 0;

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/612e904d46ec471ab26e7da9dfd87649/clipboard.png)

**1.3 大小和位置的数值获取方法**

获取精灵图中想要显示的小背景图片的大小和位置：

利用PS工具，切片工具选中该小背景图片，右击选择“编辑切片选项”

## **2.字体图标**

字体图标是一些网页常见的小图标，我们直接网上下载即可。因此使用可以分为:

1．字体图标的下载
2．字体图标的引入（引入到我们html页面中)
3．字体图标的追加（以后添加新的小图标)



2.1 字体图标的产生

字体图标使用场景：主要用于显示网页中通用、常用的一些小图标。
精灵图是有诸多优点的，但是缺点很明显。

1．图片文件还是比较大的。
2．图片本身放大和缩小会失真。
3. 一旦图片制作完毕想要更换非常复杂。

此时，有一种技术的出现很好的解决了以上问题，就是字体图标iconfont.

字体图标可以为前端工程师提供一种方便高效的图标使用方式，展示的是图标，本质属于字体



**2.2 字体图标的优点** 

轻量级︰一个图标字体要比一系列的图像要小。一旦字体加载了，图标就会马上渲染出来，减少了服务器请求

灵活性:本质其实是文字，可以很随意的改变颜色、产生阴影、透明效果、旋转等

兼容性:几乎支持所有的浏览器，请放心使用

注意:字体图标不能替代精灵技术，只是对工作中图标部分技术的提升和优化。



字体图标是一些网页常见的小图标，我们直接网上下载即可。因此使用可以分为∶

1．字体图标的下载

2．字体图标的引入（引入到我们html页面中)

3．字体图标的追加（以后添加新的小图标)

**2.3 字体图标的下载**

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/7f07bfdc55ed4fb7ad2d31f15e16d23e/clipboard.png)

http://icomoon.io

iconmoon->app->选择->generate->download，得到一个压缩包。

**2.4 字体图标的引入**

1.把下载包里面的 `fonts 文件夹`放入页面根目录下

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/928d4270bced4503ae999a5841d18511/clipboard.png)

☆**字体文件格式**

为了兼容性，所以在font文件夹里有4个类型的文件

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/a4c133c053954807a906e1ddd1bc48c7/clipboard.png)

2.在CSS样式中全局声明字体，简单理解把这些字体文件通过css引入到我们页面中。

一定注意字体文件路径的问题。

```css
@font-face {
font-family: 'icomoon' ;
src: url('fonts/icomoon.eot?7kkyc2');
src: url('fonts/icomoon.eot?7kkyc2#iefix') format ('embedded-opentype ' ), 
  url('fonts/icomoon.ttf?7kkyc2') format ('truetype') ,
	url('fonts/icomoon.woff?7kkyc2') format ('woff'), 
	url('fonts/icomoon.svg? 7kkyc2#icomoon') format('svg') ;
font-weight: normal;
font-style: normal;
}
```

也就是下载的文件中的style.css 文件中的一部分

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/e1955d3e5bfc48608adbc7cb4ffa9ee4/clipboard.png)

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/32f624d6538147789dbdf14a7ae0f6cc/clipboard.png)

3.html标签内添加小图标。

下载的文件中的IconMoon.Demo，双击点开。

复制相应的右边的小方框。

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/8ea4711c76ec409db554cb9187dd1c43/clipboard.png)

4.给标签声明一个字体

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/0ce5978e85524824b19791d0e94ac625/clipboard.png)



**2.5 字体图标的追加**

如果工作中，原来的字体图标不够用了，我们需要添加新的字体图标到原来的字体文件中。

把压缩包里面的 selection.json 从新上传，然后选中自己想要新的图标，从新下载压缩包，并替换原来的文件即可。

点击“Import Icons”按钮，导入以前的selection.json文件。

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/9502a944c84b46c1bfd27acd339f8eb4/clipboard.png)

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/435420d650f44b5284e32b5191a8a550/clipboard.png)

选择要追加的图标。

重新生成，再下载。更换掉以前的。

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/8f68f7a73b504655b7bdc6a09047fa16/clipboard.png)

字体图标加载的原理：

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/4c38063ceda942a3bad823da66782036/clipboard.png)

## 3.CSS三角

网页中常见一些三角形，使用CSS直接画出来就可以，不必做成图片或者字体图标

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/9b6f19d678c341b68dccbddab1721077/clipboard.png)

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/d8995c70ea3b4a4f908204068b64248f/clipboard.png)

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/00c06caf32674d978fad7bb38bde0f14/clipboard.png)

div { width: 0; height: 0; line-height: 0; //兼容性，照顾低版本的浏览器，移动端或者高版本的浏览器不需要这两句话 font-size: 0; //兼容性，照顾低版本的浏览器，移动端或者高版本的浏览器不需要这两句话 border: 50px solid transparent; border-left-color : pink; }

案例：京东三角

<head>   <meta charset="UTF-8">   <meta http-equiv="X-UA-Compatible" content="IE=edge">   <meta name="viewport" content="width=device-width, initial-scale=1.0">   <title>Document</title>   <link rel="stylesheet" href="style.css"> </head> <body>      <div class="rectangle">     <div class="triangle"></div>   </div>

.triangle {   position: absolute;   left: 70px;   top:-18px;   width:0;   height: 0;   line-height: 0;   font-size: 0;   border: 10px solid transparent;   border-bottom-color : pink; } .rectangle {   position: relative;   width: 100px;   height: 200px;   background-color: red; }

## **4.CSS用户界面样式**

所谓的界面样式，就是更改一些用户操作样式，以便提高更好的用户体验。



**4.1 更改用户的鼠标样式 cursor**

li {cursor: pointer;}

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/1d8f17982db44702843f9536be24f605/clipboard.png)

  <li style="cursor: default;">默认箭头</li>   <li style="cursor: pointer;">小手</li>   <li style="cursor: move;"></li>   <li style="cursor: text;"></li>   <li style="cursor: not-allowed;"></li>

**4.2 去掉表单轮廓线 outline**

比如input或者是textarea。

给表单添加下列样式之后就可以去掉默认的蓝色边框。

outline: 0;  <!-- 或者 --> outline: none; 

**4.3 防止拖拽文本域  resize**

一般右下角可以拖拽，拖拽后会影响其他标签的布局，所以一般要去掉它的拖拽功能。

用以下语句实现。

textarea {    resize: none; }

注意：textarea标签换行的话，输入框中的文字和边框会有很大的距离。尽量使用该标签时尽量放到一行上去，中间不要用空格，文字和边框的距离用padding值来设定。

## 5.vertical-align属性应用

vertical-align 属性使用场景∶经常用于设置图片或者表单(行内块元素）和文字垂直对齐。

官方解释:用于设置一个元素的垂直对齐方式，但是它只针对于行内元素或者行内块元素有效。

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/bb87de6c426b43d1993f2abb0052e741/clipboard.png)

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/106856954c4c40ec8d864f9cda9f5f5d/clipboard.png)

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/ff2768ee67c2447a9b1b6fa0401e7a1f/clipboard.png)

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/490d9fa94e58426e9ceaf1b686a4f20d/clipboard.png)

**5.2 解决图片底部默认空白缝隙问题**

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/f092abb7e7a6433ea47e0d5820fb3e7c/clipboard.png)

## **6.溢出的文字省略号显示**

1.单行文本溢出显示省略号--必须满足三个条件

/*1．先强制一行内显示文本*/ white-space: nowrap;(默认normal自动换行) /*2．超出的部分隐藏*/ overflow: hidden; /*3．文字用省略号替代超出的部分*/ text-overflow : ellipsis;

内容为纯英文加数字时，设置为white-space: normal也不会换行。这种情况怎么处理呢？

2.多行文本溢出显示省略号

多行文本溢出显示省略号，有较大兼容性问题，适合于webKit浏览器或移动端（移动端大部分是webkit内核)

overflow : hidden ; text-overflow: ellipsis; /*弹性伸缩盒子模型显示*/ display: -webkit-box ; /*限制在一个块元素显示的文本的行数*/ -webkit-line-clamp: 2; /*设置或检索伸缩盒对象的子元素的排列方式*/ -webkit-box-orient: vertical;

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/533b88b689d44110b1454aa02ff1b7dc/clipboard.png)

**7.常见布局技巧**

[7.常见布局技巧](#5758-1626788409792)

[7.1 margin负值运用](#4048-1626788424507)

[7.2 文字围绕浮动元素](#2630-1626789098868)

[7.3 行内块巧妙运用](#8613-1626789901701)

[7.4 CSS三角强化](#2086-1626831014972)

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/88a4e31672c147b7b8d7098ed31ffaf5/clipboard.png)

**7.1 margin负值运用**

border设置为1px时，相邻盒子的border会是2px。使用margin负值，从而让border为1px。

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/476a40b87bdc475bb6f562bc80ce630b/clipboard.png)

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/6b67d4eb425e44ec833c0b48276acd62/clipboard.png)

引发的问题：欲使鼠标移动到该盒子时，边框颜色变化。前面的盒子的边框被压住了，不会变化。

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/14021548e41c485d87d7dc1548f43f8a/clipboard.png)

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/269ad4b09bbf46ddba15670e4fb71619/clipboard.png)

**7.2 文字围绕浮动元素**

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/4029d14711454d989dfca3584fac0191/clipboard.png)

让文字完全占满父盒子，它的宽就是父盒子的宽。

给左侧盒子添加一个浮动，文字不会被压住，会围绕这个左侧浮动的盒子。

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/a9c95a9a314a494a8a27049da2ae1972/clipboard.png)

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/e2c8ee5aee074e52b5f9f0c8f80ca4fd/clipboard.png)

**7.3 行内块巧妙运用**

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/2d0e916204454f07ac690d763d6f3f25/clipboard.png)

利用行内块元素的特征：

- 既可以设置宽高，又可以显示在一行上；
- 本身就有间距，不需要用margin设置。
- 给父盒子添加text-align：center属性，里面所有的行内块元素都会实现水平居中对齐。

## **7.4 CSS三角强化**

父盒子中的左侧子盒子设置浮动，右侧的文字部分就会围绕左侧子盒子浮动。再设置三角形使形状满足要求。

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/4fda007a270f41faa33f45fb1e17b14c/clipboard.png)

 /*1.只保留右边的边框有颜色*/ border-color: transparent red transparent transparent; /*2．样式都是soLid */ border-style: solid; /*3.上边框宽度要大，右边框宽度稍小，其余的边框该为0*/ border-width: 100px 50px 0 0 ;

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/8e2be8d5fea54f6893714d3d37e84bb2/clipboard.png)

视频中用的i标签，设置属性如下：

width: 0; height: 0; /*1.只保留右边的边框有颜色*/ border-color: blue red yellow green; /*2．样式都是soLid */ border-style: solid; /*3.上边框宽度要大，右边框宽度稍小，其余的边框该为0*/ border-width: 70px;

效果如图，与div标签实现三角形的结果不一样。

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/c88c0b04974445219e3c1e2513e4c3ae/clipboard.png)

div 设置属性后的效果如图：

![img](C:/Users/12141/AppData/Local/YNote/data/qqD9E90CC4A15CE7F1BBDB7ED036CBCA1E/8abd66c0861a4ca9a802dec3f6e30b79/clipboard.png)

# 问题：

1. 父盒子中的最后一个子元素的margin-bottom不能实现距离父元素底边的效果，解决方案：https://www.codetd.com/article/18854

![image-20210924161538588](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210924161538588.png)

想要使胡润百富这一行距离底边的距离为10px，即红框标出的距离没有，怎么处理？

用margin-bottom: 10px 解决不了

![image-20210924161817078](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210924161817078.png)

不能在父盒子中设定距底边距多少px，来定位吗？

**可以用子绝父相来定位。**

