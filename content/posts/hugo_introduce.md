+++
title = "Hugo 之旅"
tags = [
    "博客"
]
date = "2020-11-29"
categories = [
    "博客搭建与配置"
]
keywords = [
    "博客搭建",
    "hugo"
]
menu = "main"
+++
##前言
Hugo 这种静态站点默认没有搜索功能，大概因为没了数据库实现反而不方便。Search for your Hugo Website 列出了一些可选项，要么自己生成索引用开源的工具搜索，要么用第三方搜索服务如 algolia。

自己来的方案里我选择 Github Gist for Fuse.js integration，因为它不需要另外引入 Node.js、 Grunt 或 Gulp，而是利用 Hugo 内置的功能在 build 的时候生成索引输出到 JSON，看起来更简单的样子。

第一步
创建 content/search.md
```
---
title: "搜索功能"
sitemap:
  priority : 0.1
---
```
根据 URL 规则，Hugo 会生成 /search/index.html 或 /search.html。但是因为 content/ 里的内容不支持插入 JS。


##准备环境
准备 node 和 git 环境，
首先，安装 NodeJS，因为 Hexo 是基于 Node.js 驱动的一款博客框架，相比起前面提到过的 Jekyll 框架更快更简洁，因为天 * 朝网络被墙的原因尝试过安装 Jekyll 失败而放弃了。
然后，安装 git，一个分布式版本控制系统，用于项目的版本控制管理，作者是 Linux 之父。如果 Git 还不熟悉可以参考廖雪峰大神的 Git 教程。

两个工具不同的平台安装方法有所不一样，可自行了解按步骤安装，这里不详述了。安装成功后打开 git bash（Windowns）或者终端（Mac），下方中将统一称为命令行。
在命令行中输入相应命令验证是否成功，如果成功会有相应的版本号。

##第三步配置 github page
在建好的仓库右侧有个 settings 按钮，点击它，向下拉到 GitHub Pages，你会看到有个网址，访问它，你将会惊奇的发现该项目已经被部署到网络上，能够通过外网来访问它，当然里面还很空什么东西都没有。 该地址就是你的博客默认地址，你也可以购买域名，将其换成你喜欢的地址。


