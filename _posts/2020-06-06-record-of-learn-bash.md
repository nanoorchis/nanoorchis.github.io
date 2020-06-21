---
layout: post
---
# 20200606目标

使用一行代码代替三行代码，git add commit push。

资源：https://wangdoc.com/bash/intro.html

bash与shell？shell是一个程序，一个命令解释器，一个工具箱。bash是shell的一种，全称为Bourne Again shell。

查看当前使用的bash。

```bash
$ echo SHELL   
/bin/bash
```

查看本机安装的bash。

```bash
$ cat /etc/shells
# List of acceptable shells for chpass(1).
# Ftpd will not allow users to connect who are not using
# one of these shells.

/bin/bash
/bin/csh
/bin/dash
/bin/ksh
/bin/sh
/bin/tcsh
/bin/zsh
```

查看bash 版本

```bash
$ bash --version
GNU bash, version 3.2.57(1)-release (x86_64-apple-darwin19)
Copyright (C) 2007 Free Software Foundation, Inc.
```

Shebang?指字符 “#!”。

Shebang行?脚本中以 “#!”开头的第一行。

执行脚本。$ ./script.sh

增加可执行权限。chmod +x script.sh。

最后同步的代码为

