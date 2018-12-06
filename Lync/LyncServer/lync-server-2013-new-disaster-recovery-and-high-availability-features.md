---
title: Lync Server 2013：新的灾难恢复和高可用性功能
TOCTitle: 新的灾难恢复和高可用性功能
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204892(v=OCS.15)
ms:contentKeyID: 49312820
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中新的灾难恢复和高可用性功能

 

_**上一次修改主题：** 2012-09-20_

与在 Lync Server 2010 中一样， Lync Server 2013 的主要高可用性 (HA) 架构基于借助池实现的服务器冗余。如果运行特定服务器角色的服务器发生故障，则池中运行相同角色的其他服务器将承担该服务器的负载。这适用于前端服务器、边缘服务器、中介服务器和控制器。

Lync Server 2013 通过支持您将位于两个数据中心的前端池配对添加了新的灾难恢复措施。如果其中一个配对池不可用，则管理员可将该池中的用户故障转移到配对中的其他池，以继续提供服务。此功能无需昂贵的网络或硬件解决方案，如存储网络或共享磁盘。

Lync Server 2013 还添加了后端服务器高可用性。这是一个可选拓扑，您可以在其中为前端池部署两台后端服务器，然后为在后端服务器上运行的所有 Lync 数据库设置同步 SQL 镜像。您可选择是否为镜像部署见证。

## 另请参阅

#### 概念

[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)

