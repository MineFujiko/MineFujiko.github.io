# 使用hugo搭建个人博客


* 1.简介
  官网：https://gohugo.io/
  
hexo迁移到hugo:
https://liujiacai.net/blog/2020/12/05/hexo-to-hugo/

* 2.主题收藏
https://hugoloveit.com/zh-cn/


* 安装
根据官方教程进行安装：
https://gohugo.io/getting-started/installing
https://www.gohugo.org/doc/overview/installing/ (中文文档）
#+begin_quote
Binary (Cross-platform) 
Download the appropriate version for your platform from Hugo Releases. Once downloaded, the binary can be run from anywhere. You don’t need to install it into a global location. This works well for shared hosts and other systems where you don’t have a privileged account.

Ideally, you should install it somewhere in your PATH for easy use. /usr/local/bin is the most probable location.
#+end_quote
下载：
https://github.com/gohugoio/hugo/releases

** 放在任意位置，并添加环境变量
在CMD中
#+begin_src 
hugo version
#+end_src

https://www.cnblogs.com/shaoxiao666/p/13715728.html

* 配置
1. 生成站点
   在cmd中，
   #+begin_src
   hugo new site myblog
   #+end_src

2. 创建文章
   需要先进入到 myblog目录中。
   #+begin_src
   hugo new about.md
   #+end_src

3. 配置
   下载主题到theme目录下。
   在配置文件中，配置主题。
   #+begin_src
   # 更改使用 Hugo 构建网站时使用的默认主题
   theme = "LoveIt"
   #+end_src
   
3. 启动服务
   #+begin_src
   hugo serve -D
   #+end_src

4. 部署到github
   在github上新建仓库
   仓库名称必须为:minefujiko.github.io 。即，名字必须与个人用户名一致。
   在cmd中，输入 hugo --buildDrafts 或者 hugo 也可以
   生成public文件夹。
   #+begin_src shell
     cd public/
     git init
     git add .
     git commit -m "first commit"
     git remote add origin git@github.com:MineFujiko/MineFujiko.github.io.git
     git push -u origin main
   #+end_src
只需要把public下的文件传到github的这个仓库中，即可访问：
minefujiko.github.io网站。
注意，配置文件中还需要修改：
baseURL = "https://minefujiko.github.io"

* TODO 更改域名
https://blog.csdn.net/qq_41684621/article/details/103230888

* 评论系统
https://my.oschina.net/xdr630/blog/5250405

* 配置文件修改
** 修改头像
myblog为整个站点的文件夹。
头像的位置为，./static/images/Chuan.jpg
** 修改头像下的图标链接
#+begin_src toml
[languages.zh-cn.params.social]
  Github = "xxxx" # 在这里替换为自己的路径。
#+end_src
** 插入图片
图片依旧放在./static/images/目录下。
在markdwon文档中
#+begin_src md
{{< figure src="/images/lighthouse.jpg" title="Lighthouse (figure)" >}}
#+end_src

