---
title: 将子网与网络站点相关联以启用 CAC
TOCTitle: 将子网与网络站点相关联以启用 CAC
ms:assetid: a749c9b3-15f3-4e74-9f43-1507d3c2c940
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412786(v=OCS.15)
ms:contentKeyID: 49313872
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将子网与网络站点相关联以启用 CAC

 

_**上一次修改主题：** 2012-10-20_

网络中的每个子网必须与特定网络站点相关联。这是因为子网信息用于确定端点所在的网络站点。了解会话双方的位置后，呼叫允许控制 (CAC) 可以确定是否有足够的带宽来建立呼叫。

呼叫允许控制对于将子网与网络站点相关联没有任何特殊要求。要在拓扑中的子网和网络站点之间建立关联，请执行[在 Lync Server 2013 中将子网与网络站点相关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)中的步骤。要查看呼叫允许控制的示例网络拓扑中的网络站点（及其各自的子网），请参阅规划文档中的[示例：在 Lync Server 2013 中收集呼叫允许控制要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。

