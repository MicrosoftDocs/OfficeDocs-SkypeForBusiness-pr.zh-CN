---
title: Lync Server 2013：启用基于位置的路由
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
ms.openlocfilehash: e21e1a285fa5b2129d4d0ed0b5d75e8dcee42f2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a>在 Lync Server 2013 中启用基于位置的路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-04-26_

部署企业语音并定义网络区域、网站和子网后，您可以启用基于位置的路由。 必须为以下企业语音元素启用基于位置的路由：

  - 网络站点

  - 中继配置

  - 语音策略

  - 路由配置

<div>

## <a name="enable-location-based-routing-to-network-sites"></a>启用到网络站点的基于位置的路由

部署企业语音和配置的网络站点后，即可配置基于位置的路由。 首先，创建一个语音路由策略，将网络站点与适当的 PSTN 使用情况关联起来。 将 PSTN 使用分配给语音路由策略时，请确保仅使用与在不需要基于位置的路由限制的区域中使用站点或 PSTN 网关的 pstn 网关相关的 PSTN 使用。使用 Lync Server Windows PowerShell 命令、"新建-CsVoiceRoutingPolicy" 或 "Lync Server 控制面板" 创建语音路由策略。

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

有关更多信息，请参阅 [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy)。

对于此示例，下表和 Windows PowerShell 命令演示了这种情况下定义的两个语音路由策略及其关联的 PSTN 用法。 只有特定于基于位置的路由的设置才会包含在表中，以便进行图解。

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
<td><p>Hyderabad 使用，PBX Hyd 使用，PBX Del 使用</p></td>
</tr>
</tbody>
</table>

  

接下来，为适用的网络网站配置基于位置的路由，并将你的语音路由策略关联到它们。 使用 Lync Server Windows PowerShell 命令 CsNetworkSite，可启用基于位置的路由，并将语音路由策略与您的网络站点进行关联，这些站点必须实施路由限制。

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

在此示例中，下表介绍了使用 Lync Server Windows PowerShell 在此方案中定义的两个不同网络站点、新德里和 Hyderabad 的基于位置的路由。 只有特定于基于位置的路由的设置才会包含在表中，以便进行图解。

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
<th>站点1（新德里）</th>
<th>Site 2 （Hyderabad）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>站点名称</p></td>
<td><p>站点1（新德里）</p></td>
<td><p>Site 2 （Hyderabad）</p></td>
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
<td><p>子网1（新德里）</p></td>
<td><p>子网2（Hyderabad）</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a>支持基于位置的路由到中继

在可以为基于位置的路由启用中继配置之前，你需要为每个主干或每个网络站点创建中继配置。 使用 Lync Server Windows PowerShell 命令 New-cstrunkconfiguration 创建中继配置。 如果多个中继与给定系统（即网关或 PBX）相关联，则必须修改每个中继配置以启用基于位置的路由限制。

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

有关详细信息，请参阅[new-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)。

对于此示例，以下 Windows PowerShell 命令演示了为此方案中定义的部署中的每个主干创建一个 trunk 配置。

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

每个干线配置了中继配置后，您可以使用 Lync Server Windows PowerShell 命令 New-cstrunkconfiguration，以便为必须强制执行路由限制的中继启用基于位置的路由。 启用到中继的基于位置的路由，将呼叫路由到将呼叫路由到 PSTN 的 PSTN 网关，并关联网关所在的网络站点。

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

有关详细信息，请参阅[new-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)。

在此示例中，为与新德里和 Hyderabad 中的 PSTN 网关相关联的每个干线启用基于位置的路由：

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

不要为不将呼叫路由到 PSTN 的中继启用基于位置的路由;但是，你仍然必须将主干与系统所在的网络站点相关联，因为需要针对通过此主干连接的终结点强制执行 PSTN 调用的基于位置的路由限制。 对于此示例，对于与新德里和 Hyderabad 中的 PBX 系统相关联的每个主干，不启用基于位置的路由：

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
连接到不将调用路由到 PSTN （即 PBX）的系统的终结点将具有与启用基于位置的路由的用户的 Lync 终结点类似的限制。 这意味着，无论用户的位置如何，这些用户都可以将呼叫放入和接收 Lync 用户。 他们还可以将接收呼叫与其他系统进行呼叫，而不是将呼叫路由到 PSTN 网络（即连接到其他 PBX 的终结点），无论与系统关联的网络站点。 涉及 PSTN 终结点的所有入站呼叫、出站呼叫、呼叫转移和呼叫转接将受到基于位置的路由 enforcements。 此类通话只能使用定义为此类系统本地的 PSTN 网关。

下表说明了两个不同网络站点中四个中继的干线配置：两个连接到 PSTN 网关的两个连接和连接到 PBX 系统的两个。


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
<td><p>PstnGateway：干线 1 DEL-GW</p></td>
<td><p>True</p></td>
<td><p>站点1（新德里）</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway：主干 2 HYD-GW</p></td>
<td><p>True</p></td>
<td><p>Site 2 （Hyderabad）</p></td>
</tr>
<tr class="odd">
<td><p>PstnGateway：干线 3 DEL-PBX</p></td>
<td><p>False</p></td>
<td><p>站点1（新德里）</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway：干线 4 HYD-PBX</p></td>
<td><p>False</p></td>
<td><p>Site 2 （Hyderabad）</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a>支持基于位置的路由到语音策略

若要强制将基于位置的路由到特定用户，请将这些用户的语音策略配置为阻止 PSTN 免绕过。 使用 Lync Server Windows PowerShell 命令 CsVoicePolicy 创建新的语音策略或设置 CsVoicePolicy （如果使用现有策略），以通过阻止 PSTN 免绕过来启用基于位置的路由。

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

有关详细信息，请参阅[CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy)。

在此示例中，下表和 Windows PowerShell 命令演示了如何为本方案中定义的 Hyderabad 语音策略启用 PSTN 免绕过保护。 只有特定于基于位置的路由的设置才会包含在表中，以便进行图解。

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
<td><p>新德里使用，PBX Del 用法，PBX Hyd 用法</p></td>
<td><p>Hyderabad 使用，PBX Hyd 使用，PBX Del 使用</p></td>
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

## <a name="enable-location-based-routing-in-the-routing-configuration"></a>在路由配置中启用基于位置的路由

最后，全局启用到路由配置的基于位置的路由。 使用 Lync Server Windows PowerShell 命令 CsRoutingConfiguration，以启用基于位置的路由。

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

有关详细信息，请参阅[设置 CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration)。

<div>


> [!NOTE]  
> 基于位置的路由必须通过全局配置启用时，将仅针对本文档中指定的网站、用户和中继强制执行要应用的规则集。



</div>

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

