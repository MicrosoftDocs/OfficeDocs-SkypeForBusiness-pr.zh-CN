---
title: Lync Server 2013：将拉伸的持久聊天服务器池用于灾难恢复
TOCTitle: 将拉伸的持久聊天服务器池用于灾难恢复
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205007(v=OCS.15)
ms:contentKeyID: 49313264
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中将拉伸的持久聊天服务器池用于灾难恢复

 

_**上一次修改主题：** 2012-10-06_

用于 持久聊天服务器的灾难恢复解决方案在扩展的 持久聊天服务器池中生成。这与 Lync Server 2010 中的都市站点恢复能力相似；但是，不要求具有扩展的虚拟局域网 (VLAN)。通过扩展 持久聊天服务器池，逻辑上可在拓扑中配置一个池，但实际将池中的服务器放在两个不同的数据中心中。以同一方式为数据库配置 SQL Server 镜像，并在同一数据中心中部署数据库和镜像。需要在辅助数据中心中配置一个备份数据库（在灾难恢复期间，用可选镜像来提供高可用性）。这是在灾难恢复期间用于故障转移的备份数据库。

有关如何为实现高可用性而配置 SQL Server 镜像的详细信息，请参阅 [Lync Server 2013 中的 SQL Server 镜像](lync-server-2013-sql-server-mirroring.md)。有关为进行灾难恢复而故障转移数据库的详细信息，请参阅 [在 Lync Server 2013 中为持久聊天服务器主数据库设置 SQL Server 日志传送](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md)和 [在 Lync Server 2013 中在主镜像和日志传送辅助数据库之间设置 SQL Server 日志传送](lync-server-2013-setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database.md)。

