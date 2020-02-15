---
title: Lync Server 2013：部署分支站点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edacf70cf4a8b899857864c400fa92f78bb0d94b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a>在 Lync Server 2013 中部署分支站点

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

分支站点用户从与分支站点相关联的中心站点上的服务器获取其大多数 Lync Server 2013 功能。 每个分支站点都只与一个中央站点关联。 要提供来往于公用电话交换网 (PSTN) 的呼叫，分支站点可以包含以下任一项：

  - PSTN 网关和可选的中介服务器

  - SIP 中继

  - 具有专用交换机 (PBX) 的现有语音基础结构

  - Survivable 分支设备

  - Survivable 分支服务器

具有 Survivable 分支设备或 Survivable 分支服务器的分支站点在广域网或分支服务器上的工作方式比不包含这些解决方案中的分支站点的时间更具弹性。 例如，在部署了 Survivable 分支机构或 Survivable 分支服务器的站点中，如果将分支站点连接到中心站点的网络处于关闭状态，则用户仍可以发出和接收 PSTN 呼叫。 实现分支站点恢复的另一种方法是在分支站点上使用具有完全规模的 Lync Server 部署的 PSTN 网关或 SIP 中继。

若要详细了解哪个分支站点部署适合您的组织，包括先决条件和其他规划注意事项，请参阅规划文档中的在 lync server [2013 中规划 PSTN 连接](lync-server-2013-planning-for-pstn-connectivity.md)和[规划分支站点语音2013恢复](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中提供分支站点的 PSTN 连接](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [使用 Lync Server 2013 部署 Survivable 分支设备或服务器](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

