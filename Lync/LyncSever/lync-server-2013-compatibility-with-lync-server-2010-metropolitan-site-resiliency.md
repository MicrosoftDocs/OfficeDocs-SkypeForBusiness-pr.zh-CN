---
title: Lync Server 2013 兼容性与 Lync Server 2010 都市站点恢复能力
TOCTitle: Lync Server 2010 都市站点恢复能力
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204715(v=OCS.15)
ms:contentKeyID: 49312130
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2010 都市站点恢复能力

 

_**上一次修改主题：** 2014-03-19_

Lync Server 2010 支持的都市站点复原解决方案不受 Lync Server 2013 支持。此解决方案涉及在同一都市圈中的两个数据中心之间跨越使用一个前端池。

都市站点恢复能力解决方案旨在从完整的数据中心恢复。 当您的池跨越两个数据中心时，您通常会将一半前端放在一个数据中，而另一半放在第二个数据中心中。如果您丢失整个数据中心，则您将丢失一半前端服务器。这可能导致 Lync Server 2013 中的全新前端池分布式系统模型出现问题。有关详细信息，请参阅 [Lync Server 2013 中适用于前端服务器、即时消息和状态的拓扑和组件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。

