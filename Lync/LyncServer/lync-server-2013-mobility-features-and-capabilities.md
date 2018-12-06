---
title: Lync Server 2013：移动功能和特性
TOCTitle: 移动功能和特性
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh689983(v=OCS.15)
ms:contentKeyID: 49312058
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的移动功能和特性

 

_**上一次修改主题：** 2016-12-08_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

2013 年 2 月版的 Lync Server 2013 累积更新中引入的移动功能支持 Lync 2010 Mobile 和 Lync 2013 Mobile 客户端功能。当您部署 Lync Server 2013 Mobility Service 时，用户可以使用受支持的 Apple iOS、Android 和 Windows Phone 或 Nokia Symbian 移动设备来执行发送和接收即时消息、查看联系人和查看状态等活动。此外，移动设备还支持某些企业语音功能，例如“单击加入会议”、“单位电话呼叫”、“一号通”、“语音邮件”和“未接电话”。2013 年 2 月版的 Lync Server 2013 累积更新中引入的新功能包括供与会者使用的 IP 语音 (VoIP) 功能和视频 (H.264)。

2013 年 2 月版的 Lync Server 2013 累积更新中引入的移动功能支持 Lync 2013 Mobile 客户端功能。2013 年 2 月版的 Lync Server 2013 累积更新安装统一通信 Web API 或 UCWA。UCWA 是用于 Lync 2013 Mobile 客户端的组件。在 Lync Server 2013 中，Mcx 用于 Lync 2010 Mobile 客户端。2013 年 2 月版的 Lync Server 2013 累积更新引入 UCWA 作为移动服务的新入口点。 Lync Server 2013 同时实施 2011 年 11 月版的 Lync Server 2013 累积更新中引入的 Mobility Service (Mcx)，并为 Lync 2010 Mobile 提供支持。部署 2013 年 2 月版的 Lync Server 2013 累积更新时，用户可以使用受支持的 Apple iOS、Android 和 Windows Phone 移动设备执行如下活动：

> [!IMPORTANT]
> 受 2011 年 11 月版的 Lync Server 2010 累积更新的 Mobility Service 支持的功能均带有 (Mcx) 标记。所有列出的功能均受 2013 年 2 月版的 Lync Server 2013 累积更新中引入的 UCWA 的支持。


  - 发送和接收即时消息 (Mcx)

  - 查看状态 (Mcx)

  - 查看联系人 (Mcx)

  - 单击加入会议 (Mcx)

  - 单位电话呼叫 (Mcx)

  - 一号通 (Mcx)

  - 语音邮件 (Mcx)

  - 未接电话通知 (Mcx)

  - IP 语音 (VoIP)

  - 与会者视频 (H.264)

> [!NOTE]  
> Lync 2010 Mobile 为 Nokia Symbian 设备提供了一个客户端。Lync 2013 Mobile 将不会为基于 Nokia Symbian 的设备提供客户端。



Apple iPad 用户将可以访问增强功能。在使用音频回拨加入会议后，iPad 用户将能够查看会议中已上载的 Microsoft PowerPoint 演示文稿，共享应用程序和桌面，查看会议参加人列表，并接收会议中共享的其他内容类型的通知。

> [!TIP]
> 利用一号通功能，用户可以通过移动电话接收拨打至单位号码的呼叫。利用单位电话呼叫功能，用户可以使用单位电话号码（而不是移动电话号码）从 Lync Mobile 客户端发出出站呼叫。利用电话拨出式会议，客户端可以请求 Mcx 或 UCWA（基于 Lync Mobile 版本）为其发出呼叫。服务器将发起呼叫，然后在移动电话上回拨用户。当用户应答时，服务器将通过拨打另一方的号码来完成呼叫。通过使用单位电话呼叫功能，用户可以在呼叫期间维护其工作标识，这意味着呼叫接收方将看不到呼叫者的移动电话号码，并且呼叫者可免于支付出站呼叫费。


> [!NOTE]  
> 并非所有功能在所有移动设备上的工作方式都相同。有关移动设备上支持的功能的详细信息，请参阅位于 <a href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</a> 的“移动客户端比较表”。有关受支持的设备和操作系统的详细信息，请参阅<a href="lync-server-2013-planning-for-mobile-clients.md">在 Lync Server 2013 中规划移动客户端</a>下的要求主题。



使用 Lync Server 2013 自动发现功能时，移动应用程序会自动定位 Lync Server 2013 Web 服务而无需用户在其设备设置中手动输入 URL。在移动设备设置中手动输入 URL 也是受支持的，此操作主要用于进行故障排除。

> [!IMPORTANT]
> Mcx 和 UCWA 均是赠送服务，两者的部署用于支持 Lync 2010 Mobile 和 Lync 2013 Mobile 客户端。 Lync 2013 Mobile 将无法登录 Lync Server 2010 部署。 Lync 2010 Mobile 和 Lync 2013 Mobile 将可以使用 Lync Server 2013 部署并应用 2013 年 2 月版的 Lync Server 2013 累积更新。


移动功能还支持针对不支持在后台运行的应用程序的移动设备的 *推送通知* 。推送通知是一类发送给移动设备的有关当移动应用程序处于不活动状态时发生的事件的通知。例如，错过的即时消息 (IM) 邀请会产生推送通知。

Lync Server 2013 中提供有 Mcx、UCWA、自动发现服务和推送通知的支持。2013 年 2 月版的 Lync Server 2013 累积更新中引入了更新的客户端特征、功能以及 UCWA 作为移动入口点的用法。

