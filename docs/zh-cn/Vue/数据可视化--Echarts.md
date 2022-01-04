





视频链接：https://www.bilibili.com/video/BV1bh41197p8

# 一、数据可视化前言

## 1 项目演示

### 1.1 项目运行

**启动后端工程**

1. `cd koa2-server `  进入目录
2. `npm install` 将后端工程需要的一些依赖包进行安装
3. `node app.js`  启动后端程序

正常的显示如下：

![image-20220103101656448](https://s2.loli.net/2022/01/03/BN1OskMI4pfRHdj.png)

![image-20211229183338258](https://s2.loli.net/2021/12/29/o1lVaMk2WrdC6Bv.png)

地址端口已经被占用

![image-20211229184050655](https://s2.loli.net/2021/12/29/VwL3yApPlZHnmht.png)

**启动前端工程**

1. cd vision
2. npm install
3. npm run serve

![image-20220103102239680](https://s2.loli.net/2022/01/03/4ZAPCvYX1rsta27.png)

### 1.2 项目演示

1. 该项目为电商平台数据可视化实时监控系统
2. 可以保证实时获取数据进行分析
3. 支持大屏展示，自适应分辨率
4. 支持联动效果，一端操作，多端联动展示。

### 1.3 技术选型

1. ECharts
2. Vue, Vue Router ,Vuex
3. webpack
4. Axios
5. webSocket
6. Koa2

## 2 数据可视化概念

### 2.1 什么是数据可视化

把数据以更直观的形式展现  --->图表

![image-20220103104624337](https://s2.loli.net/2022/01/03/LyTGrMtwnEl8Jcx.png)



### 2.2 数据可视化的好处

- 清晰有效地传达与沟通信息

![image-20220103104754305](https://s2.loli.net/2022/01/03/CJvjmMpHIDZl91R.png)

隐藏在数据中的信息

![image-20220103104828872](https://s2.loli.net/2022/01/03/U5fGxyi63MkrhE2.png)

 

### 2.3可视化的实现方式

- 报表类
  - Excel
  - 水晶报表
- 商业智能BI
  - Microsoft Bl
  - Power-Bl
- 编码类
  - ECharts.js
  - D3.js

## 小结

小结

- 数据可视化的概念和作用
  - 将数据以图表的形式呈现更有效的传达数据中的信息
- 常见的可视化工具
  - 报表类
  - BI类
  - 编程类

# 二、ECharts的基本使用

## 1 ECharts的介绍

### 1.1 ECharts的介绍

ECharts是一个使用JavaScript实现的开源可视化库，兼容性强，底层依赖矢量图形库ZRender，提供直观，交互丰富，可高度个性化定制的数据可视化图表。

![image-20220103110010069](https://s2.loli.net/2022/01/03/DLIWpnHS1zPjr84.png)

官网地址: https://echarts.apache.org/zh/index.html

### 1.2 ECharts的特点

- 丰富的可视化类型
  - 折线图、柱状图、饼图、K线图.......
  - 只有你想不到,没有它做不到
  - https://echarts.apache.org/examples/zh/index.html

- 多种数据格式支持
  - key-value数据格式
  - 二维表
  - TypedArray格式
- 流数据的支持
  - 流数据的动态渲染
  - 增量渲染技术
- 移动端优化
- 跨平台使用
- 绚丽的特效
- 三维可视化
- ……
- 特性介绍地址
  - https://echarts.apache.org/zh/feature.html

## 2 ECharts的快速入门


  步骤1：引入echarts.js文件
  步骤2：准备一个呈现图表的盒子
  步骤3：初始化echarts实例对象
  步骤4：准备配置项
  步骤5：将配置项设置给echarts实例对象

### 2.3 小结

- 快速上手ECharts的步骤
  - 引入
  - 准备设置
- 配置项的使用
  - 除了配置项会变化之外，其他的代码都是固定的
  - 配置项的学习和使用应该参照官方文档和示例
  - https://echarts.apache.org/zh/option.html#title

### 2.4 ECharts的基本使用

- 相关配置讲解
  - xAxis:直角坐标系中的×轴
  - yAxis:直角坐标系中的y轴
  - series:系列列表。每个系列通过type决定自己的图表类型

- 官方文档的查阅
  - 网址: https://www.echartsjs.com/zh/api.html#echarts
  - 配置项太多，无需去刻意记忆





 

## 3 ECharts的常用图表

- 7大图表
  - 图表1:柱状图
  - 图表2:折线图
  - 图表3:散点图
  - 图表4∶饼图
  - 图表5:地图
  - 图表6:雷达图
  - 图表7:仪表盘图

### 3.1 柱状图

- 图表1:柱状图

![image-20220104092555744](https://s2.loli.net/2022/01/04/54eiAVzjulRw9kF.png)

- 实现步骤
  - ECharts最基本的代码结构:
    引入js文件, DOM容器,初始化对象,设置option
  - x轴数据:
    数组1:['张三','李四','王五','闰土','小明"，'茅台"，'二妞','大强']
  - y轴数据:
    数组2:[88,92,63,77,94,80,72,86]
  - 图表类型:
    在series下设置type:bar

- 常见效果

  - 标记：最大值 最小值 平均值

    markPoint
    markLine

  - 显示：数值显示 柱宽度 横向柱状图

    labelbar
    Width
    更改x轴和y轴的角色

- 小结

  - 基本的柱状图
    - 基本的代码结构
    - x轴和y轴的数据
    - series中的type设置为bar
  - 柱状图常见效果
    - 最大值\最小值 markPoint
    - 平均值 markLine 
    - 数值的显示 label
    - 柱的宽度 barwidth
  - 柱状图特点
    - 柱状图描述的是分类数据，呈现的是每一个分类中**有多少**,通过柱状图,可以很清晰的看出每个分类数据的排名情况

- 通用配置
  通用配置指的就是任何图表都能使用的配置

  - 标题: title
  - 提示: tooltip
  - 工具按钮: toolbox
  - 图例: legend

- 通用配置title

  - 文字样式 textStyle
  - 标题边框
    borderwidth、 borderColor、borderRadius
  - 标题位置
    left、 top、right、 bottom

-  通用配置tooltip

  tooltip:提示框组件,用于配置鼠标滑过或点击图表时的显示框

  - 触发类型: trigger
    item、axis

  - 触发时机: triggerOn

    mouseover.click

  - 格式化: formatter

    字符串模板、回调函数



# 三、Echarts的高级使用

> 显示相关
>
> 动画的使用
>
> 交互API

## 1 显示相关

> 
>
> **目录：**
>
> 调色盘
>
> 样式
>
> 自适应

###  1.1 主题

- 内置主题

  - ECharts中默认内置了两套主题:light dark

  - 在初始化对象方法init中可以指明

    ```javascript
    var chart = echarts.init(dom, 'light');
    var chart = echarts.init(dom, 'dark');
    ```

- 自定义主题

  1. 在主题编辑器中编辑主题
  2. 下载主题,是一个js文件
  3. 引入主题js文件
  4. 在init方法中使用主题

# 四、电商平台数据可视化实时监控系统

> **目录：**
>
> 后台开发
> 结合Vue开发图表组件
> WebSocket实现后台数据推送
> 主题切换\页面合并\全屏切换......

## 1 Koa2的使用

### 1.1 Koa2的介绍



Koa2快速上手
搭建后台项目













 