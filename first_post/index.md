# FPGA之路-Verilog与编辑器的那些儿



Verilog HDL，硬件描述语言的一种，以文本形式描述数字系统硬件的结构和行为的语言<sup>[1]</sup>。Verilog HDL和VHDL是世界上最流行的两种硬件描述语言。在硬件描述语言中是很流行，但在所有编程语言中，其长期在100名左右徘徊，在[TIOBE 2019年2月的排行榜](https://www.tiobe.com/tiobe-index/)中甚至跌出了前100名，足见其有多小众。
{{< figure src="/images/20211014/20190227235636723_27835.png" title="Lighthouse (figure)" >}}


---
##  1.Verilog与Notepad++ 

17年大学毕业后，从事FPGA开发相关工作，进入公司后，大家都用[Notepad++](https://notepad-plus-plus.org/)，于是我也顺理成章的用上了Notepad++。Notepad++特别适合于Verilog的代码编写工作，因为Verilog不像其他编程语言，需要频繁的编译与调试，而且，一般Verilog的代码量不是特别大。前三个月，我用得很爽，但慢慢地，问题就来了。Notepad++除了支持Verilog语法高亮，除此之外只有基本的编辑功能。还是那句老话，磨刀不误砍柴工。不满足于现状的我，还是在因特内特上“疯狂”的寻找Notepad++与Verilog相关的插件，最终的结果不出意料的一无所获。
在这里，我仔细思考了一下，Verilog相关的插件为何如此之少的原因？主要有一下三点：

- 使用Verilog这种语言的人很少，无论是FPGA开发还是芯片设计的从业人员，相比于互联网的程序员的数量，完全不在一个数量级上；
- FPGA工程师号称“硬件工程师中的软件工程师”，在国内从事FPGA开发的技术人员绝大多数都是硬件出身，很少有软件出身的。插件编写需要很专业的软件功底，所以，这就尴尬了，会写插件的人不会去用Verilog，而会Verilog的人又都不会插件，同时，写Verilog的人很难有开源的思想；
- 国外的情况不清楚，但无论哪一种编程语言，国内对插件开发这类的事情似乎并不太“热衷”；

在插件寻找之路上，我意外的发现Sublime Text3在这一方面明显强于Notepad++。

*2019年2月28日写到这里，2020年4月4日才接上--！*
{{< admonition type=tip title="tip" open=false >}}
2019年2月28日写到这里，2020年4月4日才接上--！
{{< /admonition >}}

{{< mapbox 121.485 31.233 12 >}}

{{< mapbox 121.485 31.233 12 true "mapbox://styles/mapbox/streets-zh-v1" >}}

{{< bilibili BV1E34y1D7T3 >}}

---
##  2.Verilog与Sublime Text3
由于Notepad++对Verilog的支持实在太差，我转而使用[Sublime Text3](https://sublimetextcn.com/)进行Code。Sublime Text3支持Verilog的插件明显比Notepad++多很多，17年底时开始在网上疯狂地搜索与Verilog相关的插件。这些插件都很强大和使用，具体可以参照以下的文章：
> 1.[sublime3添加verilog自动补全代码段](https://blog.csdn.net/lx520aa/article/details/77848422)
> 2.[sublime text 3在windows中配置ctags插件](https://blog.csdn.net/lijing198997/article/details/47724749)
> 3.[使用模板加快编码效率（三）——sublime [更新]](https://blog.csdn.net/k331922164/article/details/48092291)
> 4.[Sublime Text 2 和 Verilog HDL](http://quqian110.github.io/pages/2014107/04/sublime_text_2_and_verilog.html)
> 5.[引用4的原创网页已经打不开了，这是备用链接](https://blog.csdn.net/David_xtd/article/details/46373419)
> 6.[sublime text3 verilog代码编写高级操作篇](https://www.cnblogs.com/hqz68/p/9825785.html)

本以为可以和Sublime Text3一起孤独终老了，用了1个多月后，发现Sublime Text3相比于Notepad++依旧略显“笨重”。同时，各种插件有很多地方并不是完全适合我。由于笔者的前公司有各种编码规范，许多自动化的功能，还需要手动进行二次修改，这样似乎并不能带来太多的便捷。有时候还不如复制粘贴来得快。于是，就这样还是和Sublime Text3和平分手了。

*近期看同事使用Sublime Text3，发现Sublime Text3编辑器有Python的API，那么只要掌握一点Pyhton的知识，就可以自己制作专属于自己的插件了。用Python去制作插件，学些成本相当较低。*

--- 
##  3.Verilog与VS Code
[VS Code](https://code.visualstudio.com/) 是15年发布的，我第一次接触大概是16年的时候，不由的想起那个时候我还在画CAD --！。17年差不多偶尔使用VS Code写点Markdown，18年写Python。但时至2020年3月之前，我从未用VS Code进行过Verilog的Code。原因主要在于，17年接触VS Code时，那时VS Code商店里与verilog/systemverilog相关插件的数量用一只手就可以数过来（欲哭无泪），同时很多功能不够完善，网上更加找不到相关的帖子。但那时，我就知道有一天VS Code会变得足够强大。等到那个时候，我会选择使用VS Code的。我于2020年4月3日切到VS Code上进行Code。此至今日（2020年4月4日），VS Code上的HDL语言相关的插件已经很强大了。
 *后续，我会写一些关于VS CODE的Verilog环境搭建的教程*
 
---
##  4.Verilog与Vim
[Vim](https://www.vim.org/)又是一个小插曲，前同事中有VIM大佬，看大佬用VIM写verilog，简直出神入化。我于2018年4月12日在JD购得一本《Vim使用技巧（第2版）》[英] Drew Neil著。不到3周，我便放弃了。。。
![VIM](_v_images/20200404152146872_17174.png)

---
##  5.重拾旧爱Notepad++
最终选用Notepad++，其一是因为轻量化。但是，我也发现当Notepad++在工作区打开太多文件夹时，也会存在各种卡顿的问题。

其二，是因为我找到了Notepad++的Python接口。可以通过Python脚本进行各种定制化操作，达到和插件一样的效果，用起来也很爽。
目前，我实现了自己定制的自动端口例化和自动声明，具体使用方法可以参考我的Github库：[Notepad_plugins_for_verilog](https://github.com/MineFujiko/Notepad_plugins_for_verilog)。（由于很多插件是在公司写的，前公司的东西都带不出来，后续写插件一定要在家里进行。--！）

---
##  6.打造专属的编辑器
待更新。。。
使用VS code的原因：
 - 跨平台
 - 趋势
 - 版本控制，对于GIT的支持

--- 

##  7.历经磨难“终得利器

---
> 1.Verilog HDL之百度百科：[https://baike.baidu.com/item/Verilog%20HDL/596353?fr=aladdin](https://baike.baidu.com/item/Verilog%20HDL/596353?fr=aladdin)
> 2.VIM：[https://www.vim.org/](https://www.vim.org/)
> 3.Python Script：[https://github.com/bruderstein/PythonScript/releases](https://github.com/bruderstein/PythonScript/releases)
> 4.Notepad++ Python Script下载链接：[http://npppythonscript.sourceforge.net/](http://npppythonscript.sourceforge.net/)

