# FAQ

列出了在使用 TermuxArch 的过程中可能会遇到的问题。

## 什么是 Termux？

> Termux 是一款 Android 的终端模拟器和 Linux 环境的应用程序。
>
> 项目地址：[Termux-App]

[Termux-App]: https://github.com/termux/termux-app

## 什么是 TermuxArch？

> TermuxArch 是一个 Shell 脚本。它将在 Termux 环境中以 PRoot
> 的方式安装 Arch Linux，类似于 [Chroot]。
>
> 项目地址：[TermuxArch]

[TermuxArch]: https://github.com/sdrausty/TermuxArch
[Chroot]: https://zh.wikipedia.org/wiki/Chroot

## 什么是 Arch Linux？

> Arch Linux 是通用 x86-64 GNU/Linux 发行版。
> Arch Linux 采用滚动升级模式，尽全力提供最新的稳定版软件。
> 初始安装的 Arch Linux 只是一个基本系统，
> 随后用户可以根据自己的喜好安装需要的软件并配置成符合自己理想的系统.
>
> 官方网站：[Arch Linux]

[Arch Linux]: https://www.archlinux.org

## 什么是 PRoot？

> PROOT 是一个用户空间实现的 chroot，mount --bind 和 binfmt_misc。
> 这意味着用户不需要任何特殊权限或设置来执行诸如使用任意目录作为新的根文件系统。
>
>项目地址：[PRoot]

[PRoot]: https://github.com/proot-me/PRoot

## 为什么选用的 Arch Linux 系统？

> 只是因为在众多的 GUN/Linux 系统中，个人独爱 Arch Linux
> 而已（在我的笔记本电脑上也是安装的 Arch Linux 系统）。
> 如果您想要在 Termux 中安装其它的发行版可以参阅下面的链接。
>
> 参考链接：[PRoot - Termux Wiki]

[PRoot - Termux Wiki]: https://wiki.termux.com/wiki/PRoot

## Termux 中没有 Ctrl、Tab 等键。

+ 在 Termux 中，按住 `` 音量键加键 `` 和 `` Q 键 `` 可打开额外的按键视图，其中会有 Ctrl、Tab 等键。
+ 使用外接键盘

## 使用外接键盘在 Termux 中不能输入中文、Ctrl 等键不可用、能输入中文但不能选词。

+ 这可能是输入法对外接键盘支持太差导致的，建议使用 `` Google 拼音输入法 ``。

## 使用 Google 拼音输入法不能输入中文。

+ 在 Termux 中，按住 `` 音量键加键 `` 和 `` Q 键 `` 可打开一个额外的按键视图，再向左滑动，可在输入框中输入中文。
+ 在 Termux 开启 `` sshd `` 服务，然后再使用其它对中文输入友好的 ssh 工具连接到这个 sshd 服务。

## 在操作过程中不流畅，卡顿。

这是由于手机 I/O 和 CPU 性能太弱导致的。

+ 不要运行对硬件要求较大的软件。
+ 使用性能更好的手机。
