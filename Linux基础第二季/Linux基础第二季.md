# Linux基础第二季

# 操作系统内核Linux

1. Linux并不是一个完整的系统。它只是一个实现操作系统基本功能的内核。内核配以一系列其他的库和软件才能成为一个完整的操作系统。事实上，我们经常用Linux来指代一系列由Linux内核和GNU计划软件组成的操作系统。
1. GNU计划的目标是创建一套完全自由的操作系统。但这个系统的内核Hurd历经多年开发都没有稳定。 因此，反倒是GNU计划的其他软件配以同为开源软件的Linux形成的所谓GNU/Linux操作系统取得了成功。


    14 Disk usage
        14.1 df: Report file system disk space usage
        14.2 du: Estimate file space usage
        14.3 stat: Report file or file system status
        14.4 sync: Synchronize cached writes to persistent storage
        14.5 truncate: Shrink or extend the size of a file


介绍包依赖的时候尽量避免循环依赖

先介绍基本的xterm

说明一下常用的bash环境变量。《Linux命令行与Shell脚本编程大全》里有个环境变量表
先介绍变量，然后介绍环境变量

尚未介绍的被依赖的包：
glibc
ncurses
readline
尚未介绍的拓展包（需要说明是对谁的拓展）：

依赖项只介绍单向依赖
可选的双向依赖作为功能拓展
（A，B相互依赖，B对A来说可选，但是A对B不可选。B为A的功能拓展。等同于B依赖于A，而A不依赖于B）
（如果A，B相互依赖，并且都为可选。视为配合，仍然放到功能拓展里介绍。）
（功能拓展里的包对介绍主题都是可选的，但是介绍主体对他们来说是不是可选的不重要。）
（功能拓展包不一定在介绍本体的时候完全介绍。一般介绍非常常用的，和本体一块写教程的或者在Arch中列为相互依赖的。）
流和管道

硬盘分区和文件系统格式化作为两层内容进行介绍

管道

虚拟终端
C-M-F1 进入终端
C-M-F7 返回图形化界面

arch官网可以查看包依赖关系


****
接下来简单复习并补充说明一下上一季介绍过的几类命令。首先是文件管理、输入输出流工具和文本编辑。
****
1. 目录、文件基本操作
    * tree 用树形图显示指定目录的结构（不属于busybox，有可能需要自行安装）
    * file 确定文件类型。该命令并未包含于busybox中，但是一般发行版会自带。
    * find 通过文件名查找文件
    * stat 显示文件或者文件系统的状态
    * md5sum 对文件进行md5检验
2. 标准输入输出流工具
    * xargs 在标准输入流的环境中执行命令（例如`find ./ | xargs ls`）。这个命令主要用于辅助一些不支持管道的命令。
3. 文本编辑
    * uniq 删除文本重复行
    * wc 显示文本行数字数等统计信息
    * cut 从文本行中提取部分内容
    * paste 把文本按行合并
    * join 连接两文本中具有相同字段的行
    * comm 逐行比较两个已排序的文件
    * diff 逐行比较文件
    * patch 给文件打补丁
    * tr 替换或删除字符


用户信息存放文件
/etc/passwd 保存用户基本信息
/etc/shadow 保存用户密码
组信息存放
/etc/group 保存组基本信息

归档压缩：tar,gzip
文件校验：md5,sha1

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

## 压缩、打包（归档）
* gzip(bzip2)(zip)  文件压缩与解压 
* tar 归档工具
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

非busybox命令：pstree
环境配置
* 查看环境变量
* 修改环境变量
* 编写配置文件


文件系统管理加上stat

正则表达式
用户和组管理

## 包管理
* dpkg
* apt

压缩归档
gzip 压缩
tar 归档
压缩就是节省数据存储所需要的空间
归档是把多个文件按目录结构打包
.tgz 为后缀的文件表示这是用gzip压缩过的tar文件
在Linux中这使用两个工具，但是在zip工具可以把这两个步骤结合

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

所有 GNU 软件包（已经在做教程的就移除）

3dldf  8sync  a2ps  acct  acm  adns  alive  anubis  apl  archimedes  aris  artanis  aspell  auctex  autoconf  autoconf-archive  autogen  automake  avl  ballandpaddle  barcode  bayonne  bazaar  bc  bfd  binutils  bison  bool  bpel2owfn  c-graph  ccaudio  ccd2cue  ccide  ccrtp  ccscript  cflow  cgicc  chess  cim  classpath  classpathx  clisp  combine  commoncpp  complexity  config  consensus  coreutils  cpio  cppi  cssc  cursynth  dap  datamash  dc  ddd  ddrescue  dejagnu  denemo  dia  dico  diction  diffutils  dionysus  direvent  djgpp  dominion  dr-geo  easejs  ed  edma  electric  emacs  emacs-muse  emms  enscript  eprints  epsilon  fdisk  ferret  findutils  fisicalab  foliot  fontopia  fontutils  freedink  freefont  freeipmi  freetalk  fribidi  g-golf  gama  garpd  gawk  gbehistun  gcal  gcc  gcide  gcl  gcompris  gdb  gdbm  gengen  gengetopt  gettext  gforth  ggradebook  ghostscript  gift  gimp  glean  gleem  glib  global  glpk  glue  gmediaserver  gmp  gnash  gnat  gnats  gnatsweb  gneuralnetwork  gnome  gnowsys  gnu-c-manual  gnu-crypto  gnu-pw-mgr  gnuae  gnuastro  gnubatch  gnubg  gnubiff  gnubik  gnucap  gnucash  gnucobol  gnucomm  gnudos  gnue  gnufm  gnugo  gnuit  gnujdoc  gnujump  gnukart  gnulib  gnumach  gnumed  gnumeric  gnump3d  gnun  gnunet  gnupg  gnupod  gnuprologjava  gnuradio  gnurobots  gnuschool  gnushogi  gnusound  gnuspeech  gnuspool  gnustandards  gnustep  gnutls  gnutrition  gnuzilla  goptical  gorm  gpaint  gperf  gprolog  grabcomics  greg  grep  gretl  groff  grub  gsasl  gsegrafix  gsl  gslip  gsrc  gss  gtick  gtk+  gtypist  guile  guile-cv  guile-dbi  guile-gnome  guile-ncurses  guile-opengl  guile-rpc  guile-sdl  guix  gurgle  gv  gvpe  gxmessage  gzip  halifax  health  hello  help2man  hp2xx  html-info  httptunnel  hurd  hyperbole  icecat  idutils  ignuit  indent  inetutils  inklingreader  intlfonts  jacal  java-getopt  jel  jtw  jwhois  kawa  kopi  leg  less  libc  libcdio  libdbh  liberty-eiffel  libextractor  libffcall  libgcrypt  libiconv  libidn  libjit  libmatheval  libmicrohttpd  libredwg  librejs  libsigsegv  libtasn1  libtool  libunistring  libxmi  lightning  lilypond  lims  linux-libre  liquidwar6  lispintro  lrzsz  lsh  m4  macchanger  mailman  mailutils  make  marst  maverik  mc  mcron  mcsim  mdk  mediagoblin  melting  metaexchange  metahtml  metalogic-inference  mifluz  mig  miscfiles  mit-scheme  moe  motti  mpc  mpfr  mpria  mtools  nana  nano  nano-archimedes  ncurses  nettle  network  ocrad  octave  oleo  oo-browser  orgadoc  osip  panorama  parallel  parted  pascal  patch  paxutils  pcb  pdf  pem  pexec  pgccfd  phantom_home  pies  pipo  plotutils  polyxmass  powerguru  proxyknife  pspp  psychosynth  pth  pyconfigure  pythonwebkit  qexo  quickthreads  r  radius  rcs  readline  recutils  reftex  remotecontrol  ring  rottlog  rpge  rush  sather  scm  screen  sed  serveez  sharutils  shepherd  shishi  shmm  shtool  sipwitch  slib  smalltalk  social  solfege  spacechart  speex  spell  sqltutor  src-highlite  stalkerfs  stow  stump  superopt  swbis  sysutils  taler  talkfilters  tar  termcap  termutils  teseq  teximpatient  texinfo  texmacs  thales  time  tramp  trans-coord  trueprint  unifont  units  unrtf  userv  uucp  vc-dwim  vcdimager  vera  vmgen  wb  wdiff  websocket4j  webstump  wget  which  womb  xaos  xboard  xhippo  xlogmaster  xmlat  xnee  xorriso  zile 

bash内置命令
 job_spec [&]                                                         
 . filename [arguments]                                                
 :                                        
 let arg [arg ...]
 local [option] name[=value] ...
 logout [n]
 mapfile [-n count] [-O origin] [-s count] [-t] [-u fd] [-C callback] [-c quantum] [array]
 bind [-lpsvPSVX] [-m keymap] [-f filename] [-q name] [-u name] [-r keyseq] [-x keyseq:shell->  popd [-n] [+N | -N]
 printf [-v var] format [arguments]
 pushd [-n] [+N | -N | dir]
 caller [expr]                                                                                          
 command [-pVv] command [arg ...]                                                    readonly [-aAf] [name[=value] ...] or readonly -p
 shift [n]
 coproc [NAME] command [redirections]                                                           shopt [-pqsu] [-o] [optname ...]
 declare [-aAfFgilnrtux] [-p] [name[=value] ...]                                                source filename [arguments]
 dirs [-clpv] [+N] [-N]
 time [-p] pipeline
 enable [-a] [-dnps] [-f filename] [name ...]                                                   times
 eval [arg ...]                                                                                 trap [-lp] [[arg] signal_spec ...]
 typeset [-aAfFgilrtux] [-p] name[=value] ...
 ulimit [-SHabcdefilmnpqrstuvxT] [limit]
 fc [-e ename] [-lnr] [first] [last] or fc -s [pat=rep] [command]                                                                               
 function name { COMMANDS ; } or name () { COMMANDS ; }                                         
 getopts optstring name [arg]                                                                  
 hash [-lr] [-p pathname] [-dt] [name ...]                                                     
