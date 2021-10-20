视频地址：https://www.bilibili.com/video/BV15P4y1t7k9?p=10&spm_id_from=pageDriver
> 目标：
> 能够基于Vue初始化项目
> 能够基于Vue技术栈进行项目开发
> 能够使用Vue的第三方组件进行项目开发
> 能够说出前后端分离的开发模式



![在这里插入图片描述](https://img-blog.csdnimg.cn/9c9f0f70afbf4697b5eb7fb3b7c6ace0.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_14,color_FFFFFF,t_70,g_se,x_16)
# 1.项目概述
## 1.1 电商项目基本业务概述
根据不同的应用场景，电商系统一般都提供了PC端、移动APP、移动Web、微信小程序等多种终端访问方式。

![在这里插入图片描述](https://img-blog.csdnimg.cn/69c3ea133f83456e9df7084f36784db7.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_17,color_FFFFFF,t_70,g_se,x_16)
## 1.2 电商后台管理系统的功能
电商后台管理系统用于管理用户账号、商品分类、商品信息、订单、数据统计等业务功能。
![在这里插入图片描述](https://gitee.com/jingw1/cloud-image/raw/master/img/761351562ee2419497f89d57cfbe89d1.png)

## 1.3 电商后台管理系统的开发模式(前后端分离)
电商后台管理系统整体采用前后端分离的开发模式，其中前端项目是**基于Vue技术栈的SPA项目**。
![在这里插入图片描述](https://img-blog.csdnimg.cn/fec629fa63014e818e44d8792a352016.png)

## 1.4 电商后台管理系统的技术选型
1.前端项目技术栈
vue
vue-router
Element-UI
Axios
Echarts

2.后端项目技术栈
Node.js
Expiess
Jwt
Mysql
sequelize

# 2 项目初始化
## 2.1前端项目初始化步骤
1.安装vue 脚手架
2.通过vue脚手架创建项目
3.配置vue路由
4.配置Element-UI组件库
5.配置axios 库 （依赖->axios)
6.初始化 git远程仓库
7.将本地项目托管到Github或码云中（注册后需要设置公钥）

文件中的字符串，就是我的公钥。

在码云的安全设置中，填写SSH公钥

![image-20211018170004288](https://i.loli.net/2021/10/18/ht37DjkQfAsad45.png)

新建仓库，注意取消勾选生成初始化文件。

跳转的页面如下图，即为OK。

![image-20211019101544086](https://i.loli.net/2021/10/19/a6CVhi41yLoFwpO.png)

按图进行Git全局设置

`git add .`和`git commit -m"add files"`提交到本地仓库

输入“已有仓库？”的命令，可查看gitee的项目状态

![image-20211019102359935](https://i.loli.net/2021/10/19/JaNnTMe2S4hUsOG.png)

## 2.2后台项目的环境安装配置
①安装 MySQL数据库

执行脚本

![image-20211019103246121](https://i.loli.net/2021/10/19/1hVKiz2LdpykbJQ.png)

![image-20211019103343027](https://i.loli.net/2021/10/19/CK7mXJPktI4lWOi.png)

验证是否导入数据成功：

根据下图进行点击，查看打开的数据库目录下是否有mydb文件夹，文件夹内是否有还原的文件。

![image-20211019103409629](https://i.loli.net/2021/10/19/qHCmOgzAdsVSYIi.png)

②安装Node.js坏境



③配置项目相关信息

先运行 npm install 安装依赖包：shift+鼠标右键，打开PowerShell窗口，输入`npm install` 命令



④启动项目

cls 清屏

`node .\app.js` 把API接口项目跑起来

正常运行起来的界面如图：

![image-20211019104102113](https://i.loli.net/2021/10/19/yK4bFXcqjgw6ntu.png)

> 一种报错：
>
> 特征：查看phpStudy，显示“端口被占用”。
>
> 解决方法：开始-运行-cmd， 输入 `netstat -ano`， 看第一列，后面的就是端口,找到3306 ,记住对应的PID
>
> 然后打开任务管理器查看 -> 选择列 -> 勾上 PID(进程标识符) -> 确定 
>
> 在任务管理器找到刚才的PID的进程，查看是什么程序占用了端口，把它关闭
>
> 再重新启动mysql就不会报端口被占用的错误了⑤使用Postman测试后台项目接口是否正常



# 3.登录/退出功能
## 3.1登录概述
1.登录业务流程
①在登录页面输入用户名和密码
②调用后台接口进行验证
③通过验证之后，根据后台的响应状态跳转到项目主页

2.登录业务的相关技术点

http是无状态的，以下三种方式记录状态：

- 通过cookie在客户端记录状态
- 通过session在服务器端记录状态（前端与服务器之间不存在跨域问题，推荐使用cookie和session）
- 通过token方式维持状态（存在跨域问题，推荐使用）
## 3.2登录—token原理分析
![在这里插入图片描述](https://img-blog.csdnimg.cn/de51fb057fbb470188ea5a647702063c.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_19,color_FFFFFF,t_70,g_se,x_16)
## 3.3登录功能实现

### 1.登录页面的布局

通过Element-UI组件实现布局

- el-form
- el-form-item
- el-input
- el-button
- 字体图标

![在这里插入图片描述](https://img-blog.csdnimg.cn/fe81d1bd9a30400094aee549de97c7ae.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_12,color_FFFFFF,t_70,g_se,x_16)

visual code中打开终端：

先用`git status`查看当前文件的状态，是否干净。

建议：开发新功能时，建议将功能都放到一个新的分支上进行开发，开发完毕后再把这个分支合并到mastar上。

`git checkout -b login`  创建子分支，名为login，并切换至该分支
`git branch`  查看当前项目的所有分支，其中打*的是当前分支。

运行项目：

![image-20211019113522422](https://i.loli.net/2021/10/19/8fAQc9jZsUoraJC.png)



查看main.js入口文件





#### 实现路由重定向

```
import Vue from 'vue'
import VueRouter from 'vue-router'
// import Login from '../components/Login.vue'
const Login = () => import('../components/Login.vue')

Vue.use(VueRouter)

const routes = [
  {
    path: '/',
    redirect: '/login'
  },
  {
    path: '/login',
    component: Login
  }
]

const router = new VueRouter({
  routes
})

export default router
```

script中的lang="less"选项，设置可以解析less的语法。scoped选项，控制节点的样式生效的区间 该节点的样式只在当前组件内生效，去掉则会全局生效。
因为设置了lang="less"，所以需要①安装开发依赖`less-loader`，②安装`less`（less-loader内部依赖于less）
![在这里插入图片描述](https://img-blog.csdnimg.cn/7fd46a7616534b2cbb7c7ffa9c5ba1a6.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_20,color_FFFFFF,t_70,g_se,x_16)
![在这里插入图片描述](https://img-blog.csdnimg.cn/d22f7d4c5de349988e1651391faeb04b.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA5Luy5aSP5aSc55qE5byA5Zy6,size_20,color_FFFFFF,t_70,g_se,x_16)

使登录盒子在页面的正中间

```css
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%,-50%);// 移动自身一半的距离
```

#### 在页面上添加表单

![image-20211019162047883](https://i.loli.net/2021/10/19/ysQVcRPhWOCMjkK.png)

![image-20211019162450976](https://i.loli.net/2021/10/19/S62zYRJTBaDKobN.png)

复制代码到本项目

用到哪些组件，就需要在plugins文件夹里的element.js文件中，按需导入对应的组件，并注册。

![image-20211019163025399](https://i.loli.net/2021/10/19/2l5COeFiABxrdh4.png)

#### 设置图标

第三方图库-阿里

![image-20211019171953690](https://i.loli.net/2021/10/19/8VtkjrzBcEIlyZM.png)

在main.js文件中导入iconfont.css文件

设置属性值

### 实现表单数据验证

1.为`el-form`通过属性绑定，指定一个`rules`校验对象

2.`data`数据中定义这个校验对象，其中每个属性都是一个校验规则

3.为不同的表单item项通过`prop`属性，指定不同的校验规则，进行表单的验证。

这里有一个疑问：:model在这里的用处是什么？

![image-20211020145427377](https://i.loli.net/2021/10/20/xKCwhq6cOjAXszb.png)

![image-20211020145456236](https://i.loli.net/2021/10/20/sFUquSjh8DJI9Y1.png)



> v-model是vue.js中内置的双向数据绑定指令，
> 	用于表单控件以外的标签是不起作用的
> 	(即只对表单控件标签的数据双向绑定有效)。
>
> :model相当于v-bind:model的缩写，
> 	v-bind动态绑定指令，默认情况下标签自带属性的值是固定的，
> 	这种只是将父组件的数据传递到了子组件，并没有实现子组件和父组件数据的双向绑定。
> 	当然引用类型除外，子组件改变引用类型的数据的话，父组件也会改变的。
>
> ```
> <input v-model="message"> =
> <input v-bind:value="message" v-on:input="message = $event.target.value" />
> ```
>
> 上面这个例子中，v-bind:value="message" 只是将message变量的值赋给了input的value，
> 并没有双向绑定，再此声明一下以防混淆

form表单的model属性和v-model没啥关系，只是一个数据对象。

![image-20211020145249584](https://i.loli.net/2021/10/20/lca92Mx5FXREZdD.png)

:model暂时没有啥用处，去掉也不影响表单item的数据双向绑定。==可能是要将数据传递到子组件==

