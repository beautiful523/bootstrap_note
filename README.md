# bootstrap_note
这是bootstrap的学习笔记
### 学习资料
bootstrap中文网 http://www.bootcss.com/
### bootstrap定义
是一种HTML，CSS，JS框架
用于开发响应式布局，移动设备优先的WEB项目
### 引用bootstrap
```

<!-- 最新版本的 Bootstrap 核心 CSS 文件 -->
<link rel="stylesheet" href="https://cdn.bootcss.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">

<!-- 可选的 Bootstrap 主题文件（一般不用引入） -->
<link rel="stylesheet" href="https://cdn.bootcss.com/bootstrap/3.3.7/css/bootstrap-theme.min.css" integrity="sha384-rHyoN1iRsVXV4nD0JutlnGaslCJuC7uwjduW9SVrLvRYooPp2bWYgmgJQIXwl/Sp" crossorigin="anonymous">

<!-- 最新的 Bootstrap 核心 JavaScript 文件 -->
<script src="https://cdn.bootcss.com/bootstrap/3.3.7/js/bootstrap.min.js" integrity="sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa" crossorigin="anonymous"></script>
```
### 预编译版
bootstrap的基本文件结构：
```

bootstrap/
├── css/
│   ├── bootstrap.css
│   ├── bootstrap.css.map
│   ├── bootstrap.min.css （min是压缩的）
│   ├── bootstrap.min.css.map （map是源码映射表）
│   ├── bootstrap-theme.css
│   ├── bootstrap-theme.css.map
│   ├── bootstrap-theme.min.css
│   └── bootstrap-theme.min.css.map
├── js/
│   ├── bootstrap.js
│   └── bootstrap.min.js
└── fonts/
    ├── glyphicons-halflings-regular.eot
    ├── glyphicons-halflings-regular.svg
    ├── glyphicons-halflings-regular.ttf
    ├── glyphicons-halflings-regular.woff
    └── glyphicons-halflings-regular.woff2

```
### bootstrap源码结构
```
bootstrap/
├── less/ （这是CSS源码）
├── js/  （这是JS源码）
├── fonts/ （这是字体图标源码）
├── dist/ （这是预编译内容）
│   ├── css/
│   ├── js/
│   └── fonts/
└── docs/ （包含所有文件的源码文件）
    └── examples/ （官方提供的实例）

```

### 注意
Bootstrap 的所有 JavaScript 插件都依赖 jQuery，因此 jQuery 必须在 Bootstrap 之前引入
### 基本模板
```
<!-- 声明文档类型 为 html5 -->
<!DOCTYPE html>
<!-- 声明页面内容主要为 中文简体 -->
<html lang="zh-CN">
  <head>
    <!-- 声明页面编码 为 utf-8 -->
    <meta charset="utf-8">
    <!-- X-UA-Compatible 浏览器兼容模式 这是个是IE8的专用标记,
    用来指定IE8浏览器去模拟某个特定版本的IE浏览器的渲染方式(比如人见人烦的IE6)，以此来解决部分兼容问题
     详情见 http://www.cnblogs.com/lovecode/articles/3377505.html-->
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <!-- 申明viewport 视口属性设置，只有在移动端才识别
    其中属性有width = device-width 视口宽度等于 设备宽度
    initial-scale = 1.0 初始化 缩放比为1：1 也就是等比显示
    还有其他的属性：
    user-scalable = 0 ;可选值1,0, 或 yes, no
    用户是否允许缩放。
    maximum = 1.0 最大缩放比
    minimum = 1.0 最小缩放比
    -->
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- 上述3个meta标签*必须*放在最前面，任何其他内容都*必须*跟随其后！ -->
    <title>Bootstrap 101 Template</title>

    <!-- Bootstrap -->
    <link href="css/bootstrap.min.css" rel="stylesheet">

    <!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
    <!-- WARNING: Respond.js doesn't work if you view the page via file:// -->
    <!-- respond 异步加载的 本地打开 不生效 需要使用服务器，例如在 Apache 上打开-->
    <!-- 只有IE才识别的注释 -->
    <!-- 不支持h5标签的浏览器需要引用 html5shiv.js 包 -->
    <!-- 不支持媒体查询的浏览器 需引入 respond.js 包 -->
    <!--[if lt IE 9]>
      <script src="https://cdn.bootcss.com/html5shiv/3.7.3/html5shiv.min.js"></script>
      <script src="https://cdn.bootcss.com/respond.js/1.4.2/respond.min.js"></script>
    <![endif]-->
  </head>
  <body>
    <h1>你好，世界！</h1>
    <script src="https://cdn.bootcss.com/jquery/1.12.4/jquery.min.js"></script>
    <script src="js/bootstrap.min.js"></script>
  </body>
</html>
```
### webstorm安装
1. 官网下载: http://www.jetbrains.com/webstorm/download/ 
2. 终端输入:  sudo apt-get install default-jdk
3. 解压运行:  tar ....  sh ....

#### 注意
在webstorm打开项目时项目要是一个文件夹，而不是一个单独的html文件，不然会找不到路径，报404
### 布局容器：.container和，.container-fluid
- .container用于固定宽度并支持响应式布局的容器。宽度是一个固定数字，哪怕父元素宽度比这个小也不变，只随屏幕调整，如果直接修改内联样式才会改变宽度
- .container-fluid用于100%宽度的容器。宽度是父元素的100%，没有父元素就是随视口变化

### 栅格系统：row 和 column
- 行与列必须包含在.container或.container-fluid中
- 通过行在水平方向创建一组列，列是行的直接子元素，内容放在列中
- 通过为列设置padding创建列间隔，通过为行设置负值margin来抵消.container的padding
- 列通过指定1到12的值来表示跨越的范围，三个等宽的列.col-xs-4,总跨度大于12另起一行

### 栅格系统的一些参数
1. 栅格系统排列行为是按照类前缀来区分的（屏幕大小手动调整，例如大屏幕一般大于1200px，我的屏幕2495px,在全屏时都是排一行，.col-lg手动调整到小于1200px时每行一列）：
    - .col-xs-：总是水平排列，随着屏幕变小列宽变小，屏幕再小（小于360px）时一行排不下到下一行；
    - .col-sm-：媒体查询大于等于768px时水平排列，小于768px时sm水平排列失效(如果同时有小的类按小的水平排列，没有就每行一列)
    - .col-md-：媒体查询大于等于992px时水平排列，小于992px时md水平排列失效(如果同时有小的类按小的水平排列，没有就每行一列)
    - .col-lg-：媒体查询大于等于1200px时水平排列，小于1200px时lg水平排列失效(如果同时有小的类按小的水平排列，没有就每行一列)
    - 以上类的优先级递增
1. .container的最大宽度是根据设备变化的
    - 手机（0-768px） .container最大值自动
    - 平板[768-?] .container最大值750px
    - 桌面显示器[970-?]  .container最大值970px
    - 大桌面显示器[1170-?]  .container最大值1170px
1. 列的最大宽度是根据设备变化的
    - 手机（0-768px） 列宽最大值自动
    - 平板[768-?] 列宽最大值62px
    - 桌面显示器[970-?]  列宽最大值81px
    - 大桌面显示器[1170-?]  列宽最大值97px
1. 槽宽
    - 30px，每列左右各15px

### 流式布局容器
布局元素为.container-fluid
### 媒体查询
```
/* 超小屏幕（手机，小于 768px） */
/* 没有任何媒体查询相关的代码，因为这在 Bootstrap 中是默认的（还记得 Bootstrap 是移动设备优先的吗？） */

/* 小屏幕（平板，大于等于 768px） */
@media (min-width: @screen-sm-min) { ... }

/* 中等屏幕（桌面显示器，大于等于 992px） */
@media (min-width: @screen-md-min) { ... }

/* 大屏幕（大桌面显示器，大于等于 1200px） */
@media (min-width: @screen-lg-min) { ... }
```
### 响应式列重置
不知道啥意思
### 列偏移:.col-md-offset-*
.col-md-offset-4 类将元素向右侧偏移了4个列（column）的宽度
### 列排序
col-md-push-3将元素往右移3
### Less mixin 和变量
不知道啥意思
### 标题
标题：.h1 .h6
副标题：<small></small> 或者 .small 是h1的副标签则写成h1的子元素
### 页面主体
Bootstrap 将全局 font-size 设置为 14px，line-height 设置为 1.428。这些属性直接赋予 <body> 元素和所有段落元素。另外，<p> （段落）元素还被设置了等于 1/2 行高（即 10px）的底部外边距（margin）。
### 中心内容
通过添加 .lead 类可以让段落突出显示。
### 标记文本
``<mark></mark>``
### 删除文本
``<del></del>``
### 无用文本
``<s></s>``
### 插入文本
``<ins></ins>``
### 下划线文本
``<u></u>``
### 小号文本
使用 <small> 标签包裹，其内的文本将被设置为父容器字体大小的 85%。标题元素中嵌套的 <small> 元素被设置不同的 font-size 。
你还可以为行内元素赋予 .small 类以代替任何 <small> 元素。
### 着重
``<strong></strong>``
### 斜体
``<em></em>``
### 文本对齐
```

<p class="text-left">Left aligned text.</p>
<p class="text-center">Center aligned text.</p>
<p class="text-right">Right aligned text.</p>
<p class="text-justify">Justified text.</p>
<p class="text-nowrap">No wrap text.</p>

```
### 大小写
```

<p class="text-lowercase">Lowercased text.</p>
<p class="text-uppercase">Uppercased text.</p>
<p class="text-capitalize">Capitalized text.</p>

```
### 缩略语
缩略语元素带有 title 属性，外观表现为带有较浅的虚线框，鼠标移至上面时会变成带有“问号”的指针。如想看完整的内容可把鼠标悬停在缩略语上（对使用辅助技术的用户也可见）, 但需要包含 title 属性。
```angular2html
An abbreviation of the word attribute is<abbr title="attribute">attr</abbr>
```
### 首字母缩略语
为缩略语添加 .initialism 类，可以让 font-size 变得稍微小些。
```angular2html
<abbr title="HyperText Markup Language" class="initialism">HTML</abbr><abbr title="HyperText Markup Language" class="initialism">HTML</abbr> is the best thing since sliced bread.
```
### 地址
让联系信息以最接近日常使用的格式呈现
```angular2html
<address></address>
```
### 引用
```angular2html

<!--引用-->
<blockquote>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
    <!--引用来源-->
    <footer>Someone famous in <cite title="Source Title">Source Title</cite></footer>
</blockquote>
<!--引用右对齐-->
<blockquote class="blockquote-reverse">
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
    <footer>Someone famous in <cite title="Source Title">Source Title</cite></footer>
</blockquote>
```
### 列表
无序列表
```angular2html

<ul>
  <li>...</li>
</ul>
```
有序列表
```angular2html

<ol>
  <li>...</li>
</ol>
```
无样式列表
```angular2html

<ul class="list-unstyled">
  <li>...</li>
</ul>
```
内联列表
```angular2html

<ul class="list-inline">
  <li>...</li>
</ul>
```
描述列表
```angular2html

<dl>
  <dt>...</dt>
  <dd>...</dd>
</dl>
```
水平排列的描述
```angular2html

.dl-horizontal 可以让 <dl> 内的短语及其描述排在一行。开始是像 <dl> 的默认样式堆叠在一起，随着导航条逐渐展开而排列在一行。

<dl class="dl-horizontal">
  <dt>...</dt>
  <dd>...</dd>
</dl> 
```
### 代码
内联代码

```For example, <code>&lt;section&gt;</code> should be wrapped as inline.```

用户键盘输入
```angular2html

To switch directories, type <kbd>cd</kbd> followed by the name of the directory.<br>
To edit settings, press <kbd><kbd>ctrl</kbd> + <kbd>,</kbd></kbd>
```
代码块，注意将尖括号做转义处理
```angular2html

<pre>&lt;p&gt;Sample text here...&lt;/p&gt;</pre>
```
变量

```angular2html

<var>y</var> = <var>m</var><var>x</var> + <var>b</var>
```
程序输出

```angular2html

<samp>This text is meant to be treated as sample output from a computer program.</samp>
```
### 表格
基本表格
```angular2html

<table class="table">
  ...
</table>
```
条纹状表格
```angular2html

<table class="table table-striped">
  ...
</table>
```
带边框的表格
```angular2html

<table class="table table-bordered">
  ...
</table>
```
鼠标停悬
```angular2html

<table class="table table-hover">
  ...
</table>
```
紧缩表格
```angular2html

<table class="table table-condensed">
  ...
</table>
```
状态类设置颜色
```angular2html

<!-- On rows -->
<tr class="active">...</tr>
<tr class="success">...</tr>
<tr class="warning">...</tr>
<tr class="danger">...</tr>
<tr class="info">...</tr>

<!-- On cells (`td` or `th`) -->
<tr>
  <td class="active">...</td>
  <td class="success">...</td>
  <td class="warning">...</td>
  <td class="danger">...</td>
  <td class="info">...</td>
</tr>
```
响应式表格
```angular2html

将任何 .table 元素包裹在 .table-responsive 元素内，即可创建响应式表格，其会在小屏幕设备上（小于768px）水平滚动。当屏幕大于 768px 宽度时，水平滚动条消失。

<div class="table-responsive">
  <table class="table">
    ...
  </table>
</div>
```
### 表单
基本实例
```angular2html

单独的表单控件会被自动赋予一些全局样式。所有设置了 .form-control 类的 <input>、<textarea> 和 <select> 元素都将被默认设置宽度属性为 width: 100%;。 将 label 元素和前面提到的控件包裹在 .form-group 中可以获得最好的排列。
```
```angular2html

<form>
  <div class="form-group">
    <label for="exampleInputEmail1">Email address</label>
    <input type="email" class="form-control" id="exampleInputEmail1" placeholder="Email">
  </div>
  <div class="form-group">
    <label for="exampleInputPassword1">Password</label>
    <input type="password" class="form-control" id="exampleInputPassword1" placeholder="Password">
  </div>
  <div class="form-group">
    <label for="exampleInputFile">File input</label>
    <input type="file" id="exampleInputFile">
    <p class="help-block">Example block-level help text here.</p>
  </div>
  <div class="checkbox">
    <label>
      <input type="checkbox"> Check me out
    </label>
  </div>
  <button type="submit" class="btn btn-default">Submit</button>
</form>
```
内联表单

```
为 <form> 元素添加 .form-inline 类可使其内容左对齐并且表现为 inline-block 级别的控件。只适用于视口（viewport）至少在 768px 宽度时（视口宽度再小的话就会使表单折叠）。
在内联表单，我们将这些元素的宽度设置为 width: auto;，因此，多个控件可以排列在同一行

```
```angular2html

<form class="form-inline">
  <div class="form-group">
    <label for="exampleInputName2">Name</label>
    <input type="text" class="form-control" id="exampleInputName2" placeholder="Jane Doe">
  </div>
  <div class="form-group">
    <label for="exampleInputEmail2">Email</label>
    <input type="email" class="form-control" id="exampleInputEmail2" placeholder="jane.doe@example.com">
  </div>
  <button type="submit" class="btn btn-default">Send invitation</button>
</form>
```
```angular2html

<form class="form-inline">
  <div class="form-group">
    <label class="sr-only" for="exampleInputEmail3">Email address</label>
    <input type="email" class="form-control" id="exampleInputEmail3" placeholder="Email">
  </div>
  <div class="form-group">
    <label class="sr-only" for="exampleInputPassword3">Password</label>
    <input type="password" class="form-control" id="exampleInputPassword3" placeholder="Password">
  </div>
  <div class="checkbox">
    <label>
      <input type="checkbox"> Remember me
    </label>
  </div>
  <button type="submit" class="btn btn-default">Sign in</button>
</form>
```
```angular2html

<form class="form-inline">
  <div class="form-group">
    <label class="sr-only" for="exampleInputAmount">Amount (in dollars)</label>
    <div class="input-group">
      <div class="input-group-addon">$</div>
      <input type="text" class="form-control" id="exampleInputAmount" placeholder="Amount">
      <div class="input-group-addon">.00</div>
    </div>
  </div>
  <button type="submit" class="btn btn-primary">Transfer cash</button>
</form>

```
水平排列的表单
```angular2html

通过为表单添加 .form-horizontal 类，并联合使用 Bootstrap 预置的栅格类，可以将 label 标签和控件组水平并排布局。这样做将改变 .form-group 的行为，使其表现为栅格系统中的行（row），因此就无需再额外添加 .row 了。
```
```angular2html

<form class="form-horizontal">
  <div class="form-group">
    <label for="inputEmail3" class="col-sm-2 control-label">Email</label>
    <div class="col-sm-10">
      <input type="email" class="form-control" id="inputEmail3" placeholder="Email">
    </div>
  </div>
  <div class="form-group">
    <label for="inputPassword3" class="col-sm-2 control-label">Password</label>
    <div class="col-sm-10">
      <input type="password" class="form-control" id="inputPassword3" placeholder="Password">
    </div>
  </div>
  <div class="form-group">
    <div class="col-sm-offset-2 col-sm-10">
      <div class="checkbox">
        <label>
          <input type="checkbox"> Remember me
        </label>
      </div>
    </div>
  </div>
  <div class="form-group">
    <div class="col-sm-offset-2 col-sm-10">
      <button type="submit" class="btn btn-default">Sign in</button>
    </div>
  </div>
</form>
```
输入框
```angular2html

包括大部分表单控件、文本输入域控件，还支持所有 HTML5 类型的输入控件： text、password、datetime、datetime-local、date、month、time、week、number、email、url、search、tel 和 color。
只有正确设置了 type 属性的输入控件才能被赋予正确的样式。
```
```angular2html

<input type="text" class="form-control" placeholder="Text input">
```
文本域
```angular2html

<textarea class="form-control" rows="3"></textarea>
```
多选和单选框

```angular2html

<div class="checkbox">
  <label>
    <input type="checkbox" value="">
    Option one is this and that&mdash;be sure to include why it's great
  </label>
</div>
<div class="checkbox disabled">
  <label>
    <input type="checkbox" value="" disabled>
    Option two is disabled
  </label>
</div>

<div class="radio">
  <label>
    <input type="radio" name="optionsRadios" id="optionsRadios1" value="option1" checked>
    Option one is this and that&mdash;be sure to include why it's great
  </label>
</div>
<div class="radio">
  <label>
    <input type="radio" name="optionsRadios" id="optionsRadios2" value="option2">
    Option two can be something else and selecting it will deselect option one
  </label>
</div>
<div class="radio disabled">
  <label>
    <input type="radio" name="optionsRadios" id="optionsRadios3" value="option3" disabled>
    Option three is disabled
  </label>
</div>
```
内联单选和多选框
```angular2html

<label class="checkbox-inline">
  <input type="checkbox" id="inlineCheckbox1" value="option1"> 1
</label>
<label class="checkbox-inline">
  <input type="checkbox" id="inlineCheckbox2" value="option2"> 2
</label>
<label class="checkbox-inline">
  <input type="checkbox" id="inlineCheckbox3" value="option3"> 3
</label>

<label class="radio-inline">
  <input type="radio" name="inlineRadioOptions" id="inlineRadio1" value="option1"> 1
</label>
<label class="radio-inline">
  <input type="radio" name="inlineRadioOptions" id="inlineRadio2" value="option2"> 2
</label>
<label class="radio-inline">
  <input type="radio" name="inlineRadioOptions" id="inlineRadio3" value="option3"> 3
</label>
```
不带label文本的Checkbox和radio
```angular2html

<div class="checkbox">
  <label>
    <input type="checkbox" id="blankCheckbox" value="option1" aria-label="...">
  </label>
</div>
<div class="radio">
  <label>
    <input type="radio" name="blankRadio" id="blankRadio1" value="option1" aria-label="...">
  </label>
</div>
```
下拉列表
```angular2html

<select class="form-control">
  <option>1</option>
  <option>2</option>
  <option>3</option>
  <option>4</option>
  <option>5</option>
</select>
```
标记了multiple属性的select默认显示多选项
```angular2html

<select multiple class="form-control">
  <option>1</option>
  <option>2</option>
  <option>3</option>
  <option>4</option>
  <option>5</option>
</select>
```
静态控件
```angular2html

如果需要在表单中将一行纯文本和label元素放置于同一行，为p元素添加.form-control-static类即可
<form class="form-horizontal">
  <div class="form-group">
    <label class="col-sm-2 control-label">Email</label>
    <div class="col-sm-10">
      <p class="form-control-static">email@example.com</p>
    </div>
  </div>
  <div class="form-group">
    <label for="inputPassword" class="col-sm-2 control-label">Password</label>
    <div class="col-sm-10">
      <input type="password" class="form-control" id="inputPassword" placeholder="Password">
    </div>
  </div>
</form>
```
焦点状态
```angular2html

表单控件的默认outline样式被移除，然后对：focus状态赋予box-shadow属性
```

禁用状态
```angular2html

<input class="form-control" id="disabledInput" type="text" placeholder="Disabled input here..." disabled>
```

被禁用的feildset
```angular2html
为feildset标签设置disabled属性，可以禁用标签内的所有控件
<form>
  <fieldset disabled>
    <div class="form-group">
      <label for="disabledTextInput">Disabled input</label>
      <input type="text" id="disabledTextInput" class="form-control" placeholder="Disabled input">
    </div>
    <div class="form-group">
      <label for="disabledSelect">Disabled select menu</label>
      <select id="disabledSelect" class="form-control">
        <option>Disabled select</option>
      </select>
    </div>
    <div class="checkbox">
      <label>
        <input type="checkbox"> Can't check this
      </label>
    </div>
    <button type="submit" class="btn btn-primary">Submit</button>
  </fieldset>
</form>
```
只读状态
```angular2html
为输入框设置 readonly 属性可以禁止用户修改输入框中的内容。处于只读状态的输入框颜色更浅（就像被禁用的输入框一样），但是仍然保留标准的鼠标状态。
<input class="form-control" type="text" placeholder="Readonly input here…" readonly>
```

校验状态
```angular2html

Bootstrap 对表单控件的校验状态，如 error、warning 和 success 状态，都定义了样式。使用时，添加 .has-warning、.has-error 或 .has-success 类到这些控件的父元素即可。任何包含在此元素之内的 .control-label、.form-control 和 .help-block 元素都将接受这些校验状态的样式。


<div class="form-group has-success">
  <label class="control-label" for="inputSuccess1">Input with success</label>
  <input type="text" class="form-control" id="inputSuccess1" aria-describedby="helpBlock2">
  <span id="helpBlock2" class="help-block">A block of help text that breaks onto a new line and may extend beyond one line.</span>
</div>
<div class="form-group has-warning">
  <label class="control-label" for="inputWarning1">Input with warning</label>
  <input type="text" class="form-control" id="inputWarning1">
</div>
<div class="form-group has-error">
  <label class="control-label" for="inputError1">Input with error</label>
  <input type="text" class="form-control" id="inputError1">
</div>
<div class="has-success">
  <div class="checkbox">
    <label>
      <input type="checkbox" id="checkboxSuccess" value="option1">
      Checkbox with success
    </label>
  </div>
</div>
<div class="has-warning">
  <div class="checkbox">
    <label>
      <input type="checkbox" id="checkboxWarning" value="option1">
      Checkbox with warning
    </label>
  </div>
</div>
<div class="has-error">
  <div class="checkbox">
    <label>
      <input type="checkbox" id="checkboxError" value="option1">
      Checkbox with error
    </label>
  </div>
</div>
```
添加额外的图标
```angular2html

可以针对校验状态为输入框添加额外的图标。只需设置相应的 .has-feedback 类并添加正确的图标即可。

反馈图标（feedback icon）只能使用在文本输入框 <input class="form-control"> 元素上。
<div class="form-group has-success has-feedback">
  <label class="control-label" for="inputSuccess2">Input with success</label>
  <input type="text" class="form-control" id="inputSuccess2" aria-describedby="inputSuccess2Status">
  <span class="glyphicon glyphicon-ok form-control-feedback" aria-hidden="true"></span>
  <span id="inputSuccess2Status" class="sr-only">(success)</span>
</div>
<div class="form-group has-warning has-feedback">
  <label class="control-label" for="inputWarning2">Input with warning</label>
  <input type="text" class="form-control" id="inputWarning2" aria-describedby="inputWarning2Status">
  <span class="glyphicon glyphicon-warning-sign form-control-feedback" aria-hidden="true"></span>
  <span id="inputWarning2Status" class="sr-only">(warning)</span>
</div>
<div class="form-group has-error has-feedback">
  <label class="control-label" for="inputError2">Input with error</label>
  <input type="text" class="form-control" id="inputError2" aria-describedby="inputError2Status">
  <span class="glyphicon glyphicon-remove form-control-feedback" aria-hidden="true"></span>
  <span id="inputError2Status" class="sr-only">(error)</span>
</div>
<div class="form-group has-success has-feedback">
  <label class="control-label" for="inputGroupSuccess1">Input group with success</label>
  <div class="input-group">
    <span class="input-group-addon">@</span>
    <input type="text" class="form-control" id="inputGroupSuccess1" aria-describedby="inputGroupSuccess1Status">
  </div>
  <span class="glyphicon glyphicon-ok form-control-feedback" aria-hidden="true"></span>
  <span id="inputGroupSuccess1Status" class="sr-only">(success)</span>
</div>
```
控件尺寸
```angular2html

通过 .input-lg 类似的类可以为控件设置高度，通过 .col-lg-* 类似的类可以为控件设置宽度
<input class="form-control input-lg" type="text" placeholder=".input-lg">
<input class="form-control" type="text" placeholder="Default input">
<input class="form-control input-sm" type="text" placeholder=".input-sm">

<select class="form-control input-lg">...</select>
<select class="form-control">...</select>
<select class="form-control input-sm">...</select>
```
### 按钮
```angular2html

<a class="btn btn-default" href="#" role="button">Link</a>
<button class="btn btn-default" type="submit">Button</button>
<input class="btn btn-default" type="button" value="Input">
<input class="btn btn-default" type="submit" value="Submit">
```
### 预定义样式按钮
```angular2html



<!-- Standard button -->
<button type="button" class="btn btn-default">（默认样式）Default</button>

<!-- Provides extra visual weight and identifies the primary action in a set of buttons -->
<button type="button" class="btn btn-primary">（首选项）Primary</button>

<!-- Indicates a successful or positive action -->
<button type="button" class="btn btn-success">（成功）Success</button>

<!-- Contextual button for informational alert messages -->
<button type="button" class="btn btn-info">（一般信息）Info</button>

<!-- Indicates caution should be taken with this action -->
<button type="button" class="btn btn-warning">（警告）Warning</button>

<!-- Indicates a dangerous or potentially negative action -->
<button type="button" class="btn btn-danger">（危险）Danger</button>

<!-- Deemphasize a button by making it look like a link while maintaining button behavior -->
<button type="button" class="btn btn-link">（链接）Link</button>
```
### 按钮尺寸
```angular2html

<p>
  <button type="button" class="btn btn-primary btn-lg">（大按钮）Large button</button>
  <button type="button" class="btn btn-default btn-lg">（大按钮）Large button</button>
</p>
<p>
  <button type="button" class="btn btn-primary">（默认尺寸）Default button</button>
  <button type="button" class="btn btn-default">（默认尺寸）Default button</button>
</p>
<p>
  <button type="button" class="btn btn-primary btn-sm">（小按钮）Small button</button>
  <button type="button" class="btn btn-default btn-sm">（小按钮）Small button</button>
</p>
<p>
  <button type="button" class="btn btn-primary btn-xs">（超小尺寸）Extra small button</button>
  <button type="button" class="btn btn-default btn-xs">（超小尺寸）Extra small button</button>
</p>
```
通过给按钮添加 .btn-block 类可以将其拉伸至父元素100%的宽度，而且按钮也变为了块级（block）元素。
```angular2html

<button type="button" class="btn btn-primary btn-lg btn-block">（块级元素）Block level button</button>
<button type="button" class="btn btn-default btn-lg btn-block">（块级元素）Block level button</button>
```
### 按钮激活状态.active
### 按钮禁用状态.disabled
### 图片
响应式图片
```angular2html

 .img-responsive 类可以让图片支持响应式布局。其实质是为图片设置了 max-width: 100%;、 height: auto; 和 display: block; 属性，从而让图片在其父元素中更好的缩放。

如果需要让使用了 .img-responsive 类的图片水平居中，请使用 .center-block 类
```
图片形状
```angular2html

<img src="..." alt="..." class="img-rounded">
<img src="..." alt="..." class="img-circle">
<img src="..." alt="..." class="img-thumbnail">
```
情境文本颜色，通过颜色来展示意图
```angular2html

<p class="text-muted">...</p>
<p class="text-primary">...</p>
<p class="text-success">...</p>
<p class="text-info">...</p>
<p class="text-warning">...</p>
<p class="text-danger">...</p>
```
情境背景色
```angular2html

<p class="bg-primary">...</p>
<p class="bg-success">...</p>
<p class="bg-info">...</p>
<p class="bg-warning">...</p>
<p class="bg-danger">...</p>
```
### 关闭按钮
```angular2html

<button type="button" class="close" aria-label="Close"><span aria-hidden="true">&times;</span></button>
```

### 下拉三角符号
```angular2html

<span class="caret"></span>
```
### 快速浮动

```angular2html

<div class="pull-left">...</div>
<div class="pull-right">...</div>
```
### 让内容块居中
```angular2html

<div class="center-block">...</div>
```
### 清除浮动
```angular2html

<div class="clearfix">...</div>
```
### 显示和隐藏
```angular2html

<div class="show">...</div>
<div class="hidden">...</div>
```
### 响应式工具
以下类可以针对不同屏幕尺寸隐藏或显示页面内容
.visible-xs-*
.visible-sm-*
.visible-md-*
.visible-lg-*
.hidden-xs
.hidden-sm
.hidden-md
.hidden-lg
.visible-*-block
.visible-*-inline
.visible-*-inline-block
以下的类可以针对打印机隐藏或显示某些内容
.visible-print-block
.visible-print-inline
.visible-print-inline-block
.hidden-print
# 还可补充“组件”，“JS插件”






