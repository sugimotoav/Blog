---
title: "黑苹果安装macOS_BigSur"
date: 2020-06-26T22:42:57+08:00
draft: true
---

下载macOS Big Sur Develop Beta 1

macOS Customer Beta Access Utility

![723t2m](https://cdn.jsdelivr.net/gh/zhaoleihello/ImageStore@master/Images/723t2m.png)

[链接:](appleseed.apple.com)

hw.model: iMac19,2

"board-id" = <"Mac-63001698E7A34814">


```
在VMware Fusion中全新安装macOS 11 Beta。
目前，版本11.5.5尚不知道如何立即安装macOS 11 Beta，因此我们执行以下操作：
1.在VMware中：
-新建-创建自定义虚拟机-Apple OS X-10.15。选择创建新的虚拟磁盘（然后将其删除）-默认情况下。在单击“完成”之前，请单击“自定义设置”。他将要求您保存设置-将其保存，例如在/Users/user/vmware/macOS11.vmwarevm中
-将打开“设置”屏幕。我们删除了VMware虚拟磁盘，我们不会将其放置在那里。谁想要玩耍-不要删除，放在那里。
2.在macOS 11上安装“闪存驱动器”：
-创建用于读取/写入的空磁盘映像：
磁盘实用程序-文件-新映像-空映像。我们将大小设置为32G，为简单起见，名称为123，例如将其保存在installmedia.dmg中。挂载生成的图像。
- 我们执行/应用程序/安装macOS Beta.app/Contents/Resources/createinstallmedia --volume / Volumes / 123
我们等待直到完成。无法卸载映像，我们将需要它，但出于可靠性考虑，最好将其卸载以便刷新缓存。
现在我们有了启动映像。
3.谁想玩macOS 11-您可以跳过此步骤，将其放在虚拟磁盘上。
-需要干净的硬盘/ SSD。只需使用磁盘实用程序将其擦除，然后将其格式化为APFS，分区方案（当然是GUID）即可。
-将其连接到VMware：
-卸载新格式化的磁盘：sudo diskutil unmountDisk diskX-
下一步/应用程序/ VMware \ Fusion.app/Contents/Library/vmware-rawdiskCreator create / dev / diskX fullDevice /Users/user/vmware/macOS11.vmwarevm/macOS11hdd sata
路径在您的磁盘上，用刚格式化的磁盘替换diskX。
4.将结果磁盘添加到我们在第1点创建
的虚拟机-在虚拟机设置中：添加设备...-现有硬盘。这很奇怪：您需要选择macOS11hdd.vmdk，但是由于某种原因，VMWare不能给它选择，但是按文件上的右键可以帮助选择文件，然后可以添加它。在选项中，选择“与...共享磁盘”。点击“应用”。
5.将“闪存驱动器”添加到虚拟机。
-从项目2挂载“闪存驱动器”
-运行
/应用程序/ VMware \ Fusion.app/Contents/Library/vmware-rawdiskCreator创建/ dev / diskY fullDevice /Users/user/vmware/macOS11.vmwarevm/installmedia-lnk lsilogicT
。 E.，通过临时磁盘installmedia-lnk.vmdk与dmg映像创建连接，diskY是您安装的映像。
-接下来，将dbg映像的内容复制到VMware映像中：
/ Applications / VMware \ Fusion.app/Contents/Library/vmware-vdiskmanager -r /Users/user/vmware/macOS11.vmwarevm/installmedia-lnk.vmdk -t 0 / Users /user/vmware/macOS11.vmwarevm/installmediadrive.vmdk-卸载
“闪存驱动器”映像，不再需要它。
-在虚拟机设置中，添加设备...-现有硬盘。这次您需要选择获得的installmediadrive.vmdk，可以正常选择它。:)在选项中，选择“与...共享磁盘”。点击“应用”。
在安装结束时，可以从设置中删除该磁盘。

因此，虚拟机应具有两个磁盘：
-带有安装闪存驱动器的磁盘。
-将目标物理硬盘驱动器绑定到VMware。
如果一切都正确完成，那么我们将启动虚拟机，macOS 11安装将自动开始。
在此阶段不需要OpenCore。
图片在这里

http://magnet/?xt=urn:btih:9b7ea32466ddad6385d22ff223d4d7dfd1d0e857&dn=macOS11.img.dd.gz&tr=http%3A%2F%2Fbt.t-ru.org%3A80&tr=http%3A%2F%2Fretracker.local%3A80
```

[vit9696的帖子](https://www.applelife.ru/threads/ustanovka-macos-big-sur-11-0-10-16-beta-na-intel-pc.2944999/page-45)

```
1.下载或创建预安装的macOS 11 DP1映像。

2.展开图像：

对于dmg（标准）：
hdid -nomount "/Volumes/acidanthera/macOS_11.dmg"

- diskutil list # смотрим нужный диск, не synthesized

- sudo dd if=/dev/diskX of=/dev/diskY bs=32m ＃从diskX还原到diskY

对于dd：

-sudo
- sudo dd if=/acidanthera/macOS_11.raw of=/dev/diskY bs=32m

对于gz中的dd:

- sudo sh -c 'gunzip -c macOS11.img.dd.gz | dd of=/dev/diskY'


命令中的X和Y必须替换为磁盘号。对于dmg扩展，不应合成磁盘，即物理标记。必须卸载目标磁盘。

4.将OpenCore和kexts更新为主版本。

- 现在仅部分更新了OpenCore，Lilu，AppleALC，VirtualSMC和WhateverGreen。

- Lilu中的Userspace修补程序尚无法使用。

- 到目前为止，仅在兼容模式下在OpenCore中注入kexts（不支持安装程序）。

5.通过将NVRAM变量添加到config.plist OpenCore（ERR059-4），将keksts的注入切换为兼容模式：
码：

- 7C436110-AB2A-4BBB-A880-FE41995C9F82:booter-fileset-kernel <00>

- 7C436110-AB2A-4BBB-A880-FE41995C9F82:booter-fileset-basesystem <00>

以dmg格式预安装的映像:

-来自@Vandroiy（[链接](https://drive.google.com/file/d/1zsZyKav6djr8hG80KxNnWAoXReGk6FJh/view?usp=sharing)，您需要至少120 GB的磁盘，密码1234）

转换为dd的映像(更小，更简单):

-来自@losinka：（[链接](https://books.foreigner.cc/)，您需要至少120 GB的磁盘，密码1234 ）

-来自@joedm：（[磁力链](magnet:?xt=urn:btih:9b7ea32466ddad6385d22ff223d4d7dfd1d0e857&dn=macOS11.img.dd.gz&tr=http%3A%2F%2Fretracker.local%3A80&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337)，您需要至少500 GB的磁盘，密码12345678）

使用QEMU完成dmg的转换:

qemu-img convert -f dmg -O raw /acidanthera/macOS_11.dmg /acidanthera/macOS_11.dd

介绍了一些手动创建预定义图像的方法在这里。

当直接通过dd卸下驱动器时，建议您首先进行零位释放以减小大小并压缩结果。对于macOS 11上的零零:

cat /dev/zero > tmp ; rm tmp

要压缩，例如:

7z a -t7z -m0=lzma -mx=9 -mfb=64 -md=32m -ms=on /acidanthera/macOS_11.7z /acidanthera/macOS_11.dd

```

[OpenCore](https://github.com/acidanthera/OpenCorePkg.git)
[Lilu](https://github.com/acidanthera/Lilu.git)
[AppleALC](https://github.com/acidanthera/AppleALC.git)
[WhateverGreen](https://github.com/acidanthera/WhateverGreen.git)


## 格式化整个磁盘

```
diskutil partitionDisk /dev/disk2 1 GPT APFS NewName R
```

```
7C436110-AB2A-4BBB-A880-FE41995C9F82
booter-fileset-kernel
booter-fileset-basesystem
```
