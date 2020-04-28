## JavaScript背景

Web前端有三层：

- HTML：从语义的角度，描述页面**结构**
  
- CSS：从审美的角度，描述**样式**（美化页面）
  
- JavaScript：从交互的角度，描述**行为**（实现业务逻辑和页面控制）

## JavaScript介绍

### JavaScript入门易学性

- JavaScript对初学者比较友好、简单易用。可以使用任何文本编辑工具编写，只需要浏览器就可以执行程序。

- JavaScript是有界面效果的（相比之下，C语言只有白底黑字）。

- JavaScript是**弱变量类型**的语言，变量只需要用 var/let/const 来声明。而Java中变量的声明，要根据变量的类型来定义。

比如Java中需要定义如下变量：

```java
int a;
float a;
double a;
String a;
boolean a;
```

而JavaScript中，只需要用一种方式来定义：

```JavaScript
// ES5 写法
var a;

// ES6 写法
const a;
let a;
```

### JavaScript是前端语言

JavaScript是前端语言，而不是后台语言。

JavaScript运行在用户的终端网页上，而不是服务器上，所以我们称之为“**前端语言**”。就是服务于页面的交互效果、美化，不能操作数据库。

**后台语言**是运行在服务器上的，比如PHP、ASP、JSP等等，这些语言都能够操作数据库，都能够对数据库进行“增删改查”操作。

备注：Node.js是用 JavaScript 开发的，现在也可以基于 Node.js 技术进行服务器端编程。

### JavaScript的组成

JavaScript基础分为三个部分：

- **ECMAScript**：JavaScript 的**语法标准**。包括变量、表达式、运算符、函数、if语句、for语句等。

- **DOM**：Document Object Model（文档对象模型），操作**页面上的元素**的API。比如让盒子移动、变色、改变大小、轮播图等等。

- **BOM**：Browser Object Model（浏览器对象模型），操作**浏览器部分功能**的API。通过BOM可以操作浏览器窗口，比如弹框、控制浏览器跳转、获取浏览器分辨率等等。

通俗理解就是：ECMAScript 是 JS 的语法；DOM 和 BOM 浏览器运行环境为 JS提供的API。

## JavaScript 的特点

### 特点1：解释型语言

JavaScript 是解释型语言，不需要事先被翻译为机器码；而是边翻译边执行（翻译一行，执行一行）。

什么是「解释型语言」？详见下一段。

> 由于少了实现编译这一步骤，所以解释型语言开发起来尤为方便，但是解释型语言运行较慢也是它的劣势。不过解释型语言中使用了JIT技术，使得运行速度得以改善。

### 特点2：单线程

### 特点3：ECMAScript标准

ECMAScript是一种由 ECMA 国际（前身为欧洲计算机制造商协会,英文名称是European Computer Manufacturers Association）制定和发布的脚本语言规范。

JavaScript是由公司开发而成的，问题是不便于其他的公司拓展和使用。所以欧洲的这个ECMA的组织，牵头制定JavaScript的标准，取名为ECMAScript。

简单来说，**ECMAScript不是一门语言，而是一个标准**。ECMAScript 规定了JS的编程语法和基础核心知识，是所有浏览器厂商共同遵守的一套JS语法工业标准。

ECMAScript在2015年6月，发布了ECMAScript 6版本（ES6），语言的能力更强（也包含了很多新特性）。但是，浏览器的厂商不会那么快去追上这个标准，需要时间。

## 开始写第一行JavaScript代码

> JavaScript 代码的书写位置在哪里呢？这个问题，也可以理解成：引入 js 代码，有哪几种方式。

### 方式1：行内式

**代码举例**：

```javascript
<input type="button" value="点我点我" onclick="alert('千古壹号')" />
```

完整的可执行代码如下：

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <title>Document</title>
    </head>
    <body>
        <input type="button" value="点我点我" onclick="alert('千古壹号的方式1')" />
    </body>
</html>

```

**分析**：

- 可以将单行或少量 JS 代码写在HTML标签的事件属性中（以 on 开头的属性），比如放在上面的 `onclick`点击事件中。

- 这种书写方式，不推荐使用，原因是：可读性差，尤其是需要编写大量 JS代码时，容易出错；引号多层嵌套时，也容易出错。

- 关于代码中的「引号」，在HTML标签中，我们推荐使用双引号, JS 中我们推荐使用单引号。

### 方式2、内嵌式

我们可以在html 页面的 `<body>` 标签里放入`<script type=”text/javascript”></script>`标签对儿，并在`<script>`里书写JavaScript 代码：

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<script type="text/javascript">
		// 在这里写 js 代码
		alert('千古壹号的方式2');
		console.log('qianguyihao 方式2');
	</script>
</body>
</html>
```

**分析**：

- text表示纯文本，因为JavaScript也是一个纯文本的语言。

- 可以将多行JS代码写到 `<script>` 标签中。

- 内嵌式 JS 是学习时常用的方式。

### 方式3：引入外部的 JS 文件

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
</head>
<body>
	<!-- 引入外部的 js 文件 -->
	<script src="tool.js"></script>
</body>
</html>
```

上面这段代码，依然是放到body标签里，可以和内嵌的js代码并列。

另外，引用外部 JS文件的 script 标签中间不可以再写代码。

**总结**：

我们在实战开发中，基本都是采用方式3，因为这种方式，可以确保 html 文件和 js 文件是分开的，有利于代码的结构化和复用。很少会有人把一大堆 js 代码塞到 html 文件里。

## JS一些简单的语法规则

学习程序，是有规律可循的，程序会有有相同的部分，这些部分就是一种规定，不能更改，我们成为：语法。

（1）JavaScript对换行、缩进、空格不敏感。每一条语句以分号结尾。

也就是说：

代码一：

```html
<script type="text/javascript">
	alert("今天蓝天白云");
	alert("我很高兴");
</script>
```

等价于代码二：

```html
<script type="text/javascript">
	alert("今天蓝天白云");alert("我很高兴");
</script>
```

备注：每一条语句末尾要加上分号，虽然分号不是必须加的，如果不写分号，浏览器会自动添加，但是会消耗一些系统资源。

（2）所有的符号，都是英语的。比如**括号**、引号、分号。

如果你用的是搜狗拼音，**建议不要用shift切换中英文**（可以在搜狗软件里进行设置），不然很容易输入中文的分号；建议用ctrl+space切换中英文输入法。

（3）严格区分大小写。

## 注释

我们不要把 HTML、CSS、JavaScript三者的注释格式搞混淆了。

### HTML 的注释

```html
<!-- 我是注释  -->
```

### CSS的注释

```html
<style type="text/css">

	/*
		我是注释
	*/

	p{
		font-weight: bold;
		font-style: italic;
		color: red;
	}

</style>
```

注意：CSS只有`/*  */`这种注释，没有`//`这种注释。而且注释要写在`<style>`标签里面才算生效哦。

### JavaScript 的注释

单行注释：

```
// 我是注释
```

多行注释：

```
/*
	多行注释1
	多行注释2
*/
```

补充：VS Code中，单行注释的快捷键是「Ctrl + /」，多行注释的默认快捷键是「Alt + Shift + A」。

当然，如果你觉得多行注释的默认快捷键不方便，我们还可以修改默认快捷键。操作如下：

VS Code --> 首选项 --> 键盘快捷方式 --> 查找“注释”这两个字 --> 将原来的快捷键修改为「Ctrl + Shift + /」。