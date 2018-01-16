# 操作系统内核Linux

1. Linux并不是一个完整的系统。它只是一个实现操作系统基本功能的内核。内核配以一系列其他的库和软件才能成为一个完整的操作系统。事实上，我们经常用Linux来指代一系列由Linux内核和GNU计划软件组成的操作系统。
1. GNU计划的目标是创建一套完全自由的操作系统。但这个系统的内核Hurd历经多年开发都没有稳定。 因此，反倒是GNU计划的其他软件配以同为开源软件的Linux形成的所谓GNU/Linux操作系统取得了成功。

    2 Common options
        2.2 Backup options
        2.3 Block size
        2.5 Signal specifications
        2.7 Sources of random data
        2.8 Target directory
        2.9 Trailing slashes
        2.10 Traversing symlinks
        2.11 Treating / specially
        2.12 Special built-in utilities
    14 Disk usage
        14.1 df: Report file system disk space usage
        14.2 du: Estimate file space usage
        14.3 stat: Report file or file system status
        14.4 sync: Synchronize cached writes to persistent storage
        14.5 truncate: Shrink or extend the size of a file
    21 System context
        21.1 date: Print or set system date and time
            21.1.1 Time conversion specifiers
            21.1.2 Date conversion specifiers
            21.1.3 Literal conversion specifiers
            21.1.4 Padding and other flags
            21.1.5 Setting the time
            21.1.6 Options for date
            21.1.7 Examples of date
        21.2 arch: Print machine hardware name
        21.3 nproc: Print the number of available processors
        21.4 uname: Print system information
        21.5 hostname: Print or set system name
        21.6 hostid: Print numeric host identifier
        21.7 uptime: Print system uptime and load
    22 SELinux context
        22.1 chcon: Change SELinux context of file
        22.2 runcon: Run a command in specified SELinux context
    23 Modified command invocation
        23.1 chroot: Run a command with a different root directory
        23.3 nice: Run a command with modified niceness
        23.5 stdbuf: Run a command with modified I/O stream buffering
        23.6 timeout: Run a command with a time limit
    25 Delaying
        25.1 sleep: Delay for a specified time
    29 Date input formats
        29.1 General date syntax
        29.2 Calendar date items
        29.3 Time of day items
        29.4 Time zone items
        29.5 Combined date and time of day items
        29.6 Day of week items
        29.7 Relative items in date strings
        29.8 Pure numbers in date strings
        29.9 Seconds since the Epoch
        29.10 Specifying time zone rules
        29.11 Authors of parse_datetime
    30 Opening the Software Toolbox
        Toolbox Introduction
        I/O Redirection
        The who Command
        The cut Command
        The sort Command
        The uniq Command
        Putting the Tools Together