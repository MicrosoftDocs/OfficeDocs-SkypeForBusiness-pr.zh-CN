---
title: Remove-CsNetworkRegionLink
TOCTitle: Remove-CsNetworkRegionLink
ms:assetid: f26cde90-e789-44a7-a304-695c85e64403
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413012(v=OCS.15)
ms:contentKeyID: 49314709
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsNetworkRegionLink

 

_**上一次修改主题：** 2015-03-09_

删除为呼叫允许控制 (CAC) 配置的两个区域间的链接。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsNetworkRegionLink -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

第一个示例删除 Identity 为 NA\_EMEA 的网络区域链接。

    Remove-CsNetworkRegionLink -Identity NA_EMEA

## 示例 2

示例 2 删除正在使用名为 HighBWLimits 的带宽策略配置文件的所有网络区域链接。在此示例中，首先调用 **Get-CsNetworkRegionLink** cmdlet（不带参数），该 cmdlet 将检索所有区域链接。然后将该链接集合通过管道传递到 **Where-Object** cmdlet。**Where-Object** cmdlet 会逐一查看集合中的每个成员，检查 BWPolicyProfileID 属性的值。如果此属性等于 (-eq) HighBWLimits，我们会将该成员通过管道传递到 **Remove-CsNetworkRegionLink** cmdlet，后者将删除该链接。

    Get-CsNetworkRegionLink | Where-Object {$_.BWPolicyProfileID -eq "HighBWLimits"} | Remove-CsNetworkRegionLink

## 详细说明

网络内的区域通过物理 WAN 连接进行链接。此 cmdlet 不会影响任何物理连接，但会从 CAC 配置中删除链接。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Remove-CsNetworkRegionLink** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsNetworkRegionLink"}

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
<td><p>要删除的网络区域链接的唯一标识符。由于仅在全局范围创建网络区域链接，因此此标识符不需要指定范围。此标识符包含一个字符串，作为标识该链接的唯一名称。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionLinkType 对象。接受通过管道传递的网络区域链接对象的输入。

## 返回类型

此 cmdlet 不会返回值。它可删除一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionLinkType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkRegionLink](new-csnetworkregionlink.md)  
[Set-CsNetworkRegionLink](set-csnetworkregionlink.md)  
[Get-CsNetworkRegionLink](get-csnetworkregionlink.md)

