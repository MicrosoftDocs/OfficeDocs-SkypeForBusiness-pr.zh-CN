---
title: Get-CsAccessEdgeConfiguration
TOCTitle: Get-CsAccessEdgeConfiguration
ms:assetid: 75a8a7e9-728f-4abd-87e9-593713ae39ee
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398574(v=OCS.15)
ms:contentKeyID: 49313277
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsAccessEdgeConfiguration

 

_**上一次修改主题：** 2015-03-09_

Returns information about the configuration settings for computers running the 访问边缘服务 in your organization (also known as Access Edge servers). Access Edge servers provide a way for users outside your internal network to communicate with users inside your internal network. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsAccessEdgeConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsAccessEdgeConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

Example 1 demonstrates the basic use of the **Get-CsAccessEdgeConfiguration** cmdlet: calling the cmdlet without any additional parameters returns all the property values for your Access Edge server implementation. Note that there is no need to include the Identity or Filter parameters; that’s because there is only one set of Access Edge server configuration data.

    Get-CsAccessEdgeConfiguration

## EXAMPLE 2

Example 2 returns just three property values for your Access Edge server configuration: AllowAnonymousUsers; AllowFederatedUsers; and AllowOutsideUsers. To do this, the command first uses the **Get-CsAccessEdgeConfiguration** cmdlet to return all the Access Edge server property values. This information is then piped to the **Select-Object** cmdlet, which picks out only those properties that start with the string value "Allow". In turn, those are the only property values displayed on the screen.

    Get-CsAccessEdgeConfiguration | Select-Object Allow*

## EXAMPLE 3

The command shown in Example 3 returns the value of a single Access Edge server configuration property: EnablePartnerDiscovery. To do this, the **Get-CsAccessEdgeConfiguration** cmdlet is first called in order to return all the Access Edge server configuration property values. The call to the **Get-CsAccessEdgeConfiguration** cmdlet is enclosed in parentheses; this ensures that Windows PowerShell completes this command before doing anything else. After all the property values have been returned, standard "dot notation" (the object name followed by a period followed by a property name) is used to display the value of a single property: EnablePartnerDiscovery.

    (Get-CsAccessEdgeConfiguration).EnablePartnerDiscovery

## Detailed Description

Access Edge servers (also known as access proxy servers) provide a way for you to extend the capabilities of Lync Server to people who are not logged on to your internal network. For example, if you have remote users -- authenticated users who log on to Lync Server over the Internet rather than through the internal network -- you will need to set up an Access Edge server. Additionally, Edge Servers are required if you want to establish federation with another organization or if you want to give your users the right to communicate with people who have accounts with a public instant messaging service such as Yahoo\!, AOL, or MSN. Access Edge servers sit on the perimeter network, and are used to make and validate SIP connections between users inside and outside of your internal network.

In Lync Server, the Access Edge servers are managed by using a single, global collection of configuration settings. The **Get-CsAccessEdgeConfiguration** cmdlet enables you to return information about these global settings. Note that the property values returned by the **Get-CsAccessEdgeConfiguration** cmdlet will vary depending on the type of routing you have configured for your Edge Servers. For details, see the **Set-CsAccessEdgeConfiguration** Help topic.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsAccessEdgeConfiguration** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsAccessEdgeConfiguration"}

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
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to use wildcards when specifying the Access Edge configuration settings to be returned. Because you can only have a single, global instance of these settings there is little reason to use the Filter parameter. However, if you prefer, you can use syntax similar to this to retrieve the global settings: -Identity &quot;g*&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier of the Access Edge configuration settings to be returned. Because you can only have a single, global instance of these settings, you do not have to include the Identity when calling the <strong>Get-CsAccessEdgeConfiguration</strong> cmdlet. However, you can use the following syntax to retrieve the global settings: -Identity global.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the Access Edge configuration data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsAccessEdgeConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsAccessEdgeConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayAccessEdgeSettingsDnsSrvRouting object or the Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayAccessEdgeSettingsDefaultRoute object.

## 另请参阅

#### 其他资源

[Set-CsAccessEdgeConfiguration](set-csaccessedgeconfiguration.md)

