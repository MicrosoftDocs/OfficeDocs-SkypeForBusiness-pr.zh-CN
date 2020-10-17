---
title: Lync Server 2013：同时响铃
description: Lync Server 2013：同时响铃。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 595c8c1d4ce105e2189002f18733ffae92cff8bf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555658"
---
# <a name="simultaneous-ringing-in-lync-server-2013"></a>Lync Server 2013 中的同时响铃

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-09_

当呼叫方启用同时响铃时，Location-Based 路由将分析呼叫方的位置和被叫方的终结点，以确定是否应路由呼叫。

下表说明了配置了同时响铃的用户，同时响铃目标是同一网络站点、不同网络站点或未知网络站点中的用户。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>的传入 PSTN 呼叫</th>
<th>位于与被呼叫方相同的网络站点中</th>
<th>位于与被呼叫者不同的网络站点中</th>
<th>位于未知网络站点中，或者未启用 Location-Based 路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 用户</p></td>
<td><p>允许同时振铃</p></td>
<td><p>不允许同时振铃</p></td>
<td><p>不允许同时振铃</p></td>
</tr>
</tbody>
</table>

  
下表说明了 Lync 用户 (的呼叫，例如，Lync 呼叫者) 在同一网络站点、不同网络站点或未知网络站点中。 被叫方有一个 PSTN 终结点 (即手机) 配置为同时振铃目标。 在这种情况下，Location-Based 路由将确定是否应将呼叫路由到 "同时环" 目标 (（即被叫方的手机) ）。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>同时振铃目标</th>
<th>位于与被呼叫方相同的网络站点中</th>
<th>位于与被呼叫者不同的网络站点中</th>
<th>位于未知网络站点中，或者未启用 Location-Based 路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 终结点</p></td>
<td><p>通过呼叫者的站点语音路由策略允许同时响铃</p></td>
<td><p>通过呼叫者的站点语音路由策略允许同时响铃</p></td>
<td><p>允许通过呼叫者的语音策略同时振铃到中继不启用 Location-Based 路由的情况</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中 Location-Based 路由的方案](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

