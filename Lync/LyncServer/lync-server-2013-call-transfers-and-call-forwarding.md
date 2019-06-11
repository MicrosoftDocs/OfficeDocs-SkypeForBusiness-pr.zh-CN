---
title: Lync Server 2013：呼叫转移和呼叫转接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d5b0661cfaaef2e514f070260f44abc4ea00572
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a>Lync Server 2013 中的呼叫转移和呼叫转接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-03-09_

当涉及 PSTN 终结点时, 基于位置的路由会分析 calle 终结点的位置以及呼叫将被转移或转发到的终结点 (例如, 传输/转发目标)。 基于位置的路由确定是否应根据两个终结点的位置来转移或转发呼叫。

下表说明了使用 PSTN 终结点的呼叫中 Lync 用户的方案, 以及 Lync 用户将呼叫转移到另一个 Lync 用户。 根据 transferee 终结点的网络站点位置, 基于位置的路由会影响呼叫转移或转发的路由。

### <a name="initiating-call-transfer-or-forward"></a>发起呼叫转接

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>发起呼叫转接的用户</th>
<th>目标终结点位于与发起呼叫转接的用户相同的网络站点中</th>
<th>目标终结点位于与发起呼叫转接的用户不同的网络站点中</th>
<th>目标终结点位于未知的网络网站中, 或者没有为基于位置的路由启用网络网站</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 用户</p></td>
<td><p>允许呼叫转接</p></td>
<td><p>不允许呼叫转接</p></td>
<td><p>不允许呼叫转接</p></td>
</tr>
</tbody>
</table>

  

例如: 使用 PSTN 终结点进行呼叫的 Lync 用户将呼叫转移到位于同一网络站点中的另一个 Lync 用户。 在这种情况下，允许进行呼叫转接。

下表说明了使用另一个 Lync 用户的呼叫中 Lync 用户的方案, 其中一个用户将呼叫转移到 PSTN 终结点。 根据呼叫转接至的用户的位置，表格详细介绍了基于位置的路由如何影响呼叫。

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a>呼叫转接至 PSTN 终结点

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>呼叫转接终结点目标</th>
<th>同一网络网站中的 Lync 用户</th>
<th>不同网络站点中的 Lync 用户</th>
<th>在未知网络网站或网络网站中的一个或两个 Lync 用户未启用基于位置的路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 终结点</p></td>
<td><p>转接用户的站点语音路由策略允许呼叫转接</p></td>
<td><p>转接用户的站点语音路由策略允许呼叫转接</p></td>
<td><p>转接用户的语音策略仅允许通过未启用基于位置的路由的中继进行呼叫转接</p></td>
</tr>
</tbody>
</table>

  
例如: 与同一网络站点中的另一个 Lync 用户进行的呼叫中的 Lync 用户将呼叫转移到 PSTN 终结点, 并允许呼叫转移。

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中基于位置的路由的方案](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

