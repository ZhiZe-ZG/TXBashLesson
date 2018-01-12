# 操作系统内核Linux

1. Linux并不是一个完整的系统。它只是一个实现操作系统基本功能的内核。内核配以一系列其他的库和软件才能成为一个完整的操作系统。事实上，我们经常用Linux来指代一系列由Linux内核和GNU计划软件组成的操作系统。
1. GNU计划的目标是创建一套完全自由的操作系统。但这个系统的内核Hurd历经多年开发都没有稳定。 因此，反倒是GNU计划的其他软件配以同为开源软件的Linux形成的所谓GNU/Linux操作系统取得了成功。

    1 Introduction
    2 Common options
        2.2 Backup options
        2.3 Block size
        2.5 Signal specifications
        2.6 chown, chgrp, chroot, id: Disambiguating user names and IDs
        2.7 Sources of random data
        2.8 Target directory
        2.9 Trailing slashes
        2.10 Traversing symlinks
        2.11 Treating / specially
        2.12 Special built-in utilities
        2.13 Standards conformance
        2.14 coreutils: Multi-call program
    5 Output of parts of files
    分割和压缩放到一起说
        5.3 split: Split a file into pieces.
        5.4 csplit: Split a file into context-determined pieces
    6 Summarizing files
        6.1 wc: Print newline, word, and byte counts
        6.2 sum: Print checksum and block counts
        6.3 cksum: Print CRC checksum and byte counts
        6.4 b2sum: Print or check BLAKE2 digests
        6.5 md5sum: Print or check MD5 digests
        6.6 sha1sum: Print or check SHA-1 digests
        6.7 sha2 utilities: Print or check SHA-2 digests
    7 Operating on sorted files
        7.5 ptx: Produce permuted indexes
            7.5.1 General options
            7.5.2 Charset selection
            7.5.3 Word selection and input processing
            7.5.4 Output formatting
            7.5.5 The GNU extensions to ptx
    8 Operating on fields
        8.1 cut: Print selected parts of lines
        8.2 paste: Merge lines of files
        8.3 join: Join lines on a common field
            8.3.1 General options
            8.3.2 Pre-sorting
            8.3.3 Working with fields
            8.3.4 Controlling join’s field matching
            8.3.5 Header lines
            8.3.6 Union, Intersection and Difference of files
    9 Operating on characters
        9.1 tr: Translate, squeeze, and/or delete characters
            9.1.1 Specifying sets of characters
            9.1.2 Translating
            9.1.3 Squeezing repeats and deleting
        9.2 expand: Convert tabs to spaces
        9.3 unexpand: Convert spaces to tabs
    12 Special file types
        12.4 mkfifo: Make FIFOs (named pipes)
        12.5 mknod: Make block or character special files
    13 Changing file attributes
        13.1 chown: Change file owner and group
        13.2 chgrp: Change group ownership
        13.3 chmod: Change access permissions
    14 Disk usage
        14.1 df: Report file system disk space usage
        14.2 du: Estimate file space usage
        14.3 stat: Report file or file system status
        14.4 sync: Synchronize cached writes to persistent storage
        14.5 truncate: Shrink or extend the size of a file
    20 User information
        20.1 id: Print user identity
        20.2 logname: Print current login name
        20.3 whoami: Print effective user ID
        20.4 groups: Print group names a user is in
        20.5 users: Print login names of users currently logged in
        20.6 who: Print who is currently logged in
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
        23.2 env: Run a command in a modified environment
        23.3 nice: Run a command with modified niceness
        23.5 stdbuf: Run a command with modified I/O stream buffering
        23.6 timeout: Run a command with a time limit
    25 Delaying
        25.1 sleep: Delay for a specified time
    27 File permissions
        27.1 Structure of File Mode Bits
        27.2 Symbolic Modes
            27.2.1 Setting Permissions
            27.2.2 Copying Existing Permissions
            27.2.3 Changing Special Mode Bits
            27.2.4 Conditional Executability
            27.2.5 Making Multiple Changes
            27.2.6 The Umask and Protection
        27.3 Numeric Modes
        27.4 Operator Numeric Modes
        27.5 Directories and the Set-User-ID and Set-Group-ID Bits
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