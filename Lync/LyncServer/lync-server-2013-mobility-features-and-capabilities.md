---
title: Lync Server 2013：移动功能和特性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e47a37acd45ed577b9ad730de39c79d4113c8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a>Lync Server 2013 中的移动功能和特性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-19_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 的累积更新中引入的移动功能: 2 月2013支持 Lync 2010 手机和 Lync 2013 移动客户端功能。 部署 Lync Server 2013 移动服务时, 用户可以使用支持的 Apple iOS、Android 和 Windows Phone 或 Nokia Symbian 移动设备执行诸如发送和接收即时消息、查看联系人和查看状态等活动。 此外, 移动设备支持某些企业语音功能, 例如单击加入会议、通过工作、单号码达到、语音邮件和未接来电进行呼叫。 Lync Server 2013 的累积更新中引入的新功能: 2 月2013包括适用于会议与会者的 IP 语音 (VoIP) 功能和视频 (H-p)。

Lync Server 2013 的累积更新中引入的移动功能: 2 月2013支持 Lync 2013 移动客户端功能。 Lync Server 2013 的累积更新: 2 月2013安装统一通信 Web API 或 UCWA。 UCWA 是用于 Lync 2013 移动客户端的组件。 在 Lync Server 2013 中, Mcx 用于 Lync 2010 移动客户端。 Lync Server 2013 的累积更新: 2 月2013将 UCWA 引入新的移动服务入口点。 Lync Server 2013 同时实现了在 Lync Server 2010 的累积更新中引入的移动服务 (Mcx): 年 11 2011 月, 并提供了对 Lync 2010 Mobile 的支持。 当你部署 Lync Server 2013 的累积更新时: 2 月 2013, 用户可以使用支持的 Apple iOS、Android 和 Windows Phone 移动设备执行如下活动:

<div>


> [!IMPORTANT]  
> Lync Server 2010 的累积更新中的移动服务支持的功能:11 月 2011 (Mcx) 注明。 在 Lync Server 2013 的累积更新中引入的 UCWA 支持所有列出的功能: 2 月2013。



</div>

  - 发送和接收即时消息 (Mcx)

  - 查看状态 (Mcx)

  - 查看联系人 (Mcx)

  - 单击以加入会议 (Mcx)

  - 通过工作进行通话 (Mcx)

  - 单数字到达 (Mcx)

  - 语音邮件 (Mcx)

  - 未接来电通知 (Mcx)

  - IP 语音 (VoIP)

  - 与会者视频 (H.264)

<div>


> [!NOTE]  
> Lync 2010 Mobile 提供了适用于 Nokia Symbian 设备的客户端。 Lync 2013 Mobile 将没有基于 Nokia Symbian 设备的客户端。



</div>

Apple iPad 用户将有权访问增强功能。 通过使用音频呼叫加入会议后, iPad 用户将能够在会议内查看上载的 Microsoft PowerPoint 演示文稿、共享应用程序和桌面、查看会议参与者列表以及接收其他内容类型的通知会议中共享的。

<div>


> [!TIP]  
> 通过单个号码, 用户可在移动电话上接收已拨至工作电话号码的呼叫。 通过工作电话, 用户通过使用工作电话号码 (而不是移动电话号码), 从 Lync 移动客户端处发出出站呼叫。 通过拨出, 客户端将向 Mcx 或 UCWA (基于 Lync Mobile 版本) 发送请求以进行呼叫。 服务器启动呼叫, 然后通过移动电话回拨用户。 当用户接听时, 服务器将通过拨另一方来完成呼叫。 通过使用 "通过工作呼叫", 用户可以在通话期间维护其工作标识, 这意味着呼叫收件人看不到呼叫者的移动电话号码, 并且呼叫者避免发出出站通话费用。



</div>

<div>


> [!NOTE]  
> 并非所有功能在所有移动设备上都具有完全相同的效果。 有关移动设备支持的功能的详细信息, 请参阅中的移动客户<A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>端比较表。 有关支持的设备和操作系统的详细信息, 请参阅<A href="lync-server-2013-planning-for-mobile-clients.md">规划 Lync Server 2013 中的移动客户端中</A>的 "要求" 主题。



</div>

使用 Lync Server 2013 自动发现功能时, 移动应用程序可以自动查找 Lync Server 2013 Web 服务, 而无需用户在其设备设置中手动输入 Url。 在移动设备设置中也支持手动输入 Url, 这主要是出于故障排除目的。

<div>


> [!IMPORTANT]  
> Mcx 和 UCWA 是免费服务, 并且都是为支持 Lync 2010 移动版和 Lync 2013 移动客户端而部署的。 Lync 2013 Mobile 将无法登录 Lync Server 2010 部署。 Lync 2010 手机和 Lync 2013 移动版将能够使用 lync server 2013 部署和 Lync Server 2013 的累积更新: 应用了 2 2013 月。



</div>

移动功能还支持针对不支持在后台运行的应用程序的移动设备的*推送通知*。 推送通知是一类发送给移动设备的有关当移动设备处于不活动状态时发生的事件的通知。 例如, 错过的即时消息 (IM) 邀请可能会导致推送通知。

Mcx、UCWA、自动发现服务和推送通知支持均在 Lync Server 2013 中提供。 在 Lync Server 2013 的累积更新中引入了客户端功能、功能和使用 UCWA 作为移动入口点: 2 月2013。

</div>

<span> </span>

</div>

</div>

</div>

