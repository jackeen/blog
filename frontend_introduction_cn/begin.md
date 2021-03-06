# 前端入门与应用笔记之开始

学习任何技术都需要切入点，根据历史的启发就先从HTML开始吧。

另，不要试图在一开始就搞清楚新接触领域的所有细节，它们只会成为你的拖累。只学习那些必要的影响下一步的知识，旁枝知识一律在将来的使用中学习。

> HTML - HyperText Markup Language

HTML，超文本标记语言。超文本的意思是不只是文本还有图片、视频等其他媒体文件包含其中。标记语言，它就是由很多约定好的标记组成，对信息进行结构化组织。发明它的原因是在互联网上共享文档。

> https://zh.wikipedia.org/wiki/HTML

现在的很多网站打开后，内容极度丰富绚丽，要达到这种效果就要使内容经过规划后呈现，而不是一堆文字的简单堆砌。最直观的规划就是排版，翻开一本书会发现它们通常有：目录、各种标题、带编号的条目、文字的行距、段落间距等等，这些都使得这本书视觉上井井有条，便于阅读。随着web技术的出现这些用于书本的技术就被用到了网页上。

> 用排版改善阅读体验是纸媒体诞生以来逐渐发展起来的。设计排版的理论依据和思路基本相同。统一大小的标题使用户可以快速区分段落和标题，以节省注意力。段落之间的适当间距消除人们阅读的疲劳感和压抑感。

标记自然是HTML的主角，它们都有适合自己的使用场景，这些人为约定好的标签都是为了解决某个具体的问题逐渐出现的，在HTML技术发展的过程中间有增加有删减，所以如果盘点所有的标签还是比较多的，如果初次接触HTML或许多少会有些茫然，但其实只了解其中的一小部分就可以愉快的使用这个标记语言了，实际上即使是专业的web开发人员经常用到的也只是一小部分。

> https://developer.mozilla.org/zh-CN/docs/Web/Guide/HTML/HTML5/HTML5_element_list
> 记住这个地址将来会经常用到

标签有两个功能，一个是组织功能，一个是表现功能。

组织功能。HTML里所有的标签都是嵌套组织的，即它们有向生物那样的父子关系，父可以有多个子，子不可以有多个父。比较形象的是用树形结构描述。

> 下面是一段简单的树形结构标记。等等，它并不是HTML，虽然它很像，因为它的标签都不是约定好的，而且约定好的标签还要有一些伦理关系。这个例子仅仅是为了凸显它的结构化的组织能力。

```html
<root>
    <books>
        <math></math>
        <history></history>
    </books>
</root>
```

表现功能。既然是约定的标签，自然就有规则由谁来执行的问题。常见的执行程序-浏览器登场了，其实还有另外一个常见的家伙是邮件客户端。浏览器必须把不同的标签显示成不同的样子才能发挥标签的表现功能，也就是实现前面提到的排版能力。

至于“伦理关系”是我自定义的一个说法。这些众多的标签可以分为两种：行内元素和块元素，这两个词都是专业的名词，因为标签都是按对出现的，它们包裹着自己里面的内容在浏览器里被当作一个个元素管理着，所以就都是元素了。行内元素就是它可以出现在文字流中，随波逐流，块元素则独占一行，行为霸道。根据它们的行为特征，在相互包裹的时候就有谁可以包裹谁的问题，谁做父亲当然是伦理问题啦。

这里有个简单的规则，就是块元素可以包裹行内元素。这是由不同元素的类型决定的，不同的类型决定了不同的用途。块元素就是用来区隔内容的，行内元素就是小范围修饰的。打开一个旅行箱，里面不同的隔断就是块元素，负责分区块，区块里面填充了不同的小包，洗漱包、电池包等等都可以看成是行内元素。

常用行内元素：
* a表示超链接，通常带有下划线，颜色通常是蓝色，点击过后变成棕色。
* em表示着重内容，通常是斜体
* b加粗
* u下划线

常用块元素：
* h1~h6六种标题
* div块，仅仅是分割内容
* ul无序列表，每行都有修饰符，默认通常是一个原点
* ol有序列表，每行都有修饰符，默认通常是自动增长的阿拉伯数字
* li列表项
* p表示段落
* form表示表单，用来向服务端提交数据

> 大多数标签都只有个别字母表示，它们都来自不同的单词前几个字母，如果感兴趣可以很方便的在网上找到它们的全称

下面就可以尝试写一段真正的HTML了。

```html
<h1>我的首页</h1>
<p>欢迎欢迎热烈欢迎</p>

<h2>我喜欢的书</h2>
<ul>
	<li>水浒</li>
	<li>三国</li>
</ul>

<h2>我的日计划</h2>
<ol>
	<li>早餐</li>
	<li>午餐</li>
	<li>晚餐</li>
</ol>
```

我把一些自己的数据填写到了这个结构化的体系里面，并且数据填写在那些标签内也经过了考量，按照标签的使用场景给它们选择了合适的内容，这样即便不看内容也大致能知道这些内容的特征，对这种郎才女貌的匹配有个专有描述-语义化。

根据结构组织的要求，这样的组织并不完整，它们现在是一盘散沙，没有统一的老大管理，无法被浏览器使用。当然如果硬要这样做浏览器也没脾气，它会自己补全剩下的部分。

```html
<html>

<head>
</head>

<body>
<h1>我的首页</h1>
<p>欢迎欢迎热烈欢迎</p>

<h2>我喜欢的书</h2>
<ul>
	<li>水浒</li>
	<li>三国</li>
</ul>

<h2>我的日计划</h2>
<ol>
	<li>早餐</li>
	<li>午餐</li>
	<li>晚餐</li>
</ol>
</body>

</html>
```

如上，多了三个标签html、head、body，它们就是专门用来结构化一个文档的，凡是需要显示的用户数据都应该在body内部，这样有唯一根的树形结构就组织好了。

以上文档中有个head标签，它可以包含如下主要内容：
* link标签，可以引入外部样式文件使得文档更加美观
* script标签，可以引入外部脚本实现复杂的交换功能
* meta标签，通常用来声明文档编码，当然还有其他功能

> 本文并没有涉及以上head标签内部内容的使用，为的是减少入门干扰，会在将来的系列文章中介绍，如果本文读者只是想做简单了解到话这些并不需要关心。

前面提到这HTML可以引入其他媒体那么就有如下标签入场了：
* video，文档中嵌入视频文件，mp4、webm等
* audio，文档中嵌入音频文件，mp3、ogg等这些文件
* img，文档中嵌入图片，png、jpg、webp

当文档有了视听体验，它能承载的内容就包罗万象了，可以使用的场景就非常的多了，现在看来超文本这种叫法还真不是乱吹。有了这些工具我就可以在之前的文档添加更多元的信息了，如下。

```html
<html>

<head>
</head>

<body>
<h1>我的首页</h1>
<p>欢迎欢迎热烈欢迎</p>

<div>
    <a href="./feedback.html" target="_blank">
        <img src="我的大头贴.jpg"/>
    </a>
    <p>天下没有白吃的三餐！！！</p>
</div>

<div>
    <video src="我家狗狗的疯狂举动.mp4"></video>
</div>

<h2>我喜欢的书</h2>
<ul>
	<li>水浒</li>
	<li>三国</li>
</ul>

<h2>我的日计划</h2>
<ol>
	<li>早餐</li>
	<li>午餐</li>
	<li>晚餐</li>
</ol>

<p> 本站纯属虚构，如有雷同算我没说 </p>

</body>

</html>
```

你可能注意到了img和video名称后面都有一个src，这个东西叫做标签属性（就像是某人拥有的头衔一样，科学家、文豪、老王...等等），可以设置多个用一个空格隔开即可。

你还可能在想这些家伙还有那些属性，其实不用太着急了解这个，属性和标签一样都是根据需要慢慢丰富起来的，随着历史而演变，有的被删除掉了，有的被保留下来了。所以只需要了解经常使用的就可以了，其余的可以在使用过程中不断深入掌握。

> 被保留、被删除，听上去有某种神秘的力量在操作。没错，在HTML在诞生之初是由商业公司维护的，但后来参与的公司越来越多造成了很多混乱，再后来就有了w3c这个标准化组织专门制定规范，然后大家遵照执行，w3c也没有独断专行的权力，凡事都需要游戏参与者商量着来，当然大公司贡献多声音也大。
> https://www.w3.org/

说回来src（sourse），只要是嵌入外部资源都用这个属性，这里是图片和视频。双引号里面的是资源网络地址，可以是绝对或是相对的。当读到这个标签浏览器会尝试下载这个资源，如果下载成功就调用对应的显示对象去处理，图片就绘制一个位图，视频就替换成一个内置的播放器，播放器功能和样式都和该浏览器相关。

看到这里之前我知道你已经忍不住想或者已经在搜索包裹在img外面那个家伙是什么了。它就是超链接，我感觉它是web里最伟大的发明，它可以将存储在世界各地不同服务器内的各种HTML文档链接起来，形成全球性的的信息网络。

> 为了方便人们使用信息网络里面的信息，最常见的方式就是查找到自己需要的信息，搜索引擎因此被发明出来，它们使用一种网络爬虫的程序在信息网里收集信息，这种爬虫程序通常也称为蜘蛛，非常形象。

超链接有两个常用的属性：href（Hypertext Reference）和target。这种元素只要用户点击浏览器会开始下载href里的网络地址并在target描述的页面打开，target的默认选项是“_self”，就是当前浏览器窗口或tab，target里可以写的还有“_blank”它可以开启一个新的浏览器窗口或tab来显示目标内容。

> 在早期浏览器里（比如IE6）是没有tab概念的，全部都是窗口。现在的浏览器都是tab了除非用户主动使用。

> 在产品设计上，一般是相似步骤的页面之间（实际应用中一个HTML文档对应一个页面）target跳转是用self，不同流程的切换使用blank。比如购物网站的商品详情页到结算页之间的跳转，或者是一个网站到另外一个网站到跳转。

> 页面很多时候也被叫做界面，常说的UI（user interface），来自人和计算机的交互（人机交互），在交互过程中使用者体验叫做UE（user experience），它们通过色彩、排版、反馈等手段使用户达到愉悦的使用感受。读到这里你可能感受到界面比页面的范围大很多，游戏界面、ATM机、工厂的操作台、汽车仪表盘、各种遥控器等等。

现在我们尝试将上面的代码保存到一个文件里面，新建一个文件home.html，然后拷贝粘贴保存即可。鼠标双击这个文件即可看见我们的劳动成果了，擦汗。
