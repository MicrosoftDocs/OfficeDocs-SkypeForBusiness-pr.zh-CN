---
title: Lync Server 2013：传入呼叫
description: Lync Server 2013：传入呼叫。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a72c7fc378240f9751eae8e6c24e9cc601b08d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547728"
---
# <a name="incoming-calls-in-lync-server-2013"></a>Lync Server 2013 中的传入呼叫

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-09_

为 Location-Based 路由启用的用户传入呼叫的路由取决于用户终结点的位置。 传入呼叫的路由通过以下方式受到影响。 如果用户对位于启用了 Location-Based 路由网络站点中的终结点的传入呼叫，并且终结点位于与 PSTN 网关相同的网络站点中，则将路由该呼叫。 如果用户对位于启用了 Location-Based 路由的网络站点中的终结点的传入呼叫，并且终结点位于与 PSTN 网关不同的网络站点中，则不会路由该呼叫。 当用户没有与传入呼叫来自的 PSTN 网关位于同一网络站点中的终结点时，传入呼叫将直接路由到用户的语音邮件，并且未接来电通知将发送给被叫方。

为 Location-Based 路由启用的用户的呼叫转接设置将继续强制实施，但转发的呼叫将受到用户 Location-Based 路由限制的约束。

下表说明了 Location-Based 路由如何影响入站呼叫的路由，具体取决于被叫方的终结点的位置。 PSTN 网关的网络站点已启用 Location-Based 路由，Location-Based 路由仅允许将 PSTN 呼叫路由到同一网络站点中的终结点。

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a>被呼叫者从 PSTN 接收入站呼叫

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>被呼叫方的终结点位于与 PSTN 网关相同的网络站点中</th>
<th>被叫方的终结点不与 PSTN 网关位于同一网络站点中</th>
<th>被呼叫者的终结点位于未知网络站点中，或者未启用 Location-Based 路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>传入 PSTN 呼叫的路由</p></td>
<td><p>传入呼叫路由到被呼叫者的终结点</p></td>
<td><p>传入呼叫未路由到被呼叫者的终结点</p></td>
<td><p>传入呼叫未路由到被呼叫者的终结点</p></td>
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

