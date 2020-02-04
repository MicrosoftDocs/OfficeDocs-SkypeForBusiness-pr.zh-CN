---
title: Lync Server 2013：针对会议基于位置的路由的概述
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
ms.openlocfilehash: adb103d1f2314e033d9ef0958dd05a7648012bde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的会议基于位置的路由概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-07-19_

基于位置的路由会议应用程序向 Lync 会议提供阻止 PSTN 免费旁路的机制。 该应用程序监控活动会议，并根据参与的 Lync 用户的位置强制实施基于位置的路由限制。

基于位置的路由会议应用程序确定如果满足以下条件，是否在 Lync 会议上强制执行基于位置的路由：

  - 会议组织者已启用基于位置的路由。 基于位置的路由限制将仅应用于启用了基于位置的路由的用户组织的会议。

  - PSTN 终结点中至少有一名会议参与者。 基于位置的路由限制仅适用于包含 PSTN 终结点的会议。

  - 用于将会议桥接到 PSTN 的 PSTN 网关所在的网络站点以及组织者和参与者用于从中连接的网络站点。

基于位置的路由会议应用程序可防止将 Lync 用户和 PSTN 终结点从不同的网络站点加入到同一会议。 如果为基于位置的路由启用了会议组织者，则会议应用程序会强制执行以下限制：

  - 可以加入 Lync 会议的终结点取决于已加入会议的终结点，并且此限制会调整为联接终结点，并将新终结点加入会议。 如果组织者和参与者从同一网络网站加入 Lync 会议，则 PSTN 终结点、同一网络网站中的另一个参与者、来自不同网络网站的另一个参与者或来自未知网络网站的参与者允许参加.

  - 如果组织者和参与者从不同或未知的网络站点加入会议，则如果 PSTN 呼叫从启用了基于位置的路由的 SIP 中继传入，将不允许 PSTN 终结点加入会议。

  - 如果组织者和参与者都从同一网络网站加入会议，并且有参与者加入来自 PSTN 的同一会议，则不允许来自其他网络网站的 Lync 终结点加入会议。

下表汇总了这些基于会议位置的路由限制。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>任意时间点处于会议中的用户</p></td>
<td><p>允许加入会议的用户</p></td>
<td><p>不允许加入会议的用户</p></td>
</tr>
<tr class="even">
<td><p>来自单个网络网站的 Lync VoIP 客户端用户</p></td>
<td><p>来自同一网络网站的 Lync VoIP 客户端用户</p>
<p>来自不同网络网站的 Lync VoIP 客户端用户</p>
<p>来自未知网络网站的 Lync VoIP 客户端用户</p>
<p>联合 Lync VoIP 客户端用户</p>
<p>从 PSTN 终结点加入的用户</p></td>
<td><p>无</p></td>
</tr>
<tr class="odd">
<td><p>来自未知网络网站的 Lync VoIP 客户端用户</p></td>
<td><p>任何网站中的 Lync VoIP 客户端用户</p>
<p>来自未知网站的 Lync VoIP 客户端用户</p>
<p>联合 Lync VoIP 客户端用户</p></td>
<td><p>通过 PSTN 终结点加入的用户</p></td>
</tr>
<tr class="even">
<td><p>来自不同网络站点的 Lync VoIP 客户端用户</p></td>
<td><p>来自任何网络网站的 Lync VoIP 客户端用户</p>
<p>来自未知网络网站的 Lync VoIP 客户端用户</p>
<p>联合 Lync VoIP 客户端用户</p></td>
<td><p>通过 PSTN 终结点加入的用户</p></td>
</tr>
<tr class="odd">
<td><p>从单个网络站点和从 PSTN 终结点加入的用户的 Lync VoIP 客户端用户</p></td>
<td><p>来自同一网络网站的 Lync VoIP 客户端用户</p></td>
<td><p>来自不同网络网站的 Lync VoIP 客户端用户</p>
<p>来自未知网络网站的 Lync VoIP 客户端用户</p>
<p>联合 Lync VoIP 客户端用户</p></td>
</tr>
</tbody>
</table>


以下是基于位置的路由会议应用程序的其他特征：

  - 当用户在给定基于位置的路由限制的情况下，不允许用户加入会议时，对会议的用户呼叫将被拒绝，并且他的 Lync 客户端将报告呼叫未完成或已结束。

  - 使用基于位置的路由 enforcements 加入会议的 PSTN 终结点不会受到限制，即使终结点通过不支持基于位置的路由的主干进行联接，也不会限制加入会议的状态。

  - 通过 SIP 主干连接到 Mediations 服务器的 PBX 系统不会对 PSTN 进行传出调用，其 enforcements 与在定义 SIP 主干的同一网络站点中的 Lync 用户具有相同的。 例如，PSTN 终结点将能够使用 PBX 用户和 Lync 用户加入会议（如果它们位于同一网络网站中）;否则，如果 PBX 用户与 Lync 用户位于不同的网络站点，则不允许 PSTN 终结点加入会议。

</div>

<span> </span>

</div>

</div>

</div>

