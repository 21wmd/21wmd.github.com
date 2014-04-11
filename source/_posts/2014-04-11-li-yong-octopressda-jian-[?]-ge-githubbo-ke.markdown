---
layout: post
title: "利用Octopress搭建一个Github博客"
date: 2014-04-11 18:58:52 +0800
comments: true
categories: 
---

**目录**

1. 安装 Ruby
2. 安装 Octopress
3. 配置个人 Github 账号
4. 将博客部署在 Github 上
5. 开始写博客
6. 更多操作
7. 配置 Octopress
8. 小结

#1. 安装 Ruby

Octopress 需要 Ruby 环境，RVM(Ruby Version Manager)负责安装和管理 Ruby 的环境。所以我们先在终端输入如下命令，来安装 RVM：

	curl -L https://get.rvm.io | bash -s stable --ruby
接着是安装 Ruby 2.1.1，在终端一次运行如下命令：

	rvm install 2.1.1
	rvm use 2.1.1
	rvm rubygems latest
完成上面的操作之后，运行 `ruby --version` 应该可以看到 ruby 2.1.1 环境已经安装好了。

参考：[Installing Ruby With RVM](http://octopress.org/docs/setup/rvm/)

#2. 安装 Octopress

在安装 Octopress 之前，请确保你的电脑上已经安装有 git 了 ，在终端输入 `git --version`，应该可以看到电脑中的 git 版本(我电脑上输出:`git version 1.8.5.2 (Apple Git-48)`)，如果没有显示相关内容，请先安装git。

git 安装之后，利用 `git` 命令将 octopress 从 github 上 clone 到本机，如下命令：

	git clone git://github.com/imathis/octopress.git 21wmd.github.com
	cd 21wmd.github.com
	ruby --version
安装相应的 gem:

	bundle update
最后安装默认的 Octopress 主题:

	rake install
参考：[Octopress Setup](http://octopress.org/docs/setup/)

#3. 配置个人 Github 账号

登录 Github.com,创建一个个个人账号,假设账号叫做 `21wmd`。然后在终端里输入命令，给 Github 生成一个 Key：

	[[ -f ~/.ssh/id_rsa.pub ]] || ssh-keygen -t rsa
按照终端中的提示操作，生成秘要之后，在终端中输入命令，查看生成的 Key：

	[[ -f ~/.ssh/id_rsa.pub ]] && cat ~/.ssh/id_rsa.pub
在浏览器中打开 Github 的 `SSH keys` 页面，点击 `Add another public key` 按钮，粘贴前面步骤中终端显示的 Key 信息，然后点击 `Add Key` 按钮即可。（请格外注意，不要在 Title 中填写内容，直接将复制的内容粘贴到 Key 中。）

#4. 将博客部署在 Github 上

因为 Github 的 Page service 可以免费托管博客，并且还可以自定义域名。所以我们可以将博客搭建在 Github 中。

首先需要在 GitHub上 创建一个仓库，并将仓库名称按照这样的方式进行命名 `21wmd.github.com`。等后面配置完毕之后，我们就可以在浏览器中使用页面地址 `http://21wmd.github.com` 来访问我们的博客。一般来说，我们希望在将博客的源码放到 `source` 分支下，并把生成的内容提交到 `master` 分支。

新增一篇测试博客：

	rake new_post["post title"]
生成静态站点：

	rake generate
创建好仓库之后，我们需要利用 Octopress 的一个配置 `rake` 任务来自动配置上面创建的仓库：可以让我们方便的部署 GitHub page。在终端输入如下命令：

	rake setup_github_pages
上面的命令会做一些事情(详细介绍看下面给出的参考链接)。其中最主要的就是创建一个 `_deploy` 目录，目录用来存放部署到 `master` 分支的内容。期间会要求你输入仓库的 `url`，根据提示，进行输入即可。 完成上面的命令之后，我们就可以生成博客并真正的部署到仓库中了。执行如下命令：

	rake generate
	rake deploy
上面的命令首先生成博客文件，并将生成的博客文件拷贝到 `_deploy/` 目录下，然后将这些内容添加到 git 中，并 `commit` 和 `push` 到仓库 `master` 分支。

现在可以访问 `http://21wmd.github.com` 了。注意：有时候可能会有延时，要等几分钟才能打开。 至此，我们的博客已经完成基本的部署，不过博客的 `source` 需要单独提交，执行如下命令就可以将 `source` 提交到仓库的 `source` 分支下。

	git add .
	git commit -m 'Initial source commit'
	git push origin source
如果在部署到仓库之前，需要先预览一下博客，可以在终端输入 `rake preview` 命令，然后就能在浏览器中进行本地预览访问了 `http://127.0.0.1:4000/` 或 `http://localhost:4000/`。

参考：[Deploying to Github Pages](http://octopress.org/docs/deploying/)

#5. 开始写博客

Octopress 为我们提供了一些 task 来创建博文和页面。博文必须存储在 `source/_posts` 目录下，并且需要按照 `Jekyll` 的命名规范对文章进行命名：`YYYY-MM-DD-post-title.markdown`。文章的名字会被当做 `url` 的一部分，而其中的日期用于对博文的区分和排序。 通过 Octopress 提供的 task 可以正确的按照命名规范创建一个博文，并且在博文中会附带常用的一些 yaml 元数据。只需要在终端输入如下命令：

	rake new_post["title"]
其中 title 为博文的文件名，创建出来的文件默认是 markdown 格式。上面的命令会创建出这样一个文件：`source/_posts/2013-08-03-title.markdown`。打开这个文件，可以看到里面有如下一些内容了(告诉Jekyll博客引擎如何处理博文和页面)：

	---
	layout: post
	title: "title"
	date: 2013-08-03 16:36
	comments: true

接着我们就可以在这个文件中写我们的博文啦。完成之后，我们可以预览和部署博文。下面是创建并部署博文的一个完整过程：

	rake new_post["New Post"]
	rake generate
	git add .
	git commit -am "Some comment here." 
	git push origin source
	rake deploy
参考：[Blogging Basics](http://octopress.org/docs/blogging/)

#6. 更多操作

在搭建博客的时候，我们可能会对博客做一些配置，例如添加评论、域名解析、分享等。这些内容我写在另外一篇文章中，会经常更新，请前往观看：[你好！github页面](http://beyondvincent.com/blog/2013/07/27/107-hello-page-of-github/)。

#7. 配置Octopress

Octopress 的作者已经尽量让配置简化了。大多数情况下只需要配置 `config.yml` 和 `Rakefile` 文件即可。其中 Rakefile 是跟博客部署相关，一般情况下并不需要修改这个文件，除非使用了 rsync。 config.yml 是博客重要的一个配置文件，在 config.yml 文件中有三大配置项：`Main Configs`、`Jekyll & Plugins` 和 `3rd Party Settings`。一般，该文件中其中url是必须要填写的，这里的 url 是在 Github 上创建的一个仓库地址，具体请看第四步中创建的地址。另外再修改一下 title、subtitle 和 author，根据需求，在开启一些第三方组件服务。 关于 config.yml 文件中的更多内容，请看这里的内容：[Configuring Octopress](http://octopress.org/docs/configuring/)

建议：最好把里面的 twitter 相关的信息全部删掉，否则由于 GFW 的原因，将会造成页面 load 很慢。同理，修改定制文件 /source/_includes/custom/head.html 把 Google 的自定义字体去掉。from [唐巧的博文中—配置](http://blog.devtang.com/blog/2012/02/10/setup-blog-based-on-github/)。

#8. 小结

本文介绍了如何利用Octopress搭建一个Github博客。大家在搭建的时候，要是遇到问题，可以回复我。
更新博客内容
	rake generate
	rake deploy
	git add .
	git commit -m "Some commit here."
	git push origin source
