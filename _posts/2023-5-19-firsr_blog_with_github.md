---
layout: post
title: "利用GitHub Pages搭建个人博客和展示项目"
date:   2023-5-19
tags: [分享]
toc: true
comments: true
author: yallongao
---

利用GitHub Pages搭建个人博客并展示项目，无需服务器和域名，点击就送。

<!-- more -->

## 写在前面

在开始搭建之前，我们先聊点其它的。个人博客兴盛的时代已经过去，个人博客的影响力也日趋下降，通过平台分享的方式才是主流。而通过GitHub Pages方式的个人博客不会带来很大的流量，因此可以考虑通过其他平台同步发布的方式获得流量。

这里推荐知乎作为第二个技术分享平台，当然你也可以选择CSDN、博客园等。虽然GitHub在流量和便捷程度方面无法比拟这些平台，但是GitHub可以自定义样式，并且GitHub在技术圈的影响力更大。

其实很久之前就有写博客的想法，但很多时候觉得这是一个伪需求，因为很多时候的分享欲望只是一瞬间。

如果你没有Github Pages并且只利用Github Pages记录博客，请查看[lemonchann](https://github.com/lemonchann)的[可能是最全面的github pages搭建个人博客教程](https://lemonchann.github.io/create_blog_with_github_pages/)。

本文作为博客的第一篇，具有纪念意义，本文将从以下几个方面进行叙述，按需阅读。

1. 使用GitHub Pages
2. 利用GitHub Pages展示个人项目
3. 搭建个人博客

## 使用GitHub Pages

拥有GitHub Pages是使用博客功能的基础，有简洁、自由、免费、无需域名、无需服务器、可以展示项目等优点，对于个人用户是一个nice的选择。

### 新建Gitub Pages

1. 准备好一个GitHub帐号

2. 在[GitHub主页](https://github.com/)右上角点击加号，新建仓库（New repository）

3. 记录Owner，这就是你的`username`，以后会多次用到，在Repository处填写`username.github.io`，`username`对大小写敏感，我这里已经创建过了所以会有红色提醒

4. 其他选项

   1. Description：对仓库的描述，可不填
   2. 仓库可见性一定选择Public
   3. Add a README file：[`README.md`](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes)介绍，建议选择
   4. Add .gitignore：可根据需求创建`.gitignore`文件，这里不选择
   5. license：开源项目许可证，可不填

5. 直接在页面下方点击create repository

   ![image-20230520102713115](/home/yanlong/Project/github-blog/assets/images/2023-5-19-firsr_blog_with_github/image-20230520102713115.png)

### 将仓库拉到本地

1. 设备有`git`
1. 在本地合适位置选择作为git到本地的仓库，在Linux下，我一般选择`~/Project`路径作为同步github项目的位置，在Windows下同理。先假设你有`~/Project`路径，并选择`Project`作为项目存放的位置
1. 先将终端`cd`到`Project`下，Linux可使用`cd ~/Project`
1. 拉取代码`git clone https://github.com/username/username.github.io.git GitHub.io` ，将你真正的`username`替换`username`，`blog`是你同步在本地文件夹的名字，名字随意，下文用`GitHub.io`指代此位置
1. 同步成功后，在`Project`下将生成`GitHub.io`文件夹
1. 终端使用命令`cd GitHub.io`

### 使用`git`提交

1. 现在让我们测试是否可以将本地内容git到云端，打开`README.md`文件清空然后编辑内容，如果不知道写什么，复制这些

   ```
   利用GitHub Pages搭建博客
   ```

2. 请确认你的终端在`GitHub.io`下

3. 请知晓`git`[基础命令](https://www.runoob.com/w3cnote/git-five-minutes-tutorial.html)

4. `git add README.md`

5. `git commit -m "update README.md"`

6. `git push -u origin main`或者`git push`，若push时候没有权限，查看[此文](https://www.jianshu.com/p/abf56f1de643)

7. 等待片刻在https://github.com/username/username.github.io将看到更新后的内容，记得替换`username`



## 利用GitHub Pages展示个人项目

到这里你已经拥有了GitHub Pages，在搭建博客之前，先让我们看一下Github Pages

另一个强悍的功能，展示项目，例如[Yallon的项目展示主页](https://yallongao.github.io/)。

在项目展示主页你可以打开烟花链接，或者在这里[打开](https://yallongao.github.io/NewYearSolar/)，下面我们就以该项目作为示例，此处的烟花项目是github大佬分享，[这是烟花项目的原地址](https://github.com/NianBroken/Firework_Simulator)。

先从创建一个基础的展示项目做起

### 创建基础的展示项目

要展示的项目只能是静态网站，所以确保你的项目可以执行，倘若展示项目`ProjectFirstView`，那步骤如下

1. `cd ~/Project/GitHub.io`

2. `mkdir ProjectFirstView `

3. `cd ProjectFirstView`

4. `touch index.html`

5. 编辑`index.html`，示例如下

   ```html
   <!DOCTYPE html>
   <html lang="en">
   <head>
     <meta charset="UTF-8">
     <meta http-equiv="X-UA-Compatible" content="IE=edge">
     <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <title>展示</title>
   </head>
   <body>
       这是我的一个显示项目
   </body>
   </html>
   ```

6. `git add .`

7. `git commit -m "update ProjectFirstView"`

8. `git push`

9. 等待片刻打开https://username.github.io/ProjectFirstView/即可查看效果，需要更换`username`

### 关于`username.github.io`

访问`https://username.github.io`会先查找该路径下有无`index.html`，没有会查找`README.md`，寻找到以后则会展示。

通常展示的项目不止一个，所以可在类似之前创建多个项目，访问路径就是`https://username.github.io/xxxx`，而`https://username.github.io`作为总的展示路径，可以作为展示项目的主页。

### 将烟花项目作为展示项目

通常过节时候可以观赏烟花，程序员也要看看电子烟花。

这里的烟花项目只是一个示例，其他可以自行探索，但是要提醒读者，遵循开源社区规范条例。

1. [烟花项目原址](https://github.com/NianBroken/Firework_Simulator)
2. `cd ~/Project/GitHuhb.io `
3. `git clone https://github.com/NianBroken/Firework_Simulator.git FireWorks`
4. ` rm -rf FireWorks/.git/`删除多余的git，否则则会git上传不成功，也可以手动删除
5. `git add FireWorks`
6. `git commit -m "烟花"`
7. `git push`
8. 等待片刻在https://username.github.io/FireWorks/查看烟花，需要更换`username`

### 展示个人项目

可以将自己的项目写前端页面进行展示，同上，这里不做过多说明。

## 搭建个人博客

通过上述我们也能发现如果只利用GitHub Pages搭建博客是有一些浪费的，这也是为什么我
