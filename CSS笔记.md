### css 层叠样式表



​		可以将css样式编写到元素的style属性中，属性值：属性名；

将样式直接编写到标签属性中，这种样式叫做内联样式 ，内联样式不方便复用，内联样式于结构耦合，不推荐使用。

#### 内部样式表

​		也可以将css编写到head里，将样式表编写到style标签中，然后通过css选择器选中指定元素，同时为这些元素设置样式，这样可以使样式进一步复用。

#### 外部样式表

​		可以在外部创建一个css文件，在HTML中引入

#### css注释

/*

*/

#### 选择器

- ​	通过选择器可以选中页面中指定的元素，并且将声明块中的样式应用到选择器对应的元素上

#### 声明块

- 声明块紧跟选择器后面，用一对{}扩起来，声明块实际就是一组一组的名值对结构，这一组一组的名值对我们称之为声明。

#### 块元素内联元素

- 块元素

  - 所谓块元素，独占一行的元素，无论他的内容多少，都会独占一行。

- 内联元素

  - 所谓内联元素指的是只会占自身大小的元素
  - 常见的内联：a ，img ，iframe等

  块元素一般用来网页的文本布局，内联元素主要用来选择文本设置样式，一般情况下只是用块元素去包含内联元素，而不会使用内联元素去包含块元素。a元素可以包含任何元素，除了它本身。p元素里不能放任何块元素。

#### 常用的选择器



- 元素选择器

  - 就是标签名

- id选择器

  - 语法：
    - #id属性值

- class选择器

  - 语法：
    - .class属性值
    - c可以为一个元素设置多个class属性值，多个值之间使用空格隔开

- 并集选择器

  - 语法：
    - 选择器1，选择器2，选择器3 .....

- 统配选择器

  - 语法：
    - *{}

- 交集选择器

  - 语法：
    - 选择器1选择器2

- 后代元素选择器

  - 选中指定元素的指定后代元素
  - 语法：
    - 祖先元素 后代元素{}

- 子元素选择器

  - 语法
    - 父元素>子元素{}
    - IE6及以下不兼容

- 伪类选择器

  伪类专门表示元素一种特殊的状态，浏览器是通过历史记录来判断我们访问与否

  - ：link   

    - 没访问过的链接

  - ：visited

    - 访问过的链接
    - 由于涉及到用户的隐私问题，不能涉及其他的样式，只能是指字体颜色

  - ：hover

    - 鼠标移入的状态

  - ：active

    - 鼠标点击的状态

  - ：focus

    - 获取焦点的状态

  - ：：selection

    - 文本选中的状态设置样式

    hover和active也可以给其他选择器使用

#### 伪元素

​	使用伪元素来表示元素中的一些特殊位置

- ：first-letter
  
  - 为第一个字设置样式
  
- ：first-line
  
  - 为第一行设置样式，以上两个针对文本标签
  
- ：before
  - 表示元素的前面的部分
  - 一般before要结合content这个样式一起使用。通过content可以向before和after的位置添加一些内容
  - p：before{
  - content："该文字会出现在段落的最前面"
  - }
  
- ：after
  - p：after{
  - content："该文字会出现在段落的最前面"
  - 且文字不能被选中
  
  ### 属性选择器
  
  可以根据元素中的属性和属性值来选取指定元素
  
  - 语法：
    - p[属性名]   选择拥有该属性的标签名
    - p[属性名=属性值] 选择拥有该属性值的标签名
    - p[属性名^=属性值] 选择以某某属性值开头的元素
    - p[属性名$=属性值] 选择以某某属性值结尾的元素
    - p[属性名*=属性值]  选择包含某某属性值的元素
  
  - title
    - 当我们鼠标移到元素上去，元素中的title属性的值将会作为提示文字显示
  
  ### 子元素选择器
  
  - ​	p：first-child
    - 找p元素下的第一个p
  - ​	p：last-child
    - p元素的最后一个p
  - ​	p：nth-child（序号）
    - 可以选中任意位置的子元素，按照序号来
    - 该选择器后面可以有一个参数，可以指定位置
      - even  偶数位置的子元素
      - odd   奇数位置的子元素
  - p：first-of-type
    - p类型的第一个
  - p：last-of-type
    - p类型的最后一个
  - p：nth-of-type
    - 指定位置的p
  
  ### 兄弟选择器
  
  - ​	span+p{
  
    ​					}
  
    - 可以选择span后的第一个p元素
    - 语法： 前一个 +后一个
  
  - ​	span～p{
  
    ​					}
  
  - 可以选择span后的所有p元素
  
  - 语法： 前一个 +后边所有

### 否定伪类

​		可以从已经选中的元素中剔除某些元素

- ​		语法：
  - ：not（选择器）
  - p：not（.hello）
    - 除去p中有class属性的所有p元素

### 样式的继承

​	像儿子继承父亲的财产一样，在CSS中，祖先元素上的样式，也会被他的后代元素所继承，利用继承，可以将一些基本样式设置给祖先元素，这样所有的后代元素将会自动继承这些样式。



但是说，不是所有的样式都会被后代继承，比如：背景颜色

### 	选择器的优先级

当使用不同的选择器选择同一个元素时并且设置同一个样式时 ，这样选择气之间就会出现冲突，这样就选择选择器高的。

- 优先级规则

  - 内联样式  1000
  - id选择器 100
  - 类和伪类 10
  - 元素选择器 1
  - 通配 * 0
  - 继承 没有优先级

  当我们选择器包含多种选择器时，我们需要把选择器相加，再比较。但是选择器的优先级计算，不会超过它的最大数量级。如果选择器优先级一样，谁在后选择谁。

  ​	并集选择器的优先级是单独计算

  可以在样式最后，添加一个！important，，则此时样式会获得一个最高的优先级，甚至比内联的优先级还高。但是慎用！

### 伪类的顺序

涉及到a的伪类优先级是一样的， 但是顺序会覆盖，一般顺序lvha。

### 文本标签

- em标签用于表示一段内容的着重点，em在浏览器默认时斜体
- strong标签，表示强调的内容，默认粗体。
  - 这两个标签都表示一个强调的内容，em是主要表示语气上的强调
- i 标签中的内容会议斜体显示
- b 标签中的内容会以加粗显示
  - h5规范中规定，对于不需要着重的内容单纯的加粗或者斜体用i和b
- small 标签中的内容会比它的父元素小一点，在h5使用small标签表示一些细则一类的内容。
- cite 网页中所有加书名号的内容都尅使用cite标签，表示参考的内容。默认斜体。比如书名，歌名...
- q 标签  q标签表示一个短的引用，浏览器会默认加上引号
- blockquote  标签表示一个长引用（块级引用）
  - 独占一行
- sup 使用sup设置上标   2<sup>2<sup />
- sub 下标
- ins  表示一个插入内容，ins里面的内容会自动添加下划线
- del 使用del标签表示一个删除的内容，del里的内容删除
- pre 是一个预格式标签，把代码放进pre，会保留代码的格式
- code 专门用来表示代码的，但是它不会保留格式

#### 列表标签

- 无序列表

  - 使用li在ul中创建一个一个列表项，一个li就是一个列表项，使用type属性可以修改无序列表的项目符号
    - 可选值：
      - disc 默认
      - square 实行的方块
      - circle  空心的圆
    - 去掉项目符号
      - list-style：none
    - 默认的项目符号我们一般不使用，因为在不同的浏览器显示的效果不一样。一般我们采用为li设置背景图片的方式来设置

- 有序列表

  - 有序列表和无序列表类似，ol表示

    - 可以使用type属性设置项目符号

      - 1 采用123计数
      - a 采用小写计数
      - A 采用大写计数
      - i 采用罗马计数
      - I 大写罗马计数

      列表之间都是可以互相嵌套的

- 定义列表

  - 定义列表用来对一些词汇或内容进行定义
  - dl 来创建一个定义列表
    - dl有两个标签
      - dt 被定义的内容
      - dd 对定义的内容进行描述

### 单位

1. ​	长度单位

   1. 像素 px
   2. 百分比 %
      1. 也可以将单位设置为一个百分比的形式
         1. 这样浏览器将会根据父元素的样式来计算该值，使用百分比的好处，当父元素发生变化时，子元素也会按照比例发生改变。
   3. em
      1. em和百分比类似，它是相当于当前元素的字体大小来计算的。1em=1font-size
      2. font=size 改变 em也会发生改变
      3. 当设置字体的相关样式时，经常会使用em

2. 颜色单位

   ​		在css中可以直接用颜色单词来表示不同的颜色，也可以使用rgb值来表示。红绿蓝。通过这三种颜色的浓度，来表示不同的颜色。颜色的浓度也可以使用一个百分数来表示（0-100）。使用百分数最终也会转换成0-255之间的数值。

   ​		rgb(x,x,x)

   ​	也可以使用十六进制来代替数值，使用两组十六进制数组来表示一个颜色.

   00 最小  ff最小

   1. 语法：
      1. #红色绿色蓝色
      2. rgb(#ff0000)
         1. rgb(#f00)  简写针对重复的

### 字体样式

- ​	字体颜色

  - color

- 字体大小（默认文字大小16px）

  - font-size/行高
    - font-size 设置的不是文字本身的大小，在页面中每个文字都是存在在一个看不见的框中，我们设置的font-size实际上是格的大小。有时候也会比格大。

- 字体类型

  - font-family

    - 当采用某种字体，如果浏览器支持则使用该字体，如果字体不支持，则使用默认字体。该样式可以同时指定多个字体，多个字体使用逗号字体，浏览器会默认使用前面一个字体，如果不支持则使用后面一个字体。字体都是电脑默认的，如果用户的电脑没有，就会用默认值。

  - 字体的分类：

    - 在网页中将字体分成了五大类

      - serif 衬线字体
      - sans-serif   非衬线字体
      - monospace 等宽字体
      - cursive 草书字体
      - fantasy  虚幻字体

    - 一般我们会将字体设置为这些大的分类，当设置大的分类之后，兰兰器会自动选择制定字体并设置样式。

    - 字体的其他样式

      - font-style
        - 可以用来设置文字的斜体
        - 可选值
          - normal 默认值，文字正常显示
          - italic 文字会以斜体显示
          - oblique 文字会以倾斜额效果显示
          - 大部分浏览器都不会对倾斜和斜体作区分，一般我们只会使用italic

    - font-weight

      - 设置文本的粗细
        - 参数
          - normal 默认，正常显示
          - bold 文字会加粗显示

    - font-variant

      - ​	设置小型大写字母
      - 参数
        - normal 默认
        - small-caps   文本以小型大写字母显示

      在CSS中，我们可以通过font，使用该样式可以同时设置字体相关的所有样式，不同的值之间使用逗号隔开。

      ​		但是在使用font时，字体大小，字体样式必须是倒数第二和倒数第一。

      其他的参数顺序没有要求。实际上我们使用简写也会有好的性能。

### 行间距

​		在CSS中并没有为我们提供一个直接设置行间距的方式，我们只能设置行高来间接设置行间距。行高相当于上学时的单线本。文字会迷人在行高中垂直居中显示。

​	行间距=行高-字体大小

- 通过line-height 来设置行高
  - 可以接收的值
    1. 直接接收一个大小
    2. 可以指定一个百分数
    3. 可以传一个整数
       1. 我们的行高会变成字体大小的倍数

### 文本样式

- ​	text-transform可以用来设置文本的大小写
  - 参数
    - none  默认值
    - capitalize   单词的首字母变大写 通过空格识别单词
    - uppercase  所有字母都大写
    - lowercase 所有字母都小写
- 文本的修饰
  - text-decoration
    - 参数
      - none 默认，不添加任何修饰
      - underline 文本下划线
      - overline  文本的上划线
      - line-through  文本添加删除线
    - 超链接会默认有下划线
      - 我们如果想要去除下划线，我们可以将a的样式设置为none
  - letter-spacing
    - 设置字符间距，we w和e之前的距离
  - word-spacing  
    - 设置单词之间的间距
  - text-align
    - 用于设置文本的对齐方式
    - 参数
      - left 默认靠左对齐
      - right 靠右对齐
      - center 居中对齐 
      - justify  两端对齐 通过调整文本之间的空格大小
  - text-indent
    - 设置文本的缩进
    - 语法：
      - text-indent{大小}
      - 只对第一行有用，一般我们用em来设置（保证我们的缩进2个字符）
      - 设置负值，把文本往左缩进，把不想让用户的看见的文字，设置为左缩进

### 盒子模型（框模型）

- element 内容
- padding 内边距
- margin 外边距
- border 边框



- 为元素设置边框
  - 必须要有三个样式
    - border-width
      - 可以设置四个方向的宽度
        - 上右下左（顺时针设置）
        - 如果设置三个值，会给上  左右  下
        - 两个值  上下  左右
    - 除了border-width，css还设置了四个border-xxx-width。xxx的值可能时，bottom，top，left，right
    - border-color
      - 同上设置，也可以设置成四个值，三个，两个，一个
    - border-style
      - 同上设置，也可以设置成四个值，三个，两个，一个
      - 可选值
        - none  默认值，没有边框
        - dotted  点状边框
        - dashed  虚线边框
        - double 双线边框
        - solid  实线边框

我们平常设置的width，height。都是内容区的大小。而不是盒子整个的大小，盒子可见框的大小由内容区，内边距和边框共同决定。

​	大部分的浏览器边框的宽度和颜色都有默认值的，而边框的样式的默认值时none

​	边框的简写形式：border：x,x,x    顺序没有要求

### 内边距

padding，指的是盒子内容区与盒子边框之间的距离，内边距会影响盒子可见框的大小。 

- padding-right

- padding-top

- padding-left

- padding-bottom

  盒子大小由内容区， 边距，内边距构成

  盒子可见框的宽度：左边框+左边距+内容区+右边距+右边框

  也可以简写：padding：规则和border一致

### 外边距

​	margin，指的是盒子与其他盒子之间的距离，他不会影响可见框的大小，但是他可以影响盒子之间的位置

- margin-top
- margin-bottom
- margin-left
- margin-right

由于页面的元素都是靠左，所以当我们设置上和左的边距时，会导致盒子的自身位置发生改变，如果设置下和有边距庙会改变其他盒子的位置。会挤别的盒子。

​	外边距也可以设置一个负值，如果我们设置负值，我们的元素会向反方向移动。

​	margin还可以设置为auto，auto一般设置给水平方向的margin

如果只指定左或右margin为auto则会将外边距设置为最大值 。如果把两个值设置都设置为auto，就可以使元素在其父元素中居中。

- margin也可以简写
  - margin：x,x,x,x
  - 规则和padding值一样

### 垂直外边距重叠

​	在网页中垂直方向的相邻外边距会发生外边距的重叠

#### 所谓的外边距重叠指兄弟元素之间的相邻外边距会取最大值而不是求和。不相邻就不会发生重叠。两个要素：相邻  垂直

如果父子元素的垂直的外边距重叠了，这个外边距会传递给父元素

### 默认样式

​	浏览器会有默认的样式，浏览器在页面没有样式时，会默认给页面添加一个样式。而他的默认样式正常情况下，我们是不需要使用的。所以我们往往在编写样式之前需要将浏览器的margin和padding统统去掉。*{}

### 内联元素的盒子模型

- 内联元素不能设置width，height

- 设置水平内边距，内联元素可以设置水平方向的内边距

- 设置垂直方向的内边距，内联元素可以设置垂直方向内边距，但不会影响布局

- 为元素设置边框，可以设置边框，但是垂直的边框会影响布局，水平不会影响布局。

- 内联元素支持水平方向的外边距，水平方向的外边距不会重叠，会进行求和。

- 内联元素不支持垂直外边距

- 将一个内联元素设置成块元素。，属性：display

- 语法 display

  - 参数

    - inline

      - 设置为内联元素

    - block

      - 设置为块元素

    - inline-block

      - 设置为行内块元素
        - 使一个元素设置为块元素，但不会独占一行

    - none

      - 设置为none
        - 隐藏元素，不显示元素。并且元素不会在页面占位置

      - visbility

      - 参数
        - visible
          - 可见的，默认值
          - hidden
            - 使用visbility设置的hidden，会将元素隐藏。但是位置还在。

- ### overflow

  - 子元素默认是存在父元素的内容区中，理论上讲子元素的的最大可以等于父元素内容区大小，如果子元素的大小超过父元素的内容，我们称之为溢出的内容。
  - 父元素默认是将子元素溢出的内容在外面显示
  - 通过overflow可以设置如何处理溢出的内容
    - 参数
      - visible 元素不会对溢出内容作出处理
      - hidden 内容会被修剪，而且不会显示
      - scrol  内容会被修剪，但是通过滚动条来查看内容，该属性无论内容是否溢出，都会添加水平垂直的滚动条
      - auto  会根据需求自动添加滚动条

### 文档流

​	每个页面都是一个文档，文档流处在网页的最底层，它表示的是一个页面的位置，我们所创建的元素默认在文档流中。

​	元素在文档流中的特点

- ​	块元素
  - 块元素在文档流中，会独占一行，自上向下排列
  - 块元素在文档流里的宽度，默认是auto，是父元素的100%。当元素的高度或者宽度值为auto时，此时制定内编剧不会影响可见框的大小，而是会自动修改宽度和高度，以适应内边距
  - 块元素在文档流中的里的高度默认被内容撑开的。
- 内联元素
  - 内联元素，在文档中只占自身大小，会迷人自左向右排列。如果一行字中不足以容纳内联元素，会默认跑到下一行。
  - 内联元素的宽度和高度默认被内容撑开的。

### 浮动

如果需要块元素在页面中水平排列 ，可以使块元素脱离文档流。使用float来使元素浮动 ，从而脱离文档流。

- float

  可选参数

  - none 
    - 没有影响
  - left
    - 向左侧浮动
  - right
    - 向页面的右面浮动

  ​         当为元素设置浮动以后，元素会立即脱离文档流，元素脱离文档流以后，下面的元素会顶替它的位置。元素浮动会尽量往页面的左上或者右上飘，直到遇到父元素的边框或者其他的浮动元素。浮动流比文档流高一级。浮动会在文档的上面。如果浮动元素上边是一个没有浮动的块元素，他不会超过块元素。浮动元素不会超过它的兄弟元素。

  浮动元素不会盖住文字，文字会自动环绕在图片的周围。

  - 在文档流中，子元素的宽度默认占父元素的全部
  - 块元素脱离文档流以后，宽度和高度都会被内容撑开
  - 内联元素脱离文档流以后，变成块元素。

  ### 高度塌陷

  ​		在文档流中，父元素的高度默认是被子元素撑开的，也就是子元素多高，父元素就多高。但是当为子元素设置浮动以后，子元素就会完全脱离文档流，此时将会导致子元素无法撑起父元素的高度，导致父元素高度塌陷。所以在开发中一定要避免父元素高度塌陷的问题。我们可以把父元素的高度写死，但是这样会有一个问题，子元素的高度如果大于父元素。就会导致子元素溢出。所以不推荐这种方法。

  - 根据w3c的标准，在页面中元素都有一个遗憾的属性叫做Black Formatting Context，简称BFC，该属性可以设置打开或者关闭。当开启BFC以后，元素会具有以下特性：
    - 父元素的垂直外边距不会和子元素重叠
    - 开启的BFC，不会被浮动元素覆盖
    - 开启的BFC的元素可以包含浮动的子元素
  - 如何开启元素的BFC
    - 设置元素的浮动
      - 设置这种方式开启，虽然可以撑开父元素，但是会导致父元素的宽度丢失
    - 设置元素绝对定位
    - 设置元素为inline-block
      - 可以解决问题，但是会导致父元素的宽度缺失
    - 将元素的overflow设置为一个非visible的值
      - 将元素的overflow的设为hidden。副作用最小。推荐使用。但是在IE6及以下不支持。
      - 在IE6中虽然没有BFC，但是具有另一个隐含的属性叫做has Layout,该睡醒的作用和BFC类似，所在IE6的浏览器可以通过开启这个来解决这个问题。直接将元素的zoom设置为1.zoom：1即可。zoom表示放大的意思，后边跟着一个数值，表示放大几倍。

### 清除浮动

​	设置三个盒子，把第一个盒子设置浮动，那么它后面的的所有盒子都会顶上来。但是在日常开发中，我们不需要这种需求，就可以清除这个浮动带来的影响。这种现象我们把他叫做清除浮动。

clear

- 可以用来清除其他元素对当前元素的影响。
- 可选值
  - none 默认
  - left 清除左侧浮动元素对当前元素的影响
  - right 清除右侧浮动元素对当前元素的影响
  - both 清除两侧元素对当前元素的影响，其实是清除影响对他最大的元素。
- 清除浮动以后，元素会回到元素之前的位置
- 解决高度塌陷方案二
  - 可以直接在高度塌陷的父元素的最后，添加一个空白的div，由于这个div没有浮动，所以他是可以撑开父元素的高度，然后再对其清除浮动，这样可以通过这个空白的div来撑开父元素，基本没有副作用。各个浏览器都可以兼容。使用这种方式可以解决问题，但是会在页面添加多余的结构。
  - 终极方案：
    - 可以通过after伪类想元素的最后添加一个空白的块元素，然后对其清除浮动。这样做和添加一个div的原理一样，可以达到一个相同的效果，而且不会在页面中添加多余的div，这是最推荐的方式。
    - 在IE6不兼容after伪类！
    - 通过zoom：1兼容IE6

### 相对定位

​	定位：就是将指定元素摆放到页面的任意位置，通过定位，可以任意摆放元素。

通过position设置定位属性

- 参数

  - static  默认 元素没有开启定位

  - absolute 开启元素的绝对定位

    - ### 特点

    - 开启绝对定位，会使元素脱离文档流。

    - 开启绝对定位以后，如果不设置偏移量，元素位置不会改变。 

    - 绝对定位会使元素提升一个层级。盖住文档流。

    - 绝对定位是相对于离他最近的开启了定位的祖先元素进行定位的，如果祖先元素都没开启定位，则相对于浏览器窗口。

    - 绝对定位会改变元素的性质，内联会变成块元素。

  - relative 元素开启相对定位

    - 当开启了相对定位以后，而不设置偏移量时，不会产生任何变化。可以通过，left，right，top，bottom四个属性来设置元素的偏移量。

    - left 元素相对于其定位位置的左侧偏移量

    - right 元素相对于其定位位置的右侧偏移量

    - top 元素相对于其定位位置的上侧偏移量

    - bottom 元素相对于其定位位置的底侧偏移量

      - ### 特点

      - 相对定位的元素没有脱离文档流

      - 相对定位会使元素提升一个等级。定位元素会盖住文档流的元素

      - 通常偏移量只使用两个。一般会选择水平方向和垂直方向的偏移量。

      - 相对定位不会改变元素的性质，块元素还是块元素。内联元素还是内联元素

  - fixed 开启元素的固定定位（也是绝对定位的一种）

    - ### 特点

      - 固定定位也是一种绝对定位，它的大部分特点和绝对定位一样。
      - 不同的是：
        - 固定定位永远都是相对于浏览器窗口进行定位
        - 固定定位会固定在浏览器的某个位置，不会随滚动条滚动
        - IE6不支持固定定位

### 元素的层级

- 如果定位元素的层级时一样的，则下面的元素会盖住上面的元素
- 通过z-index属性可以用来设置元素的层级
  - 可以为z-index 指定一个正整数值，该值将会作为当前元素的层级，层级越高，越会优先显示，对于没有开启定位的元素，z-index没有作用。父元素的层级再高，也不会盖住子元素。
- 设置透明属性
  - opacity
    - 可以用来设置透明度，0-1之间的数值。0表示不透明，1表示全透明。
    - opacity这个属性在IE8和以下的不兼容
    - filter：alpha（opacity=50）
      - ie里使用这个属性来设置透明
      - 值  0-100
        - 100 完全不透明

### 背景

- ​	background-image设置背景图片
  - background-image：url（图片地址）
  - 如果图片大于背景尺寸，默认显示图片左上角
  - 如果背景图片和元素一样大，则会完全显示
  - 如果图片小于元素大小，则会默认将背景图片平铺，排满为止
  - 可以为一个元素同时指定背景颜色和背景图片。一般同时设置背景颜色和背景图片。
  - background-repeat
    - 可选值
      - repeat 默认值 双方向重复
      - no-repeat  背景图片不会重复，有多大显示多大
      - repeat-x   背景图片沿x轴重复
      - repeat-y  背景图片沿垂直方向重复
    - 背景图片默认贴着元素的左上角显示，我们有一个属性为background-position可以调整背景图片在元素中的位置
      - 该属性可以使用 top ，right ，left ，bottom ，center。一般使用两个值确认方向。
      - top left 左上
      - bottom right 右下
      - 如果只写一个，另一个值默认为center
    - 也可以指定两个偏移量
      - background-position： 100px 100px  水平方向，垂直方向的偏移
      - 第一个如果是正值，则向右偏移，如果是负值，就是向左偏移。
      - 第二个如果是正值，向下偏移。如果负值。向上偏移。
    - background-attachment
      - 用来设置背景图片是否和页面一起滚动
        - 参数
          - scroll  默认值 背景图片随窗口滚动
          - fixed   固定在某一位置 不随窗口滚动
            - 一般是给body设置，相对于body，背景不会动，可以当做网页的背景图片

​	

### 图片

​	背景图片是以外部资源的形式加载网页，浏览器加载一个外部资源就会发送一个请求。但是我们外部资源不是同时加载。由于加载需要一定的时间，到时背景图片无法显示。



​	为了解决该问题，我们可以将三个图片整合成一张图片，然后将三张图片一起加载，然后再通过background-position来切换显示图片的位置。这种技术叫图片整合技术。

- 优点
  - 提高访问效率，优化用户体验
  - 减小图片的总大小

### 简写属性

通过该属性可以同时设置所有背景相关样式

background：x,x,x,x,x,x,x

​	没有顺序要求

### 表格

在html中使用table创建表格

- 在table中使用tr表示一行 

- 在tr中使用td创建一列

- 合并单元格

  - 横向
    - colspan=2 横向合并2个
  - 纵向
    - rowspan=2 纵向合并2个

- table也是一个块元素

- ## 边框的样式

  - border-spacing
    - 边框的距离
  - border-collapse
    - 可以用来表格表框的合并
    - 如果设置了边框的合并，border-spacing 自动失效
    - th 表头 th就是一个特殊的td
      - 只是有一些默认的效果，居中和加粗

### 长表格

有些情况下表格是非常长的，这时需要把表格分为三个部分，表头，表格和主体，表格底部、在HTML中为我们提供了三个标签：

​	thead 表头

​	tbody 表格主体

​    tfoot 表格的底部

这三个标签的就是区分表格的不同的部分，他们都是table的内容，都需要table的子标签。

​	优点：我们可以为这三个标签去设置样式，thead中的内容永远会在表格的头部，tfoot内容永远在表格的底部，tbody永远呢会在表格的中间。

### 注意：如果页面没有tbody，浏览器会在页面默认添加。添加样式的时候，如果用子代选择器，会出现问题。所以以后写的时候要带上tbody。

### 表格的布局

- 以前我们都是用表格进行布局，但是已经被淘汰。
- 表格的列数由td最多的那一行决定，表格是可以嵌套的。

### 完善clearfix

子元素和父元素相邻的垂直外边距会发生重叠，子元素的外边距会传递给父元素。使用table变迁可以隔离父子元素的外边距，组织外边距重叠。

display：table  可以设置一个元素为表格显示

进过经过修改的clearfix是一个多功能的

​	既可以解决高度塌陷和子元素和父元素的垂直外边距重叠

.clearfix.after,

.clearfix.before{

content:""

dispaly:table

clear:both

zoom:1

}

### 表单

表单就是将用户的信息提交给服务器的

​	比如百度的搜索框，登录，注册

- 创建表单

  - 使用form标签创建一个表单

  - <form action="">
        必须有一个action，该属性指向的是一个服务器地址，当我们提交表单时将会提交到action属性对应的地址
    </form>

  - 使用form创建仅仅是一个空白的表单

    - 我们还需要向form中添加一些表单项

  - 使用input创建一个文本框，它的type属性是text

    - value  也可以在文本框填一个value，该值会作为默认填在框中

  - 使用input创建一个提交按钮，它的type属性submit

    - 如果希望表单项中信息提交到服务器中，还必须给表单项一个name属性，name表示提交内容的名字
    - 在提交按钮中，可以通过value属性值来修改我们按钮上的文字

  - 使用input创建一个密码框，它的type属性值passwd

  - 单选按钮

    - 使用input创建一个单选按钮，type属性设置为radio
    - 我们的单选按钮，通过name属性进行分组，name属性相同的为一组
    - 像需要用户选择但是不需要填写的文本项，还必须指定的value属性，这样被选中的表单项的value属性值将会提交给服务器

  - 多选框

    - 使用input创建一个多选框 ，type属性值为checkbox
    - name属性进行分组
    - value跟单选框一样

  - 下拉列表

    - 使用select创建一个列表
    - 在下拉列表中用option标签来创建一个列表项
    - optgrup
      - 在select中可以使用optgroup对选项进行分组，同一个optgroup中的选项为一组
      - optgroup 有一个属性，可以通过label属性，为分组起一个名字
    - 注意：下拉列表的name属性要给select，value给每个表单项
    - 当为select添加一个mutiple=mutiple，则下拉列表变成一个多选的下拉列表

    如果希望单选按钮或者多选框中某项被选中，可以在该项写个属性checked=checked

    如果希望下拉菜单有默认值，需要使用selected=selected进行设置默认值

  - 使用textarea创建一个文本域

    - 有一个name属性值 

  - 使用input创建一个重置按钮 type值为reset，点击按钮之后，表单里的内容都会回复默认值

  - 使用input创建一个按钮 type值为button

    - 只是一个单纯按钮，只能点。
    - 除了使用input，也可以使用button创建按钮
      - <button><button />,这种方式和input类似，只不过inpu是自结束标签。button

  - 在html中还未我们提供了一个标签，专门用来选中表单中的提示文字。label。label中有一个属性 for，for后面的内容指定一个id值。我们的input框有一个id值，这样一来，就可以不用点击框选中，点击文字也可以选择。

  - firldset

    - 在表单中可以使用firldset来为表单进行分组，可以讲表单的同一组放到一个fieldset中
    - firldset下面还有一个子标签，可以为这个组取个名字。legend，使用legend为标签进行设置名称。

## 框架集

框架集和内联框架的作用类似，都是用于在一个页面中引入外部页面，框架集可以引入多个页面。内联框架只能引入一个。h5

推荐使用框架集。

- 使用frameset来创建一个框架集，frameset和body不能出现在一个页面中。
- frameset使用子标签frame指定要引入的页面
  - <frame src=""><frame />
- frameset 有一个属性rows
  - 指定框架集所有的框架，一行一行的显示
  - cols  一列一列的显示
  - 这两个属性必须选择一个，并且在属性中指定每一部分的大小。
- frameset中也可以嵌套frameset
- frameset和iframe一样，它里面的内容不会被搜索引擎搜索到。使用框架集就意味着页面中不能有自己的内容，只能引外部的页面。引入几个页面，就发几次请求，对用户的体验不好。

### ie6png问题

​	在ie6中，对图片的格式png24支持度不高，如果使用的图片的格式png24，则会导致透明效果无法正常显示

​	解决方法：

1. 使用png8代替，则可解决问题
2. 使用js来解决该问题，需要向页面中引入一个js文件。

### CSS Hack

​		有些情况，有一些代码我们只需要在某些特殊的浏览器中执行，而在其他的浏览器中不需要执行，这是我们可以使用CSS Hack、来解决问题。CSS Hack实际上指的是一个特殊的代码，这段代码只在某些浏览器中可以识别，而其他浏览器不能识别，通过这种方式，来为一些浏览器设置特殊的代码。

<! - -[if IE]>

<![endif]- ->

1. 条件Hack，条件hack只对IE起作用，其他的浏览器都会识别为注释。ie10以上的不支持这种方法。

2. <! - -[if IE 6]>

   <![endif]- ->

   以上代码针对ie6，还可以ie8...

3. <! - -[if  lt IE 9]>

   <![endif]- ->

   小于ie9的，会显示该段代码

   ite  小于等于  gt 表示大于

### 属性hack

1. 在样式前面添加下划线，只有ie6和一下以下才可以识别
2. 添加了*号的样式，只有ie7及以下才可以识别
3. 在样式的后面加\0，则只有ie8及以上才能识别
   1. hack不到万不得已，不推荐使用
4. 在选择器前面使用* html  的样式只有ie6认识