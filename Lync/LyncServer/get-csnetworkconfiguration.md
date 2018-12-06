---
title: Get-CsNetworkConfiguration
TOCTitle: Get-CsNetworkConfiguration
ms:assetid: 08bc8eca-b244-4d5e-b089-1cc95605ba14
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398140(v=OCS.15)
ms:contentKeyID: 49311921
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsNetworkConfiguration

 

_**上一次修改主题：** 2015-03-09_

检索呼叫允许控制 (CAC)、增强型 9-1-1 (E9-1-1) 和媒体旁路的全局设置。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsNetworkConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsNetworkConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## 示例

## 示例 1

此示例检索网络配置设置。仅在全局范围内定义这些设置，因此仅返回一个项。

    Get-CsNetworkConfiguration

## 示例 2

只存在一组全局应用的媒体旁路设置。这些设置存储为总体网络配置的一部分。此命令首先通过调用 **Get-CsNetworkConfiguration** cmdlet 检索该配置，然后检索配置的 MediaBypassSettings 属性。

    (Get-CsNetworkConfiguration).MediaBypassSettings

## 详细说明

网络配置对象包含媒体旁路的所有全局设置和 Lync Server 部署中整个 CAC 配置的所有全局设置，其中包括是否已启用该配置。可以使用此 cmdlet 检索这些配置和设置。但是，建议不要使用 EnableBandwidthPolicyCheck 和 MediaBypassSettings，而是使用此对象类型专用的 cmdlet 检索 CAC 配置设置。例如，若要检索网络区域，那么调用 **Get-CsNetworkRegion** cmdlet 然后检索该配置的 NetworkRegions 属性通常要比调用 **Get-CsNetworkConfiguration** cmdlet 然后再这样做更容易。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsNetworkConfiguration** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsNetworkConfiguration"}

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
<td><p>由于始终只会有一个网络配置，因此此 cmdlet 不需要此参数。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>将始终是“Global”。</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本，而不是从中央管理存储本身检索网络配置。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

**Get-CsNetworkConfiguration** cmdlet 将返回 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkConfigurationSettings 对象的实例。

## 另请参阅

#### 其他资源

[Remove-CsNetworkConfiguration](remove-csnetworkconfiguration.md)  
[Set-CsNetworkConfiguration](set-csnetworkconfiguration.md)  
[Get-CsNetworkSite](get-csnetworksite.md)  
[Get-CsNetworkRegionLink](get-csnetworkregionlink.md)  
[Get-CsNetworkInterSitePolicy](get-csnetworkintersitepolicy.md)  
[Get-CsNetworkInterRegionRoute](get-csnetworkinterregionroute.md)  
[Get-CsNetworkRegion](get-csnetworkregion.md)  
[Get-CsNetworkSubnet](get-csnetworksubnet.md)  
[Get-CsNetworkBandwidthPolicyProfile](get-csnetworkbandwidthpolicyprofile.md)

