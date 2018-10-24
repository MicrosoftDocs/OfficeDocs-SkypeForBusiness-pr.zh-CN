---
title: New-CsNetworkSite
TOCTitle: New-CsNetworkSite
ms:assetid: 55134dd4-eb2b-483b-8b3d-e9e42ac1acc2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398365(v=OCS.15)
ms:contentKeyID: 49312881
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsNetworkSite

 

_**上一次修改主题：** 2015-03-09_

Creates a new network site for use with call admission control (CAC) or Enhanced 9-1-1 (E9-1-1). 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsNetworkSite -Identity <XdsGlobalRelativeIdentity> <COMMON PARAMETERS>

    New-CsNetworkSite -NetworkSiteID <String> <COMMON PARAMETERS>

    COMMON PARAMETERS: -NetworkRegionID <String> [-BWPolicyProfileID <String>] [-BypassID <String>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-EnableLocationBasedRouting <$true | $false>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-LocationPolicy <String>] [-VoiceRoutingPolicy <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In this example a new network site named Vancouver is created. The site name is specified as the value for the Identity parameter. A value is also specified for the NetworkRegionID parameter, which associates the site with the region (in this example NorthAmerica). A BypassID value will be automatically generated. Manually setting a value for BypassID is not recommended.

Notice that the command in this example did not include the BWPolicyProfileID parameter. Unless (or until) a value is added to this site later using the **Set-CsNetworkSite** cmdlet, it will have no bandwidth limitations for media connections.

    New-CsNetworkSite -Identity Vancouver -NetworkRegionID NorthAmerica

## EXAMPLE 2

In Example 2 we create a new network site named Paris. The site name is specified as the value for the Identity parameter. As in Example 1 we also specify a value for the NetworkRegionID, this time the region EMEA. Once again we are following the recommended path by allowing the cmdlet to generate the BypassID. Unlike Example 1, this example also specifies a value for the BWPolicyProfileID parameter: LowBWLimits. The policies associated with that profile will be used for this site.

    New-CsNetworkSite -Identity Paris -NetworkRegionID EMEA -BWPolicyProfileID LowBWLimits

## Detailed Description

Network sites are the offices or locations configured within each region of a CAC or E9-1-1 deployment. This cmdlet creates a new site and optionally associates it with a region. For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver. A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsNetworkSite** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsNetworkSite"}

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
<th>Parameter</th>
<th>Required</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>A unique identifier for the newly created network site. Sites are created only at the global scope, so this identifier does not need to specify a scope. Instead, it contains a string that is unique among all network sites within the Lync Server deployment.</p></td>
</tr>
<tr class="even">
<td><p><em>NetworkRegionID</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The Identity of the network region that this site is associated with. This parameter must contain a value if you want to provide a BypassID (either through auto-generation or manually), or if the EnableBandwidthPolicyCheck property of the network configuration is True. You can retrieve the network configuration settings by calling the <strong>Get-CsNetworkConfiguration</strong> cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>NetworkSiteID</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>This value is the same as the Identity. You cannot specify both an Identity and a NetworkSiteID; a value entered for one will be automatically used for both.</p></td>
</tr>
<tr class="even">
<td><p><em>BWPolicyProfileID</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The Identity of the bandwidth policy profile that will define the bandwidth limitations for this site. You can retrieve a list of available profiles by calling the <strong>Get-CsNetworkBandwidthPolicyProfile</strong> cmdlet.</p>
<p>If you specify a value for this parameter, you must also specify a value for the NetworkRegionID parameter.</p></td>
</tr>
<tr class="odd">
<td><p><em>BypassID</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A globally unique identifier (GUID). This GUID is used to map network sites to media bypass settings within a CAC or E9-1-1 network configuration. (Use this BypassID value in the call to the <strong>New-CsNetworkMediaBypassConfiguration</strong> cmdlet.)</p>
<p>If you do not specify a value for this parameter, a value will be automatically generated, but only if you supply a value for the NetworkRegionID parameter. If you do not supply a NetworkRegionID parameter, no BypassID will be generated. You also cannot explicitly supply a value for the BypassID parameter without also supplying a value for the NetworkRegionID parameter.</p>
<p>If you explicitly specify a value, it must be in the format of a GUID (for example, 3b24a047-dce6-48b2-9f20-9fbff17ed62a). Auto-generation is recommended. If you manually enter a value, you will receive a confirmation prompt to verify that you don’t want to auto-generate the value.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A string that describes the site. This parameter can be used to provide a more descriptive explanation of what the site is for or where it is than can be expressed by the Identity alone.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableLocationBasedRouting</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, voice routing will be managed by taking into account the location of both the user placing the call and the user receiving the call. The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="odd">
<td><p><em>LocationPolicy</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The name of the location policy associated with this site. The location policy assigns specific E9-1-1 settings to the site. You can retrieve a list of location policies by calling the <strong>Get-CsLocationPolicy</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>VoiceRoutingPolicy</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Per-user voice routing policy to be assigned to the site. For example:</p>
<p>-VoiceRoutingPolicy &quot;RedmondVoiceRouting”</p>
<p>Note that you must specify a per-user policy; global and/or site policies cannot be assigned tio a site using the VoiceRoutingPolicy parameter.</p>
<p>This parameter was introduced in the February, 2013 release of Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

Create an object of type Microsoft.Rtc.Management.WritableConfig.Settings.NetworkConfiguration.DisplayNetworkSiteType.

## 另请参阅

#### 其他资源

[Remove-CsNetworkSite](remove-csnetworksite.md)  
[Set-CsNetworkSite](set-csnetworksite.md)  
[Get-CsNetworkSite](get-csnetworksite.md)  
[Get-CsNetworkBandwidthPolicyProfile](get-csnetworkbandwidthpolicyprofile.md)  
[New-CsNetworkMediaBypassConfiguration](new-csnetworkmediabypassconfiguration.md)  
[Get-CsLocationPolicy](get-cslocationpolicy.md)  
[Get-CsNetworkConfiguration](get-csnetworkconfiguration.md)

