<center><font size="8" color="#e9c341">setlocal和endlocal</font></center>

[TOC]

# 1 命令解释

这两个命令在批处理脚本中配合起来使用，可以为把变量保存在一个单独的地方，不受上下文中其他的同名变量的干扰。它就像PS中的一个图层，在新添加的图层上乱写乱画，撤掉图层后，对图层下面的内容没有任何影响。

# 2 举例

```bat
@echo off
set var=123
set num=4456
set a=ham
echo %var% %num% %a% %max%

rem 增加一个图层
setlocal

set var=abcd
set num=jkl
set a=efg
set max=1234567
echo %var% %num% %a% %max%

endlocal
rem 撤掉图层，就好像setlocal和setlocal之间的代码没运行一样。

echo %var% %num% %a% %max%

```

