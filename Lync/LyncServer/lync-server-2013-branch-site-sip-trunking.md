---
title: 'Lync Server 2013: 分支站点 SIP 中继'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 955e920138021941db0e75832d56d06499738edd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-sip-trunking-in-lync-server-2013"></a>Branch site SIP trunking in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-21_

在某些情况下, 你可能需要在选定的分支站点上实施分布式 SIP 中继。 若要确定分支站点是否需要 SIP 主干, 请查看[如何在 Lync Server 2013 中实现 sip 中继](lync-server-2013-how-do-i-implement-sip-trunking.md)的信息？。

有关在分支站点中部署 SIP 中继支持的拓扑选项的详细信息, 请参阅[Lync Server 2013 中的分支站点恢复解决方案](lync-server-2013-branch-site-resiliency-solutions.md)。

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>示例分支站点 SIP 中继要求分析

当您决定部署分支站点 SIP 主干时, 您需要执行特定于站点的成本分析。 例如, 在 Redmond、华盛顿和纽约的分支站点中具有中心网站的企业, 应执行分析以确定是否要从纽约站点向本地服务提供商实施 SIP 主干。

为了确定纽约的分布式 SIP 中继是否经济高效，请标识将使用 SIP 中继的外线直拨分机（DID）号码，并分析纽约向雷德蒙德 (425) 以外的地区发出的呼叫数量。 您可以在中心站点上终止分支站点。 例如, Redmond 中心网站可以托管纽约分支网站的号码。 如果实施分布式 SIP 主干的费用低于这些呼叫的费用, 请考虑在纽约分支机构实施 SIP 中继。

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a>其他分支站点 SIP 中继要求

根据每个选项的公用电话交换网（PSTN）长途电话费的差额，选择部署 SIP 中继，而不是网关。 如果你部署分支网站 SIP 主干, 还需要确定你的恢复性和带宽要求。 如果分支站点和中心网站之间的链接具有弹性且带宽充足, 则可以部署 SIP 主干或网关。 无需在分支站点上部署 Survivable 分支装置。 如果你的分支站点和中心网站之间的链接不能复原, 请部署 Survivable 分支设备, 或使用分支站点上的网关或 SIP 中继部署 Survivable 分支服务器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

