---
title: Remove-CsNetworkSubnet
TOCTitle: Remove-CsNetworkSubnet
ms:assetid: 251ddb5c-4837-4810-b46f-d276f9535653
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425726(v=OCS.15)
ms:contentKeyID: 49312271
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsNetworkSubnet

 

_**上一次修改主题：** 2015-03-09_

删除现有网络子网。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsNetworkSubnet -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例删除 Identity（子网 ID）为 172.11.15.0 的子网。

    Remove-CsNetworkSubnet -Identity 172.11.15.0

## 示例 2

示例 2 删除与 Vancouver 站点关联的所有子网。为执行此操作，我们首先调用 **Get-CsNetworkSubnet** cmdlet。这将检索在 Lync Server 部署中定义的所有子网的集合。然后将该子网集合通过管道传递到 **Where-Object** cmdlet。**Where-Object** cmdlet 会接受该集合并将其范围缩小为仅包含 NetworkSiteID 等于 (-eq) Vancouver 的子网。现在，该集合只包含与 Vancouver 站点关联的子网，接下来我们将此集合通过管道传递到 **Remove-CsNetworkSubnet** cmdlet，后者会删除集合中的每一项。

    Get-CsNetworkSubnet | Where-Object {$_.NetworkSiteID -eq "Vancouver"} | Remove-CsNetworkSubnet

## 详细说明

每个子网都必须与一个网络站点关联，以便确定此子网所属主机的地理位置。使用此 cmdlet 可删除网络子网。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Remove-CsNetworkSubnet** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsNetworkSubnet"}

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
<td><p>要删除的子网的唯一子网 ID。该值将为一个 IP 地址（如 174.11.12.0）。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.SubnetType 对象。接受通过管道传递的网络子网对象的输入。

## 返回类型

此 cmdlet 不会返回值。它会删除一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.SubnetType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkSubnet](new-csnetworksubnet.md)  
[Set-CsNetworkSubnet](set-csnetworksubnet.md)  
[Get-CsNetworkSubnet](get-csnetworksubnet.md)

