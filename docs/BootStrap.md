## 一、主要内容

![image-20210920162624037](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210920162624037.png)

## 二、BootStrap的安装和使用

# 移动WEB开发之响应式布局



> 视频地址：
>
> https://www.bilibili.com/video/BV1R7411s72K?p=7&spm_id_from=pageDriver
>
> **目录：**
>
> 响应式开发
> Bootstrap前端开发框架
> Bootstrap栅格系统
> 阿里百秀首页案例

## 1.响应式开发



### 1.1响应式开发原理

就是使用**媒体查询**针对不同宽度的设备进行布局和样式的设置，从而适配不同设备的目的。

![image-20210922005255176](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210922005255176.png)



### 1.2响应式布局容器

响应式需要一个父级做为布局容器,来配合子级元素来实现变化效果
原理就是在不同屏幕下，通过媒体查询来改变这个布局容器的大小，再改变里面子元素的排列方式和大小，从而实现不同屏幕下，看到不同的页面布局和样式变化。

**平时我们的响应式尺寸划分**
超小屏幕（手机，小于768px )：设置宽度为100%

小屏幕(（平板，大于等于768px)∶设置宽度为750px

中等屏幕（桌面显示器，大于等于992px ) :宽度设置为970px

大屏幕(大桌面显示器，大于等于1200px):宽度设设置为1170px

但是我们也可以根据实际情况自己定义划分



### 案例：响应式导航

当我们屏幕大于等于768像素，我们给布局容器container宽度为750px。
container里面包含8个小i盒子，每个盒子的宽度定为93.75px ( 750/8)，高度为30px，浮动一行显示当我们屏幕缩放，宽度小于768像素的时候，container盒子宽度修改为100%宽度。
此时里面的8个小li，宽度修改为33.33%，这样一行就只能显示3个小i，剩余下行显示。

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    * {
      margin: 0;
      padding: 0;
    }
    .container {
      width: 750px;
      margin: 0 auto;
    }
    ul {
      list-style: none;
    }
    .container ul li {
      float: left;
      width: 93.75px;
      height: 30px;
      background-color: green;
    }
    /* 1.超小屏幕（手机，小于768px )：设置宽度为100%*/
    @media screen and (max-width: 767px) {
      .container {
        width: 100%;
      }
      .container ul li {
        width: 33.33%;
      }
    }
    
  </style>
</head>
<body>
  <div class="container">
    <ul>
      <li>导航栏</li>
      <li>导航栏</li>
      <li>导航栏</li>
      <li>导航栏</li>
      <li>导航栏</li>
      <li>导航栏</li>
      <li>导航栏</li>
      <li>导航栏</li>
    </ul>
  </div>
</body>
</html>
```



## 2.Bootstrap前端开发框架

### 2.1 Bootstrap简介

Bootstrap来自Twitter(推特），是目前最受欢迎的前端框架。Bootstrap是基于HTML、CSS和JAVASCRIPT的，它简洁灵活，使得Web并发更加快捷。

中文官网: http://www.bootcss.com/

官网: http://getbootstrap.com/

推荐使用:https://v3.bootcss.com/ 

框架∶顾名思义就是一套架构，它有一套比较完整的网页功能解决方案，而且控制权在框架本身，有预制样式库、组件和插件。使用者要按照框架所规定的某种规范进行开发。



1.优点

- 标准化的html+css编码规范
- 提供了一套简洁、直观、强悍的组件
- 有自己的生态圈，不断的更新迭代
- 让开发更简单，提高了开发的效率

2.版本

- 2.x.x︰停止维护,兼容性好,代码不够简洁，功能不够完善。
- 3.xx︰目前使用最多,稳定,但是放弃了IE6-IE7。对IE8支持但是界面效果不好,偏向用于开发响应式布局、移动设备优先的WEB项目。
- 4.x.x︰最新版，目前还不是很流行

### 2.2 Bootstrap使用

在现阶段我们还没有接触JS相关课程，所以我们只考虑使用它的样式库。

控制权在框架本身，使用者要按照框架所规定的某种规范进行开发。

Bootstrap使用四步曲∶

1.创建文件夹结构⒉创建html骨架结构3.引入相关样式文件4.书写内容

1.创建文件夹结构

从官网进行下载：

![image-20210922143438730](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210922143438730.png)

![image-20210922143506379](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210922143506379.png)

压缩包解压后，复制相关文件至项目。

![image-20210922142122897](https://gitee.com/jingw1/cloud-image/raw/master/img/image-20210922142122897.png)



⒉创建html骨架结构

3.引入相关样式文件

```html
<!-- Bootstrap核心样式-->
<link rel="stylesheet" href="bootstrap/css/bootstrap.min.css">
```

4.书写内容









