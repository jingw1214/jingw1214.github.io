> 视频地址：
>
> https://www.bilibili.com/video/BV1ji4y1876Y?p=20

# 1.Ajax 基础

传统网站中存在的问题：
- 网速慢的情况下，页面加载时间长,用户只能等待
- 表单提交后，如果一项内容不合格，需要重新填写所有表单内容
- 页面跳转，重新加载页面，造成资源浪费，增加用户等待时间

## 1.1 Ajax 概述
Ajax：标准读音[ˈeɪdʒæks] ，中文音译:阿贾克斯
它是浏览器提供的一套方法，可以**实现页面无刷新更新数据，提高用户浏览网站应用的体验**。

## 1.2 Ajax 的应用场景

 1. 页面上拉加载更多数据
 2. 列表数据无刷新分页
 3. 表单项离开焦点数据验证
 4. 搜索框提示文字下拉列表

## 1.3 Ajax的运行环境
Ajax技术需要**运行在网站环境中才能生效**，当前课程会使用Node创建的服务器作为网站服务器。

# 2.Ajax运行原理及实现
##  2.1 Ajax运行原理
Ajax相当于浏览器发送请求与接收响应的代理人，以实现在不影响用户浏览页面的情况下，局部更新页面数据，从而提高用户体验。
![在这里插入图片描述](https://img-blog.csdnimg.cn/338e33b0c8c54eeaa16436f766900b63.png)
##  2.2 Ajax的实现步骤

1.创建Ajax对象

```javascript
var xhr =new XMLHttpRequest();
```
2.Ajax初始化，配置请求方式以及请求地址

```javascript
xhr.open('get', 'http://www.example.com');
```
3.发送请求

```javascript
xhr.send();
```
4.获取服务器端给与客户端的响应数据

当ajax接收完服务器端对客户端的响应后，浏览器就会触发xhr的onload事件。

```javascript
xhr.onload = function () {
console.log (xhr.responseText);//获取响应数据
)
```

```javascript
// 创建 Ajax 对象
var xhr = new XMLHttpRequest()
// 告诉ajax对象向哪发送请求，以什么方式发送请求
xhr.open('get','http://localhost:3000/first');
// 发送请求
xhr.send();
// 获取服务器端响应到客户端的数据
xhr.onload = function() {
    // 获取响应数据
    console.log(xhr.responseText);
}
```
##  2.3 服务器端响应的数据格式
在真实的项目中，服务器端**大多数情况下会以JSON对象作为响应数据的格式**。当客户端拿到响应数据时,要将JSON 数据和HTML字符串进行拼接，然后将拼接的结果展示在页面中。

在http请求与响应的过程中，无论是请求参数还是响应内容，如果是对象类型，最终都会被转换为**字符串**进行传输。

window对象的JSON对象的`parse()方法`：

```javascript
JSON.parse() // 将json字符串转换为json对象
```
##  2.4 请求参数传递
### 2.4.1.传统网站表单提交

根据请求方式的不同，表单内容会变成请求参数，被自动拼接到对应的位置。

- get请求方式：请求参数会被拼接到请求地址后面
- post请求方式：请求参数会被放到请求体中。

无论是get请求，还是post请求，请求参数的格式都是：`参数名称=参数值`，多个请求参数用`&`进行分隔。

```html
<form method="get" action="http : //waw.example.com">
<input type="text" name="username" />
<input type="password" name="password"></form>
<!- http://wwra.example.com?username=zhangsa&spassword=123456-->
```
### 2.4.2.使用Ajax请求参数

 1. 请求参数需要程序自己拼接
 2. 根据请求方式的不同，将请求参数放到对应的位置上。
 3. 参数的格式依然是：`参数名称=参数值`，多个请求参数用`&`进行分隔。

● GET请求方式
拼接完成的请求参数，放在`请求地址 + ?`的后面。
```javascript
xhr.open ('get','http://www.example.com?name=zhangsan&age=20');
```

```javascript
<body>
    <p>
        <input type="text" id="username">
    </p>
    <p>
        <input type="text" id="age">
    </p>
    <p>
        <input type="button" value="提交" id="btn">
    </p>
    <script>
        // 获取按钮元素
        var btn = document.getElementById('btn')
        var username = document.getElementById('username');
        var age = document.getElementById('age');

        // 为按钮添加点击事件响应函数
        btn.onclick = function() {
            // 创建 Ajax 对象
            var xhr = new XMLHttpRequest()
            // 获取用户在文本框中输入的值
            var nameValue = username.value;
            var ageValue = age.value;
            // 拼接请求参数字符串
            var params = 'username=' + nameValue +'&age=' +ageValue;
            // Ajax 初始化，配置请求方式和请求地址
            xhr.open('get','http://localhost:3000/get?' + params);
            // 发送请求
            xhr.send();
            // 当ajax接收完服务器端对客户端的响应后，浏览器就会触发xhr的onload事件。
            // 监听xhr 的onload事件，获取完整的响应数据
            xhr.onload = function() {
            // 获取的响应数据
            console.log(xhr.responseText);
            // var responseText = JSON.parse(xhr.responseText);
            // console.log(responseText);
            // var str = '<h2>' + responseText.name + '</h2>';
            // document.body.innerHTML = str;
        }
        }
       
    </script>
</body>
```
● POST请求方式

1. POST请求必须在请求报文中，明确设置**请求参数内容的类型**。`setRequestHeader()方法`设置`content-type属性`为：

	1.application/x-www-form-urlencoded
	> name=zhangsan&age=20&sex=男

	2.application/json
	在请求头中指定Content-Type属性的值是application/json，告诉服务器端当前请求参数的格式是json。
	
	> {name: 'zhangsan', age: '20',sex: '男'}


2. POST请求方式的请求参数，不放在请求地址后面，而是放在请求体--`send()方法`中。

```javascript
// 设置请求报文中的报文头信息,
// content-type属性设置为`'application/x-www-form-urlencoded'`
xhr.setRequestHeader('content-Type', 'application/x-www-form-urlencoded')
xhr.send ('name=zhangsan&age=20');
```
由于向服务器传递请求参数时，参数必须以字符串的形式进行传递。需要用`JSON.stringify()方法`将json对象转换为json字符串。

```javascript
JSON.stringify()  
```

传递的post 请求参数如下图：
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/b7b91f9e57384b1c9d68ef4fa3570fc8.png)

```javascript
// 请求参数的格式是json
 <script>
     // 创建 Ajax 对象
     var xhr = new XMLHttpRequest()
     // Ajax 初始化，配置请求方式和请求地址
     xhr.open('post','http://localhost:3000/json');
     // 设置请求报文中的报文头信息,
	 // content-type属性设置为`'application/json'`
     xhr.setRequestHeader('Content-Type', 'Application/json');
     // JSON.string() 将json对象转换为json字符串
     // 发送请求
     xhr.send(JSON.stringify({name:'zs',age: 22}));
     // 获取服务器端响应到客户端的数据
     xhr.onload = function() {
         // 获取响应数据
         console.log(xhr.responseText);
     }
 </script>
```

```javascript
const express = require('express');
const path = require('path');
const bodyParser = require('body-parser');

const app = new express();

app.use(express.static(path.join(__dirname, 'public')));
// 定义全局的中间件，处理req.body，使其不为空。
app.use(bodyParser.json());

app.post('/json',(req, res) => {
    // 请求处理函数
    // 返回一个对象类型的值
    // 在对象里存储的就是客户端传到服务端的get请求参数
    console.log(req.body);
    res.send(req.body);
    
})

app.listen(3000, function(){
    console.log('服务器启动成功');
})

```
注意: get请求是不能提交json对象数据格式的，传统网站的表单提交也是不支持json对象数据格式的。

☆ 请求报文
在HTTP请求和响应的过程中传递的数据块就叫`报文`，包括要传送的数据和一些附加信息，这些数据和信息要遵守规定好的格式。
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/f777f9d6a5cb49228abf94d7ddd834cd.png)
##  2.5 获取服务器端的响应
###  2.5.1 onload事件
监听xhr 的onload事件，获取完整的响应数据。
当ajax接收完服务器端对客户端的响应后，浏览器就会触发xhr的onload事件。
###  2.5.2 利用Ajax状态码
在创建ajax对象，配置ajax对象，发送请求，以及接收完服务器端响应数据，这个过程中的每一个步骤都会对应一个数值，这个数值就是**ajax状态码**。
`xhr.readystate属性`获取Ajax状态码：
0:请求未初始化(还没有调用open())
1:请求已经建立。但是还没有发送(还没有调用send())
2:请求已经发送
3:请求正在处理中。通常响应中已经有部分数据可以用了
4:响应已经完成，可以获取并使用服务器的响应了

监听ajax对象的`onreadystatechange 事件`，当ajax状态码发生变化时将自动触发该事件。再判断当前的Ajax状态码是否等于4，可判断是否已经获取了完整的服务器传给客户端的响应数据。

###  2.5.3 区别
两种获取服务器端响应方式的区别：
![在这里插入图片描述](https://img-blog.csdnimg.cn/9188a321950142ddb331a8bceb49f39d.png)
因为当前IE低版本浏览器已经很少有人在用了，使用onload事件代码更简洁，且只需要调用一次，效率更高。所以更推荐onload事件。如果一定要兼容IE低版本浏览器，则使用onreadystatechange事件。
##  2.6 Ajax 错误处理
1.网络畅通，服务器端能接收到请求，服务器端返回的结果不是预期结果。
----*可以判断服务器端返回的状态码，分别进行处理。xhr.status获取http状态码*
设置返回400的代码如下：

```javascript
app.get('/error', (req, res) => {
    // 在服务端设置响应给客户端的http状态码为400
    res.status(400).send('not OK');
})
```
判断服务器返回的状态码，并进行处理：
```javascript
// 获取服务器端响应到客户端的数据
xhr.onload = function() {
      console.log(xhr.responseText);
      // xhr.status 获取http状态码
      if (xhr.status == 400) {
          alert('请求出错');
      }
      
  }
```
2.网络畅通,服务器端没有接收到请求，返回404状态码（代表请求地址不存在）。
----*检查请求地址是否错误*
html文件中：  `xhr.open('get','http://localhost:3000/error1');`js文件中，没有写对应的路由。故而报错404。
![在这里插入图片描述](https://img-blog.csdnimg.cn/437880c0aedf4855a22f9665352661d6.png)
3.网络畅通，服务器端能接收到请求，服务器端返回500状态码。

```javascript
app.get('/error', (req, res) => {
    // 变量未定义
    console.log(abc);
})
```
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/c9193008e9e94369ae132fd97796d2ac.png)
4．网络中断，请求无法发送到服务器端。
----*会触发xhr对象下面的onerror事件，在onerror事件处理函数中对错误进行处理。*

```javascript
btn.onclick = function() {
	var xhr = new XMLHttpRequest(); 
	xhr.open('get','http://localhost:3000/error');
    xhr.send();
    // 当网络中断时会触发onerror事件
    xhr.onerror = function() {
        alert('网络中断，无法发送Ajax请求');
    }
 }
```
Ajax状态码：表示Ajax请求的过程状态，ajax对象返回的
Http状态码：表示请求的处理结果，是服务器端返回的
##  2.7 低版本IE浏览器的缓存问题
问题：在低版本的IE浏览器中，Ajax请求有严重的缓存问题，即在请求地址不发生变化的情况下，只有第一次请求会真正发送到服务器端，后续的请求都会从浏览器的缓存中获取结果。即使服务器端的数据更新了，客户端依然拿到的是缓存中的旧数据。

解决方案：在请求地址的后面加请求参数，保证每一次请求中的请求参数的值不相同。
`xhr.open ( 'get' , 'http://www.example.com?t=' + Math.random ());`

#  3 Ajax 异步编程
## 3.1 同步异步概述
同步：
一个人同一时间只能做一件事情,只有一件事情做完，才能做另外一件事情。
落实到代码中，就是上一行代码执行完成后，才能执行下一行代码，即代码逐行执行。

```javascript
console. log ('before') ;
console. log ('after') ;
```
异步：
一个人一件事情做了一半，转而去做其他事情，当其他事情做完以后，再回过头来继续做之前未完成的事情。

落实到代码上，就是异步代码虽然需要花费时间去执行，但程序不会等待异步代码执行完成后再继续执行后续代码，而是直接执行后续代码，当后续代码执行完成后再回头看异步代码是否返回结果，如果已有返回结果，再调用事先准备好的回调函数处理异步代码执行的结果。

```javascript
console.log('before');
setTimeout(
	() =>{ console.log ('last') ;
} , 2000);
console.log ('after');
```
验证代码如下：
```javascript
var xhr = new XMLHttpRequest();
xhr.open('get','http://localhost:3000/first');
xhr.send();
xhr.onload = function() {
    console.log('2');
    console.log(xhr.responseText);
}
console.log('1');
```
执行结果如图：
控制台先输出1，再输出2.
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/b52e648e9689430c80e1d39362e923f0.png)
## 3.2 Ajax 封装
问题:发送一次请求代码过多，发送多次请求代码冗余且重复。
解决方案:将请求代码封装到函数中，发请求时调用函数即可。
## 3.2.1 封装Ajax初始化、发送请求和完成后的处理函数
封装函数：

```javascript
function ajax(options) {
	// 创建ajax 对象
	var xhr = new XMLHttpRequest();
	// 拼接请求参数的变量
	var params = '';
	// 循环用户传递进来的对象格式的参数
	for (var attr in options.data) {
	    params += attr + '=' + options.data[attr] + '&';
	}
	// 将最后的‘&’截掉
	params = params.substr(0, params.length - 1);
	if (options.type == 'get') {
	    options.url = options.url + '?' + params;
	}
	// 配置ajax 对象
	xhr.open(options.type, options.url);
	
	// 发送请求
	if (options.type == 'post') {
	    // 用户希望的向服务器端传递的请求参数的类型
	    var contentType = options.header['Content-Type'];
	    xhr.setRequestHeader('Content-Type', contentType);
	    if (contentType == 'application/json') {
	        // 向服务器传递JSON数据格式的参数
	        // 向服务器传递的必须是字符串类型，用JSON.stringify()方法转换成字符串
	        xhr.send(JSON.stringify(options.data));
	    } else {
	        // 向服务器传递普通数据格式的参数
	        xhr.send(params);
	    }
	} else {
	    xhr.send();
	}
	
	xhr.onload = function () {
	    if (xhr.status == 200) {
	        // 当http状态码等于200的时候，请求成功
	        // 调用处理成功情况的函数
	        options.sucess(xhr.responseText), xhr;
	    } else {
	        // 请求失败
	        options.error(xhr.responseText, xhr);
	    }
	}
	}
```
调用函数：

```javascript
// 调用ajax 函数
ajax({
    // 请求方式
    type: 'get',
    // 请求地址
    url: "http://localhost:3000/first",
    data: {
        name: 'zs',
        age: 10
    },
    header: {
        // Content-Type带了中横线，如果不是字符串的话，就不合法
        'Content-Type': 'application/json'
    },
    // 接收完服务器响应数据后的处理函数
    sucess: function (data) {
        console.log('这里是sucess函数' + data);
    },
    error: function (data, xhr) {
        console.log('这里是error函数' + data);
        console.log(xhr);
    }
})
```
## 3.2.2 封装请求完成后的处理函数扩展
客户端请求成功之后，服务器一般将json数据作为响应内容返回客户端，客户端拿到的是json对象的字符串。使用之前需要将json对象的字符串转换为字符串
1.判断是否请求成功
在`xhr.onload()`方法中进行判断http状态码`xhr.status`是否等于200。

```javascript
xhr.onload = function () {
	if (xhr.status == 200) {
	    // 当http状态码等于200的时候，请求成功
	    // 调用处理成功情况的函数
	    // 请求成功之后，服务器一般返回的是json数据作为响应内容，客户端拿到的是json对象的字符串
	    // 使用之前需要将json对象的字符串转换为字符串
	    // 1.判断服务器返回的是json数据的字符串还是普通的字符串
	    defaults.sucess(responseText, xhr);
	} else {
	    // 请求失败
	    defaults.error(responseText, xhr);
	}
	}
```

2.在`xhr.onload()`方法中，使用`xhr.getResponseHeader('Content-Type')方法，`判断服务器返回的数据，是json数据的字符串还是普通的字符串，封装将拿到的字符串转换成json对象方法：

```javascript
xhr.onload = function () {
     // 获取响应头中的信息
     var contentType = (xhr.getResponseHeader('Content-Type'));
     // 如果包含'application/json'，则传递的是json对象
     if (contentType.includes('application/json')) {
         // 将json字符串转换成json对象
         responseText = JSON.parse(responseText);
     }
```

3.设置默认值
在函数中，设置defaults对象存储默认值，使用`Object.assign()`方法，判断options对象的值是否传递给函数，传递了则覆盖defaults对象中的值；否则，使用defaults对象中的值。
```javascript
// 存储默认值
var defaults = {
      type: 'get',
      url: '',
      data: {},
      header: {
          'Content-Type': 'application/x-www-form-urlencoded'
      },
      success: function () { },
      error: function () { }
  };
  //使用options对象中的属性覆盖defaults对象中的属性
  // 如果传递了值的话，就覆盖defaults对象中的值；
  // 否则就使用defaults中的值
  Object.assign(defaults,options);
```
# 4.模板引擎
##  4.1模板引擎概述
作用：使用模板引擎提供的模板语法，可以将数据和HTML拼接起来。
官方地址: https://aui.github.io/art-template/zh-cn/index.html

##  4.2 模板引擎的下载
1.下载 `art-template` 模板引擎库文件
官方网站中，选择“Docs”->“安装”，在页面的“template-web.js”处鼠标右键，文件“另存为“->存储到本地的项目中。
![在这里插入图片描述](https://img-blog.csdnimg.cn/b8c1569b63464041b660dfaf0fa9dffc.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzMzMzkwNzAw,size_16,color_FFFFFF,t_70)
##  4.3 使用步骤
1. 在HTML页面中引入库文件。
2. 准备`art-template`模板 。
	- （由于客户端不具备文件读取的能力，所以在客户端，模板不是一个单独的文件，就是当前的html文件中的代码片段，需要被包裹在`script`标签内）
	- 设置模板的id和type
	- 通过模板语法告诉模板引擎，数据和html字符串要如何拼接
3. 使用`template()方法`，将模板和数据拼接成html字符串。
	- 引入模板引擎的库文件后，全局作用域下就可以使用`template()方法`
4. 将拼接好的html字符串添加到页面中。


示例代码如下：
```html
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  
  <!-- 1.在HTML页面中引入库文件 -->
  <script src="./js/template-web.js"></script>
</head>
<body>
  <!-- dom元素 -->
  <div id="container"></div>
  
  <!-- 2.准备`art-template`模板  -->
  <!-- 为了书写HTML代码片段，将type设置为`text/html`，语法高亮正确。-->
  <!--`id属性`是当前模板的唯一标识，用来区分其他模板 -->
  <script id="tpl" type="text/html">
    <!-- 通过模板语法告诉模板引擎，数据和HTML字符串如何拼接 -->
    <div id="container">{{ username }}{{age}}</div>
  </script>

  <script>
    // 3.使用`template()方法`，将模板和数据拼接成html字符串
    // 参数1：模板id;参数2：数据;返回的变量是拼接好的html字符串
    var html = template ('tpl', {username : 'zhangsan ', age: '20'});
    
    // 4.将拼接好的html字符串添加到页面中
    document.getElementById ('container').innerHTML= html;
  </script>
```
# 5.案例
## 5.1 案例1：验证邮箱地址唯一性
1.获取文本框并为其添加离开焦点事件
2.离开焦点时，检测用户输入的邮箱地址是否符合规则。
3.如果不符合规则，阻止程序向下执行并给出提示信息
4.向服务器端发送请求，检测邮箱地址是否被别人注册
5.根据服务器端返回值决定客户端显示何种提示信息
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/74108c0313374625a6278b0b7d52674b.png)
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/bacac22cde034035aa9c29a8c44cf086.png)