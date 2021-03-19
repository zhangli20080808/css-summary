# 专题一: 掌握HTML(5)和CSS(3)语言核心

> 大纲目录:  
> - HTML语义: 学会如何写出更优的html
> - HTML及扩展: Doctype、Meta、Entity、DTD、XML、namespace、SVG、MathML
> - CSS绘制: linear-gradient，radial-gradient、background、box-shadow，text-shadow、border-radius、Filter , clip-path，Counter等
> - CSS机制at-rule: @charset、@import、@namespace、@document、@font-face、@keyframes、@media、@page、@supports
> - CSS变量var的使用

<a name="Cwzd4"></a>
## HTML语义: 学会如何写出更优的html
> 超文本标记语言（英语：HyperText Markup Language，简称：HTML）是一种用于创建网页的标准标记语言。
> <br />
> **常用的html(5)标签汇总: **
> HTML4: 
> - 基本文档：html、head、body...
> - 基本标签:  h1-h6、p、br、hr、[<!--...-->](https://www.runoob.com/tags/tag-comment.html)..
> - 文本格式化：strong、b、em、i、small、strong、del、sub、sup...
> - 链接: a、link
> - 图片: img、map、area
> - 区块: div、span
> - 三大列表: ul li 、ol li、dl dt dd
> - 表格 table、caption、th、tr、td、thead、tbody、tfoot
> - 框架 iframe
> - 表单: form、input、select option、textarea、button、label
> - 实体: &lt、&gt、&copy、&nbsp...
> 
<br />
> HTML5:
> - 图形新元素：canvas
> - 新多媒体元素: audio、video、source、embed、track
> - 新表单元素: deatalist、keygen、output
> - 新的语义和结构元素: article、aside、bdi、command、details、dialog、summary、figure、figcaption、footer、header、mark、meter、nav、progress、ruby、rt、rp、section、time、wbr
> 
<br />
> **语义化含义和好处：**
> 含义:  指对文本内容的结构化（内容语义化），选择合乎语义的标签（代码语义化），便于开发者阅读，维护和写出更优雅的代码的同时，让浏览器的爬虫和辅助技术更好的解析 (通俗理解: 用正确的标签做正确的事)
> 

> 通过使用恰当语义的HTML标签，让页面具有良好的结构与含义，可以有效提高：
> - 可访问性：帮助辅助技术更好的阅读和转译你的网页，利于无障碍阅读；
> - 可检索性：有了良好的结构和语义，可以提高搜索引擎的有效爬取，提高网站流量；
> - 国际化：全球只有13%的人口是英语母语使用者，因此通用的语义化标签可以让各国开发者更容易弄懂你网页的结构；
> - 互用性：减少网页间的差异性，帮助其他开发者了解你网页的结构，方便后期开发和维护；
> 


> 好处: <br />
> - 利于SEO优化（也就是搜索引擎的抓取，搜索引擎的爬虫也依赖于标记来确定上下文和各个关键字的权重）；
> - 在样式丢失的时候，还是可以比较好的呈现结构；
> - 更好的支持各种终端，例如无障碍阅读和有声小说等；
> - 利于团队开发和维护，W3C给我们定了一个标准，那么团队中都遵循这个标准，那么代码的差异就会缩小，在开发和维护的时候就可以提高效率；
> 


> **学会如何写出更优的html:**
> 结构搭建上: 
> - 采用HTML5标准时开头应该加上<!DOCTYPE html>;
> - 应在head标签中引入CSS文件，这样浏览器就可以在输出HTML之前获取CSS信息；
> - 在body标签的末尾引入js文件，这样可以在页面显示之后再编译js文件，以加快页面读取速度，同时有助于js对页面中的元素进行操作
> - 对元素的操作应添加在js代码中，而不要在html中添加，后期难以维护；
> 


> 代码校验:
> 虽然现在浏览器的容错力越来越高，但这不能成为代码粗制滥造的借口。不管什么时候，正确的HTML代码都更易于debug、体积更小、运行更快、渲染时消耗资源更少，而错误的HTML代码只会使页面的最终设计难以实现想要的效果。特别是在使用模板来开发时，正确有效的HTML就更显得尤为重要，也许一个正常运行的模块会在其他环境中出现可怕的异常。
> - 在项目中加入校验过程：可以在代码编辑器中使用HTMLHint、SublimeLinter这类代码校验插件,也可以在build的时候使用HTMLHint with Grunt这类校验工具，还可以通过W3C HTML validator等网站来在线检测代码；
> - 尽量采用HTML5标准；
> - 确保正确的HTML层级：嵌套元素时确保元素首尾完整，在一个有大量内容的元素的结束标签后应添加注释，这样有助于后期debug，特别是在使用模板的时候；
> - 在所有不能自动结束的元素末尾添加结束标签；
> - li结束标签不是必须的，所以有些人认为可以不写li，这可以接受，但是ul和ol标签一定要加；
> - video和audio元素必须要有结束标签；
> 
<br />
> 良好的代码排版:
> - 在项目中保持统一的HTML代码风格；
> - 使用代码编辑器来帮助你自动排版，比如在Sublime Text中可以使用自带的Reindent，也可以找一些自动排版插件来帮助你。同样也可以使用一些在线工具比如；CSS Beautifier 和 JS Beautifier；
> - 在HTML中用缩进来分层更易于阅读，如果代码编辑器没有自动缩进功能的话可以自行修改相应的设置。当你发现你的HTML层级过深的时候，那就表示你需要重构一下你的HTML了；
> - 用更直接易读的方式写HTML代码，注意标签的相互嵌套关系；
> - 元素要按常规放置，比如footer元素最好是放在HTML页面的底部，虽然理论上把它放在任何地方都可以正常运行；
> - 统一所有引号的使用规则，不要这里用双引号，那里又单引号；
> - 使用小写字母来写标签和属性，大写字母很不易读；
> 
<br />
> 语义化设计: 
> - 标题使用h1(h2、h3、...) ，列表使用ul或者ol；
> - 在适当的地方使用HTML5的新元素，比如header、footer、nav、aside；
> - 正文中的文本内容要用p标签，内容的结构化可以使用HTML5的新元素（或者div);
> - 修改文字样式时，em和strong要比i和b更好些，因为前者语义更加明显；
> - form中要包含label元素，input要有type、placeholder以及其他必要的属性，即使值为空都可以；
> - 尽量减少使用无意义标签，例如span和div；
> - 尽量不使用标签本身的css属性，例如b、font、s等标签，如果需要这些样式，那么使用css样式来进行添加；
> - 在需要强调的部分，使用strong、em，但是样式尽量使用css样式来描述；
> - 使用表格时，标题用 caption，表头用 thead，主体部分用 tbody 包围，尾部用 tfoot 包围。表头和一般单元格要区分开，表头用 th，单元格用 td。
> - 列表搭建时，使用<ul>无序列表<ul><ol>有序列表<ol><dl>定义列表;
> - 表单域要用 fieldset 标签包起来，并用 legend 标签说明表单的用途（可理解为表单标题）
> - 每个input标签对应的说明文本都需要使用label标签，并且通过为input设置id属性，在lable标签中设置for = ld来让说明文本和相对应的input关联起来，或者直接在label中内嵌控件。
> 


> 布局规范: 
> - p元素用来放文字，而不是用来布局。在浏览器自身的样式中默认p有margin和其他样式；
> - 想实现换行可以使用block元素或者css的display属性，尽量避免使用br来换行。文字内容中的换行可以用br，但通常也很少这样用；
> - 不要滥用div，w3c对div的描述是这样的：当没有其他元素可用时才能使用div，如果想让link和img这类元素能够在结尾换行，可以在样式中添加display:block, 这样要比把他们放进div或者使用br来换行要好很多；
> - 必须知道哪些是块级元素，这样就可以避免把块级元素放到div里面，比如列表就不需要放到div里面；
> - table是用来放表格数据的，不是用来布局的；
> - Flex box现在越来越流行，学一学没有坏处；
> - 盒模型一定要掌握，必须知道什么时候该用padding，什么时候该用margin;是top和left
> - 使用margin的规则: 通常情况下，margin都是添加在元素的bottom和right，有时也可以是top或者left。无论如何，尽量避免同时在bottom和top，或者right和left添加margin，可以用last-of-type选择器来去掉最后一个子元素的margin；
> 
<br />
> 标签嵌套规范:
> 块元素可以包含内联元素或某些块元素，但内联元素却不能包含块元素，它只能包含其它的内联元素
> - <div><h1></h1><p></p></div> —— 对
> - <a href=”#”><span></span></a> —— 对
> - <span><div></div></span> —— 错
> 


> 块级元素不能放在<p>里面
> - <p><ol><li></li></ol></p> —— 错
> - <p><div></div></p> —— 错
> 


> 有几个特殊的块级元素只能包含内嵌元素，不能再包含块级元素
> - 这几个特殊的标签是： h1、h2、h3、h4、h5、h6、p、dt 
> 


> ul,li/ol,li/dl,dt,dd拥有父子级关系的标签；ul、ol下都只能跟li，dl下只能跟dt.dd
> - <ul><li><a></a></li></ul> —— 对
> - <ul><a></a><li></li></ul> —— 错
> - <dl><dt><a></a></dt><dd></dd></dl> —— 对
> - <dl><a></a><dt></dt><dd></dd></dl> ——  错
> 


> a标签不能嵌套a标签
> - <a><a></a></a>   ——  错
> 
<br />
> 易访问性(网站代码优化):
> 要多为用户考虑，不同的设备条件、使用环境以及输入法等都会给你的HTML带来不同的体验：
> - 网页的title，keywords，description一定要写，要精简全面。
> - 网页使用语义化代码。
> - a标签要设置title属性；外部链接还要设置rel属性– –rel=”nofollow”，nofollow值会使得网络爬虫不顺着链接爬出。
> - 所有的标题使用h1标签，样式可以使用css设置。
> - br标签只能用于文本换行。
> - table一定要使用caption设置表格题目。
> - strong用来设置重标，em设置斜体。
> - img标签一定要设置其alt属性。

```
// 表单域
<form>
  <fieldset>
    <legend>Personalia:</legend>    <!-- legend 可理解为表单标题 -->
    Name: <input type="text"><br>
    Email: <input type="text"><br>
    Date of birth: <input type="text">
  </fieldset>
</form>

// label文本
<label for="username">请输入用户名: </label> 
<input type="text" id="username" name="username">

<label>请输入用户名<input type="text" id="username" name="username"></label>
```
<a name="ihh4C"></a>
## HTML及扩展
> Doctype、Meta> 、Entity> 、DTD、XML、namespace、SVG、MathML> <br />
> DOCTYPE文档声明: 
> - 声明帮助浏览器正确地显示网页 ;
> - 定义这个文档的类型，浏览器会先识别这句话，会按照这个类型去解析这个文档；
> - HTML 也有多个不同的版本，只有完全明白页面中使用的确切 HTML 版本，浏览器才能完全正确地显示出 HTML 页面 ；
> - 一般高版本兼容低版本，所以在工作中我们默认写高版本就可以了(html5文档声明)
> - 文档声明不区分大小写；
> - 文档声明必须放在第一行(因为浏览器是从上到下解析的)
> - 必须写文档声明，如果不写就会发生怪异事件；
> - 文档声明不是一个标签，它只是一个声明；**

```html
HTML5
<!DOCTYPE html>

HTML 4.01
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN"
"http://www.w3.org/TR/html4/loose.dtd">

XHTML 1.0
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"> 
```
> meta元信息
> meta标签提供关于HTML文档的元数据。元数据不会显示在页面上，但是对于机器是可读的。它可用于浏览器（如何显示内容或重新加载页面），搜索引擎（关键词），或其他 web 服务。

```html
// 申明编码
<meta charset="UTF-8" />

// 页面关键词
<meta name="keywords" content="" />

//页面描述
<meta name="description" content=" " />

// 视口-移动设备
<meta name="viewport" content="width=device-width, initial-scale=1">

// 搜索引擎索引方式
all：文件将被检索，且页面上的链接可以被查询；
none：文件将不被检索，且页面上的链接不可以被查询；
index：文件将被检索；
follow：页面上的链接可以被查询；
noindex：文件将不被检索；
nofollow：页面上的链接不可以被查询。
<meta name="robots" content="index,follow" />

// 定义网页作者
<meta name="author" content="author name" /> 

// 优先使用IE最新版本和 Chrome
<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />
// 关于X-UA-Compatible
<meta http-equiv="X-UA-Compatible" content="IE=6" ><!-- 使用IE6 -->
<meta http-equiv="X-UA-Compatible" content="IE=7" ><!-- 使用IE7 -->
<meta http-equiv="X-UA-Compatible" content="IE=8" ><!-- 使用IE8 -->
// 页面重定向和刷新
<meta http-equiv="refresh" content="0;url=" />
// 禁止浏览器从本地计算机的缓存中访问页面内容：这样设定，访问者将无法脱机浏览
<meta http-equiv="Pragma" content="no-cache">
// 转码申明:用百度打开网页可能会对其进行转码（比如贴广告），避免转码可添加如下meta。
<meta http-equiv="Cache-Control" content="no-siteapp" />

// 启用 WebApp 全屏模式
<meta name="apple-mobile-web-app-capable" content="yes" />
// 隐藏状态栏/设置状态栏颜色：只有在开启WebApp全屏模式时才生效。
// content的值为default | black | black-translucent 
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent" />
// 添加到主屏后的标题
<meta name="apple-mobile-web-app-title" content="标题">
// 忽略数字自动识别为电话号码
<meta content="telephone=no" name="format-detection" />
// 忽略识别邮箱
<meta content="email=no" name="format-detection" />
// 添加智能 App 广告条 Smart App Banner
<meta name="apple-itunes-app" content="app-id=myAppStoreID, 
  affiliate-data=myAffiliateData, app-argument=myURL">
<!-- 针对手持设备优化，主要是针对一些老的不识别viewport的浏览器，比如黑莓 -->
<meta name="HandheldFriendly" content="true">
<!-- 微软的老式浏览器 -->
<meta name="MobileOptimized"  content="320">
<!-- uc强制竖屏 -->
<meta name="screen-orientation" content="portrait">
<!-- QQ强制竖屏 -->
<meta name="x5-orientation" content="portrait">
<!-- UC强制全屏 -->
<meta name="full-screen" content="yes">
<!-- QQ强制全屏 -->
<meta name="x5-fullscreen" content="true">
<!-- UC应用模式 -->
<meta name="browsermode" content="application">
<!-- QQ应用模式 -->
<meta name="x5-page-mode" content="app">
<!-- windows phone 点击无高光 -->
<meta name="msapplication-tap-highlight" content="no">
// 浏览器内核控制 
<meta name="renderer" content="webkit|ie-comp|ie-stand">
```
> HTML Entity
> [https://developer.mozilla.org/en-US/docs/Glossary/Entity](https://developer.mozilla.org/en-US/docs/Glossary/Entity)
> [https://www.cnblogs.com/gopark/p/11342753.html](https://www.cnblogs.com/gopark/p/11342753.html)
> 

> 在编写HTML页面时，需要用到"<"、">"、"空格"等符号，直接输入这些符号时，会错误的把它们与标记混在一起，非常不利于编码。
> 那么就需要把这些字符进行转义，以另一种方式抒写，以相同的形式展现。
> 在HTML中，这些字符可称为HTML Entity，即HTML字符实体。
> 一个HTML Entity都含有2种转义格式：Entity Name 和 Entity Number。
> 

> Entity Name
> 格式： &entityName; 
> 说明："&"开头，";"结尾，以语义的形式描述字符。如字符"<"，英文名称为"less than"，Entity Name为"&lt;"，取自"less than"2个单词的首字母。
>  
> Entity Number
> 格式： &#entityNumber; 
> 说明："&#"开头，";"结尾，以编号的形式描述字符。此编号可以为十进制或十六进制(以"&#x"开头)等数字格式。
>  
> 作用: 
> 显示 HTML 保留字符，如 <、>、&、 " 等（联想到防御 XSS 攻击）；
> 表示难以用常规输入设备输入的字符，如 ©、®、± 等；
> 表示给定的字符编码可能无法表达文档字符集的其他字符，如ASCII 编码想显示中文，使用`&#x6C34;`表示 “水”;
> ![image.png](https://cdn.nlark.com/yuque/0/2020/png/454050/1594631342382-ed0d0ea5-6b62-4338-a359-59c3a7aa4ee4.png#align=left&display=inline&height=462&margin=%5Bobject%20Object%5D&name=image.png&originHeight=862&originWidth=1102&size=82914&status=done&style=none&width=590)
> SVG矢量图形
> [https://www.w3school.com.cn/svg/svg_examples.asp](https://www.w3school.com.cn/svg/svg_examples.asp)
> 
> 含义：
> - SVG 指可伸缩矢量图形 (Scalable Vector Graphics)
> - SVG 用来定义用于网络的基于矢量的图形
> - SVG 使用 XML 格式定义图形
> - SVG 图像在放大或改变尺寸的情况下其图形质量不会有所损失
> - SVG 是万维网联盟的标准
> - SVG 与诸如 DOM 和 XSL 之类的 W3C 标准是一个整体；
> 


> 优势：
> 与其他图像格式相比（比如 JPEG 和 GIF），使用 SVG 的优势在于：
> - SVG 图像可通过文本编辑器来创建和修改
> - SVG 图像可被搜索、索引、脚本化或压缩
> - SVG 是可伸缩的
> - SVG 图像可在任何的分辨率下被高质量地打印
> - SVG 可在图像质量不下降的情况下被放大
> 


> 浏览器支持:
> - Internet Explorer 9+, Firefox, Opera, Chrome, 和 Safari 支持内联SVG。

```html
// 把 SVG 直接嵌入 HTML 页面
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" height="190">
  <polygon points="100,10 40,180 190,60 10,60 160,180"
  style="fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;">
</svg>  
  
  
// 包含了 XML 声明。请注意 standalone 属性！该属性规定此 SVG 文件是否是“独立的”，
// 或含有对外部文件的引用。standalone="no" 意味着 SVG 文档会引用一个外部文件 - 在这里，是 DTD 文件
<?xml version="1.0" standalone="no"?>

// 引用了这个外部的 SVG DTD。该 DTD位于 “http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd”。
// 该DTD位于W3C，含有所有允许的 SVG 元素
<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.1//EN" 
"http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd">

// SVG 代码以 <svg> 元素开始，包括开启标签 <svg> 和关闭标签 </svg> 。这是根元素。
// width 和 height 属性可设置此 SVG 文档的宽度和高度。
// version 属性可定义所使用的 SVG 版本，xmlns 属性可定义 SVG 命名空间
<svg width="100%" height="100%" version="1.1"
xmlns="http://www.w3.org/2000/svg">

// SVG 的 <circle> 用来创建一个圆。cx 和 cy 属性定义圆中心的 x 和 y 坐标。如果忽略这两个属性，
// 那么圆点会被设置为 (0, 0)。r 属性定义圆的半径
// stroke 和 stroke-width 属性控制如何显示形状的轮廓。我们把圆的轮廓设置为 2px 宽，黑边框
// fill 属性设置形状内的颜色。我们把填充颜色设置为红色
<circle cx="100" cy="50" r="40" stroke="black"
stroke-width="2" fill="red"/>

</svg>
```
<a name="mitn2"></a>
## CSS绘制高级技巧
> linear-gradient，radial-gradient、background、border-radius、box-shadow，text-shadow、Filter , clip-path，Counter等
> 

> linear-gradient> <br />> [https://developer.mozilla.org/zh-CN/docs/Web/CSS/linear-gradient](https://developer.mozilla.org/zh-CN/docs/Web/CSS/linear-gradient)> <br />> 语法: 可以使用角度或者关键字；
> - background: linear-gradient(color-stop1, color-stop2, …)
> - background: linear-gradient(direction, color-stop1, color-stop2, …)
> - background: linear-gradient(angle, color-stop1, color-stop2);
> 
![](https://cdn.nlark.com/yuque/0/2020/jpeg/454050/1594777827219-dcafc9ef-87dd-4d9c-a8c7-52e5d2272e74.jpeg#align=left&display=inline&height=158&margin=%5Bobject%20Object%5D&originHeight=158&originWidth=379&size=0&status=done&style=none&width=379)
> 参数：
> 第一个参数:指定渐变方向，可以用“角度”的关键词或“英文”来表示：to/top、bottom、left、right
> 第一个参数省略时，默认为“180deg”，等同于“to bottom”。
> 第二个和第三个参数，表示颜色的起始点和结束点，可以有多个颜色值。
> ![](https://cdn.nlark.com/yuque/0/2020/jpeg/454050/1594777747978-b7914630-e855-4f77-b525-014dcfe10e21.jpeg#align=left&display=inline&height=195&margin=%5Bobject%20Object%5D&originHeight=223&originWidth=698&size=0&status=done&style=none&width=609)

```
// 1、线性渐变默认是从上到下
.box{
    background:linear-gradient(red,green);
    background:-webkit-linear-gradient(red,green);
}

// 2、从一个方向到另一个方向（to/left 、right 、bottom、top）
background:linear-gradient(to left,red,green);
background:-webkit-linear-gradient(to left,red,green); 

// 3、对角的，两个方向可以进行组合，比如下面的就是从左上角到右下角
background:linear-gradient(to left top,red,green);
background:-webkit-linear-gradient(to left top,red,green); 

// 4、还可以是角度
background:linear-gradient(90deg,red,green);
background:-webkit-linear-gradient(90deg,red,green);
```
> radial-gradient
> [https://developer.mozilla.org/zh-CN/docs/Web/CSS/radial-gradient](https://developer.mozilla.org/zh-CN/docs/Web/CSS/radial-gradient)
> 径向渐变：默认的形状是椭圆，至少得有两个颜色值。
> 形状：ellipse 椭圆（默认），circle（圆）

```
background: radial-gradient(#e66465, #9198e5);
background: radial-gradient(closest-side, #3f87a6, #ebf8e1, #f69d3c);
background: radial-gradient(circle at 100%, #333, #333 50%, #eee 75%, #333 75%);
background: radial-gradient(ellipse at top, #e66465, transparent),
            radial-gradient(ellipse at bottom, #4d9f0c, transparent);
```
![image.png](https://cdn.nlark.com/yuque/0/2020/png/454050/1594633147016-7178833d-5154-41f6-add7-88aff163ef1f.png#align=left&display=inline&height=221&margin=%5Bobject%20Object%5D&name=image.png&originHeight=441&originWidth=993&size=92894&status=done&style=none&width=496.5)
> 背景 - 纹理、图案、渐变、雪碧图动画、背景图尺寸适应
> background-size
> [https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-size](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-size)
> - 检索或设置对象的背景图像的尺寸大小。
> - 该属性提供2个参数值(特性值cover和contain除外)。
> - 如果提供两个，第一个用于定义背景图像的宽度，第二个用于定义背景图像的高度。
> - 如果只提供一个，该值将用于定义背景图像的宽度，第2个值默认为auto，即高度为auto，此时背景图以提供的宽度作为参照来进行等比缩放。
> 


> 取值情况：
> - length：用长度值指定背景图像大小。不允许负值。
> - percentage：用百分比指定背景图像大小。不允许负值。
> - auto： 背景图像的真实大小。
> - cover： 将背景图像等比缩放到完全覆盖容器，背景图像有可能超出容器。
> - contain： 将背景图像等比缩放到宽度或高度与容器的宽度或高度相等，背景图像始终被包含在容器内。
> 


> background-origin> <br />> [https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-origin](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-origin)> - 设置或检索对象的背景图像计算 background-position 时的参考原点(位置)
> - padding-box： 从padding区域（含padding）开始显示背景图像。
> - border-box： 从border区域（含border）开始显示背景图像。
> - content-box： 从content区域开始显示背景图像。
> 


> background-clip> <br />> [https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-clip](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-clip)> - 指定对象的背景图像向外裁剪的区域
> - padding-box： 从padding区域（不含padding）开始向外裁剪背景。
> - border-box： 从border区域（不含border）开始向外裁剪背景。
> - content-box： 从content区域开始向外裁剪背景。
> - text: 从前景内容的形状（比如文字）作为裁剪区域向外裁剪，如此即可实现使用背景作为填充色之类的遮罩效果
> 
<br />
> 
> border-radius
> [https://developer.mozilla.org/zh-CN/docs/Web/CSS/border-radius](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border-radius)
> 作用:
> - 圆角矩形
> - 圆形
> - 半圆/扇形
> - 一些奇怪的角角
> 


> 含义: 设置或检索对象使用圆角边框
> - 提供2个参数，2个参数以“/”分隔，每个参数允许设置1~4个参数值，第1个参数表示水平半径，第2个参数表示垂直半径，如第2个参数省略，则默认等于第1个参数
> - 水平半径：如果提供全部四个参数值，将按上左(top-left)、上右(top-right)、下右(bottom-right)、下左(bottom-left)的顺序作用于四个角。
> - 垂直半径也遵循以上4点。
> 


> 取值情况:
> - 四个值: 第一个值为左上角，第二个值为右上角，第三个值为右下角，第四个值为左下角。
> - 三个值: 第一个值为左上角, 第二个值为右上角和左下角，第三个值为右下角
> - 两个值: 第一个值为左上角与右下角，第二个值为右上角与左下角
> - 一个值： 四个圆角值相同
> 


> box-shadow
> [https://developer.mozilla.org/zh-CN/docs/Web/CSS/box-shadow](https://developer.mozilla.org/zh-CN/docs/Web/CSS/box-shadow)
> 作用: 
> - 营造层次感(立体感)
> - 充当没有宽度的边框
> - 特殊效果
> 


> 含义: 设置或检索对象阴影
> - none： 无阴影
> - length ①： 第1个长度值用来设置对象的阴影水平偏移值。可以为负值
> - length ②： 第2个长度值用来设置对象的阴影垂直偏移值。可以为负值
> - length ③： 如果提供了第3个长度值则用来设置对象的阴影模糊值。不允许负值
> - length ④： 如果提供了第4个长度值则用来设置对象的阴影外延值。可以为负值
> - color： 设置对象的阴影的颜色。
> - inset： 设置对象的阴影类型为内阴影。该值为空时，则对象的阴影类型为外阴影。
> 


> 语法: 
> - box-shadow: X轴偏移量 Y轴偏移量 [阴影模糊半径] [阴影扩展半径] [阴影颜色] [投影方式];
> 
![](https://cdn.nlark.com/yuque/0/2020/jpeg/454050/1594778087216-c8375c71-fe64-4142-b7af-10f191c96924.jpeg#align=left&display=inline&height=192&margin=%5Bobject%20Object%5D&originHeight=250&originWidth=708&size=0&status=done&style=none&width=545)
> 

> text-shadow
> [https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-shadow](https://developer.mozilla.org/zh-CN/docs/Web/CSS/text-shadow)
> 作用: 
> - 立体感
> - 印刷品质感
> 


> 含义: 设置或检索对象中文本的文字是否有阴影及模糊效果
> - none： 无阴影
> - length ①： 第1个长度值用来设置对象的阴影水平偏移值。可以为负值
> - length ②： 第2个长度值用来设置对象的阴影垂直偏移值。可以为负值
> - length ③： 如果提供了第3个长度值则用来设置对象的阴影模糊值。不允许负值
> - color ： 设置对象的阴影的颜色
> 


> 语法: 
> - box-shadow: X轴偏移量 Y轴偏移量 [阴影模糊半径] [阴影扩展半径] [阴影颜色] [投影方式];
> 
<br />

> Filter
> [https://developer.mozilla.org/zh-CN/docs/Web/CSS/filter](https://developer.mozilla.org/zh-CN/docs/Web/CSS/filter)> filter: none | blur() | brightness() | contrast() | drop-shadow() | grayscale() | hue-rotate() | invert() | opacity() | saturate() | sepia() | url();
> - none：默认值，没有效果。
> - blur(_px_)：给图像设置高斯模糊，"radius"一值设定高斯函数的标准差，或者是屏幕上以多少像素融在一起， 所以值越大越模糊；如果没有设定值，则默认是0；这个参数可设置css长度值，但不接受百分比值。
> - brightness(_%_)：给图片应用一种线性乘法，使其看起来更亮或更暗。如果值是0%，图像会全黑。值是100%，则图像无变化。其他的值对应线性乘数效果。值超过100%也是可以的，图像会比原来更亮。如果没有设定值，默认是1。
> - contrast(_%_):  调整图像的对比度。值是0%的话，图像会全黑。值是100%，图像不变。值可以超过100%，意味着会运用更低的对比。若没有设置值，默认是1
> - drop-shadow (_h-shadow v-shadow blur spread color_)： 给图像设置一个阴影效果
> - grayscale(_%_)：将图像转换为灰度图像。值定义转换的比例。值为100%则完全转为灰度图像，值为0%图像无变化。值在0%到100%之间，则是效果的线性乘子。若未设置，值默认是0；
> - hue-rotate(_deg_)：给图像应用色相旋转。"angle"一值设定图像会被调整的色环角度值。值为0deg，则图像无变化。若值未设置，默认值是0deg。该值虽然没有最大值，超过360deg的值相当于又绕一圈
> - invert(_%_) ：反转输入图像。值定义转换的比例。100%的价值是完全反转。值为0%则图像无变化。值在0%和100%之间，则是效果的线性乘子。 若值未设置，值默认是0
> - opacity(_%_)：转化图像的透明程度。值定义转换的比例。值为0%则是完全透明，值为100%则图像无变化。值在0%和100%之间，则是效果的线性乘子，也相当于图像样本乘以数量。 若值未设置，值默认是1。该函数与已有的opacity属性很相似，不同之处在于通过filter，一些浏览器为了提升性能会提供硬件加速。
> - saturate(_%_)：转换图像饱和度。值定义转换的比例。值为0%则是完全不饱和，值为100%则图像无变化。其他值，则是效果的线性乘子。超过100%的值是允许的，则有更高的饱和度。 若值未设置，值默认是1。
> - sepia(_%_)：将图像转换为深褐色。值定义转换的比例。值为100%则完全是深褐色的，值为0%图像无变化。值在0%到100%之间，则是效果的线性乘子。若未设置，值默认是0；
> - url()：URL函数接受一个XML文件，该文件设置了 一个SVG滤镜，且可以包含一个锚点来指定一个具体的滤镜元素，filter: url(svg-url#element-id)
> 
<br />
> clip-path
> [https://developer.mozilla.org/zh-CN/docs/Web/SVG/Attribute/clip-path](https://developer.mozilla.org/zh-CN/docs/Web/SVG/Attribute/clip-path)
> clip-path生成器   [https://www.html.cn/tool/css-clip-path/](https://www.html.cn/tool/css-clip-path/)   
> <br />
> 属性使用裁剪方式创建元素的可显示区域。区域内的部分显示，区域外的隐藏
> - 对容器进行裁剪
> - 常见几何图形
> - 自定义路径

```
// 圆形circle（半径at圆心坐标）
.circle{
    width:100px;
    height:100px;
    background:#0cc;
    -webkit-clip-path:circle(50% at 50% 50%);
}

// 椭圆形ellipse（长、短轴半径at圆心坐标）
.ellipse{
    width:100px;
    height:100px;
    background:#aaa;
    -webkit-clip-path:ellipse(25% 50% at 50% 50%);
}

// 内置矩形inset (上右下左的边距round上右下左圆角)
.inset{
    width:100px;
    height:100px;
    background:#99f;
    -webkit-clip-path:inset(10px 20px 30px 10px round 20px 5px 50px 0);
}

// 正三角形
.triangle{
    width:100px;
    height:87px;
    background:#c00;
    -webkit-clip-path:polygon(0% 100%, 50%  0%,100% 100%);
}

// 正方形
.square{
    width:100px;
    height:100px;
    background:#069;
    -webkit-clip-path:polygon(0% 0%, 0% 100%,100% 100%,100% 0%);
}
```
> css-counter
> - counter-reset:name num：name即标记计数器名称，num即记录计数器初始值。num非必写，默认为0（计数器声明及初始值设置）
> - counter-increment：name num：name即选择递增的计数器，num即增量。num非必写，默认为1，可以是正数、零或者负数。（递增规则）
> - counter()/counters(计算结果生成)

```
<style>
ol{margin:0;padding:0;list-style:none;counter-reset:item;}
li{padding-left:2em;}
li:before{counter-increment:item;content:counter(item)".";color:#f00;}
</style>
<ol class="test">
    <li>Node
        <ol>
            <li>Node
                <ol>
                    <li>Node</li>
                    <li>Node</li>
                    <li>Node</li>
                </ol>
            </li>
            <li>Node</li>
        </ol>
    </li>
    <li>Node</li>
    <li>Node</li>
</ol>
```
> CSS面试题真题
> - 如何用一个div画xxx
>    - box-shadow无限投影
>    - ::before
>    - ::after
> - 如何产生不占空间的边框
>    - box-shadow
>    - outline
>    - box-sizing:border-box
> - 如何实现圆形元素(头像)
>    - box-radius:50%
> - 如何实现IOS图标的圆角
>    - clip-path: (svg)
> - 如何实现半圆、扇形等图形
>    - border-radius组合：
>    - 有无边框
>    - 边框粗细
>    - 圆角半径
> - 如何实现背景图居中显示/不重复/改变大小
>    - background-position
>    - background-repeat
>    - background-size(cover/contain)

<a name="4Ednd"></a>
## CSS机制At-rule
> [https://css-tricks.com/the-at-rules-of-css/](https://css-tricks.com/the-at-rules-of-css/)
> [https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule)
> 

> 大家可能在CSS中见到过字符@然后加一些关键字的用法，这种用法就称之为AT规则，在CSS中，种类还是很多的，这里总结列举下：
> @charset、@import、@namespace、@document、@font-face、@keyframes、@media、@page、@supports
> 
> 
> 

> 所谓“常规规则”指的是语法类似下面的规则：@[KEYWORD] (RULE) 
> - @charset
> - @import
> - @namespace
> 


> 所谓“嵌套规则”就是带有花括号{} , 语法类似下面的规则 @[KEYWORD] { /* 嵌套语句 */ }
> - @document
> - @font-face
> - @keyframes
> - @media
> - @page
> - @supports
> 
<br />
> @charset
> 定义字符集。⽤于提示CSS文件使用的字符编码方式，它如果被使用，必须出现在最前面。这个规则只在给出语法解析阶段前使用，并不影响页面上的展示效果；
> 某些软件，例如Dreamweaver新建CSS文件时候，自动会带有下面所示代码，但实际开发时候，作用不大，因为meta中已经有所设置 (<meta charset="utf-8">)，会覆盖，所以我都是直接删掉的。

```
@charset "utf-8";
```
> @import

> 导入其他CSS样式文件。除了@charset规则不会被引入，@import可以引⼊另⼀个文件的全部内容。
> 实际上线时候，不建议使用，多请求，阻塞加载之类。但本地开发可以使用，用做CSS模块化开发，然后使用一些(如grunt)工具进行压缩并合并。但是呢，相比less, sass等还是有不足，就是@import语句只能在CSS文件顶部，使得文件的前后关系控制，就不那么灵活。

```
@import 'index.css';
@import url('index.css');
```
> 此规则应用到XML HTML(XHTML)上特别有用，因为这样的话XHTML元素可以作为选择器在CSS中使用。

```
/* XHTML命名空间 */
@namespace url(http://www.w3.org/1999/xhtml);

/* 内嵌在XHTML的SVG的命名空间 */
@namespace svg url(http://www.w3.org/2000/svg);
```
> @document

> CSS 4.0规范有相关说明。如果文档满足给定的一些条件，就可以应用我们指定的一些样式。比如说，这个CSS文件被子站A调用，和被子站C调用，我们可以通过域名匹配来执行不同的CSS样式。这样，我们可以有效避免冲突，或者防止外链之类

```
@document 
  /* 页面URL需要是 */
  url(http://www.zhangxinxu.com/),
  
  /* 页面URL的开头必须是... */
  url-prefix(www.zhangxinxu.com/wordpress/),
  
  /* 该域上的所有页面 */
  domain(zhangxinxu.com),

  /* 所有https协议页面 */
  regexp("https:.*")
{
  
  /* 开始样式 */
  body { font-family: Comic Sans; }

}
```
> @font-face   

> 自定义字体用的。IE6也支持

```
@font-face {
  font-family: 'MyWebFont';
  src:  url('myfont.woff2') format('woff2'),
        url('myfont.woff') format('woff');
}
```
> @keyframes   

> 用来声明CSS3 animation动画关键帧

```
@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
```
> @media  

> 媒介查询

```
@media all and (min-width: 1280px) {
    /* 宽度大于1280干嘛干嘛嘞... */ 
}
@media (-webkit-min-device-pixel-ratio: 1.5), (min-resolution: 2dppx) { 
    /* Retina屏幕干嘛干嘛嘞... */ 
}
@media print {
    /* 闪开闪开，我要打印啦！ */ 
}
@media \0screen\,screen\9 {
    /* IE7,IE8干嘛干嘛嘞... */ 
}
@media screen\9 {
    /* IE7干嘛干嘛嘞... */ 
}
```
> @page

> page⽤于分页媒体访问网页时的表现设置，页面是⼀种特殊的盒模型结构，除了页面本身，还可以设置它周围的盒,这个规则用在打印文档时候修改一些CSS属性。使用@page我们只能改变部分CSS属性，例如间距属性margin, 打印相关的orphans, widows, 以及page-break-*, 其他CSS属性会被忽略。

```
@page :first {
   margin: 1in;
}
上面CSS表示:first页面也要有:left, :right页面margin间距。zxx: 
//@page的伪类包括：:blank, :first, :left, :right
```
> @supports

> 是否支持某CSS属性声明的AT规则，浏览器对其支持性越来越好了

```
/* 检查是否支持CSS声明 */ 
@supports (display: flex) {
  .module { display: flex; }
}

/* 检查多个条件 */ 
@supports (display: flex) and (-webkit-appearance: checkbox) {
  .module { display: flex; }
}
```
<a name="hACwL"></a>
## CSS变量var的使用
> [https://www.zhangxinxu.com/wordpress/2016/11/css-css3-variables-var/](https://www.zhangxinxu.com/wordpress/2016/11/css-css3-variables-var/)
> [http://www.ruanyifeng.com/blog/2017/05/css-variables.html](http://www.ruanyifeng.com/blog/2017/05/css-variables.html)
> [https://blog.csdn.net/muzidigbig/article/details/89917424](https://blog.csdn.net/muzidigbig/article/details/89917424)
> [https://www.w3cplus.com/css/everything-you-need-to-know-about-css-variables.html](https://www.w3cplus.com/css/everything-you-need-to-know-about-css-variables.html)
> [https://developer.mozilla.org/zh-CN/docs/Web/CSS/Using_CSS_custom_properties](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Using_CSS_custom_properties)
> 

> 在任何语言中，变量的有一点作用都是一样的，那就是可以降低维护成本，附带还有更高性能，文件更高压缩率的好处。
> 随着CSS预编译工具Sass/Less/[Stylus](http://www.zhangxinxu.com/wordpress/2012/06/stylus-nodejs-expressive-dynamic-robust-css/)的关注和逐渐流行，CSS工作组迅速跟进[CSS变量的规范](https://drafts.csswg.org/css-variables/)制定，并且，很多浏览器已经跟进，目前，在部分项目中已经可以直接使用了。
> CSS 变量（CSS variable）又叫做"CSS 自定义属性"（CSS custom properties）。因为变量与自定义的 CSS 属性其实是一回事。
> 你可能会问，为什么选择两根连词线（`--`）表示变量？因为`$foo`被 Sass 用掉了，`@foo`被 Less 用掉了。为了不产生冲突，官方的 CSS 变量就改用两根连词线了。
> <br />
CSS变量的> 兼容性
> 2017年3月，微软宣布 Edge 浏览器将支持 CSS 变量。这个重要的 CSS 新功能，所有主要浏览器已经都支持了。         ![](https://cdn.nlark.com/yuque/0/2020/png/454050/1594187649345-862693a0-0e51-41f6-9ea5-4dc4485f8a55.png)                                       
> 


> CSS变量的语法和用法

> - CSS中原生的变量定义语法是：变量名前面要加两根连词线 `--*`
> - 变量使用语法是：var()函数用于读取变量 `var(--*)`
> - 其中 `* `表示我们的变量名称
> - var()函数还可以使用第二个参数，表示变量的默认值。如果该变量不存在，就会使用这个默认值；第二个参数不处理内部的逗号或空格，都视作参数的一部分
> - 变量名大小写敏感，--header-color和--Header-Color是两个不同变量
> 
<br />
> CSS变量的命名
> 
> 关于命名这个东西，各种语言都有些显示，例如CSS选择器不能是数字开头，JS中的变量是不能直接数值的，但是，在CSS变量中，这些限制通通没有，例如：

```
:root {
  --1: #369;
}
body {
  background-color: var(--1);
}
```
> 但是，不能包含$，[，^，(，%等字符，普通字符局限在只要是“数字[0-9]”“字母[a-zA-Z]”“下划线_”和“短横线-”这些组合，但是可以是中文，日文或者韩文，例如：

```
body {
  --深蓝: #369;
  background-color: var(--深蓝);
}
```
> 无论是变量的定义和使用只能在声明块{}里面，例如，下面这样是无效的：

```
--深蓝: #369;
body {
  background-color: var(--深蓝);
}
```
> 变量值只能用作属性值，不能用作属性名; 下面代码中，变量`--side`用作属性名，这是无效的。

```
.foo {
  --side: margin-top;
  /* 无效 */
  var(--side): 20px;
}
```
> 全局/局部变量

> - :root伪类可以看做是一个全局作用域，在里面声明的变量，他下面的所有选择器都可以拿到；
> - 局部变量；

```
// 全局变量
:root { --color: blue; }
.box{color: var(--color)}

// 局部变量
.box{
    --color: red;
    color: var(--color);
}
```
> CSS变量的默认参数

> - var() 函数还可以使用第二个参数，表示变量的默认值。如果该变量不存在，就会使用这个默认值。<br />
> - 第二个参数不处理内部的逗号或空格，都视作参数的一部分;<br />

```
color: var(--foo, #7F583F);
var(--font-stack, "Roboto", "Helvetica");   var(--pad, 10px 15px 20px);
```
> CSS变量的拼接

> - 如果变量值是一个字符串，可以与其他字符串拼接；
> - 如果变量值是数值，不能与数值单位直接连用;
> - 如果变量值带有单位，就不能写成字符串;

```
// 字符串
--bar: 'hello';   
--foo: var(--bar)' world';

// 变量值是数值
foo { 
	--gap: 20; 
  margin-top: var(--gap)px;  /* 无效 */  
}

// 上面代码中，数值与单位直接写在一起，这是无效的。必须使用calc() 函数，将它们连接，
foo { 
	--gap: 20; 
  margin-top: calc(var(--gap) * 1px); 
}

// 变量值带有单位
.foo {
	--foo: '20px'; 
  font-size: var(--foo);  /* 无效 */ 
} 

.foo {
	--foo: 20px;
  font-size: var(--foo);  /* 有效 */ 
}
```
> CSS变量的作用域

> 同一个 CSS 变量，可以在多个选择器内声明。读取的时候，优先级最高的声明生效。这与 CSS 的"层叠"（cascade）规则是一致的；

```
<style>
  :root { --color: blue; }
  div { --color: green; }
  #alert { --color: red; }
  * { color: var(--color); }
</style>

<p>蓝色</p>
<div>绿色</div>
<div id="alert">红色</div>
```
> 上面代码中，三个选择器都声明了--color变量。不同元素读取这个变量的时候，会采用优先级最高的规则，因此三段文字的颜色是不一样的。 这就是说，变量的作用域就是它所在的选择器的有效范围;

```
body {
  --foo: #7F583F;
}

.content {
  --bar: #F7EFD2;
}
```
> 上面代码中，变量--foo的作用域是body选择器的生效范围，--bar的作用域是.content选择器的生效范围。
> 由于这个原因，全局的变量通常放在根元素:root里面，确保任何选择器都可以读取它们。

```
:root {
  --main-color: #06c;
}
```
> CSS变量的注意问题

> - 当存在多个同样名称的变量时候，变量的覆盖规则由CSS选择器的权重决定的，但并无!important这种用法。
> - 变量的取值采用就近原则。
> - 如果变量值是数值，不能与数值单位直接连用。必须使用calc()函数，将它们连接;
> - 如果变量值带有单位，就不能写成字符串。
> - CSS属性名是不可以使用变量的；
> - CSS变量是存在缺省值，只要定义正确，里面的值不对，结果以缺省值显示;
> - CSS变量默认尾部是有空格的;
> <br />
CSS变量的响应式布局
> 
> CSS 是动态的，页面的任何变化，都会导致采用的规则变化。
> 利用这个特点，可以在响应式布局的media命令里面声明变量，使得不同的屏幕宽度有不同的变量值。

```
body {
  --primary: #7F583F;
  --secondary: #F7EFD2;
}

a {
  color: var(--primary);
  text-decoration-color: var(--secondary);
}

@media screen and (min-width: 768px) {
  body {
    --primary:  #F7EFD2;
    --secondary: #7F583F;
  }
}
```
> CSS变量的兼容性处理

> 对于不支持 CSS 变量的浏览器，可以采用下面的写法

```
// 用属性值得无效声明
a {
  color: #7F583F;
  color: var(--primary);
}

// 也可以使用@support命令进行检测
@supports ( (--a: 0)) {
  /* supported */
}
@supports ( not (--a: 0)) {
  /* not supported */
}

// JavaScript 检测浏览器是否支持 CSS变量
const isSupported =
    window.CSS &&
    window.CSS.supports &&
    window.CSS.supports('--a', 0);
 
if (isSupported) {
    /* supported */
} else {
    /* not supported */
}

// JavaScript 操作 CSS 变量的写法
window.onload = function() {
    // 设置值
    document.body.style.setProperty("--primary","pink");
    // 读取值
    let primary = document.body.style.getPropertyValue("--primary");
    console.log(primary);
    // 删除变量;返回删除的变量值
    let delPrimary = document.body.style.removeProperty("--primary");
    console.log(delPrimary);
}
```


