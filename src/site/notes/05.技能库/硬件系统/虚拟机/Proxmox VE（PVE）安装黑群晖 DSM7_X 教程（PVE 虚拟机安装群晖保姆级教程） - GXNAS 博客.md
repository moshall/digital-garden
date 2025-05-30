---
{"dg-publish":true,"permalink":"/05.技能库/硬件系统/虚拟机/Proxmox VE（PVE）安装黑群晖 DSM7_X 教程（PVE 虚拟机安装群晖保姆级教程） - GXNAS 博客/","title":"Proxmox VE（PVE）安装黑群晖 DSM7.X 教程（PVE 虚拟机安装群晖保姆级教程） - GXNAS 博客","tags":["虚拟机"]}
---

**【前言】**

 本教程基于 Proxmox VE（PVE）7.0 虚拟机环境下安装黑群晖 DS918-7.01，因此对硬件的要求如下：

1、CPU 要求（如果 CPU 不满足要求，建议安装 DS3615-7.01，安装 DS3615-7.01 的步骤和安装 DS918-7.01 的步骤大致一样，只是使用不同引导和不同安装包的区别。）

（1）至少要用第四代 Intel 酷睿处理器、或者同等级别的奔腾处理器、或者同等级别的赛扬处理器，比如：Intel i5-4430、J3455、N3160；

（2）至强的处理器，要求是 v3 或者以上级别，比如：Intel Xeon E3-1230 v3；

（3）如果是 AMD，要求是锐龙 3 或者以上级别，比如：Ryzen 3 - 2200G；

2、网卡要求

（1）如果使用虚拟网卡，优先使用 “virtio” 这种半虚拟化的网卡类型；

（2）如果是用直通网卡的，建议使用 Intel 品牌的网卡，使用其他品牌的网卡有可能引导不包含该网卡驱动造成无法引导；

（3）由于网卡品牌及型号众多，博主编译的引导无法适合所有人，如果用不了的话建议自行去编译引导。

**【安装步骤】**

1、在电脑上新建一个文件夹（我在 E 盘建立 dsm7 这个文件夹），需要注意：不可以用中文或者特殊符号。到【[我的网盘](https://d.gxnas.com/)】下载以下文件，全部下载完成后，然后点到下图红框处，把当前这个路径复制一下；

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160225262.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631754-1.jpg)

2、把引导文件~【redpill-DS918+_7.0.1-42214（引导文件）.img】~（由于 7.01 的引导已过时，博主网盘里面有最新的 7.21/7.22 的引导，建议使用该版本引导）改个名，去掉中文字（不可以有中文），同时把文件名改短一些，方便操作，我这改成 DS918_7.0.1.img；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631757-2.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160226780.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631757-2.jpg)

3、在电脑浏览器打开 PVE 的 IP 地址，用 root 登录，在左边栏如下图的位置右键，创建虚拟机；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631758-3.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160227268.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631758-3.jpg)

4、填写虚拟机名称，VM ID 这个数字自动生成不用更改，但是需要记住这个数字，后面需要用到；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631759-4.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160227715.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631759-4.jpg)

5、不使用任何介质，下一步；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631760-5.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160228157.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631760-5.jpg)

6、下一步；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631761-6.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160228546.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631761-6.jpg)

7、在 “总结 / 设备” 点一下，选“SATA”；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631762-7.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160228926.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631762-7.jpg)

8、磁盘大小先写一个 “1”，临时的设置，等下会删除；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631763-8.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160229314.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631763-8.jpg)

9、单 CPU 的 “插槽” 写“1”（双路写 2）、核心则根据自己使用的 CPU 真实核心数量填写（给群晖分配的 CPU 核心数量，不可以超过实际 CPU 核心数量），类别选“host”，下一步；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631764-9.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160229705.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631764-9.jpg)

10、内存根据实际情况分配，我分配的是 4096MB，下一步；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631765-10.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160230089.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631765-10.jpg)

11、模型选：~E1000e~（2022 年 11 月 25 日更新：早期的引导不支持 virtio 所以才使用 E1000e，目前博主编译的引导已全面支持 virtio，建议优先使用 virtio 这个网卡类型。），下一步；

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160230535.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631774-11.jpg)

12、完成；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631774-12.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160230987.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631774-12.jpg)

13、找到刚刚建立的虚拟机，选中前面临时建立那个 1G 的磁盘（sata0），选菜单上的 “分离”；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631776-13.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160231521.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631776-13.jpg)

14、是；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631777-14.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160231891.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631777-14.jpg)

15、选中分离出来的这个 “未使用的磁盘 0”，点菜单上的 “删除”；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631778-15.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160232412.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631778-15.jpg)

16、是；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631778-16.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160232750.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631778-16.jpg)

17、选中 BIOS，编辑；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631779-17.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160233253.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631779-17.jpg)

18、改成 “OVMF（UEFI）”；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631779-18.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160233585.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631779-18.jpg)

19、OK；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631780-19.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160233981.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631780-19.jpg)

20、选中 “机器”，编辑；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631781-20.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160234435.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631781-20.jpg)

21、改成 q35，OK；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632640529-85.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160234784.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632640529-85.jpg)

22、打开 DiskGenius 软件，点菜单上的 “硬盘”—“打开虚拟硬盘文件”；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631784-21.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160235305.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631784-21.jpg)

23、进入第 1 步建立的文件夹，找到 DS918_7.0.1.img 文件，打开；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631785-22.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160235840.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631785-22.jpg)

24、在左边栏中点 +，~点 grub 文件夹，在右边找到 grub.cfg 文件~（7.21/7.22 的引导，直接找根目录下 user-config.yml，不在 grub 文件夹），在此文件上点鼠标右键，弹出的菜单中选择 “复制到指定的文件夹”；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631787-23.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160236590.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631787-23.jpg)

25、在文件夹处点一下，把在第 1 步建立的路径粘贴进去，确定；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631788-24.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160237060.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631788-24.jpg)

26、完成；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631788-25.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160239168.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631788-25.jpg)

27、用 Notepad2 打开 ~grub.cfg 文件~（7.21/7.22 的引导，打开 user-config.yml），在菜单上的 “查看”，找到自动换行，点一下；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631789-26.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160240132.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631789-26.jpg)

28、（如果是用博主网盘里面 7.21/7.22 的引导，参考【[本教程](https://wp.gxnas.com/13657.html)】修改，此步骤跳过）向下翻页到第 58 行和第 68 行，先找到下图圈出蓝色字，根据实际情况修改（58 行和 68 行都要改），改好了就保存文件，关闭 Notepad2；

（1）~netif_num=1：网口数量，默认为 1，如果你要给虚拟机添加两个网口的，请改成 netif_num=2~（7.21/7.22 的引导，不需要设置）；  
（2）~mac1=001132123456：默认只填写了一个网口的 mac 地址，如果给虚拟机添加两个网口的，需要在 mac1 的后面添加了一个 mac2=001132123466（两个 mac 值不可以一样）；如果你有真实的洗白码，可以替换成洗白码 mac 的值~；（7.21/7.22 的引导，如果不需要洗白此步骤跳过；洗白则修改 mac1 的值为洗白码的 mac1，如果有多个 mac 的则删除，只保留 mac1）  
（3）sn=2021PDN123456 为默认的序列号，如果不需要洗白此步骤跳过（7.21/7.22 的引导，洗白则修改 sn 的值为洗白码的 sn）；  
（4）虚拟机安装，不需要改 VID 和 PID。

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160240966.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631790-27.jpg)

29、（如果是用博主网盘里面 7.21/7.22 的引导，参考【[本教程](https://wp.gxnas.com/13657.html)】修改，此步骤跳过）切换到 DiskGenius 软件，在右边空白处点右键，在弹出的菜单选择 “复制文件到当前分区”；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631791-28.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160242694.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631791-28.jpg)

30、（如果是用博主网盘里面 7.21/7.22 的引导，参考【[本教程](https://wp.gxnas.com/13657.html)】修改，此步骤跳过）找到刚才修改好的 grub.cfg，打开；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631792-29.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160243321.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631792-29.jpg)

31、（如果是用博主网盘里面 7.21/7.22 的引导，参考【[本教程](https://wp.gxnas.com/13657.html)】修改，此步骤跳过）替换；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631792-30.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160243746.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631792-30.jpg)

32、（如果是用博主网盘里面 7.21/7.22 的引导，参考【[本教程](https://wp.gxnas.com/13657.html)】修改，此步骤跳过）完成；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631793-31.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160244186.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631793-31.jpg)

33、（如果是用博主网盘里面 7.21/7.22 的引导，参考【[本教程](https://wp.gxnas.com/13657.html)】修改，此步骤跳过）退出 DiskGenius 软件；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631793-32.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160244660.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631793-32.jpg)

34、把下载在电脑上的 “MobaXterm v20.0 中文汉化专业版” 压缩包解压出来，运行 MobaXterm1_CHS1.exe；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631794-33.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160245077.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631794-33.jpg)

35、用 root 用户登录到 PVE 的 SSH 下，正常的话右边栏会显示如下图以 root@开头的界面，左边栏下图位置应该会显示 / root/；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631796-34.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160245598.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631796-34.jpg)

36、把电脑上的 DS918_7.0.1.img 点鼠标左键不松开，拖到 MobaXterm 的左边如下图的空白位置，再松开鼠标左键；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631797-35.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160246299.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631797-35.jpg)

37、此时会看到文件在上传的状态，需要等一下；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631801-36.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160246933.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631801-36.jpg)

38、上传完成，显示有文件出来了；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631810-37.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160247457.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631810-37.jpg)

39、在 MobaXterm 的右边黑色区域，输入以下命令转换群晖引导盘，使它变成 PVE 虚拟机的格式（命令别照搬，100 为第 4 步骤显示的 VM ID）：

```
qm importdisk 100 DS918_7.0.1.img local-lvm

```

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160248123.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631812-39.jpg)

40、确认无误后，回车；

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160248669.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631811-38.jpg)

41、转换完成后，PVE 的虚拟机会多出一个 “未使用的磁盘 0”；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631814-40.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160250712.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631814-40.jpg)

42、双击这个 “未使用的磁盘 0”，在“总线 / 设备” 点下拉列表，选 SATA；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631814-41.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160251253.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631814-41.jpg)

43、确认一下这个引导盘必须是：SATA  0，然后点 “添加”；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631815-42.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160251609.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631815-42.jpg)

44、之前的 “未使用的磁盘 0”，此时会变成 “磁盘（sata0）”，大小是 128M；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631816-43.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160252023.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631816-43.jpg)

45、给群晖虚拟机添加硬盘，本教程使用的是 PVE 虚拟的硬盘，在菜单上选 “添加”，“硬盘”；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631817-44.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160252541.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631817-44.jpg)

46、“总线 / 设备” 会自动显示为 SATA1，“存储” 选 PVE 的存储盘，磁盘大小根据实际需要设置（DSM7.X 存储硬盘最低要求为 19GB，如果小于 19GB 安装必定失败，本教程以 50GB 为例）；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631817-45.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160252930.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631817-45.jpg)

47、如果想模拟为 NVME 硬盘，可以在 “高级” 这里 “SSD 仿真” 打勾，添加；（如果 PVE 存储盘为机械硬盘或者群晖虚拟机添加了一个 SATA 格式虚拟硬盘的，此步骤跳过不做设置）

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160253352.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631819-46.jpg)

48、选中群晖虚拟机，选项，引导顺序，编辑；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631829-47.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160253948.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631829-47.jpg)

49、只勾选 “sata0”，别的打勾都去掉，点 “OK”；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631829-48.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160254486.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631829-48.jpg)

50、选中群晖虚拟机，在右上方的 “启动” 点一下；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631830-49.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160255182.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631830-49.jpg)

51、点到群晖虚拟机的控制台，会看到群晖引导盘启动的过程，此时会有一个菜单，向上下键移动到下面的 “RedPill DS918+ v7.0.1-42214 RC（SATA，Verbose）”，回车；（如果是用博主网盘里面 7.21/7.22 的引导，系统会自动引导，无需手动操作）[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631831-50.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160255862.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631831-50.jpg)

52、然后屏幕会显示如下图，黑群晖 7.X 的引导启动后就显示这样，在 UEFI 方式启动方式下，会有一个光标停在上面不动，不要以为是系统卡住了；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631831-51.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160256386.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631831-51.jpg)

53、在电脑浏览器新开一个标签，输入（[http://find.synology.com/](http://find.synology.com/)）这个地址回车，开始搜索局域网内的群晖设备；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631832-52.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160257441.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631832-52.jpg)

54、如果局域网内有多台群晖设备的，右边会有一个三角形显示，可以翻页找到我们需要安装的设备（状态会显示：未安装），点 “连接”；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631833-53.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160258157.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631833-53.jpg)

55、左下角 “我已阅读并同意 EULA 的条款” 打勾，下一步；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631833-54.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160258965.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631833-54.jpg)

56、继续；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631834-55.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160301006.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631834-55.jpg)

57、正在加载；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631835-56.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160302226.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631835-56.jpg)

58、安装；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631836-57.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160302642.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631836-57.jpg)

59、浏览；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631837-58.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160304249.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631837-58.jpg)

60、找到之前下载的  DS918+_7.01-42214（系统安装包）.pat  这个安装包文件，打开；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631838-59.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160306858.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631838-59.jpg)

61、确认一下安装包的版本号（用什么版本的引导，就要选对应版本的安装包，不可以搞错），无误后点下一步；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631847-60.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160307384.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631847-60.jpg)

62、安装过程中，群晖系统会自动把存储硬盘重新分区并格式化为群晖格式的硬盘，在 “我了解这些硬盘上的所有数据都将被删除” 打勾，继续；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631848-61.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160307730.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631848-61.jpg)

63、开始安装；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631849-62.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160308084.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631849-62.jpg)

64、正在格式化系统分区；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631849-63.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160308445.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631849-63.jpg)

65、正在上传 DSM 安装包；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631850-64.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160308874.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631850-64.jpg)

66、不卡 40%；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631851-65.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160309267.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631851-65.jpg)

67、正在安装系统，不卡 55%；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631851-66.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160309707.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631851-66.jpg)

68、耐心等待安装，安装完成系统会自动重启，此时会显示一个 10 分钟的倒计时，重启等待的时间由硬件性能决定（正常等待 1-10 分钟）；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631852-67.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160310121.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631852-67.jpg)

69、重启完成，会显示 “正在启动内置套件”；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631852-68.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160310506.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631852-68.jpg)

70、点：开始； [](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631853-69.jpg) 

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160310899.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631853-69.jpg)

71、给设备起个名字（不可以用中文），设置一个用户名（不可以用 admin），设置密码（密码要求：大写字母 + 小写字母 + 数字的组合，长度至少 8 位），下一步。[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631855-70.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160311370.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631855-70.jpg)

72、选 “当有可用的 DSM 或者套件更新时通知我，我会手动安装”，下一步。[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631855-71.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160311868.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631855-71.jpg)

73、跳过； [](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631856-72.jpg) 

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160314259.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631856-72.jpg)

74、不打勾，直接点提交；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631857-73.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160314931.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631857-73.jpg)

75、进入系统桌面，提示创建存储池和存储空间，点：立即创建；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631866-74.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160315543.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631866-74.jpg)

76、开始； [](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631866-75.jpg) 

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160316090.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631866-75.jpg)

77、RAID 类型根据实际选择（如果有多个硬盘需要组阵列的选 SHR，如果需要把多个硬盘组成一个大容量的选 JBOD），本教程使用单硬盘，选 Basic，下一步；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631867-76.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160316645.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631867-76.jpg)

78、选中需要建立存储的硬盘，下一步；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631867-77.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160317396.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631867-77.jpg)

79、提示我的硬盘不在 Synology 产品兼容列表中，不用理会，这个不影响使用，继续。[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631868-78.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160318038.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631868-78.jpg)

80、跳过硬盘检查（如果你组的是 RAID，强烈建议勾选 “执行硬盘检查”，以免硬盘出问题引起 RAID 损毁），下一步；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631868-79.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160318606.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631868-79.jpg)

81、在 “修改分配的大小” 这里，点“最大化”，下一步；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631868-80.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160319177.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631868-80.jpg)

82、“选择文件系统” 这里有两个选择，根据实际情况选择，如果想要使用群晖系统所有功能不受限制的，选 Btrfs，下一步；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631869-81.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160319756.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631869-81.jpg)

83、应用；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631869-82.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160320272.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631869-82.jpg)

84、确定；[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631870-83.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160320703.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631870-83.jpg)

85、存储空间建立完成[](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631870-84.jpg)

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160323171.jpeg?cd-oss-obs)](https://wp.gxnas.com/wp-content/uploads/2021/09/1632631870-84.jpg)

86、系统安装至此结束。