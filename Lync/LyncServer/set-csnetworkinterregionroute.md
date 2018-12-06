---
title: Set-CsNetworkInterRegionRoute
TOCTitle: Set-CsNetworkInterRegionRoute
ms:assetid: 5d9da3c0-56fc-401d-baf3-ed6c0f50f53d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398410(v=OCS.15)
ms:contentKeyID: 49312985
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsNetworkInterRegionRoute

 

_**上一次修改主题：** 2015-03-09_

修改呼叫允许控制 (CAC) 配置中连接网络区域的现有路由。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsNetworkInterRegionRoute [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsNetworkInterRegionRoute [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-NetworkRegionID1 <String>] [-NetworkRegionID2 <String>] [-NetworkRegionLinkIDs <String>] [-NetworkRegionLinks <PSListModifier>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例通过更改沿路由遍历的地区链接，对路由 NA\_APAC\_Route 进行修改。NetworkRegionLinkIDs 参数与“NA\_SA,SA\_APAC”的值结合使用，这会替换该字符串中指定这两者的所有现有链接。

    Set-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionLinkIDs "NA_SA,SA_APAC"

## 示例 2

与示例 1 一样，示例 2 也可修改 NA\_APAC\_Route 路由中的链接。但是，在该示例中并不是使用 NetworkRegionLinkIDs 参数替换该路由的所有链接，而是使用 NetworkRegionLinks 参数将链接添加到该路由中已存在的链接的列表中。在此示例中，链接 SA\_EMEA 会添加到路由中。语法 @{add=\<link\>} 会将元素添加到链接列表。您还可以使用语法 @{replace=\<link\>} 替换由 \<link\> 指定的所有现有链接（本质上与使用 NetworkRegionLinkIDs 的行为相同），或使用语法 @{remove=\<link\>} 从列表中删除链接。

    Set-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionLinks @{add="SA_EMEA"}

## 示例 3

示例 3 可修改名为 NA\_Route5 的路由。此示例可更改组成此路由的一个区域。NetworkRegionID2 参数用于指定新区域，而 NetworkRegionLinkIDs 参数用于创建一个新链接列表以连接此路由的各个区域。

    Set-CsNetworkInterRegionRoute -Identity NA_Route5 -NetworkRegionID2 SouthAmerica -NetworkRegionLinkIDs "NA_SA,SA_APAC"

## 详细说明

CAC 配置中的每个地区都必须有一些访问所有其他地区的方式。虽然区域链接会对区域之间的连接设置带宽限制，并代表物理链接，但是路由可确定连接从一个区域到另一个区域将遍历的链接路径。此 cmdlet 可修改该路由关联。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsNetworkInterRegionRoute** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsNetworkInterRegionRoute"}

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
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>禁止显示任何本该在进行更改前显示的确认提示。</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>XdsGlobalRelativeIdentity</p></td>
<td><p>要修改的网络地区路由的唯一标识符。仅会在全局范围创建网络地区路由，因此该标识符不需要指定范围。而是包含一个字符串，该字符串是标识该路由的唯一名称。</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>内部网络地区路由类型</p></td>
<td><p>现有地区路由的对象引用。此对象的类型必须为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkRegionRouteType，它可以通过呼叫 <strong>Get-CsNetworkInterRegionRoute</strong> cmdlet 进行检索。</p></td>
</tr>
<tr class="odd">
<td><p><em>NetworkRegionID1</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>通过此路由连接的两个地区的其中一个的 Identity (NetworkRegionID)。传递到此参数的值必须是与 NetworkRegionID2 参数的值不同的地区。（换句话说，不能将某个地区路由到自身。）另外，NetworkRegionID1 和 NetworkRegionID2 的组合必须是唯一的（例如，您不能定义连接北美和 EMEA 的两个路由）。</p></td>
</tr>
<tr class="even">
<td><p><em>NetworkRegionID2</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>通过此路由连接的两个地区的其中一个的 Identity (NetworkRegionID)。传递到此参数的值必须是与 NetworkRegionID1 参数的值不同的地区。（换句话说，不能将某个地区路由到自身。）另外，NetworkRegionID1 和 NetworkRegionID2 的组合必须是唯一的（例如，您不能定义连接北美和 EMEA 的两个路由）。</p></td>
</tr>
<tr class="odd">
<td><p><em>NetworkRegionLinkIDs</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>允许将此路由的所有链接指定为逗号分隔值组成的字符串。这些值是各个地区链接的标识 (NetworkRegionLinkIDs)。如果为 NetworkRegionLinkIDs 和 NetworkRegionLinks 均输入值，将忽略 NetworkRegionLinkIDs。使用此参数修改的所有链接将替换路由中的所有现有链接。</p></td>
</tr>
<tr class="even">
<td><p><em>NetworkRegionLinks</em></p></td>
<td><p>可选</p></td>
<td><p>PSListModifier</p></td>
<td><p>一个列表对象，其中包含应用于此路由的地区链接的标识 (NetworkRegionLinkIDs)。对于此 cmdlet，除了能够让您替换此路由的所有现有链接这一点相同外，此参数与 NetworkRegionLinkIDs 有所不同，您还可以添加或删除单个链接。</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkRegionRouteType 对象。接受通过管道传递的网络区域间路由对象的输入。

## 返回类型

此 cmdlet 不返回值。它会修改一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.InterNetworkRegionRouteType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkInterRegionRoute](new-csnetworkinterregionroute.md)  
[Remove-CsNetworkInterRegionRoute](remove-csnetworkinterregionroute.md)  
[Get-CsNetworkInterRegionRoute](get-csnetworkinterregionroute.md)

