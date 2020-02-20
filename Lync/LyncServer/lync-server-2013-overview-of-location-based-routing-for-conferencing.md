---
title: Lync Server 2013：会议的基于位置的路由概述
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
ms.openlocfilehash: 863cd213fb28d3adeedc04a5d46e4310ea4cd83b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的会议基于位置的路由概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-07-19_

基于位置的路由会议应用程序为 Lync 会议提供了阻止 PSTN 收费旁路的机制。 该应用程序监视活动会议，并根据所参与的 Lync 用户的位置强制实施基于位置的路由限制。

如果满足以下条件，则基于位置的路由会议应用程序将确定是否在 Lync 会议上强制实施基于位置的路由：

  - 会议组织者启用了基于位置的路由。 基于位置的路由限制将仅应用于由启用了基于位置的路由的用户组织的会议。

  - 至少有一个会议参与者是 PSTN 终结点。 基于位置的路由限制仅适用于包含 PSTN 终结点的会议。

  - PSTN 网关用于将会议桥接到 PSTN 的网络站点，以及组织者和参与者从中连接的网络站点。

基于位置的路由会议应用程序阻止将 Lync 用户和 PSTN 终结点从不同的网络站点加入同一会议。 如果为会议的组织者启用了基于位置的路由，会议应用程序将强制实施以下限制：

  - 可以加入 Lync 会议的终结点取决于已加入会议的终结点，并且此限制将根据联接的终结点保留，并将新的终结点加入会议进行调整。 如果组织者和参与者从同一个网络站点加入 Lync 会议，则来自同一网络站点的另一个参与者、来自不同网络站点的另一个参与者或来自未知网络站点的参与者允许加入.

  - 如果组织者和参与者从不同或未知网络站点加入会议，则不允许 PSTN 终结点加入会议（如果 PSTN 呼叫 ingresses 来自 SIP 中继启用基于位置的路由）。

  - 如果组织者和参与者都从同一个网络站点加入会议，并且有参与者加入来自 PSTN 的同一会议，则不允许来自不同网络站点的 Lync 终结点加入会议。

下表汇总了这些基于会议位置的路由限制。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>在任意给定时刻会议中的用户</p></td>
<td><p>允许加入会议的用户</p></td>
<td><p>不允许用户加入会议</p></td>
</tr>
<tr class="even">
<td><p>来自单个网络站点的 Lync VoIP 客户端用户</p></td>
<td><p>来自相同网络站点的 Lync VoIP 客户端用户</p>
<p>来自不同网络站点的 Lync VoIP 客户端用户</p>
<p>来自未知网络站点的 Lync VoIP 客户端用户</p>
<p>联合 Lync VoIP 客户端用户</p>
<p>从 PSTN 终结点加入的用户</p></td>
<td><p>无</p></td>
</tr>
<tr class="odd">
<td><p>来自未知网络站点的 Lync VoIP 客户端用户</p></td>
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
<td><p>来自单个网络站点的 Lync VoIP 客户端用户和从 PSTN 终结点加入的用户</p></td>
<td><p>来自相同网络站点的 Lync VoIP 客户端用户</p></td>
<td><p>来自不同网络站点的 Lync VoIP 客户端用户</p>
<p>来自未知网络站点的 Lync VoIP 客户端用户</p>
<p>联合 Lync VoIP 客户端用户</p></td>
</tr>
</tbody>
</table>


以下是基于位置的路由会议应用程序的其他特征：

  - 如果不允许用户加入会议给定的基于位置的路由限制，则对会议的用户呼叫将被拒绝，并且他的 Lync 客户端将报告呼叫未完成或已结束。

  - 使用基于位置的路由之后加入会议的 PSTN 终结点如果终结点通过未启用基于位置的路由的中继进行联接，则不会限制加入会议的会议。

  - 通过 SIP 中继连接到 Mediations 服务器的 PBX 系统不会对 PSTN 进行传出呼叫，这将与在定义 SIP 中继的同一网络站点中的 Lync 用户具有相同的之后。 例如，PSTN 终结点将能够通过 PBX 用户和 Lync 用户加入会议（如果它们位于同一网络站点中）;否则，如果 PBX 用户位于与 Lync 用户不同的网络站点中，则不允许 PSTN 终结点加入会议。

</div>

<span> </span>

</div>

</div>

</div>

