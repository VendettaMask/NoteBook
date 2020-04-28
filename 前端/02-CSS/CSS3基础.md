## CSS3基础
### CSS3编程语言化
有人开发了一些扩展CSS功能的写法，比如less,sass,其目的是让css能支持一些编程语言才有的功能，比如:

表达式，函数，变量，循环，判断.

有这些功能就能方便重复定义，写css时省事.举以下例子.
```
var colorRed {color:red}//用var定义一个字体颜色变量样式
//定义一个新闻列表样式
.news-list{
  font-size:12px;
  line-height:1.76;
  color:@colorRed;
  //这里文字颜色引用自变量 var colorRed
}
```
上面这段扩展css语言的写法里面有变量，然而浏览器的css解析引擎是不认识css里面的var这些东西的，这就是一个无效的css，所以这些扩展css的语言有预处理器，作用是把上面这段浏览器不认识的代码，还原为浏览器认识的CSS标准发给浏览器解析.
如下：
```
.news-list{
  font-size:12px;
  line-height:1.76;
  color:red;
}
```
### CSS命名规范-BEM
