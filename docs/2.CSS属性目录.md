## align-items 属性

### 实例

居中对齐弹性盒的各项 `<div>` 元素：

```css
div {
  display: flex;
  align-items:center;
}
```

### CSS 语法

`align-items: stretch|center|flex-start|flex-end|baseline|initial|inherit;`

### 属性值



| 值         | 描述                                                         | 测试                                                         |
| :--------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| stretch    | 默认值。元素被拉伸以适应容器。如果指定侧轴大小的属性值为'auto'，则其值会使项目的边距盒的尺寸尽可能接近所在行的尺寸，但同时会遵照'min/max-width/height'属性的限制。 | [测试 »](https://www.runoob.com/try/playit.php?f=playcss_align-items&preval=stretch) |
| **center** | 元素位于容器的中心。弹性盒子元素在该行的侧轴（纵轴）上居中放置。（如果该行的尺寸小于弹性盒子元素的尺寸，则会向两个方向溢出相同的长度）。 | [测试 »](https://www.runoob.com/try/playit.php?f=playcss_align-items&preval=center) |
| flex-start | 元素位于容器的开头。弹性盒子元素的侧轴（纵轴）起始位置的边界紧靠住该行的侧轴起始边界。 | [测试 »](https://www.runoob.com/try/playit.php?f=playcss_align-items&preval=flex-start) |
| flex-end   | 元素位于容器的结尾。弹性盒子元素的侧轴（纵轴）起始位置的边界紧靠住该行的侧轴结束边界。 | [测试 »](https://www.runoob.com/try/playit.php?f=playcss_align-items&preval=flex-end) |
| baseline   | 元素位于容器的基线上。如弹性盒子元素的行内轴与侧轴为同一条，则该值与'flex-start'等效。其它情况下，该值将参与基线对齐。 | [测试 »](https://www.runoob.com/try/playit.php?f=playcss_align-items&preval=baseline) |
| initial    | 设置该属性为它的默认值。请参阅 [*initial*](https://www.runoob.com/cssref/css-initial.html)。 | [测试 »](https://www.runoob.com/try/playit.php?f=playcss_align-items&preval=initial) |
| inherit    | 从父元素继承该属性。请参阅 [*inherit*](https://www.runoob.com/cssref/css-inherit.html)。 |                                                              |

## background

### 标签定义及使用说明

背景缩写属性可以在一个声明中设置所有的背景属性。

可以设置的属性分别是：background-color、background-position、background-size、background-repeat、background-origin、background-clip、background-attachment 和 background-image。

各值之间用空格分隔，不分先后顺序。可以只有其中的某些值，例如 ` background：＃FF0000 URL（smiley.gif); `是允许的。

## background-image

### 标签定义及使用说明

background-image 属性设置一个元素的背景图像。

元素的背景是元素的总大小，包括填充和边界（但不包括边距）。

默认情况下，background-image放置在元素的左上角，并重复垂直和水平方向。

提示：请设置一种可用的背景颜色，这样的话，假如背景图像不可用，可以使用背景色带代替。

| 值                                                           | 说明                                      |
| :----------------------------------------------------------- | :---------------------------------------- |
| **url(*'URL'*)**                                             | **图像的URL**                             |
| none                                                         | 无图像背景会显示。这是默认                |
| [linear-gradient()](https://www.runoob.com/cssref/func-linear-gradient.html) | 创建一个线性渐变的 "图像"(从上到下)       |
| [radial-gradient()](https://www.runoob.com/cssref/func-radial-gradient.html) | 用径向渐变创建 "图像"。 (center to edges) |
| [repeating-linear-gradient()](https://www.runoob.com/cssref/func-repeating-linear-gradient.html) | 创建重复的线性渐变 "图像"。               |
| [repeating-radial-gradient()](https://www.runoob.com/cssref/func-repeating-radial-gradient.html) | 创建重复的径向渐变 "图像"                 |
| inherit                                                      | 指定背景图像应该从父元素继承              |

## background-repeat

### 标签定义及使用说明

设置如何平铺对象的 background-image 属性。

默认情况下，重复background-image的垂直和水平方向。

| 值            | 说明                                         |
| :------------ | :------------------------------------------- |
| repeat        | 背景图像将向垂直和水平方向重复。这是默认     |
| repeat-x      | 只有水平位置会重复背景图像                   |
| repeat-y      | 只有垂直位置会重复背景图像                   |
| **no-repeat** | **background-image不会重复**                 |
| inherit       | 指定background-repea属性设置应该从父元素继承 |

### 标签定义及使用说明

background-position属性设置背景图像的起始位置。

### 属性值

| 值                                                           | 描述                                                         |
| :----------------------------------------------------------- | ------------------------------------------------------------ |
| left top <br />left center<br /> left bottom<br /> right top<br /> right center<br />right bottom center top center center<br />center bottom | 如果仅指定一个关键字，其他值将会是"center"                   |
| *x% y%*                                                      | 第一个值是水平位置，第二个值是垂直。左上角是0％0％。右下角是100％100％。如果仅指定了一个值，其他值将是50％。 。默认值为：0％0％ |
| *xpos ypos*                                                  | 第一个值是水平位置，第二个值是垂直。左上角是0。单位可以是像素（0px0px）或任何其他 [CSS单位](https://www.runoob.com/try/css-units.html)。如果仅指定了一个值，其他值将是50％。你可以混合使用％和positions |
| inherit                                                      | 指定background-position属性设置应该从父元素继承              |

## border-radius

### 定义和用法

border-radius 属性是一个简写属性，用于设置四个 border-*-radius 属性。

### 语法

```
border-radius: 1-4 length|% / 1-4 length|%;
```

**注释：**按此顺序设置每个 radii 的四个值。如果省略 bottom-left，则与 top-right 相同。如果省略 bottom-right，则与 top-left 相同。如果省略 top-right，则与 top-left 相同。

| 值       | 描述                     | 测试                                                         |
| :------- | :----------------------- | :----------------------------------------------------------- |
| *length* | 定义圆角的形状。         | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_border-radius) |
| *%*      | 以百分比定义圆角的形状。 | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_border-radius&p=6) |

### 举例：

```
border-radius:2em;
```

等价于：

```
border-top-left-radius:2em;
border-top-right-radius:2em;
border-bottom-right-radius:2em;
border-bottom-left-radius:2em;
```

### 应用：

设置圆角矩形

```
border-radius: 3px;
```

设置圆型边框

```
 border-radius: 50%;
```

## box-shadow 盒子阴影

CSS3中新增了盒子阴影，用box-shadow属性为盒子添加阴影。

### 语法

```
box-shadow: h-shadow v-shadow blur spread color inset;
```

| 值         | 描述                                     | 测试                                                         |
| :--------- | :--------------------------------------- | :----------------------------------------------------------- |
| *h-shadow* | 必需。水平阴影的位置。允许负值。         | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_box-shadow) |
| *v-shadow* | 必需。垂直阴影的位置。允许负值。         | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_box-shadow) |
| *blur*     | 可选。模糊距离。                         | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_box-shadow&p=3) |
| *spread*   | 可选。阴影的尺寸。                       | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_box-shadow&p=7) |
| *color*    | 可选。阴影的颜色。请参阅 CSS 颜色值。    | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_box-shadow&p=10) |
| inset      | 可选。将外部阴影 (outset) 改为内部阴影。 | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_box-shadow&p=15) |

 注意:
1.默认的是外阴影(outset),但是不可以写这个单词,否则导致阴影无效
2.盒子阴影不占用空间，不会影响其他盒子排列。

### 用法：

```
// 阴影在盒子的右边10px，下边10px，模糊10px，阴影的尺寸是-4px
box-shadow: 10px 10px 10px -4px rgba(0，0， 0， .3); 
```

<u>猜想：模糊是指发散的尺寸；阴影是指</u>

## box-sizing

box-sizing 属性允许您以特定的方式定义匹配某个区域的特定元素。

例如，假如您需要并排放置两个带边框的框，可通过将 box-sizing 设置为 "border-box"。这可令浏览器呈现出带有指定宽度和高度的框，并把边框和内边距放入框中。

### 语法

```
box-sizing: content-box|border-box|inherit;
```

| 值          | 描述                                                         |
| :---------- | :----------------------------------------------------------- |
| content-box | 这是由 CSS2.1 规定的宽度高度行为。宽度和高度分别应用到元素的内容框。在宽度和高度之外绘制元素的内边距和边框。 |
| border-box  | 为元素设定的宽度和高度决定了元素的边框盒。就是说，为元素指定的任何内边距和边框都将在已设定的宽度和高度内进行绘制。通过从已设定的宽度和高度分别减去边框和内边距才能得到内容的宽度和高度。 |
| inherit     | 规定应从父元素继承 box-sizing 属性的值。                     |

## display

属性定义及使用说明

display 属性规定元素应该生成的框的类型。

### 属性值

| 值                 | 描述                                                         |
| :----------------- | :----------------------------------------------------------- |
| none               | 此元素不会被显示。                                           |
| block              | 此元素将显示为块级元素，此元素前后会带有换行符。             |
| inline             | 默认。此元素会被显示为内联元素，元素前后没有换行符。         |
| inline-block       | 行内块元素。（CSS2.1 新增的值）                              |
| list-item          | 此元素会作为列表显示。                                       |
| run-in             | 此元素会根据上下文作为块级元素或内联元素显示。               |
| compact            | CSS 中有值 compact，不过由于缺乏广泛支持，已经从 CSS2.1 中删除。 |
| marker             | CSS 中有值 marker，不过由于缺乏广泛支持，已经从 CSS2.1 中删除。 |
| table              | 此元素会作为块级表格来显示（类似 <table>），表格前后带有换行符。 |
| inline-table       | 此元素会作为内联表格来显示（类似 <table>），表格前后没有换行符。 |
| table-row-group    | 此元素会作为一个或多个行的分组来显示（类似 <tbody>）。       |
| table-header-group | 此元素会作为一个或多个行的分组来显示（类似 <thead>）。       |
| table-footer-group | 此元素会作为一个或多个行的分组来显示（类似 <tfoot>）。       |
| table-row          | 此元素会作为一个表格行显示（类似 <tr>）。                    |
| table-column-group | 此元素会作为一个或多个列的分组来显示（类似 <colgroup>）。    |
| table-column       | 此元素会作为一个单元格列显示（类似 <col>）                   |
| table-cell         | 此元素会作为一个表格单元格显示（类似 <td> 和 <th>）          |
| table-caption      | 此元素会作为一个表格标题显示（类似 <caption>）               |
| inherit            | 规定应该从父元素继承 display 属性的值。                      |

### 实例：

使div居右对齐

```
div {
	display: flex;
	justifi-content: flex-end;
}
```



## justify-content 属性

### 实例

在弹性盒对象的 <div> 元素中的各项周围留有空白：

```css
div {
	display: flex;
  justify-content: space-around; 
 }
```

### CSS 语法

```
justify-content: flex-start|flex-end|center|space-between|space-around|initial|inherit;
```



### 属性值



| 值            | 描述                                                         | 测试                                                         |
| :------------ | :----------------------------------------------------------- | :----------------------------------------------------------- |
| flex-start    | 默认值。项目位于容器的开头。                                 | [测试 »](https://www.runoob.com/try/playit.php?f=playcss_justify-content&preval=flex-start) |
| flex-end      | 项目位于容器的结尾。                                         | [测试 »](https://www.runoob.com/try/playit.php?f=playcss_justify-content&preval=flex-end) |
| center        | 项目位于容器的中心。                                         | [测试 »](https://www.runoob.com/try/playit.php?f=playcss_justify-content&preval=center) |
| space-between | 项目位于各行之间留有空白的容器内。                           | [测试 »](https://www.runoob.com/try/playit.php?f=playcss_justify-content&preval=space-between) |
| space-around  | 项目位于各行之前、之间、之后都留有空白的容器内。             | [测试 »](https://www.runoob.com/try/playit.php?f=playcss_justify-content&preval=space-around) |
| initial       | 设置该属性为它的默认值。请参阅 [*initial*](https://www.runoob.com/cssref/css-initial.html)。 | [测试 »](https://www.runoob.com/try/playit.php?f=playcss_justify-content&preval=initial) |
| inherit       | 从父元素继承该属性。请参阅 [*inherit*](https://www.runoob.com/cssref/css-inherit.html)。 |                                                              |

`space-between`和`space-around`之间的区别：

`space-between`的各项目之间有空隙，项目前面（后面）没有项目的时候没有空隙。

`space-around`的项目的前面后面都有空隙。

### 属性定义及使用说明

Transform属性应用于元素的2D或3D转换。这个属性允许你将元素旋转，缩放，移动，倾斜等。

### 语法

`transform: none|transform-functions;`

| 值                                                           | 描述                                    |
| :----------------------------------------------------------- | :-------------------------------------- |
| none                                                         | 定义不进行转换。                        |
| matrix(*n*,*n*,*n*,*n*,*n*,*n*)                              | 定义 2D 转换，使用六个值的矩阵。        |
| matrix3d(*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*) | 定义 3D 转换，使用 16 个值的 4x4 矩阵。 |
| **translate(*x*,*y*)**                                       | **定义 2D 转换。**                      |
| translate3d(*x*,*y*,*z*)                                     | 定义 3D 转换。                          |
| translateX(*x*)                                              | 定义转换，只是用 X 轴的值。             |
| translateY(*y*)                                              | 定义转换，只是用 Y 轴的值。             |
| translateZ(*z*)                                              | 定义 3D 转换，只是用 Z 轴的值。         |
| scale(*x*[,*y*]?)                                            | 定义 2D 缩放转换。                      |
| scale3d(*x*,*y*,*z*)                                         | 定义 3D 缩放转换。                      |
| scaleX(*x*)                                                  | 通过设置 X 轴的值来定义缩放转换。       |
| scaleY(*y*)                                                  | 通过设置 Y 轴的值来定义缩放转换。       |
| scaleZ(*z*)                                                  | 通过设置 Z 轴的值来定义 3D 缩放转换。   |
| rotate(*angle*)                                              | 定义 2D 旋转，在参数中规定角度。        |
| rotate3d(*x*,*y*,*z*,*angle*)                                | 定义 3D 旋转。                          |
| rotateX(*angle*)                                             | 定义沿着 X 轴的 3D 旋转。               |
| rotateY(*angle*)                                             | 定义沿着 Y 轴的 3D 旋转。               |
| rotateZ(*angle*)                                             | 定义沿着 Z 轴的 3D 旋转。               |
| skew(*x-angle*,*y-angle*)                                    | 定义沿着 X 和 Y 轴的 2D 倾斜转换。      |
| skewX(*angle*)                                               | 定义沿着 X 轴的 2D 倾斜转换。           |
| skewY(*angle*)                                               | 定义沿着 Y 轴的 2D 倾斜转换。           |
| perspective(*n*)                                             | 为 3D 转换元素定义透视视图。            |

应用场景：

将div放在页面的最中间

```css
.loginAndRegBox {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%,-50%);
  width: 400px;
  height: 310px;
  background-color: #fff;
}
```



## transform

### 定义和用法

transform 属性向元素应用 2D 或 3D 转换。该属性允许我们对元素进行旋转、缩放、移动或倾斜。

### 语法

```
transform: none|transform-functions;
```

| 值                                                           | 描述                                    | 测试                                                         |
| :----------------------------------------------------------- | :-------------------------------------- | :----------------------------------------------------------- |
| none                                                         | 定义不进行转换。                        | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_transform_rotate&p=22) |
| matrix(*n*,*n*,*n*,*n*,*n*,*n*)                              | 定义 2D 转换，使用六个值的矩阵。        | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_transform_matrix) |
| matrix3d(*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*,*n*) | 定义 3D 转换，使用 16 个值的 4x4 矩阵。 |                                                              |
| **translate(*x*,*y*)**                                       | 定义 2D 转换。                          | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_transform_translate) |
| translate3d(*x*,*y*,*z*)                                     | 定义 3D 转换。                          |                                                              |
| translateX(*x*)                                              | 定义转换，只是用 X 轴的值。             | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_transform_translatex) |
| translateY(*y*)                                              | 定义转换，只是用 Y 轴的值。             | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_transform_translatey) |
| translateZ(*z*)                                              | 定义 3D 转换，只是用 Z 轴的值。         |                                                              |
| scale(*x*,*y*)                                               | 定义 2D 缩放转换。                      | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_transform_scale) |
| scale3d(*x*,*y*,*z*)                                         | 定义 3D 缩放转换。                      |                                                              |
| scaleX(*x*)                                                  | 通过设置 X 轴的值来定义缩放转换。       | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_transform_scalex) |
| scaleY(*y*)                                                  | 通过设置 Y 轴的值来定义缩放转换。       | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_transform_scaley) |
| scaleZ(*z*)                                                  | 通过设置 Z 轴的值来定义 3D 缩放转换。   |                                                              |
| rotate(*angle*)                                              | 定义 2D 旋转，在参数中规定角度。        | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_transform_rotate) |
| rotate3d(*x*,*y*,*z*,*angle*)                                | 定义 3D 旋转。                          |                                                              |
| rotateX(*angle*)                                             | 定义沿着 X 轴的 3D 旋转。               | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_transform_rotatex) |
| rotateY(*angle*)                                             | 定义沿着 Y 轴的 3D 旋转。               | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_transform_rotatey) |
| rotateZ(*angle*)                                             | 定义沿着 Z 轴的 3D 旋转。               | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_transform_rotatez) |
| skew(*x-angle*,*y-angle*)                                    | 定义沿着 X 和 Y 轴的 2D 倾斜转换。      | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_transform_skew) |
| skewX(*angle*)                                               | 定义沿着 X 轴的 2D 倾斜转换。           | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_transform_skewx) |
| skewY(*angle*)                                               | 定义沿着 Y 轴的 2D 倾斜转换。           | [测试](https://www.w3school.com.cn/tiy/c.asp?f=css_transform_skewy) |
| perspective(*n*)                                             | 为 3D 转换元素定义透视视图。            | 测试                                                         |

### 应用

设置矩形位置在父容器的正中间

```
 position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%,-50%);
```



## user-select

### user-select定义和用法

**user-select**：none | text | all | element

**默认值**：text

**适用于**：除替换元素外的所有元素

**继承性**：无

### user-select属性值

- none：

  文本不能被选择

- text：

  可以选择文本

- all：

  当所有内容作为一个整体时可以被选择。如果双击或者在上下文上点击子元素，那么被选择的部分将是以该子元素向上回溯的最高祖先元素。

- element：

  可以选择文本，但选择范围受元素边界的约束

### user-select说明

**设置或检索是否允许用户选中文本。**

- IE6-9不支持该属性，但支持使用标签属性 `onselectstart="return false;"` 来达到 `user-select:none` 的效果；Safari和Chrome也支持该标签属性；
- 直到Opera12.5仍然不支持该属性，但和IE6-9一样，也支持使用私有的标签属性 `unselectable="on"` 来达到 `user-select:none` 的效果；unselectable 的另一个值是 off；
- 除Chrome和Safari外，在其它浏览器中，如果将文本设置为 `-ms-user-select:none;`，则用户将无法在该文本块中开始选择文本。不过，如果用户在页面的其他区域开始选择文本，则用户仍然可以继续选择将文本设置为 `-ms-user-select:none;` 的区域文本；
- 对应的脚本特性为**userSelect**。