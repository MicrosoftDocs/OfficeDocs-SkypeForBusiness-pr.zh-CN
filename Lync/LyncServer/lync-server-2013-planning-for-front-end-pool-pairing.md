---
title: Lync Server 2013：规划前端池配对
TOCTitle: 规划前端池配对
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205293(v=OCS.15)
ms:contentKeyID: 49314266
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中规划前端池配对

 

_**上一次修改主题：** 2012-09-28_

为了在 Lync Server 2013 中实现最佳灾难恢复能力，跨两个地理位置分散型站点部署前端池对。每个站点包含一个前端池，该池与另一个站点中的相应前端池配对。这两个站点都处于活动状态，并且 Lync Server 备份服务提供了实时数据复制以保持池同步。该备份服务是 Lync Server 2013 中的一项新功能，旨在支持灾难恢复解决方案。当您将该前端池与另一个前端池配对时，会将该服务安装到该池上。

如果某个站点中的池失败，则您可以将用户从该前端池故障转移到另一个站点中的池，然后可向两个池中的所有用户提供服务。出于容量规划目的，每个池应设计为在发生灾难时处理两个池中所有用户的工作负荷。

## 本节内容

  - [Lync Server 2013 支持的池配对选项和最佳做法](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Lync Server 2013 中的备份注册器关系](lync-server-2013-backup-registrar-relationships.md)

  - [Lync Server 2013 中的池故障转移和池故障回复的恢复时间](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Lync Server 2013 中的中央管理存储故障转移](lync-server-2013-central-management-store-failover.md)

  - [Lync Server 2013 中的前端池配对数据安全](lync-server-2013-front-end-pool-pairing-data-security.md)

