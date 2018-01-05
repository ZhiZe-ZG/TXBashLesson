
8. 如果在一个bash中通过bash命令打开了另一个bash，那么前者是父进程，后者是子进程。父进程中的变量在子进程中默认可见，反之则不然。
9. 父进程中声明的全局变量可以对子进程起效，但是子进程的对父进程无效。并且如果子进程修改或删除了父进程中定义的全局变量，不会影响到父进程。


退出状态,选择循环和运算,函数


0X05文件操作视频演示
0X06变量视频演示
0X07脚本视频演示


搜索等介绍了grep后介绍().grep顺便介绍bash的正则表达式完整版.

流式处理作为文件编辑介绍.

基本介绍bash之后介绍zsh

util-linux(设置tty等(setterm))和linux的kernel在一个网站(utils中)
也提供了cal等命令

终端设置和登陆

(systemd)shutdown,reboot

grep,less,diff

tree 命令

在一个shell中修改变量值,其实都是临时修改

chsh属于shadow

coreutils提供stty命令

设置tty的快捷键(查看用stty -a)
C-c,C-d等快捷键就是tty的快捷键.这些并非是shell的快捷键.


退出状态和执行时输出的结果不是一回事

文件编辑,文件查看,流式编辑器

用户管理
修改文件权限

进程管理

env命令(coreutils的)