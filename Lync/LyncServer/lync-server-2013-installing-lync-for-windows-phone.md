---
title: 'Lync Server 2013: 安装 Lync for Windows Phone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aeb8f43ea4f4db15a9a057bd0d7b24c55d858cb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a>在 Lync Server 2013 中安装 Lync for Windows Phone

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-02-03_

适用于 windows phone 的 Lync 2013 是可由用户安装的应用程序, 可在 Windows Phone Marketplace 中使用。

<div>

## <a name="installing-lync-for-windows-mobile"></a>安装 Lync for Windows Mobile

通过将 Lync 2013 for Windows Phone 定向到 Windows phone 上的 Windows phone, 你可以指示用户在其设备上<http://go.microsoft.com/fwlink/p/?linkid=231901>安装 Lync For windows phone。

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a>如果使用 DNS SRV 记录发布 Exchange Web 服务

为了为 Lync 客户端启用 Exchange 集成, 某些组织使用 DNS SRV 记录发布 Exchange Web 服务 URL。 文档 "了解和疑难解答 Exchange 集成" 适用于 Microsoft 下载中心中的[http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095), 介绍了可能需要此操作的方案。 但是, 由于 Windows Phone 平台不支持 SRV 查找, 因此 Windows Phone 用户的 Exchange 集成将无法在此情况下使用。 你将需要指示 Windows Phone 用户指定 Exchange Web 服务 URL, 而不是允许手机自动检测服务器。

指导用户在其 Windows 手机上配置 Lync 设置, 如下所示:

1.  在 Windows Phone 中, 在 "Lync 设置" 中, 选择 " **Exchange** " 屏幕。

2.  将**自动检测服务器**移动到 "**关闭**"。

3.  点击空字段并输入 Exchange Web 服务的完全限定的域名 (FQDN) 或 URL。
    
    <div>
    

    > [!NOTE]  
    > 你可以指定 Exchange Web 服务服务器的完全限定的域名 (FQDN) 或完整 URL。 如果你指定 FQDN, 将自动添加协议 (https://) 和 Exchange Web 服务路径 (/ews/exchange.asmx)。 如果 Exchange Web 服务路径不同, 则可以指定完整的 URL。

    
    </div>

4.  关闭屏幕。

</div>

<div>

## <a name="verifying-mobile-client-installation"></a>验证移动客户端安装

配置客户端并成功登录后, 请使用以下测试验证您的 Lync 2013 安装是否在移动设备上正常工作。

**搜索企业目录中的联系人**

1.  在 "联系人" 列表中, 点击底部的 "**搜索**"。

2.  搜索仅存在于全局地址列表中的联系人。

3.  确认联系人姓名出现在搜索结果中。

**测试即时消息和状态**

1.  在“联系人”列表中，点击一个联系人。

2.  在联系人卡片中, 点击 " **IM** " 图标。

3.  确认显示了即时消息 (IM) 窗口并且您可以键入和发送 IM。

**测试电话拨出式会议**

1.  在 Outlook 中, 安排 Lync 会议。

2.  在移动设备上，打开会议邀请。

3.  单击会议中的链接以加入会议。

4.  应答来自会议服务的呼叫，并确认您已连接到会议音频。

**测试推送通知**

1.  在用户 A 的移动设备上, 使用用户 A 的帐户登录到 Lync。

2.  在移动设备上打开其他应用程序。

3.  在其他客户端上, 使用用户 B 的帐户登录到 Lync。

4.  将 IM 从用户 B 发送到用户 A。

5.  确保用户 A 的移动设备上显示 IM 通知。

</div>

</div>

<span> </span>

</div>

</div>

</div>

