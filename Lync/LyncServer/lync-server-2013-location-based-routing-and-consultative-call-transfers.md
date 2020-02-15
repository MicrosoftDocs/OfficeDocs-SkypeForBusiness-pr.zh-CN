---
title: Lync Server 2013：基于位置的路由和咨询呼叫转移
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a72ddbba79bf0de777c8567164475ab573d09a2c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a>Lync Server 2013 中的基于位置的路由和咨询呼叫转移

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-07-31_

除了强制对 Lync 会议进行基于位置的路由，基于位置的路由会议应用程序还强制对 PSTN 终结点传出的咨询呼叫转移基于位置的路由限制。 咨询呼叫转接是在双方将呼叫转移到新用户之间建立的呼叫。 例如，PSTN 终结点呼叫用户 A （Lync 被呼叫者）。 用户 A 确定应将 PSTN 用户转发到用户 B （Lync 用户）。 用户 A 将呼叫与 PSTN 用户置于保留状态，并呼叫用户 B。用户 B 同意与 PSTN 用户对话。 用户 A 将呼叫（保留）转移到用户 B。

**咨询呼叫转接呼叫流**

![会议图的基于位置的路由](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "会议图的基于位置的路由")

当启用基于位置的路由的用户启动 PSTN 终结点的咨询呼叫转移（如上图所示）时，这将创建两个活动呼叫、PSTN 用户和 Lync 用户 A 之间的一个呼叫，以及 Lync 用户 A 和 Lync 用户 B 之间的一个呼叫。基于位置的路由会议应用程序强制执行以下行为：

  - 如果对 PSTN 呼叫的 SIP 中继路由有权将 PSTN 呼叫重新路由到网络站点（Lync 用户 B （即传输目标）所在的网络站点），则将允许呼叫转移;否则，将阻止咨询呼叫转移。 此授权根据被转移方在与将活动呼叫路由到 PSTN 终结点的 SIP 中继位于同一网络站点中的位置进行。

  - 如果 SIP 中继路由未授权入站 PSTN 呼叫将呼叫路由到传输方（Lync 用户 B）所在的网络站点，或者转移方位于未知网络站点中，则咨询呼叫转移到 PSTN将阻止终结点（例如，呼叫转移目标）。

下表介绍基于位置的路由会议应用程序如何应用基于位置的路由限制以进行咨询呼叫转移。 虽然 PBX 终结点不与网络站点直接关联，但 PBX 的 SIP 中继可分配给网络站点。 因此，PBX 终结点可以与网络站点间接关联。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>呼叫转移方的网络站点</p></td>
<td><p>呼叫转接目标的网络站点</p></td>
<td><p>行为</p></td>
</tr>
<tr class="even">
<td><p>PSTN 终结点</p></td>
<td><p>同一网络站点中的 Lync 用户（例如，站点1）</p></td>
<td><p>将允许咨询转移</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 终结点</p></td>
<td><p>不同网络站点中的 Lync 用户（即 site 2）</p></td>
<td><p>将不允许咨询转移</p></td>
</tr>
<tr class="even">
<td><p>PSTN 终结点</p></td>
<td><p>未知网络站点中的 Lync 用户</p></td>
<td><p>将不允许咨询转移</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 终结点</p></td>
<td><p>联合 Lync 用户</p></td>
<td><p>将不允许咨询转移</p></td>
</tr>
<tr class="even">
<td><p>PSTN 终结点</p></td>
<td><p>同一站点中的 PBX 终结点（例如，site 1）</p></td>
<td><p>将允许咨询转移</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 终结点</p></td>
<td><p>不同站点中的 PBX 终结点（即 site 2）</p></td>
<td><p>将不允许咨询转移</p></td>
</tr>
<tr class="even">
<td><p>同一站点中的 PBX 终结点（例如，site 1）</p></td>
<td><p>PSTN 终结点</p></td>
<td><p>将允许咨询转移</p></td>
</tr>
<tr class="odd">
<td><p>不同站点中的 PBX 终结点（即 site 2）</p></td>
<td><p>PSTN 终结点</p></td>
<td><p>将不允许咨询转移</p></td>
</tr>
<tr class="even">
<td><p>任何站点中的 PBX 终结点</p></td>
<td><p>同一网络站点中的 Lync 用户（例如，站点1）</p></td>
<td><p>将允许咨询转移</p></td>
</tr>
<tr class="odd">
<td><p>任何站点中的 PBX 终结点</p></td>
<td><p>不同网络站点中的 Lync 用户（即 site 2）</p></td>
<td><p>将允许咨询转移</p></td>
</tr>
<tr class="even">
<td><p>任何站点中的 PBX 终结点</p></td>
<td><p>未知网络站点中的 Lync 用户</p></td>
<td><p>将允许咨询转移</p></td>
</tr>
<tr class="odd">
<td><p>任何站点中的 PBX 终结点</p></td>
<td><p>联合 Lync 用户</p></td>
<td><p>将允许咨询转移</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

