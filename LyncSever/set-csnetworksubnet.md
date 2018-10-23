---
title: Set-CsNetworkSubnet
TOCTitle: Set-CsNetworkSubnet
ms:assetid: 9e85cdbb-b5fb-48d6-8f95-6e7cba9d9597
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412739(v=OCS.15)
ms:contentKeyID: 49313760
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsNetworkSubnet

 

_**上一次修改主题：** 2015-03-09_

修改现有网络子网。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsNetworkSubnet [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsNetworkSubnet [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-MaskBits <Int32>] [-NetworkSiteID <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例会对 Identity（子网 ID）为 172.11.15.0 的子网进行修改。使用新 MaskBits 值 (25) 和新 NetworkSiteID (Chicago) 修改子网。

    Set-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 25 -NetworkSiteID Chicago

## 示例 2

示例 2 会将 Vancouver 站点上的所有子网移动到 Chicago 站点。为此，我们首先调用 **Get-CsNetworkSubnet** cmdlet。这将检索在 Lync Server 部署中定义的所有子网的集合。然后将该子网集合通过管道传递到 **Where-Object** cmdlet。**Where-Object** cmdlet 会接受该集合并将其范围缩小为仅包含 NetworkSiteID 等于 (-eq) Vancouver 的子网。现在，集合仅由与 Vancouver 站点关联的子网组成，我们将此集合通过管道传递到 **Set-CsNetworkSubnet** cmdlet。向 **Set-CsNetworkSubnet** cmdlet 提供一个参数：NetworkSiteID。通过传递参数值 Chicago，我们指示 **Set-CsNetworkSubnet** cmdlet 将集合中每个成员的网络站点 ID 更改为 Chicago。

    Get-CsNetworkSubnet | Where-Object {$_.NetworkSiteID -eq "Vancouver"} | Set-CsNetworkSubnet -NetworkSiteID Chicago

## 详细说明

每个子网都必须与一个网络站点关联，以便确定此子网所属主机的地理位置。使用此 cmdlet 可以修改关联网络站点、更改子网的描述，或修改子网的掩码位。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsNetworkSubnet** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsNetworkSubnet"}

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
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>修改的子网的描述。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>禁止显示任何本该在进行更改前显示的确认提示。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>XdsGlobalRelativeIdentity</p></td>
<td><p>要修改的子网的唯一子网 ID。此值可以是 IP 地址（例如 174.11.12.0）或以 http: 或https: 开头的 URL。</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>SubnetType</p></td>
<td><p>对要修改的网络子网对象的引用。此对象的类型必须为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.SubnetType，它可以通过调用 <strong>Get-CsNetworkSubnet</strong> cmdlet 进行检索。</p></td>
</tr>
<tr class="even">
<td><p><em>MaskBits</em></p></td>
<td><p>可选</p></td>
<td><p>Int32</p></td>
<td><p>要应用于子网的位掩码。</p></td>
</tr>
<tr class="odd">
<td><p><em>NetworkSiteID</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>此子网应用于的网络站点的站点 ID。通过调用 <strong>Get-CsNetworkSite</strong> cmdlet，可以检索部署的站点 ID。</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.SubnetType 对象。接受通过管道传递的网络子网对象的输入。

## 返回类型

此 cmdlet 不返回值。它会修改一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.SubnetType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkSubnet](new-csnetworksubnet.md)  
[Remove-CsNetworkSubnet](remove-csnetworksubnet.md)  
[Get-CsNetworkSubnet](get-csnetworksubnet.md)

