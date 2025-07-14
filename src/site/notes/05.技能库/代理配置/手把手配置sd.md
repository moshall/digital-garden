---
{"dg-publish":true,"permalink":"/05.技能库/代理配置/手把手配置sd/","title":"手把手配置shado"}
---



## 原理说明：
规则：依据Shadowrocket分流规则，实现不同类型网站走不同的线路
应用场景：AI服务走自建节点，Gemimi走其他节点

## 原始规则项目地址：
https://johnshall.github.io/Shadowrocket-ADBlock-Rules-Forever/#%E6%87%92%E4%BA%BA%E9%85%8D%E7%BD%AE-%E5%90%AB%E7%AD%96%E7%95%A5%E7%BB%84


## 具体规则地址：

```
https://johnshall.github.io/Shadowrocket-ADBlock-Rules-Forever/lazy_group.conf
```


## 手把手配置步骤：


#### 1.将PicoPico的自建节点订阅，重命名

![IMG_7776.jpg](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527172932563.jpg?cd-oss-obs)
![IMG_7777.jpg](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527172942481.jpg?cd-oss-obs)



#### 2.下载策略组

策略组地址：
```
https://johnshall.github.io/Shadowrocket-ADBlock-Rules-Forever/lazy_group.conf
```

进入配置，点击 + 号，复制策略组下载


![IMG_7797.jpg](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527173718190.jpg?cd-oss-obs)

![IMG_7778.jpg](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527173646452.jpg?cd-oss-obs)



#### 3.配置策略组 - 代理分组

将代理分组AI配置为PicoPico的指定节点，配置后，所有AI类服务都会走这个节点
如果出现故障，也是同样的切换配置方法
在代理分组 -> 正则匹配包含Pico的分组 -> 选择一个Pico节点 

如果有一天，比如我们想让youtube走香港节点，也是类似的设置

![IMG_7779.jpg](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527173835985.jpg?cd-oss-obs)
![IMG_7780.jpg](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527173848909.jpg?cd-oss-obs)
![IMG_7781.jpg](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527173856898.jpg?cd-oss-obs)
![IMG_7784.jpg](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527173914359.jpg?cd-oss-obs)
![IMG_7785.jpg](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527173925492.jpg?cd-oss-obs)



#### 4.配置策略组 - 代理规则


代理规则的含义就是哪些IP或域名是Netflix，哪些IP和域名是chatgpt，哪些是google，哪些是youtuebe
可以让不同的规则，走不同的策略组
比如让netflix走新加坡节点，中文资源是最多的
比如让youtube走香港节点，速度快距离近
比如让OpenAI走AI节点，都是家宽，不会降职


一步步跟着做：（这个示例是，google屏蔽了pico自建IP，我们让gemini不走ai规则）
a.配置Tab，点击规则文件，点击规则
b.找到gemini规则
c.点击策略
d.选择一个其他策略
比如可以选择新加坡节点，选择这个，就代表会访问gemeni的时候会从新加坡分组中走其中一个
也可以向下拉，选择你想走的特定节点



![IMG_7786.jpg](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527174244565.jpg?cd-oss-obs)
![IMG_7798.jpg](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527174604281.jpg?cd-oss-obs)
![IMG_7788.jpg](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527174633735.jpg?cd-oss-obs)
![IMG_7789.jpg](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527174644197.jpg?cd-oss-obs)



#### 5.使用配置

选择我们之前的配置文件，点击使用配置
![IMG_7792.jpg](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527175346502.jpg?cd-oss-obs)


#### 6.云同步 - 手机电脑不用重复设置

![IMG_7794.jpg](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527175425911.jpg?cd-oss-obs)
![IMG_7795.jpg](https://chengdu-obsidian-milkkey.oss-cn-chengdu.aliyuncs.com/img/20250527175434813.jpg?cd-oss-obs)




## 小白科普：


分流规则：
proxy：就是当前选中的节点，可以理解为默认代理节点
direct：直连的意思，就是不过代理，一般国内服务，苹果服务都选这个
有命名的规则：需要结合规则和代理分组一起看走哪个策略，如果没特殊配置，就是Proxy

