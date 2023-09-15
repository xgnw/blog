---
title: "Waline国内用户设置方法"
description: "Waline国内用户设置方法"

date: 2023-08-02T11:52:03+08:00

categories:
 - 博客
tags:
 - Hugo
 - 开始

url: post/Waline.html
toc: true
---

## 基本说明

该文章为国际版设置教程。

## 准备Waline

https://waline.js.org/guide/get-started/ 

欢迎使用 Waline，只需几个步骤，你就可以在你的网站中启用 Waline 提供评论与浏览量服务。

### LeanCloud 设置 (数据库)

1）、 登录  或 注册  LeanCloud 国际版 并进入 控制台 

2）、点击左上角 创建应用  并起一个你喜欢的名字 (请选择免费的开发版):

3）、进入应用，选择左下角的 设置 > 应用 Key。你可以看到你的 APP ID,APP Key 和 Master Key。请记录它们，以便后续使用。

### 国内版需要完成备案接入

如果你正在使用 Leancloud 国内版 (leancloud.cn)，我们推荐你切换到国际版 (leancloud.app)。否则，你需要为应用额外绑定已备案的域名，同时购买独立 IP 并完成备案接入:

登录国内版并进入需要使用的应用 选择 设置 > 域名绑定 > API 访问域名 > 绑定新域名 > 输入域名 > 确定。 按照页面上的提示按要求在 DNS 上完成 CNAME 解析。 购买独立 IP 并提交工单完成备案接入。(独立 IP 目前价格为 ￥ 50/个/月)

### Vercel 部署 (服务端)

登录 Vercel  ，跳转至 Vercel 进行 Server 端部署。

1）、如果你未登录的话，Vercel 会让你注册或登录，请使用 GitHub 账户进行快捷登录。

2）、输入一个你喜欢的 Vercel 项目名称并点击 Create 继续:

3）、此时 Vercel 会基于 Waline 模板帮助你新建并初始化仓库，仓库名为你之前输入的项目名。几分钟后，满屏的烟花会庆祝你部署成功。此时点击 Go to Dashboard 可以跳转到应用的控制台。

4）、点击顶部的 Settings - Environment Variables 进入环境变量配置页，并配置三个环境变量 LEAN_ID, LEAN_KEY 和 LEAN_MASTER_KEY 。它们的值分别对应上一步在 LeanCloud 中获得的 APP ID, APP KEY, Master Key，Environment下的Production、Preview、Development全部选中，如果你使用 LeanCloud 国内版，请额外配置 LEAN_SERVER 环境变量，值为你绑定好的域名。点击顶部的 Settings - Domains 进入域名配置页，输入需要绑定的域名并点击 Add，在域名服务器商处添加新的 CNAME 解析记录，等待生效，你可以通过自己的域名来访问了。

5）、环境变量配置完成之后点击顶部的 Deployments 点击顶部最新的一次部署右侧的 Redeploy 按钮进行重新部署。该步骤是为了让刚才设置的环境变量生效。

6）、此时会跳转到 Overview 界面开始部署，等待片刻后 STATUS 会变成 Ready。此时请点击 Visit ，即可跳转到部署好的网站地址，此地址即为你的服务端地址。

本来到这里就该配置客户端正常使用了，但是vercel.app 域名遭受 DNS 污染攻击，在国内无法直接访问此域名，接着看下面的配置吧！

## 国内访问vercel

Waline 官方提供的免费部署方案，vercel.app 域名遭受 DNS 污染攻击，在国内无法直接访问此域名，导致众多 Waline 用户的服务直接陷入“宕机”状态，真可谓是雪上加霜。

遇到问题解决问题

### 方案1

DNS Server转发

有备案可用域名，直接转发Vercel DNS Server地址

在自有域名的DNS服务中添加一条记录，选择CNAME类型转发，记录值填写为：cname.vercel-dns.com，然后在Vercel中找到Waline后端服务的项目，点击Settings标签卡，跳转页面后点击左侧的Domains菜单项，输入你自己定义的域名点击Add按钮即可。

### 方案2

申请免费域名，配置 Vercel 提供的 DNS 服务器

申请免费域名，不过这里不需要借助 DNSPOD 提供的解析服务，所以在申请域名时可以直接填写 Vercel 提供的 DNS 服务，默认地址为ns1.vercel-dns.com、ns2.vercel-dns.com，域名申请下来后，访问 Vercel 的域名控制面板 Domains Dashboard 点击右上角的Add按钮选择你的 Waline 项目点击Continue按钮，再输入申请好的域名确认即可。

该方案中的免费域名一直没有申请下来，于是做了自己域名的NS记录，转到ns1.vercel-dns.com。

### 方案3

域名A记录，vercel CNAME转发

如果你有自己的域名，那么可以按照如下来配置，首先打开的域名控制台，添加一条如下的规则

vercel A 76.223.126.88

然后我们进入 vercel 的控制台，进入你上面新建的项目，点击Setting，Domains，添加对应的域名，这里要和我们在域名控制台设置的一样，填 vercel.xxx.com 即可

新建之后我们点击右侧的 edit 按钮，会出现如下

点击 View DNS Records & More for XXX → 这个链接，然后添加一条 CNAME 规则，如下

vercel CNAME cname-china.vercel-dns.com

这样就完成了

## 创建免费域名

[创建属于你自己的org永久域名](https://blog.jiandan.cf/post/create-your-forever-org-domain.html)

## 备注

以上内容整理自Waline官网、lisenhui.cn博客。

不足之处，后期整理细化。