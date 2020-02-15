---
title: Lync Server 2013：分支站点 SIP 中继
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 161964bc7a183672323ac277eae4f3a7ce0d2b82
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-sip-trunking-in-lync-server-2013"></a>Lync Server 2013 中的分支站点 SIP 中继

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

在某些情况下，您可能需要在选定的分支站点中实施分布式 SIP 中继。 若要确定分支站点是否需要 SIP 中继，请参阅[如何在 Lync Server 2013 中实现 sip 中继？](lync-server-2013-how-do-i-implement-sip-trunking.md)中的信息。

有关在分支站点中部署 SIP 中继的受支持拓扑选项的详细信息，请参阅[Lync Server 2013 中的分支站点恢复解决方案](lync-server-2013-branch-site-resiliency-solutions.md)。

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>示例分支站点 SIP 中继要求分析

当您决定部署分支站点 SIP 中继时，您需要执行特定于站点的成本分析。 例如，在 Redmond、华盛顿和纽约的分支站点中具有中央站点的企业，应进行分析以确定是否将 SIP 中继从纽约站点实施到本地服务提供商。

为了确定纽约的分布式 SIP 中继是否经济高效，请标识将使用 SIP 中继的外线直拨分机（DID）号码，并分析纽约向雷德蒙德 (425) 以外的地区发出的呼叫数量。 您可以在中央站点上终止分支站点。 例如，Redmond 中央网站可以承载纽约分支站点的编号。 如果实施分布式 SIP 中继的成本低于这些呼叫的成本，请考虑在纽约分支站点实施 SIP 中继。

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a>其他分支站点 SIP 中继要求

根据每个选项的公用电话交换网（PSTN）长途电话费的差额，选择部署 SIP 中继，而不是网关。 如果部署分支站点 SIP 中继，还需要确定恢复能力和带宽要求。 如果您的分支站点和中央站点之间的链接具有可恢复性且具有足够的带宽，则可以部署 SIP 中继或网关。 您无需在分支站点上部署 Survivable 分支设备。 如果您的分支站点和中央站点之间的链接不可恢复，请部署 Survivable 分支设备，或使用分支站点的网关或 SIP 中继部署 Survivable 分支服务器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

