---
title: Lync Server 2013：传出呼叫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a353cecbf1cdc1ff411c2cfe7c57edcd909c5c8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a>Lync Server 2013 中的传出呼叫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-03-09_

对启用了基于位置的路由的用户的出站呼叫的路由受用户终结点的网络位置的影响。 下表说明了基于位置的路由如何影响出站呼叫路由，具体取决于呼叫者终结点的位置。

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a>向 PSTN 发出出站呼叫的呼叫者

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>位于启用了基于位置的路由的网络站点中的用户终结点</th>
<th>位于未知网络站点或者未启用基于位置的路由的网络站点中的用户终结点</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>出站呼叫授权</p></td>
<td><p>基于用户的语音策略授权呼叫</p></td>
<td><p>基于用户的语音策略授权呼叫</p></td>
</tr>
<tr class="even">
<td><p>出站呼叫路由</p></td>
<td><p>根据网络站点的语音路由策略路由呼叫</p></td>
<td><p>根据用户的语音策略仅通过未启用基于位置的路由的中继路由呼叫（如果可用）</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中基于位置的路由的方案](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

