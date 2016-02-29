title: hexo博客搭建过程
date: 2016-01-21 21:10:44
categories: 爱折腾
tags: [博客]
top: true
---
## 2016.2.9
* 取消toc
* 撤销左侧栏宽度更改
* 修改回到顶部样式

<!--more-->

### 取消toc
之前那个toc做得不满意，打算模仿next主题里的sidebar里的toc样式。那个做得不错。
### 取消左侧栏宽度
按之前的commit记录修改之后left-col里的元素不能居中对齐，强迫症表示不能忍受。
### 修改回到顶部样式
之前那个带有hover的弹跳效果，但是这个总会出现因为弹跳而点不到按钮的情况，表示有点舍本逐末了。
### 感想
今天直接reset了两个版本之后commit提示有conflict不让提交，用revert又搞不清楚接下来是怎么弄得，来来回回弄了几次太急躁了就直接`push origin-master --force`了。但是表示这真的是太不负责任了！感觉最近遇到瓶颈了，之前太匮乏，想弄得又太多，导致花了很多时间却效果不大。俗话说
>思而不学则惘

先放下一段时间，不要那么浮躁。先去学习一下`css`和`javascript`再回来继续修改。

## 2016.2.6
* 添加toc
* 修改左侧栏宽度

## 2015.2.5
* 更改头像动画
* 加入不蒜子网页统计
* 加入文章置顶功能
* 代码样式及代码框样式调整
* 加入jquery_ui

### 更改头像动画
使用`animate.css`这个库,动画演示:[Animate](http://daneden.github.io/animate.css/)
代码更改：[头像特效](https://github.com/Jeffrey95/hexo-theme-yilia/commit/9dd5b0a8b78902708ab4f99d53291cf555175721)

### 不蒜子网页统计
就是现在我博客底部那个统计信息。
[不蒜子](http://ibruce.info/2015/04/04/busuanzi/)
代码更改：[增加不蒜子网页统计功能](https://github.com/Jeffrey95/hexo-theme-yilia/commit/912e454f977bdb2ebe6ec74a215314152e0ede4a)

### 文章置顶
因为原来theme里面就已经有做好的js，所以只需要补上一点东西：
代码更改：[置顶](https://github.com/Jeffrey95/hexo-theme-yilia/commit/e0840814d548ab33e726262ef2c6e84d52f73380)

### 代码样式及代码框样式调整
这个直接搬运改好的highlight.styl好像并不能起作用。然后字体也不能正确显示。字体的话估计是font-family的问题，可是w3school上面说
>font-family 规定元素的字体系列。
font-family 可以把多个字体名称作为一个“回退”系统来保存。如果浏览器不支持第一个字体，则会尝试下一个。也就是说，font-family 属性的值是用于某个元素的字体族名称或/及类族名称的一个优先表。浏览器会使用它可识别的第一个值。

我的电脑上有Consolas字体，可是在font-family里我不把font-family放在第一位，字体就变成了默认字体，而不能自动识别Consolas。代码样式这个改起来真心蛋疼。每个人喜欢的配置都不同，所以自己参考着更改吧。
代码更改：[高亮样式](https://github.com/Jeffrey95/hexo-theme-yilia/commit/8da6fda5f6b1d3d181a510b155769a4d7d125378)

### jqurey_ui
嘿嘿嘿这个是别人教我的。[就是他](http://moxfive.xyz/2015/10/25/hexo-tag-cloud/ "在他的评论框里")
再来点有意思的：

<p class="ui-state-default ui-corner-all ui-helper-clearfix" style="padding:4px;">
  <span class="ui-icon ui-icon-pencil" style="float:left; margin:-2px 5px 0 0;"></span>
  简单的颜色选择器
</p>
 
<div id="red"></div>
<div id="green"></div>
<div id="blue"></div>
 
<div id="swatch" class="ui-widget-content ui-corner-all"></div>

这个需要的技能点：
* 引入jquery_ui库
* 添加js代码
* 了解markdown语法的工作原理

代码更改参考：[加入jquery_ui动画](https://github.com/Jeffrey95/hexo-theme-yilia/commit/4d42a6960e1a0b0303ce7b54318867b4e639a488 "颜色选择器依葫芦画瓢")
参考资料： [jQuery UI 教程](http://www.runoob.com/jqueryui/jqueryui-tutorial.html)

---

## 2016.2.4
* 尝试去模仿一个all-categories的界面，但是并没有搞出来。结果是下面这样子的：
![吐血](http://7xqrox.com1.z0.glb.clouddn.com/tags.png)

<li>~~七牛实名认证通过~~</li>

---
## 2016.2.3

* 添加分类页
* 代码高亮样式

实现方法有两种
1. 在文章中使用hexo的辅助函数`<%- list_categories([options]) %>`和`<%- list_tags([options]) %>`，来插入分类列表和标签列表。参考[让 Hexo 自动生成 Tag Cloud 标签云页面](http://moxfive.xyz/2015/10/25/hexo-tag-cloud/ "MOxFIVE的博客")
2. 自定义一个模板`.ejs`配合`js`去实现一个页面，参考[Jay Chung](http://jaychung.tw/all-categories/ "all-cateories")，显示第二种的定制性会更高一些。

鉴于自己的前端知识有限，故这里暂时只使用第1种方法。至于效果可以点击我的分类页查看，我这里是把theme里的tagcloud配合辅助函数完成的。参考[添加分类页](https://github.com/Jeffrey95/hexo-theme-yilia/commit/bae8cb3ea3c8cb78803315f874c32f8b0ca46be2)

---

## 2016.2.2

~~1. 改theme颜色~~
~~2. 完成多说评论框~~
~~3. Markdown语法样式~~

找了一晚上的theme，几乎把github上面所有高star的都看过了一遍，最后还是决定换一个简约一点的主题[yilia](https://github.com/Jeffrey95/hexo-theme-yilia "一个简洁优雅的hexo主题")。原来那个虽然首页比较好看，但是用起来并不怎么顺手。有了之前的经验，这次布置主题的过程还是比较顺利的。然而我怎么能忍受把主题搬过来一套就用呢？这和QQ空间还有什么区别呢，于是就开始了我的个性化博客之旅了。
要想个性化，最基本的技能点就是善用chrome的`审查元素`和在github看repositories上的`issues`和`commit记录`

### 审查元素
![审查元素](http://7xqrox.com1.z0.glb.clouddn.com/F12.png) 
chrome上面按f12，然后点箭头处，
![审查元素](http://7xqrox.com1.z0.glb.clouddn.com/%E5%AE%A1%E6%9F%A5%E5%85%83%E7%B4%A0.png)

### 看commit记录
![commit](http://7xqrox.com1.z0.glb.clouddn.com/commit.png)
![commit1](http://7xqrox.com1.z0.glb.clouddn.com/commit1.png)
绿色是增加的，红色是删除的，不过对于已经学会用git的你来说应该不难吧。

其实这都是最基本的技能，善用的话有助于你了解别人做了哪些修改，从而学习并自主进行修改。

### 改主题颜色
原主题的颜色是暗色调的我不太喜欢，我更喜欢小清新一点的颜色。具体更改可以参考：
@[669a097](https://github.com/Jeffrey95/hexo-theme-yilia/commit/84f58dde1174c382902453c647b978e2b68310b0)

---

## Day 3
### 域名
云+计划学生认证通过，送了38元的域名优惠券和云服务器的优惠券。云服务器的暂时不知道弄些什么，就还没有买。买了一年的.com域名，减去优惠券只用了11块。不过在腾讯买域名还要开通财付通，感觉不太喜欢啦。

至于为什么不云腾讯云服务器搭博客，因为要备案域名啊，不备案的话访问不了啊。在重庆备案还挺麻烦的， 非本地人居然还不能备案了。

申请到了域名之后，就要域名解析啦，我是直接在腾讯云上面进行解析的。我这里用的是一个二级域名`blog.qiujinfeng.com`

1. 添加两个`A`记录，主机记录为`blog`，记录值为github page ip,分别设置为：
`192.30.252.153`
`192.30.252.154`
添加CNAME记录，主机记录为`www`,记录值为`username@github.io`（改成你自己的）
2. 在username@github.io的项目根目录下建立**CNAME**文件，
并填写内容为：**blog.你的域名**,**commit**。以我这个为例，就可以通过**blog.qiujinfeng.com**来访问我的博客了。这和访问**jeffrey95.github.io**的效果是一样的。
3. `一定要添加CNAME文件！一定要添加CNAME文件！一定要添加CNAME文件。`今晚上deploy之后发现CNAME文件不见了，然后博客就莫名其妙404了，害我还找好久。。

### 主页优化
1. 今天去问了主题的Designer,然后在github在commit记录里找到了实现透明下来改变opacity的代码。在
`source/css/style.css`
和
`source/js/scripts.js`
里面改

### 新姿势
当你修改文章Tag或内容，不能正确重新生成内容，可以删除``hexo\db.json``后重试

### NEXT
~~1. 实现评论框~~
~~2. 注册七牛云空间作为博客的图床。~~

---

## Day 2
### 域名
在腾讯云+计划里找到了一个1元申请服务器和域名的计划，已经通过了学生认证。但是还没有申请域名。这也是一件不容易的事呢，想要的已经被申请了，真的想不太出要申请什么域名呢！等过两天域名代金券下来之后就可以开始弄域名解析啦，想想也是酷呢。
### 主页优化
想在主页添加下拉的时候有透明度的改变，以及每次进入都会有图片的变化。但是貌似要学习js的知识。嗯，那就学吧~

---
## Day one
一直就希望拥有一个自己的博客，之前考虑过用wordpress去搭建，可是考虑到要买vps和域名有点麻烦。今晚在找sublime搭建c++环境的时候无意间进到了一个博客，感觉做得还不错。一看域名是github.io结尾的，估计就是搭建在github上面的了。然后看了一关于我，看到是基于Hexo搭建的。百度了一下，就找到了不少教程。搭建过程还是挺简单的，因为之前就搭建好了github环境，所以只用再下一个node.js，然后按教程来就可以了。整个搭建过程不超过一个小时。而且以后也支持自定义域名，感觉还是挺方便的。


今天做的事：
1. 本机搭建与调试hexo
2. 初步尝试插入主题和评论框
3. 熟悉基本操作
4. 尝试上传到网上

### Remind
每次在本地修改调试可以用这条命令
`$ hexo s -g`

### link

[Hexo搭建Github静态博客](http://www.cnblogs.com/zhcncn/p/4097881.html)
[hexo你的博客](http://ibruce.info/2013/11/22/hexo-your-blog/)
[零基础免费搭建个人博客-hexo+github](http://hifor.net/2015/07/01/%E9%9B%B6%E5%9F%BA%E7%A1%80%E5%85%8D%E8%B4%B9%E6%90%AD%E5%BB%BA%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2-hexo-github/)
[有哪些好看的 Hexo 主题？](https://www.zhihu.com/question/24422335)
[hexo博客搭建时遇到的一些问题](http://segmentfault.com/a/1190000003710962?_ea=336354)
### Error
1. ** hexo一直deploy不上去，提示公钥错误**。之前那个公钥是安装windows桌面版的github的时候生成的公钥，所以用git shell连接的时候是可以连上去的。可是用git bash的时候，就一直deny。估计是桌面版的github生成的公钥只能让github客户端和git shell用？
	解决方案：
	重新生成一个公钥并在github账号的setting里设置一下。
	`ssh-keygen -t rsa -C "usrname@email.com"`
	回车回车回车
	```
	$ cd ~/.ssh
	$ ll
total 14
-rw-r--r-- 1 QIU 197609 1679 9月  16 15:10 github_rsa
-rw-r--r-- 1 QIU 197609  389 9月  16 15:10 github_rsa.pub
-rw-r--r-- 1 QIU 197609 1679 1月  21 15:38 id_rsa
-rw-r--r-- 1 QIU 197609  405 1月  21 15:38 id_rsa.pub
-rw-r--r-- 1 QIU 197609 1199 1月  21 15:52 known_hosts

	```
	```
	$ cat id_rsa.pub
	```
	把打印出来的内容复制到github的key里面去。这样就可以正常连接了

2. **hexo deploy命令显示ERROR Deployer not found : github**
	原因：hexo下的`_config.yml`里的
		``` 
	deploy: 
	  type: github
	```
	deploy的type改成git，然后运行下在git bush里运行
	`npm install hexo-deployer-git --save`
`hexo g`
`hexo d`
网上的教程大多都是针对**2.x**的, 最新版本是**3.x**要像上面那样那么弄。许多作者没有注明hexo版本。

3. `_config.yml`yaml语法要求严格，每一个脑要后面都要一个空格，否则报错：
	```
	can not read a block mapping entry; a multiline key may not be an imp
	licit key
	```
	错误的设置：
	```
	author:Zhchnchn
	email:XXX@qq.com
	language:zh-CN
	```
	正确的设置：
	```
	author: Zhchnchn
	email: XXX@qq.com
	language: zh-CN
	```
	注意空格。

### Summray
1. 今天把sublime的build system弄好了，支持路径名里带空格~
2. 搭了个最最基本的自己的博客。虽然还是很丑，速度也很慢，还有很多需要自己学习呢~
3. 重新学习了git的用法

### Next
1. 学习相应的js知识来优化博客界面
2. 优化访问速度。

