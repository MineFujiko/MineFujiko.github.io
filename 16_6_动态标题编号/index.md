# org-mode-标题自动编号



## 动态标题编号 {#动态标题编号}

ORG的标题默认是不带编号的，如图1所示。
[fig1.png](/ox-hugo/fig1.png)
注意：1. 图片插入时，目录中不能有空格，不能有.等特殊字符。


### 使能自动编号功能 {#使能自动编号功能}

使用命令 _M-x org-num-mode_ ,即可打开动态标题编号。其效果，如图2所示。
[fig2.png](/ox-hugo/fig2.png)


### 更多设置 {#更多设置}


#### 限制自动编号功能 {#限制自动编号功能}

在使能自动编号功能后，在ORG文档中默认所有的标题都会自动编号。我们可以通过编号的级别、标签、 _COMMENT_ 关键字, _UNNUMBERED_ 属性等，限制自动编号功能。通过修改一下变量的值，设置限制条件：

-   org-num-max-level
-   org-num-skip-tags
-   org-num-skip-commented
-   org-num-skip-unnumbered
-   org-num-skip-footnotes

示例1：设置org-num-max-level 为1, 效果如图3所示。
[fig3.png](/ox-hugo/fig3.png)
设置方式为： C-h v org-num-max-level 修改配置为1，如图4所示。
[fig4.png](/ox-hugo/fig4.png)


#### 使能全局自动编号功能 {#使能全局自动编号功能}

在配置文件中，设置 _org-startup-munerated_ 变量为 _t_ ,可以全局使能自动编号功能。
在当前文件中，使用 _#+startup:num_ 可以在当前文档中使能自动编号功能。


### 参考文档 {#参考文档}

> 1.  The Org Manual Release 9.4, 16.6 Dynamic Headline Numbering
