---
title: Lync Server 2013：会议的 Location-Based 路由概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dd3508221babdd9c503e21d5662a1bbe60d4ce0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520949"
---
# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的会议 Location-Based 路由概述

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-07-19_

Location-Based 路由会议应用程序为 Lync 会议提供了阻止 PSTN 收费旁路的机制。 该应用程序监视活动会议，并根据所参与的 Lync 用户的位置强制实施 Location-Based 路由限制。

如果满足以下条件，则 Location-Based 路由会议应用程序将确定是否在 Lync 会议上强制执行 Location-Based 路由：

  - 会议组织者已启用 Location-Based 路由。 Location-Based 路由限制将仅应用于由启用 Location-Based 路由的用户组织的会议。

  - 至少有一个会议参与者是 PSTN 终结点。 Location-Based 路由限制仅适用于包含 PSTN 终结点的会议。

  - PSTN 网关用于将会议桥接到 PSTN 的网络站点，以及组织者和参与者从中连接的网络站点。

Location-Based 路由会议应用程序阻止将 Lync 用户和 PSTN 终结点从不同的网络站点加入同一会议。 如果为 Location-Based 的路由启用了会议的组织者，会议应用程序将强制实施以下限制：

  - 可以加入 Lync 会议的终结点取决于已加入会议的终结点，并且此限制将根据联接的终结点保留，并将新的终结点加入会议进行调整。 如果组织者和参与者从同一个网络站点加入 Lync 会议，则来自同一网络站点的另一个参与者、来自不同网络站点的另一个参与者或来自未知网络站点的参与者允许加入。

  - 如果组织者和参与者从不同或未知网络站点加入会议，则不允许 PSTN 终结点加入会议（如果 PSTN 呼叫 ingresses 来自 SIP 中继为 Location-Based 路由而启用）。

  - 如果组织者和参与者都从同一个网络站点加入会议，并且有参与者加入来自 PSTN 的同一会议，则不允许来自不同网络站点的 Lync 终结点加入会议。

下表汇总了这些会议 Location-Based 路由限制。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>在任意给定点的会议中，用户 (s) </p></td>
<td><p>用户 (s) 允许加入会议</p></td>
<td><p>用户 (s) 不允许加入会议</p></td>
</tr>
<tr class="even">
<td><p>从单个网络站点) Lync VoIP 客户端用户 (s</p></td>
<td><p>来自相同网络站点的 Lync VoIP 客户端用户</p>
<p>来自不同网络站点的 Lync VoIP 客户端用户</p>
<p>来自未知网络站点的 Lync VoIP 客户端用户</p>
<p>联合 Lync VoIP 客户端用户</p>
<p>从 PSTN 终结点加入的用户</p></td>
<td><p>无</p></td>
</tr>
<tr class="odd">
<td><p>来自未知网络站点的 Lync VoIP 客户端用户 (s) </p></td>
<td><p>来自任何网站的 Lync VoIP 客户端用户</p>
<p>来自未知网站的 Lync VoIP 客户端用户</p>
<p>联合 Lync VoIP 客户端用户</p></td>
<td><p>通过 PSTN 终结点加入的用户</p></td>
</tr>
<tr class="even">
<td><p>来自不同网络站点的 Lync VoIP 客户端用户</p></td>
<td><p>来自任何网络站点的 Lync VoIP 客户端用户</p>
<p>来自未知网络站点的 Lync VoIP 客户端用户</p>
<p>联合 Lync VoIP 客户端用户</p></td>
<td><p>通过 PSTN 终结点加入的用户</p></td>
</tr>
<tr class="odd">
<td><p>Lync VoIP 客户端用户 (s) 从单个网络站点和从 PSTN 终结点加入的用户</p></td>
<td><p>来自相同网络站点的 Lync VoIP 客户端用户</p></td>
<td><p>来自不同网络站点的 Lync VoIP 客户端用户</p>
<p>来自未知网络站点的 Lync VoIP 客户端用户</p>
<p>联合 Lync VoIP 客户端用户</p></td>
</tr>
</tbody>
</table>


以下是 Location-Based 路由会议应用程序的其他特征：

  - 如果不允许用户加入给定 Location-Based 路由限制的会议，则对会议的用户呼叫将被拒绝，并且他的 Lync 客户端将报告呼叫未完成或已结束。

  - 如果终结点通过未启用 Location-Based 路由的中继进行连接，则不限制加入加入会议的 Location-Based 路由之后的 PSTN 终结点。

  - 通过 SIP 中继连接到 Mediations 服务器的 PBX 系统不会对 PSTN 进行传出呼叫，这将与在定义 SIP 中继的同一网络站点中的 Lync 用户具有相同的之后。 例如，PSTN 终结点将能够通过 PBX 用户和 Lync 用户加入会议（如果它们位于同一网络站点中）;否则，如果 PBX 用户位于与 Lync 用户不同的网络站点中，则不允许 PSTN 终结点加入会议。

</div>

<span> </span>

</div>

</div>

</div>

