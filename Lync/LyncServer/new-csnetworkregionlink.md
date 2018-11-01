---
title: New-CsNetworkRegionLink
TOCTitle: New-CsNetworkRegionLink
ms:assetid: 61a6a7be-8078-4d59-a78a-2f241f6bf800
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398437(v=OCS.15)
ms:contentKeyID: 49313013
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsNetworkRegionLink

 

_**上一次修改主题：** 2015-03-09_

在为呼叫允许控制 (CAC) 配置的两个地区之间创建链接。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsNetworkRegionLink -NetworkRegionLinkID <String> <COMMON PARAMETERS>

    New-CsNetworkRegionLink -Identity <XdsGlobalRelativeIdentity> <COMMON PARAMETERS>

    COMMON PARAMETERS: -NetworkRegionID1 <String> -NetworkRegionID2 <String> [-BWPolicyProfileID <String>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例可创建名为 NA\_EMEA 的新网络地区链接，并将地区 NorthAmerica 和 EMEA 链接起来。地区链接的名称指定为 Identity 参数的值。（这将自动分配作为 NetworkRegionLinkID 的值。）创建链接时，要链接的两个网络地区是必需的参数，在此示例中，地区名为 NorthAmerica 和 EMEA。在此示例中，我们还将值分配到 BWPolicyProfile 参数。这会将在该带宽策略配置文件 (LowBWLimits) 中定义的带宽限制分配到这些地区之间的连接。如果没有提供 BWPolicyProfileID，则在这两个地区之间的连接上没有带宽限制。（但在站点之间仍然有限制。有关详细信息，请参阅 **New-CsNetworkSite** cmdlet 帮助主题。）

    New-CsNetworkRegionLink -Identity NA_EMEA -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID LowBWLimits

## 详细说明

网络中的地区是通过物理 WAN 连接进行链接的。此 cmdlet 在两个地区之间定义链接，并且设置在这些地区之间音频和视频连接的带宽限制。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **New-CsNetworkRegionLink** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsNetworkRegionLink"}

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
<td><p>新创建网络地区链接的唯一标识符。仅会在全局范围创建网络地区链接，因此该标识符不需要指定范围。但它包含一个字符串，该字符串是标识该链接的唯一名称。</p></td>
</tr>
<tr class="even">
<td><p><em>NetworkRegionID1</em></p></td>
<td><p>必需</p></td>
<td><p>System.String</p></td>
<td><p>链接到由 NetworkRegionID2 参数标识的地区的地区的 Identity (NetworkRegionID)。</p></td>
</tr>
<tr class="odd">
<td><p><em>NetworkRegionID2</em></p></td>
<td><p>必需</p></td>
<td><p>System.String</p></td>
<td><p>链接到由 NetworkRegionID1 参数标识的地区的地区的 Identity (NetworkRegionID)。</p></td>
</tr>
<tr class="even">
<td><p><em>NetworkRegionLinkID</em></p></td>
<td><p>必需</p></td>
<td><p>System.String</p></td>
<td><p>此值与 Identity 相同。无法同时指定 Identity 和 NetworkRegionLinkID；为其中一个输入的值将自动用于二者。</p></td>
</tr>
<tr class="odd">
<td><p><em>BWPolicyProfileID</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>定义此链接的带宽限制的带宽策略配置文件的 Identity。您可以通过调用 <strong>Get-CsNetworkBandwidthPolicyProfile</strong> cmdlet 来检索可用配置文件的列表。</p></td>
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
<td><p><em>InMemory</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

此 cmdlet 可创建一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionLinkType 的对象。

## 另请参阅

#### 其他资源

[Remove-CsNetworkRegionLink](remove-csnetworkregionlink.md)  
[Set-CsNetworkRegionLink](set-csnetworkregionlink.md)  
[Get-CsNetworkRegionLink](get-csnetworkregionlink.md)  
[Get-CsNetworkBandwidthPolicyProfile](get-csnetworkbandwidthpolicyprofile.md)  
[New-CsNetworkSite](new-csnetworksite.md)

