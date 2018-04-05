# Linux基础第二季

1. Linux并不是一个完整的系统。它只是一个实现操作系统基本功能的内核。内核配以一系列其他的库和软件才能成为一个完整的操作系统。事实上，我们经常用Linux来指代一系列由Linux内核和GNU计划软件组成的操作系统。
1. GNU计划的目标是创建一套完全自由的操作系统。但这个系统的内核Hurd历经多年开发都没有稳定。 因此，反倒是GNU计划的其他软件配以同为开源软件的Linux形成的所谓GNU/Linux操作系统取得了成功。

    14 Disk usage
        14.1 df: Report file system disk space usage
        14.2 du: Estimate file space usage
        14.3 stat: Report file or file system status
        14.4 sync: Synchronize cached writes to persistent storage
        14.5 truncate: Shrink or extend the size of a file

说明一下常用的bash环境变量。《Linux命令行与Shell脚本编程大全》里有个环境变量表
先介绍变量，然后介绍环境变量

依赖项只介绍单向依赖
可选的双向依赖作为功能拓展
（A，B相互依赖，B对A来说可选，但是A对B不可选。B为A的功能拓展。等同于B依赖于A，而A不依赖于B）
（如果A，B相互依赖，并且都为可选。视为配合，仍然放到功能拓展里介绍。）
（功能拓展里的包对介绍主题都是可选的，但是介绍主体对他们来说是不是可选的不重要。）
（功能拓展包不一定在介绍本体的时候完全介绍。一般介绍非常常用的，和本体一块写教程的或者在Arch中列为相互依赖的。）
流和管道

硬盘分区和文件系统格式化作为两层内容进行介绍

虚拟终端
C-M-F1 进入终端
C-M-F7 返回图形化界面

arch官网可以查看包依赖关系

****
接下来简单复习并补充说明一下上一季介绍过的几类命令。首先是文件管理、输入输出流工具和文本编辑。
****


用户信息存放文件
/etc/passwd 保存用户基本信息
/etc/shadow 保存用户密码
组信息存放
/etc/group 保存组基本信息

12. 命令行小工具
    * clear 清屏
# 总计划
* 包管理：dpkg、apt
# 包含的工具包或者单体软件
* sudo
* xlogo
* shutdown
* apt
* ssh

## 权限、用户、群组
* id 显示用户身份标识
* su 以另一用户身份运行shell
* sudo 以另一用户身份执行命令
* xlogo 用窗体显示一个logo
## 存储介质管理
* mount 挂载文件系统 在挂载之前，设备并不是一个目录
* umount 卸载文件系统
* fdisk 硬盘分区 设备需要先分区然后创建文件系统
* mkfs 创建文件系统
* fsck 检查修复文件系统
* dd 直接操作存储器数据
* df 查看已挂载磁盘使用情况    df -h
* du 查看制定目录磁盘使用情况
## 网络
* ping 检查网络联通状况
* traceroute 显示数据包到网络主机的路由路径
* netstat 检查网络设置及相关统计数据
* ftp 用FTP（文件传输协议）传输文件
* wget 非交互式网络下载工具
* rsync 远程文件同步
* ssh 安全登录远程计算机。ssh程序还提供scp和sftp命令，用于安全传输文件。
## Linux包管理
* dpkg （包含于busybox）
* apt （未包含于busybox）
pacman

环境配置
* 查看环境变量
* 修改环境变量
* 编写配置文件

文件系统管理加上stat

sudo不能使用bash内嵌命令。

## 环境变量 
* 所谓的环境变量就是控制bash工作环境的变量。对环境变量进行调整就能影响到shell的工作方式。所以调整环境变量其实就是在设置bash。
* 环境变量分为两类：全局变量对所有的shell进程都可见，而局部变量只在创建它的进程可见（创建它的进程关闭后则消失）
## 环境设置
* printenv 输出环境变量到标准输出流

* 系统初始化的全局环境变量，变量名字母全为大写。
* 直接在标识符后使用等号赋值，即可创建环境变量。（值可以是数值或字符串）
* 这样创建的环境变量只是局部变量。就是在当前shell的子shell中也不能使用。
* 全局变量在该进程和其所有子进程可见。但关闭进程后还是得重新设置。
* 可以把设置写到随shell启动的脚本中，这样就不用每次设置。
* 如果在子进程中使用删除全局变量操作，这个操作仅仅对这个子进程有效。
关于设置bash具体项目的系统环境变量名，可以通过帮助手册查看
演示一个自定义命令提示符。还有把home文件夹设置入PATH

登陆bash后启动的文件
按顺序
/etc/profile
$HOME/.bash_profile
$HOME/.bash_login
$HOME/.profile
后三个文件一般只用一个。例如Debian用.profile
如果bash不是随登陆启动的（例如是在另一个bash中通过bash命令启动的）。这种bash叫做交互式bash。交互式bash不读取以上四个文件，而会读取
$HOME/.bashrc
而这个文件会先访问
/etc/bashrc

这一系列机制保证了有公共执行的部分也有用户自定义的空间

nohup
screen


arch等命令,查看系统信息