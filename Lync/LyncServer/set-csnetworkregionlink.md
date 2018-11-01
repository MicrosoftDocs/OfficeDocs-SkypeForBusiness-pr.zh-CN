---
title: Set-CsNetworkRegionLink
TOCTitle: Set-CsNetworkRegionLink
ms:assetid: b3d5d203-2aa7-4a54-93d4-30bcda391d68
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412867(v=OCS.15)
ms:contentKeyID: 49313992
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsNetworkRegionLink

 

_**上一次修改主题：** 2015-03-09_

修改为呼叫允许控制 (CAC) 配置的两个网络区域之间的链接。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsNetworkRegionLink [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsNetworkRegionLink [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-BWPolicyProfileID <String>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-NetworkRegionID1 <String>] [-NetworkRegionID2 <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例将名为 NA\_EMEA 的网络区域链接的带宽策略配置文件更改为 HighBWLimits 配置文件。将要修改的网络区域链接的名称指定为 Identity 参数的值。接下来，我们已将值 HighBWLimits 分配给 BWPolicyProfile 参数。这会将该带宽策略配置文件 (HighBWLimits) 中定义的带宽限制分配给这些区域之间的连接。

    Set-CsNetworkRegionLink -Identity NA_EMEA -BWPolicyProfileID HighBWLimits

## 详细说明

网络内的区域通过物理 WAN 连接进行链接。此 cmdlet 可修改两个区域之间的链接，使您可以更改链接的任一区域以及这些区域之间的音频和视频连接的带宽限制。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsNetworkRegionLink** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsNetworkRegionLink"}

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
<td><p><em>BWPolicyProfileID</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>用于定义对此链接的限制的带宽策略配置文件的标识。您可以通过调用 <strong>Get-CsNetworkBandwidthPolicyProfile</strong> cmdlet 来检索可用配置文件的列表。</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>XdsGlobalRelativeIdentity</p></td>
<td><p>要修改的网络区域链接的唯一标识符。由于仅在全局范围创建网络区域链接，因此此标识符不需要指定范围。此标识符包含一个字符串，作为标识该链接的唯一名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>NetworkRegionLinkType</p></td>
<td><p>网络区域链接的对象引用。此对象的类型必须是 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionLinkType，可以通过调用 <strong>Get-CsNetworkRegionLink</strong> cmdlet 来检索该对象类型。</p></td>
</tr>
<tr class="even">
<td><p><em>NetworkRegionID1</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>与 NetworkRegionID2 属性标识的区域链接的区域的标识 (NetworkRegionID)。</p></td>
</tr>
<tr class="odd">
<td><p><em>NetworkRegionID2</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>与 NetworkRegionID1 属性标识的区域链接的区域的标识 (NetworkRegionID)。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionLinkType 对象。接受通过管道传递的网络区域链接对象的输入。

## 返回类型

此 cmdlet 不会返回值。它修改类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkRegionRouteType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkRegionLink](new-csnetworkregionlink.md)  
[Remove-CsNetworkRegionLink](remove-csnetworkregionlink.md)  
[Get-CsNetworkRegionLink](get-csnetworkregionlink.md)  
[Get-CsNetworkBandwidthPolicyProfile](get-csnetworkbandwidthpolicyprofile.md)

