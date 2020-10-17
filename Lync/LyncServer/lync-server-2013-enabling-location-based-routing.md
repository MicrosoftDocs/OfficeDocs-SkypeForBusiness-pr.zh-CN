---
title: Lync Server 2013：启用 Location-Based 路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ab22ffdfc47f390671f2bf66ea76dd734aaa128
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500969"
---
# <a name="enabling-location-based-routing-in-lync-server-2013"></a>在 Lync Server 2013 中启用 Location-Based 路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-04-26_

部署企业语音并定义网络区域、站点和子网之后，您可以启用 Location-Based 路由。 必须为以下 Enterprise Voice 元素启用 Location-Based 路由：

  - 网络站点

  - 中继配置

  - 语音策略

  - 路由配置

<div>

## <a name="enable-location-based-routing-to-network-sites"></a>启用到网络站点的 Location-Based 路由

部署企业语音和配置的网络站点后，即可配置 Location-Based 路由。 首先，创建语音路由策略以将网络站点与适当的 PSTN 用法关联起来。 为语音路由策略分配 PSTN 用法时，请确保仅使用与使用站点的 PSTN 网关或 PSTN 网关（位于不需要 Location-Based 路由限制的区域）的语音路由相关联的 PSTN 用法。使用 Lync Server Windows PowerShell 命令 "Grant-csvoiceroutingpolicy" 或 "Lync Server 控制面板" 创建语音路由策略。

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

有关详细信息，请参阅 [grant-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy)。

对于此示例，下表和 Windows PowerShell 命令说明了在此方案中定义的两种语音路由策略及其关联 PSTN 用法。 为了便于说明，表中仅包括特定于 Location-Based 路由的设置。

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>语音路由策略1</th>
<th>语音路由策略2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>语音策略 ID</p></td>
<td><p>新德里语音路由策略</p></td>
<td><p>Hyderabad 语音路由策略</p></td>
</tr>
<tr class="even">
<td><p>PSTN 用法</p></td>
<td><p>新德里使用，PBX Del 用法，PBX Hyd 用法</p></td>
<td><p>Hyderabad 用法，PBX Hyd usage，PBX Del 用法</p></td>
</tr>
</tbody>
</table>

  

接下来，为相应的网络站点配置 Location-Based 路由，并将您的语音路由策略关联到它们。 使用 Lync Server Windows PowerShell 命令 CsNetworkSite，启用 Location-Based 路由，并将语音路由策略与必须强制实施路由限制的网络站点关联。

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

在此示例中，下表说明了使用 Lync Server Windows PowerShell 在此方案中定义的两个不同网络站点（Hyderabad 和）的 Location-Based 路由。 为了便于说明，表中仅包括特定于 Location-Based 路由的设置。

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Site 1 (新德里) </th>
<th>Site 2 (Hyderabad) </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>网站名称</p></td>
<td><p>Site 1 (新德里) </p></td>
<td><p>Site 2 (Hyderabad) </p></td>
</tr>
<tr class="even">
<td><p>EnableLocationBasedRouting</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>语音路由策略</p></td>
<td><p>新德里语音路由策略</p></td>
<td><p>Hyderabad 语音路由策略</p></td>
</tr>
<tr class="even">
<td><p>子网</p></td>
<td><p>Subnet 1 (新德里) </p></td>
<td><p>Subnet 2 (Hyderabad) </p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a>启用到中继的 Location-Based 路由

在可以为 Location-Based 路由启用中继配置之前，您需要为每个中继或每个网络站点创建中继配置。 使用 Lync Server Windows PowerShell 命令 Remove-cstrunkconfiguration，创建中继配置。 如果多个中继与给定系统相关联 (即 Gateway 或 PBX) ，则必须修改每个中继配置，以启用 Location-Based 路由限制。

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

有关详细信息，请参阅 [remove-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)。

对于此示例，以下 Windows PowerShell 命令说明了如何为此方案中定义的部署中的每个中继创建一个中继配置。

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

一旦每个中继配置了中继配置，您就可以使用 Lync Server Windows PowerShell 命令 Remove-cstrunkconfiguration，以启用到必须强制执行路由限制的中继的 Location-Based 路由。 Location-Based 启用到中继的路由，将呼叫路由到将呼叫路由到 PSTN 网关的 PSTN 网关，并将该网关所在的网络站点关联起来。

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

有关详细信息，请参阅 [remove-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)。

在此示例中，将为与在新德里和 Hyderabad 中的 PSTN 网关关联的每个中继启用 Location-Based 路由：

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

请勿为不将呼叫路由到 PSTN 的中继启用 Location-Based 路由;但是，仍必须将中继与系统所在的网络站点相关联，以便在到达通过此中继连接的终结点的 PSTN 呼叫时，需要强制实施 Location-Based 路由限制。 对于此示例，对于与在新德里和 Hyderabad 中的 PBX 系统相关联的每个中继，不启用 Location-Based 路由：

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
连接到不将呼叫路由到 PSTN 的系统的终结点 (即 PBX) 的限制与启用了 Location-Based 路由的用户的 Lync 终结点的类似限制。 这意味着，无论用户的位置如何，这些用户都将能够在 Lync 用户处呼叫和接收呼叫。 他们还可以在不将呼叫路由到 PSTN (网络的其他系统（即连接到不同) PBX 的终结点，无论与系统关联的网络站点）之间进行接收呼叫。 涉及 PSTN 终结点的所有入站呼叫、出站呼叫、呼叫转移和呼叫转接将受 Location-Based 路由之后。 此类呼叫必须仅使用定义为此类系统的本地的 PSTN 网关。

下表说明了两个不同网络站点中四个中继的中继配置：两个连接到 PSTN 网关的两个网络站点，以及两个连接到 PBX 系统的站点。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>EnableLocationRestriction</th>
<th>NetworkSiteID</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>为 pstngateway：中继 1 DEL-GW</p></td>
<td><p>True</p></td>
<td><p>Site 1 (新德里) </p></td>
</tr>
<tr class="even">
<td><p>为 pstngateway： Trunk 2 HYD-GW</p></td>
<td><p>True</p></td>
<td><p>Site 2 (Hyderabad) </p></td>
</tr>
<tr class="odd">
<td><p>为 pstngateway： Trunk 3 DEL-PBX</p></td>
<td><p>False</p></td>
<td><p>Site 1 (新德里) </p></td>
</tr>
<tr class="even">
<td><p>为 pstngateway： Trunk 4 HYD-PBX</p></td>
<td><p>False</p></td>
<td><p>Site 2 (Hyderabad) </p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a>启用 Location-Based 路由到语音策略

若要强制 Location-Based 路由到特定用户，请将这些用户的语音策略配置为阻止 PSTN 收费旁路。 使用 Lync Server Windows PowerShell 命令 Set-csvoicepolicy，创建新的语音策略或 Set-csvoicepolicy （如果使用现有策略），通过防止 PSTN 收费旁路来启用 Location-Based 路由。

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

有关详细信息，请参阅 [set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy)。

对于此示例，下表和 Windows PowerShell 命令说明了如何防止对此方案中定义的新德里和 Hyderabad 语音策略禁止 PSTN 收费旁路。 为了便于说明，表中仅包括特定于 Location-Based 路由的设置。

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


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
<th>语音策略2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>语音策略 ID</p></td>
<td><p>新德里语音策略</p></td>
<td><p>Hyderabad 语音策略</p></td>
</tr>
<tr class="even">
<td><p>PSTN 用法</p></td>
<td><p>新德里使用，PBX Del 用法，PBX Hyd 用法</p></td>
<td><p>Hyderabad 用法，PBX Hyd usage，PBX Del 用法</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a>在路由配置中启用 Location-Based 路由

最后，全局启用 Location-Based 路由到您的路由配置。 使用 Lync Server Windows PowerShell 命令 CsRoutingConfiguration，启用 Location-Based 路由。

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

有关详细信息，请参阅 [CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration)。

<div>


> [!NOTE]  
> 虽然必须通过全局配置启用 Location-Based 路由，但只会对要应用的一组规则强制实施此文档中为其配置的网站、用户和中继。



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置 Location-Based 路由](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

