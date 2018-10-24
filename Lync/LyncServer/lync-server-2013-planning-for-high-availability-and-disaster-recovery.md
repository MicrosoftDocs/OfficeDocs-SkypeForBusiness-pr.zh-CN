---
title: Lync Server 2013：规划高可用性和灾难恢复
TOCTitle: 规划高可用性和灾难恢复
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204703(v=OCS.15)
ms:contentKeyID: 49312101
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中规划高可用性和灾难恢复

 

_**上一次修改主题：** 2013-10-31_

在 Lync Server 2010 中，Lync Server 2013 中用于大多数服务器角色的主要高可用性方案以通过池化的服务器冗余为基础。如果运行特定服务器角色的服务器发生故障，那么池中运行同一角色的其他服务器将接纳该服务器的负荷。这适用于前端服务器、边缘服务器、中介服务器和控制器。

Lync Server 2013 为前端池添加了新的灾难恢复措施，方法是将您的服务器分散到两个数据中心，以便在某个池或站点整个瘫痪时可以继续提供服务。

Lync Server 2013 通过支持用于后端数据库的同步 SQL 镜像，还增强了后端服务器的高可用性。

本节对这些主要的高可用性和灾难恢复功能进行了说明，还介绍了为其他服务器角色实现高可用性和灾难恢复所需执行的步骤。

## 本节内容

  - [Lync Server 2013 中的前端池灾难恢复](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [Lync Server 2013 中的边缘服务器灾难恢复](lync-server-2013-edge-server-disaster-recovery.md)

  - [在 Lync Server 2013 中规划企业语音恢复能力](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [Lync Server 2013 中实现灾难恢复的呼叫管理功能](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [在 Lync Server 2013 中为持久聊天服务器配置高可用性和灾难恢复](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [Lync Server 2010 都市站点恢复能力](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

