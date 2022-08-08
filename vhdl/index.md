# VHDL学习笔记


* 代码结构
VHDL代码，由3个基本部分组成：
- LIBRARY(库)
- ENTITY(实体)
- ARCHITECTURE(构造体)

  |        |              |                                  |
  |--------+--------------+----------------------------------|
  | 库     | LIBRARY      | 列出当前设计中所用到的所有库文件 |
  | 实体   | ENTITY       | 定义电路的输入/输出引脚          |
  | 构造体 | ARCHITECTURE | 描述实现具体电路                 |

** 库
库，是一些常用代码的集合。将电路设计中经常使用的一些代码存放在库中，有利于设计的复用和代码共享，同时可以使代码结构更加清晰。
*** 库是如何构建的？
代码的标准形式，包括了函数(FUNCTION), 过程(PROCEDURE), 元件(COMPONENT)等。将标准形式的代码打包成在一起，形成包集(PACKAGE)。用户根据需要对其进行编译使用。
*** 库声明
VHDL中，有3个常用的库：
- ieee库
- std库
- work库
**** TODO ieee库
| 包集               |                                                                        |                        |
|--------------------+------------------------------------------------------------------------+------------------------|
| std_logic_1164     | 定义了STD_LOGIC(8值)和STD_ULOGIC(9值)多值逻辑系统                      |                        |
| std_logic_arith    | 定义了SIGNED(有符号)和UNSIGNED(无符号)数据类型、相关算术运算、比较运算 | 包含了多种数据转换函数 |
| std_logic_signed   | 可以使STD_LOGIC_VECTOR像SIGNED一样进行运算                             |                        |
| std_logic_unsigned | 可以使STD_LOGIC_VECTOR像UNSIGNED一样进行运算                           |                        |

1. std_logic_arith
   常用转化函数：
   - conv_integer(p)
   - conv_unsigned(p,b)
   - conv_signed(p,b)
   - conv_std_logic_vector(p,b)
**** std库
std库，是VHDL设计环境的标准资源库，包括2个包集：
- standard, 数据类型
- textio, 输入输出文本
**** work库
work库，为当前工作库，当前设计所有代码都放在work库中
*** 示例
库的声明及使用。
#+begin_src vhdl
  library ieee;
  use IEEE.STD_LOGIC_1164.ALL;

  library std;
  use std.standard.all;

  library work;
  use work.all;
#+end_src

