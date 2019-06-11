---
title: Lync Server 2013：基于位置的路由的部署过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 108dd35c7f184c974a317f68901c94bc81e9e403
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 中基于位置的路由的部署过程

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-03-09_

本主题概述了配置基于位置的路由所涉及的过程。 在配置基于位置的路由之前, 必须部署 Lync Server Enterprise Edition 或标准版和企业版语音。 部署企业语音时, 已安装并启用基于位置的路由所需的组件。

### <a name="location-based-routing-deployment-process"></a>基于位置的路由部署过程

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>阶段</th>
<th>步骤</th>
<th>所需的组和角色</th>
<th>部署文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>部署企业语音</p></td>
<td><ul>
<li><p>配置中继</p></li>
<li><p>创建语音策略</p></li>
<li><p>定义语音路由</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>部署企业语音</p></td>
</tr>
<tr class="even">
<td><p>验证您的企业语音部署</p></td>
<td></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>配置网络区域、网站和子网</p></td>
<td><ul>
<li><p>创建网络区域</p></li>
<li><p>创建网络网站</p></li>
<li><p>将子网与网络站点关联</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>关于网络区域、站点和子网<br />
创建或修改网络区域<br />
创建或修改网络网站<br />
将子网与网络站点关联</p></td>
</tr>
<tr class="even">
<td><p>配置基于位置的路由</p></td>
<td><ul>
<li><p>创建语音路由策略</p></li>
<li><p>为每个主干定义单独的中继配置</p></li>
<li><p>修改语音策略</p></li>
<li><p>启用基于位置的路由配置</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a>示例部署

以下部署用于进一步演示基于位置的路由启用的机制。

![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")

<div>

## <a name="incoming-pstn-calls"></a>拨入 PSTN 呼叫

管理员可以启用定义以将呼叫路由到 "Site 1 网关" 以查找基于位置的路由, 并将 "站点1网关" 与站点1相关联。 一旦启用, 通过 "站点1网关" 路由的呼叫将仅路由到位于站点1中的用户。 所有呼叫均通过 "站点1网关" 主干发送到其他网站中的用户, 例如 "网站 2" 将被阻止以防止 PSTN 免绕过。

所有通过 "站点1网关" 拨入的 PSTN 呼叫仅允许路由到位于站点1中的终结点。 例如, 当 "Lync 用户 1" 传播到站点2时, 所有通过 "站点1网关" 传入的 PSTN 呼叫将不会被路由到位于站点2中的 "Lync 用户 1" 终结点。 如果 "Lync 用户 1" 传播到无法确定用户位置的未知网络网站, 则会应用相同的路由规则。

下表概述了在此上下文中 "Lync 用户 1" 的用户体验。


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
<th>Lync 用户1位于网络站点1中的终结点</th>
<th>Lync 用户1位于网络站点2中的终结点</th>
<th>位于未知网络网站中的 Lync 用户1终结点</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>对 Lync 用户1的入站 PSTN 呼叫</p></td>
<td><p>呼叫将路由到此位置中的终结点</p></td>
<td><p>调用未路由到此位置中的终结点</p></td>
<td><p>调用未路由到此位置中的终结点</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a>出局 PSTN 呼叫

语音路由以直接分配给用户的语音策略以及分配给网络站点的语音路由策略引用。 这两个策略都包含对路由的引用, 可用于以不同的方式路由通话。 例如, 管理员可以为位于 network 1 中的所有用户定义一个语音路由策略, 以便通过 "Site 1 网关" 路由所有出站呼叫, 而某些用户的语音策略定义了通过 "Site 2 网关" 进行的所有出站呼叫的路由。 虽然这些用户位于网络站点1中, 但其出站呼叫将通过 "站点1网关" 传送。

当用户位于为基于位置的路由配置的网络网站中时, 网络网站的语音路由策略路由将覆盖用户的语音策略路由。 此规则对于临时移动到其他网站的用户尤其有用。 在此特定情况下, 用户将始终使用本地到其位置的网关;如果 "Lync 用户 3" 位于 "Site 2" 中, 则其所有出站呼叫将通过 "Site 2 网关" 路由, 但如果他向站点1传播, 则在站点1处发出的所有出站呼叫将通过 "站点1网关" 进行路由。

下表说明了 Lync 用户1从以下网络站点发出出站呼叫的用户体验。


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
<th>网络站点1</th>
<th>网络站点2</th>
<th>未知网络网站或未启用基于位置的路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>出站呼叫授权</p></td>
<td><p>Lync 用户1语音策略</p></td>
<td><p>Lync 用户1语音策略</p></td>
<td><p>Lync 用户1语音策略</p></td>
</tr>
<tr class="even">
<td><p>传出呼叫的路由</p></td>
<td><p>站点1语音路由策略</p></td>
<td><p>站点2语音路由策略</p></td>
<td><p>用户的语音策略, 并且仅适用于不支持基于位置的路由的系统</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a>呼叫转移和转发

当转接或转发呼叫时, 呼叫的路由受基于位置的路由影响。

下表描述了 Lync 用户1将 PSTN 呼叫转移或转发给另一个 Lync 用户的情况。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>用户启动呼叫转移或转发</th>
<th>Lync 用户2</th>
<th>Lync 用户4</th>
<th>没有为基于位置的路由启用网络站点中的 Lync 用户</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 用户1</p></td>
<td><p>允许呼叫转接</p></td>
<td><p>不允许呼叫转接</p></td>
<td><p>不允许呼叫转接</p></td>
</tr>
</tbody>
</table>

  
下表说明了基于位置的路由如何根据正在传输到 PSTN 终结点的 Lync 用户的位置 (Lync 用户2、Lync 用户4等) 来影响呼叫的路由方式


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>呼叫转移或转发到的终结点</th>
<th>Lync 用户2</th>
<th>Lync 用户4</th>
<th>没有为基于位置的路由启用网络站点中的 Lync 用户</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 终结点</p></td>
<td><p>呼叫转移或转移通过站点1的 "语音路由策略" 和 "通过站点1网关的外出" 传送</p></td>
<td><p>呼叫转移或转移通过站点2的 "语音路由策略" 和 "站点 2" 网关的外出进行路由</p></td>
<td><p>呼叫转移或转移通过 Lync 用户语音策略进行路由, 并通过不支持基于位置的路由的网关进行传出 (如果可用)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a>同时响铃

在示例拓扑中配置基于位置的路由后, 将强制执行以下交互。

下表说明了基于位置的路由是否允许不同 Lync 用户同时拨打 (如 Lync 用户2、Lync 用户4等)。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>打入的 PSTN 呼叫目标</th>
<th>Lync 用户2</th>
<th>Lync 用户4</th>
<th>没有为基于位置的路由启用网络站点中的 Lync 用户</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 用户1</p></td>
<td><p>允许同时拨打</p></td>
<td><p>不允许同时拨打</p></td>
<td><p>不允许同时拨打</p></td>
</tr>
</tbody>
</table>

  
下表说明了基于位置的路由是否允许来自不同 Lync 用户 (即 Lync 用户2、Lync 用户4等) 的 PSTN 终结点同时拨打 PSTN 终结点。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>同时响铃目标</th>
<th>Lync 用户2</th>
<th>Lync 用户4</th>
<th>没有为基于位置的路由启用网络站点中的 Lync 用户</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 用户1移动电话 (PSTN 终结点)</p></td>
<td><p>通过网络站点1的语音路由策略和通过站点1网关传出的呼叫进行路由</p></td>
<td><p>通过网络站点2的语音路由策略和通过站点2网关传出的呼叫进行路由</p></td>
<td><p>呼叫通过呼叫者语音政策路由, 并且将通过不支持基于位置的路由的 PSTN 网关外出</p></td>
</tr>
</tbody>
</table>


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

