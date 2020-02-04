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
ms.openlocfilehash: f2e5dc3323ad14f02a5b24258878512707f66f19
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a>Lync Server 2013 的 Lync Server 网站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-16_

在 Lync Server 中，你可以在网络上定义包含 Lync Server 组件的*网站*。 站点是一组由高速度、低延迟网络（例如，单个局域网 (LAN) 或由高速光纤网络连接的两个网络）完美连接的计算机。 请注意，Lync Server 网站是来自 Active Directory 域服务站点和 Microsoft Exchange Server 站点的独立概念。 您的 Lync 服务器站点不需要对应于您的 Active Directory 站点。

<div>

## <a name="site-types"></a>网站类型

每个网站都是一个*中心网站*，其中包含至少一个前端池或一个标准版服务器或一个*分支站点*。 每个分支站点仅与一个中心网站相关联，并且分支网站中的用户可以从关联的中心网站上的服务器中获取大多数 Lync Server 功能。

每个分支站点都包含下列内容之一：

  - *Survivable 分支装置（SBA）*，它是一台具有 Lync 服务器注册机构的行业标准刀片式服务器和在 Windows server 上运行的中介服务器。 Survivable 分支装置还包含一个公共交换电话网络（PSTN）网关。 Survivable 分支设备适用于25至1000用户之间的分支站点。

  - *Survivable 分支服务器（SBS）*，它是一台运行 Windows Server 的服务器，它满足指定的硬件要求，并且安装了 Lync Server 注册机构和中介服务器软件。 它必须连接到 PSTN 网关或电话服务提供商的 SIP 中继。 Survivable 分支服务器专为1000和5000用户之间的分支站点而设计。

  - PSTN 网关和*中介服务器*（可选）。 有关此服务器角色和其他服务器角色的详细信息，请参阅[Lync server 2013 中的服务器角色](lync-server-2013-server-roles.md)。

对中央网站具有弹性广域网（WAN）链接的分支机构可以使用第三个选项： PSTN 网关，也可以使用中介服务器。 具有不太弹性的链接的分支 office 网站应使用 Survivable 分支装置或 Survivable 分支服务器，这种服务可在广域网络故障的时间内提供恢复。 例如，在具有 Survivable 分支装置或部署 Survivable 分支服务器的网站中，如果将分支站点连接到中心网站的 WAN 已关闭，则用户仍可以发出和接收企业语音呼叫。 有关 Survivable 分支装置、Survivable 分支服务器和复原的详细信息，请参阅规划文档中的[Lync server 2013 中的 "规划企业语音复原](lync-server-2013-planning-for-enterprise-voice-resiliency.md)"。

</div>

<div>

## <a name="site-topologies"></a>网站拓扑

你的部署必须包含至少一个中心网站，并且可以包含零个到多个分支网站。 每个分支站点都与一个中心站点关联。 中心网站向分支网站提供 Lync 服务器服务，该服务不是在本地的分支网站托管，例如状态和会议。

如果你有多个网站，则可以将不同站点上的前端池结合在一起，以启用灾难恢复功能。 有关详细信息，请参阅[Lync Server 2013 中的高可用性和灾难恢复支持](lync-server-2013-high-availability-and-disaster-recovery-support.md)。

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

