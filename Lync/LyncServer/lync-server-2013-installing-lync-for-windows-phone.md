---
title: Lync Server 2013：安装适用于 Windows Phone 的 Lync
description: Lync Server 2013：安装适用于 Windows Phone 的 Lync。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f5da90a5dc0babdc6944e4f9c426fe896d4f156
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573978"
---
# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a>在 Lync Server 2013 中安装适用于 Windows Phone 的 Lync

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-03_

适用于 Windows phone 的 Lync 2013 是可在 Windows Phone 市场中使用的用户可安装的应用程序。

<div>

## <a name="installing-lync-for-windows-mobile"></a>安装 Lync for Windows Mobile

您可以指示用户通过将 Lync 2013 for Windows Phone 安装在其设备上，具体方法是将其定向到 Windows Phone Marketplace <https://go.microsoft.com/fwlink/p/?linkid=231901> 。

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a>如果使用 DNS SRV 记录发布 Exchange Web 服务

若要为 Lync 客户端启用 Exchange 集成，某些组织会使用 DNS SRV 记录发布 Exchange Web 服务 URL。 Microsoft 下载中心中的 "了解和疑难解答 Exchange 集成" 文档 [https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095) 介绍了可能需要此功能的情况。 但是，由于 Windows Phone 平台不支持 SRV 查找，因此 Windows Phone 用户的 Exchange 集成将无法在这种情况下运行。 你将需要指示 Windows Phone 用户指定 Exchange Web 服务 URL，而不是允许电话自动检测服务器。

指导用户在其 Windows phone 上配置 Lync 设置，如下所示：

1.  在 Windows Phone 中，在 "Lync 设置" 中，选择 " **Exchange** " 屏幕。

2.  将 **自动检测服务器** 移动到 **关闭状态**。

3.  点击 "空" 字段，并输入 Exchange Web 服务 (FQDN) 或 URL 的完全限定的域名称。
    
    <div>
    

    > [!NOTE]  
    > 您可以指定完全限定的域名 (FQDN) 或 Exchange Web 服务服务器的完整 URL。 如果指定 FQDN，协议 (https://) 和 Exchange Web 服务路径 (/ews/exchange.asmx) 将自动添加。 如果您的 Exchange Web 服务路径不同，您可以指定完整的 URL。

    
    </div>

4.  关闭屏幕。

</div>

<div>

## <a name="verifying-mobile-client-installation"></a>验证移动客户端安装

配置客户端并成功登录后，请使用以下测试来验证您的 Lync 2013 安装是否在移动设备上正常运行。

**搜索企业目录中的联系人**

1.  在“联系人”列表中，点击底部的“搜索”****。

2.  搜索仅存在于全局地址列表中的联系人。

3.  确认联系人姓名出现在搜索结果中。

**测试即时消息和状态**

1.  在“联系人”列表中，点击一个联系人。

2.  在联系人卡片中，点击“IM”**** 图标。

3.  验证即时消息 (IM) 窗口是否显示，以及是否可以键入和发送即时消息。

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

</div>

</div>

<span> </span>

</div>

</div>

</div>

