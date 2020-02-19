---
title: Lync Server 2013：针对基于位置的路由的客户端和服务器支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d78ae3fcfe9bd834fbddced1bdeccc20be45481
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a>在 Lync Server 2013 中对基于位置的路由的客户端和服务器支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-06-18_

基于位置的路由由 Lync Server 强制实施。 Lync Server 可以标识用户从公司网络中连接的网络站点。 由于远程用户位于企业网络外部，因此其位置被视为未知。

<div>

## <a name="lync-server-support"></a>Lync Server 支持

基于位置的路由要求在给定拓扑中的所有前端池和 Standard Edition 服务器上部署 Lync Server 2013 CU1。 如果未在拓扑中的某些 Lync 组件上安装 Lync Server 2013 CU1，则不能完全强制实施基于位置的路由限制。

下表标识了服务器角色和支持的基于位置的路由的版本组合。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>池版本</th>
<th>中介服务器版本</th>
<th>支持</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 二月2013累积更新</p></td>
<td><p>Lync Server 2013 二月2013累积更新</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 二月2013累积更新</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 二月2013累积更新</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 二月2013累积更新</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>任意</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>任意</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>任意</p></td>
<td><p>否</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a>Lync 客户端支持

下表标识了基于位置的路由支持的客户端。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>客户端类型</th>
<th>支持</th>
<th>详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>是</p></td>
<td><p>包括 Lync 2013 二月2013累积更新</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>是</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>否</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>是</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync 助理</p></td>
<td><p>是</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>适用于 Windows 8 的 Lync</p></td>
<td><p>否</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Mobile 2013</p></td>
<td><p>否</p></td>
<td><p>如果启用了基于位置的路由的用户使用，则必须对 Lync Mobile 2013 客户端禁用 VoIP。</p></td>
</tr>
<tr class="even">
<td><p>Lync Mobile 2010</p></td>
<td><p>是</p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> 若要对 Lync Mobile 2013 客户端禁用 VoIP，请为启用了基于位置的路由的所有用户的设置（IP 音频/视频）分配移动策略。 有关移动策略的更多详细信息，请参阅<A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">set-csmobilitypolicy</A>。



</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划基于位置的路由](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

