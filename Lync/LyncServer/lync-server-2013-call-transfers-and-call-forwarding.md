---
title: Lync Server 2013：呼叫转移和呼叫转接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de2d258b5820c95b346c76fb5ee7e47e9749c617
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a>Lync Server 2013 中的呼叫转移和呼叫转接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-09_

当涉及 PSTN 终结点时，基于位置的路由将分析 calle 终结点的位置和呼叫将被转移到的终结点（例如，传输/转发目标）。 基于位置的路由根据两个终结点的位置确定是否应转移或转发呼叫。

下表说明了使用 PSTN 终结点的呼叫中 Lync 用户的方案，并且 Lync 用户将呼叫转移到另一个 Lync 用户。 根据受让方的终结点的网络站点位置，基于位置的路由会影响呼叫转移或转发的路由。

### <a name="initiating-call-transfer-or-forward"></a>启动呼叫转移或转发

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>用户启动呼叫转接/转发</th>
<th>目标终结点位于与启动呼叫转移或转发的用户相同的网络站点中</th>
<th>目标终结点位于不同的网络站点中，以供用户初始化呼叫转移或转发</th>
<th>目标终结点位于未知网络站点或未启用基于位置的路由的网络站点</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 用户</p></td>
<td><p>允许呼叫转接或转接</p></td>
<td><p>不允许呼叫转接或转接</p></td>
<td><p>不允许呼叫转接或转接</p></td>
</tr>
</tbody>
</table>

  

例如：具有 PSTN 终结点的呼叫中的 Lync 用户将呼叫转移到位于同一网络站点中的另一个 Lync 用户。 在这种情况下，允许呼叫转移。

下表说明了使用其他 Lync 用户的呼叫中 Lync 用户的方案，其中一个用户将呼叫转移到 PSTN 终结点。 根据将呼叫转接到的用户的位置，此表详细介绍了基于位置的路由对呼叫的影响。

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a>呼叫转移或转发到 PSTN 终结点

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>呼叫转接/转发终结点目标</th>
<th>同一网络站点中的 Lync 用户</th>
<th>不同网络站点中的 Lync 用户</th>
<th>未知网络站点中的一个或两个 Lync 用户或未启用基于位置的路由的网络站点</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 终结点</p></td>
<td><p>转接用户的站点语音路由策略允许呼叫转接或转接</p></td>
<td><p>转接用户的站点语音路由策略允许呼叫转接或转接</p></td>
<td><p>转接用户的语音策略仅允许通过未启用基于位置的路由的中继进行呼叫转接或转移</p></td>
</tr>
</tbody>
</table>

  
例如：呼叫中具有同一网络站点中另一个 Lync 用户的 Lync 用户将呼叫转移到 PSTN 终结点，并允许呼叫转移。

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中基于位置的路由的方案](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

