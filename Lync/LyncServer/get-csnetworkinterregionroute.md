---
title: Get-CsNetworkInterRegionRoute
TOCTitle: Get-CsNetworkInterRegionRoute
ms:assetid: 31c38d92-1cef-40fe-bd04-26e5b373703e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425817(v=OCS.15)
ms:contentKeyID: 49312423
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsNetworkInterRegionRoute

 

_**上一次修改主题：** 2015-03-09_

检索连接呼叫允许控制 (CAC) 配置中网络区域的一个或多个路由。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsNetworkInterRegionRoute [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsNetworkInterRegionRoute [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## 示例

## 示例 1

示例 1 检索 Identity 为 NA\_APAC\_Route 的路由。

    Get-CsNetworkInterRegionRoute -Identity NA_APAC_Route

## 示例 2

示例 2 中使用 Filter 参数检索 Identity 中任意位置包含字符串 APAC 的所有路由。

    Get-CsNetworkInterRegionRoute -Filter *APAC*

## 示例 3

此示例检索使用网络区域链接 NA\_EMEA 的所有区域路由。该命令首先调用 **Get-CsNetworkInterRegionRoute** cmdlet。调用此不带任何参数的 cmdlet 将检索通过 CAC 配置定义的所有路由。然后，将此路由集合通过管道传递到 **Where-Object** cmdlet。**Where-Object** cmdlet 将获取该集合，并检索该集合中其 NetworkRegionLinks 列表中具有值 NA\_EMEA 的所有项。

    Get-CsNetworkInterRegionRoute | Where-Object {$_.NetworkRegionLinks -eq "NA_EMEA"}

## 示例 4

示例 4 检索包括 NorthAmerica 区域在内的所有区域路由。该命令的第一部分是调用 **Get-CsNetworkInterRegionRoute** cmdlet。在无任何参数的情况下调用此 cmdlet 将检索所有区域路由。接下来，将该路由集合通过管道传递到 **Where-Object** cmdlet。**Where-Object** cmdlet 将该集合的范围缩小到仅包含将 NorthAmerica 定义为路由中的区域之一的路由。这一点是通过查看路由的 NetworkRegionID1 值是否等于 (-eq) NorthAmerica 或 (-or) NetworkRegionID2 值是否等于 NorthAmerica 实现的。

    Get-CsNetworkInterRegionRoute | Where-Object {$_.NetworkRegionID1 -eq "NorthAmerica" -or $_.NetworkRegionID2 -eq "NorthAmerica"}

## 详细说明

CAC 配置中的每个区域都必须有某种方式以访问其他每个区域。虽然区域链接会对区域之间的连接设置带宽限制，并代表物理链接，但是路由可确定连接从一个区域到另一个区域将遍历的链接路径。此 cmdlet 检索有关这些路由关联的信息。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsNetworkInterRegionRoute** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsNetworkInterRegionRoute"}

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
<td><p><em>Filter</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>通过此字符串可根据将 Identity 值与以值的方式传递给此参数的通配符字符串相匹配来检索路由。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>要检索的网络区域路由的唯一标识符。仅会在全局范围创建网络地区路由，因此该标识符不需要指定范围。它包含一个字符串，此字符串是一个用于标识特定路由的唯一名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本，而不是从中央管理存储本身检索网络区域间路由信息。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

此 cmdlet 返回一个或多个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkRegionRouteType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkInterRegionRoute](new-csnetworkinterregionroute.md)  
[Remove-CsNetworkInterRegionRoute](remove-csnetworkinterregionroute.md)  
[Set-CsNetworkInterRegionRoute](set-csnetworkinterregionroute.md)

