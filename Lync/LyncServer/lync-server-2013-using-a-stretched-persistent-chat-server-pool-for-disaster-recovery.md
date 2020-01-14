---
title: 将拉伸的持久聊天服务器池用于灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ae23ed2d12548388cd1462aad653de4652633dc
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中将拉伸的持久聊天服务器池用于灾难恢复

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-06_

持久聊天服务器的灾难恢复解决方案是在延长的持久聊天服务器池中构建的。 这类似于 Lync Server 2010 中的大都市网站复原;但是，不需要对已延长的虚拟局域网（VLAN）有任何要求。 通过拉伸持久聊天服务器池，你基本上可以在拓扑中逻辑地配置一个池，但实际上是将服务器放在两个不同数据中心的池中。 以相同的方式为数据库配置 SQL Server 镜像，并在同一数据中心部署数据库和镜像。 需要在辅助数据中心中配置一个备份数据库（在灾难恢复期间，用可选镜像来提供高可用性）。 这是在灾难恢复期间用于故障转移的备份数据库。

有关如何配置 SQL Server 镜像以获得高可用性的详细信息，请参阅[Lync Server 2013 中的 SQL server 镜像](lync-server-2013-sql-server-mirroring.md)。 有关故障恢复数据库以进行灾难恢复的详细信息，请参阅[在 Lync server 2013 中为持久聊天服务器主数据库设置 Sql Server 日志传送](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md)，以及[在 lync server 2013 中的主镜像和日志传送辅助数据库之间设置 Sql server 日志传送](lync-server-2013-set-up-log-shipping-secondary-database.md)。

</div>

<span> </span>

</div>

</div>

</div>

