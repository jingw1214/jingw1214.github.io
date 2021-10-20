> 视频地址：https://www.bilibili.com/video/BV15741177Eh

# 一、邂逅Vue.js

### 1.1 认识Vue.js
#### 1.1.1 为什么学习Vue.js
- 对原有的项目使用Vue进行重构。
- 新项目决定使用Vue的技术栈。
- 招聘前端的需求中，10个中有8个都对Vue有或多或少的要求。
- Vue.js目前是前端必备的一个技能。
#### 1.1.2 简单认识一下Vue.js
- Vue(读音/vju:/，类似于view)，注意不要读错。

- Vue是一个渐进式的框架，什么是渐进式的呢?
  - 渐进式意味着你可以将Vue作为你应用的一部分嵌入其中，带来更丰富的交互体验。
  - 或者如果你希望将更多的业务逻辑使用Vue实现，那么Vue的核心库以及其生态系统。
  - 比如Core+Vue+router+Vuex，可以满足各种各样的需求。

- Vue有很多特点和Web开发中常见的高级功能：
  - 解耦视图和数据
  - 可复用的组件
  - 前端路由技术
  - 状态管理
  - 虚拟DOM

- 学习Vuejs的前提：
  - 从零学习Vue开发，并不需要你具备其他类似于Angular、React，甚至是jQuery的经验。
  - 但是你需要具备一定的HTML、CSS、JavaScript基础。

### 1.2 安装Vue.js
#### 1.2.1 直接CDN引入

```html
可以选择引入开发环境版本还是生产环境版本
<! --开发环境版本，包含了有帮助的命令行警告 -->
<script src="https:/ /cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<! --生产环境版本，优化了尺寸和速度-->
<script src="https:// cdn.jsdelivr.net/npm/vue"></script>
```

#### 1.2.2 下载引入
开发环境：https: //vuejs.org/js/vue.js  ----本次学习使用该方法
生产环境：https:// /vuejs.org/js/vue.min.js

#### 1.2.3 NPM安装
后续通过webpack和CLI的使用，我们使用该方式。

### 1.3 体验Vue.js
#### 1.3.1 Hello Vuejs
- 创建一个Vue对象，并传入一个包含一些options的对象。
	* 对象中包含了`el`属性:该属性决定了这个Vue对象挂载到哪一个元素上，很明显，我们这里是挂载到了id为app的元素上
	* 对象中包含了`data`属性︰该属性中通常会存储一些数据
		+ 这些数据可以是我们直接定义出来的，比如像上面这样。
		+ 也可能是来自网络，从服务器加载的。
- Vue 代码是可以做到响应式的。
在控制台输入`app.message = '今天天气真好';`界面上就会对应显示“今天天气真好”

- Vue实例的作用范围：
Vue会管理`el`选项命中的**元素**及其内部的**后代元素**。

- 选择器的使用：
可以使用类选择器、标签选择器。
但是建议使用id选择器，因为开发的时候约定，id选择器是唯一的；而类选择器和标签选择器都可以命中多个元素，会造成语义的不清晰。

- 可以使用其他的双标签，比如p标签或者h1标签
注意：不要把Vue挂载在\<html> 或者\<body>标签上，建议\<div>作为挂在的元素，因为它没有独有的样式。

```html
<div id="app">{{message}}</div>
<!-- 导入开发版本的Vue.js -->
<script src="../js/vue.js"></script>
<script>
	//创建Vue实例对象，设置el属性和data属性
    //对原HTML进行解析和修改
    const app = new Vue({
    	// 设置Vue实例挂载（管理）的元素
    	//设置之后，el命中的元素内部使用两个大括号修饰的部分，会被data中同名的数据替换
        el:"#app", 
        data: {    // 定义数据
            message: '你好啊，李银河！'
        }
    })
</script>
```
注：这里创建实例使用的是const关键字。（es6使用let（变量） 和 const（常量）这两个关键字来声明，var关键字不再使用，因为存在设计缺陷。）Vue实例不用修改，故使用const 关键字创建实例。

Vue的编程范式：声明式编程
*[声明式编程]:当实例去管理div时，只需要告诉写什么东西就可以了。内部怎么处理，我们不用管。
好处：数据和界面分离

元素js的做法(编程范式:命令式编程)：
*[命令式编程]:   一步一步的去做
1.创建div元素,设置id属性
2.定义一个变量叫message
3.将message变量放在前面的div元素中显示
4.修改message的数据
5.将修改后的数据再次替换到div元素中

#### 1.3.2 Vue列表展示

HTML代码中，使用`v-for`指令展示一个更加复杂的数据--数据列表。

```html
<div id="app">
     <ul>
         <li v-for="item in movies">{{item}}</li>
     </ul>
 </div>    
 <script src="../js/vue.js"></script>
 <script>
     const app = new Vue({
         el: '#app',
         data: {
             message: '你好啊',
             movies: ['海贼王','火影忍者','破产姐妹']
         }
     })
 </script>
```

- 不需要在JavaScript代码中完成DOM的拼接相关操作。
- 是响应式的，当我们数组中的数据发生改变时，界面会自动改变。开发者模式的console ，输入`app.movies.push= '你是我的荣耀';`界面上就会对应追加显示

#### 1.3.3 案例∶计数器
实现一个小的计数器：
![在这里插入图片描述](https://img-blog.csdnimg.cn/f7aade37d7434417a511b5970ebe5c79.png)

	点击＋：计数器+1
	点击-：计数器-1
使用新的指令和属性：
- `methods`属性，该属性用于在Vue对象中定义方法。
- `v-on:click`指令（语法糖：`@click`），该指令用于监听某个元素的点击事件，并且需要指定当发生点击时，执行的方法（通常是methods中定义的方法）。
*[语法糖]:简写
```html
<div id="app">
    <h2>当前计数：{{counter}}</h2>
    <!-- 用下面2个语句也能实现，但是html 和数据没有分离 -->
    <!-- <button v-on:click="counter++">+</button>
    <button v-on:click="counter--">-</button> -->
    <button v-on:click="add">+</button>
    <button v-on:click="sub">-</button>
</div>
<script src="../js/vue.js"></script>
<script>
    const app = new Vue({
        el: '#app',
        data: {
            counter:0
        },
        methods: {
            add: function () {
                this.counter++;
            },
            sub: function () {
                this.counter--;
            }
        }
    })
</script>
```

### 1.4 MVVM 架构
#### 1.4.1 data和Vue对象的分离
#### 1.4.2 Vue中的MVVM


什么是MVVM
维基百科：https://zh.wikipedia.ora/wiki/MVVM
Vue 的MVVM:
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/abb368eb206a4bbba1344e75d107db63.png)
- view层:
	* 视图层
	* 在我们前端开发中，通常就是DOM层。
	* 主要的作用是给用户展示各种信息。
- Model层:
	*  数据层
	* 数据可能是我们固定的死数据,更多的是来自我们服务器，从网络上请求下来的数据。
	* 在我们计数器的案例中，就是后面抽取出来的obj，当然,里面的数据可能没有这么简单。
- vueModel层:
	* 视图模型层
	* 视图模型层是view和lModel沟通的桥梁。
	* 一方面它实现了Data Binding，也就是数据绑定，将Model的改变实时的反应到view中
	* 另一方面它实现了DOM Listener，也就是DOM监听，当DOM发生一些事件(点击、滚动、touch等)时，可以监听到，并在需要的情况下改变对应的Data。

### 1.5 创建Vue 实例传入的options选项
创建Vue实例的时候，传入了一个对象options。这个options可以包含的选项详细解析：https://cn.vuejs.org/v2/api/#el

目前掌握这些选项:
#### 1.5.1 el:
- 类型: string | HTMLElement
- 作用∶决定之后Vue实例会管理哪一个DOM.

#### 1.5.2 data:
- 类型:Object | Function
- 作用:Vue实例对应的数据对象。

#### 1.5.3 methods:
- 类型:{[key: string]: Function }
- 作用︰定义属于Vue的一些方法，可以在其他地方调用，也可以在指令中使用。

#### 1.5.4 vue的生命周期函数
查看声明周期图示：

https://cn.vuejs.org/v2/guide/instance.html#%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F%E5%9B%BE%E7%A4%BA

在实例的options对象里，除了可以传以上的选项外，还可以传生命周期的函数。

![image-20210916202308069](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210916202308069.png)

☆ 在VScode 中搜索 tabsize，可以修改缩进为2，更为标准。
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/605bf93eb7324e778f148cb5b94e7688.png)
# 二、Vue基础语法
### 1 插值语法
将值插入到我们模板的内容当中的Vue指令。
#### 1.1 Mustache
使用Mustache[məˈstɑːʃ]语法（也就是双大括号），将data中的文本数据，插入到HTML中。
并且数据是响应式的。

```html
<div id="app">
  <h2>{{message}}</h2>
  <!-- mustache 语法中，不仅仅可以直接写变量，还可以写简单的表达式 -->
  <h2>{{message + name}}。吃了吗？</h2>
  <h2>{{message}}{{name}}。吃了吗？</h2>
  <h2>{{counter * 2}}</h2>
</div>
<script src="../js/vue.js"></script>
<script>
  const app = new Vue({
    el: '#app',
    data: {
      message:'你好啊，',
      name: '张三',
      counter: 100
    }
})
</script>
```
#### 1.2 v-once
`v-once` 指令表示元素和组件(组件后面才会学习)只渲染一次，不会随着数据的改变而改变。
该指令后面**不**需要跟任何表达式(v-for后面是有跟表达式的)

```html
<div id="app">
  <h2>{{message}}</h2>
  <!-- mustache 语法中，不仅仅可以直接写变量，还可以写简单的表达式 -->
  <!-- 当设置了v-on指令后，在开发者模式的console中，修改app.message的值，界面中的显示不变 -->
  <h2 v-once>{{message}}</h2>
</div>
<script src="../js/vue.js"></script>
<script>
  const app = new Vue({
    el: '#app',
    data: {
      message:'你好啊，',
      name: '张三',
      counter: 100
    }
})
</script>
```
在开发者模式的console中，修改app.message的值后，设置了v-on指令的元素，显示不变。

console控制台输入：
![在这里插入图片描述](https://img-blog.csdnimg.cn/43c6be435e484411b51e0999a7ea2f09.png)
界面显示：
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/68682b8c773f479b97e662eba4c12777.png)
#### 1.3 v-html
数据中有 html 标签时，使用`v-html`指令，设置标签的innerHTML，按照html格式进行解析，并显示对应的内容。；而不是直接显示数据本身。
代码如下：

```html
<body>
    <!--html结构-->
    <div id="app">
        <!--使用指令渲染上去-->
        <p v-html="content"></p>
        <p v-text="content"></p>
    </div>
    <!-- 导入开发版本的Vue.js -->
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    
    <script>
        //创建Vue实例
        var app = new Vue({
            el:"#app",
            data:{
                //content:"黑马程序员",
                content:"<a href='http://www.itheima.com'>黑马程序员</a>"
            }
        })
    </script>
</body>
```
网页显示如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/decf7117dd334e098281761571a6ed4f.png)
#### 1.4 v-text
`v-text` 指令可以展示数据，和`mustache`语法的功能差不多。区别在于`v-text`指令不够灵活，不能完成数据与标签中内容的拼接，会进行覆盖。所以比起mustache语法用的比较少。

```html
<div id="app">
  <!-- mustache插值语法可以拼接字符串 -->
  <h2>{{message}}李四</h2>
  <!-- v-text 不够灵活，会覆盖标签中的内容-->
  <h2 v-text="message">，李四</h2>
</div>
<script src="../js/vue.js"></script>
<script>
  const app = new Vue({
    el: '#app',
    data: {
      message:'你好啊，',
      name: '张三',
      counter: 100
    }
})
</script>
```
显示结果如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/5eaa4761e6424a908034326ac9e0af29.png)
#### 1.5 v-pre
`v-pre`用于跳过这个元素和它子元素的编译过程，用于显示原本的Mustache语法{{}}。
比如下面的代码:

```html
 <div id="app">
    <!-- mustache插值语法可以拼接字符串 -->
    <h2>{{message}}</h2>
    <!-- v-text 会覆盖标签中的内容-->
    <h2 v-pre="message">{{message}}</h2>
  </div>
  <script src="../js/vue.js"></script>
  <script>
    const app = new Vue({
      el: '#app',
      data: {
        message:'你好啊'
      }
  })
  </script>
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/0d1d020837ac4739b3f12f983e53e41a.png)

- 第一个h2元素中的内容会被编译解析出来对应的内容
- 第二个h2元素中会直接显示{{message}}


#### 1.6 v-cloak
在某些情况下，我们浏览器可能会直接显然出未编译的Mustache标签。
设置了`v-cloak`指令的标签，在vue解析之前,有属性v-cloak；在vue解析之后，没有v-cloak属性，避免加载过程中显示出未编译的mustache标签的情况。

```html
<head>
  <style>
  	 <!-- 设置有 v-cloak 指令的标签不显示-->
    [v-cloak] {
      display: none;
    }
  </style>
</head>
```

```html
<body>
  <div id="app">
    <h2>{{message}}</h2>
    <!-- 设置了v-cloak的h2，在vue解析之前,有属性v-cloak；在vue解析之后，没有v-cloak属性-->
    <h2 v-cloak>{{message}}</h2>
  </div>
  <script src="../js/vue.js"></script>
  <script>
  	// setTimeout(function() {},1000) 函数延迟1秒钟
    setTimeout(function () {
      const app = new Vue({
        el: '#app',
        data: {
          message:'你好啊',
          name: '张三',
          counter: 100
        }
      })
    },1000)
  </script>
```

### 2 绑定属性
#### 2.1 v-bind的介绍
使用`v-bind`指令∶
作用：动态绑定**属性**
缩写：`:`
预期：any (with argument) | Object (without argument)
参数：attrOrProp (optional)

`v-bind`用于绑定一个或多个属性值，或者向另一个组件传递props值(这个学到组件时再介绍)
在开发中，有很多属性需要动态进行绑定，比如图片的链接src、网站的链接href、动态绑定一些类、样式等等。

#### 2.2 v-bind 绑定基本属性
比如通过Vue实例中的data绑定元素的src和href，代码如下∶

```html
  <div id="app">
    <!-- v-bind 给src 赋值 -->
    <img v-bind:src="imageUrl" alt="">
    <!-- v-bind 给href 赋值 -->
    <a v-bind:href="aHref">百度一下</a>
  </div>
    <script src="../js/vue.js"></script>
    <script>
      const app = new Vue({
        el: '#app',
        data: {
          message: 'hello Vue',
          imageUrl: 'https://img11.360buyimg.com/seckillcms/s140x140_jfs/t1/187467/26/6629/80813/60ba0541Ef4868511/1f190ae8e1af3920.jpg.webp',
          aHref: 'http://baidu.com'
        }
      })
    </script>
```

#### 2.3 v-bind语法糖
`v-bind`有一个对应的语法糖，也就是简写方式`:`。
在开发中，我们通常会使用语法糖的形式，因为这样更加简洁。

简写方式如下:

```html
  <div id="app">
    <!-- v-bind 给src 赋值，语法糖写法 -->
    <img :src="imageUrl" alt="">
    <!-- v-bind 给href 赋值，语法糖写法 -->
    <a :href="aHref">百度一下</a>
  </div>
```

#### 2.4 绑定class
动态绑定class 的方式根据绑定方式分为两种：

**1.对象语法**
class后面跟的是一个对象：
`:class: {class名：boolean}`

用法如下：

```html
<div id="app">
    <!-- 用法一：直接通过{}绑定一个类 -->
    <h2 :class="{'active': isActive}">Hello world</h2>

    <!-- 用法二：也可以通过判断，传入多个值 -->
    <h2 :class=" {'active': isActive, 'line': isLine}">Hello world</h2>

    <!-- 用法三：和普通的类同时存在，并不冲突 -->
    <!-- 注:如果isActive和isLine都为true，那么会有title/active/line三个类 -->
    <h2 class="title" :class=" { ' active': isActive，'line': isLine}" Hello world</h2>
	
	<!-- 用法四：如果过于复杂，可以放在一个methods或者computed中 -->
    <!-- 注: classes是一个计算属性 -->
    <h2 class="title" :class="getClasses()" >Hello world</h2>
    
    <button @click="changeColor">变色</button>
  </div>
    <script src="../js/vue.js"></script>
    <script>
      const app = new Vue({
        el: '#app',
        data: {
          message: 'hello Vue',
          isActive: true,
          isStrong: true
        },
        methods: {
          changeColor: function () {
            this.isActive = !this.isActive
          },
          getClasses: function () {
				return {active: this.isActive,line: this.isLine};
			}
        }
      })
    </script>
```

**2.数组语法**
class后面跟的是一个数组，用的较少。
用法如下：

```html
<div id="app">
    <!-- 用法一:直接通过[]绑定一个类 -->
    <!-- 'active'代表一个字符串 active代表变量 -->
    <h2 :class="['active']">Hello world</h2>

    <!-- 用法二:也可以传入多个值 -->
    <h2 :class="['active', 'line']">Hello world</h2>

    <!-- 用法三:和普通的类同时存在，并不冲突 -->
    <!-- 注:会有title/active/line三个类 -->
    <h2 class="title" :class="['active', 'line' ]">Hello world</h2>

    <!-- 用法四:如果过于复杂，可以放在一个methods或者computed中 -->
    <!-- 注:classes是一个计算属性 -->
    <h2 class="title" :class="getClasses">Hello world</h2>
    <button @click="changeColor">变色</button>
  </div>
  <script src="../js/vue.js"></script>
  <script>
    const app = new Vue({
      el: '#app',
      data: {
        message: 'hello Vue',
        active: 'aaa',
        line: 'bbb'
      },
      methods: {
        changeColor: function () {
          this.isActive = !this.isActive
        },
        getClasses: function () {
          return [this.active, this.line]
        }
      }
    })
  </script>
```
☆ 小作业

```html
  <!-- 使用v-for 和v-bind，完成作业 -->
  <!-- 作业需求：网页中有一个4个选项的列表，初次加载，第一项为红色。点击列表中的某一项，该项的字体颜色设置为红色，其他复原为黑色 -->
  <div id="app">
    <ul>
      <li :class="{'active': current === index}" @click="changeColor(index)" v-for="(m, index) in movies">{{index}}-{{m}}</li>
    </ul>
  </div>
  <script src="../js/vue.js"></script>
  <script>
    const app = new Vue({
      el: '#app',
      data: {
        movies: ['你是我的荣耀','三生三世枕上书','火隐忍者','眷思量'],
        current: 0
      },
      methods: {
        changeColor: function (i) {
          this.current = i;
        }
      }
    })
  </script>
  
```

#### 2.2.1 绑定样式
利用`v-bind:style`来绑定一些CSS内联样式。

在写CSS属性名的时候，比如font-size
1.我们可以使用驼峰式(camelCase)  fontSize
2.或短横线分隔(kebab-case，记得用单引号括起来) ‘font-size'

动态绑定 样式 的方式根据绑定方式分为两种：
**绑定方式一：对象语法**

```html
:style:"{color:currentColor, fontSize: fontSize + 'px'}"
```
style后面跟的是一个对象类型
- 对象的 key 是**CSS属性名称**
- 对象的 value 是具体赋的值，值可以来自于data中的属性

示例代码：
```html
<div id="app">
  <!-- :style后面跟的对象中的key值，是CSS属性名称 -->
  <!-- 要么是驼峰式写法，要么外面用单引号包围，里面用 - 符号连接单词 -->
  <h2 :style="{fontSize: fontSize + 'px', 'background-Color': finalColor}">{{message}}</h2>
</div>
<script src="../js/vue.js"></script>
<script>
  const app = new Vue({
    el: '#app',
    data: {
      message: 'Hello Vue',
      fontSize: 100,
      finalColor: 'pink', 
    }
  })
</script>
```
如果对象写起来过长，可以抽取这个对象，写在methods里。代码如下：

```html
  <div id="app">
    <!-- 如果对象写起来过长，可以抽取这个对象，放到methods里面 -->
    <h2 :style="getStyles()">{{message}}</h2>
  </div>
  <script src="../js/vue.js"></script>
  <script>
    const app = new Vue({
      el: '#app',
      data: {
        message: 'Hello Vue',
        fontSize: 100,
        finalColor: 'pink', 
      },
      methods: {
        getStyles: function () {
          return {
            fontSize: this.fontSize + 'px', 
            'background-Color': this.finalColor
          }
        }
      }
    })
  </script>
```

**绑定方式二：数组语法**

```html
<div v-bind:style: "[baseStyles, overridingStyles]"></div>
```
`:style` 后面跟的是一个数组类型，数组中的多个值以`,`分隔。
注：位于前面的值设置的CSS属性，会被位于后面的值设置的CSS属性给覆盖。
示例代码：

```html
<div id="app">
  <!-- 数组语法 -->
  <h2 :style="[baseStyles,overridingStyles]">{{message}}</h2>
</div>
<script src="../js/vue.js"></script>
<script>
  const app = new Vue({
    el: '#app',
    data: {
      message: 'Hello Vue',
      baseStyles: {
        color: 'red',
        'font-size': '100px'
      },
      overridingStyles: {
        color: 'pink',
        backgroundColor: 'purple'
      }
    },
    methods: {
      getStyles: function () {
        return {
          fontSize: this.fontSize + 'px', 
          'background-Color': this.finalColor
        }
      }
    }
  })
</script>
```

### ☆ 1 计算属性 -- computed
通过`插值语法`，可以直接显示一些data中的数据。
使用`计算属性`，可以对数据进行一些转化后再显示，或者将多个数据结合起来进行显示。比如有firstName和lastName两个变量，需要显示完整的名称。
计算属性是写在实例的`computed`选项中的。

#### 1.1计算属性的基本使用

示例代码如下：
```html
<div id="app">
  <!-- 直接写计算属性，不用加小括号 -->
  <h2>{{fullname}}</h2>
</div>
<script src="../js/vue.js"></script>
<script>
  const app = new Vue({
    el:'#app',
    data: {
      firstname: 'zhang',
      lastname:'san'
    },
    // 计算属性，是当做属性来使用的
    computed: {
      // 定义的是函数
      // 一般都是名词
      fullname: function () {
        return this.firstname +' ' + this.lastname;
      }
    }
  })
</script>
```
#### 1.2 计算属性的复杂操作
```html
<!-- 写出书的总价格 -->
<div id="app">
  <!-- 直接写计算属性，不用加小括号 -->
  <h2>总价格：{{totalPrice}}</h2>
</div>
<script src="../js/vue.js"></script>
<script>
  const app = new Vue({
    el:'#app',
    data: {
      books: [
      {id: 110, name:'unix编程艺术', price: 119},
      {id: 111, name:'代码大全', price: 105},
      {id: 112, name:'深入理解计算机原理', price: 98},
      {id: 113, name:'现代操作系统',price: 87},
    ]
    },
    // 计算属性，是当做属性来使用的
    computed: {
      // 定义的是函数
      // 一般都是名词
      totalPrice: function () {
        let result = 0;
        for (let i = 0; i < this.books.length; i++) {
          result += this.books[i].price;
        }
        return result;
      }
    }
  })
</script>
```
#### 1.3 计算属性的完整写法
计算属性一般是没有`set方法`的，只有只读属性。
在需要写`set方法`时，完整写法如下：

```html
  <div id="app">
  	<!-- fullName 其实是一个属性，不是个函数，不用写小括号 -->
    <h2>{{fullName}}</h2>
  </div>
  <script src="../js/vue.js"></script>
  <script>
    const app = new Vue({
      el:'#app',
      data: {
        firstname: 'zhang',
        lastname: 'san'
      },
      // 计算属性，是当做属性来使用的
      computed: {
        // 定义的是函数
        // 一般都是名词
        fullName: {
          // 写fullName
          // 开发者模式中的console中输入：`app.fullName = 'li si';`会将'li si'作为参数 newValue，执行set函数。
          // <h2>标签中显示 ‘li si’
          set: function (newValue) {
            const names = newValue.split(' ');
            this.firstname = names[0],// 'li'
            this.lastname = names[1]  // 'si'
          },
          // 读 fullName
          get: function () {
            return this.firstname + ' ' + this.lastname;
          }
        }
      }
    })
  </script>
```

#### 1.4 计算属性的缓存
methods和computed计算属性的对比：
计算属性会进行缓存，如果多次使用时，没有发生变化，计算属性只会调用一次，性能更高。

代码如下：

```html
<div id="app">
    <!-- 1.mustache直接拼接：语法过于繁琐 -->
    <h2>{{firstname}} {{lastname}}</h2>
    <!-- 2.通过 methods 方法返回显示 -->
    <h2>{{getFullname()}}</h2>
    <h2>{{getFullname()}}</h2>
    <h2>{{getFullname()}}</h2>
    <h2>{{getFullname()}}</h2>
    <!-- 3.通过computed -->
    <h2>{{fullName}}</h2>
    <h2>{{fullName}}</h2>
    <h2>{{fullName}}</h2>
    <h2>{{fullName}}</h2>
  </div>
  <script src="../js/vue.js"></script>
  <script>
    const app = new Vue({
      el:'#app',
      data: {
        firstname: 'zhang',
        lastname: 'san'
      },
      // 计算属性，是当做属性来使用的
      computed: {
        // 定义的是函数
        // 一般都是名词
        fullName: {
          // 写fullName
          set: function (newValue) {
            const names = newValue.split(' ');
            this.firstname = names[0],
            this.lastname = names[1]
          },
          // 读 fullName
          get: function () {
            console.log('fullName');
            return this.firstname + ' ' + this.lastname;
          }
        }
      },
      methods: {
        getFullname: function () {
          console.log('getFullname');
          return this.firstname + ' ' + this.lastname;
        }
      }
    })
  </script>
```
开发者模式的控制台显示如下，说明每次都会调用getFullName()方法，而使用计算属性fullName时，只会调用一次。
![在这里插入图片描述](https://img-blog.csdnimg.cn/9ad15930da104c0fb88943d857989c37.png)
控制台输入：`app.firstname = 'wang;`控制台输出如下，说明：当数据发生变化后，methods 和 computed 都会再次调用。
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/a56fb3fff9044eccbe9bd15945c1bf36.png)

### 3 事件监听
在Vue中，使用`v-on`指令监听用户事件发生的时间，比如点击、拖拽、键盘事件等等用于交互。

#### 3.1 v-on介绍
作用:绑定事件监听器
缩写:@
预期:Function | Inline Statement | Object
参数:event
#### 3.2 v-on基础
使用`v-on:click="counter++"`监听按钮的点击事件，
使用`v-on:click="函数名"`将事件指向一个在methods中定义的函数

#### 3.3 v-on参数
当通过methods中定义方法，以供@click调用时，需要注意参数问题：
- 情况一︰如果该方法不需要额外参数，那么方法后的()可以不添加。
	* 但是注意︰如果方法本身中有一个参数，那么会默认将原生事件event参数传递进去
- 情况二︰如果需要同时传入某个参数，同时需要event时，可以通过`$event`传入事件。

```html
  <div id="app">
    <!-- 事件调用方法时可以不写小括号 -->
    <button @click="btn1Click()">按钮1</button>
    <button @click="btn1Click">按钮1</button>
    <!-- 在事件定义时，写函数时省略了小括号，但是方法本身是需要一个参数的，这个时候 Vue会默认将浏览器生成的event 对象作为形参传入到方法 -->
    <button @click="btn2Click">按钮2</button>
    <!-- 在事件定义时，写函数时省略了小括号，但是方法本身是需要一个参数的，这个时候 Vue会默认将浏览器生成的event 对象作为第一个形参传入到方法 -->
    <button @click="btn3Click">按钮3</button>
     <!-- 方法定义时，我们需要event 对象，同时有需要其他参数 -->
    <!-- 在调用方法时，如何手动的获取到浏览器产生的event对象：$event -->
    <button @click="btn4Click(123,$event)">按钮4</button>
  </div>
  <script src="../js/vue.js"></script>
  <script>
    const app = new Vue({
      el: '#app',
      data: {
        message: 'hello'
      },
      methods: {
        btn1Click() {
          console.log('btn1Click');
        },
        btn2Click(event) {
          console.log(event);// abc为浏览器生成的事件
        },
        btn3Click(abc,event) {
          console.log(abc,event);// abc为浏览器生成的事件 event 为undefined
        },
        btn4Click(count,event) {
          console.log('++++',abc,event);// abc为浏览器生成的事件
        },
      }
    })
  </script>
```

#### 3.4 v-on修饰符
- 在某些情况下，我们拿到event的目的可能是**进行一些事件处理**。
- Vue提供了修饰符来帮助我们方便的处理一些事件：
	* `.stop` - 调用event.stopPropagation()。
	* `.prevent` - 调用event.preventDefault()。
	* `.{keyCode | keyAlias}` （键盘按键的编码或者别名）- 当事件是特定键触发时才触发回调。
	* `.native` - 监听组件根元素的原生事件。
	* `.once` - 只触发一次回调。

1..stop修饰符的使用：停止事件冒泡
```html
<div @click="divClick">
      <!-- 事件冒泡：点击button，父元素div的点击事件也会调用 -->
      <button @click.stop="btnClick">按钮</button>
</div>
```
2.`.prevent`修饰符的使用：阻止默认行为

```html
<!-- .prevent修饰符的使用：阻止默认的事件处理，使用自己写的监听方法 -->
    <!-- 如下使用，则点击submit按钮，不再将baidu加在路径后面进行跳转，而是执行submitClick方法 -->
    <form action="baidu">
      <input type="submit" value="提交" @click.prevent="submitClick">
       <!-- 如下使用，阻止默认行为，没有表达式 -->
      <input type="submit" value="提交" @click.prevent>
    </form>
```
3.`.{keyCode | keyAlias}` - 监听某个键盘的键帽事件

```html
   <!-- 3.监听某个键盘的键帽弹起 -->
    <input type="text" @keyup="keyUp">
    <!-- 3.监听回车的弹起-键别名 -->
    <input type="text" @keyup.enter="enter">
    <!-- 3.监听回车的弹起-键编码 -->
    <input type="text" @keyup.13="enter">
```
4.`.native` - 与组件相关，待补 
5.`.once` - 只触发一次回调

```html
<!-- .once修饰，click只触发一次回调 -->
    <button @click.once="once">按钮</button>
```
6.串联修饰符

```html
<button @click.stop.prevent="doThis"></button>
```

### 4 条件和循环
#### 4.1 条件判断
`v-if`、`v-else-if`、`v-else`
- 这三个指令与JavaScript的条件语句if、 else、else if类似。
- Vue的条件指令可以根据表达式的值在DOM中渲染或销毁元素或组件

简单的案例演示：

```html
  <div id="app">
    <p v-if="score>=90">优秀</p>
    <p v-else-if="score>=80">良好</p>
    <p v-else-if="score>=60">及格</p>
    <p v-else>不及格</p>
  </div>
  <script src="../js/vue.js"></script>
  <script>
    const app = new Vue({
      el:'#app',
      data: {
        score:90
      }
    })
  </script>
```

`v-if`的原理:
- `v-if`后面的条件为`false`时，对应的元素以及其子元素不会渲染
- 也就是根本不会有对应的标签出现在DOM中。

**条件渲染案例：**
用户在登录时，可以切换使用用户账号登录还是邮箱地址登录。
页面初始界面：
![在这里插入图片描述](https://img-blog.csdnimg.cn/9200eb7b8cf9489a8ad592c09d459cf5.png)
点击“切换类型”按钮界面：
![在这里插入图片描述](https://img-blog.csdnimg.cn/03edef0f1b0e42369e684b8e50ecfa14.png)


```html
  <div id="app">
    <span v-if="isUser">
      <label for="username">用户账号</label>
      <input type="text" id="username" placeholder="用户账号">
    </span>
    <span v-else>
      <label for="email">用户邮箱</label>
      <input type="text" id="email" placeholder="用户邮箱">
    </span>
    <button @click="isUser = !isUser">切换类型</button>
  </div>
  <script src="../js/vue.js"></script>
  <script>
    const app = new Vue({
      el:'#app',
      data: {
        isUser: true
      }
    })
  </script>
```

**案例小问题：**
问题：
如果我们在有输入内容的情况下，切换了类型，我们会发现文字依然显示之前输入的内容。
但是按道理讲，我们应该切换到另外一个input元素中了。在另一个input元素中，我们并没有输入内容。

为什么会出现这个问题呢?
这是因为Vue在进行DOM渲染时，出于性能考虑，会尽可能的复用已经存在的元素,而不是重新创建新的元萃-
在上面的案例中，Vue内部会发现原来的input元素不再使用，直接作为else中的input来使用了。

解决方案:
- 如果我们不希望Vue出现类似重复利用的问题，可以给对应的input添加`key`
- 并且我们需要保证`key`的不同

```html
<div id="app">
    <span v-if="isUser">
      <label for="username">用户账号</label>
      <input type="text" id="username" placeholder="用户账号" key="username">
    </span>
    <span v-else>
      <label for="email">用户邮箱</label>
      <input type="text" id="email" placeholder="用户邮箱" key="email">
    </span>
    <button @click="isUser = !isUser">切换类型</button>
```
**v-show**
v-if和v-show对比
相同点：
- `v-show`的用法和`v-if`非常相似，也用于决定一个元素是否显示。

不同点：
- v-if当条件为false时，压根不会有对应的元素在DOM中。
- v-show当条件为false时，仅仅是将元素的`display`属性设置为none而已。

使用场景：
- 需要在显示与隐藏之间切片很频繁时，使用`v-show`
- 当只有一次切换时，通过使用`v-if`

#### 4.2 循环遍历
##### 4.2.1 v-for 遍历数组
使用`v-for`进行数组的渲染，语法格式：`v-for="item in items"`。
如果遍历的过程中需要拿到元素在数组中的索引值，则语法格式为：`v-for="(item,index) in items`
```html
<div id="app">
    <!-- 1.在遍历的过程中，没有使用索引值 -->
    <ul>
      <!-- 在元素的内容中，可以用mustache语法使用item -->
      <li v-for="item in names">{{item}}</li>
    </ul>
    <!-- 2.在遍历的过程中，获取索引值 -->
    <ul>
      <li v-for="(item,index) in names">{{index+1}}.{{item}}</li>
    </ul>
  </div>
  <script src="../js/vue.js"></script>
  <script>
    const app = new Vue({
      el:'#app',
      data: {
        names: ['why','cobe','james','curry']
      }
    })
  </script>
```
##### 4.2.1 v-for 遍历对象

示例代码如下：
```html
  <div id="app">
    <!-- 1.遍历对象的过程中，如果只是获取一个值，那么获取到的是value -->
    <ul>
      <li v-for="value in info">{{value}}</li>
    </ul>
    <!-- 2.获取key和value 格式：(value,key) -->
    <ul>
      <li v-for="(value,key) in info">{{key}}：{{value}}</li>
    </ul>
    <!-- 3.获取key和value和index 格式：(value,key,index) 用的很少 -->
    <ul>
      <li v-for="(value,key,index) in info">{{index}}.{{key}}：{{value}}</li>
    </ul>
  </div>
  <script src="../js/vue.js"></script>
  <script>
    const app = new Vue({
      el:'#app',
      data: {
        info: {
          name: 'why',
          age: 18,
          height: 1.88
        }
      }
    })
  </script>
```
显示如下图：
![在这里插入图片描述](https://img-blog.csdnimg.cn/92f9723f05554d0188cc11258b6b8e89.png)
☆ 组件的key属性
为了高效的更新虚拟DOM，官方推荐使用v-for时，给对应的元素或组件**添加上一个`key`属性**（不可以是index，因为不是一一对应的。一旦位置啥的发生变化，index就变化了）。
和Vue的虚拟DOM的Diff算法有关系。当某一层有很多相同的节点时，也就是列表节点时，插入一个新的节点。比如在列表`letters: ['A','B','C','D','E']`中的B和C之间加一个F：`app.letters.splice(2,0,'F')`，Diff算法默认执行起来是这样的：把C更新成F，D更新成C，E更新成D，最后再插入E。这样很没有效率。

所以我们需要使用key来给每个节点做一个唯一标识，Diff算法就可以正确的识别此节点，找到正确的位置区插入新的节点。
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/35f75c16111f47fa894b83a551ff5313.png)
绑定key属性的示例代码：
```html
 <div id="app">
    <ul>
    <!-- 加上key属性-->
      <li v-for="item in letters" :key="item">{{item}}</li>
    </ul>
  </div>
  <script src="../js/vue.js"></script>
  <script>
    const app = new Vue({
      el:'#app',
      data: {
        letters: ['A','B','C','D','E']
      }
    })
  </script>
```
☆ 检测数组更新
因为Vue是响应式的，所以当数据发生变化时，Vue会自动检测数据变化，视图会发生对应的更新。
Vue中包含了一组观察数组编辑的方法，使用它们改变数组也会触发视图的更新。
- push()
- pop()
- shift()
- unshift()
- splice()
- sort()
- reverse()

使用代码如下：
```html
  <div id="app">
    <ul>
      <li v-for="item in letters" :key="item">{{item}}</li>
    </ul>
    <button @click="btnClick">按钮</button>
  </div>
  <script src="../js/vue.js"></script>
  <script>
    const app = new Vue({
      el:'#app',
      data: {
        letters: ['A','B','C','D','E','F']
      },
      methods: {
        btnClick() {
          // 1.push方法--响应式
          this.letters.push('1','2');

          // 2.pop方法-- 删除数组中的最后一个元素 -- 响应式
          this.letters.pop();

          // 3.shift()：删除数组中的第一个元素
          this.letters.shift();

          // 4.在数组最前面添加元素
          this.letters.unshift('1','2');

          // 5.splice()作用：删除元素/插入元素/替换元素
          // 删除：第一个参数：开始元素的位置；第二个参数：删除几个元素（不传的话就删除后面所有的元素）
          this.letters.splice(2,3); // 从第3个元素开始删掉3个
          // 替换：第2个参数：要替换几个元素；后面是用于替换前面的元素
          // 可以理解为：先删掉几个元素，再插入后面的元素
          this.letters.splice(2,3,'1','2','3'); // 把第2个元素后面的3个元素替换为1,2,3
          // 插入：第2个参数传入0，表示要删掉0个元素；后面的元素时要插入的元素
          this.letters.splice(2,0,'1','2','3');
          
          // 6.sort()：排序
          this.letters.sort();

          // 7.reverse()：翻转
          this.letters.reverse();

          // 注意：通过索引值修改数组中的元素 -- 非响应式
          // Vue 不监听，界面不改变
          this.letters[0]='bbb';
          // 可以换下面这种写法--可以做到响应式
          this.letters.splice(0,1,'bbb');
          // set(要修改的对象，索引值，修改后的值) -- 响应式
          Vue.set(this.letters, 0, 'bbb');
        }
      }
    })
  </script>
```

### 5 阶段案例
图书购物车
![在这里插入图片描述](https://img-blog.csdnimg.cn/f73d5037abe5448c9a4ae7faa4b2ec19.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMzMzkwNzAw,size_16,color_FFFFFF,t_70)



### 6 表单绑定
`v-model`获取和设置**表单元素**的值（双向数据绑定）
- v-model指令的作用是便捷的设置和获取表单元素的值
- 绑定的数据会和表单元素的值相关联
- 绑定的数据←→表单元素的值
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/7baebaf10aaa47ed8064174d5d96d7e0.png)
#### 6.1 基本使用
更改两边中任意一方的值，都会同步改变对方的值。

```javascript
  <div id="app">
      <!--在输入框中输入值时，message的值随之改变-->
      <input type="text" v-model="message" >
      {{message}}
  </div>
  <script src="../js/vue.js"></script>
  <script>
      var app = new Vue({
          el:"#app",
          data:{
              message:"message",
          }
      })
  </script>
```
也可以将`v-model`用于`textarea`元素。

#### 6.2 v-model原理
`v-model`其实是一个语法糖，它的背后本质上是包含两个操作：
1.`v-bind`绑定value属性，将message放到value里；
2.`v-on`指令给当前元素绑定input事件，监听用户输入。通过事件event，给message变量赋值。

```html
<input type="text" v-model="message">
等同于
<input type="text" 
	v-bind:value="message" 
	v-on:input= "message = $event.target.value">
```

#### 6.3 其他类型
**单选框**
`v-model:radio`

```html
  <div id="app">
    <label for="male">
      <input type="radio" id="male" value="男" v-model="sex">男
    </label>
    <label for="female">
      <input type="radio" id="female" value="女" v-model="sex">女
    </label>
    <h2>{{sex}}</h2>
  </div>
  <script src="../js/vue.js"></script>
  <script>
      var app = new Vue({
          el:"#app",
          data:{
              sex: '女'
          }
      })
  </script>
```
**复选框**
分为两种情况:单个勾选框和多个勾选框

```html
  <div id="app">
    <!-- checkbox 单选框 -->
    <label for="agree">
      <input type="checkbox" id="agree"  v-model="isAgree">同意协议
    </label>
    <br>
    <button :disabled="!isAgree">下一步</button>
    <br>
    
    <!-- checkbox 多选框 -->
    <label for="basketball">
      <input type="checkbox" value="篮球" id="basketball" v-model="hobbies">篮球
    </label>
    <label for="football">
      <input type="checkbox" value="足球" id="football" v-model="hobbies">足球
    </label>
    <label for="tennis">
      <input type="checkbox" value="网球" id="tennis" v-model="hobbies">网球
    </label>
    <label for="ping-pong">
      <input type="checkbox" value="乒乓球" id="ping-pong" v-model="hobbies">乒乓球
    </label>
    <h2>您的选择是：{{hobbies}}</h2>
  </div>
  <script src="../js/vue.js"></script>
  <script>
      var app = new Vue({
          el:"#app",
          data:{
            isAgree: false,// 单选框对应的是bool值
            hobbies: []// 多选框对应的是数组类型
          }
      })
  </script>
```
**select**

和checkbox一样，select也分单选和多选两种情况。
- 单选:只能选中一个值。
	* v-model绑定的是一个值。
	* 当我们选中option中的一个时，会将它对应的value赋值到fruit中
- 多选:可以选中多个值。
	* v-model绑定的是一个数组。
	当选中多个值时，就会将选中的option对应的value添加到数组fruits中
	![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/86b35f7c6f92435f8fd62e8e65c385f2.png)

```html
  <div id="app">
    <!-- select 选择一个 -->
    <select name="" id="" v-model="fruit">
      <option value="苹果" value="苹果" >苹果</option>
      <option value="香蕉" value="苹果" >香蕉</option>
      <option value="梨">梨</option>
      <option value="草莓">草莓</option>
    </select>
    <h2>您选择的是：{{fruit}}</h2>
    <!-- select 按住ctrl键，选择多个 -->
    <!-- id 不能重复，可以删掉 -->
    <select name="" v-model="fruits" multiple>
      <option value="苹果" value="苹果" >苹果</option>
      <option value="香蕉" value="苹果" >香蕉</option>
      <option value="梨">梨</option>
      <option value="草莓">草莓</option>
    </select>
    <h2>您选择的是：{{fruits}}</h2>
  </div>
  <script src="../js/vue.js"></script>
  <script>
      var app = new Vue({
          el:"#app",
          data:{
            fruit: "香蕉",
            fruits: []
          }
      })
  </script>
```

#### 6.4 值绑定
实际开发中，input属性的值时从网络获取或定义在data中的，通过`v-bind`**动态**的给value属性绑定赋值，就叫做“值绑定”。
```html
<div id="app">
	<label v-for= "item in originHobbies" :for="item">
		<input type="checkbox" :value="item" v-model="hobbies" :id="item">{{item}}
	</label>
 </div>
  <script src="../js/vue.js"></script>
  <script>
      var app = new Vue({
          el:"#app",
          data:{
            originHobbies: ["篮球","足球","网球","乒乓球"]
          }
      })
  </script>
```

#### 6.5 修饰符
- `lazy`修饰符：
	* 默认情况下,v-model默认是在input事件中同步输入框的数据的。
	* 也就是说，一旦有数据发生改变对应的data中的数据就会变动发生改变。
	* lazy修饰符可以让数据在**失去焦点**或者**回车时**才会更新
- `number`修饰符:
	* 默认情况下，在输入框中无论我们输入的是字母还是数字，都会被当做字符串类型进行处理。
	* 但是如果我们希望处理的是数字类型，那么最好直接将内容当做数字处理。
	* number修饰符可以让在输入框中输入的内容**自动转成数字类型**。
- `trim`修饰符∶
	* 如果输入的内容首尾有很多空格，通常我们希望将其去除。
	* trim修饰符可以**过滤内容左右两边的空格**。

示例代码如下：
```html
  <div id="app">
    <!-- 1.lazy修饰符：敲回车键或失去焦点时才绑定过去 -->
    <input type="text" name=""  v-model.lazy="message">
    <h2>{{message}}</h2>
    <!-- 2.num修饰符：让在输入框中输入的内容自动转成数字类型。 -->
    <!-- 将input的type属性设置为number，作用只是无法输入字母和汉字，输入的仍然是string类型 -->
    <input type="text" name="" v-model.number="num">
    <h2>输入的值：{{num}}，输入的类型：{{typeof num}}</h2>
    <!-- 3.trim修饰符：。 -->
    <!-- 浏览器会对字符串进行处理：字符串左右两边很多的空格去掉，左边和中间只会展示1个 -->
    <!-- 用console.log输出输入的值会更加准确 -->
    <input type="text" name="" v-model.trim="trim">
    <h2>输入的值{{trim}}</h2>
  </div>
  <script src="../js/vue.js"></script>
  <script>
      var app = new Vue({
          el:"#app",
          data:{
            message: 'hello',
            num: 0,
            trim:''
          }
      })
  </script>
```

# 三、组件化开发

## 1 认识组件化
### 1.1 什么是组件化
人面对复杂问题的处理方式：
任何一个人处理信息的逻辑能力都是有限的。所以，当面对一个非常复杂的问题时，我们不太可能一次性搞定一大堆的内容。
但是，我们人有一种天生的能力，就是将问题进行拆解。如果将一个复杂的问题，拆分成很多个可以处理的小问题，再将其放在整体当中，你会发现大的问题也会迎刃而解。
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/706bd90d22bb48aaa58d562044aef681.png)

组件化也是类似的思想︰
如果我们将一个页面中所有的处理逻辑全部放在一起，处理起来就会变得非常复杂，而且不利于后续的管理以及扩展。
但如果，我们将一个页面拆分成一个个小的功能块，每个功能块完成属于自己这部分独立的功能，那么之后整个页面的管理和维护就变得非常容易了。

**我们将一个完整的页面分成很多个组件。每个组件都用于实现页面的一个功能块。而每一个组件又可以进行细分。**
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/63bfe736f688462095fe5caad687e752.png)

### 1.2 Vue组件化思想
- 组件化是Vue.js中的重要思想
	* 它提供了一种抽象，让我们可以开发出一个个独立可复用的小组件来构造我们的应用。
	* 任何的应用都会被抽象成一棵组件树。
	![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/ba0eb2c8ad0b4321912b866afb60d19e.png)
- 组件化思想的应用：
	* 有了组件化的思想，我们在之后的开发中就要充分的利用它
	* 尽可能的将页面拆分成一个个小的、可复用的组件。
	* 这样让我们的代码更加方便组织和管理，并且扩展性也更强。

## 2 组件化基础
注册组件的基本步骤
组件的使用分成三个步骤:
- 创建组件构造器
- 注册组件
- 使用组件
- 我们来看看通过代码如何注册组件查看运行结果:
口和直接使用一个div看起来并没有什么区别。
口但是我们可以设想，如果很多地方都要显示这样的信息，我们是不是就可以直接使用`<my-cpn></my-cpn>`来完成呢?

![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/aab29f20c51243d1b8a159c3bdadb4c5.png)

### 2.1 注册组件
#### 2.1.1 注册的基本步骤

```html
  <div id="app">
    <!-- 3.使用组件 -->
    <my-cpn></my-cpn>
    <my-cpn></my-cpn>
    <my-cpn></my-cpn>
    <my-cpn></my-cpn>
  </div>
  <script src="../js/vue.js"></script>
  <script>
    // ES6中新加了 ``包裹字符串，可以换行
    // 1.创建组件构造器对象
    const cpnConstructor = Vue.extend({
      template: `
        <div>
          <h2>标题</h2>
          <p>内容1</p>
          <p>内容2</p>
        </div>`
    })
    // 2.注册组件
    // 参数1：组件的标签名
    // 参数2：组件构造器对象
    Vue.component('my-cpn', cpnConstructor);

    const app = new Vue({
      el:'#app',
    })
  </script>
```

注册组件步骤解析
这里的步骤都代表什么含义呢?

1.Vue.extend() :
- 调用Vue.extend()创建的是一个组件构造器。
- 通常在创建组件构造器时，传入template代表我们自定义组件的模板。
- 该模板就是在使用到组件的地方，要显示的HTML代码。
- 事实上，这种写法在Vue2.x的文档中几乎已经看不到了，它会直接使用下面我们会讲到的语法糖，但是在很多资料还是会提到这种方式，而且这种方式是学习后面方式的基础。

2.vue.component() :
- 调用Vue.component()是将刚才的组件构造器注册为一个组件，并且给它起一个组件的标签名称。
- 所以需要传递两个参数:1、注册组件的标签名2、组件构造器

3.组件必须挂载在某个Vue实例下否则它不会生效。(见下页)
- 我们来看下面我使用了三次<my-cpn> </my-cpn>
- 而第三次其实并没有生效:
![在这里插入图片描述](https://img-blog.csdnimg.cn/2c13342f269f4919adf4764319664050.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMzMzkwNzAw,size_16,color_FFFFFF,t_70)

#### 2.1.2 全局和局部组件
全局组件：在Vue的实例之外将构造器注册为组件。
可以在多个Vue的实例下面使用

局部组件：在Vue的实例中，使用templates选项将构造器注册为组件。
只可以在注册为组件的实例下面使用。

```html
  <div id="app">
    <!-- 3.使用组件 -->
    <cpn></cpn>
    <cpn></cpn>
    <cpn></cpn>
    <cpn></cpn>
  </div>
  <script src="../js/vue.js"></script>
  <script>
    // ES6中新加了 ``包裹字符串，可以换行
    // 1.创建组件构造器对象
    const cpnConstructor = Vue.extend({
      template: `
        <div>
          <h2>标题</h2>
          <p>内容1</p>
          <p>内容2</p>
        </div>`
    })

    const app = new Vue({
      el:'#app',
      components: {
        // 2.注册组件
        // cpn:使用组件时的标签名；cpnConstructor：组件构造器对象
        cpn: cpnConstructor
      }
    })
  </script>
```
在实际开发中，用的最多的是局部组件，一般只有一个Vue实例。

#### 2.1.2 父组件和子组件
在前面我们看到了组件树：组件和组件之间存在层级关系，而其中一种非常重要的关系就是父子组件的关系。

我们来看通过代码如何组成的这种层级关系：

```html
 <div id="app">
    <!-- 3.使用组件 -->
    <cpn2></cpn2>
    <!-- 不能以子标签的形式在Vue实例中使用，会报错 -->
    <!-- <cpn1></cpn1> -->
  </div>
  <script src="../js/vue.js"></script>
  <script>
    // 1.创建cpnC1构造器--子组件构造器
    const cpnC1 = Vue.extend({
      template: `
        <div>
          <h2>标题</h2>
          <p>内容1</p>
        </div>`
    })
    // 2.创建cpnC2构造器--父组件构造器
    const cpnC2 = Vue.extend({
    template: `
      <div>
        <h2>标题</h2>
        <p>内容2</p>
        <cpn1></cpn1>
      </div>
      `,
    // 在父组件构造器中，注册子组件
    components: {
      cpn1: cpnC1
    }

    })
    const app = new Vue({
      el:'#app',
      // 在Vue实例app中注册父组件
      components: {
        // cpn:使用组件时的标签名；cpnConstructor：组件构造器对象
        cpn2: cpnC2
      }
    })
  </script>
```

父子组件错误用法:**以子标签的形式在Vue实例中使用**
因为当子组件注册到父组件的components时,Vue会编译好父组件的模块
该模板的内容已经决定了父组件将要渲染的HTML(相当于父组件中已经有了子组件中的内容了)
`<child-cpn></child-cpn>`是只能在父组件中被识别的。
类似这种用法（以子标签的形式在Vue实例中使用），`<child-cpn></child-cpn>`是会被浏览器忽略的。

#### 2.1.2 注册组件语法糖
Vue提供注册的语法糖，简化过程。
主要是**省去了调用Vue.extend()的步骤**，而是直接使用一个对象来代替。（内部传给了extend方法）
 1. 全局组件注册的语法糖
```html
  <div id="app">
    <!-- 使用组件 -->
    <cpn></cpn>
  </div>
  <script src="../js/vue.js"></script>
  <script>
    // 1.全局组件注册的语法糖
    Vue.component('cpn',{
      template: `
        <div>
          <h2>标题</h2>
          <p>内容1</p>
        </div>`
    });

    const app = new Vue({
      el:'#app'
    })
  </script>
```
2. 注册局部组件的语法糖
```html
 <div id="app">
    <!-- 使用组件 -->
    <cpn2></cpn2>
  </div>
  <script src="../js/vue.js"></script>
  <script>
    const app = new Vue({
      el:'#app',
      // 注册局部组件的语法糖
      components: {
        cpn2: {
          template: `
	        <div>
	          <h2>标题</h2>
	          <p>内容2</p>
	        </div>`
        }
      }
    })
  </script>
```

#### 2.1.2 模板的分离写法
在JS代码里，template模板写法中，有很多HTML模板，看起来很乱。
使用分离写法，将模板分离出来写，挂载到对应的组件上，结构会更加清晰。
Vue 提供了两种方案定义HTML模板内容：
1. 使用`<script>`标签

```html
 <div id="app">
    <!-- 使用组件 -->
    <cpn></cpn>
  </div>
  <!-- 1.使用script标签定义模板内容 -->
  <!-- type 设置为"text/x-template"-->
  <!-- id 设置为标签名-->
  <script type="text/x-template" id="myCpn">
    <div>
      <h2>标题</h2>
      <p>内容2</p>
    </div>
  </script>
  
  <script src="../js/vue.js"></script>
  
  <script>
    // cpn是标签名
    Vue.component('cpn',{
      // 因为是id，所以用id选择器，id名前加上“#“
      template: '#myCpn'
    });
    const app = new Vue({
      el:'#app'
    })
</script>
```
局部组件的模板分离写法：
```html
 <div id="app">
    <!-- 使用组件 -->
    <cpn></cpn>
  </div>
  <!-- 1.使用script标签定义模板内容 -->
  <!-- type 设置为"text/x-template"-->
  <!-- id 设置为标签名-->
  <script type="text/x-template" id="myCpn">
    <div>
      <h2>标题</h2>
      <p>内容2</p>
    </div>
  </script>
  
  <script src="../js/vue.js"></script>
  
  <script>
    const app = new Vue({
      el:'#app',
      // 注册局部组件的语法糖
      components: {
        cpn: {
          template: myCpn
        }
      }
    })
  </script>
```
2. 使用`<template>`标签

```html
  <div id="app">
    <!-- 使用组件 -->
    <cpn></cpn>
    
  </div>
  <!-- 2.使用template标签 -->
  <template id="myCpn">
    <div>
      <h2>标题</h2>
      <p>内容2</p>
    </div>
  </template>
  
  <script src="../js/vue.js"></script>
  
  <script>
    // 1.全局组件注册的语法糖
    Vue.component('cpn',{
      template: '#myCpn'
    });

    const app = new Vue({
      el:'#app'
    })
  </script>
```



#### 2.1.2 组件的其他属性
data属性

组件是一个单独功能模块的封装，有属于自己的HTML模板，也应该有属于自己的数据data。
组件中**不能**访问Vue实例中的data，通过组件自己的data选项，保存数据。

组件数据的存放
组件对象也有一个data属性(也可以有methods等属性，下面我们有用到)
只是这个data属性必须是一个函数
而且这个函数返回一个对象，对象内部保存着数据

```html
  <script>
    // 1.全局组件注册的语法糖
    Vue.component('cpn',{
      template: '#myCpn',
      data() {
      	return {
      		title: 'hello'
      	}
      }
    });

    const app = new Vue({
      el:'#app'
    })
  </script>
```
为什么组件data必须是函数


### 2.2 数据传递
- 子组件是**不能**引用父组件或者Vue实例的数据的。
- 但是，在开发中，往往一些数据确实需要从上层传递到下层︰
	- 比如在一个页面中，我们从服务器请求到了很多的数据。
	- 其中一部分数据，并非是我们整个页面的大组件来展示的，而是需要下面的子组件进行展示。
	- 这个时候，并不会让子组件再次发送一个网络请求，而是直接让大组件(父组伟)将数据传递给小组件(子组件)。

- 如何进行父子组件间的通信呢?Vue官方提到
	- 通过props向子组件传递数据
	- 通过事件向父组件发送消息
	Patent(父组件)
	Child([水组件)
	-----$emit Events------
	在下面的代码中，我直接将Vue实例当做父组件，并且其中包含子组件来简化代码。
	真实的开发中，**Vue实例和子组件的通信**和**父组件和子组件的通信**过程是一样的。

父子组件的访问方式：$children

- 有时候我们需要父组件直接访问子组件,子组件直接访问父组件，或者是子组件访问跟组件。
	- 父组件访问子组件:使用`$children`或$`refs`
	- 子组件访问父组件:使用`$parent`
- 我们先来看下`$children`的访问
	- `this.$children`是一个数组类型，它包含所有子组件对象。
	- 我们这里通过一个遍历，取出所有子组件的`message`状态。

```html
  <div id="app">
    <cpn></cpn>
    <cpn></cpn>
    <cpn></cpn>
    <button @click="btnClick">按钮</button>
  </div>

  <template id="cpn">
    <div>我是子组件</div>
  </template> 

  <script src="../js/vue.js"></script>
  <script>
    const app = new Vue({
      el:'#app',
      data: {
        message: 'hello'
      },
      methods: {
        btnClick() {
           console.log(this.$children);
           for (let item of this.$children) {
             console.log(item.name);
             item.showMessage();
           }
        }
      },
      components: {
        cpn: {
          template: '#cpn',
          data() {
            return {
              name: '我是子组件的name'
            }
          },
          methods: {
            showMessage() {
              console.log('showMessage');
            }
          }
        }
      }
    })
  </script>
```

$children需要通过下标值去拿子组件，在实际开发中下标值会变化，用的非常少（比如拿到所有的子组件）。

父子组件的访问方式：$refs
```html
  <div id="app">
    <cpn></cpn>
    <cpn></cpn>
    // 在该子组件上加上ref属性
    <cpn ref="aaa"></cpn>
    <button @click="btnClick">按钮</button>
  </div>

  <template id="cpn">
    <div>我是子组件</div>
  </template> 

  <script src="../js/vue.js"></script>
  <script>
    const app = new Vue({
      el:'#app',
      data: {
        message: 'hello'
      },
      methods: {
        btnClick() {
          // $refs 默认是空白的
          // 在某个组件上加一个ref属性，可以通过this.$refs.aaa（属性值）拿到该组件
          console.log(this.$refs.aaa);
        }
      },
      components: {
        cpn: {
          template: '#cpn',
          data() {
            return {
              name: '我是子组件的name'
            }
          },
          methods: {
            showMessage() {
              console.log('showMessage');
            }
          }
        }
      }
    })
  </script>
```
子访问父：`$parent`和`$root`

```html
 <div id="app">
    <cpn></cpn>
  </div>

  <template id="cpn">
    <div>
      <ccpn></ccpn>
    </div>
  </template>

  <template id="ccpn">
    <div>
      <h2>我是子组件</h2>
      <button @click="btnClick">按钮</button>
    </div>
  </template>

  <script src="../js/vue.js"></script>
  <script>
    const app = new Vue({
      el:'#app',
      data: {
        name: '我是根组件的name'
      },
      components: {
        cpn: {
          template: '#cpn',
          data() {
            return {
              name: '我是父组件的name'
            }
          },
          components: {
            ccpn: {
              template: '#ccpn',
              methods: {
                btnClick() {
                  // 1.访问父组件 $parent
                  console.log(this.$parent);
                  console.log(this.$parent.name);

                  // 2.访问根组件 $root
                  console.log(this.$root);
                  console.log(this.$root.name);
                }
          }
            }
          }
        }
      }
    })
  </script>
```

## 3.组件化高级
### 3.1 插槽slot



#### 3.1.1 为什么使用slot

- slot（发音为[slɒt]）翻译为插槽:
	- 在生活中很多地方都有插槽，电脑的USB插槽，插板当中的电源插槽。
	- 插槽的目的是让我们原来的设备具备更多的扩展性。
	- 比如电脑的USB我们可以插入U盘、硬盘、手机、音响、键盘、鼠标等等。
- 组件的插槽:
	- 组件的插槽也是为了让我们封装的组件更加具有扩展性。
	- 让使用者可以决定组件内部的一些内容到底展示什么。
- 例子︰移动网站中的导航栏。
	- 移动开发中，几乎每个页面都有导航栏。
	- 导航栏我们必然会封装成一个插件，比如nav-bar组件。
	- 一旦有了这个组件，我们就可以在多个页面中复用了。

- 但是，每个页面的导航是一样的吗?No，我以京东M站为例
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/1d29dc7cd5f5423991c5ccccb0398eee.png)
- 如何去封装这类的组件呢?
	- 它们也很多区别，但是也有很多共性。
	- 如果，我们每一个单独去封装一个组件，显然不合适︰比如每个页面都返回，这部分内容我们就要重复去封装。
	- 但是，如果我们封装成一个，好像也不合理︰有些左侧是菜单，有些是返回，有些中间是搜索，有些是文字，等等。
- 如何封装合适呢?抽取共性，保留不同。
	- 最好的封装方式就是将共性抽取到组件中，将不同暴露为插槽。
	- 一旦我们预留了插槽，就可以让使用者根据自己的需求，决定插槽中插入什么内容。
	- 是搜索框，还是文字，还是菜单。由调用者自己来决定。

这就是为什么我们要学习组件中的插槽slot的原因。

#### 3.1.2 slot的基本使用
1. 插槽的基本使用：在组件里定义一个`<slot></slot>`，在使用该组件时，在中间插入要替换的元素。
2. 插槽的默认值：`<slot><button>按钮</button></slot>`。如果在该组件中没有插入任何其他内容，就默认显示默认值。
3. 如果有多个值，同时放入到组件进行替换时,一起作为替换元素。

```html
  <div id="app">
    <cpn><button>按钮</button></cpn>
    <cpn><span>span</span></cpn>
    <cpn>
      <!-- 3.如果有多个值，同时放入到组件进行替换时,一起作为替换元素。 -->
      <i>i</i>
      <div>div</div>
      <p>p</p>
  </cpn>
    <cpn></cpn>
    <cpn></cpn>
    <cpn></cpn>
  </div>
  <template id="cpn">
    <div>
      <h2>我是组件h2</h2>
      <p>我是组件p</p>
      <!-- 1.插槽的基本使用：在组件里定义一个`<slot></slot>` -->
      <!-- 2.插槽的默认值：`<slot><button>按钮</button></slot>` -->
      <slot><button>按钮</button></slot>
    </div>
  </template>
  <script src="../js/vue.js"></script>
  <script>
    const app = new Vue({
      el: '#app',
      components: {
        cpn: {
          template: '#cpn'
        }
      }
    })
  </script>
```

#### 3.1.3 slot的具名插槽
- 当子组件的功能复杂时，子组件的插槽可能并非是一个。
	- 比如我们封装一个导航栏的子组件，可能就需要三个插槽，分别代表左边、中间、右边。
	- 那么，外面在给插槽插入内容时，如何区分插入的是哪一个呢?
	- 这个时候，我们就需要给插槽起一个名字
- 如何使用具名插槽呢?
	- 非常简单，只要给slot元素一个`name`属性即可
	- `<slot name='myslot'></slot>`

示例代码如下：
```html
  <div id="app">
    <cpn>
      <!-- 只会替换没有名字的slot -->
      <span>标题</span>
      <!-- 只会替换名字为left的slot -->
      <button slot="left">按钮</button>
      <span slot="center">替换</span>
      <p slot="right">p</p>
    </cpn>
  </div>

  <template id="cpn">
    <div>
      <slot name="left"><span>左边</span></slot>
      <slot name="center"><span>中间</span></slot>
      <slot name="right"><span>右边</span></slot>
    </div>
  </template>
  <script src="../js/vue.js"></script>
  <script>
    const app = new Vue({
      el: '#app',
      components: {
        cpn: {
          template: '#cpn'
        }
      }
    })
  </script>
```

#### 3.1.4 slot作用域插槽
##### 3.1.4.1 编译作用域

- 官方对于编译的作用域解析比较简单，我们自己来通过一个例子来理解这个概念:
- 我们来考虑下面的代码是否最终是可以渲染出来的:
  - `<my-cpn v-show="isShow"></my-cpn>`中，我们使用了isShow属性。
  - isShow属性包含在组件中，也包含在Vue实例中。
- 答案︰最终可以渲染出来，也就是使用的是vue实例的属性。
- 为什么呢?
  - 官方给出了一条准则∶**父组件模板的所有东西都会在父级作用域内编译;子组件模板的所有东西都会在子级作用域内编译。**
  - 而我们在使用<my-cpn v-show="isShow"></my-cpn>的时候，整个组件的使用过程是相当于在父组件中出现的。
  - 那么他的作用域就是父组件，使用的属性也是属于父组件的属性。
  - 因此，isShow使用的是Vue实例中的属性，而不是子组件的属性。

![image-20210916182952283](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210916182952283.png)



```html
  <div id="app">
    <!-- isShow使用的是实例中的属性，而不是子组件的属性-->
    <!-- 查找变量时，看是在哪个模板里（Vue实例的模板） -->
    <!-- 可以当做普通的div来看 -->
    <cpn v-show="isShow"></cpn>
  </div>

  <template id="cpn">
    <!-- 给div设置 v-show="isShow" ，仍然是显示的，不知道为什么 -->
    <div>
      <!-- 会使用子组件里的isShow -->
      <h2 v-show="isShow">我是子组件</h2>
      <p>我是内容</p>
    </div>
  </template>
  <script src="../js/vue.js"></script>
  <script>
    const app = new Vue({
      el: '#app',
      data: {
        message: 'hello',
        isShow: true
      },
      components: {
        cpn: {
          template: '#cpn',
          data() {
            return {
              isShow: false
            }
          }
        }
      }
    })
  </script>
```


##### 3.1.4.2 作用域插槽
- 作用域插槽：父组件替换插槽的标签，但是内容由子组件来提供。

- 我们先提一个需求∶
	- 子组件中包括一组数据，比如: `pLanguages: ['JavaScript' , 'Python', 'Swift' , 'Go','C++']`
	- 需要在多个界面进行展示︰
		- 某些界面是以水平方向——展示的，
		- 某些界面是以列表形式展示的，
		- 某些界面直接展示一个数组
	- 内容在子组件，希望父组件告诉我们如何展示，怎么办呢?
		- 利用slot作用域插槽就可以了
	
	==P72==
	
	

### 3.2 动态组件
### 3.3 异步组件
## 4 组件声明周期

# 模块化开发

## 1.JavaScript原始功能

在网页开发的早期，js制作为一种脚本语言，做一些简单的表单验证或动画实现等，那个时候代码还是很少的。
那个时候的代码是怎么写的呢?直接将代码写在\<script>标签中即可

随着ajax异步请求的出现，慢慢形成了前后端的分离
客户端需要完成的事情越来越多，代码量也是与日俱增。
为了应对代码量的剧增，我们通常会将代码组织在多个js文件中，进行维护。

但是这种维护方式，依然不能避免一些灾难性的问题。
比如全局变量同名问题:
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/3a41a20620264dd9bc40f7b47ef43f0a.png)


另外，这种代码的编写方式对js文件的依赖顺序几乎是强制性的
口但是当js交件过多，比如有几十个的时候，弄清楚它们的顺序是一件比较痛苦的事情。
口而且即使你弄清楚顺序了，也不能避免上面出现的这种尴尬问题的发生。


## 2.匿名函数的解决方案

我们可以使用匿名函数来解决方面的重名问题
在aaa.js文件中，我们使用匿名函数

```html
(function() {
var f1ag = true
})()
```

但是如果我们希望在main.js文件中，用到flag，应该如何处理呢?
显然，另外一个文件中不容易使用，因为flag是一个局部变量。

## 3.使用模块作为出口

我们可以使用将需要暴露到外面的变量，使用一个模块作为出口，什么意思呢?
来看下对应的代码:
我们做了什么事情呢?
非常简单，在匿名函数内部，定义一个对象。
给对象添加各种需要暴露到外面的属性和方法(不需要暴露的直接定义即可)。
最后将这个对象返回，并且在外面使用了一个MoudleA接受。

```javascript
var ModuleA =(function() {
	// 1.定义一个对象
	var obj = {}
	// 2.在对象内部添加变量和方法
	obj.flag = true
	obj.myFunc = function (info) {
	console.1og(info);
	)
	// 3.将对象返回
	return obj
})()
```

接下来，我们在man.js中怎么使用呢?
口我们只需要使用属于自己模块的属性和方法即可
这就是模块最基础的封装，事实上模块的封装还有很多高级的话题:
口但是我们这里就是要认识一下为什么需要模块，以及模块的原始雏形。
口幸运的是，前端模块化开发已经有了很多既有的规范，以及对应的实现方案。

```javascript
if (ModuleA.flag) {
	console.log( '小明是个天才');
}
ModuleA.myFunc("小明长得真帅")
conso1e.log(ModuleA);
```

常见的模块化规范:
CommonJS、AMD、CMD，也有ES6的Modules

## 4.CommonJS ( 了解)

模块化有两个核心∶导出和导入
CommonJS的导出∶

```javascript
module. exports = {
	flag: true,
	test(a, b){
		return a + b
	}
	demo(a, b){
		return a * b
	}
}
```

CommonJS的导入

```javascript
// Commons模块
let (test, demo, flag } = require('modu1eA');
// 等同于
let _mA = require('moduleA');
let test =_mA.test;
let demo =_mA.demo;
let flag =_mA.f1ag;
```

## 5.ES6的Modules

### 5.1 export使用

#### 5.1.1 export指令用于导出变量

定义一个变量的同时，直接导出

```javascript
// info.js
export let name = 'why'
export let age = 18
export let height = 1.88
```

上面的代码还有另外一种写法︰
先定义好变量，再填入一个对象导出

```javascript
// info.js
let name = "why'
let age = 18
let height = 1.88
export {name, age, height)
```

**导出函数或类**
上面我们主要是输出变量，也可以输出函数或者输出类
口上面的代码也可以写成这种形式︰

```javascript
export function test(content) {
	console.log(content);
}
export class Person {
	constructor(name, age) {
	this.name = name ;
	this.age = age;
	}
	run() {
		console.log(this.name + '在奔跑');
	}
}
```

```javascript
function test(content) {
	console.log(content);
class Person {
	constructor(name, age) {
		this.name = name ;
		this.age = age ;
	}
	run() {
		console.log(this.name + '在奔跑');
	}
}
export {test, Person}

```

**export default**
某些情况下，一个模块中包含某个的功能，我们并不希望给这个功能命名，而且让导入者可以自己来命名
口这个时候就可以使用export default
导出变量

```javascript
//  info.js
const address = '北京市'
export default address
```

```javascript
import addr from './info.js '
console.log(addr)
```

导出函数

```javascript
//  info.js
export default function () {
	console.log('default function');
}
```

我们来到main.js中，这样使用就可以了
口这里的myFunc是我自己命名的，你可以根据需要命名它对应的名字

```javascript
import myFunc from './info.js '
myFunc()
```

另外，需要注意:
`export default` 在同一个模块中，不允许同时存在多个。

### 5.2 import使用

我们使用export指令导出了模块对外提供的接口，下面我们就可以通过import命令来加载对应的这个模块了
首先，我们需要在HTML代码中引入两个js文件，并且类型需要设置为`module`。

```html
<script src="info.js" type="module"></script>
<script src="main.js " type="module"></script>
```

`import`指令用于导入模块中的内容，比如main.js的代码

```html
import {name，age，heighg} from "./info.js"
console.log(name，age，height);
```

如果我们希望某个模块中所有的信息都导入，一个个导入显然有些麻烦︰

- 通过`*` 可以导入模块中所有的export变量
- 但是通常情况下我们需要给`*`起一个别名，方便后续的使用

```javascript
import * as info from './info.js "
console.log(info.name, info.age, info.height,  info.friends) ;

```



# 四、Vue CLI详解

## 1.webpack

### 1.1 认识Webpack
#### 1.1 什么是webpack
官方解释：
At its core, webpack is a static module bundlerfor modern JavaScript applications.
从本质上来讲，webpack是一个现代的JavaScript应用的静态**模块打包**工具。

**前端模块化：**
- 在前面学习中，我已经用了大量的篇幅解释了为什么前端需要模块化。
- 目前使用前端模块化的一些方案：AMD、CMD、CommonJS、ES6。
- 在ES6之前，我们要想进行模块化开发，就必须借助于其他的工具，让我们可以进行模块化开发。
- 并且在通过模块化开发完成了项目后，还需要处理模块间的各种依赖，并且将其进行整合打包。
- 不仅仅是JavaScript文件，我们的CSS、图片、json文件等等在webpack中都可以被当做模块来使用(在后续我们会看到)。

**打包：**
- 理解了webpack可以帮助我们进行模块化，并且处理模块间的各种复杂关系后，打包的概念就非常好理解了。
- 就是将webpack中的各种资源模块进行打包合并成一个或多个包(Bundle)。
- 并且在打包的过程中，还可以对资源进行处理，比如压缩图片，将scss转成css，将ES6语法转成ES5语法，将TypeScript转成JavaScript等等操作。

### 1.2  Webpack和grunt/gulp的对比
- grunt/gulp的核心是Task
	- 我们可以配置一系列的task，并且定义task要处理的事务（例如ES6、ts转化，图片压缩，scss转成css )
	- 之后让grunt/gulp来依次执行这些task ,而且让整个流程**自动化**。
	- 所以grunt/gulp也被称为前端自动化任务管理工具。
- 我们来看一个gulp的task
	- 下面的task就是将src下面的所有js文件转成ES5的语法。
	- 并且最终输出到dist文件夹中。

	```javascript
	const gulp = require('gu1p');
	const babe1 = require('gu1p-babe1');
	gulp.task( 'js ', () =>
		gulp.src('src/* .js ')
			.pipe(babel({
				presets: ['es2015'])
			}))
			.pipe(gulp.dest('dist'))
	);
	
	```
- 什么时候用grunt/gulp呢?
	- 如果你的工程模块依赖非常简单，甚至是没有用到模块化的概念。
	- 只需要进行简单的合并、压缩，就使用grunt/gulp即可。
	- 但是如果整个项目使用了模块化管理，而且相互依赖非常强，我们就可以使用更加强大的webpack了。
- 所以，grunt/gulp和webpack有什么不同呢?
	- grunt/gulp更加强调的是前端流程的自动化，模块化不是它的核心。
	- webpack更加强调模块化开发管理，而文件压缩合并、预处理等功能，是他附带的功能。

### 1.3 webpack依赖环境--node
webpack为了可以正常运行,必须依赖node环境。
==怎么安装node来着==
查看自己的node版本：`node -v` 

node环境为了可以正常的执行很多代码,必须其中包含各种依赖的包。
安装node的时候，会自动安装软件包管理工具npm（node packages manager）
### 2 webpack安装
1. 全局安装webpack
(这里先指定版本号3.6.0，因为vue cli2依赖该版本，而vue cli3 的配置被隐藏了，不好看）
`npm install webpack@3.6.0 -g` （-g 代表全局 -- global）

2. 局部安装webpack(后续才需要)
	`--save-dev`是开发时依赖，项目打包后不需要继续使用的。
	```bash
	cd对应目录
	npm install webpack@3.6.0 --save-dev
	```

☆ 为什么全局安装后，还需要局部安装呢?
- 在终端直接执行webpack命令，使用的全局安装的webpack
- 当在package.json中定义的scripts中，包含了webpack命令时，使用的是局部webpack

### 3 webpack的基本使用
### 3.1 准备工作：创建文件和文件夹
- 创建文件和文件夹:
	- dist文件夹：用于存放之后打包的文件
	- src文件夹：用于存放我们写的源文件
		-  main.js：项目的入口文件。具体内容查看下面详情
		- mathUtils.js：定义了一些数学工具函数，可以在其他地方引用，并且使用。具体内容查看下面的详情。
		- info.js：根据ES6规范，定义了一些变量，可以在其他地方引用，并且使用。
	- index.html：浏览器打开展示的首页html
	- package.json：通过npm init生成的，npm包管理的文件(暂时没有用上，后面才会用上)
	![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/c04f4c346a904744b4ba70f1027563d7.png)
	**使用模块化的方式进行开发js文件：**
	mathutils.js文件中的代码︰

```javascript
function add(num1, num2) {
  return num1 + num2;
}
function mul(num1, num2) {
  return num1 * num2;
}

// 1.使用commenjs的模块化规范导出
module.exports = {
  add,
  mul
}

```
- info.js文件中的代码︰

```javascript
// 2.使用ES6的模块化规范导出
export const name = 'why';
export const age = 18;
}

```

- main.js文件中的代码︰

```javascript
// 1.使用commenjs的模块化规范导入
const {add, mul} = require('./mathUtils.js')
console.log(add(1, 2));
console.log(mul(1, 2));

// 2.使用ES6的模块化规范导入
import { name, age } from './info.js';
console.log(name, age);
```

### 2.2  js文件的打包
- 使用模块化的方式开发的 js文件，它们不可以直接使用。
	- 因为如果直接在index.html引入这两个js文件，浏览器并不识别其中的模块化代码。
	- 另外，在真实项目中当有许多这样的js文件时，我们一个个引用非常麻烦，并且后期非常不方便对它们进行管理。

- 可以使用webpack工具，对多个js文件进行打包。
	- webpack就是一个模块化的打包工具，支持我们代码中写模块化，可以对模块化的代码进行处理。==(如何处理的，待会儿在原理中，我会讲解)==
	- 在处理完所有模块之间的关系后，将多个js打包到一个js文件中，引入时就变得非常方便了。
- 如何打包呢?
	- 使用`cd命令`进入dist和src文件夹所在的目录，使用webpack的指令即可:`webpack 。./src/main.js ./dist/bundle.js`
	- 其中，`./src/main`代表入口文件，`./dist/bundle.js`设置了出口路径和生成的js文件名称。
- 打包成功 的截图如下：![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/df801cc8f4504ba186ec18b6884cf681.png)
### 2.3 使用打包后的文件
webpack处理项目直接文件依赖，在dist文件下生成bundle.js文件。
将打包生成的的bundle.js文件在index.html中引入即可。
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/48d1145b073e4d30b24ea4c540e52ce0.png)

### 4 webpack的配置
#### 4.1 webpack.config.js配置
每次使用`webpack`的命令都需要写上**入口文件**和**出口**作为参数，就非常麻烦。
解决方法：将这两个参数写到配置文件`webpack.config.js`（名字固定）中，在运行时，直接读取。


1. 手动创建`webpack.config.js`文件

	```javascript
	// 依赖node包，需要使用npm init建package.json文件帮忙管理node包
	const path = require('path');
	module.exports = {
	  // 入口:可以是字符串/数组/对象，这里我们入口只有一个,所以写一个字符串即可
	  entry: './src/main.js',
	  //出口:通常是一个对象，里面至少包含两个重要属性：path和 filename
	  output: {
	    // 注意：path的值要求绝对路径
	    // 为了动态的获取路径需要用到path包
	    // path.resolve()方法拼接路径
	    // __dirname是node自带的全局变量
	    path: path.resolve(__dirname,'dist'),
	    filename: 'bundle.js'
	  }
	}
	```
2. 终端使用`cd`命令，进入dist和src文件夹所在的目录中，输入`webpack`，点击回车即可。
### 4.2 package.json配置
（package.json文件使用 `npm init`命令创建，注意name不能有中文。）
**使用局部webpack**
因为一个项目往往依赖特定的webpack版本，全局的版本可能和这个项目的webpack版本不一致，导出打包出现问题。 所以通常一个项目，都有自己局部的webpack。
目前，我们使用的webpack是全局的webpack（只要是在终端运行命令的，用的都是全局的），如何使用局部来打包：
- 第一步，项目中需要安装自己局部的webpack
	- 这里我们局部安装webpack3.6.0
	（注意：webpack 是开发时依赖--只是开发时打包需要，项目打包后不需要继续使用，添加webpack时需要 添加上‘--save-dev’
	本地安装webpack后，会新增node_modules文件夹，里面都是默认安装的包。）
	（Vue CLI3中已经升级到webpack4，但是它将配置文件隐藏了起来，所以查看起来不是很方便。）
	命令如下：
```bash
	cd对应目录
	npm install webpack@3.6.0 --save-dev
```
- 第二步，通过node_modules/.bin/webpack启动webpack打包
![在这里插入图片描述](https://img-blog.csdnimg.cn/a52b37566d6542f3bfd2f0c2f2366b78.png)

**package.json中定义启动**
每次执行都敲这么一长串不方便，我们可以在package.json的scripts中定义自己的执行脚本。
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/d42a7b9a4b9c4332ad61a69161e7b657.png)

执行我们的build指令
`npm run build`

**定义脚本，添加`npm run build`指令到`webpack`的映射后，使用该命令，会优先使用本地的webpack版本，而不是全局的webpack版本。**

package.json中的scripts的脚本在执行时，会按照一定的顺序寻找命令对应的位置。
- 首先，会寻找本地的node_modules/.bin路径中对应的命令。
- 如果没有找到，会去全局的环境变量中寻找。

### 5  loader的使用

### 5.1 什么是loader
- webpack本身可以处理我们写的js代码，自动处理js之间相关的依赖。
- **给webpack扩展对应的loader**，就可以在开发中**加载css、图片，也包括一些高级的将ES6转成ES5代码，将TypeScript转成ES5代码，将scss、less转成css，将.jsx、.vue文件转成js文件等等这些转化**。

### 5.2 loader的使用
步骤：
- 通过npm安装需要使用的loader
- 在webpack.config.js中的module关键字下进行配置

大部分loader我们都可以在[webpack的官网](https://webpack.docschina.org/loaders/)找到，并且学习对应的用法。
![在这里插入图片描述](https://img-blog.csdnimg.cn/c2c8f7d25b17493188a93a3e41707566.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_20,color_FFFFFF,t_70,g_se,x_16)

### 5.3 CSS文件处理- 准备工作
项目开发过程中，我们必然需要添加很多的样式，而样式我们往往写到一个单独的文件中。
- 在src目录中，创建—个css文件，其中创建一个normal.css文件。
- 我们也可以重新组织文件的目录结构,将零散的js文件放在一个js文件夹中。

normal.css中的代码非常简单，就是将body设置为red。但是，这个时候normal.css中的样式会生效吗?
口当然不会，因为我们压根就没有引用它。
webpack也不可能找到它，因为我们只有一个入口，webpack会从入口开始查找其他依赖的文件。
在入口文件中引用∶
![在这里插入图片描述](https://img-blog.csdnimg.cn/58a4fd7810024658afd39377bb540f6e.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_12,color_FFFFFF,t_70,g_se,x_16)

![在这里插入图片描述](https://img-blog.csdnimg.cn/b4607b65d79e4c688e8054c17ca08c62.png)

安装loader：
`npm install --save-dev css-loader`
`npm install --save-dev style-loader`
配置loader：
![在这里插入图片描述](https://img-blog.csdnimg.cn/a2ddc1a46f7e4dde8e68c8a869aa667e.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_14,color_FFFFFF,t_70,g_se,x_16)
其中：text选项中是正则表达式，意为：以.css结尾的文件。

注：具体的loader如何使用，可以参照：https://webpack.docschina.org/loaders/
### 6 webpack配置Vue
### 6.1 引入vue.js
在我们的webpack环境中集成Vue.js的步骤：
1. 安装vue包
注:因为我们后续是在实际项目中也会使用vue的，所以并不是开发时依赖，用`--save`。
`npm install vue --save`

2. 导入vue包

	```javascript
	// 没有写路径时，会先去node_modules文件夹里找
	// 源码中导出是用的：export default Vue
	import Vue from 'vue'
	```

	那么,接下来就可以按照我们之前学习的方式来使用Vue了
	![在这里插入图片描述](https://img-blog.csdnimg.cn/767eeb8c72de4a78b72c79e9d2137c85.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMzMzkwNzAw,size_16,color_FFFFFF,t_70)

3. 修改vue的版本
修改webpack的配置（webpack.config.js文件），添加如下内容即可
```javascript
  resolve: {
    alias: {
      // 指向具体的文件，会先去找该文件，是有包括compiler的
      // 不设置的话，默认是指向vue.runtime.js的
      'vue$': 'vue/dist/vue.esm.js'
    }
  }
```
	关于第3步的必要性解释：
	
	只做第1、 2步，不修改vue的版本的话，vue版本默认是指向vue.runtime.js的。
	重新打包后，运行程序：
	打包过程没有任何错误。(因为只是多打包了一个vue的js文件而已)
	但是运行程序，没有出现想要的效果，而且浏览器中有报错
	![在这里插入图片描述](https://img-blog.csdnimg.cn/8e8439f5c52b44978f8b63fb7bff2cc3.png)
	这个错误说的是我们使用的是runtime-only版本的Vue。
	
	runtime-only和runtime-compiler的区别：
	1.runtime-only ->代码中,不可以有任何的template（包括Vue实例）
	2.runtime-compiler ->代码中,可以有template,因为有compiler可以用于编译template

### 6.2 el 和template区别（一）
正常运行之后，我们来考虑另外一个问题：
- 如果我们希望将data中的数据显示在界面中，就必须是修改index.html
- 如果我们后面自定义了组件，也必须修改index.html来使用组件
- 但是**html模板在之后的开发中，并不希望手动的来频繁修改**，是否可以做到呢?

定义template属性：
- 在前面的Vue实例中，我们定义了el属性，用于和index.html中的#app进行绑定，让Vue实例之后可以管理它其中的内容
- 这里，我们可以将div元素中的{{message}}内容删掉，只保留一个基本的id为app的元素
- 但是如果我依然希望在其中显示{{message}}的内容，应该怎么处理呢?
- 我们可以再定义一个`template属性`，代码如下:

```javascript
new vue({
	el: '#app',
	template: '<div id="app">{{message}}</div>' ,
	data: {
		message: 'coderwhy'
	}
})
```
同时有el和template属性的情况下，template的值会将el挂载到的dom替换掉。
好处是：不需要修改html代码。


### 6.3 el 和template区别（二）
.Vue文件封装处理
但是—个组件以一个js对象的形式进行组织和使用的时候是非常不方便的
一方面编写template模块非常的麻烦
另外一方面如果有样式的话，我们写在哪里比较合适呢?现在，我们以一种全新的方式来组织一个vue的组件
但是，这个时候这个文件可以被正确的加载吗?
必然不可以，这种特殊的文件以及特殊的格式,必须有人帮助我们处理。
谁来处理呢? vue-loader以及vue-template-compiler。
安装vue-loader和vue-template-compiler
`npm install vue-loader vue-template-compiler --save-dev`
修改webpack.config.js的配置文件:

```javascript
{
	test: /\.vue$/ ,
	use: [ 'vue-loader']
}

```
### 7 plugin的使用
### 8 搭建本地服务器
#### 8.1 本地服务器的作用
webpack提供了一个可选的本地开发服务器，这个本地服务器基于node.js搭建，内部使用express框架，可以实现我们想要的让**浏览器自动刷新显示我们修改后的结果**。
#### 8.2 本地服务器的安装
它是一个单独的模块，在webpack中使用之前需要先安装：
`npm install --save-dev webpack-dev-server@2.9.1`

	注：
	- 这个版本需要与webpack的（3.6.1）版本相对应.
	- `--dev`代表：开发时依赖，为开发时服务。
	- 没有`-g`，属于局部安装。

### 8.3 本地服务器的配置
配置webpack中的`devserver选项`，设置如下属性：
- `contentBase`：为哪一个文件夹提供本地服务，默认是根文件夹，我们这里要填写`./dist`
- `port`：端口号（默认：8080）
- `inline`：页面实时监听刷新
- `historyApiFallback`：在SPA页面中，依赖HTML5的==history模式（待补）==

webpack.config.js文件配置修改如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/0af6f767e5e647b98e1e5820f2f92db3.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_15,color_FFFFFF,t_70,g_se,x_16)
### 8.4 本地服务器的启动
不可以在终端直接运行`webpack-dev-server`，因为之前是局部安装的，而在终端直接运行的命令，运行的是全局安装的。

可以通过相对路径下的bin目录，找到它来运行。这个方法是可行的，但是视频老师没成功，待补。

![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/caa532ff6f77442787d46b7e0ef6dab8.png)
更简洁的方式：
在package.json文件中添加配置，再在终端中执行`npm run dev`，这时会优先在本地找。
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/9a6457e07515482faa5f7b6d761e3408.png)

运行成功后，点击该路径，可以打开运行的本地服务。
![在这里插入图片描述](https://img-blog.csdnimg.cn/0a188f99f5e4416b941c2db7365c421c.png)
补充：
1. 加上`--open`参数，设置启动本地服务器后，自动打开浏览器，不需要手动点击打开。
![在这里插入图片描述](https://img-blog.csdnimg.cn/03651e0697294a92bdc12c72df0bcf08.png)
2. 开发阶段，不进行丑化，否则出错后，在浏览器不好进行调试。
### 8.5 本地服务启动成功的验证
在main.js文件中删除之前添加的`document.writeln('<button>按钮')</button>)`，查看页面显示，该按钮被消除了（不需要再重新编译之类或者手动刷新）。
证明本地服务可以让浏览器自动刷新显示我们修改后的结果。


### 9 开发时和发布时依赖的配置分离
==其实，得先弄清楚，哪些是开发时的依赖配置，哪些是发布时的依赖配置。（这里还不太清楚）==
开发时和发布时的公共依赖： 
- Vue -- 因为代码里有Vue，生产环境肯定也有

开发时依赖：
- webpack -- 只是打包工具，生成生产环境的代码。
- loader和plugin -- 对源代码进行一些处理，并生成最终代码的预处理器。

发布时依赖：
- webpack的丑化插件
1. 代码分离
webpackage.config.js未分离代码：

```javascript
// 依赖node包，使用npm init建package.json文件帮忙管理node包
const path = require('path');
const webpack = require('webpack')
const HtmlWebpackPlugin = require('html-webpack-plugin')
const UglifyjsWebpackPlugin = require('Uglifyjs-webpack-plugin')

module.exports = {
  entry: './src/main.js',
  output: {
    // path的值要求绝对路径
    // 动态的获取路径需要用到path包
    // path.resolve()方法拼接路径
    // __dirname是node自带的全局变量
    path: path.resolve(__dirname,'dist'),
    filename: 'bundle.js'
  },
  module: {
    rules: [
      {
        test: /\.css$/ ,
        // 'css-loader 只负责将css文件进行加载
        // 'style-loader 负责将样式添加到DOM中
        use: ['style-loader','css-loader']
      },
      {
      test: /\.vue$/ ,
      use: ['vue-loader']
      }
    ]
  },
  resolve: {
    alias: {
      // 指向具体的文件，会先去找该文件，是有包括compiler的
      // 不设置的话，默认是指向vue.runtime.js的
      'vue$': 'vue/dist/vue.esm.js'
    }
  }
  plugins: [
    new webpack.BannerPlugin('最终解释权归XX所有'),
    new UglifyjsWebpackPlugin()
  ]
}
```
新建一个与dist、src文件夹同目录下的文件夹build，在该文件夹里新建
 - **base.config.js** -- 放公共的配置部分--开发时+发布时。

```javascript
// 依赖node包，使用npm init建package.json文件帮忙管理node包
const path = require('path');
const webpack = require('webpack')
const HtmlWebpackPlugin = require('html-webpack-plugin')


module.exports = {
  entry: './src/main.js',
  output: {
    // path的值要求绝对路径
    // 动态的获取路径需要用到path包
    // path.resolve()方法拼接路径
    // __dirname是node自带的全局变量
    path: path.resolve(__dirname,'dist'),
    filename: 'bundle.js'
  },
  module: {
    rules: [
      {
        test: /\.css$/ ,
        // 'css-loader 只负责将css文件进行加载
        // 'style-loader 负责将样式添加到DOM中
        use: ['style-loader','css-loader']
      },
      {
      test: /\.vue$/ ,
      use: ['vue-loader']
      }
    ]
  },
  // base
 resolve: {
    alias: {
      // 指向具体的文件，会先去找该文件，是有包括compiler的
      // 不设置的话，默认是指向vue.runtime.js的
      'vue$': 'vue/dist/vue.esm.js'
    }
  }
  plugins: [
    new webpack.BannerPlugin('最终解释权归XX所有')
  ]
}
```

 - **dev.config.js** -- 开发时

```javascript
// 这个是干嘛的来着，就放这一个
module.exports = {
  deVServer: {
    contentBase: './dist',
    inline: true
  }
}
```
 - prod.config.js -- 发布时


```javascript
const UglifyjsWebpackPlugin = require('Uglifyjs-webpack-plugin')

module.exports = {
  plugins: [
    new UglifyjsWebpackPlugin()
  ]
}
```
2. 安装合并包
`npm install webpack-merge --save-dev`
3. 导入合并包
以dev.config.js 为例，体会合并包的使用
```javascript
const webpackMerge = require('webpack-merge')
const baseConfig = require('./base.config')

// 合并的使用
module.exports = webpackMerge(baseConfig, {
  deVServer: {
    contentBase: './dist',
    inline: true
  }
})
```

## 2.Vue CLI
### 2.1 Vue CLI是什么
使用Vue.js开发大型应用时，我们需要考虑代码目录结构、项目结构和部署、热加载、代码单元测试等事情。
通常我们会使用一些脚手架工具来帮助完成这些事情。

CLI是Command-Line Interface,翻译为命令行界面，俗称脚手架。
Vue CLI是一个官方发布vue.js项目脚手架，使用Vue CLI可以**快速搭建Vue开发环境以及对应的webpack配置**。


### 2.2 Vue CLI依赖环境
#### 1.2.1 Vue CLI使用前提-Node
- 安装NodeJs
	- 可以直接在官方网站中下载安装.
	- 网址: 	http://nodejs.cn/download/
- 检测安装的版本
	- 默认情况下自动安装Node和NPM
	- Node环境要求8.9以上或者更高版本
	-![在这里插入图片描述](https://img-blog.csdnimg.cn/afb9260e13b44d1f8a13827a90cfdce6.png)

- 什么是NPM呢?
	- NPM的全称是Node Package Manager
	- 是一个NodeJS包管理和分发工具，已经成为了非官方的发布Node模块(包)的标准。
	- 后续我们会经常使用NPM来安装一些开发过程中依赖包.

- cnpm安装
	- 由于国内直接使用npm的官方镜像是非常慢的，这里推荐使用淘宝NPM镜像。
	- 可以使用淘宝定制的cnpm (gzip压缩支持)命令行工具代替默认的npm:
	`npm install -g cnpm --registry=https://registry.npm.taobao.org`
	这样就可以使用cnpm命令来安装模块了:
	`cnpm install [name]`
#### 1.2.2 Vue CLI使用前提-webPack
- Vue.js官方脚手架工具使用了webpack模板
	- 对所有的资源会压缩等优化操作
	- 它在开发过程中提供了一套完整的功能，能够使得我们开发过程中变得高效。
- Webpack的全局安装
	- `npm install webpack -g`

### 2.3 Vue CLI的安装
#### 1.3.1 安装 Vue CLI3
 `npm install -g @vue/cli`
	![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/eb6bc44e604d4454b8061be450527614.png)
注意∶上面安装的是Vue CLI3的版本，如果需要想按照Vue CLI2的方式初始化项目时不可以的。

#### 1.3.2 拉取2.x模板(旧版本)
Vue CLI3 和旧版使用了相同的`vue`命令，所以 Vue CLI2（vue-cli）被覆盖了，如果仍然需要使用旧版本的`vue init` 功能，可以全局安装一个桥接工具：

```bash
npm install -g @vue/cli-init
# "vue init’的运行效果将会跟‘vue-clie2.x”相同
vue init webpack my-project
```

## 3 Vue CLI2 的使用
### 1.4.1  Vue CLI2 初始化项目
- Vue CLI2 初始化项目
	- `vue init webpack my-project`
	- 会生成webpack相关的代码


### 1.4.2 Vue CLI2配置过程
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/863cf2b7c89745cc895403525036d685.png)
### 1.4.3 Vue CLI2目录结构解析
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/8fd8f30ae4ec4141a5fd26b2edcd752e.png)
### 1.4.4 runtime-compile和runtime-only的区别
#### 1.4.4.1 Vue程序运行过程
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/e074b92aa69f49c3b757f8078013c34c.png)

runtime-compiler(v1)
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/6264e5b8cf644ba5a65048c3690b750e.png)
template -> ast（abstract synax tree抽象语法树） -> render 函数-> vdom（virtual 虚拟 dom）->UI（真实dom）



runtime-only(v2)(1.性能更高2.下面的代码量更少)
![在这里插入图片描述](https://img-blog.csdnimg.cn/551a8b6bcb4d47549115e41ce59907a8.png)
render -> vdom -> UI
#### 1.4.4.2 render函数的使用
![在这里插入图片描述](https://img-blog.csdnimg.cn/502ff306fb874ff9885b4c6fcb1d05ec.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_13,color_FFFFFF,t_70,g_se,x_16)

![在这里插入图片描述](https://img-blog.csdnimg.cn/9125da3f1edf45c3b992701862777ef3.png)
`.$mount('app')`相当于`el: '#app'`。
### 1.4.3 使用runtime-only
最终被编译出来的就是一个普通的对象。这个普通的对象里，已经将template全部渲染成render函数了。
例如：下方的被编译出来的就是app对象，这个对象里没有template。（打印app对象，是没有template的，有render函数）
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/0cf2b56971b44f9cae7989a9382e244e.png)
在引用App对象时，引用的不是整个.vue文件，而是解析后的app对象，里面所有的template都转成render函数了。（vue-template-compiler 将.vue文件里的template，解析成render函数。）
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/cafa41520b874e22a3dc2a9e97d6b8ed.png)
所有的vue的组件里，包含的都是render函数，而不是template，所以vue用runtime-only即可。
## 4 Vue CLI3 的使用
### 4.1  Vue CLI3 初始化项目
- Vue CLI3 初始化项目
	- `vue create my-project`

项目名一般全是小写，可以用`-`分隔语义

### 4.2 Vue CLI3配置过程
![在这里插入图片描述](https://img-blog.csdnimg.cn/8ce1ce5cfb0148149a836111df30eb3d.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_20,color_FFFFFF,t_70,g_se,x_16)

### 4.3 Vue CLI3目录结构

![在这里插入图片描述](https://img-blog.csdnimg.cn/ee7925d8ebc946f483bd256baede0f32.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_20,color_FFFFFF,t_70,g_se,x_16)

### 4.3 Vue CLI配置修改

#### 4.3.1 Vue UI
`vue ui`，可以通过浏览器打开Vue项目管理器。
与目录无关，可以在任何目录下输入该命令。

#### 4.3.2 配置存放路径
CLI3的设置原则是“0配置”
#### 4.3.3 自定义配置
例：添加新的别名
在Vue CLI3创建的项目里如果需要修改配置的话，可以在当前项目的目录下，创建vue.config.js文件（名字是固定的）。 

![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/5b23bbf537b849a6b5339e15899f0ff9.png)

# 五、vue-router

![在这里插入图片描述](https://img-blog.csdnimg.cn/375d5c8926f748238ffb7c6ff25946d9.png)
## 1 认识路由
### 1.1 前端路由阶段：
1.**后端路由阶段**
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/b8aa316ceb524e19989de461b5a87200.png)

服务器端处理jsp代码，包括html+css+java代码（读取+渲染），直接传给浏览器进行展示。

后端路由：后端处理url和页面的映射关系。

2.**前后端分离阶段**
随着Ajax的出现,有了前后端分离的开发模式.
后端只提供API来返回数据,前端通过Ajax获取数据,并且可以通过JavaScript将数据渲染到页面中.
这样做最大的优点就是前后端责任的清晰,后端专注于数据上，前端专注于交互和可视化上.
并且当移动端(iOS/Android)出现后,后端不需要进行任何处理,依然使用之前的一套API即可.
目前很多的网站依然采用这种模式开发.
~~浏览器中显示的网页中的大部分内容,都是由前端写的js代码在浏览器中执行,最终渲染出来的网页.
后端只负责提供数据，不负责任何阶段内容。浏览器从静态资源服务器拿到html+css+js，执行js代码。向提供API接口服务的服务器请求，拿到数据。将数据相关的js代码渲染到浏览器中。~~

3.**单页面富应用阶段**:
其实SPA最主要的特点就是在前后端分离的基础上加了一层前端路由，也就是前端来维护一套路由规则。
一旦url发生改变，前端就去（html+css+js）全部资源抽取一部分js代码，把页面渲染出来。
前端路由：前端处理url和页面的映射关系。

### 1.2 前端路由核心的实现
前端路由的核心：**改变URL，但是页面不进行整体的刷新**。（F12的Network->All，观察是否有新文件的产生，“favicon.ico”文件忽略）。
#### 1.3.1 实现方式1：url的hash
- URL的hash也就是锚点(#),本质上是改变window.location的href属性.
- 我们可以通过直接赋值`location.hash`来改变href,但是页面不发生刷新。
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/79f743ae02ed4661aafef1185c5c65bb.png)


#### 1.3.2 html5的history模式
**1.history.pushState()**
特点：显示的url永远是最后压入栈的url。
点击浏览器的返回箭头，或者console控制台输入`history.back()`，会将栈顶移除掉，显示下一个栈顶的url。
浏览器的url显示如下：==为什么会带#==
![在这里插入图片描述](https://img-blog.csdnimg.cn/018d4f0db537451da34d4cc87c695b2b.png)

![在这里插入图片描述](https://img-blog.csdnimg.cn/81701d101fca4061ae8fcff7c5d05bb8.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_18,color_FFFFFF,t_70,g_se,x_16)
**2.history.replaceState()**
特点：用输入的url替换最新的url。
返回按钮会灰掉，不可以点击。
浏览器显示如下：==没有#==
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/fd9dee637ce0473d9f2c704eabd4f2a4.png)
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/9b06aad75172479686df10ee2b1ea345.png)
**3.history.go()**
`history.go(-1)`等价于`history.back()`
`history.go(-2)`等价于调用**2**次`history.back()`
`history.go(1)`等价于`history.forward()`
都等同于浏览器界面的前进后退箭头点击。
### 1.3 vue-router
目前前端流行的三大框架,都有自己的路由实现：
- Angular的ngRouter
- React的ReactRouter
- Vue的vue-router

vue-router 是 Vue.js (opens new window)官方的路由管理器。它和 Vue.js 的核心深度集成，让**构建单页面应用**变得易如反掌。
可以访问官方网站进行学习：https://router.vuejs.org/zh/

vue-router是基于路由和组件的
- 路由用于设定访问路径，将路径和组件映射起来.
- 在vue-router的单页面应用中，页面的路径的改变就是组件的切换.









利用vue cli2创建项目，配置如下：
==为啥要选runtime-only==
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/63e725e3041f478ab8b382600235ea96.png)
观察创建的项目，src文件夹下会多一个router文件夹；package.json文件中的依赖，会多一个vue-router。


## 2 vue-router基本使用
### 2.1 安装
使用npm来安装路由vue-router：
`npm install vue-router --save`
### 2.2 基本使用
- 搭建路由框架
	- 1.导入路由对象`import VueRouter from 'vue-router'`，导入vue对象`import Vue from 'vue'`，
	- 2.调用vue对象的方法，安装插件：`Vue.use(VueRouter)`
	(因为是一个插件,所以可以通过`Vue.use(插件)`来安装该插件)
	- 3.创建路由对象，并且配置路由映射配置。
	```javascript
	const router = new VueRouter({
		routes:[]
	})
	```
	- 4.导出路由对象`export default router`
	- 5.在Vue实例中挂载创建的路由实例
	注：import router的路径为一个文件夹，如果路径中设置的是文件夹，则默认查找该文件夹中名为index的文件。故文件名省略了。
	![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/931c72a453264744b5e11d4214b401aa.png)

- 配置路由的映射关系的步骤：
	- 第一步：创建路由组件（component文件夹下创建vue文件）
	- 第二步：router对象中的routes属性，配置组件和路径映射关系
	- 第三步:使用`<router-link to:"/home">`在页面上显示链接，to属性设置跳转路径
	- 第四步：使用`<router-view>`占位，展示组件内容

解释：
`<router-link>`:该标签是一个vue-router已经内置的组件,它会被渲染成一个`<a>`标签.
`<router-view>`:该标签会根据当前的路径,动态渲染出不同的组件.
网页的其他内容,比如顶部的标题/导航,或者底部的一些版权信息等会和`<router-view>`处于同一个等级.
在路由切换时,切换的是`<router-view>`挂载的组件,其他内容不会发生改变.
### 2.3 路由的默认路径
默认情况下，进入网站的首页，我们希望让路径默认跳到到首页,并且`<router-view>`渲染首页组件。
需要添加一个映射就可以。

```javascript
const routes = [
	{
		path: '/',
		redirect: '/home'
	},
```

配置解析：
我们在routes中添加一个映射
path配置的是根路径：/
redirect是重定向,也就是我们将根路径重定向到/home的路径下.

### 2.4 设置html5的history模式
默认是hash模式，url中会有“#”，不太好看。需要设置为history模式。

```javascript
const router = new VueRouter({
	//配置路由和组件之间的应用关系
	routes,
	mode: 'history'
})

```
### 2.5 router-link属性
`<router-link>`的属性：
- to，用于指定跳转的路径.
- tag，指定`<router-link>`之后渲染成什么组件，比如`<router-link to='/home' tag='li'>`会被渲染成一个`<li>`元素,而不是`<a>`
- replace: replace不会留下history记录,所以指定replace的情况下,后退键返回不能返回到上一个页面中
- active-class：当`<router-link>`对应的路由匹配成功时,会自动给当前元素设置一个`router-link-active`的class,设置active-class可以修改默认的名称.
	- 在进行高亮显示的导航菜单或者底部tabbar时,会使用到该类.
	- 通常不会修改类的属性,会直接使用默认的router-link-active即可.
	- 统一修改匹配的class名，可以在router对象中设置属性：linkActiveClass: 'active'`

### 2.6 通过代码跳转路由
有时候,页面的跳转可能需要执行对应的JavaScript代码,这个时候,就可以使用第二种跳转方式了。

```javascript
<template>
  <div id="app">
    <button @click="homeClick">首页</router-link>
    <button @click="aboutClick">关于</router-link>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'App',
  methods: {
  	homeClick() {
   	  //通过代码的方式修改路由
   	  this.$router.push('/home')
  	},
  	aboutClick() {
   	  //通过代码的方式修改路由
   	  this.$router.replace('/about')
  	}
  }
}
</script>

<style>

</style>
```

### 2.7 动态路由
在某些情况下，一个页面的path路径可能是不确定的，比如我们进入用户界面时，希望是如下的路径∶
/user/aaaa或/user/bbbb
除了有前面的/user之外，后面还跟上了用户的ID
这种path和Component的匹配关系，我们称之为动态路由(也是路由传递数据的一种方式)。
#### 2.7.1 动态路由举例
点击“用户”，跳转至的页面与用户ID相关，是不确定的。跳转后的页面要能正常显示，渲染的组件是确定的。
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/14c54386260241e9b451c9dbb9857d2b.png)

1. 新建User.vue组件文件
2. router文件夹下的index.js文件，导入User，并且配置映射关系
![在这里插入图片描述](https://img-blog.csdnimg.cn/8155f63c8e824a88b3a0a95581da18b3.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_12,color_FFFFFF,t_70,g_se,x_16)

3. Vue实例中设置userId变量，模板中设置`<router-link>`组件的to属性为‘/user/+userId’。因为userId需要访问实例中的变量，所以需要用到`v-bind`语法。
![在这里插入图片描述](https://img-blog.csdnimg.cn/f8746d31a0d8433eba2949ccb5b5ce6d.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_17,color_FFFFFF,t_70,g_se,x_16)
==这里的userId是写在App.vue文件里的，为啥后面的computed属性UserId是写在User.vue文件里呢？==
可能是因为使用的位置不一样。

#### 2.7.2 传递路径中的参数
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/77534b6a639841d1bd6a97ac50116b7c.png)
其中：`this.$route`代表的是当前活跃的路由对象。
`this.$route.params.userId`中的`userId`与路由映射里的参数写一致。
，![在这里插入图片描述](https://img-blog.csdnimg.cn/ee8041eb94ba4da29b8cf83402357818.png)
也可以不放在计算属性里，直接在模板中使用。这里不加`this`，可以这样理解：`this.$route.params.userId`取的是实例的data属性中的变量，故要加this，但是直接使用是不需要加的。
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/21c5589112a84b4baf204c0c506ed8d0.png)


### 2.8 认识路由的懒加载
#####  2.8.1 什么是路由懒加载
路由懒加载，就是用到时再加载。

官方解释:
- 当打包构建应用时，Javascript包会变得非常大，影响页面加载。
- 如果我们能**把不同路由对应的组件分割成不同的代码块，然后当路由被访问的时候才加载对应组件**，这样就更加高效了。

官方在说什么呢?
- 首先,我们知道路由中通常会定义很多不同的页面.
- 这个页面最后被打包在哪里呢?一般情况下,是放在一个js文件中.
- 但是,页面这么多放在一个js文件中,必然会造成这个页面非常的大.
- 如果我们一次性从服务器请求下来这个页面,可能需要花费一定的时间,甚至用户的电脑上还出现了短暂空白的情况.

- 如何避免这种情况呢?使用路由懒加载就可以了.

路由懒加载做了什么?
- 路由懒加载的主要作用就是将路由对应的组件打包成一个个的js代码块
- 只有在这个路由被访问到的时候,才加载对应的组件

**未使用懒加载，npm run build 打包文件的解析：**
![在这里插入图片描述](https://img-blog.csdnimg.cn/7c11bad13b4448dabe3e665970105cd0.png)
使用懒加载后，一个懒加载打包为一个js文件。
####  2.8.2 懒加载和非懒加载打包区别
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/4091e1f69095476f9e529b3cd4750c9a.png)
####  2.8.3 懒加载的方式
方式1：结合Vue的异步组件和webpack的代码分析。
（能认识即可）
`const Home = resolve => { require.ensure([ ' ../components/Home.vue']，() =>{ resolve(require( ' ../ components /Home.vue' )) })};`

方式2：ADM写法
`const About = resolve => require([ ' ../components/About.vue'],resolve);`

**方式3：在ES6中，我们可以有更加简单的写法来组织Vue异步组件和Webpack的代码分割.**
`const Home = () => import( '../components/Home. vue ' )`

## 3 vue-router嵌套路由

#### 3.1 认识嵌套路由
嵌套路由是一个很常见的功能
- 比如在home页面中,我们希望通过/home/news和/home/message访问一些内容.
- 一个路径映射一个组件，访问这两个路径也会分别渲染两个组件.

路径和组件的关系如下：
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/a26d16b5a094441c84a4955c2942b150.png)

#### 3.2 嵌套路由实现

实现嵌套路由的步骤：
- 创建对应的子组件
- 路由映射中配置对应的子路由
- 在组件内部使用`<router-view>`标签，确定子组件显示的位置
![在这里插入图片描述](https://img-blog.csdnimg.cn/6a6f0c1bf64a4c28a6c7b3c31260a4d2.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_16,color_FFFFFF,t_70,g_se,x_16)
注：子组件的path中不要加`‘/’`；路径写完整路径。

#### 5.3 嵌套默认路径
嵌套路由配置默认路径的方式如下：
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/30b11bab07544965bb70e99e55da804f.png)


## 4 vue-router参数传递
### 4.1 准备工作
![在这里插入图片描述](https://img-blog.csdnimg.cn/0a77c73363784b29ba868089e5fb2297.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_20,color_FFFFFF,t_70,g_se,x_16)
### 4.2 传递参数的方式
传递参数主要有两种类型: 
- params和query

params的类型:
- 配置路由格式：`/router/:id`
- 传递的方式：在path后面跟上对应的值
- 传递后形成的路径： `/router/123`，`/router/abc`

query的类型:
- 配置路由格式: `/router`，也就是普通配置
- 传递的方式：对象中使用query的key作为传递方式传递后形成
- 路径: `/router?id=123`，`/router?id=abc`

如何使用它们呢?
也有两种方式: `<router-link>`的方式和JavaScript代码方式

### 4.3 获取参数
获取参数通过`$route`对象获取的.
在使用了vue-router的应用中，路由对象会被注入每个组件中，赋值为`this.$route`，并且当路由切换时，路由对象会被更新。
通过`$route`获取传递的信息如下:
![在这里插入图片描述](https://img-blog.csdnimg.cn/91dd9dbbcff945d2b87a2c90ea4be663.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_20,color_FFFFFF,t_70,g_se,x_16)
`$route` 和`$router`的区别：
`$router`为VueRouter实例，想要导航到不同URL，则使用`$router.push`方法
`$route`为当前router跳转对象里面可以获取name、path、query. params等
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/aa261f7074df4e9c93ba5ac726215056.png)


## 7 vue-router导航守卫keep-alive
### 7.1 作用
### 导航首位补充
补充一：如果是后置钩子，也就是afterEach,不需要主动调用next()函数.
补充二：上面我们使用的导航守卫,被称之为全局守卫.
- 路由独享的守卫.
- 组件内的守卫.

更多内容,可以查看官网进行学习:
https://router.vuejs.org/zh/guide/advanced/navigation-
guards.htmI#%E8%B7%AF%E7%94%B1%
E7%9A%84%E5%AE%88%E5%8D
%AB
https://router.vuejs.org/guide/advanced/navigation-guards.html#navigation-guards

### keep-alive 遇见vue-rooter
keep-alive 是 Vue内置的一个组件，可以使被包含的组件保留状态，或避免重新渲染。

它们有两个非常重要的属性:
- include -字符串或正则表达，只有匹配的组件会被缓存
- exclude -字符串或正则表达式，任何匹配的组件都不会被缓存

router-view也是一个组件，如果直接被包在keep-alive里面，所有路径匹配到的视图组件都会被缓存︰

```html
<keep-alive>
	<router-view>
	<!--所有路径匹配到的视图组件都会被缓存!-->
	</router-view>
</keep-alive>
```

通过create声明周期函数来验证

## 案例：TabBar实现
## 1.1 实现思路
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/4bc5ea232d254225a26f449a94b087da.png)
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/748b12fa9dff4e37be79218635c73ef9.png)


# Promise
==这应该是ES6的内容，不知道为啥要在这里讲==

## 什么是promise
ES6中一个非常重要和好用的特性就是Promise
Promise到底是做什么的呢?
**Promise是异步编程的一种解决方案。**

那什么时候我们会来处理异步事件呢?
- 一种很常见的场景应该就是网络请求了。
- 我们封装一个网络请求的函数，因为不能立即拿到结果，所以不能像简单的3+4=7一样将结果返回。
- 所以往往我们会传入另外一个函数，在数据请求成功时，将数据通过传入的函数回调出去。
- 如果只是一个简单的网络请求，那么这种方案不会给我们带来很大的麻烦。
但是，当网络请求非常复杂时，就会出现回调地狱。
OK，我以一个非常夸张的案例来说明。
![在这里插入图片描述](https://img-blog.csdnimg.cn/5f18ac60b9a94d56b377d889d537fb5c.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_20,color_FFFFFF,t_70,g_se,x_16)
## 基本语法
我们先来看看Promise最基本的语法。
这里，我们用一个定时器来模拟异步事件:
假设下面的data是从网络上1秒后请求的数据console.log就是我们的处理方式。

这是我们过去的处理方式，我们将它换成Promise代码这个例子
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/1f20caab071c48b5a9ca35861a771780.png)

会让我们感觉脱裤放屁，多此—举
首先，下面的Promise代码明显比上面的代码看起来还要复杂。
其次，下面的Promise代码中包含的resolve、reject、then、catch都是些什么东西?
我们先不管第一个复杂度的问题，因为这样的一个屁大点的程序根本看不出来Promise真正的作用。


## Promise三种状态
首先,当我们开发中有异步操作时,就可以给异步操作包装一个Promise
异步操作之后会有三种状态我们一起来看一下这三种状态:
pending :等待状态，比如正在进行网络请求，或者定时器没有到时间。
fulfill:满足状态，当我们主动回调了resolve时，就处于该状态，并且会回调.then()
reject:拒绝状态，当我们主动回调了reject时，就处于该状态，并且会回调.catch)

==promise.all==

# 六、Vuex详情
## 1.认识Vuex
### 1.1 Vue是做什么的
官方解释: Vuex是一个专为Vue.js应用程序开发的状态管理模式。
- 它采用集中式存储管理应用的所有组件的状态，并以相应的规则保证状态以一种可预测的方式发生变化。
- Vuex也集成到Vue的官方调试工具devtools extension，提供了诸如零配置的 time-travel调试、状态快照导入导出等高级调试
功能。

**状态管理**，可以简单的将其看成把需要多个组件共享的变量全部存储在一个对象里面。然后，将这个对象放在页层的Vue实例中，让其他组件可以使用。
那么，多个组件是不是就可以共享这个对象中的所有变量属性了呢?

如果是这样的话，为什么官方还要专门出一个插件Vuex呢?难道我们不能自己封装一个对象来管理吗?
- 当然可以，只是我们要先想想VueJS带给我们最大的便利是什么呢?没错，就是**响应式**。
- 如果你自己封装实现一个对象能不能保证它里面所有的属性做到响应式呢?当然也可以，只是自己封装可能稍微麻烦一些。
- 不用怀疑，Vuex就是为了提供这样一个在多个组件间共享状态的插件，用它就可以了。
## 1.2 管理什么状态
有什么状态时需要我们在多个组件间共享的呢?
- 如果你做过大型开放，你一定遇到过多个状态，在多个界面间的共享问题。
- 比如用户的登录状态、用户名称、头像、地理位置信息等等。
- 比如商品的收藏、购物车中的物品等等。
- 这些状态信息，我们都可以放在统一的地方，对它进行保存和管理，而且它们还是响应式的(待会儿我们就可以看到代码了，莫着急）。

OK，从理论上理解了状态管理之后，让我们从实际的代码再来看看状态管理。毕竟，Talk is cheap, Show me the code.(来自Linus)
## 1.3 单界面的状态管理
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/682f4061a3904ee7a86ec8c3923792f5.png)

图片的理解：
State：就是我们的状态。（你姑且可以当做就是
data中的属性)
View：视图层，可以针对State的变化，显示不同的信息。
Actions：这里的Actions主要是用户的各种操作︰点击、输入等等，会导致状态的改变。
## 1.4 多界面的状态管理
Vue已经帮我们做好了单个界面的状态管理，但是如果是多个界面呢?多个试图都依赖同一个状态（一个状态改了，多个界面需要进行更新)
不同界面的Actions都想修改同一个状态(Home.vue需要修改，Profile.vue也需要修改这个状态)
也就是说对于某些状态(状态1/状态2/状态3)来说只属于我们某一个试图，但是也有一些状态(状态a/状态b/状态c)属于多个试图共同想要维护的
状态1/状态2/状态3你放在自己的房间中，你自己管理自己用，没问题。但是状态a/状态b/状态c我们希望交给一个大管家来统一帮助我们管理!!!没错，Vuex就是为我们提供这个大管家的工具。
全局单例模式(大管家)
我们现在要做的就是将共享的状态抽取出来，交给我们的大管家，统一进行管理。之后，你们每个试图，按照我规定好的规定，进行访问和修改等操作。
这就是Vuex背后的基本思想。
## 1.5 Vuex状态管理图例
![在这里插入图片描述](https://img-blog.csdnimg.cn/1386d58429d24dc3bca3164f1bfdd803.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_20,color_FFFFFF,t_70,g_se,x_16)
## 2 简单的案例
### 2.1 vuex 安装
安装vue的插件：
`npm install vuex --save`
### 2.2 vuex 使用
调用vue.use()插件
vue devtools插件的安装，见：https://blog.csdn.net/li22356/article/details/113092495
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/d2772ff3b40b4d8b971d6a4997f57306.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/8c432d4d97884d25a5ea7c5ff2362a43.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_20,color_FFFFFF,t_70,g_se,x_16)
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/c666d712164b4c50b5ade895bdc66d2d.png)


## 3.vuex 核心概念
vuex有几个比较核心的概念：
State 
Getters
Mutation
Action
Module 
###  3.1 State单一状态树
在一个项目中，只建一个store
###  3.2 getters 
#### 3.2.1 getters 基本使用
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/61e596a2a7874f378a364951e1998e8b.png)
#### 3.2.2 getters 作为参数和传递参数
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/a28d8f4dcc074917b290b234bd838386.png)

![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/3323153cbdeb41f2a8eec5d43e33682a.png)
###  3.3 mutation 
#### 3.3.1 mutation 状态更新
- vuex的store状态的更新唯一方式∶提交Mutation

- Mutation主要包括两部分∶
	- 字符串的事件类型( type )
	- 一个回调函数( handler ) ,该回调函数的第一个参数就是state。
- mutation的定义方式:

```javascript
mutations: {
	increment(state) {
		state.count++
	}
}
```

- 在methods选项中，通过mutation更新

```javascript
increment() {
	this.$store.commit('increment')
}
```
#### 3.3.2 mutation 传递参数

- 在通过mutation更新数据的时候，有可能我们希望携带一些额外的参数
- 参数被称为是mutation的载荷(payload)
- mutation中的代码：
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/09ca8cc46dca4e43b85bcca24c6e9833.png)
- 但是如果参数不是一个呢?
有很多参数需要传递的时候，我们通常会以对象的形式传递，也就是payload是一个对象，再从对象中取出相关的信息。
![在这里插入图片描述](https://img-blog.csdnimg.cn/15b28813a23446a790e083403b6ffd28.png)
#### 3.3.3 mutation 提交风格
![在这里插入图片描述](https://img-blog.csdnimg.cn/372febdd81db40c9be243ff938af3c0a.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_20,color_FFFFFF,t_70,g_se,x_16)
#### 3.3.4 mutation 响应规则 

> 这些属性都会被加入到响应式系统中,而响应式系统会监听属性的变化。当属性发生变化时，会通知所有界面中用到该属性的地方,让界面发生刷新。

Vuex的store中的state是响应式的，当state中的数据发生改变时, Vue组件会自动更新。 

这就要求我们必须遵守一些Vuex对应的规则：
- 提前在store中初始化好所需的属性.
- 当给state中的对象添加新属性时,使用下面的方式:
	- 方式一：使用Vue.set(obj, 'newProp',123)
	- 方式二:用新对象给旧对象重新赋值

![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/fbd3921310d84bc394a7ebb254b49b33.png)
delete补充：
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/5f60a258570e42d5bb087dfa183341a8.png)
#### 3.3.5 mutation 常量类型
##### 3.3.5.1 概念
在mutation中,我们定义了很多事件类型(也就是其中的方法名称).
当我们的项目增大时，Vuex管理的状态越来越多，需要更新状态的情况越来越多，那么意味着Mutation中的方法越来越多

方法过多，使用者需要花费大量的经历去记住这些方法，甚至是多个文件间来回切换.查看方法名称,甚至如果不是复制的时候,可能还会出现写错的情况.
##### 3.3.5.2 代码
1.创建mutations-types.js文件，设置常量；
2.在index.js文件中，导入并替换常量代替的变量
2.在App.vue文件中，导入并替换变量。
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/04da091d95184e5b8f3a68a187a8b0f2.png)
#### 3.3.6 mutation 同步函数
通常情况下, Vuex要求我们Mutation中的方法必须是同步方法.
主要的原因是当我们使用devtools时,可以devtools可以帮助我们捕捉mutation的快照.但是如果是异步操作,那么devtools将不能很好的追踪这个操作什么时候会被完成.
比如我们之前的代码,当执行更新时, devtools中，state中的info数据一直没有被改变，因为他无法追踪到。
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/8aae5db6b13b47de9b4e75cc60082463.png)
所以，通常请款下，不要在mutations中进行异步的操作。
### 3.4 action
我们强调，不要再Mutation中进行异步操作.
但是某些情况,我们确实希望在Vuex中进行一些异步操作，比如网络请求,必然是异步的.这个时候怎么处理呢?
Action类似于Mutation,但是是用来代替Mutation进行异步操作的.
#### 3.4.1 action的使用
1.设置按钮点击方法为`updateInfo`

```html
<h2>info中的name：{{$store.state.info.name}}</h2>
<button @click="updateInfo">修改info</button>
```
2.在methods选项中写该方法，使用`dispatch()`调用action

```javascript
    updateInfo() {
      // 异步操作，用dispatch调用action中的方法
      this.$store.dispatch('aUpdateInfo')
    }
```
3.在store文件夹下的index.js中Vuex.Store对象的action选项中写方法，并在该方法中使用commit()调用mutations选项中的方法

```javascript
  // 异步操作
  // 异步操作的情况：发送网络请求
  actions: {
    // context:上下文
    aUpdateInfo(context) {
      setTimeout(() => {
        context.commit('updateInfo')
      },1000)
    }
  },
```
4.mutations选项中的方法，进行具体的操作。

```javascript
  //同步操作的方法 
  mutations: {
    // 默认传过来state
    updateInfo(state) {
      state.info.name = 'zs'
    }
  },
```
#### 3.4.2 action传递参数
1.App.vue文件中使用dispatch()，方法中传入参数的值。

```javascript
    updateInfo() {
      // 异步操作，在action中进行
      this.$store.dispatch('aUpdateInfo','我是payload')
    }
```
2.actions的方法中的参数列表对应，并在该方法中使用传入的参数。
```javascript
actions: {
    // context:上下文
    aUpdateInfo(context,payload) {
      setTimeout(() => {
        context.commit('updateInfo')
        console.log(payload)
      },1000)
    }
  },
```
### 3.5 modules
#### 3.5.1 认识modules
Module是模块的意思,为什么在Vuex中我们要使用模块呢?Vue使用单—状态树,那么也意味着很多状态都会交给Vuex来管理.

当应用变得非常复杂时,store对象就有可能变得相当臃
肿.
为了解决这个问题, Vuex允许我们将store分割成模块
(Module),而每个模块拥有自己的state、mutations、actions、getters等
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/ebf6455d36fb40519093e9a4cad99460.png)
### 3.5.2 modules局部状态
上面的代码中,我们已经有了整体的组织结构,下面我们来看看具体的局部模块中的代码如何书写.我们在moduleA中添加state、mutations、getters
mutation和getters接收的第一个参数是局部状态对象
![在这里插入图片描述](https://img-blog.csdnimg.cn/083b705dadb44491b0da5dfa28e1869a.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_20,color_FFFFFF,t_70,g_se,x_16)
注意:
虽然,我们的doubleCount和
increment都是定义在对象内部的.>但是在调用的时候,依然是通过
this.$store来直接调用的.

![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/c274175ac49a49beb00459c4fe26004b.png)
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/e7b9c970ec4e49de8158de0041171ff6.png)
### 3.5.3 actions的写法
![在这里插入图片描述](https://img-blog.csdnimg.cn/988f9acca0b14c5b9f4211ed872381c7.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_18,color_FFFFFF,t_70,g_se,x_16)

# 七、网络封装

## 1.网络模块选择

vue中发送网络请求有非常多的方式,那么,在开发中,如何选择呢?

### 选择一:传统的Ajax是基于`XMLHttpRequestXHR)`
为什么不用它呢?
非常好解释,配置和调用方式等非常混乱.
编码起来看起来就非常蛋疼.
所以真实开发中很少直接使用,而是使用jQuery-Ajax

### 选择二:在前面的学习中,我们经常会使用`jQuery-Ajax`
相对于传统的Ajax非常好用.
为什么不选择它呢?
首先,我们先明确一点:在Vue的整个开发中都是不需要
使用jQuery 了.
那么,就意味着为了方便我们进行一个网络请求,特意引用一个jQuery,你觉得合理吗?
jQuery的代码1w+行.
Vue的代码才1w+行.
完全没有必要为了用网络请求就引用这个重量级的框架.

### 选择三:官方在Vue1.x的时候,推出了`Vue-resource`.Vue-resource的体积相对于jQuery小很多.≥另外Vue-resource是官方推出的.

为什么不选择它呢?
在Vue2.0退出后, Vue作者就在GitHub的Issues中说明
了去掉vue-resource,并且以后也不会再更新.
那么意味着以后vue-reource不再支持新的版本时,也不
会再继续更新和维护.
对以后的项目开发和维护都存在很大的隐患.

### 选择四:在说明不再继续更新和维护vue-resource的同时,作者还推荐了一个框架: `axios`为什么不用它呢?
axios有非常多的优点,并且用起来也非常方便。稍后,我们对他详细学习.

## 2.JSONP

在前端开发中,我们一种常见的网络请求方式就是JSONP，使用JSONP最主要的原因往往是为了解决跨域访问的问题.

### 2.1 JSONP原理的回顾

JSONP的原理是什么呢?
JSONP的核心在于通过`<script>`标签的src来帮助我们请求数据.原因是我们的项目部署在domain1.com服务器上时，是不能直接访问domain2.com服务器上的资料的.
这个时候我们利用`<script>`标签的src帮助我们去服务器请求到数据,将数据当做一个javascript的函数来执行,并且执行的过程中传入我们需要的json.
所以封装jsonp的核心就在于我们监听window上的jsonp进行回调时的名称。

### 2.2 JSONP代码的封装
我们一起自己来封装一个处理JSONP的代码吧.
![在这里插入图片描述](https://img-blog.csdnimg.cn/b8a4d4fe32ef4fb6a22975899f8b243b.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_13,color_FFFFFF,t_70,g_se,x_16)

## 3.axios的使用

### 3.1 认识axios

#### 3.1.1 为什么选择axios

- 为什么选择axios：

  - vue作者官方推荐

  ![image-20210917201825728](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210917201825728.png)

  - 功能特点
    - 在浏览器中发送XMLHttpRequests请求
    - 在node.js中发送http请求
    - 支持Promise API
    - 拦截请求和响应转换请求和响应数据
    - 等等
      

![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/64e7b7ebeda64103aee5d3a1929c8d70.png)

####  3.1.2 axiox请求方式

支持多种请求方式：
- axios(config)
- axios.request(config)
- axios.get(url[, config])
- axios.delete(url[, config])
- axios.head(url[, config])
- axios.post(url[, data[, configl])
- axios.put(url[, data[, config]])
- axios.patch(url[, data[, config]])

### 3.2 axios框架的基本使用

1.安装axios框架：

`npm install axios --save`

注：线上程序依然适用，故用`--save`，而不是`--save -dev`

2.import导入

3.axios对象



API：

可以通过http://httpbin.org/进行验证，有很多的API。

老师使用的是：123.207.32.32:8000/home/multidata



以发送get请求为例，代码如下：

（在main.js文件中）

```javascript
import axios from 'axios'

axios({
  url: 'http://123.207.32.32:8000/home/multidata',
  // 请求方式设置，不写的话，默认为get
  methods: 'get'
}).then(res => {
  console.log(res);
}).catch(err => {
  console.log(err);
})
```

遇到的bug如图：

![image-20210916150936283](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210916150936283.png)

报错的原因是：url 写成uri了。 

### 3.2 发送请求

#### 3.2.1 发送get请求

（API：123.207.32.32:8000/home/data?type=pop&page=2）

有请求参数的2种写法：

1.直接放在url的后面，用`?`拼接

```javascript
import axios from 'axios'

axios({
  url: 'http://123.207.32.32:8000/home/data?type=pop&page=2'
}).then(res => {
  console.log(res);
})
```

2.写在params选项中

```javascript
import axios from 'axios'

axios({
  url: 'http://123.207.32.32:8000/home/data',
  // 专门针对get请求的参数拼接
  params: {
    type: 'pop',
    page: 2
  }
}).then(res => {
  console.log(res);
})
```



#### 3.2.2 发送并发请求

- 有时候,我们可能需求同时发送两个请求。

  - 使用`axios.all`,可以放入多个请求的数组.

  ```javascript
  import axios from 'axios'
  
  // axios发送并发请求
  axios.all([
    axios({
      url: 'http://123.207.32.32:8000/home/multidata',
      // 请求方式设置，不写的话，默认为get
      methods: 'get'
    }),
    axios({
      url: 'http://123.207.32.32:8000/home/data',
      params: {
        type: 'sell',
        page: 5
      }
    })
  ]).then(results => {
    console.log(results);
  })
  ```

  

  - `axios.all([])`返回的结果是一个数组，使用`axios.spread` 可将数组[res1,res2]展开为res1, res2

![image-20210916155749985](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210916155749985.png)

#### 3.2.3 axios全局配置

- 在上面的示例中,我们的BaseURL是固定的
  - 事实上，在开发中可能很多参数都是固定的.
  - 这个时候我们可以进行一些抽取,也可以利用axiox的全局配置

在main.js文件中进行设置即可。

```javascript
axios.defaults.baseURL = 'http://123.207.32.32:8000'
axios.defaults.timeout = 5000
axios.defaults.headers.post['Content-Type'] ='application/x-www-form-urlencoded';
```

axios.defaults.baseURL 和axios对象中的url变量拼接起来，为发送请求的url。

![image-20210916161745738](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210916161745738.png)

#### 3.2.4 常见配置选项

- 请求地址
  - url: "/user',
- 请求类型
  - method: 'get',
- 请求根路径
  - baseURL: 'http://www.mt.com/api',
- 请求前的数据处理
  - transformRequest: [function(data){}].
- 请求后的数据处理
  - transformResponse: [function(data){}].
- 自定义的请求头
  - headers:{'x-Requested-With': 'XMLHttpRequest'),
- URL查询对象
  params: { id: 12 },

![image-20210916161635961](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210916161635961.png)

![image-20210916162556813](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210916162556813.png)

### 3.3 axios实例

#### 3.3.1 为什么创建axios实例

- 为什么要创建axios的实例呢?
  - 当我们从axios模块中导入对象时，使用的实例是默认的实例.
  - 当给该实例设置一些默认配置时，这些配置就被固定下来了。但是后续开发中,某些配置可能会不太一样.
  - 比如某些请求需要使用特定的baseURL或者timeout或者content-Type等.
  - 这个时候我们就可以创建新的实例,并且传入属于该实例的配置信息.



#### 3.3.2 如何创建axios实例

```javascript
// 创建axios的实例
const instance1 = axios.create({
  baseURL: 'http://123.207.32.32:8000',
  timeout: 5000
})
// 传入配置信息
instance1({
  url: '/home/multidata'
}).then(res => {
  console.log(res);
})
// 传入配置信息
instance1({
  url: '/home/data',
  params: {
    type: 'pop',
    page: 1
  }
}).then(res => {
  console.log(res);
})
```



#### 3.3.3 axios的封装

1.一般使用（不做封装）

```JavaScript
<template>
  <div id="app">
    <img src="./assets/logo.png">
    <div>{{result}}</div>
    <router-view/>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'App',
  data() {
    return {
      result: ''
    }
  },
  // 监听组件创建完，发送请求
  created() {
    axios({
      url: 'http://123.207.32.32:8000/home/multidata'
    }).then(res => {
      console.log(res);
      this.result = res;
    })
  }
}
</script>

<style>
</style>

```

缺点：对网络请求的框架过于依赖，一旦需要更换，每个组件的引入和使用都需要更换。

注意：对于第三方框架的使用，一定注意不要每个组件都引用和使用一遍。

2.进行封装：

使用单独一个文件对该第三方框架进行封装，使所有的组件进行网络请求时，都是面向自己的这个文件的。





### 3.4 axios 的拦截器

### 3.4.1 请求拦截器

### 3.4.2 响应拦截器

# 八、项目实战

## 1 项目创建和Git托管
### 1.1 项目创建
使用Vue CLI3创建项目：
`npm create supermall`
暂时先选择最简单的配置，有啥需要的==这里是配置啥来着== ，以后再添加。
`npm run serve`语句，启动本地服务器。
![在这里插入图片描述](https://img-blog.csdnimg.cn/937b8902889a460abb03a0fc4920fffe.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_13,color_FFFFFF,t_70,g_se,x_16)
新建仓库
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/f5ddb3b5767a486999b3619dcabb53c9.png)
复制https链接
![在这里插入图片描述](https://img-blog.csdnimg.cn/5f10452c2dca46c1aae102466900473c.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_19,color_FFFFFF,t_70,g_se,x_16)
终端输入命令`git clone '复制的链接’`
![在这里插入图片描述](https://img-blog.csdnimg.cn/e44b0d751a5a47539b2c5c78851d35a6.png)
将除了.git（联系本地和远程git的文件）和node_modules（被忽略）以外的文件移至克隆的目录下。
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/9673d5c87e8d4e909e8f9bcebedb7abf.png)
绿色表示：不在代码管理之下。
![在这里插入图片描述](https://img-blog.csdnimg.cn/4c345ca1283d44ceb4272d8f3995251b.png)
1.`cd supermall`，进入目录下
2.`git status`命令，可以发现全部是红色的。
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/0b1c1c76abcf49ccb29e1cb9b53c5cec.png)
3.`git add .`，将所有的文件添加
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/34bdad5bc3d249849ffbd7584264d4f4.png)

4.`git commit -m '初始化项目'`，提交到本地

![在这里插入图片描述](https://img-blog.csdnimg.cn/c86e7753ddee4d4ead5294614dcf80a6.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_16,color_FFFFFF,t_70,g_se,x_16)
5.`git push`，提交到服务器

这里

或者，不想使用复制文件到仓库的方式，也可以
1.创建空仓库（啥也不要选）
2.用`git remote add origin 仓库地址`
3.`git push -u origin master`
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/eb3f39da856e41bb8e673c5c0c52c63e.png)
### 1.2 划分目录结构
1.删除多余的文件和内容
![在这里插入图片描述](https://img-blog.csdnimg.cn/93564891631e44f9b1a787ab784b9df7.png)
删掉app.vue文件中相关的引用部分。
![在这里插入图片描述](https://img-blog.csdnimg.cn/92cc45d5330a470a9b63c3f517e5965b.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_16,color_FFFFFF,t_70,g_se,x_16)
新增几个文件夹
- assets文件夹：添加资源类文件
	- css文件夹：放css文件
	- img：放图片
- commen文件夹：放公用的变量
- 
	

![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/7311f1a290064e0bb35f2a557701fa67.png)
### 1.3 vue.config.js配置
配置别名：
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/e1490072a07c499d909f43649285156c.png)
可以通过`this.$router`、`this.$store`来得到对应的对象。并且引用的地方只有一个。故，不用写别名。

### 1.4 tabbar引入和模块划分

