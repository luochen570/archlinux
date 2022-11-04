Arch Linux的原则
简单
Arch Linux 将简单定义为没有不必要的添加或修改。它发布由原始开发人员（上游）发布的软件，具有最小的特定于发行版（下游）的更改：避免上游不接受的补丁，Arch 的下游补丁几乎完全由项目的下一个版本过时的向后移植的错误修复组成。
以类似的方式，Arch 发布了上游提供的配置文件，其更改仅限于特定于发行版的问题，例如调整系统文件路径。它不会仅仅因为安装了软件包而添加了诸如启用服务之类的自动化功能。仅当存在引人注目的优势时才拆分包，例如在特别严重的浪费情况下节省磁盘空间。官方未提供 GUI 配置实用程序，鼓励用户从 shell 和文本编辑器执行大多数系统配置。
现代性
Arch Linux 努力维护其软件的最新稳定版本，只要可以合理地避免系统包损坏。它基于滚动发布系统，允许一次性安装并持续升级。
Arch 整合了许多可供 GNU/Linux 用户使用的新特性，包括systemd init 系统、现代文件系统、LVM2、软件 RAID、udev 支持和 initcpio（带有mkinitcpio），以及最新的可用内核。
实用主义
Arch 是一种实用的分布，而不是意识形态的分布。这里的原则只是有用的指导。最终，设计决策是通过开发人员的共识逐案做出的。重要的是基于证据的技术分析和辩论，而不是政治或流行观点。
各种 Arch Linux 存储库中的大量软件包和构建脚本为喜欢它的人提供免费和开源软件，并为那些拥抱功能胜过意识形态的人提供专有软件包。
用户中心性
尽管许多 GNU/Linux 发行版都试图对用户更加友好，但 Arch Linux 一直是，并且将始终保持以用户为中心。该发行版旨在满足为其贡献者的需求，而不是试图吸引尽可能多的用户。它面向精通 GNU/Linux 的用户，或任何愿意阅读文档并解决自己问题的自己动手的态度的人。
鼓励所有用户参与并为分发做出贡献。报告和帮助修复错误受到高度重视，并且非常感谢补丁改进包或核心项目：Arch 的开发人员是志愿者，积极的贡献者经常会发现自己成为该团队的一部分。Archers可以自由地向Arch 用户存储库贡献包，改进ArchWiki 文档，向他人提供技术帮助，或者只是在论坛、邮件列表或IRC 频道中交换意见。. Arch Linux 是全球许多人首选的操作系统，并且存在多个国际社区提供帮助并提供多种不同语言的文档。
多功能性
Arch Linux 是一个通用的发行版。安装时只提供命令行环境；用户无需删除不需要和不需要的包，而是可以通过在x86-64架构 的官方存储库中提供的数千个高质量包中进行选择来构建自定义系统。
Arch 是一个由pacman支持的滚动发布模型， pacman是一个轻量级、简单和快速的包管理器，允许使用一个命令持续升级整个系统。Arch 还提供Arch Build System，一个类似端口的系统，可以轻松地从源代码构建和安装包，也可以与一个命令同步。此外，Arch 用户存储库包含数千个社区贡献的PKGBUILD脚本，用于使用makepkg应用程序从源代码编译可安装包。用户也可以轻松地构建和维护自己的自定义存储库。

#以上是本人从Arch wiki介绍里面扣下来的
#接下来是我的个人叭叭时间
个人认为Arch Linux不适合刚刚接触Linux的萌新，它适合的是敢于尝试（作死）会自己百度google长问题有一定解决能力的用户的，假如你不是请转战其他发行版。

ArchLinux拥有最好用的wiki和aur（由用户维护和主导的软件包仓库）并且是一个滚动发行版（软件版本滚过来滚过去）没有固定的版本号。很适合日常使用（折腾）很高的可定制化（连图形化安装程序都没有哦，所有都需要自己安装设置）。arch用户永远都懂得如何善于使用各种搜索引擎和翻阅wiki资料等解决自己的问题，甚至敢于独自尝试gentoo（从安装到使用都在编译。。。。）这样的Linux发行版。很多情况下arch用户可以自己独立解决一些常见的问题和报错。因为他们拥有世界上最好的linux wiki————>>Arch Wiki。

本教程根据ArchWiki 安装指南（Installation guide） 建议阅读（General recommendations） 软件列表（List of applications）所进行编写

首先获取archlinux镜像
可以从archlinux官网获取
https://archlinux.org/download/
#个人推荐去镜像站下载例如
https://mirrors.tuna.tsinghua.edu.cn				#清华大学开源软件镜像站
http://mirrors.ustc.edu.cn					#中国科技大学开源软件镜像站
https://developer.aliyun.com/mirror				#阿里巴巴开源镜像站
https://mirrors.huaweicloud.com/home				#华为开源镜像站

烧录启动盘
烧录USB启动盘可以使用Ventoy、Rufus、balenaEtcher或者dd命令
#推荐ventoy烧录一次即可一直使用
Ventoy								#官网教程：https://www.ventoy.net/cn/doc_start.html
Rufus								#官网教程：https://rufus.ie
balenaEtcher							#官网教程：https://www.balena.io/etcher/
dd								#命令示范： sudo dd if=~/archlinux-2022.**.**-x86_64.img of=/dev/sda
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
烧录启动盘记得备份U盘数据 U盘有价，数据无价

进入主板 BIOS 进行设置
各主板厂商进Bios入按键不同通常是ESC、F1、F2、F4、F8、F12、Del等一一尝试或者百度搜索对应型号即可
进入bios后关闭安全启动（Secure Boot）设置为Disable后按F10保存重启
插入U盘开机进入临时启动项选择按键与进入bios按键相似但不同可以一一尝试或者百度搜索对应型号
选中启动盘回车启动
此时你应该可以看见屏幕上会有代码在跑请稍等片刻
当你看见 “root@archiso ~#" 和不断闪烁的”◼️“时就可以进行下一步了

首先连接网络
若您是无线连接网络请看这一步若您是有线连接请直接跳过这一步
iwctl								#进入交互式命令行
device list							#列出无线网卡设备名，比如无线网卡看到叫 ”wlan0“
station wlan0 scan 						#扫描网络
station wlan0 get-networks					#列出所有wifi网络
station wlan0 connect wifi-name 				#连接无线网络（Wifi）输入密码后回车即可
exit								#连接成功后退出

ping www.archlinux.org						#ping archlinux官网测试网络连通性

pacman -Syyu							#使用更新命令测试镜像源速度若速度较慢请更换镜像源

#更换镜像源
#使用Reflector选择在最近同步的，位于中国的5个镜像，然后根据下载速度进行排序自动还源
sudo reflector --verbose -c China --latest 5 --sort rate --threads 100 --save /etc/pacman.d/mirrorlist
#手动更换镜像源
nano /etc/pacman.d/mirrorlist
#将下列镜像站写到文件
# 中国科学技术大学开源镜像站
Server = https://mirrors.ustc.edu.cn/archlinux/$repo/os/$arch 
# 清华大学开源软件镜像站
Server https://mirrors.tuna.tsinghua.edu.cn/archlinux/$repo/os/$arch 
# 华为开源镜像站
Server = https://repo.huaweicloud.com/archlinux/$repo/os/$arch 

pacman -Syyu							#再次检查镜像源速度速度假如很慢请更换镜像源

timedatectl set-ntp true					#将系统时间与网络时间进行同步
timedatectl status						#检查服务状态

#接下来开始分区
lsblk -i							#显示硬盘分区情况
cfdisk /dev/sd*							#利用进行分区工具cfdisk进行分区
cfdisk /dev/nvmen*

普通情况下分区分三个分别为 "/boot/efi/" "/" "swap"
/boot/efi	efi分区		通常在300mb-1G    安装引导文件
/		linux根分区	建议30G以上上不封顶     Linux根分区
swap		交换分区	建议设置为内存的一半到两倍（16G内存可以不用设置）     休眠睡眠

格式化对应硬盘 
mkfs.fat -F32 /dev/sd**
mkfs.btrfs /dev/sd**
mkswap /dev/sd**

#创建挂载点&挂载对应分区
mount /dev/sd** /mnt
mkdir /mnt/home
mkdir /mnt/boot
mkdir /mnt/boot/efi
mkdir /mnt/@
mkdir /mnt/@home
mount /dev/sd** /mnt/boot/efi
swapon /dev/sd**

#安装基本系统
pacstrap /mnt base base-devel linux linux-firmware
#安装基本工具
pacstrap /mnt dhcpcd iwd vim sudo zsh zsh-completions

#生成fstab文件
genfstab -U /mnt >> /mnt/etc/fstab

#chroot进新系统
arch-chroot /mnt

#设置时区
ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

#同步硬件时间
hwclock --systohc

#设置Locale（本土化设置）
nano /etc/locale.gen
#取消下列两行注释（#）
#en_US.UTF-8 UTF-8
#zh_CN.UTF-8 UTF-8
#生成Locale文件
locale-gen

#设置主机名（写入自己想用的主机名）
nano /etc/hostname
#设置hosts
nano /etc/hosts
#在该文件中加入以下几行
127.0.0.1   localhost
::1         localhost
127.0.1.1   主机名.localdomain	主机名

#设置root账户密码
passwd root

#安装引导程序
pacman -S grub efibootmgr os-prober
#修改grub配置
nano /etc/default/grub
#添加这一行引导硬盘上的其它系统例如win10
GRUB_DISABLE_OS_PROBER=false
#生成GRUB引导文件
grub-mkconfig -o /boot/grub/grub.cfg

至此基本系统已经安装完毕







但是没有安装图形化界面（桌面环境&窗口管理器）
关于桌面环境和窗口管理器详见wiki                wiki链接： https://wiki.archlinux.org/title/Category:Graphical_user_interfaces

















#关于ArchLinux的进阶操作指南
#本教程由luochen570（洛尘）编写
#本教程所有操作均在安装好ArchLinux后进行
#本教程不保证ArchLinux衍生版能够适用


#关于pacman.conf(以下操作均在 /etc/pacman.conf 中进行)
sudo nano /etc/pacman.conf

#开启32位库，取消以下两行取消注释（去除前面的”#“）
[multilib]
Include = /etc/pacman.d/mirrorlist

#添加archlinuxcn源（包含中文用户常用软件、工具、字体/美化包等）
#在 /etc/pacman.conf 结尾添加下列两行
[archlinuxcn]
Server = https://mirrors.tuna.tsinghua.edu.cn/archlinuxcn/$arch
#安装 archlinuxcn-keyring
sudo pacman -Sy archlinuxcn-keyring

#添加Chaotic-AUR自动构建仓库(自动编译常用的3000个AUR包)       #官网：https://github.com/chaotic-aur
#添加密钥和软件源
sudo pacman -U 'https://mirrors.aliyun.com/chaotic-aur/chaotic-keyring.pkg.tar.zst' 'https://mirrors.aliyun.com/chaotic-aur/chaotic-mirrorlist.pkg.tar.zst'
#在 /etc/pacman.conf 结尾添加下列两行
[chaotic-aur]
Include = /etc/pacman.d/chaotic-mirrorlist

#在 /etc/pacman.conf 中 ”Misc options“ 字段后添加修改对应选项
ParallelDownloads = 10		#并行下载（本人一般设置为20，榨干网络带宽）
VerbosePkgLists			#列表显示更新或安装的名称、版本和大小等信息
IloveCandy 			#吃豆人皮肤（应该是彩蛋吧？）
Color				#pacman&yay命令行高亮
#禁用签名检查（⚠️危险操作）
SigLevel = Never
#LocalFileSigLevel = Optional
#RemoteFileSigLevel = Required



#关于 makepkg.conf （以下操作均在/etc/makepkg.conf 中进行）
sudo nano /etc/makepkg.conf

#aur多线程下载
#安装axel
sudo pacman -S axel
#将第一段注释掉,在下面添加第二段

DLAGENTS=('file::/usr/bin/curl -qgC - -o %o %u'
          'ftp::/usr/bin/curl -qgfC - --ftp-pasv --retry 3 --retry-delay 3 -o %o %u'
          'http::/usr/bin/curl -qgb "" -fLC - --retry 3 --retry-delay 3 -o %o %u'
          'https::/usr/bin/curl -qgb "" -fLC - --retry 3 --retry-delay 3 -o %o %u'
          'rsync::/usr/bin/rsync --no-motd -z %u %o'
          'scp::/usr/bin/scp -C %u %o')

#axel
DLAGENTS=('file::/usr/bin/curl-gqC - -o %o %u'
          'ftp::/usr/bin/axel -n 15 -o %o %u'
          'http::/usr/bin/axel-n15-o %o %u'
          'https::/usr/bin/axel -n 15 -o %o %u'
          'rsync::/usr/bin/rsync--no-motd -z %u %o'
          'scp::/usr/bin/scp -C %u %o')

#修改下列选项提升AUR编译速度
#多线程编译aur包(根据自己cpu线程修改)
MAKEFLAGS="-j16"
#将构建目录移动到tmpfs（⚠️危险操作请谨慎操作:避免在 tmpfs 中编译较大的包，以防止内存不足）
BUILDDIR=/tmp/makepkg makepkg


#以上所有操作完成后请更新系统 sudo pacman -Syyu 




#更换默认内核
#内核推荐
linux-hardened			#注重安全的 Linux 内核，采用一系列加固补丁以缓解内核和用户空间漏洞,但是部分内核软件包会失效
linux-lts			#受长期支持（LTS）的 Linux内核，可以放心地在更长的时间内享受相同的内核版本，稳定性最好
linux-zen			#日常使用游戏娱乐的优秀内核，以吞吐量和功耗为代价调整内核的响应能力，加入了Fsync 功能，游戏表现优秀
linux-clear			#英特尔Clear Linux项目的补丁，提供性能和安全优化
linux-galliumos			#带有Chromebook的GalliumOS补丁的Linux内核和模块
linux-xanmod			#充分利用设备性能，可以提供更坚如磐石、响应速度更快、更流畅的桌面体验
#以linux-zen为例需要安装linux-zen-headers

#安装内核
yay -S linux-lts linux-lts-headers

#！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！
#注意更换非默认内核后虽然可以提高稳定性性能等等，但原有的显卡驱动内核补丁等需要更换为dkms版本。默认内核和非默认内核可能会有驱动内核dkms冲突建议卸载默认内核linux
sudo pacman -Rsc linux linux-headers

#修改GRUB设置
sudo nano /etc/default/grub
#修改对应条目
GRUB_DEFAULT=saved			#默认使用保存的内核条目
GRUB_SAVEDEFAULT=true			#保存最后一个使用的内核条目
GRUB_DISABLE_SUBMENU=y			#禁用GRUB子菜单，更方便选择内核

#使用grub-mkconfig工具生成/boot/grub/grub.cfg，更新引导配置
sudo grub-mkconfig -o /boot/grub/grub.cfg
#！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！
#更新内核后请重启

#archwiki 内核
https://wiki.archlinux.org/title/Kernel_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)




#笔记本双显卡切换optimus-manager
yay -S optimus-manager optimus-manager-qt
#设置 optimus-manager服务开机自启
sudo systemctl enable optimus-manager.service




#Fcitx5
sudo pacman -S fcitx5-im fcitx5-chinese-addons fcitx5-rime fcitx5-pinyin-zhwiki fcitx5-pinyin-zhwiki-rime fcitx5-pinyin-moegirl-rime fcitx5-configtool fcitx5-nord fcitx5-material-color fcitx5-solarized rime-cloverpinyin rime-emoji noto-fonts-emoji

fcitx5-im				#提供了fcitx5本体的包,配置工具和必要的输入法模块
fcitx5-chinese-addons			#包含与中文相关的插件，例如拼音、双拼和五笔
fcitx5-rime				#使用Rime引擎(可以使用四叶草输入法)
fcitx5-pinyin-zhwiki			#根据中文维基百科创作的词库。适用于拼音输入法
fcitx5-pinyin-zhwiki-rime		#根据中文维基百科编制的用于Rime输入法的词库
fcitx5-pinyin-moegirl-rime		#根据萌娘百科编制的用于Rime输入法的词库
fcitx5-nord				#Nord颜色的主题
fcitx5-material-color			#类似微软拼音的主题
fcitx5-solarized			#Solarized颜色主题
rime-cloverpinyin			#适用于Rime的四叶草输入方案
rime-emoji				#emoji表情字体（解决emoji 字体呈方块状）
noto-fonts-emoji			#emoji表情字体（解决emoji 字体呈方块状）

#添加环境变量
sudo nano /etc/environment
#Fcitx
GTK_IM_MODULE=fcitx
QT_IM_MODULE=fcitx
XMODIFIERS=@im=fcitx
SDL_IM_MODULE=fcitx
GLFW_IM_MODULE=ibus

#四叶草输入方案变量配置
#详细请访问https://www.fkxxyz.com/d/cloverpinyin/#%E5%9F%BA%E6%9C%AC%E9%85%8D%E7%BD%AE
nano ~/.local/share/fcitx5/rime/default.custom.yaml
#cloverpinyin
patch:
  "menu/page_size": 7
  schema_list:
    - schema: clover

#四叶草输入方案官网
https://www.fkxxyz.com/d/cloverpinyin/

#Fcitx5需要重启后生效
#皮肤需要在配置附加组件——>经典用户界面——>主题 修改
#四叶草输入方案需要使用rime输入法输入时按F4切换

fcitx5-diagnose				#通常可以找到fcitx5报错的原因

#archwiki Fcitx5
https://wiki.archlinux.org/title/Fcitx5_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)




#zsh&Oh My Zsh
#安装zsh
sudo pacman -S zsh
#安装Oh My Zsh
git clone https://mirrors.tuna.tsinghua.edu.cn/git/ohmyzsh.git
cd ohmyzsh/tools
REMOTE=https://mirrors.tuna.tsinghua.edu.cn/git/ohmyzsh.git sh install.sh

#插件推荐以及配置
sudo					#双击ESC自动加sudo&为上一条自动加上sudo
zsh-autosuggestions			#自动补全
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
zsh-syntax-highlighting			#高亮显示常用命令
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
incr					#超级好用的自动补全！！！
mkdir ~/.oh-my-zsh/custom/plugins/incr
cd ~/.oh-my-zsh/custom/plugins/incr
wget -O incr.plugin.zsh http://mimosa-pudica.net/src/incr-0.2.zsh 
# wget -O ~/.oh-my-zsh/plugins/incr/incr.plugin.zsh http://mimosa-pudica.net/src/incr-0.2.zsh 

#配置zsh
nano ~/.zshrc
#对应部分改为
plugins=(git
        sudo
        zsh-syntax-highlighting
        zsh-autosuggestions)
#最后加上
source ~/.oh-my-zsh/custom/plugins/incr/incr*.zsh

#zsh主题美化
#Powerlevel10k安装
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
#国内用户可以使用 http://gitee.com 上的官方镜像加速下载
git clone --depth=1 https://gitee.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k

nano ~/.zshrc
#修改对应内容
ZSH_THEME="powerlevel10k/powerlevel10k"

#部分用户可能会有字体问题，请安装Nerd Fonts系列字体即解决
#以下为官方推荐字体
https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf

#主题地址
https://github.com/romkatv/powerlevel10k




#ASCII 艺术与终端
#neofetch
#显示发行版的LOGO以及系统信息
sudo pacman -S neofetch
#例如 neofetch 

#pfetch
#简洁的显示发行版LOGO和一些系统信息
sudo pacman -S pfetch
#例如 pfetch

#lolcat
#用渐变为终端输出着色，看起来就像彩虹一样！
sudo pacman -S lolcat
#例如 neofetch | lolcat

#figlet
#用字符表示艺术文字
sudo pacman -S figlet
#例如 echo "pacman -Syyu" | figlet

#archwiki相关内容
https://wiki.archlinux.org/title/ASCII_art




#应用推荐
#浏览器
#Firefox				#Mozilla基金会及其非营利子公司Mozilla公司开发的开源浏览器
sudo pacman -S firefox
#Google Chrome				#Google开发的免费网页浏览器
yay -S goole-chrome
#Chromium				#Chromium是Google的开源浏览器，和Chrome共享大多数代码
sudo pacman -S chromium
#Vivaldi				#基于Chromium的功能定制化更强的浏览器
sudo pacman -S vivaldi

#办公Office
#WPS Office				#金山一站式服务办公软件，最适合国人的office软件
yay -S wps-office-cn ttf-wps-fonts
#LibreOffice				#一款功能强大的Linux老牌办公软件
sudo pacman -S libreoffice-still libreoffice-still-zh-cn
#Onlyoffice				#类似微软office界面的办公软件
yay -S onlyoffice-bin


#聊天通讯
#qq
#deepin-wine-qq				#移植Deepin打包的QQ容器（com.qq.im.deepin）到arch		项目地址：https://github.com/vufa/deepin-wine-qq-arch
yay -S deepin-wine-qq
#linuxqq				#腾讯官方的原生QQ，仿佛回到了2008年的界面
sudo pacman -S linuxqq
#icalingua++				#通过实现 Adapter 后端接口来适配的第三方客户端

#tim
#deepin-wine-tim			#移植Deepin打包的QQ容器（com.qq.im.deepin）到Arch		项目地址：https://github.com/vufa/deepin-wine-tim-arch
yay -S deepin-wine-tim

#微信
#deepin-wine-wechat			#移植Deepin打包的微信容器( com.qq.weixin.deepin)到Arch		项目地址：https://github.com/vufa/deepin-wine-wechat-arch
yay -S deepin-wine-wechat

#视频播放器
#vlc					#一个老牌免费开源的跨平台多媒体播放器和框架，播放大多数多媒体文件以及流媒体
sudo pacman -S vlc
#kodi					#免费和开源(GPL)软件媒体播放器和娱乐中心

#实用工具
#ventoy					#新一代多系统启动U盘解决方案，将镜像拷贝到U盘即可
yay -S ventoy-bin

#qbittorrent				#著名开源图形化bt磁力下载工具
sudo pacman -S qbittorrent

#Thunderbird 				#来自 Mozilla 的功能丰富的电子邮件客户端，用 GTK 编写。
sudo pacman -S thunderbird 

#Todesk					#Todesk是一款安全快速免费的远程控制软件
yay -S todesk-bin			#aur的包不能正常使用建议使用官网的包				官网包：https://newdl.todesk.com/linux/todesk_4.1.0_x86_64.pkg.tar.zst

#Spectacle				#kde默认截图软件，及其好用！
sudo pacman -S spectacle

#游戏
#steam					#G胖快乐微笑🙂
sudo pacman -S steam

#任务管理器
#htop

#gotop

#gtop

#btop

#bpytop
