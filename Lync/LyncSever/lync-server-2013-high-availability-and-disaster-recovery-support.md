---
title: Lync Server 2013：高可用性和灾难恢复支持
TOCTitle: 高可用性和灾难恢复支持
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204866(v=OCS.15)
ms:contentKeyID: 49312729
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的高可用性和灾难恢复支持

 

_**上一次修改主题：** 2012-09-25_

Lync Server 2013 通过借助池实现的服务器冗余提供了高可用性。如果运行特定服务器角色的服务器发生故障，则池中运行相同角色的其他服务器将承担该服务器的负载。这适用于前端服务器、边缘服务器、中介服务器和控制器。有关服务器角色的详细信息，请参阅 [Lync Server 2013 中的服务器角色](lync-server-2013-server-roles.md)。

Lync Server 2013 还通过启用池配对提供了灾难恢复措施。如果您部署了此拓扑，则将指定前端池对，对中的每个池位于不同地理区域的不同数据中心。如果一个池或一个站点不可用，则可将该池中的用户重定向至使用对中的其他池，并且对服务的干扰程度可以忽略不计。

Lync Server 2013 还支持后端服务器高可用性。这是一个可选拓扑，您可以在其中为前端池部署两台后端服务器，然后为在后端服务器上运行的所有 Lync 数据库设置同步的 SQL Server 镜像。

有关池配对和后端服务器镜像的详细信息，请参阅 [在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。

## 另请参阅

#### 概念

[Lync Server 2013 中的服务器角色](lync-server-2013-server-roles.md)  
[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)

