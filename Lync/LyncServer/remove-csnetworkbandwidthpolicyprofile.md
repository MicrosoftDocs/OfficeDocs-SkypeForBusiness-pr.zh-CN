---
title: Remove-CsNetworkBandwidthPolicyProfile
TOCTitle: Remove-CsNetworkBandwidthPolicyProfile
ms:assetid: 7b1f3c8d-486c-4a7e-aa40-57893f249f66
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398609(v=OCS.15)
ms:contentKeyID: 49313361
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsNetworkBandwidthPolicyProfile

 

_**上一次修改主题：** 2015-03-09_

删除网络带宽策略配置文件。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsNetworkBandwidthPolicyProfile -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例将删除 Identity 为 LowBWProfile 的带宽策略配置文件。因为标识必须是唯一的，这将最多删除一个配置文件。

    Remove-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile

## 示例 2

示例 2 可从分配了 Identity 为 LowBWProfile 的带宽策略配置文件的所有站点删除对该配置文件的所有引用，然后删除该配置文件。此示例的第一行首先调用 **Get-CsNetworkSite** cmdlet，以检索为呼叫允许控制 (CAC) 配置的所有站点。此站点集合随后将通过管道传递到 **Where-Object** cmdlet，后者将只查找 BWPolicyProfileID 为 (-eq) LowBWProfile 的站点。对于只包含 BWPolicyProfileID 值为 LowBWProfile 的站点的已缩小范围的此集合，会通过管道传递到 **Set-CSNetworkSite** cmdlet，后者会对所有这些站点进行修改，以将 BWPolicyProfileID 更改为 Null ($null)。这样，就完成了查找 BWPolicyProfileID 为 LowBWProfile 的所有站点，并且将该值设置为 Null 的过程。此时就不存在使用 LowBWProfile 配置文件的站点。现在，对配置文件 LowBWProfile 调用 **Remove-CsNetworkBandwidthPolicyProfile** cmdlet 以删除该配置文件，因为已知晓该配置文件当前未被任何站点使用。

要确保该配置文件未用于网络配置中的任何位置，请在第 1 行中针对站点间策略和网络区域链接执行相同的步骤。

    Get-CsNetworkSite | Where-Object {$_.BWPolicyProfileID -eq "LowBWProfile"} | Set-CsNetworkSite -BWPolicyProfileID $null
    Remove-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile

## 详细说明

作为呼叫允许控制 (CAC) 的一部分，使用带宽策略可定义某些形式的带宽限制。（在 Lync Server 中，只能为音频和视频形式指定带宽限制。）此 cmdlet 会删除这些策略的容器配置文件。

重要说明：如果配置文件已分配给站点（使用 **New-CsNetworkSite** cmdlet 或 **Set-CsNetworkSite** cmdlet）、站点间策略（使用 **New-CsNetworkInterSitePolicy** cmdlet 或 **Set-CsNetworkInterSitePolicy** cmdlet）或者网络区域链接（使用 **New-CsNetworkRegionLink** cmdlet 或 **Set-CsNetworkRegionLink** cmdlet），则无法将其删除。如果尝试通过调用 **Remove-CsNetworkBandwidthPolicyProfile** cmdlet 来删除配置文件，您将会收到一条错误。必须首先从所有站点、站点间策略和网络区域链接删除配置文件，然后才能删除该配置文件。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Remove-CsNetworkBandwidthPolicyProfile** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsNetworkBandwidthPolicyProfile"}

## 参数


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>参数</th>
<th>是否必需</th>
<th>类型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>必需</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>用于唯一标识要删除的带宽策略配置文件的字符串值。指定 Identity 将最多删除一个配置文件。</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示任何本该在进行更改前显示的确认提示。</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyProfileType 对象。接受通过管道传递的网络带宽策略配置文件对象的输入。

## 返回类型

此 cmdlet 不返回值。它可删除一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.BWPolicyProfileType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkBandwidthPolicyProfile](new-csnetworkbandwidthpolicyprofile.md)  
[Set-CsNetworkBandwidthPolicyProfile](set-csnetworkbandwidthpolicyprofile.md)  
[Get-CsNetworkBandwidthPolicyProfile](get-csnetworkbandwidthpolicyprofile.md)

