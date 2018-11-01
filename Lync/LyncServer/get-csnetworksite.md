---
title: Get-CsNetworkSite
TOCTitle: Get-CsNetworkSite
ms:assetid: 9627869d-101f-4668-bee2-01fce1d84cbd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398766(v=OCS.15)
ms:contentKeyID: 49313657
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsNetworkSite

 

_**上一次修改主题：** 2015-03-09_

检索为呼叫允许控制 (CAC) 或增强型 9-1-1 (E9-1-1) 定义的一个或多个网络站点。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsNetworkSite [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsNetworkSite [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## 示例

## 示例 1

调用不带任何参数的 **Get-CsNetworkSite** cmdlet 将返回 Lync Server 部署中为 CAC 或 E9-1-1 配置的所有网络站点。

    Get-CsNetworkSite

## 示例 2

此命令检索 Identity（根据定义，即 NetworkSiteID）为 Redmond 的站点。

    Get-CsNetworkSite -Identity Redmond

## 示例 3

示例 3 中的命令调用带有 Filter 参数的 **Get-CsNetworkSite** cmdlet。Filter 参数的值为 NA\*，这意味着此命令将检索 Identity 以字符串 NA 开头且后跟有任意数目的字符的所有站点。这将返回 NARedmond、NAVancouver 和 NAChicago 等站点。

    Get-CsNetworkSite -Filter NA*

## 示例 4

示例 4 使用两个 cmdlet（即 **Get-CsNetworkSite** cmdlet 和 **Where-Object** cmdlet）来检索属于 NorthAmerica 区域的一部分的所有站点。该命令首先调用不带任何参数的 **Get-CsNetworkSite** cmdlet，以检索所有网络站点。然后，将该站点集合通过管道传递到 **Where-Object** cmdlet，后者会对该集合进行筛选，并在 NetworkRegionID 属性等于 (-eq) NorthAmerica 的集合中查找所有站点。

    Get-CsNetworkSite | Where-Object {$_.NetworkRegionID -eq "NorthAmerica"}

## 详细说明

网络站点是指在部署了 CAC 或 E9-1-1 的每个区域中配置的办公室或位置。此 cmdlet 可检索一个或多个现有站点的设置。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsNetworkSite** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsNetworkSite"}

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
<td><p>一个通配符字符串，使您可以通过将站点 Identity 与 Filter 匹配来检索多个站点。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>要检索的网络站点的唯一标识符。站点只能在全局范围创建，因此不需要指定范围，只需要指定站点 ID。（请注意，该值与网络站点的 NetworkSiteID 相同。）</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本，而不是从中央管理存储本身检索网络站点信息。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

检索一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.DisplayNetworkSiteType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkSite](new-csnetworksite.md)  
[Remove-CsNetworkSite](remove-csnetworksite.md)  
[Set-CsNetworkSite](set-csnetworksite.md)

