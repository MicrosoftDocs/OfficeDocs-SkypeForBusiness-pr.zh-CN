---
title: 安装 Lync for Windows Phone
TOCTitle: 安装 Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690996(v=OCS.15)
ms:contentKeyID: 52061128
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 安装 Lync for Windows Phone

 

_**上一次修改主题：** 2016-12-08_

Lync 2013 for Windows Phone 是 Windows Phone Marketplace 中提供的一种用户可安装的应用程序。

## 安装 Lync for Windows Mobile

通过将用户定向到 Windows Phone Marketplace（网址为 <http://go.microsoft.com/fwlink/?linkid=231901>），您可以指示用户在其设备上安装 Lync 2013 for Windows Phone。

## 如果您使用 DNS SRV 记录发布 Exchange Web 服务

为了对 Lync 客户端启用 Exchange 集成，一些组织使用 DNS SRV 记录发布 Exchange Web 服务 URL。文档“了解 Exchange 集成并对其进行故障排除”（可从 Microsoft 下载中心获得，地址是 [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)）介绍了可能必需这样做时的情形。然而，对 Windows Phone 用户而言，在这种情形下 Exchange 集成无法正常工作，因为 Windows Phone 平台不支持 SRV 查找。您需要指导 Windows Phone 用户指定 Exchange Web 服务 URL，而不是让手机自动检测服务器。

指导用户按以下操作在其 Windows Phone 上配置 Lync 设置：

1.  在 Windows Phone 中，在 Lync 设置中，选择“Exchange”屏幕。

2.  将“自动检测服务器”移至“关”。

3.  点击空字段，输入 Exchange Web 服务的完全限定域名 (FQDN) 或 URL。
    
    > [!NOTE]  
    > 您可以指定 Exchange Web 服务服务器的完全限定域名 (FQDN) 或完整 URL。如果您指定 FQDN，则自动添加协议 (https://) 和 Exchange Web 服务路径 (/ews/exchange.asmx)。如果您的 Exchange Web 服务路径不同，您可以指定完整 URL。
    


4.  关闭该屏幕。

## 验证移动客户端安装

配置客户端并成功登录后，可使用以下测试来确认所安装的 Lync 2013 在移动设备上能否正常工作。

**搜索企业目录中的联系人**

1.  在“联系人”列表中，点击底部的“搜索”。

2.  搜索仅存在于全局地址列表中的联系人。

3.  确认联系人姓名出现在搜索结果中。

**测试即时消息和状态**

1.  在“联系人”列表中，点击一个联系人。

2.  在联系人卡片中，点击“IM”图标。

3.  确认显示了即时消息 (IM) 窗口并且您可以键入和发送 IM。

**测试电话拨出式会议**

1.  在 Outlook 中安排 Lync 会议。

2.  在移动设备上，打开会议邀请。

3.  单击会议中的链接以加入会议。

4.  应答来自会议服务的呼叫，并确认您已连接到会议音频。

**测试推送通知**

1.  在用户 A 的移动设备上，使用用户 A 的帐户登录 Lync。

2.  在移动设备上打开其他应用程序。

3.  在其他客户端上，使用用户 B 的帐户登录 Lync。

4.  将 IM 从用户 B 发送到用户 A。

5.  确保用户 A 的移动设备上显示 IM 通知。

