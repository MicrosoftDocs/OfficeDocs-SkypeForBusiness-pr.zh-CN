---
title: Lync Server 2013：移动特性和功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a001a6fb76a0612f7f650a31de5cf788a7f69327
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a>Lync Server 2013 中的移动特性和功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-19_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 的累积更新中引入的移动功能：二月份2013支持 Lync 2010 移动和 Lync 2013 移动客户端功能。 在部署 Lync Server 2013 移动服务时，用户可以使用支持的 Apple iOS、Android 和 Windows Phone 或 Nokia Symbian 移动设备执行诸如发送和接收即时消息、查看联系人和查看状态等活动。 此外，移动设备还支持某些企业语音功能，例如，“单击加入会议”、“单位电话呼叫”、“一号通”、“语音邮件”和“错过的呼叫”。 Lync Server 2013 的累积更新中引入的新功能：二月份2013包括适用于会议与会者的 IP 语音（VoIP）功能和视频（）。

Lync Server 2013 的累积更新中引入的移动功能：2月2013支持 Lync 2013 移动客户端功能。 Lync Server 2013 的累积更新：2月2013安装统一通信 Web API 或 UCWA。 UCWA 是用于 Lync 2013 移动客户端的组件。 在 Lync Server 2013 中，Mcx 用于 Lync 2010 移动客户端。 Lync Server 2013 的累积更新：二月份2013将 UCWA 作为移动服务的新入口点引入。 Lync Server 2013 在 Lync Server 2011 2010 的累积更新中引入了移动服务（Mcx），并为 Lync 2010 移动提供了支持。 在部署 Lync Server 2013 2013 的累积更新时，用户可以使用受支持的 Apple iOS、Android 和 Windows Phone 移动设备执行此类活动，如下所示：

<div>


> [!IMPORTANT]  
> 移动服务从 Lync Server 2010 的累积更新支持的功能：11月2011日使用（Mcx）进行标注。 在 Lync Server 2013 的累积更新中引入的 UCWA 支持所有列出的功能：二月份2013。



</div>

  - 发送和接收即时消息（Mcx）

  - 查看状态（Mcx）

  - 查看联系人（Mcx）

  - 单击以加入会议（Mcx）

  - 通过工作呼叫（Mcx）

  - 单个数字范围（Mcx）

  - 语音邮件（Mcx）

  - 未接来电通知（Mcx）

  - IP 电话 (VoIP)

  - 与会者视频（H-p）

<div>


> [!NOTE]  
> Lync 2010 Mobile 提供了适用于 Nokia Symbian 设备的客户端。 Lync 2013 Mobile 不会有客户端用于基于 Nokia Symbian 的设备。



</div>

Apple iPad 用户将可以访问增强功能。 使用音频呼叫回电加入会议后，iPad 用户将能够在会议中查看已上载的 Microsoft PowerPoint 演示文稿、共享应用程序和桌面、查看会议参与者列表，以及接收其他内容类型的通知会议中共享的。

<div>


> [!TIP]  
> 利用一号通功能，用户可以通过移动电话接收拨打至单位号码的呼叫。 通过工作的呼叫，用户通过使用工作电话号码而不是移动电话号码，从 Lync 移动客户端发出出站呼叫。 通过拨出，客户端将向 Mcx 或 UCWA （基于 Lync Mobile 版本）发送请求，以便对其进行呼叫。 服务器将发起呼叫，然后在移动电话上回拨用户。 当用户应答时，服务器将通过拨打另一方的号码来完成呼叫。 通过使用单位电话呼叫功能，用户可以在呼叫期间维护其工作标识，这意味着呼叫接收方将看不到呼叫者的移动电话号码，并且呼叫者可免于支付出站呼叫费。



</div>

<div>


> [!NOTE]  
> 并非所有功能在所有移动设备上的工作方式都相同。 有关移动设备支持的功能的详细信息，请参阅中<A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A>的移动客户端比较表。 有关受支持的设备和操作系统的详细信息，请参阅在<A href="lync-server-2013-planning-for-mobile-clients.md">Lync Server 2013 中规划移动客户端</A>的要求主题。



</div>

当您使用 Lync Server 2013 自动发现功能时，移动应用程序可以自动定位 Lync Server 2013 Web 服务，而无需用户在其设备设置中手动输入 Url。 在移动设备设置中手动输入 URL 也是受支持的，此操作主要用于进行故障排除。

<div>


> [!IMPORTANT]  
> Mcx 和 UCWA 是免费的服务，同时还部署了这两个服务，以支持 Lync 2010 移动和 Lync 2013 移动客户端。 Lync 2013 移动将无法登录 Lync Server 2010 部署。 Lync 2010 Mobile 和 Lync 2013 移动版将能够使用 lync server 2013 部署，其中包含应用了 Lync Server 2013：二月份2013的累积更新。



</div>

移动功能还支持针对不支持在后台运行的应用程序的移动设备的*推送通知*。 推送通知是一类发送给移动设备的有关当移动设备处于不活动状态时发生的事件的通知。 例如，错过的即时消息（IM）邀请可能会导致推送通知。

Lync Server 2013 中提供了 Mcx、UCWA、自动发现服务和对推送通知的支持。 在 Lync Server 2013 的累积更新中引入了客户端功能、功能和使用 UCWA 作为移动入口点的更新：2月2013。

</div>

<span> </span>

</div>

</div>

</div>

