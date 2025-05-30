---
{"dg-publish":true,"permalink":"/05.技能库/硬件系统/虚拟机/Proxmox VE 直通硬盘（全盘映射方式） - 星哥的博客/","title":"Proxmox VE 直通硬盘（全盘映射方式） - 星哥的博客","tags":["虚拟机"]}
---

使用 PVE 有时为了方便，需要将硬盘直通，一般有两种方式，一是硬件直通，一是全盘映射，这里介绍第二种（由于硬件直通需要把直通分组才能把按照 PVE 的系统盘隔离出来），方法如下：

**一、打开 PVE 管理网页 Shell**

输入

ls /dev/disk/by-id

查看存储设备的 id

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160416589.png?cd-oss-obs)](https://wangxingcs.com/wp-content/uploads/2020/02/1-2.png)

图上划红线即为硬盘 ID 号，复制下来

**二、硬盘映射**

**注意：这里需要将 100 换成虚拟机的真实 ID，sata1 这里也可以换成未占用的 id 数（PVE 支持 satat0-5）**

qm set 100 -sata1 /dev/disk/by-id/ata-WDC_XXXX_XXXX_XXXX

如果返回以下信息, 说明已成功映射

update VM 100: -sata1 /dev/disk/by-id/ata-WDC_XXXX_XXXX_XXXX

**三、确定是否成功**

进入 PVE 对应虚拟机的硬件页面，查看是否硬盘是否已经在虚拟机里，如图所示说明已成功，这时打开虚拟机就能找到对应硬盘。

[![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160417899.png?cd-oss-obs)](https://wangxingcs.com/wp-content/uploads/2020/02/2-2.png)