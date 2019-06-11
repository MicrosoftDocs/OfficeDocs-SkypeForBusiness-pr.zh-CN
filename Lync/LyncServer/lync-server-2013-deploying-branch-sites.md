---
title: Lync Server 2013：部署分支站点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c96a8c99b6f80e7e70f3129e502d33b93a73f42
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a>在 Lync Server 2013 中部署分支站点

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-21_

分支网站用户从与分支站点相关联的中心站点上的服务器获取最大部分 Lync Server 2013 功能。 每个分支站点只与一个中心站点相关联。 若要提供与公共交换电话网络 (PSTN) 的呼叫, 分支站点可能包含以下任何内容:

  - PSTN 网关和可能是冥想服务器

  - SIP 主干

  - 使用专用分支交换 (PBX) 的现有语音基础结构

  - Survivable 分支装置

  - Survivable 分支服务器

具有 Survivable 分支装置或 Survivable 分支服务器的分支站点在广域网或分支服务器上的分支站点比没有这些解决方案的分支站点的广域网或中心站点故障更有弹性。 例如, 在具有 Survivable 分支装置或部署的 Survivable 分支服务器的网站中, 如果将分支站点连接到中心站点的网络处于关闭状态, 则用户仍可以发出和接收 PSTN 呼叫。 实现分支站点弹性的另一种方法是在分支站点上使用具有完全规模的 Lync 服务器部署的 PSTN 网关或 SIP 中继。

有关哪些分支站点部署适合你的组织 (包括先决条件和其他规划注意事项) 的详细信息, 请参阅[在 Lync Server 2013 中规划 PSTN 连接](lync-server-2013-planning-for-pstn-connectivity.md)和[规划 lync 中的分支站点语音弹性](lync-server-2013-planning-for-branch-site-voice-resiliency.md)在规划文档中的服务器2013。

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中在分支站点提供 PSTN 连接](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

