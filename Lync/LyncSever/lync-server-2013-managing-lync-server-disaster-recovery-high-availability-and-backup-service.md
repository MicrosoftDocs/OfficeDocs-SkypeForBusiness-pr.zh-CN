---
title: Lync Server 2013：管理 Lync Server 灾难恢复、高可用性和备份服务
TOCTitle: 管理 Lync Server 2013 灾难恢复、高可用性和备份服务
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49888684
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 管理 Lync Server 2013 灾难恢复、高可用性和备份服务

 

_**上一次修改主题：** 2012-11-12_

本节包含灾难恢复操作以及维护同步配对前端池中数据的备份服务的过程。

灾难恢复过程（故障转移和故障回复）都是手动的操作。如果出现灾难，管理员必须手动调用故障转移过程。在修复池之后，此规则同样适用于故障回复。

本节其余部分中的灾难恢复过程假定以下内容：

  - 您有一个部署具有配对的前端池，它们位于不同站点中，如 [在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)中所述。这些配对池中已经运行备份服务，以使其保持同步。

  - 如果 中央管理存储托管在任何一个池中，则它会在两个配对池中安装并运行，其中一个池托管活动的主存储，另一个池承载备用存储。

> [!IMPORTANT]  
> 在下面的过程中， <em>PoolFQDN</em> 参数表示受灾难影响的池而不是受影响的用户从中重定向的池的 FQDN。对于同一组受影响的用户，它在故障转移和故障回复 cmdlet 中表示同一个池（即，在故障转移之前先承载用户的池）。<br />
> 例如，假定这样一种情况，其中驻留在池 P1 中的所有用户都故障转移到备份池 P2。如果管理员要将当前由 P2 服务的所有用户都移动为由 P1 服务，则管理员必须执行以下步骤：
> <ol>
> <li><p>使用故障回复 cmdlet 将最初驻留在 P1 上的所有用户从 P2 故障回复到 P1。在此情况下， <em>PoolFQDN</em> 为 P1 的 FQDN。</p></li>
> <li><p>使用故障转移 cmdlet 将最初驻留在 P2 上的所有用户故障转移到 P1。在此情况下， <em>PoolFQDN</em> 为 P2 的 FQDN。</p></li>
> <li><p>如果稍后管理员要将这些 P2 用户故障回复到 P2，则 <em>PoolFQDN</em> 为 P2 的 FQDN。</p></li>
> </ol>
> 请注意，上面的步骤 1 必须在步骤 2 之前执行，才能保留池完整性。如果在步骤 1 之前尝试步骤 2，则步骤 2 cmdlet 将失败。


## 本部分内容

  - [在 Lync Server 2013 中配置和监控备份服务](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [在 Lync Server 2013 中对池进行故障转移](lync-server-2013-failing-over-a-pool.md)

  - [在 Lync Server 2013 中对池进行故障回复](lync-server-2013-failing-back-a-pool.md)

  - [在 Lync Server 2013 中对镜像数据库进行故障转移](lync-server-2013-failing-over-a-mirrored-database.md)

  - [在 Lync Server 2013 中对用于 Lync Server 联盟的边缘池进行故障转移](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [在 Lync Server 2013 中对用于 XMPP 联盟的边缘池进行故障转移](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [在 Lync Server 2013 中对用于 Lync Server 联盟或 XMPP 联盟的边缘池进行故障回复](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [在 Lync Server 2013 中更改与前端池关联的边缘池](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [在 Lync Server 2013 中使用备份服务还原会议内容](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

## 另请参阅

#### 概念

[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)

