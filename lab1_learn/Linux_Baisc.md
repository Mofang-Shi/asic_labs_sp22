
# Linux基础

[TOC]

## 介绍

本教程来自`UCB EECS151 ASIC Lab1`推荐阅读的教程：Learning the Shell：[Learning the Shell](http://linuxcommand.org/lc3_learning_the_shell.php)

## “Shell”是什么?

简而言之，Shell是一个**从键盘上获取命令并将其交给操作系统执行的程序**。在过去，它是Linux等类Unix系统上唯一可用的用户界面。如今，除了Shell等命令行界面（command line interfaces，CLI）外，我们还有图形用户界面（graphical user interfaces，GUI）。

在大多数Linux系统上，一个名为`bash`的程序（代表Bourne Again SHell，由Steve Bourne编写的原始Unix shell程序sh的增强版本）充当Shell程序。除了bash，还有其他适用于Linux系统的shell程序。这些包括：`ksh`、`tcsh`和`zsh`。

### 在终端（Terminal）键入/使用鼠标

打开一个终端窗口。我们应该看到的第一个东西是一个shell提示，其中包含我们的用户名和机器名称，后跟一个美元符号（$）。如下所示：

```shell
shimofang@shimofang-virtual-machine:~$ 
```

**向上箭头键**——上一个命令（Command history）
**向下箭头键**——回到空白行
**向左/右键**——移动光标
**使用鼠标**——复制文本

**超级用户（Superuser）**： 如果shell提示符的最后一个字符是`#`而不是`$`，则正在作为超级用户操作。这意味着拥有管理权限，可以删除或覆盖系统上的任何文件。
**除非绝对需要管理权限，否则不要作为超级用户操作！**

## 导航（Navigation）

这个部分将会使用到一下三个命令：`pwd`打印工作目录、`cd`更改目录、`ls`列表文件和目录

### `pwd`

我们所处的目录称为工作目录（Working directory）。要查看工作目录的名称，我们使用pwd命令：

```shell
shimofang@shimofang-virtual-machine:~$ pwd
/home/shimofang
```

当我们第一次登录Linux系统时，工作目录被设置为我们的主目录（home directory）。这就是我们放文件的地方。在大多数系统上，主目录将被称为`/home/user_name`，但根据系统管理员的奇思妙想，它可以是任何东西。

### `ls`

要列出工作目录中的文件，我们使用ls命令：

```shell
shimofang@shimofang-virtual-machine:~$ ls
公共的  模板  视频  图片  文档  下载  音乐  桌面  snap
```

### `cd`

要更改工作目录，我们使用cd命令：
`cd + 所需工作目录的路径名`
路径名可以指定两种不同的方式：`绝对路径名`或`相对路径名`。

**绝对路径名**从根目录开始，并逐个分支跟随树，直到所需目录或文件的路径完成。例如，您的系统上有一个目录，其中安装了大多数程序。目录的路径名是`/usr/bin`。这意味着从根目录（由路径名中的前导斜杠表示）有一个名为“usr”的目录，其中包含一个名为“bin”的目录。

```shell
shimofang@shimofang-virtual-machine:~$ cd /usr/bin
shimofang@shimofang-virtual-machine:/usr/bin$ pwd
/usr/bin
shimofang@shimofang-virtual-machine:/usr/bin$ ls
'['                                   mtr-packet
 aa-enabled                           mv
 aa-exec                              namei
 aa-features-abi                      nano
 aconnect                             nautilus
 acpi_listen                          nautilus-autorun-software
 add-apt-repository                   nautilus-sendto
 addpart                              nawk
 airscan-discover                     nc

and many more...
```

现在我们可以看到，我们已经将当前工作目录更改为/usr/bin，并且它充满了文件。注意shell提示是如何更改的吗？为了方便起见，它通常设置为**显示工作目录的名称**。

**相对路径名**从工作目录开始。为此，它使用几个特殊符号来表示文件系统树中的相对位置。
`.`——指工作目录本身、`..`——指工作目录的父目录

```shell
shimofang@shimofang-virtual-machine:~$ cd /usr/bin
shimofang@shimofang-virtual-machine:/usr/bin$ cd ..
shimofang@shimofang-virtual-machine:/usr$ cd ./bin
shimofang@shimofang-virtual-machine:/usr/bin$ 
```

**键入cd后不跟任何内容**——cd会将工作目录更改为我们的主目录。
**键入cd ~user_name**——cd会将工作目录更改为指定用户的主目录。
**键入cd-**——将工作目录更改为上一个目录。

### 关于文件名的重要事实

1、以句号字符开头的文件名被隐藏。除非我们用`ls -a`，否则ls不会列出它们。

2、Linux中的文件名和Unix一样，区分大小写。文件名“File1”和“file1”指的是不同的文件。

3、Linux没有像Windows系统那样的“文件扩展”概念。您可以以任何您喜欢的方式命名文件。但许多应用程序会关心文件扩展名。

4、虽然Linux支持可能包含嵌入式空格和标点符号的长文件名，但将标点符号限制为句号`.`、破折号`-`和下划线`_`。

5、最重要的是，**不要在文件名中嵌入空格**。如果您想表示文件名中单词之间的空格，请使用下划线字符。

## Looking Around

## A Guided Tour

## Manipulating Files

## Working with Commands

## I/O Redirection

## Expansion

## Permissions

## Job Control
