* 转载过来主要是为收藏 最小字体的解决方案：Web-Developer/css-notes/compatible-with-less-than-12px-fontsize.md


/*<br>
Web-Developer:wangfeng<br>
QQ:769407183<br>
date： October 31 modify<br>
Used to store the front-end development file<br>
*/
<h2>1. 规范说明</h2>
注: 本文档采用 Front-End-Standards 项目编写

1.1 规范目的

项目在扩展，人员在变化，为提高团队相互协作效率以及快速熟悉的目的，提高代码的规范性，可维护性，美观性，统一团队编码规范和风格。建立一个合理的规范，前端开发人员按本文档规范进行前台页面开发，达到规范的目的。

此规范为参考规范，仅供参考，仅让所有代码都是有规可循的，并且能够得到堆积，减少重复劳动和不必要的修改。

本文档如有不对或者不合适的地方请反馈，大家一起学习。


<h2>2. 代码规范</h2>

<h3>2.1 Html规范</h3>

<h4>2.1.1 文件命名规范</h4>

1.Html文件统一用大小写英文字母（开头用小写，全小写更好，以免和js里的冲突），数字与划线组合，其中不能包含汉字，空格与特殊字符

命名原则：可以参考bootstrap里的方法名，中划线组合以模块区分css的位置；使得项目组每一个成员能够方便直观的理解每一个累名的意义和所在位置;当在文件夹中使用“按名称排列”的命令时，同一种性质的模块文件能够排列在一起，然后可以快速的操作。

2.各子页命名的原则是以栏目英文翻译后取单一单词做名称如：

关于我们：aboutus.html ；产品：product.html；联系我们：contactus.html；公用文章模板：page.html

<h4>2.1.2 html注释</h4>

注释格式

&lt;!-- 这儿是注释 --&gt;
注释中’–’只能在始末位置,不可置入注释文字区域;
head中不要加注释，以免造成有些浏览器出现不正常现象；

<h4>2.1.3 html书写规范</h4>

1.文档类型声明及编码: <br/>
统一为html5声明类型 <br/>
&lt;!DOCTYPE html&gt;;  <br/>
编码统一为&lt;meta charset=”utf-8″ /&gt; <br/>
书写时实现层次分明的缩进（2个或者4个空格,据不完全统计，2个空格的适应所有设备环境）;

2.非特殊情况下样式文件必须外链至&lt;head&gt;…&lt;/head&gt;之间;
非特殊情况下JavaScript文件必须外链至页面底部;

3.引入样式文件或JavaScript文件时, 须略去默认类型声明, 写法如下:

&lt;link rel=”stylesheet” type=”text/css” href=”…” /&gt;       
&lt;style&gt;…&lt;/style&gt;       
&lt;script src=”…”&gt;&lt;/script&gt;     
(style标签在浏览器中是css的事实标准,script标签在浏览器是js的事实标准)

引入JS库文件, 文件名须包含库名称及版本号及是否为压缩版, 比如jquery-1.9.1.min.js; 引入插件, 文件名格式为库名称+插件名称, 比如jQuery.cookie.js; 

4.所有编码均遵循xhtml标准, 标签 & 属性 & 属性命名, 且所有标签必须闭合, 包括&lt;br /&gt;, &lt;hr /&gt;等; 属性值必须用双引号包括;（但html5无耻的给忽略了，说明规范再一次被规范了）

5.充分利用无兼容性问题的html自身标签, 比如div，span, em, strong, optgroup, label,等等; 需要为 html元素添加自定义属性的时候, 先要考虑下有没有默认的已有的合适标签去设置填充, 如果没有, 可以使用须以”data-”为前缀来添加自定义属性，避免使用”data:”等其他命名方式;

6.语义化html, 如标题根据重要性用h*(同一页面只能有一个h1), 段落标记用p, 列表用ul或者ol, 内联元素中不可嵌套块级元素;（语义化一直是大家讨论的问题，但语义化应该是如何，一直也没有强制的规范。）

7.尽可能减少标签嵌套,充分的组合利用每个标签的默认属性规则, 如

&lt;div class=”box”&gt;     
&lt;div class=”welcome”&gt; 
欢迎访问XXX, 您的用户名是&lt;div class=”name”&gt;用户名&lt;/div&gt;   
&lt;/div&gt;  
&lt;/div&gt;  

用以下代码替代更能显示你对标签的理解:

&lt;div class=”box”&gt;     
&lt;p&gt;欢迎访问XXX, 您的用户名是&lt;span&gt;用户名&lt;/span&gt;&lt;/p&gt;  
&lt;/div&gt;  

8.书写链接地址时, 必须避免重定向（还能避免浏览器之间的问题），例如：href=”http://&Chi;&Chi;&Chi;.&Chi;&Chi;&Chi;/”, 即须在URL地址后面加上“/”；

9.在页面中尽量避免使用style属性,即style=”…”;利用好分离模式。

10.必须为含有描述性表单元素(checkbox, radio)添加label, input, textarea按实际需要如:

&lt;p&gt;姓名: &lt;input type=”text” id=”name” name=”name” /&gt;&lt;/p&gt;

写成一下为好（可以避免浏览器中解析的区别，样式不一样）:

&lt;p&gt;&lt;label&gt;姓名:&lt;input type=”text” id=”name” /&gt;&lt;/label&gt;&lt;/p&gt;

11.图片加上alt属性（方便查找理解，当然看情况，模板文件动态变化没有办法添加）; 给重要的元素和截断的元素加上title;

12.给区块代码及重要功能(比如循环)加上注释, 方便后台添加功能;

13.对特殊符号使用: 尽可能使用html代码替代: 比如 <(<) & >(>) & 空格( ) & »(») 等等;

14.书写页面过程中, 请考虑模块的扩展性，实用性，可维护性;

15.class & id 参见 css书写规范


<h3>2.2 Css规范</h3>

1.编码统一为utf-8

2.协作开发及分工:

前端页面重构者会根据各个模块, 同时根据页面相似程序, 事先写好大体框架文件, 分配给前端人员实现内部结构表现行为;

共用css文件reset.css由前端页面重构者书写, 协作开发过程中, 每个页面请务必都要引入, 此文件包含整站基础样式, 此文件不可随意 修改; 

common.css为页容样式（命名模块区分）； 

mainsource.css为当前项目开发模式下的其它css文件管理文件，mainsource文件夹放置其它各页面css，多人开发时，统一为自己订制一个代号，具体作用下文会做说明。 预防多人开发同一个项目时的svn冲突。

结构可以参见：目录结构级说明

3.class与id命名与使用：

a：属性尽量不用Id，如特殊情况下有属性内容，使用请加上css_；

b：其他样式名称由小写英文&数字&_or-来组合命名,如i_comment,fontred,w200,h200; （若要加划线，css最好采用中线式，避免可以js的冲突）
注意：
1，最好全部用小写字母
2，避免使用中文拼音,尽量使用简易的单词组合；
3，尽量不缩写，除非易懂的单词
4. 不要以大写字母或者数字开头

c：属性少加important，降低级别

d：z-index层级不要开始就定很高。要有合理性


e：命名要语义化, 简明化。

常用类
页　眉：header  内　容：content 容　器：container   页　脚：footer  版　权：copyright
导　航：`nav`   主导航:mainnav(globalnav)  顶导航：topnav  子导航：subnav  菜单：menu
子菜单：submenu 标　志：logo    标　语：banner  标　题：title   侧边栏：sidebar
状态：status   投票：vote  合作伙伴：partner    友情链接：friendlink 外　套：wrap
商　标：label   左导航：leftsideBar 右导航：rightsideBar    菜单内容：menu1content   菜单容量：menucontainer
子图标：Icon    注　释：note    搜　索：search  按　钮：btn 登陆条：loginbar
登　录：login   链　接：link    信息框：manage  标签页：tab 文章列表：list
提示信息：msg    小技巧：tips    加入：joinus   指南：guild    服务：service
热点：hot  新闻：news 下载：download 注册：regsiter 功能区： shop(如购物车，收银台)
模块前缀(区分话，模块话)
作用:  
设置: set 添加: add 删除: del 操作: op  密码: pw  导入: inc
类型:  
按钮: btn  文本: tx  段落: p   图标: icon    颜色: color   背景: bg  边框: bor
状态:  
成功: suc 失败: lost    透明: tran
位置:  
公共: gb  边框: bor  弹出: pop 标题: title,tit   菜单: menu   内容: cont    提示: hint    导航: nav 信息: info        预览: pvw
模块：
首页：index ；文章：page；详情：detailsInfo；

例如：index-head，page-head；index-p，page-p；

f. 取父级元素id/class命名部分命名;

g. 重复使用率高的命名,在reset中统一定义，如属性有所不同，以页面或者区别加划线起始,比如page-fl，fl—db（db是display：block）;

h. 适用于已建好框架的页面, 
如, 要已建好框架的页面代码&lt;div id=”nav”&gt;&lt;/div&gt;中加入新的div元素,

按易懂命名法则: &lt;div id=”nav”&gt;&lt;div class=”subNav”&gt;…&lt;/div&gt;&lt;/div&gt; 样式写法:#nav .subNav {……};    
按后缀命名法则: &lt;div id=”nav”&gt;&lt;div class=”nav-subnav”&gt;…&lt;/div&gt;&lt;/div&gt; 样式写法:.nav-subnav{……}   

4.css属性书写顺序, 建议遵循: 布局定位属性–>自身属性–>文本属性–>其他属性.尽量保证同类属性写在一起.

属性列举： 

布局定位属性主要包括: display & list-style & position（相应的 top, right, bottom, left） ＆ float & clear ＆ visibility ＆ overflow；

自身属性主要包括: width & height & margin & padding & border & background

5.书写代码, 考虑并提高样式重复使用率;

6.充分利用html自身属性及样式继承原理减少代码量（上面也有提到，就是语义化）, 比如:

7.若样式表中出现中文字体名, 请务必转码成unicode码, 以避免编码错误时乱码;

8.使用table标签时(尽量避免使用table标签), 请不要用width/height/cellspacing/cellpadding等table属性直接定义表现, 应尽可能的利用table自身私有属性分离结构与表现, 如 thead,tr,th,td,tbody,tfoot,colgroup,scope
(cellspaing及cellpadding的css控制方法：
table{border:0;margin:0;border-collapse:collapse;}
table th, table td{padding:0;}
reset.css文件中会初始化表格样式)

9.杜绝使用

&lt;meta http-equiv=”X-UA-Compatible” content=”IE=7“/&gt;
来兼容IE8

10.比如css3的相关属性，毕竟现在兼容有限，用png图片做透明图片时, 要求图片格式为png-24格式,尽量避免兼容性属性的使用。

11.若css文件很容很多，须为大区块样式添加注释,小区块适量注释；以后修改维护的时候也尽量加上修改的日期，人员，原因

12.代码缩进与格式: 建议单行书写, 后期优化前端交互会统一处理;

<h4>2.2.2 css注释</h4>

a.组件注释

/**
* @name: 组件名
* @overview: 组件介绍
* @require: 依赖的样式
* @author: (xxx@gmail.com)
*/
b.块状或行内元素，都请使用 /* comment */ 注释，注释文字前后端保持各有一个空格。

c.为了您的体验着想，一目了然的代码，就不要注释了，比如:

display:none; /* 让元素看不见 */

<h3>2.3 图片规范</h3>

a.所有页面元素类图片均放入images文件夹,测试或者临时用图片放于image/template文件夹；

b.图片格式仅限于gif || png || jpg；

c.在保证视觉效果的情况下选择最小的图片格式与图片质量, 以减少加载时间；

1.gif充分利用动画的画布大小，减少KB值
2.png尽量用png-24，然后用高倍压缩不失真的压缩工具
3.对于公用性不大，不容易调整或者扩展的，尽量用jpg，降低KB，
质量要求高的用80，一般高清用60，没有色彩要求的40或以下即可

d.尽量避免使用半透明的png图片(注：根据设计搞来；若使用, 请参考css规范相关说明)；

e.运用css sprite技术集中小的背景图或图标, 减小页面http请求, 但注意, 请务必在对应的sprite的psd原图中划参考线规范, 并保存至images目录下；

f.命名全部用小写英文字母 || 数字 || _ 的组合，其中不得包含汉字 || 空格 || 特殊字符；尽量用易懂的词汇, 便于团队其他成员理解； 另图片全称分为前后两部分，用下划线隔开，前端部分表示图片的大类性质，如：广告，icon，标志，按钮，菜单，背景。（原理同css规则）

页面顶端的较大矩形广告图片取名：banner； 例如：banner_aboutus.jpg , banner_01.jpg, banner_02.jpg, 

功能性鼠标感应图片效果单独时:图片名称_on/off     例如：menu_on/off.png，button_on/off.png


<h3>2.3 Javascript规范</h3>

<h4>2.3.1 文件结构和命名</h4>

文件结构见项目脚手架：js文件结构，文件命名见项目脚手架：文件命名

<h4>2.3.2 编码风格</h4>

代码检测工具

根据不同IDE配置不同的检测工具(JSLint, JSHint等)及其选项，列举JSHint：
<ul>
<li>"jshint_options": {</li>
<li> "es3": true, //兼容es3规范，针对旧版浏览器编写的代码</li>
<li>"esnext": false, //不使用最新的es6规范</li>
<li>"camelcase": true, //使用驼峰式命名</li>
<li>"eqeqeq": false, //不强制使用===比较运算符</li>
<li>"expr": true, //允许未赋值的函数名表达式，例如console && console.log(1)</li>
<li>"freeze": false, //不限制对内置对象的扩展</li>
<li>"immed": true, //禁止未用括号包含立即执行函数</li>
<li>"latedef": true, //禁止先调用后定义</li>
<li>"maxparams": 4, //函数最多不超过4个参数</li>
<li>"noarg": false, //不禁止对arguments.caller和arguments.callee的调用</li>
<li>"noempty": false, //禁止空代码块</li>
<li>"nonew": false, //允许直接new实例化而不赋值给变量</li>
<li>"plusplus": false, //允许++和--运算符使用</li>
<li>"quotmark": "single", //字符串使用单引号</li>
<li>"smarttabs": false, //不允许混合tab和空格缩进</li>
<li>"maxerr": false,</li>
<li>"strict": false, //不强制使用es5严格模式</li>
<li>"sub": true, //允许用[]形式访问对象属性</li>
<li>"unused": false, //允许定义没用的变量，在某些函数回调中，经常出现多个参数，但不一定会用</li>
<li>"multistr": false, //禁止多行字符串，改用加号连接</li>
<li>"undef": true,  //禁止明确未定义的变量调用，如果你的变量（myvar）是在其他文件中定义的，可以使用/*global myvar */绕过检测</li>
<li>"forin": false, // 如果为真，那么，jsHint允许在for in 循环里面不出现hasOwnProperty</li>
<li>"devel": true, //允许对调试用的alert和console.log的调用</li>
<li>"jquery": true, //检查预定义的全局变量，防止出现$未定义，该项根据实际代码修改</li>
<li>"browser": true,</li>
<li>"predef": ["define", "seajs", "console", "require", "module"],</li>
<li>"wsh": true,</li>
<li>"evil": false, // 不允许使用eval</li>
<li>"asi": true, // 行尾分号</li>
<li>"newcap": true, // jsHint会要求每一个构造函数名都要大写字母开头</li>
<li>"curly": true, // 使用if和while等结构语句时加上{}来明确代码块</li>
<li>"maxlen": 100 }</li>
</ul>
缩进：

两个空格 2space，注： 不同IDE可以配置缩进风格

<h4>2.3.3 编码注释：</h4>

方法内部使用 // ，方法外部使用YUIDoc注释，{{YUIDoc注释}}

<h4>2.3.4 代码格式：</h4>

1.每行代码长度不超过100字符;(尽量没一个条件或者动画格式一句)

2.空格：

//一元操作符前后不带空格
i++;
i--;

//二元操作符前后使用一个空格
var name = 'web';

//对象的属性冒号前没有空格，后面留一个空格
var obj = {
foo: 'foo',
bar: 'bar'
}

//方法定义的时候，括号前不留空格，括号后留一个空格
function test() {
//todo
}

3.条件控制语句if不省略大括号对 {} 注：一条语句的时候也不能省， 并且注意换行和空格

//if语句
if (condition){
//do
} else if (condition) {
//todo
} else {
//todo
}
4.多个变量用多个 var 声明

//多个变量声明
var foo = 'foo';
var bar = 'bar';
变量命名的风格：

注： 变量均遵循驼峰式命名规则
<h4>2.3.4 js变量和函数：</h4>
1.jquery对象变量使用 $ 开头

var $list = $('#list'); //jquery变量
var list = document.getElementById('list'); //普通变量

2.类名首字母大写(ClassDefine)

//Person类
function Person(name){
this.name = name;
}

3.方法名使用动词或动名词结合的驼峰式（getFunctionName，setFunctionName, isFunctionName，hasFunction）

4.常量用大写，用下划线连接

//常量
var STATIC_VARIABLE = 100;
var PI = Math.PI;

<h4>2.3.5 语言规范</h4>

1.变量命名必须加上 var 关键字

2.语句结尾总是使用分号

var foo = function(a) {
console.log(a);
} //这里丢掉分号自己可以试一下效果
(function(){
console.log('hello');
})();

3.创建基本类型时，不使用 new 关键字，而直接使用对象字面量，
注: 除了在需要实例化一个对象，或罕见的需要延时加载数据的情况外

//不使用new关键字创建
var list = new Array(1, 2, 3);
var obj = new Object();
//使用字面量
var list = [1, 2, 3];
var obj = {};

4.大字符串的创建注意格式

//html结构的字符串推荐使用这种方式
var listHtml = '&lt;ul class="list"&gt;' +
       '&lt;li class="item"&gt;first item&lt;/li&gt;' +
       '&lt;li class="item"&gt;second item&lt;/li&gt;' +
     '&lt;/ul&gt;';
     
5.使用闭包封装整个js文件代码

6.避免使用 eval，with

7.避免使用 for ... in 语句来循环数字，非得使用的情况下加上 hasOwnProperty 来判断

8.避免使用IE下的条件注释

//不要这样子写:             
var f = function () {              
/* @cc_on if (@_jscript) { return 2* @*/  3; /*@ } @*/         
};            
//条件注释妨碍自动化工具的执行, 因为在运行时, 它们会改变 JavaScript 语法树.         


<h2>3. 前端工具推荐</h2>

3.1 for Mac OS

for more app detial check -> IUSETHIS

3.2 前端相关工具(Mac)

编辑器：Sublime Text 2 / TextMate 2 / Vim / Intellij IDEA

命令行：iTerm2

浏览器调试环境：Chrome / Firefox + Firebug

移动设备调试环境：Mozilla Fennec

兼容性测试：VirtualBox + Win XP（IE 8）

版本控制工具：GitHub for Mac / Versions / SourceTree

FTP工具：Filezilla / ForkLift

HTTP抓包及Post/Get模拟：Charles

PHP集成环境：XAMPP for Mac / MAMP

SQL数据库管理：Sequel Pro

标注工具：Mark Man / xScope

取色拾色器： Frank DeLoupe / Sip / Snip / xScope

MarkDown编辑器：Mou

浏览器免刷新开发环境：LiveReLoad / CodeKit

CSS Sprite切图工具：SpriteRight

sass -> CSS 编译ruby+compass、koala

配色方案工具：ColorSchemer Studio

多浏览器Cookie管理：Cookie

图片素材收集：Sparkbox / Pixa

<h2>4. 其他规则</h2>

<h3>4.1 hack规则</h3>

一般情况下，不要使用 IE 条件注释：
通用 Hack
<table id="tipTable">
              <tbody><tr  >
                <th>标记</th><th>IE6</th><th>IE7</th><th>IE8</th><th>FF</th><th>Opera</th><th>Safari</th>
              </tr>
              <tr  >
                <td>[*+&gt;&lt;]</td><td>√</td><td>√</td><td>X</td><td>X</td><td>X</td><td>X</td>
              </tr>             
              <tr  >
                <td>_</td><td>√</td><td>X</td><td>X</td><td>X</td><td>X</td><td>X</td>
              </tr>
              <tr  >
                <td>\9</td><td>√</td><td>√</td><td>√</td><td>X</td><td>X</td><td>X</td>
              </tr>
              <tr  >
                <td>\0</td><td>X</td><td>X</td><td>√</td><td>X</td><td>√</td><td>X</td>
              </tr>
              <tr  >
                <td>!important</td><td>X</td><td>√</td><td>√</td><td>√</td><td>√</td><td>√</td>
              </tr>
              <tr  >
                <td>@media screen and (-webkit-min-device-pixel-ratio:0){<span class="red">.selector </span>{}}</td><td>X</td><td>X</td><td>X</td><td>X</td><td>X</td><td>√</td>
              </tr>
              <tr  >
                <td><span class="red">.selector </span>, x:-moz-any-link, x:default</td><td>X</td><td>√</td><td>X</td><td>√(ff3.5及以下)</td><td>X</td><td>X</td>
              </tr>
              <tr  >
                <td>@-moz-document url-prefix(){<span class="red">.selector</span>{}}</td><td>X</td><td>X</td><td>X</td><td>√</td><td>X</td><td>X</td>
              </tr>
              <tr  >
                <td>@media all and (min-width: 0px){<span class="red">.selector </span>{}}</td><td>X</td><td>X</td><td>X</td><td>√</td><td>√</td><td>√</td>
              </tr>
              <tr  >
                <td>* +html <span class="red">.selector </span>{}</td><td>X</td><td>√</td><td>X</td><td>X</td><td>X</td><td>X</td>
              </tr>
              <tr >
                <td>游览器内核</td><td>Trident</td><td>Trident</td><td>Trident</td><td>Gecko</td><td>Presto</td><td>WebKit</td>
              </tr>
            </tbody></table>
注意：                       
浏览器优先级别:FF<IE7<IE6,CSS hack书写顺序一般为FF IE7 IE6            
举例：               
background-color:red\0;IE8和IE9都支持；             
background-color:blue\9\0; 仅IE9支持；  

<h3>其它hack</h3>
1、Firefox  
@-moz-document url-prefix() { .selector { property: value; } } 
上面是仅仅被Firefox浏览器识别的写法   支持所有firefox版本  
ep：#selector[id=selector] { property: value; }      
或： @-moz-document url-prefix() { .selector { property: value; } }      
支持所有Gecko内核的浏览器 (包括Firefox)  *>.selector { property: value; }
                            
2、Webkit枘核浏览器(chrome and safari) 
@media screen and (-webkit-min-device-pixel-ratio:0) { selector { property: value; } }             主要是针对Webkit内核的浏览器，如 Chrome 和 Safari浏览器：      
ep：@media screen and (-webkit-min-device-pixel-ratio:0) { .demo { color: #666666; } }            
                     
3、Opera浏览器（挪威 Kestrel内核Presto）                        
html:first-child>body selector {property:value;} 或： @media all and (min-width:0) { selector {property: value;} } 或： @media all and (-webkit-min-device-pixel-ratio:10000), not all and (-webkit-min-device-pixel-ratio:0) { head~body selector { property: value; } }                    
这些都是Opera浏览器的Hack写法：           
ep：@media all and (-webkit-min-device-pixel-ratio:10000), not all and (-webkit-min-device-pixel-ratio:0) { head~body .demo { background: green; } }     
              
4、IE9浏览器         
:root selector {property: value/9;} 经测试这是IE9特有的写法。                 
ep： :root .demo {color: #fff03f/9;}          
              
5、IE9以及IE9以下版本                     
selector {property:value/9;}                        这种写法只有IE9以及IE9以下版本能识别，这里需要注意此处“9”只能是“9”不能是别的，比如说“7”，不然会失去效果的。           
ep： .demo {background: lime/9;} 
              
6.移动设备（只做简单介绍）                         
@media screen and (max-device-width: 480px) { .iphone-or-mobile-s-webkit{property:value;} }              
              
建议你使用更完美的hack方式，就是避免hack。或者在书写上，做点小trick。比如：
.selector .child{property:value;} /* for ie-6 */ 
.selector > .child{property:value;} /* except ie-6 */                 

<h3>4.2 Reset.css 部分代码(参考)</h3>

Html,body{padding:0;margin:0;font:12px/normal SunSin;color:#666; background:#ffffff; }                                   
html {  -ms-text-size-adjust: 100%;  -webkit-text-size-adjust: 100%;  overflow-y: scroll;  -webkit-overflow-scrolling: touch;}                                                            
h1, h2, h3, h4, h5, h6, form, div, p, i, img, ul, li, ol, table, tr, td,th, fieldset, label, legend,button,input { margin:0;padding:0;}                                                         
ul,li { list-style:none;}                                                    
img{border:none; vertical-align:middle; }                                                  
table{border-collapse:collapse;}                                                                                       
hr{clear:both;border-width:0;border-top:1px solid #ccc;border-bottom:1px solid #FFF;height:2px;overflow:hidden;}       
下面方法自己可以选择                                       
.cl{*zoom:1;}                                                     
.cl:after{display:block;clear:both;height:0;visibility:hidden;content:".";}                                   
(这是一种流行的方法)

.cl {*zoom:1}                                                   
.cl:after { content: '\20'; display: block; clear: both;  }                                                  
（这是一种简洁的方法）<br/>

.cl{ *zoom: 1;}<br/>
.cl:before, .cl:after {  content: "";  display: table; }<br/>
.cl:after {  clear: both; }<br/>
(这是sass库的定义)
                                                               
/*link*/                                                       
a { text-decoration:none; outline:none; color:#666;cursor:pointer;}   
a:link {color:#333;} 
a:visited {color:#333;}     
a:hover {color:#bc2931;}    
a:active {color:#bc2931;}   
                            
/*font*/                                         
.f12{font-size:12px;}               
.f14{font-size:14px;}                
.fb{font-weight:800;}               
.fi{font-style:italic;}                    
.dn{display:none;}                 
.db{display:block;}         
.fl{float:left;}                     
.fr{float:right}            
.dele{text-decoration:line-through;}                    
.ful {text-decoration:underline;}                                     


其他
开发过程中严格按分工完成页面, 以提高css复用率, 避免重复开发;
减小沉冗代码, 书写所有人都可以看的懂的代码. 简洁易懂是一种美德. 为用户着想, 为服务器着想.
<h2 class="h2">前端工具</h2>
在线压缩工具<br>
http://ganquan.info/yui<br>
css速查表<br>
http://code.ciaoca.com/style/css-cheat-sheet<br>
字符编解码<br>
http://www.baidufe.com/fehelper/endecode.html<br>
JSON格式化<br>
http://www.baidufe.com/fehelper/jsonformat.html<br>
CSS在线检查工具<br>
http://jigsaw.w3.org/css-validator<br>
CSS动画手册<br>
http://ecd.tencent.com/css3/guide.html<br>
CSS在线手册<br>
http://css.doyoe.com<br>
png压缩工具<br>
https://tinypng.com<br>
在线编辑器<br>
http://jsbin.com<br>

这里面都是工作或者学习中遇到的css，html，js和一些其他工具或者插件遇到的问题和解决方案。仅供参考。若有错误，请指正。谢谢
