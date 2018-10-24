---
title: Lync Server 2013：保护传输途中的数据 – 存档、监控、群聊合规性服务器数据库
TOCTitle: 保护传输途中的数据 – Lync Server 2013 中的存档、监控、群聊合规性服务器数据库
ms:assetid: ea219705-1015-43a7-890b-e7e67b451e7c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn518336(v=OCS.15)
ms:contentKeyID: 60505971
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 保护传输途中的数据 – Lync Server 2013 中的存档、监控、群聊合规性服务器数据库

 

_**上一次修改主题：** 2016-12-08_

Microsoft Lync Server 2013 存档服务器和监控服务器都使用消息队列（也称为 MSMQ）服务来收集数据消息，并将其可靠地从收集点移到存储库服务器中。合规性服务与群聊服务器一起收集数据，此服务器也使用消息队列。

在 Lync Server 2013 中，未对网络上的数据提供内部保护；但是，如果需要保护此流量，则消息队列服务可以为发送的消息队列提供消息级别的加密。为此，请使用由 Active Directory 域服务管理的证书。有关详细信息，请参阅位于 [http://go.microsoft.com/fwlink/p/?LinkId=145238](http://go.microsoft.com/fwlink/p/?linkid=145238)上的“附录 D：Windows Server 2008 中的消息队列和 Internet 通信”或位于 [http://go.microsoft.com/fwlink/p/?LinkId=211883](http://go.microsoft.com/fwlink/p/?linkid=211883) 上的“附录 I：Windows Server 2008 R2 中的消息队列和 Internet 通信”（针对 Windows Server 2008 R2）。

