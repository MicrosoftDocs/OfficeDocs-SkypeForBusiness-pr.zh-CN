---
title: 管理 Lync Server 灾难恢复、高可用性和备份服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7adc4086ac8ac6b8e5ad33c2e4c1dc131d357e0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a>管理 Lync Server 2013 灾难恢复、高可用性和备份服务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-12_

本部分包含灾难恢复操作的过程，以及用于维护同步服务的过程，该备份服务将同步成对前端池内的数据。

灾难恢复过程（故障转移和回切）是手动的。 如果发生灾难，管理员必须手动调用故障转移过程。 修复完池后，故障回复也同样适用。

本部分其余部分中的灾难恢复过程假设如下：

  - 你的部署具有成对的前端池，位于不同的网站中，如在[Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)中所述。 备份服务已在这些配对的池上运行，以使其保持同步。

  - 如果中央管理存储托管在任一池中，则会在这两个配对的池上安装和运行它，其中一个托管活动主机的池和另一个托管备用池的池。

<div>


> [!IMPORTANT]
> 在以下过程中， <EM>PoolFQDN</EM>参数是指受灾难影响的池的 FQDN，而不是对受影响的用户进行重定向的池的 FQDN。 对于同一组受影响的用户，它指的是故障转移和故障回复 cmdlet 中的同一池（即，在故障转移之前首先驻留用户的池）。<BR>例如，假设驻留在池 P1 上的所有用户都已故障转移到备份池 P2 的情况。 如果管理员想要移动当前由 P2 服务的所有用户以供 P1 处理，管理员必须执行以下步骤： 
> <OL>
> <LI>
> <P>使用故障回复 cmdlet，将原来位于 P1 中的所有用户从 P2 切换回 P1。 在此情况下， <EM>PoolFQDN</EM>为 P1's FQDN。</P>
> <LI>
> <P>使用故障转移 cmdlet，将所有最初驻留在 P2 上的用户故障转移到 P1。 在此情况下， <EM>PoolFQDN</EM>为 P2's FQDN。</P>
> <LI>
> <P>如果管理员稍后希望将这些 P2 用户故障回复回 P2，则<EM>PoolFQDN</EM>为 P2's FQDN。</P></LI></OL>请注意，上面的步骤1必须在步骤2之前执行，以保留池完整性。 如果你在步骤1之前尝试步骤2，则步骤 2 cmdlet 将失败。



</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中配置和监控备份服务](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [在 Lync Server 2013 中对池进行故障转移](lync-server-2013-failing-over-a-pool.md)

  - [在 Lync Server 2013 中对池进行故障回复](lync-server-2013-failing-back-a-pool.md)

  - [在 Lync Server 2013 中对镜像数据库进行故障转移](lync-server-2013-failing-over-a-mirrored-database.md)

  - [在 Lync Server 2013 中对用于 Lync Server 联盟的边缘池进行故障转移](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [在 Lync Server 2013 中对用于 XMPP 联盟的边缘池进行故障转移](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [在 Lync Server 2013 中对用于 Lync Server 联盟或 XMPP 联盟的边缘池进行故障回复](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [在 Lync Server 2013 中更改与前端池关联的边缘池](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [在 Lync Server 2013 中使用备份服务还原会议内容](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

