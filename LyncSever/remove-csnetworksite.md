---
title: Remove-CsNetworkSite
TOCTitle: Remove-CsNetworkSite
ms:assetid: 07b543a6-3aa0-4fce-85f9-9ddc75d7b14f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398135(v=OCS.15)
ms:contentKeyID: 49311907
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsNetworkSite

 

_**上一次修改主题：** 2015-03-09_

删除已为呼叫允许控制 (CAC) 或增强型 9-1-1 (E9-1-1) 定义的网络站点。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsNetworkSite -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例从 CAC 或 E9-1-1 配置中删除 Identity 为 Vancouver 的站点。

    Remove-CsNetworkSite -Identity Vancouver

## 示例 2

示例 2 从 CAC 或 E9-1-1 配置中删除使用名为 LowBWProfile 的带宽策略配置文件的所有站点。此示例首先调用 **Get-CsNetworkSite** cmdlet 以检索所有网络站点。将这些站点的集合通过管道传递到 **Where-Object** cmdlet，后者将集合的范围缩小到仅 BWPolicyProfileID 等于 (-eq) LowBWProfile 的那些站点。然后，将此新集合通过管道传递到 **Remove-CsNetworkSite** cmdlet 以删除那些站点。

    Get-CsNetworkSite | Where-Object {$_.BWPolicyProfileID -eq "LowBWProfile"} | Remove-CsNetworkSite

## 详细说明

网络站点是指在部署了 CAC 或 E9-1-1 的每个区域中配置的办公室或位置。此 cmdlet 从 CAC 或 E9-1-1 配置中删除站点。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Remove-CsNetworkSite** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsNetworkSite"}

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
<td><p>要删除的网络站点的唯一标识符。仅在全局范围内创建站点，因此不需要指定范围。而是只需要指定站点 ID。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.DisplayNetworkSiteType 对象。接受通过管道传递的网络站点对象的输入。

## 返回类型

此 cmdlet 不返回值。删除一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.DisplayNetworkSiteType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkSite](new-csnetworksite.md)  
[Set-CsNetworkSite](set-csnetworksite.md)  
[Get-CsNetworkSite](get-csnetworksite.md)

