---
{"dg-publish":true,"permalink":"/05.技能库/硬件系统/虚拟机/PVE(Proxmox VE) 下网卡是如何设置直通的 - 下一朵云/","title":"PVE(Proxmox VE) 下网卡是如何设置直通的 - 下一朵云","tags":["虚拟机"]}
---

## 默认未直通，在 PVE 添加 PCI 设备会有如下提示：

![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160429783.png?cd-oss-obs)

图 1 报错提示内容

## 直通网卡需要修改 gurb、增加模块、虚拟机添加网卡

**#修改 gurb**

#Intel CPU

shell 里面输入命令：

```
nano /etc/default/grub

```

在里面找到：

```
GRUB_CMDLINE_LINUX_DEFAULT="quiet"

```

然后修改为

```
GRUB_CMDLINE_LINUX_DEFAULT="quiet intel_iommu=on"

```

在更新一下

```
update-grub

```

重启一下

```
reboot

```

  
# AMD CPU

shell 里面输入命令：

```
nano /etc/default/grub

```

在里面找到：

```
GRUB_CMDLINE_LINUX_DEFAULT="quiet"

```

然后修改为

```
GRUB_CMDLINE_LINUX_DEFAULT="quiet amd_iommu=on""

```

重启一下

```
reboot

```

**#增加模块**

修改文件 /etc/modules 加入如下的行（默认为空）：

```
vfio
 vfio_iommu_type1
 vfio_pci
 vfio_virqfd

```

**#虚拟机添加网卡（可在 web 页面添加）**

查找网卡 ID

```
lspci |grep net

```

![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160430391.png?cd-oss-obs)

图 2 查找网卡 ID

需要记住前面 ID 值

命令行登录系统，打开文件

```
/etc/pve/nodes/你的集群名称/qemu-server/虚拟机id.conf 

```

其内容由上述操做所生成。一下项目必须手工添加。

```
machine:q35
 hostpci0:02:00.0,pcie=1  # 网卡 1
 hostpci1:02:00.1,pcie=1  # 网卡 2

```

![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160430975.png?cd-oss-obs)

图 3 添加成功

成功后会在上述出现 ，注意 : 如果不小心添加了物理主机所使用的网卡，会导致，服务器掉线，这时候使用 u 盘进入救救援模式，删除原来的配置，重启即可。

＃补充说明：Web 管理页面添加网卡操作如下

![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160431583.png?cd-oss-obs)

图 4 添加 PCI 设备

![](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250402160432099.png?cd-oss-obs)

图 5 选择要添加的网卡