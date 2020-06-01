# TermuxArch 安装教程

这是一份有关于 TermuxArch 的详细安装教程，
可以帮助您完成 TermuxArch 的安装。

## 前言

就我个人而言，手机只是一个通讯工具，但通讯功能对于现代手机来说只是无限功能中的一个小功能。
对其并没有物尽其用，所以打算折腾一下，在 Android 手机上安装一个完整的 Linux 系统，
来替代一下自己原来在 Linux 桌面系统上的部分开发工作（当然，也仅限于小项目）。

目前在 Android 手机上运行完整的 Linux 系统有很多种方法，网上也有各种的教程，这里就不赘述，
如果需要了解的话可以点击括号中的链接（[ChrootOnAndroid]）进行查阅。

在根据自己的需求权衡后，选用了 `` Termux + TermuxArch `` 这个方案，要实现这个方案会有以下的两个步骤。

[ChrootOnAndroid]: https://wiki.debian.org/ChrootOnAndroid

## 安装

首先，为了保证最低的体验，您的 Android 手机需要满足以下的条件。

+ Android 系统的版本不能低于 5.0。
+ 手机可用的 RAM 不小于 1GB。
+ Android 系统中的 data 分区可用空间不少于 1.5 GB。
+ 手机处于一个高速且稳定的网络环境下。

如果想要获得更好的体验，您的 Android 手机至少需要满足以下的条件。

+ Android 系统的版本不能低于 5.0。
+ 手机可用的 RAM 不小于 2GB。
+ Android 系统中的 data 分区可用空间不小于 3 GB。
+ 手机处于一个能无障碍访问国际互联网的高速且稳定的网络环境下。
+ 手机有一个高性能的 CPU。

当然，您也应该至少需要会一种 Linux 终端下的编辑器（vi(m)、nano、emacs...）以及 [Shell] 的基础语法。

[Shell]: https://github.com/qinjx/30min_guides/blob/master/shell.md

### 安装 Termux

打开下面的链接地址，然后下载 Termux 的安装包到手机上并安装它。

> [Termux on F-Droid]

在安装完成 Termux 后手机就已有一个简陋的 Linux 环境了。
但是目前 Termux 可用的软件包太少，虽然可以自己通过 [交叉编译] 软件包，
但是会有些繁琐，所以就借助 TermuxArch 这个脚本来以 PRoot 的方式安装一个完整的
Arch Linux 系统（架构为 [ARM]）。

[Termux on F-Droid]: https://f-droid.org/packages/com.termux/
[交叉编译]: https://github.com/termux/termux-packages
[ARM]: https://zh.wikipedia.org/wiki/ARM架構

### 安装 Arch Linux

打开刚才安装的 Termux，然后依次执行下面的命令，而后它会开始自动安装 Arch Linux。

``` BASH
pkg install curl

bash -c "$(curl -fsSL https://git.io/vNtJl)"
```

在安装的过程中应该会有 **四次** 交互式提示，在这里只对其进行解释，您可以根据自身的需求修改相应的内容。

+ Would you like to use nano or vi to edit the Arch Linux configuration files? Answer nano or vi [n/V]?

```TEXT
这一步是让您在 nano 和 vi 这两个编辑器中选择一个编辑器去修改软件源。

备注：目前我的所在地访问官方源速度还不错，所以我没有修改软件源。
      如果需要修改的话，由于我个人是 Vim 的重度用户，所以我会输入 V 可以进入 Vi 编辑器，
      在修改完成后输入 :wq 可保存并退出 Vi 编辑器。
```

+ Would you like to run locale-gen with the English en_US.UTF-8 locale only? Answer yes to generate the English en_US.UTF-8 locale only [Y|e]

```TEXT
这一步是设置系统的区域设置。

备注：如果不需要显示中文，可以输入 Y 跳过这一步。
      如果需要显示中文，输入 e 进行编辑，再将下面两行内容前面的注释（也就是符号 #）去掉。

      en_US.UTF-8 UTF-8
      zh_CN.UTF-8 UTF-8
```

+ Add the tzselect output code to .bash_profile so the system time in Arch Linux for future sessions will be set correctly.

```TEXT
这一步设置系统的时区。

备注：这一步只是引导您去设置时区，并不会真正的修改系统的时区设置。
      如果您需要知道如何设置中国的标准时区只需依次输入 4、9、1、1 即可。
```

+ Copy startarch to /data/data/com.termux/files/usr/bin? Answer yes or no [Y|n]

```TEXT
这一步是让您选择是否将 startarch 脚本从 arch 目录复制到 /data/data/com.termux/files/usr/bin 目录。

备注：建议选择复制，这样在下一次启动 Arch 时会更方便，所以输入 Y 即可。
```

如果您已完成了上面的步骤，那么您应该已成功进入了所安装的 Arch Linux 中。

因此，开始体验美妙的 Arch Linux 吧。

## 须知

+ 如果需要进入 Arch Linux 系统中，在 Termux 中执行 `` startarch `` 命令即可。
+ 如果需要退出 Arch Linux 系统并返回到 Termux 中，执行 `` exit `` 命令即可。
+ 由于手机屏幕大小有限，而又需要在输入时留有较大的屏幕空间来浏览相应的信息，建议通过 [OTG] 或蓝牙连接外部键盘进行输入。
+ 由于 data 分区的空间有限又不便于扩展，所以在使用 Arch Linux 的时候，如果进行了安装软件包的操作，建议执行 `` pacman -Scc `` 命令来清理缓存的软件包。

[OTG]: https://zh.wikipedia.org/wiki/USB_On-The-Go
