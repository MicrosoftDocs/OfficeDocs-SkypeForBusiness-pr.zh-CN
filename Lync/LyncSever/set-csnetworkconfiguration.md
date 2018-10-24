---
title: Set-CsNetworkConfiguration
TOCTitle: Set-CsNetworkConfiguration
ms:assetid: d54dc154-c092-4be9-8656-f7fec3fbd835
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398927(v=OCS.15)
ms:contentKeyID: 49314370
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsNetworkConfiguration

 

_**上一次修改主题：** 2015-03-09_

修改网络配置的设置。此 cmdlet 通常用于启用或禁用通话允许控制 (CAC)。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsNetworkConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsNetworkConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-BWPolicyProfiles <PSListModifier>] [-Confirm [<SwitchParameter>]] [-EnableBandwidthPolicyCheck <$true | $false>] [-Force <SwitchParameter>] [-InterNetworkRegionRoutes <PSListModifier>] [-InterNetworkSitePolicies <PSListModifier>] [-MediaBypassSettings <MediaBypassSettingsType>] [-NetworkRegionLinks <PSListModifier>] [-NetworkRegions <PSListModifier>] [-NetworkSites <PSListModifier>] [-Subnets <PSListModifier>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例中的命令将针对整个 CAC 配置运行验证检查，然后（取决于您对返回的警告提示的响应）启用 CAC。如果在已启用 CAC（也就是说，EnableBandwidthPolicyCheck 属性为 True）的情况下运行此命令，将只运行验证检查。

    Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck $True

## 详细说明

网络配置对象包含 Lync Server 部署内整个 CAC 配置的所有设置，以及媒体旁路设置。可以使用此 cmdlet 修改 CAC 配置的任何部分；如果需要更改媒体旁路设置，则必须使用此 cmdlet。但是，修改大部分 CAC 配置设置时，建议使用特定于对象类型的 cmdlet。例如，要修改网络区域，应使用以名词 CsNetworkRegion 结尾的 cmdlet，而不使用此 cmdlet 的 NetworkRegions 参数。

此 cmdlet 主要用于启用（和禁用）CAC，并应用媒体旁路设置。设置完配置所需的各种组件（例如，区域、站点和子网）后，必须先启用该配置，才能使其生效。为执行此操作，只需将 EnableBandwidthPolicyCheck 参数设置为 True。请注意，在运行此 cmdlet 时将 EnableBandwidthPolicyCheck 设置为 True 并不会立即启用 CAC。启用 CAC 之前，将执行一系列验证检查，以确保正确配置安装。安装过程中出现的任何错误或异常都会以警告的形式进行提示，询问是否要在存在问题的情况下继续启用 CAC。如果选择继续（按 Enter 或 Y），将继续进行验证，如果发现其他问题，会再次提示您。

如果运行整个验证过程，在每次出现警告时均选择继续，会将 EnableBandwidthPolicyCheck 设置为 True 并启用 CAC，但是在解决这些问题之前，CAC 很可能无法按预期工作。如果在验证过程中的任意时刻选择停止验证（在出现警告提示时按 N），验证将结束，EnableBandwidthPolicyCheck 的值也将保持为 False（默认值）。

如果 EnableBandwidthPolicyCheck 已设置为 True，可以调用 **Set-CsNetworkConfiguration** cmdlet 并向 EnableBandwidthPolicyCheck 参数传递 True 值，以便在不修改任何设置的前提下运行验证。此外，将 EnableBandwidthPolicyCheck 设置为 True 时，通过调用 **Set-CsNetworkConfiguration** cmdlet 尝试做出的任何更改，都会导致再次运行验证检查。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsNetworkConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsNetworkConfiguration"}

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
<td><p><em>BWPolicyProfiles</em></p></td>
<td><p>可选</p></td>
<td><p>PSListModifier</p></td>
<td><p>可以分配给站点、站点间策略和网络区域链接的所有带宽策略配置文件的集合。每个带宽策略配置文件均包含音频和/或视频连接的带宽限制（总体限制和会话限制）。通过调用 <strong>Get-CsNetworkBandwidthPolicyProfile</strong> cmdlet 可以检索带宽策略配置文件的完整列表。</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableBandwidthPolicyCheck</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>将此参数设置为 True 将针对整个 CAC 配置运行验证检查。如果通过所有验证检查，或选择忽略所有警告，将启用 CAC。如果未通过某项验证检查，可以选择停止验证，EnableBandwidthPolicyCheck 的值将保持不变。在运行验证检查之前，必须先在每对网络区域之间定义区域路由。</p>
<p>将该值设置为 False 将禁用 CAC。</p>
<p>默认值：False</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>此参数不接收任何值。如果包含此参数，对此配置所做的任何更改（包括启用该配置）都将直接生效，不会出现警告，也不会对其进行验证检查。</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>XdsIdentity</p></td>
<td><p>该值将始终为 Global。</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>NetworkConfigurationSettings</p></td>
<td><p>对网络配置对象的引用。该对象的类型必须是 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkConfigurationSettings，可以通过调用 <strong>Get-CsNetworkConfiguration</strong> cmdlet 来检索该对象类型。</p></td>
</tr>
<tr class="odd">
<td><p><em>InterNetworkRegionRoutes</em></p></td>
<td><p>可选</p></td>
<td><p>PSListModifier</p></td>
<td><p>CAC 配置内定义的所有网络区域路由的集合。可以通过调用 <strong>Get-CsNetworkInterRegionRoute</strong> cmdlet 检索该集合的所有成员。</p></td>
</tr>
<tr class="even">
<td><p><em>InterNetworkSitePolicies</em></p></td>
<td><p>可选</p></td>
<td><p>PSListModifier</p></td>
<td><p>CAC 配置内定义的网络站点间策略的集合。可以通过调用 <strong>Get-CsNetworkInterSitePolicy</strong> cmdlet 检索该集合的所有成员。</p></td>
</tr>
<tr class="odd">
<td><p><em>MediaBypassSettings</em></p></td>
<td><p>可选</p></td>
<td><p>MediaBypassSettingsType</p></td>
<td><p>对定义 CAC 配置的全局媒体旁路设置的对象的引用。设置该值将覆盖所有现有媒体旁路设置。通过调用 <strong>New-CsNetworkMediaBypassConfiguration</strong> cmdlet 并将新配置设置分配给某个变量可获取该对象引用。将此变量传递给 MediaBypassSettings 参数可更改全局媒体旁路设置。</p></td>
</tr>
<tr class="even">
<td><p><em>NetworkRegionLinks</em></p></td>
<td><p>可选</p></td>
<td><p>PSListModifier</p></td>
<td><p>CAC 配置内定义的网络区域链接的集合。每个网络区域链接都定义了存在于两个区域间的连接，以及可应用于这两个区域间的连接的所有带宽限制。可以通过调用 <strong>Get-CsNetworkRegionLink</strong> cmdlet 检索该集合的所有成员。</p></td>
</tr>
<tr class="odd">
<td><p><em>NetworkRegions</em></p></td>
<td><p>可选</p></td>
<td><p>PSListModifier</p></td>
<td><p>CAC 配置内定义的网络区域（其中每个区域均代表网络中的一个中心或中枢）的集合。可以通过调用 <strong>Get-CsNetworkRegion</strong> cmdlet 检索该集合的所有成员。</p></td>
</tr>
<tr class="even">
<td><p><em>NetworkSites</em></p></td>
<td><p>可选</p></td>
<td><p>PSListModifier</p></td>
<td><p>CAC 配置内定义的网络站点（其中每个站点均代表区域中的一个办公室或位置）的集合。可以通过调用 <strong>Get-CsNetworkSite</strong> cmdlet 检索该集合的所有成员。</p></td>
</tr>
<tr class="odd">
<td><p><em>Subnets</em></p></td>
<td><p>可选</p></td>
<td><p>PSListModifier</p></td>
<td><p>CAC 配置内定义的网络子网（其中每个子网均关联一个终结点和一个站点）的集合。可以通过调用 <strong>Get-CsNetworkSubnet</strong> cmdlet 检索该集合的所有成员。</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkConfigurationSettings 对象。接受通过管道传递的网络配置对象的输入。

## 返回类型

**Set-CsNetworkConfiguration** cmdlet 不会返回值或对象。此 cmdlet 会修改 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.NetworkConfigurationSettings 对象的实例。

## 另请参阅

#### 其他资源

[Remove-CsNetworkConfiguration](remove-csnetworkconfiguration.md)  
[Get-CsNetworkConfiguration](get-csnetworkconfiguration.md)  
[Get-CsNetworkSite](get-csnetworksite.md)  
[Get-CsNetworkRegionLink](get-csnetworkregionlink.md)  
[Get-CsNetworkInterSitePolicy](get-csnetworkintersitepolicy.md)  
[Get-CsNetworkInterRegionRoute](get-csnetworkinterregionroute.md)  
[Get-CsNetworkRegion](get-csnetworkregion.md)  
[Get-CsNetworkSubnet](get-csnetworksubnet.md)  
[Get-CsNetworkBandwidthPolicyProfile](get-csnetworkbandwidthpolicyprofile.md)  
[New-CsNetworkMediaBypassConfiguration](new-csnetworkmediabypassconfiguration.md)

