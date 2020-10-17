---
title: Lync Server 2013 网站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7193d657ad1e585b1a82ba8e934e5bf99d83e65b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519609"
---
# <a name="lync-server-sites-for-lync-server-2013"></a>Lync Server 2013 的 lync Server 网站

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-16_

在 Lync Server 中，您需要定义网络上包含 Lync Server 组件的 *网站* 。 站点是一组由高速度、低延迟网络（例如，单个局域网 (LAN) 或由高速光纤网络连接的两个网络）完美连接的计算机。 请注意，Lync Server 站点是来自 Active Directory 域服务站点和 Microsoft Exchange Server 站点的单独概念。 您的 Lync Server 网站不需要对应于 Active Directory 站点。

<div>

## <a name="site-types"></a>站点类型

每个站点都是一个 *中央站点*，其中至少包含一个前端池或一个标准版服务器或一个 *分支站点*。 每个分支站点只与一个中心站点相关联，而分支站点的用户从关联的中央站点的服务器获取其大多数 Lync Server 功能。

每个分支站点包含以下设备之一：

  - *Survivable Branch 装置 (SBA) *，这是一个具有 Lync server 注册器的行业标准刀片服务器和在 Windows server 上运行的中介服务器。 Survivable 分支设备还包含公开交换电话网络 (PSTN) 网关。 Survivable 分支设备适用于25到1000个用户之间的分支站点。

  - *Survivable Branch Server (SBS) *，它是一台运行 Windows Server 的服务器，它满足指定的硬件要求，并且已在其上安装 Lync server 注册器和中介服务器软件。 它必须连接到 PSTN 网关或电话服务提供商的 SIP 中继。 Survivable Branch Server 是为具有 1000 至 5000 个用户的分支站点而设计的。

  - PSTN 网关和可选的*中介服务器*。 有关此服务器角色和其他服务器角色的详细信息，请参阅 [Lync server 2013 中的服务器角色](lync-server-2013-server-roles.md)。

具有指向中央站点的可恢复广域网 (WAN) 链接的分支机构可以使用第三个选项，即 PSTN 网关和可选的中介服务器。 具有较低弹性链接的分支机构网站应使用 Survivable 分支设备或 Survivable 分支服务器，这将在广域网络故障发生时提供恢复能力。 例如，在部署了 Survivable 分支机构或 Survivable 分支服务器的站点中，如果将分支站点连接到中心站点的 WAN 处于关闭状态，则用户仍可以发出和接收企业语音呼叫。 有关 Survivable 分支装置、Survivable 分支服务器和恢复的详细信息，请参阅规划文档中的在 [Lync server 2013 中规划企业语音恢复](lync-server-2013-planning-for-enterprise-voice-resiliency.md) 。

</div>

<div>

## <a name="site-topologies"></a>站点拓扑

部署中必须至少包含一个中央站点，可以包含多个分支站点，也可以不包含分支站点。 每个分支站点都与一个中央站点关联。 中央站点向分支站点提供了 Lync Server 服务，该站点不在分支站点本地托管，如状态和会议。

如果有多个站点，则可以将不同站点的前端池配对，以实现灾难恢复能力。 有关详细信息，请参阅 [Lync Server 2013 中的高可用性和灾难恢复支持](lync-server-2013-high-availability-and-disaster-recovery-support.md)。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的服务器角色](lync-server-2013-server-roles.md)  
[Lync Server 2013 中的高可用性和灾难恢复支持](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[在 Lync Server 2013 中规划企业语音恢复能力](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

