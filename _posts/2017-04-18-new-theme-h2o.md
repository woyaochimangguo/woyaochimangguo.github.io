---
layout: post
title: 'Conclusion and Reflection'
subtitle: 'A great learning opportunity'
date: 2024-04-16
categories: 技术
cover: 'http://on2171g4d.bkt.clouddn.com/jekyll-theme-h2o-postcover.jpg'
tags: Github_Pages JeKyll Markdown
---

在这一次作业的实现过程中，遇到了不少问题也学到了很多东西，以下是我的一些个人的思考与反思

## 博客主题及选取的原因
博客首页先简单介绍了一下自己，在下面的blog模块简单的介绍了一下区块链领域最早的几篇论文。区块链是一种去中心化的分布式数据库技术，最初作为比特币的底层技术而出现，但现在已经被广泛应用于许多领域。
它的核心特点包括去中心化，安全性，透明性和不可篡改性。

## 博客页面布局及其设计思路

### 主题配色

支持两种主题配色——蓝色和粉色。

![](https://github.com/kaeyleo/jekyll-theme-H2O/blob/master/screenshot/jekyll-theme-h2o-themecolor.jpg?raw=true)

### 侧边栏

相比自己上一个版本的博客主题，首页增加了侧边栏，方便展示博主的个人信息和文章标签。

### 社交图标

使用阿里的图标管理平台[Iconfont](http://iconfont.cn/)整理了一套<strike>墙内外</strike>常用的社交图标，包括微博、知乎、掘金、简书、Github等十多个网站，鼠标悬停会显示该站的主题色。

### 自定义文章封面

在Markdown的[文章头信息](http://jekyll.com.cn/docs/frontmatter/)里添加cover参数来配置文章的封面图片，如果没有配置封面，则默认【主题色+底纹】的组合作为文章封面。值得一提的是，H2O有两种（粉、蓝）主题色和六种底纹（电路板、食物、云海、钻石等等）供你选择。

### 头图个性化底纹

在没有图片的情况下单纯显示颜色会不会太无趣了点？于是想到了加入底纹元素，底纹素材是SVG格式的（保存在css样式里），加载比图片快很多。

### 代码高亮

模板引入了[Prism.js](http://prismjs.com)，一款轻量、可扩展的代码语法高亮库。

很多知名网站如[MDN](https://developer.mozilla.org/)、[css-tricks](https://css-tricks.com/)也在用它，JavaScript 之父 [Brendan Eich](https://brendaneich.com/) 也在个人博客上使用。

遵循 [HTML5](https://www.w3.org/TR/html5/grouping-content.html#the-pre-element) 标准，Prism 使用语义化的 `<pre>` 元素和 `<code>` 元素来标记代码区块：

```
<pre><code class="language-css">p { color: red }</code></pre>
```

在Markdown中你可以这样写：


 ```css
	p { color: red }
 ```


支持语言：

- HTML
- CSS
- Sass
- JavaScript
- CoffeeScript
- Java
- C-like
- Swift
- PHP
- Go
- Python

## 博客功能实现和技术选择
主要采用了jekyll+GitHubPages的方式，下面简单介绍一下这种搭建方式
```
	Jekyll 是一个简单的博客形态的静态站点生产机器。它有一个模版目录，其中包含原始文本格式的文档，通过一个转换器（如 Markdown）和我们的 Liquid 渲染器转化成一个完整的可发布的静态网站，你可以发布在任何你喜爱的服务器上。Jekyll 也可以运行在 GitHub Pages 上，也就是说，你可以使用 GitHub 的服务来搭建你的项目页面、博客或者网站，而且是完全免费的。

	GitHub Pages 是一个静态网站托管服务，直接从github仓库托管你个人、公司或者项目页面 ，并且不需要你写任何后端语言来支持。
```
根据自己刚学到的知识，简单来说，GitHub Pages 可以被认为是用户编写的、托管在 GitHub 上的静态网页，即可以当作一个小服务器使用。

而 Jekyll 是一个生成静态网页的工具，在 Github 上绑定自己的域名后可以当作个人博客访问

接下来就是使用这两个工具搭建一个属于我们自己的博客
# 1.创建一个Github库并且开启Github Pages
首先我们用自己的 Github 账号创建一个新的库（repository），这个库的名称有固定的格式： `username.github.io`，其中 username 必须是 Github 账户的用户名，.github.io 是固定的，这个地址将会成为个人站点的网站地址。另外，我们可以勾选Initialize this repository with a README，让仓库自动创建一个 README.md 文件
创建完成后，进入所创建的库，在settings页面找到GitHub Pages进行设置，如果你的库有按照上述方式进行命名，则它会自动进行设置，设置成功后会该页面出现绿色的提示，成功后可选择Choose a theme选择一个主题。
到这一步，我们就成功完成了 Github Pages 的配置，接下来我们就需要安装 Jekyll ，上网找一个 Jekyll 的博客模板，再将自己修改后的模板上传至这个库中就可以完成我们的个人博客了。

# 2.Jekyll 运行环境的配置与安装
运行 Jekyll 所需的环境如下：
```
	Ruby
	Ruby Gems
	NodeJS或其他 JavaScript 运行环境
	Python2.7（或2.7以上版本）
```
首先安装Ruby 和 Ruby DevKit，[安装教程](http://jekyll-windows.juthilo.com/1-ruby-and-devkit/)
执行`gem install jekyll`，安装完成后可以用命令行执行`ruby -v`和`gem -v`检测是否安装成功。
接下来我们可以安装NodeJS，这个比较简单，在NodeJS[官网](https://nodejs.org/en/download/)就可以下载，找到适合自己系统的版本并安装，安装过程一路选择默认选项，安装后可以用命令行执行`node -v`和`npm -v`检测是否安装成功。
安装Python 环境
完成了上面环境的配置，打开命令行，执行`gem install jekyll`，完成环境配置。

# 3.个人博客的搭建
下载一个模板，在对模板的改造过程中熟悉jekyll的目录结构和操作方式。
jekyll的目录结构大概是

```.
├── assets # 存放用于线上环境的静态资源，比如我们想放在博客上的图片之类
├── _config.yml # 配置文件，我们通过修改这里的参数改造博客
├── _data
|   └── members.yml
├── _drafts # 未发布的文章。这些文件的格式中都没有title.MARKUP数据。
|   ├── begin-with-the-crazy-ideas.md
|   └── on-simplicity-in-technology.md
└── index.html # 模板首页
├── _includes
|   ├── footer.html
|   └── header.html
├── _layouts
|   ├── default.html
|   └── post.html
├── _posts # 用于存放博客文章的文件夹，文件格式必须符合: 年-月-日-文章标题.md
|   ├── 2007-10-29-why-every-programmer-should-play-nethack.md
|   └── 2009-04-26-barcamp-boston-4-roundup.md
├── _sass
|   ├── _base.scss
|   └── _layout.scss
├── _site
├── .jekyll-metadata
```

几个主要文件的参数在上面的 Github 页面上有很清楚的说明。在修改模板中，我暂时只改了_config.yml、index.html，在../assets/img里面加上了一些图片，将../_posts里的文章修改整理了一下。
为了看到博客呈现出来的效果，就要用上我们上一步安装的Jekyll，先打开命令行，将路径修改至博客模板所在路径，执行命令jekyll server，复制 `http://127.0.0.1:4000/` 到浏览器打开，就能看见本地的博客了

# 4.博客文件的上传
将文件上传至 Github 上的方法就不多赘述，我使用的是 GitHub 桌面版，操作起来比较简单，具体操作可以参考[这里](https://zhuanlan.zhihu.com/p/28321740)。

文件成功上传之后，在 Github 库页面就可以看到你的博客文件了，这时只要访问username.github.io，你就能看到自己搭建的个人博客了