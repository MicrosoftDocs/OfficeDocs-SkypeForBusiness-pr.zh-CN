---
title: Get-CsNetworkRegionLink
TOCTitle: Get-CsNetworkRegionLink
ms:assetid: dc5cb988-13e2-4af4-8b36-0aaa58ebf1c5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398972(v=OCS.15)
ms:contentKeyID: 49314449
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsNetworkRegionLink

 

_**上一次修改主题：** 2015-03-09_

检索为呼叫允许控制 (CAC) 配置的网络区域间的一个或多个链接。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsNetworkRegionLink [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsNetworkRegionLink [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## 示例

## 示例 1

示例 1 检索在 Lync Server 部署内定义的所有网络区域链接。

    Get-CsNetworkRegionLink

## 示例 2

示例 2 检索有关（最多）一个 Identity 为 NA\_EMEA 的网络区域链接的信息。

    Get-CsNetworkRegionLink -Identity NA_EMEA

## 示例 3

在此示例中，我们使用 Filter 参数来检索链接名称 (Identity) 中包含字符串 EMEA 的所有网络区域链接。请注意，在字符串 EMEA 前后各有一个 \* 字符。这意味着，该字符串前后可有任意一个或多个字符，只是字符串 EMEA 必须包含在 Identity 中。这将检索名称为 NA\_EMEA、EMEA\_APAC 和 EMEA2\_SA 等的链接。

    Get-CsNetworkRegionLink -Filter *EMEA*

## 示例 4

此示例检索 EMEA 为链接的两个区域之一的所有网络区域链接。此示例首先调用不带参数的 **Get-CsNetworkRegionLink** cmdlet，以检索所有区域链接。然后将该链接集合通过管道传递到 **Where-Object** cmdlet。**Where-Object** cmdlet 将逐个查看该集合的每个成员，检查 NetworkRegionID1 和 NetworkRegionID2 属性的值。如果这两个属性值之一等于 EMEA，也就是说，如果 NetworkRegionID1 等于 (-eq) EMEA 或 (-or) NetworkRegionID2 等于 (-eq) EMEA，则我们将该项保留在集合中，并将其显示出来。

    Get-CsNetworkRegionLink | Where-Object {$_.NetworkRegionID1 -eq "EMEA" -or $_.NetworkRegionID2 -eq "EMEA"}

## 详细说明

网络内的区域通过物理 WAN 连接进行链接。此 cmdlet 可检索在 Lync Server 部署的网络配置设置内定义的一个或多个区域链接。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsNetworkRegionLink** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsNetworkRegionLink"}

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
<td><p>接受用于检索网络链接（通过将 Identity 的值与通配符字符串匹配）的通配符字符串。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>要检索的网络区域链接的唯一标识符。由于仅在全局范围创建网络区域链接，因此此标识符不需要指定范围。此标识符包含一个字符串，作为标识该链接的唯一名称。（请注意，该值与 NetworkRegionLinkID 相同。）</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本，而不是从中央管理存储本身检索网络区域链接信息。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

检索一个或多个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionLinkType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkRegionLink](new-csnetworkregionlink.md)  
[Remove-CsNetworkRegionLink](remove-csnetworkregionlink.md)  
[Set-CsNetworkRegionLink](set-csnetworkregionlink.md)

