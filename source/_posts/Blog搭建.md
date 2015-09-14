title: Blog搭建
date: 2015-09-14 10:54:59
tags:
	- 随笔
brief: "Hexo github io"
---
Github Pages 可以免费托管静态网站,静态博客有许多现成的工具可以生成(如Hexo),所以可以很方便的搭建一个个人博客.所以cpoopc博客就诞生了 :)
简要归纳下搭建步骤
## 搭建步骤
### 1.github创建repository,这个repository的命名规则为:username.github.io
### 2.安装Hexo (基础软件[Nodejs](http://nodejs.org/),[Git](http://git-scm.com/),在此略过,默认已经安装)
``` bash
$ npm install -g hexo-cli
```
### 3.新建存放目录(blog),使用Hexo生成博客静态网站
``` bash
$ hexo init blog
$ cd blog
$ npm install
$ hexo server
```
hexo server执行后,命令行提示
``` bash
INFO  Hexo is running at http://0.0.0.0:4000/. Press Ctrl+C to stop.
```
这时候浏览器打开 http://localhost:4000/,就看到搭建在本地的博客主页啦.不过有点简陋.
### 4.使用自定义风格
网上有许多人做好并分享了漂亮的主题,比如[Yilia](http://litten.github.io/2014/08/31/hexo-theme-yilia/)
直接拿来用
``` bash
$ git clone https://github.com/litten/hexo-theme-yilia.git themes/yilia
```
编辑blog/_config.yml文件,配置
```
theme: yilia
```

### 5.发布到github
编辑blog/_config.yml文件,配置
```
deploy:
type: git
repository: git@github.com:cpoopc/cpoopc.github.io.git
branch: master
```
执行hexo指令,上传到github
``` bash
$ hexo deploy
```

### 6.域名绑定
blog/source目录中创建CNAME文件,内容为我的域名 cpoopc.cn
到购买域名的网站上,设置域名解析,
把github的ip 192.30.252.154配置进去.
大功告成!可以开始happy的写博客了!

## 写博客
``` bash
$ hexo new post
```
执行生成source/_posts/post.md
编辑器打开post.md,就开始写咯.
好了,可以去熟悉下[MarkDown](http://sspai.com/25137)语法了.

## Tip
1. hexo generate --watch  // 监听文件变化,自动generate
2. 使用yilia主题时,配置文件中
duoshuo: cpoopc
打开[多说](http://duoshuo.com/)评论系统.
3. 备份source,themes到github,方便在其他地方继续写博客