---
title: Remove-CsNetworkRegion
TOCTitle: Remove-CsNetworkRegion
ms:assetid: 661dce40-f601-4181-b8f1-3277a76d5df4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398466(v=OCS.15)
ms:contentKeyID: 49313074
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsNetworkRegion

 

_**上一次修改主题：** 2015-03-09_

删除现有网络区域。网络区域表示企业网络中的网络中心或主干网络。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsNetworkRegion -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 删除 Identity 为 NorthAmerica 的网络区域。由于标识是唯一的，因此该命令将只删除一个网络区域。

    Remove-CsNetworkRegion -Identity NorthAmerica

## 示例 2

此示例删除与中央站点 Redmond 关联的所有网络区域。该命令首先调用不带任何参数的 **Get-CsNetworkRegion** cmdlet，以便检索为 Lync Server 部署定义的所有网络区域的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet。**Where-Object** cmdlet 会筛选该集合，以便仅返回 CentralSite 值等于 (-eq) site:Redmond 的项目（网络区域）。将集合的范围缩小为这些项目后，将此新集合通过管道传递到 **Remove-CsNetworkRegion** cmdlet，后者会删除该集合中的每一项。

    Get-CsNetworkRegion | Where-Object {$_.CentralSite -eq "site:Redmond"} | Remove-CsNetworkRegion

## 示例 3

此示例删除 Identity 为 NorthAmerica 的网络区域。但是，如果区域与某个站点关联，则不能删除该区域。因此，此示例首先删除 NorthAmerica 区域与站点之间的任何关联。

此示例首先调用不带任何参数的 **Get-CsNetworkSite** cmdlet，以便检索为 Lync Server 部署定义的所有网络站点的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet。**Where-Object** cmdlet 会筛选该集合，以便仅返回 NetworkRegionID 值等于 (-eq) NorthAmerica 的项目（网络站点）。将集合的范围缩小为这些项目后，将此新集合通过管道传递到 **Set-CsNetworkSite** cmdlet。对于包含 NetworkRegionID NorthAmerica 的每个站点，将 NetworkRegionID 设置为空 ($null)。这将删除对该站点上的区域的引用。但是，如果某个站点未与其他站点关联，则该站点不能具有绕过 ID。因此，除了通过将 NetworkRegionID 设置为 Null 来删除对区域的引用外，还必须通过将 BypassID 设置为 Null 来删除绕过关联。

第一行完成后，与 NorthAmerica 区域关联的任何站点都将不再绑定到区域或任何绕过设置。此时，可以调用第二行，以删除网络区域。

    Get-CsNetworkSite | Where-Object {$_.NetworkRegionID -eq "NorthAmerica"} | Set-CsNetworkSite -NetworkRegionID $null -BypassID $null
    Remove-CsNetworkRegion -Identity "NorthAmerica"

## 详细说明

网络区域将跨多个地理区域的网络的各个部分相互连接起来。每个网络区域都必须与中央站点关联。中央站点是运行带宽策略服务的数据中心站点。使用此 cmdlet 可删除网络区域。

请注意，如果网络区域与某个网络站点关联（也就是说，网络区域的 Identity 等于任一站点的 NetworkRegionID），则不能删除该网络区域。如果尝试删除与某个站点关联的区域，您将收到错误消息。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Remove-CsNetworkRegion** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsNetworkRegion"}

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
<td><p>要删除的网络区域的唯一标识符。Identity 将采用唯一标识该区域的字符串的形式。</p></td>
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
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionType 对象。接受通过管道传递的网络区域对象的输入。

## 返回类型

此 cmdlet 不会返回值。它会删除一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkRegion](new-csnetworkregion.md)  
[Set-CsNetworkRegion](set-csnetworkregion.md)  
[Get-CsNetworkRegion](get-csnetworkregion.md)

