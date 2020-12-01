# 1 命令介绍

set命令可以设置当前shell解释器的执行方式和选项，显示系统中已经存在的shell变量，以及设置shell变量的新变量值，set命令不能够定义新的shell变量，但是我们可以用set对新增的已有的变量进行一些操作，使之有了新的意义，如set可以把已有的的变量操作成环境变量等等。

使用方式：`set <+/-> <option> [args]`，执行set 命令后，对整个脚本有效。

# 2 选项说明

选项前缀：`+，-`

- \- ：表示使这个选项生效
- +：表示取消这个选项的功能

选项：

- a：标记已修改的变量，可以输出至环境变量

- b：使被中止的后台程序立刻回报执行状态。

- C：转向所产生的文件无法覆盖已存在的文件。 

- d：Shell预设会用杂凑表记忆使用过的指令，以加速指令的执行。使用-d参数可取消。 

- e：若指令传回值不等于0，则立即退出shell。 (一般来说，一条命令返回0，表示正常退出)

- f：取消使用通配符。

- h：自动记录函数的所在位置。 

- H shell ：可利用"!"加<指令编号>的方式来执行history中记录的指令。 

- k：指令所给的参数都会被视为此指令的环境变量。 

- l：记录for循环的变量名称。 

- m：使用监视模式。 

- n：只读取指令，而不实际执行。 

- p：启动优先顺序模式。

- P：启动-P参数后，执行指令时，会以实际的文件或目录来取代符号连接。 

- t：执行完随后的指令，即退出shell。 

- u：当执行时使用到未定义过的变量，则显示错误信息。

- v：显示shell所读取的输入值。 

- x：执行指令后，会先显示该指令及所下的参数。

- o：是一个复合的选项，里面有一些子选项，可以使用set -o来查看这些子选项的名称和开启关闭状态

  allexport       off
  braceexpand     on
  emacs           on
  errexit         off
  errtrace        off
  functrace       off
  hashall         on
  histexpand      on
  history         on
  igncr           off
  ignoreeof       off
  interactive-comments    on
  keyword         off
  monitor         on
  noclobber       off
  noexec          off
  noglob          off
  nolog           off
  notify          off
  nounset         off
  onecmd          off
  physical        off
  pipefail        off
  posix           off
  privileged      off
  verbose         off
  vi              off
  xtrace          off

  其中pipefail 选项的作用是：包含管道命令的语句的返回值，会变成最后一个返回非零的管道命令的返回值。一般包含管道的命令，如下格式：

  `cmd1 | cmd2 | cmd3......| cmdn`，如果不设置这个选项，整个命令的返回值是cmdn的返回值，如果加上，返回值就是，从cmdn开始往前找，第一个返回非0的命令的返回值

