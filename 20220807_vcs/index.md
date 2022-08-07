# VCS学习笔记


* 流程
一般使用vcs/modelsim/irun等仿真生成波形文件(一般为fsdb)，再用verdi查看波形，跟踪代码。

** 三步法
什么场景下使用三步法？
*** Elaboration-润色、详细制作
elaborate的作用是，？？？，生成可执行文件simv。

1. 指定elaboration的顶层
   #+begin_src shell
     # 默认库(WORK)的模块tb_top, 作为顶层
     vcs WORK.tb_top
     # 或者
     vcs -top tb_top
   #+end_src
   注意：若不指定，如果有多个顶层，则会默认每个顶层都会被仿真执行。
   详细参见:
   - VCS ug-Compiling/Elaborating the Design, Key Compilation or Elaboration Features, Verilog Configuration and Libmaps;
   - [[https://mp.weixin.qq.com/s/g0SbBUwQkucGmlRd6KD4DA][VCS仿真中的configuration和libmap]]

*** Simulation
执行仿真。
#+begin_src shell
  # set vcs simulation options
  vcs_sim_opts="-ucli -licqueue -l simulate.log
  ./simv $vcs_sim_opts -do simulate.do
#+end_src

* 命令说明
#+begin_src bash
  vcs -sverilog -full64 -override_timescale=1ns/1ps +cli+4 -Mupdate +lint=all +race=all +notimingcheck +v2k -f filelist -l run.log &
#+end_src

| Args                         | Info                                                                              |   |
|------------------------------+-----------------------------------------------------------------------------------+---|
| -debug or -debug_all         | 使能UCLI命令行                                                                    |   |
| -f <filename>                | 指定文件列表的名称，文件中可包含源代码文件的路径和名称、编译选项参数等            |   |
| -full64                      | 在64位下编译                                                                      |   |
| -j<number>                   | 设置并行编译的进程数，j后没有空格                                                 |   |
| -l <filename>                | 指定log文件名                                                                     |   |
| -Mupdate[=0]                 |                                                                                   |   |
| -o <name>                    | 指定编译生成的可执行文件名，默认为simv                                            |   |
| -timescale=1ns/1ps           |                                                                                   |   |
| -override_timescale=1ns/1ps  | 让源文件统一使用指定的timescale，即文件中的失效                                   |   |
| -P <pli.tab>                 | 指定PLI表文件                                                                     |   |
| -R                           | 在编译之后，立即执行产生的可执行文件                                              |   |
| -v <filename>                | 指定verilog库文件                                                                 |   |
| -y <dir_pathname>            | 指定verilog库路径                                                                 |   |
| +cli+[<name>=1,2,3,4         | 使能CLI调试功能                                                                   |   |
| +incdir+<dir_path>           | 指定`include指令包含文件的目录                                                    |   |
| +nospecify                   | 屏蔽specify块中的路径延时和时序检查                                               |   |
| +notimingcheck               | 屏蔽specify块中的时序检查                                                         |   |
| +race                        | 纪录设计中的竞争冒险，输出到race.out中                                            |   |
| +v2k                         | 支持verilog-2001标准                                                              |   |
| -cm line+cond+fsm+tgl+branch | 代码覆盖检查                                                                      |   |
| +lint=all                    | 显示详尽的诊断信息/输出警告信息                                                   |   |
| +define+<name>=<value>       | 增加一个宏定义，如：+define+INCR_EN=1                                             |   |
| -ucli                        | 用户命令接口                                                                      |   |
| -licqueue                    | 系统中VCS license被占用的情况下通知VCS等待license空闲的时候再执行，而不是直接退出 |   |
| -sverilog                    | 支持systemverilog编译                                                             |   |

* 问题汇总

