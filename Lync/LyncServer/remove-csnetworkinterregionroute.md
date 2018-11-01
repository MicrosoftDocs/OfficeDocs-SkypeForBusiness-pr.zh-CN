---
title: Remove-CsNetworkInterRegionRoute
TOCTitle: Remove-CsNetworkInterRegionRoute
ms:assetid: 91948c03-2bcb-4e25-b0b6-23827e85bbb3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398743(v=OCS.15)
ms:contentKeyID: 49313612
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsNetworkInterRegionRoute

 

_**上一次修改主题：** 2015-03-09_

删除呼叫允许控制 (CAC) 配置中连接网络区域的路由。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsNetworkInterRegionRoute -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 删除 Identity 为 NA\_APAC\_Route 的路由。

    Remove-CsNetworkInterRegionRoute -Identity NA_APAC_Route

## 示例 2

示例 2 删除包括 NorthAmerica 区域的所有区域路由。该命令的第一部分是调用 **Get-CsNetworkInterRegionRoute** cmdlet。调用的此 cmdlet 不带任何参数，将检索所有区域路由。接下来，将该路由集合通过管道传递到 **Where-Object** cmdlet。**Where-Object** cmdlet 将该集合的范围缩小到仅包含将 NorthAmerica 定义为路由中的区域之一的路由。这是通过检查路由的 NetworkRegionID1 值是否等于 (-eq) NorthAmerica，或 (-or) NetworkRegionID2 值是否等于 NorthAmerica 实现的。只要该集合仅包含含有 NorthAmerica 区域的路由，就可将此集合通过管道传递到 **Remove-CsNetworkInterRegionRoute** cmdlet，后者会删除其中的每个路由。

    Get-CsNetworkInterRegionRoute | Where-Object {$_.NetworkRegionID1 -eq "NorthAmerica" -or $_.NetworkRegionID2 -eq "NorthAmerica"} | Remove-CsNetworkInterRegionRoute

## 详细说明

CAC 配置中的每个区域必须具有某种可访问其他每个区域的方式。虽然区域链接会对区域之间的连接设置带宽限制，并代表物理链接，但是路由可确定连接从一个区域到另一个区域将遍历的链接路径。此 cmdlet 可删除其中的某个路由关联。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Remove-CsNetworkInterRegionRoute** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsNetworkInterRegionRoute"}

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
<td><p>要删除的网络区域路由的唯一标识符。网络区域路由只能在全局范围创建，因此该标识符不需要指定范围。它包含一个字符串，此字符串是一个用于标识该路由的唯一名称。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkRegionRouteType 对象。接受通过管道传递的网络区域间路由对象的输入。

## 返回类型

此 cmdlet 不会返回值。它会删除一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkRegionRouteType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkInterRegionRoute](new-csnetworkinterregionroute.md)  
[Set-CsNetworkInterRegionRoute](set-csnetworkinterregionroute.md)  
[Get-CsNetworkInterRegionRoute](get-csnetworkinterregionroute.md)

