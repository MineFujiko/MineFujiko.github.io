# hugo发布流程


** 1.进入站点的根目录下
   /myblog
   （如： F:\\Workspace\\Hugo\\Sites\\myblog）

** 2.创建新文章
   输入：
#+begin_src shell
hugo new posts/first_post.md
#+end_src
会按照模板在 posts/目录下，生成first_post.md文章。
注意：也可以自行在该目录下，创建新的文件，需要注意的是文章的头部需要一定设置。
*** 文件头设置
#+begin_src shell
---
title: "FPGA之路-Verilog与编辑器的那些儿"
date: 2021-10-11T23:18:22+08:00
draft: false
author: Nic
tags: [FPGA,verilog]
categories: [编辑器]
---
#+end_src

注：draft:false，代表草稿，不会真正发布。即，hugo指令时，不会再public下生成相关文件。

** 3.本地预览
输入如下命令，在本地访问：//localhost:1313/，即可预览博客。
#+begin_src shell
hugo server -D
#+end_src

** 4.生成文件
输入如下命令，会在public/目录下生成相关网页文件。
#+begin_src shell
  hugo
  // 或者
  hugo -D  // 连草稿文章也发布
#+end_src

** 5.部署
将 public/目录提交到github仓库即可。
小技巧：在根目录下，新建.gitignore文件，添加/public/,可以使得/public自成一个仓库。

** 其他
*** 图片插入
Hugo的根目录下有一个static目录，这个目录是用来存放静态文件的，如：图片、css、js等文件。在部署时，hugo会把static目录下的文件复制到pulic目录下，且目录层级保持一致。
#+begin_src shell
![Vimium Help](/images/20220820_vimium/vimium_help.jpg)
#+end_src
那么，图片放在 static/images/20220820_vimium/vimium_help.jpg
hugo拷贝生成   public/images/20220820_vimium/vimium_help.jpg

或者，使用LoveIt的shortcode
https://hugoloveit.com/zh-cn/theme-documentation-extended-shortcodes/#image
