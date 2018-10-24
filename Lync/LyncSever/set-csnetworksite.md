---
title: Set-CsNetworkSite
TOCTitle: Set-CsNetworkSite
ms:assetid: 221a099c-72c4-4eb0-8812-6b2b7639a9ee
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398295(v=OCS.15)
ms:contentKeyID: 49312237
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsNetworkSite

 

_**上一次修改主题：** 2015-03-09_

修改为呼叫允许控制 (CAC) 或增强型 9-1-1 (E9-1-1) 定义的现有网络站点。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsNetworkSite [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsNetworkSite [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-BWPolicyProfileID <String>] [-BypassID <String>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-EnableLocationBasedRouting <$true | $false>] [-Force <SwitchParameter>] [-LocationPolicy <String>] [-NetworkRegionID <String>] [-VoiceRoutingPolicy <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

在此示例中，修改名为 Vancouver 的网络站点。所修改站点的名称指定为 Identity 参数的值。Vancouver 站点被移到一个新区域，这要求更改 NetworkRegionID 参数，在此示例中将该参数更改为名为 Canada 的区域。由于已提供 NetworkRegionID，但没有为 BypassID 指定值，因此将自动生成 BypassID 值。先前存在的所有 BypassID 都将被覆盖。

    Set-CsNetworkSite -Identity Vancouver -NetworkRegionID Canada

## 示例 2

示例 2 只是修改与 Vancouver 站点关联的带宽策略配置文件。站点名称指定为 Identity 参数的值。然后，指定 BWPolicyProfileID 参数的值：LowBWLimits。与该配置文件关联的策略将用于此站点。

    Set-CsNetworkSite -Identity Vancouver - BWPolicyProfileID LowBWLimits

## 详细说明

网络站点是指在部署了 CAC 或 E9-1-1 的每个区域中配置的办公室或位置。此 cmdlet 用于修改现有站点的设置。这可能包括与该站点关联的区域、站点描述以及关联的带宽策略配置文件等项。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsNetworkSite** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsNetworkSite"}

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
<td><p><em>BWPolicyProfileID</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>用于定义此站点的限制的带宽策略配置文件的标识。您可以通过调用 <strong>Get-CsNetworkBandwidthPolicyProfile</strong> cmdlet 来检索可用配置文件的列表。</p>
<p>如果为此参数指定值，则还必须为 NetworkRegionID 参数指定值。</p></td>
</tr>
<tr class="even">
<td><p><em>BypassID</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>全局唯一标识符 (GUID)。此 GUID 用于将网络站点映射到 CAC 或 E9-1-1 网络配置中的媒体旁路设置。（可在调用 <strong>New-CsNetworkMediaBypassConfiguration</strong> cmdlet 时使用此 BypassID 值。）</p>
<p>如果为此参数指定值，则还必须为 NetworkRegionID 参数指定值。如果没有为此参数指定值，但指定了 NetworkRegionID，将会自动生成 BypassID。</p>
<p>如果显式指定值，则该值必须采用 GUID 的格式（例如，3b24a047-dce6-48b2-9f20-9fbff17ed62a）。建议您为 NetworkRegionID 提供值，并允许自动生成 BypassID 值。如果手动输入值，您将收到确认提示，要求您确认是否不希望自动生成值。</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>用于描述站点的字符串。此参数可用于说明站点用途或站点位置，与只用 Identity 表示相比，该说明更具描述性。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableLocationBasedRouting</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>设置为 True 时，将通过分析发出和接收呼叫的用户的位置来管理语音路由。默认值为 False。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>XdsGlobalRelativeIdentity</p></td>
<td><p>要修改的网络站点的唯一标识符。站点只能在全局范围创建，因此不需要指定范围，而只需指定网络站点 ID。</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>DisplayNetworkSiteType</p></td>
<td><p>对网络站点对象（类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.DisplayNetworkSiteType 的对象）的引用。可以通过调用 <strong>Get-CsNetworkSite</strong> cmdlet 来检索此对象。</p></td>
</tr>
<tr class="odd">
<td><p><em>LocationPolicy</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>与此站点关联的位置策略的名称。位置策略为站点分配特定的 E9-1-1 设置。要检索位置策略列表，请调用 <strong>Get-CsLocationPolicy</strong> cmdlet。</p></td>
</tr>
<tr class="even">
<td><p><em>NetworkRegionID</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>与此站点关联的网络区域的标识。如果要提供 BypassID（通过自动生成或手动输入），或者网络配置的 EnableBandwidthPolicyCheck 属性为 True，则此参数必须包含值。您可以通过调用 <strong>Get-CsNetworkConfiguration</strong> cmdlet 来检索网络配置设置。</p>
<p>如果此站点上已存在 BypassID，但您没有为 BypassID 参数指定值，则现有 BypassID 将被自动生成的 BypassID 覆盖。</p></td>
</tr>
<tr class="odd">
<td><p><em>VoiceRoutingPolicy</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>要分配给站点的每用户语音路由策略。例如：</p>
<p>-VoiceRoutingPolicy &quot;RedmondVoiceRouting”</p>
<p>请注意，您必须指定每用户策略；无法使用 VoiceRoutingPolicy 参数将全局和/或站点策略分配给站点。</p>
<p>此参数是在 Lync Server 2013 2013 年 2 月发行版中引入的。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.DisplayNetworkSiteType 对象。接受通过管道传递的网络站点对象的输入。

## 返回类型

此 cmdlet 不会返回值。它会修改一个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.DisplayNetworkSiteType 的对象。

## 另请参阅

#### 其他资源

[New-CsNetworkSite](new-csnetworksite.md)  
[Remove-CsNetworkSite](remove-csnetworksite.md)  
[Get-CsNetworkSite](get-csnetworksite.md)  
[Get-CsNetworkBandwidthPolicyProfile](get-csnetworkbandwidthpolicyprofile.md)  
[New-CsNetworkMediaBypassConfiguration](new-csnetworkmediabypassconfiguration.md)  
[Get-CsLocationPolicy](get-cslocationpolicy.md)  
[Get-CsNetworkConfiguration](get-csnetworkconfiguration.md)

