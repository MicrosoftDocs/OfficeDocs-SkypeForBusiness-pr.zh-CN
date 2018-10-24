---
title: 在 Lync Server 2013 中启用基于位置的路由
TOCTitle: 在 Lync Server 2013 中启用基于位置的路由
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994014(v=OCS.15)
ms:contentKeyID: 52060951
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中启用基于位置的路由

 

_**上一次修改主题：** 2015-03-09_

部署 企业语音 并且定义网络区域、站点和子网之后，您可以启用基于位置的路由。必须为以下 企业语音 元素启用基于位置的路由：

  - 网络站点

  - Trunk 配置

  - 语音策略

  - 路由配置

## 为网络站点启用基于位置的路由

在您部署 企业语音 并配置网络站点之后，您已准备好配置基于位置的路由。首先，创建一个语音路由策略以将网络站点与合适的 PSTN 用法进行关联。当向语音路由策略分配 PSTN 用法之后，请确保仅使用与语音路由相关联的 PSTN 用法，这些用法使用站点本地的 PSTN 网关或者位于不需要基于位置的路由限制的区域的 PSTN 网关。使用 Lync ServerWindows PowerShell 命令 New-CsVoiceRoutingPolicy 或 Lync Server 控制面板 创建语音路由策略。

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

有关详细信息，请参阅 [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsVoiceRoutingPolicy)。

对于此示例，下表和 Windows PowerShell 命令阐释了两个语音路由策略以及此方案中定义的相关联的 PSTN 用法。出于说明目的，该表中仅包括特定于基于位置的路由的设置。

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
<th>语音路由策略 1</th>
<th>语音路由策略 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>语音策略 ID</p></td>
<td><p>德里语音路由策略</p></td>
<td><p>海得拉巴语音路由策略</p></td>
</tr>
<tr class="even">
<td><p>PSTN 用法</p></td>
<td><p>德里用法、PBX Del 用法、PBX Hyd 用法</p></td>
<td><p>海得拉巴用法、PBX Hyd 用法、PBX Del 用法</p></td>
</tr>
</tbody>
</table>

  

接下来，为合适的网站站点配置基于位置的路由并将您的语音路由策略与其相关联。使用 Lync ServerWindows PowerShell 命令 New-CsNetworkSite 启用基于位置的路由，并将语音路由策略与必须强制实施路由限制的网络站点相关联。

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

在此示例中，下表说明了两个不同网站“德里”和“海得拉巴”的基于位置的路由，此方案中的两个站点是使用 Lync ServerWindows PowerShell 定义的。出于说明目的，该表中仅包括特定于基于位置的路由的设置。

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
<th>站点 1（德里）</th>
<th>站点 2（海得拉巴）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>站点名称</p></td>
<td><p>站点 1（德里）</p></td>
<td><p>站点 2（海得拉巴）</p></td>
</tr>
<tr class="even">
<td><p>EnableLocationBasedRouting</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>语音路由策略</p></td>
<td><p>德里语音路由策略</p></td>
<td><p>海得拉巴语音路由策略</p></td>
</tr>
<tr class="even">
<td><p>子网</p></td>
<td><p>子网 1（德里）</p></td>
<td><p>子网 2（海得拉巴）</p></td>
</tr>
</tbody>
</table>



## 为 Trunk 启用基于位置的路由

在可以为 Trunk 配置启用基于位置的路由之前，您需要为每个 Trunk 或每个网络站点创建 Trunk 配置。使用 Lync ServerWindows PowerShell 命令 New-CsTrunkConfiguration 创建 Trunk 配置。如果多个 Trunk 与给定系统（如网关或 PBX）相关联，则必须修改每个 Trunk 配置以启用基于位置的路由限制。

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

有关详细信息，请参阅 [New-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration)。

对于此示例，以下 Windows PowerShell 命令说明了如何为此方案中定义的部署中的每个 Trunk 创建一个 Trunk 配置。

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

为每个 Trunk 配置 Trunk 配置之后，您可以使用 Lync ServerWindows PowerShell 命令 Set-CsTrunkConfiguration 为必须强制实施路由限制的 Trunk 启用基于位置的路由。为将呼叫路由到 PSTN 网关的 Trunk 启用基于位置的路由以将呼叫路由到 PSTN，并关联网关所在的网络站点。

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

有关详细信息，请参阅 [New-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration)。

在此示例中，为与德里和海得拉巴中的 PSTN 网关相关联的每个 Trunk 启用了基于位置的路由：

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

不要为不会将呼叫路由到 PSTN 的 Trunk 启用基于位置的路由；然而，您仍然需要将该 Trunk 与系统所在的网络站点相关联，因为必须为通过此 Trunk 达到连接的终结点的 PSTN 呼叫强制实施基于位置的路由限制。对于此示例，没有为与德里和海得拉巴中的 PBX 系统相关联的每个 Trunk 启用基于位置的路由：

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
与不会将呼叫路由到 PSTN 的系统（如 PBX）相连接的终结点具有类似限制，因为为用户的 Lync 终结点启用了基于位置的路由。这意味着这些用户不管位置如何都能够向 Lync 发出呼叫并接收来自 Lync 用户的呼叫。此外，他们也能够从不会将呼叫路由到 PSTN 网络的其他系统（如连接到不同 PBX 的终结点）发出呼叫和应答来自这些系统的呼叫。所有牵涉 PSTN 终结点的入站呼叫、出站呼叫和呼叫转接都将强制实施基于位置的路由。此类呼叫必须仅使用定义为此类系统的本地网关的 PSTN 网关。

下表说明了两个不同的网站站点中四个 Trunk 的 Trunk 配置：两个 Trunk 连接到 PSTN 网关，两个 Trunk 连接到 PBX 系统。


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
<td><p>PstnGateway:Trunk 1 DEL-GW</p></td>
<td><p>True</p></td>
<td><p>站点 1（德里）</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway:Trunk 2 HYD-GW</p></td>
<td><p>True</p></td>
<td><p>站点 2（海得拉巴）</p></td>
</tr>
<tr class="odd">
<td><p>PstnGateway:Trunk 3 DEL-PBX</p></td>
<td><p>False</p></td>
<td><p>站点 1（德里）</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway:Trunk 4 HYD-PBX</p></td>
<td><p>False</p></td>
<td><p>站点 2（海得拉巴）</p></td>
</tr>
</tbody>
</table>



## 为语音策略启用基于位置的路由

要为特定用户强制实施基于位置的路由，请配置这些用户的语音策略以防止 PSTN 收费绕路情形。使用 Lync ServerWindows PowerShell 命令 New-CsVoicePolicy 创建新的语音策略，或者使用 Set-CsVoicePolicy（如果使用现有策略）启用基于位置的路由并防止 PSTN 收费绕路情形。

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

有关详细信息，请参阅 [New-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsVoicePolicy)。

对于此示例，下表和 Windows PowerShell 命令说明了如何通过此方案中定义的德里和海得拉巴语音策略防止 PSTN 收费绕路情形。出于说明目的，该表中仅包括特定于基于位置的路由的设置。

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
<th>语音策略 1</th>
<th>语音策略 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>语音策略 ID</p></td>
<td><p>德里语音策略</p></td>
<td><p>海得拉巴语音策略</p></td>
</tr>
<tr class="even">
<td><p>PSTN 用法</p></td>
<td><p>德里用法、PBX Del 用法、PBX Hyd 用法</p></td>
<td><p>海得拉巴用法、PBX Hyd 用法、PBX Del 用法</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
</tbody>
</table>



## 在路由配置中启用基于位置的路由

最后，为您的路由配置全局启用基于位置的路由。使用 Lync ServerWindows PowerShell 命令 New-CsRoutingConfiguration 启用基于位置的路由。

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

有关详细信息，请参阅 [Set-CsRoutingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRoutingConfiguration)。

> [!NOTE]  
> 虽然基于位置的路由必须通过全局配置启用，但是只将为已按照本文档中指定的内容配置了基于位置的路由的那些站点、用户和 Trunk 强制实施要应用的一组规则。




## 另请参阅

#### 其他资源

[在 Lync Server 2013 中配置基于位置的路由](lync-server-2013-configuring-location-based-routing.md)

