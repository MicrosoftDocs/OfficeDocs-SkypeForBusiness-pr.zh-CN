---
title: Get-CsNetworkRegion
TOCTitle: Get-CsNetworkRegion
ms:assetid: 5c9eef10-16c1-45f7-ae7b-2bee0965b421
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398406(v=OCS.15)
ms:contentKeyID: 49312977
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsNetworkRegion

 

_**上一次修改主题：** 2015-03-09_

检索一个或多个网络区域。网络区域代表企业网络中的网络集线器或主干网。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsNetworkRegion [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsNetworkRegion [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## 示例

## 示例 1

示例 1 检索为组织定义的所有网络地区。

    Get-CsNetworkRegion

## 示例 2

示例 2 检索 Identity 为 NorthAmerica 的网络地区。由于标识是唯一的，因而此命令最多会检索到一个网络地区。

    Get-CsNetworkRegion -Identity NorthAmerica

## 示例 3

此示例检索标识以字符串“America”结尾的所有网络地区。这会检索标识为 NorthAmerica、SouthAmerica 和 CentralAmerica 等的地区。

    Get-CsNetworkRegion | Where-Object {$_.CentralSite -eq "site:Redmond"}

## 示例 4

此示例检索与中央站点 Redmond 关联的所有网络区域。该命令首先调用不带任何参数的 **Get-CsNetworkRegion** cmdlet，以便检索为 Lync Server 部署定义的所有网络区域的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet。**Where-Object** cmdlet 会筛选该集合，以便仅返回 CentralSite 值等于 (-eq) site:Redmond 的项目（网络区域）。

    Get-CsNetworkRegion | Where-Object {$_.CentralSite -eq "site:Redmond"}

## 详细说明

网络区域将跨多个地理区域的网络的各个部分相互连接起来。每个网络区域都必须与中央站点关联。使用此 cmdlet 可检索有关一个或多个网络区域的信息，包括确定是否允许音频和视频连接使用备用路径以及将区域内的站点与媒体旁路配置相关联的中央站点和设置。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsNetworkRegion** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsNetworkRegion"}

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
<td><p>通过此参数可以对为组织配置的所有网络地区的 Identity 执行通配符搜索。使用通配符可以对 Identity 的任何部分进行筛选。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>要检索的网络地区的唯一标识符。Identity 是字符串，唯一标识地区。（请注意，Identity 与 NetworkRegionID 相同。）</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本，而不是从中央管理存储本身检索网络区域信息。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

返回一个或多个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkRegionType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkRegion](new-csnetworkregion.md)  
[Remove-CsNetworkRegion](remove-csnetworkregion.md)  
[Set-CsNetworkRegion](set-csnetworkregion.md)

