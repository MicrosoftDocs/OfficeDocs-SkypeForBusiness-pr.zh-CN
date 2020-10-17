---
title: Lync Server 2013：规划前端池配对
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 484a19b890602ea338f5e98a126a13582ce7e931
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522189"
---
# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a>在 Lync Server 2013 中规划前端池配对

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-28_

为了在 Lync Server 2013 中获取最佳的灾难恢复能力，请跨两个地理位置分散的网站部署前端池的对。 每个站点包含一个前端池，该池与另一个站点中的相应前端池配对。 这两个站点都处于活动状态，并且 Lync Server 备份服务提供实时数据复制以保持池同步。 备份服务是 Lync Server 2013 中的一项新功能，旨在支持灾难恢复解决方案。 当您将该前端池与另一个前端池配对时，会将该服务安装到该池上。

如果某个站点中的池失败，则您可以将用户从该前端池故障转移到另一个站点中的池，然后可向两个池中的所有用户提供服务。出于容量规划目的，每个池应设计为在发生灾难时处理两个池中所有用户的工作负荷。

<div>

## <a name="in-this-section"></a>本节内容

  - [Lync Server 2013 的受支持的池配对选项和最佳做法](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Lync Server 2013 中的备份注册器关系](lync-server-2013-backup-registrar-relationships.md)

  - [Lync Server 2013 中池故障转移和池故障回复的恢复时间](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Lync Server 2013 中的中央管理存储故障转移](lync-server-2013-central-management-store-failover.md)

  - [Lync Server 2013 中的前端池配对数据安全性](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

