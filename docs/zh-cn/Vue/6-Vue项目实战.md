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
> ![image-20211211110345593](https://s2.loli.net/2021/12/11/maLTGFbHOBhcrNy.png)
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

### 实现表单重置功能

3.路由导航守卫控制访问权限
如果用户没有登录，但是直接通过URL访问特定页面，需要重新导航到登录页面。

```js
// 为 路由对象 添加 beforeEach 导航守卫
router.beforeEach((to, from, next)=>{
  //如果用户访问的登录页,直接放行
  if (to.path == '/login') return next()
  //从sessionstorage中获取到保存的token值
  const tokenstr = window.sessionstorage.getItem ( 'token ' )
  //没有token，强制跳转到登录页
  if ( !tokenstr) return next('/login' )next()
})
```

3.4退出
退出功能实现原理
基于token 的方式实现退出比较简单，只需要销毁本地的 token 即可。这样，后续的请求就不会携带token，必须重新登录生成一个新的 token之后才可以访问页面。

```js
//清空token
window.sessionStorage.clear()

//编程式导航 -- 跳转到登录页
this.$router.push ('/login')

```

处理项目中的eslint语法报错问题

1.在项目的根目录下新建`.prettierrc`文件

2.在文件中进行相应的配置

```js
{
// 禁用默认加冒号
"semi": false,
  // 单引号来表示字符串
"singleQuote": true
}
```

3.某些报错属于不想要eslint检查的情况，如下的`在函数的小括号前未添加空格`.

复制报错信息中的浅灰色部分，在配置文件`.eslintrc.js`中禁用 -- 置为`0`

![image-20211022092901026](https://i.loli.net/2021/10/22/LMFE7ScoKmP98yJ.png)

![image-20211022093113226](https://i.loli.net/2021/10/22/Mz39inlSuroZQN8.png)

将本地代码提交到github上

`git status`查看文件状态

`git branch`查看此时所处的分支

`git add .`将所有的文件提交到暂存区

`git commit -m"XXX"`暂存区中所有代码提交到本地仓库

`git checkout main` 切换到main分支

`git merge login` login分支中的代码合并到main分支

`git push`本地的master提交到github上



如何将login分支推送到github

`git checkout login`

`git push -u origin login` 将本地的login分支提交到github（第一次需要用 -u）

# 4.主页布局

## 侧边栏

### 4.3通过接口获取菜单数据

通过axios请求拦截器添加token，保证拥有获取数据的权限。

```js
// axios请求拦截
axios.interceptors.request.use(config => {
  //  config 是请求对象
  // 为请求头对象 添加Token验证的Authorization字段
  config.headers.Authorization = window.sessionStorage.getItem ( 'token')
  // 固定写法，在最后必须return config
  return config
})

```

导航菜单

<el-menu> 

<el-submenu>

<el-menu-item>

其中，index 是 sub-menu和 menu-item 的唯一标志





==如果不加`：`，二级菜单会同时显示为蓝色。不知道为啥==

![image-20211025111337669](https://i.loli.net/2021/10/25/Qkx1OHUZBmIE385.png)

# 用户列表

## 通过路由的形式展示用户列表组件

## 列表在sessionStorage中保存左侧菜单的激活状态

## 绘制用户列表组件的基础布局结构

![image-20211025154929484](https://i.loli.net/2021/10/25/HCNapAMVI5dR2vQ.png)

**1.面包屑导航**

复制粘贴element-ui中面包屑的代码

在plugins->element.js中，进行组件的导入，并调用vue对象的方法，全局注册：`Vue.use(组件名)`



**2.主题区域**

复制粘贴el-card中代码，添加卡片区域

在plugins->element.js中，进行组件的导入，并调用vue对象的方法，全局注册：`Vue.use(组件名)`

在global.css中使用类名选择器，为.el-breadcrumb设置margin-bottom间距和字体

在global.css中,调整卡片的阴影

```css
box-shadow: 0 1px 1px rgba(0,0,0,0.15) !important
```

​	**①搜索和添加用户区域**

​	选择复合型输入框的第三种，复制粘贴代码，删除el-select标签的代码，和没有用到的属性。

![image-20211026143212880](https://i.loli.net/2021/10/26/mRdtxbzWuwToA39.png)

​		设置固定宽度：利用element-ui中的栅格系统 -- layout设置

![image-20211026143620471](https://i.loli.net/2021/10/26/Vdjx4GgYeLXwr7S.png)

复制粘贴代码	

在plugins->element.js中，进行组件的导入，并调用vue对象的方法，全局注册：`Vue.use(组件名)`

el-row实现栅格布局，el-row里有很多列 el-col。

el-row的gutter属性，设置栅格间隔，值为任意数字。

el-col的span属性，设置栅格占据的列数。设置为24则占满了。



②用户列表

​	③分页的页码条

## 获取用户列表数据



## 使用el-table组件渲染基本的用户列表

el-table表格，:data属性设置数据源，border属性添加边框，stripe属性设置隔行变色。

el-table-column表格列，label设置列名，prop设置数据源中的key值。



为表格添加索引列

```html
<el-table-column type="index"></el-table-column>
```

想要索引列的列名为`#`，可以添加` label="#" `

## 自定义状态列的显示效果

同时指定prop和作用域插槽，prop会被==作用域插槽==覆盖，prop不生效。

```html
<el-table-column label="状态" prop="mg_state">
  <template slot-scope="scope">
    {{scope.row}}
    <el-switch v-model="scope.row.mg_state">
    </el-switch>
  </template>
</el-table-column>
```

## 通过作用域插槽渲染操作列

```html
<el-table-column label="操作" width="180px">
  <template slot-scope="scope">
    <!-- 修改 -->
    <el-button type="primary" icon="el-icon-edit" size="mini"></el-button>
    <!-- 删除 -->
    <el-button type="danger" icon="el-icon-delete" size="mini"></el-button>
    <!-- 分配角色 -->
    <el-tooltip effect="dark" content="分配角色" placement="top" :enterable="false">
      <el-button type="warning" icon="el-icon-setting" size="mini"></el-button>
    </el-tooltip>
  </template>
</el-table-column>
```

**文字提示**

el-tooltip组件的enterable属性设置false，可以解决文字提示遮挡住其他按钮的情况。

==由于false是bool值，所以要加`:`==

```html
<!-- 分配角色 -->
<el-tooltip effect="dark" content="分配角色" placement="top" :enterable="false">
  <el-button type="warning" icon="el-icon-setting" size="mini"></el-button>
</el-tooltip>
```

## 实现分页效果

layout属性，控制在页面上显示的功能

```html
<el-pagination 
@size-change="handleSizeChange" 
@current-change="handleCurrentChange" 
:current-page="queryInfo.pagenum"
:page-sizes="[1,2,10, 20, 50,100, 200, 300, 400]"
:page-size="queryInfo.pagesize"
layout="total, sizes, prev, pager, next, jumper"
:total="total">
</el-pagination>
```

```js
methods: {
    // 监听 pagesize 改变的事件
    handleSizeChange(newSize) {
      console.log(newSize);
      this.queryInfo.pagesize = newSize
      this.getUserList()
    },
    // 监听页码值改变的事件
    handleCurrentChange(newPage) {
      console.log(newPage);
      this.queryInfo.pagenum = newPage
      this.getUserList()
    }
  }
```

## 修改用户状态

### el-switch 的事件

| 事件名称 | 说明                            | 回调参数   |
| :------- | :------------------------------ | :--------- |
| change   | switch 状态发生变化时的回调函数 | 新状态的值 |

## 实现搜索功能

自定义手机号的校验规则

```html
<script>
export default {
  data() {
    // 验证手机的校验规则
    var checkMobile = (rule, value, cb) => {
   		// 定义正则表达式
      const regMobile = /^(0|86|17951)?(13[0-9]|15[0123456789]|17[678]|18[0-9]|14[57])[0-9]{8}$/
      // 调用test 检验值是否合法
      if (regMobile.test(value)) {
        return cb()
      }
      cb(new Error('请输入合法的手机号'))
    }
    return {
      ...
      // 添加表单的验证规则对象
      addFormRules: {
        username: [
          { required: true, message: '请输入用户名', trigger: 'blur' }, 
          { 
            min: 3, 
            max: 10, 
            message: '用户名的长度在3~10个字符之间',
            trigger: 'blur' 
          }
        ],
        password: [
          { required: true, message: '请输入密码', trigger: 'blur' }, { min: 6, max: 15, message: 
            '密码的长度在6~15个字符之间', trigger: 'blur' }
        ],
        email: [
           { required: true, message: '请输入邮箱', trigger: 'blur' },
           { type: 'email', message: '请输入正确的邮箱地址', trigger: ['blur','change']}
        ],
        mobile: [
        	{ required: true, message: '请输入邮箱', trigger: 'blur' },
          // validator 属性指定具体校验规则， trigger指定校验时机
          { validator: checkMobile, trigger: 'blur'}
        ]
      },
      
    }
  },
  created() {
    
  },
  methods: {
  }
</script>
```

## 删除用户

弹框询问用户是否确认删除数据

1.单独引入`element-ui`中的`MessageBox`

2.进行全局挂载，比较特殊，不使用use函数

```javascript
Vue.prototype.$confirm = MessageBox.confirm;
```

3.为删除按钮绑定一个删除事件`removeUserById`

```html
<el-table-column label="操作" width="180px">
          <template slot-scope="scope">
            <!-- 修改 -->
            <el-button type="primary" icon="el-icon-edit" size="mini" @click="showEditDialog(scope.row.id)"></el-button>
            <!-- 删除 -->
            <el-button type="danger" icon="el-icon-delete" size="mini" @click="removeUserById(scope.row.id)"></el-button>
            <!-- 分配角色 -->
            <el-tooltip effect="dark" content="分配角色" placement="top" :enterable="false">
              <el-button type="warning" icon="el-icon-setting" size="mini"></el-button>
            </el-tooltip>
          </template>
        </el-table-column>
```

4.在行为区域新增该处理函数

`this.$confirm()`返回值是一个promise，使用await和async进行优化。

打印优化后返回的结果，如果用户确认了删除，返回的是文本confirm；

如果用户取消了删除，会触发$confirm中的一个错误。

可以用.catch()接收错误，此时取消删除，返回的是文本cancel。

```javascript
// 根据id删除对应的用户信息
async removeUserById(id) {
  // 弹框询问用户是否删除数据
  const confirmResult = await this.$confirm('此操作将永久删除该用户, 是否继续?', '提示', {
    confirmButtonText: '确定',
    cancelButtonText: '取消',
    type: 'warning'
  }).catch(err => err)
  // 如果用户确认了删除，则返回值为字符串 confirm
  // 如果用户取消了删除，则返回值为字符串 cancel
  // console.log(confirmResult);
  if(confirmResult !== 'confirm') {
    return this.$message.info('已取消删除！')
  }
  // 用户确认删除
  // console.log('确认了删除！');
  const {data: res} = await this.$http.delete('users/' + id)
  if(res.meta.status !== 200) {
    return this.$message.error('删除用户失败！')
  }
  this.$message.success('删除用户成功！')
  this.getUserList()
```



# 权限列表

创建rights分支并推送到云端

```bash
git checkout -b rights
git push -u origin rights
```

==为啥welcome和users都是home的子组件呢？==

![image-20211105102417249](https://i.loli.net/2021/11/05/RBSJctvEOK6Z8Dj.png)

**通过路由展示权限列表组件**

1.在power文件夹下，新增Rights.vue文件

2.router文件夹下的index.js文件中，如下：

其中，path字段的值由点击导航栏菜单后，跳转的链接决定。==这个跳转链接好像是由Home组件决定==

![image-20211105162109942](https://i.loli.net/2021/11/05/IY9TzehSwcAF4Rl.png)

**绘制面包屑导航和卡片视图**

![image-20211105162909903](https://i.loli.net/2021/11/05/e17hCQ5UzEX9RZp.png)

# 角色列表

![image-20211106214031369](C:/Users/12141/AppData/Roaming/Typora/typora-user-images/image-20211106214031369.png)





## 删除角色下指定权限

API接口文档中相关内容

![image-20211107111923423](C:/Users/12141/AppData/Roaming/Typora/typora-user-images/image-20211107111923423.png)

```js
// 根据id删除对应的权限
async removeRightById(role, rightId) {
  // 弹框提示用户是否要删除
  const confirmResult = await this.$confirm('此操作将永久删除该文件, 是否继续?', '提示', 
                                            {
    confirmButtonText: '确定',
    cancelButtonText: '取消',
    type: 'warning'
  }
                                           ).catch(err => err)

  if(confirmResult !== 'confirm') {
    return this.$message.info('取消了删除')
  }
  // 删除角色指定权限
  // const {data: res} = await this.$http.delete('roles/' + role.id + '/rights/' + rightId)
  // 模板字符串进行字符串的拼接方式
  const {data: res} = await this.$http.delete(`roles/${role.id}/rights/${rightId}`)
  if(res.meta.status !== 200) {
    console.log(res);
    return this.$message.error('删除权限失败！')
  }
  // 会发生页面的重新渲染
  // this.getRolesList() 
  // 这样就不会有关上展开行的问题
  role.children = res.data
},
```

## el-tree树形控件展示权限列表

按需导入el-tree组件，并进行全局注册

el-tree组件，绑定data值为data对象，绑定属性props值为“defaultProps”

在data中设置defaultProps对象，children属性为子节点的字段名，label为显示文字的字段名。

设置show-checkbox，显示多选框，设置el-tree的node-key唯一标识为data对象中的唯一标识。只要选中了节点，就选中了该id值。

设置default-expand-all属性，默认展开所有节点



```html
<template>
  <div>
  	<!-- 分配权限的对话框 -->
    <el-dialog
      title="分配权限"
      :visible.sync="setRightDialogVisible"
      width="50%">
      <el-tree show-checkbox :data="rightsList" :props="defaultProps" node-key="id" default-expand-all :default-checked-keys="defKeys"></el-tree>
      <span slot="footer" class="dialog-footer">
        <el-button @click="setRightDialogVisible = false">取 消</el-button>
        <el-button type="primary" @click="setRightDialogVisible = false">确 定</el-button>
      </span>
    </el-dialog>
  </div>
</template>

<script>
export default {
  data() {
    return {
      // 所有角色列表数据
      rolesList: [],
      // 控制分配权限对话框的显示与隐藏
      setRightDialogVisible : false,
      rightsList:[],
      // 树形控件的属性绑定对象
      defaultProps: {
        children: 'children',
        label: 'authName'
      },
      // 默认选中的节点Id值数组
      defKeys: [105, 116]
    }
  },
  created() {
    this.getRolesList()
  },
  methods: {
    // 展示分配权限的对话框
    async showSetRightDialog() {
      // 获取所有权限列表
      const {data: res} = await this.$http.get('rights/tree')
      if(res.meta.status !== 200) {
        return this.$message.error('获取权限列表失败')
      }
      // 获取到的权限数据，保存到data中
      this.rightsList = res.data
      console.log(this.rolesList);
      // 对话框设为可视
      this.setRightDialogVisible = true
    }
  }
```





### 将已有权限实现默认勾选

`:default-checked-keys="defKeys"`，设置默认勾选的节点的key的数组，绑定到数组defKeys上。

复制数组的名字，进行简单的定义

```javascript
<script>
export default {
  data() {
    return {
      
      // 默认选中的节点Id值数组
      defKeys: [105, 116]
    }
  }
</script>
```



forEach() 方法对数组的每个元素执行一次提供的函数。

```
var array = ['a', 'b', 'c'];

array.forEach(function(element) {
  console.log(element);
});

```

输出为：
a;
b;
c;

输出为：
a;
b;
c;

渲染分配角色的对话框并请求角色列表数据

![image-20211112150245725](https://i.loli.net/2021/11/12/JsmEDG68HbnNByK.png)

## 商品管理

### 商品分类

![image-20211112192604886](https://i.loli.net/2021/11/12/uZnC8IoRiahwvxb.png)

使用第三方插件vue-table-with-tree-grid 0.2.4 实现属性的table表格

1.安装依赖

![image-20211113130953045](https://i.loli.net/2021/11/13/OKbJfk7INADqvZ2.png)

![image-20211113131308289](https://i.loli.net/2021/11/13/Bv6S2FQjZyYXUJd.png)

点击查看详情，可以获取该插件的api和使用方法和使用代码。

![image-20211113131409291](https://i.loli.net/2021/11/13/UMOytaTzLHW1SYN.png)

点击代码中的example，对应api，学习用法

![image-20211113132138522](https://i.loli.net/2021/11/13/CmNDB85FRbhX3kg.png)

![image-20211113132346308](https://i.loli.net/2021/11/13/d6nDmRiVK38UouH.png)2.在项目中将插件加载进来，并进行注册

![image-20211113131550947](https://i.loli.net/2021/11/13/n91cOHVlUrmNxou.png)

main.js文件中

```javascript
// 将插件导入到项目中
import TreeTable from 'vue-table-with-tree-grid'
// 注册为全局可用的组件
Vue.component('tree-table', TreeTable)
```



![image-20211127104539814](C:/Users/12141/AppData/Roaming/Typora/typora-user-images/image-20211127104539814.png)



![image-20211127125834792](C:/Users/12141/AppData/Roaming/Typora/typora-user-images/image-20211128214706926.png)



### 分类参数

注意：空字符串用split() 方法把一个字符串分割成字符串数组时，得到的是一个长度为1的数组。

![image-20211203212436779](https://i.loli.net/2021/12/03/Atdm98OiHPI2nXu.png)

没有参数时，会显示内容为空的tag。

![image-20211203212607269](https://i.loli.net/2021/12/03/d2GJjMY9FRfHyEr.png)



### 商品列表

#### 通过路由加载商品列表组件

1. 新建组件List.vue，编写基本结构
2. 路由文件导入组件List.vue，将其注册为Home的子路由
3. 

![image-20211205123656166](https://s2.loli.net/2021/12/05/wdbxPi5UyFuK3js.png)



### 商品添加

![image-20211210103611116](C:/Users/12141/AppData/Roaming/Typora/typora-user-images/image-20211210103611116.png)



将一个长得像数字的字符串，转换成数字类型，最简单的方法：减0





#### 获取动态参数列表数据

通过`Tabs 标签页` 的事件`tab-click`，监听tab被选中的事件。

![image-20211211113810556](https://s2.loli.net/2021/12/11/TnZpqWX6xIbjtg1.png)



#### 安装并配置vue-quill-editor

![image-20211215151342388](https://s2.loli.net/2021/12/15/NpxXHse2Vf54Gwi.png)



![image-20211215152902048](https://s2.loli.net/2021/12/15/9mnlJj3kHpgqzi5.png)

安装插件

![image-20211215153222108](https://s2.loli.net/2021/12/15/6U2eimPpWuXhL9A.png)

![image-20211215153834405](https://s2.loli.net/2021/12/15/3J1ZrbNumYjLXPx.png)

导入包，导入编译器对应的样式表，用`vue.use`方法注册为全局可用的组件。

#### 实现表单数据的预验证

在add函数中，找到表单的引用对象，调用validate函数，从该函数的回调函数中，拿到验证结果valid，判断是否合法，如果经过！取非之后，为true，则不合法，直接return错误消息；没有return，则执行添加的业务逻辑。

![image-20211217130323667](https://s2.loli.net/2021/12/17/91oxFulNeDTAHjh.png)

## 订单管理

![image-20211220123247604](https://s2.loli.net/2021/12/20/vjVBugLbFNHnY4M.png)

## 数据统计

![image-20211224095829829](https://s2.loli.net/2021/12/24/l6dnToACRxKpDsX.png)

![image-20211224100115719](https://s2.loli.net/2021/12/24/sbg6PXe4fVpLS2q.png)

![image-20211224100647334](C:/Users/12141/AppData/Roaming/Typora/typora-user-images/image-20211224100647334.png)



# 项目优化上线

### 1.1项目优化策略

1.生成打包报告
2.第三方库启用CDN
3.element-UI组件按需加载
4.路由懒加载
5.首页内容定制

通过nprogress添加进度条效果

如果代码格式化工具与eslint代码报错冲突了： 

![image-20211228134825731](https://s2.loli.net/2021/12/28/bwzt1dgPK5lE3QB.png)

![image-20211228134859013](https://s2.loli.net/2021/12/28/xVi4QzhUg3kJGyr.png)

修改默认字长配置（80=>200）

![image-20211228133402043](https://s2.loli.net/2021/12/28/gIzMdOlFfX9A7wc.png)

百度搜索，移除所有console的代码的插件：

babel-plugin-transform-remove-console

![image-20211224170953800](https://s2.loli.net/2021/12/24/uU4qEXO69JG2wpB.png)



![image-20211228151209238](https://s2.loli.net/2021/12/28/wQA7tPnRe4zgFNC.png)

![](https://s2.loli.net/2021/12/28/gzGhjxi7OC9dYMv.png)

![image-20211228151835564](https://s2.loli.net/2021/12/28/T8SvEoRBrYtVUHN.png)

发布阶段的插件，使其在开发阶段不适用的解决方案：

![image-20211228132409639](https://s2.loli.net/2021/12/28/wvlCUX8EbhNZIiq.png)



#### 1.生成打包报告

打包时，为了直观地发现项目中存在的问题，可以在打包时生成报告。生成报告的方式有两种:
① 通过命令行参数的形式生成报告

```c
// 通过vue-cli的命令选项可以生成打包报告
// --report选项可以生成report.htm1以帮助分析包内容
vue-cli-service build --report
```

② 通过可视化的UI面板直接查看报告(**推荐**)
在可视化的UI面板中，通过**控制台**和**分析**面板，可以方便地看到项目中所存在的问题。



#### 2.通过vue.config.js 修改webpack的默认配置

通过vue-cli 3.0工具生成的项目，**默认隐藏了所有webpack的配置项**，目的是为了屏蔽项目的配置过程，让程序员把工作的重心，放到具体功能和业务逻辑的实现上

如果程序员有修改webpack默认配置的需求，可以在项目根目录中，按需创建vue.config,js这个配置文件，从而对项目的打包发布过程做自定义的配置（具体配置参考 https://cli.vuejs.org/zh/config/#vue-config-js).

```javascript
//  vue.config.js
// 这个文件中，应该导出一个包含了自定义配置选项的对象
module.exports = {
	// 选项...
}
```

#### 3.为开发模式与发布模式指定不同的打包入口

默认情况下，Vue项目的**开发模式**与**发布模式**，共用同一个打包的入口文件(即**src/main.js**)。为了将项目的开发过程与发布过程分离，我们可以为两种模式，各自指定打包的入口文件，即:
①开发模式的入口文件为**src/main-dev.js**
②发布模式的入口文件为**src/main-prod.js**

#### 4.configureWebpack和chainWebpack

在vue.config,js 导出的配置对象中，新增configureWebpack或 chainWebpack 节点，来自定义webpack的打包配置.
在这里，configureWebpack和chainWebpack的作用相同，唯一的区别就是它们修改webpack 配置的方式不同:

① chainWebpack 通过链式编程的形式，来修改默认的webpack配置

② configureWebpack通过操作对象的形式，来修改默认的webpack配置

两者具体的使用差异，可参考如下网址:
https://cli.vuejs.org/zh/guide/webpack.html#webpack-%E7%98%B8%E5%85%B3



#### 5.通过chainWebpack自定义打包入口

代码示例如下:

```javascript
module.exports = {
  chainwebpack: config => {
    config.when(process.env.NODE_ENV === 'production', config => {
      config.entry ('app').clear().add('./src/main-prod.js')
    })
    config.when(process.env.NODE_ENV === 'development', config =>{
      config.entry('app').clear().add('./src/main-dev.js')
    })
	}
}
```

#### 6.通过externals 加载外部CDN资源

默认情况下，通过import语法导入的第三方依赖包，最终会被打包合并到同一个文件中，从而导致打包成功后，单文件体积过大的问题。

为了解决上述问题，可以通过webpack的externals节点，来配置并加载外部的CDN资源。凡是声明在externals 中的第三方依赖包，都不会被打包。



![image-20211229123231937](https://s2.loli.net/2021/12/29/bnRmcsZlef21vq6.png)

#### 7.通过CDN优化ElementUI的打包

虽然在开发阶段，我们启用了element-ui组件的按需加载，尽可能的减少了打包的体积，但是那些被按需加载的组件，还是占用了较大的文件体积。此时，我们可以将element-ui中的组件，也通过CDN的形式来加载，这样能够进—步减小打包后的文件体积。
具体操作流程如下:
①在main-prod.js中，注释掉element-ui按需加载的代码
②在index.html的头部区域中，通过CDN加载 element-ui的js和css样式

```html
<!-- element-ui 的样式表文件-->
<link relm="stylesheet" href="https://cdn.staticfile.org/element-ui/2.8.2/theme-chalk/index.css"/>
<!-- element-ui的js文件-->
<script src="https://cdn.staticfile.org/element-ui/2.8.2/index.js"></script>
```



#### 9.路由懒加载

当打包构建项目时，JavaScript包会变得非常大，影响页面加载。如果我们能把不同路由对应的组件分割成不同的代码块，然后当路由被访问的时候才加载对应组件，这样就更加高效了。
具体需要3步:
① 安装@babel/plugin-syntax-dynamic-import包。
② 在babel.config.js配置文件中声明该插件。
③ 将路由改为按需加载的形式，示例代码如下:

```javascript
const Foo = () => import ( /* webpackchunkName: "group-foo" */ './Foo. vue')
const Bar = () => import ( /* webpackchunkName: "group-foo" */ './Bar.vue')
const Baz = () => import (/* webpackchunkName: "group-boo" */ './Baz.vue')


```

关于路由懒加载的详细文档，可参考如下链接;
https://router.vuejs.org/zh/guide/advanced/lazy-loading.html

## 2.项目上线



### 2.1项目上线相关配置

#### 1.通过node创建web服务器

创建node项目，并安装express，通过 express快速创建web服务器，将vue打包生成的dist文件夹，托管为静态资源即可，关键代码如下:

```javascript
const express = require ( " express")
// 创建web服务器
const app = express()
// 托管静态资源
app.use (express.static('./dist'))

//启动web服务器
app.listen (80,())=>{
console.log ( ' web server running at http:/ /127.0.0.1')))
```

#### 3.配置HTTPS服务

**为什么要启用HTTPS服务?**

- 传统的HTTP协议传输的数据都是明文，不安全
- 采用HTTPS协议对传输的数据进行了加密处理，可以防止数据被中间人窃取，使用更安全



**申请SSL证书(https://freessl.org)**

1. 进入 https://freessl.cn/官网，输入要申请的域名并选择品牌。
2. 输入自己的邮箱并选择相关选项。
3. 验证DNS(在域名管理后台添加TXT记录).
4. 验证通过之后，下载SSL证书（ full_chain.pem公钥; private.key私钥)。

![image-20211229161122843](https://s2.loli.net/2021/12/29/47maNSR8GLzqfWh.png)

![image-20211229161221101](https://s2.loli.net/2021/12/29/CrUleQZJMH74ijE.png)

**在后台项目中导入证书**

```javascript
const https = require('https') ;
const fs = require ('fs');
const options = {
  cert: fs.readFileSync('./full_chain.pem'),
  key: fs.readFileSync('/private.key')
}
https.createServer(options, app).listen (443);
```

#### 4.使用pm2管理应用

好处：不用每时每刻打开这个终端窗口了。

1. 在服务器中安装pm2: `npm i pm2 -g`
2. 启动项目: pm2 start 脚本 --name 自定义名称
3. 查看运行项目:pm2 ls
4. 重启项目: pm2 restart 自定义名称
5. 停止项目:pm2 stop 自定义名称
6. 删除项目:pm2 delete 自定义名称



![image-20211229165246720](https://s2.loli.net/2021/12/29/w1oGfpNzMQX2PYj.png)







