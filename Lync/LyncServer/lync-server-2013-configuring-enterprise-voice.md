---
title: 'Lync Server 2013: 配置企业语音'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e46bd64efd8aa2eb6e1aead17083aa8593c8544
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a>在 Lync Server 2013 中配置企业语音

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-03-12_

若要部署企业语音, 需要配置下列内容:

  - 创建主干

  - 定义语音策略

  - 定义语音路线

  - Enable Users for Enterprise Voice

<div>

## <a name="create-a-trunk"></a>创建主干

您必须在您的企业语音部署中定义中继。 对于基于位置的路由, 必须为每个主干创建中继配置。 使用 Lync Server 拓扑生成器定义你的中继, 并使用 Lync Server Windows PowerShell 命令、新 New-cstrunkconfiguration 或 Lync Server 控制面板定义相应的 trunk 配置。 有关如何在中继配置上启用基于位置的路由的详细信息, 请参阅本部分中的 "在[Lync Server 2013 中启用基于位置的路由](lync-server-2013-enabling-location-based-routing.md)" 中继中的 "基于位置的路由"。 对于此示例, 下表介绍了此方案中使用的中继。

有关详细信息, 请参阅[在 Lync Server 2013 的拓扑生成器中定义其他中继](lync-server-2013-define-additional-trunks-in-topology-builder.md)。


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>主干名称</th>
<th>系统类型</th>
<th>名称</th>
<th>位置</th>
<th>中介服务器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>干线 1 DEL-GW</p></td>
<td><p>PSTN 网关</p></td>
<td><p>DEL-GW</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>主干 2 HYD-GW</p></td>
<td><p>PSTN 网关</p></td>
<td><p>HYD-GW</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="odd">
<td><p>干线 3 DEL-PBX</p></td>
<td><p>PBX</p></td>
<td><p>DEL-PBX</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>主干 4 HYD-PBX</p></td>
<td><p>PBX</p></td>
<td><p>HYD-PBX</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a>定义语音策略

您必须为您的企业语音部署定义语音策略。 定义语音策略, 以便对用户的子集强制使用基于位置的路由限制 (如果只有它们的子集才能使用基于位置的路由)。 对于此示例, 下表介绍了此方案中使用的语音策略。 只有特定于基于位置的路由的设置才会包含在表中, 以便进行图解。

有关详细信息, 请参阅[配置语音策略和 PSTN 使用记录以在 Lync Server 2013 中授权呼叫功能和权限](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>语音策略1</th>
<th>语音政策2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>语音策略 ID</p></td>
<td><p>新德里语音政策</p></td>
<td><p>Hyderabad 语音政策</p></td>
</tr>
<tr class="even">
<td><p>PSTN 用法</p></td>
<td><p>新德里使用, PBX Del 用法, PBX Hyd 用法</p></td>
<td><p>Hyderabad 使用, PBX Hyd 使用, PBX Del 使用</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>False</p></td>
<td><p>False</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a>定义语音路由

您必须为您的企业语音部署定义语音路由。 对于此示例, 下表介绍了在此方案中使用的语音路线。 只有特定于基于位置的路由的设置才会包含在表中, 以便进行图解。

有关详细信息, 请参阅[在 Lync Server 2013 中配置出站呼叫的语音路由](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)。


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>语音路由1</th>
<th>语音路由2</th>
<th>语音路由3</th>
<th>语音路由4</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名称</p></td>
<td><p>新德里路线</p></td>
<td><p>Hyderabad 路线</p></td>
<td><p>PBX Del 路由</p></td>
<td><p>PBX Hyd 路线</p></td>
</tr>
<tr class="even">
<td><p>PSTN 用法</p></td>
<td><p>新德里使用</p></td>
<td><p>Hyderabad 用法</p></td>
<td><p>PBX Del 使用</p></td>
<td><p>PBX Hyd 使用情况</p></td>
</tr>
<tr class="odd">
<td><p>中继</p></td>
<td><p>干线 1 DEL-GW</p></td>
<td><p>主干 2 HYD-GW</p></td>
<td><p>干线 3 DEL-PBX</p></td>
<td><p>主干 4 HYD-PBX</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a>Enable Users for Enterprise Voice

为用户启用企业语音, 并为他们分配你以前定义的语音策略。 对于此示例, 下表介绍了此方案中使用的作业。 只有特定于基于位置的路由的设置才会包含在表中, 以便进行图解。

有关详细信息, 请参阅[在 Lync Server 2013 中启用企业语音用户](lync-server-2013-enable-users-for-enterprise-voice.md)。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>位于新德里的用户</th>
<th>位于 Hyderabad 的用户</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>关联的语音政策</p></td>
<td><p>新德里语音政策</p></td>
<td><p>Hyderabad 语音政策</p></td>
</tr>
<tr class="even">
<td><p>示例用户</p></td>
<td><p>DEL-LYNC-1、DEL-LYNC-2、DEL-LYNC-3</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置基于位置的路由](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

