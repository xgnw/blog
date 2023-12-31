---
# 当前页面内容标题
title: 关于微信备份到pc端(ios)
date: 2023-08-27T14:41:50+08:00
# 分类
category:
- 微信
- 技术杂谈
# 标签
tag:
- 微信
- 技术杂谈
# 原文作者
# Post's origin author name
author: 阿刚同学
# 原文链接
# Post's origin link URL
link: https://www.isharepc.com/31303.html
url: post/WeChat-backup.html
toc: true
---

微信作为高频率日常应用在国内是许多用户社交网络中最重要的一环，几乎大家全部的人际关系、工作人脉均在其中，它的重要性与安全性不言而喻，尤其是日常的聊天记录可说是重中之重。

微信官方的做法，是将其全部保存在用户本机设备中，云端仅同步一部分，一方面随着日常使用微信的聊天数据占据大量本地存储空间，另一方面如果因为手机遗失、被盗或者各种意外状况导致设备无法正常使用，则意味着数据全部丢失。

![](https://img.isharepc.com/wp-content/uploads/wxbackuppinc-b.png)

因此日常使用中，微信聊天记录的备份尤为重要。而微信本身自带了聊天记录备份与恢复功能，可通过PC客户端将全部聊天记录备份至本地，方便你一键迁移和恢复。

**具体而言：**

- 1，登录PC端微信，备份与恢复
- 2，备份聊天记录至手机（可选全部或部分好友记录）

![](https://img.isharepc.com/wp-content/uploads/wxbackuppinc-1.png)

客观的说，综合安全与实用性两方面，微信官方的备份与恢复功能相当好用，既能备份聊天记录又可以恢复或迁移至其他设备，如果非要说不足之处，大概就是数据全部加密，所有记录必须在微信 APP 并登录帐号才能查看，其实有时大家备份数据，可能只是方便日后随时随地查阅，怎么方便怎么来。于是乎，下面的这两款工具就派上用场了。

## WX Backup/WechatExporter，微信聊天记录备份导出与查看工具

WX Backup和WechatExporter是免费的微信聊天记录备份导出工具，它们通过读取Itune备份的数据，解析出微信账号中全部的聊天记录，包括文字、图片、语音和视频记录，并且一键导出成html网页，方便你在电脑端随时查阅。

![](https://img.isharepc.com/wp-content/uploads/wxbackuppinc-7.png)

（图片来自官网）

他们目前支持Windows+MAC客户端，使用也相当简单~阿刚来通过WX Backup简单的说下使用过程：

### **1，使用iTunes备份你的手机**

首先如前面所述，微信自身导出的聊天记录文件是全部加密的，目前第三方工具只能通过苹果iTune备份的手机数据中提取微信数据，因此要使用WX Backup导出记录，首先你的微信聊天数据必须存储在iphone设备中，如果你是安卓用户，则必须找一台苹果设备，通过微信自带的聊天记录迁移功能，在两台机器接入同一WiFi下进行记录迁移。

![](https://img.isharepc.com/wp-content/uploads/wxbackuppinc-2.png)

迁移完成后，电脑端安装iTunes软件备份iPhone设备至本地电脑，注意备份时切记勿加密备份，否则导致程序无法读取微信数据。

![](https://img.isharepc.com/wp-content/uploads/wxbackuppinc-3.png)

### **2，使用WX Backup导出微信备份**

苹果iTunes备份数据默认保存在C盘中，默认的具体路径

C:\Users\你电脑用户名\AppData\Roaming\Apple Computer\MobileSync\Backup

运行WX Backup并手动指定上述的备份路径，软件将自动读取微信数据，你可根据选择的账号和联系人导出聊天记录，而且最关键的是它还支持增量导出，即有新的内容更新到iPhone备份文件后，可以增加更新的内容到导出记录中，这一点非常棒。

![](https://img.isharepc.com/wp-content/uploads/wxbackuppinc-4.png)

### **3，使用浏览器查看导出的微信数据**

WX Backup导出的数据均保存至一个html文档中，实际上它输出的是一个前端网页，样式与微信网页版几乎一致，在内容上完美还原了微信的聊天记录，包括文字、语音、图片视频等，支持直接播放。如果你的记录较多，他还支持按照年月进行筛选查看，另外导出的目录下可以查看图片、音频和视频的文件。

![](https://img.isharepc.com/wp-content/uploads/wxbackuppinc-5.gif)

（动图中展示的demo来源于官网）

另外一款WechatExporter与WX Backup在功能几乎相同，均是通过提取iTunes手机备份数据中的微信聊天记录，导出的html前端同样是类似微信网页版，但在一些细节上，比如WechatExporter不能按照月份来查看消息记录，只能不断的上拉加载消息，不过它运行时无需手动指定iTunes备份的数据，可自动识别，而且阿刚测试后发现WechatExporter读取的聊天记录中，昵称显示准确完美。

![](https://img.isharepc.com/wp-content/uploads/wxbackuppinc-6.png)

另外，阿刚个人在测试发现，WX Backup导出后不能正常播放音频，不知道是不是我ios版本太高的原因。而WechatExporter则能完美的读取。

### **写在最后：**

WX Backup与WechatExporter只是微信聊天记录备份和导出工具，自身不具备恢复功能，如需聊天恢复你仍然需要通过PC端的微信进行操作，这两款工具实际上是微信备份的辅助工具，你要问我这俩工具最大的用处在哪：

第一，通过它备份的数据你可以永久保存在电脑上，甚至上传至网盘中进行备份，从此重要的聊天记录可以永久保存，最关键的是手机上保存的聊天记录可以毫无顾忌的直接删了，节省空间。

第二，保存的格式是Html，不限制于微信，只要有浏览器就能打开浏览。

就这么方便~

## 相关文件下载

[WX Backup官网](http://wxbackup.imxfd.com/)

[WechatExporter项目主页](https://github.com/BlueMatthew/WechatExporter)