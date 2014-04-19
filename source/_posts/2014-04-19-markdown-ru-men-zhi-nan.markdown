---
layout: post
title: "Markdown——入门指南"
date: 2014-04-19 21:53:43 +0800
comments: true
categories: 
---

Markdown——入门指南

**导语：**

> [**Markdown**](http://zh.wikipedia.org/wiki/Markdown) 是一种轻量级的「标记语言」，它的优点很多，目前也被越来越多的写作爱好者，撰稿者广泛使用。看到这里请不要被「标记」、「语言」所迷惑，Markdown 的语法十分简单。常用的标记符号也不超过十个，这种相对于更为复杂的HTML 标记语言来说，Markdown 可谓是十分轻量的，学习成本也不需要太多，且一旦熟悉这种语法规则，会有一劳永逸的效果。

<!--more-->

![](http://ww3.sinaimg.cn/large/6aee7dbbgw1effia3l1xoj214z0n8dkl.jpg)

#一、认识Markdown
在刚才的导语里提到，Markdown 是一种用来写作的轻量级「标记语言」，它用简洁的语法代替排版，而不像一般我们用的字处理软件 Word 或 Pages 有大量的排版、字体设置。它使我们专心于码字，用「标记」语法，来代替常见的排版格式。例如此文从内容到格式，甚至插图，键盘就可以通通搞定了。目前来看，支持Markdown 语法的编辑器有很多，包括很多网站（例如[简书](http://jianshu.io/)）也支持了Markdown 的文字录入。Markdown 从写作到完成，导出格式随心所欲，你可以导出HTML格式的文件用来网站发布，也可以十分方便的导出PDF格式，这种格式写出的简历更能得到HR的好感。甚至可以利用[CloudApp](http://www.getcloudapp.com/)这种云服务工具直接上传至网页用来分享你的文章，全球最大的轻博客平台[Tumblr](http://te1ee.tumblr.com/)，也支持Mou这类Markdown 工具的直接上传。
#Markdown官方文档
> 这里可以看到官方的Markdown语法规则文档，当然，后文我也会用自己的方式阐述这些语法的具体用法。

* [创始人John Gruber的Markdown语法说明](http://daringfireball.net/projects/markdown/syntax)

* [Markdown中文版语法说明](Markdown中文版语法说明)

#Markdown中文版语法说明
* 专注你的文字内容而不是排版样式。
* 轻松的导出HTML、PDF和本身的.md文件。
* 纯文本内容，兼容所有的文本编辑器与字处理软件。
* 可读，直观。适合所有人的写作语言。

#我该用什么工具？
![](http://mouapp.com/Mou_128.png)

* 在Mac OS X上，我强烈建议你用[Mou](http://mouapp.com/)这款免费且十分好用的Markdown编辑器，它支持**实时预览**，既左边是你编辑Markdown语言，右边会实时的生成预览效果，笔者文章就是Mou这款软件写出来的。

![](http://ww1.sinaimg.cn/large/6aee7dbbgw1effcq2gx92j210j0ustj7.jpg)

其次还有很多，如果你是个编辑作者，我强烈建议你购买 [Ulysses Ⅲ](http://www.ulyssesapp.com/)，这款软件入围了苹果去年Mac App Store的The Best of 2013。它支持更多的写作格式、多文档的支持。Mou，iA writer这些软件都是基于单文档的管理方式，而Ulysses Ⅲ支持Folder、Filter的管理，一个Folder里面可以创建多个Sheet，Sheet之间也可以进行Combine处理。

![](http://ww3.sinaimg.cn/large/6aee7dbbgw1effd31zsw9j20o604iaae.jpg)

* 由于笔者不用Windows，Windows下的Markdown工具没有用过，经朋友介绍，有两款还算不错，一款叫[MarkdownPad](http://www.markdownpad.com/)，另一款叫[MarkPad](http://code52.org/DownmarkerWPF/)
* iOS端很多app早已经支持了Markdown录入，例如Drafts，Day One，iA writer等。
* 在Web端，我强烈推荐[简书](http://jianshu.io/)这款产品，上面有无数热爱文字的人在不停的创造，分享。在Web端使用Markdown没有比简书更舒服的地方了，同样支持左右两栏的实时预览，字体优雅，简洁。

![](http://ww2.sinaimg.cn/large/6aee7dbbgw1effdkfijo1j21220nigth.jpg)

* 同样是Web端，[Draftin](https://draftin.com/) 也近乎完美。

#二、Markdown语法的简要规则
##标题

![](http://ww1.sinaimg.cn/large/6aee7dbbgw1effeaclhiyj20eh09cwez.jpg)

标题是每篇文章都需要也是最常用的格式，在Markdown 中，如果一段文字被定义为标题，只要在这段文字前加 # 号即可。

`# 一级标题`

`## 二级标题`

`### 三级标题`

`### 三级标题`

以此类推，总共六级标题，建议在井号后加一个空格，这是最标准的Markdown语法。

##列表
熟悉HTML的同学肯定知道有序列表与无序列表的区别，在Markdown 下，列表的显示只需要在文字前加上 `-` 或 `*` 即可变为无序列表，有序列表则直接在文字前加`1.` `2.` `3.` 符号要和文字之间加上一个字符的空格。

![](http://ww4.sinaimg.cn/large/6aee7dbbgw1effew5aftij20d80bz3yw.jpg)

##引用
如果你需要引用一小段别处的句子，那么就要用引用的格式。

> 例如这样

只需要在文本前加入 `>` 这种尖括号（大于号）即可

![](http://ww3.sinaimg.cn/large/6aee7dbbgw1effezhonxlj20e009c3yu.jpg)

##图片与链接
插入链接与插入图片的语法很像，区别在一个 `!`号

图片为：`![]()`

链接为：`[]()`

插入图片的地址需要图床，这里推荐[CloudApp](http://www.getcloudapp.com/)的服务，生成URL地址即可。

![](http://ww2.sinaimg.cn/large/6aee7dbbgw1efffa67voyj20ix0ctq3n.jpg)

##粗体与斜体
Markdown 的粗体和斜体也非常简单，用两个 `*` 包含一段文本就是粗体的语法，用一个 `*` 包含一段文本就是斜体的语法。

例如：**这里是粗体** *这里是斜体*

##表格
表格是我觉得Markdown比较累人的地方，例子如下：
> | Tables        | Are           | Cool  |
> | ------------- |:-------------:| -----:|
> | col 3 is      | right-aligned | $1600 |
> | col 2 is      | centered      |   $12 |
> | zebra stripes | are neat      |    $1 |


这种语法生成的表格如下：

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

##代码框
如果你是个程序猿，需要在文章里优雅的引用代码框，在Markdown下实现也非常简单，只需要用两个 ` 把中间的代码包裹起来。图例：

![](http://ww3.sinaimg.cn/large/6aee7dbbgw1effg1lsa97j20lt0a8dgs.jpg)

使用 `tab` 键即可缩进。

##分割线
> 分割线的语法只需要三个 `*` 号，例如：
到这里，Markdown 的基本语法在日常的使用中基本就没什么大问题了，只要多加练习，配合好用的工具，写起东西来肯定会行云流水。更多的语法规则，其实Mou的Help文档栗子很好，当你第一次使用Mou时，就会显示该文档。可以用来对用的查找和学习。

![](http://ww3.sinaimg.cn/large/6aee7dbbgw1effgmnpgqlj210j0us44j.jpg)

#三、相关推荐:
##工具
图床工具用来上传图片获取URL地址

* [Droplr](http://droplr.com/)
* [Cloudapp](http://www.getcloudapp.com/)
* [ezShare for Mac](https://itunes.apple.com/cn/app/yi-xiang/id672522335?mt=12&uo=4)
* [围脖图床修复计划](http://weibotuchuang.sinaapp.com/)

在线好用的Markdown工具，为印象笔记而生

* [马克飞象，专为印象笔记打造的Markdown编辑器，非常推荐](http://maxiang.info/)

#相关文章阅读：
* [为什么作家应该用 Markdown 保存自己的文稿](http://ww3.sinaimg.cn/large/6aee7dbbgw1effgmnpgqlj210j0us44j.jpg)
* [Markdown 写作浅谈](http://www.yangzhiping.com/tech/r-markdown-knitr.html)
* [Markdown 工具补完](http://www.appinn.com/markdown-tools/)
* [Drafts + Scriptogr.am + Dropbox 打造移动端 Markdown 风格博客](http://jianshu.io/p/63HYZ6)
* [图灵社区，怎样使用Markdown](http://www.ituring.com.cn/article/23)
* [为什么我们要学习Markdown的三个理由](http://news.cnblogs.com/n/139649/)
* [Markdown 语法写作入门指南 by ibuick](http://ibuick.me/?p=4093)
