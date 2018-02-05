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
# 学到了全局CSS样式