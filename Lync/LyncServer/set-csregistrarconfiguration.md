---
title: Set-CsRegistrarConfiguration
TOCTitle: Set-CsRegistrarConfiguration
ms:assetid: 9616b967-09dd-470d-8d0a-acce1ff4fbf9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398764(v=OCS.15)
ms:contentKeyID: 49313659
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsRegistrarConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies the property values in an existing collection of Registrar configuration settings. Registrars are used to authenticate logon requests and to maintain information about user status and availability. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsRegistrarConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsRegistrarConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-BackupStoreUnavailableThreshold <TimeSpan>] [-Confirm [<SwitchParameter>]] [-DefaultEndpointExpiration <Int32>] [-EnableDHCPServer <$true | $false>] [-Force <SwitchParameter>] [-MaxEndpointExpiration <Int32>] [-MaxEndpointsPerUser <UInt16>] [-MaxUserCount <UInt64>] [-MinEndpointExpiration <Int32>] [-PoolState <FailedOver | Active | FailingOver | FailingBack>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 modifies the Registrar configuration settings applied to the Redmond site (-Identity site:Redmond). In this example, the value of the EnableDHCPServer property is set to True.

    Set-CsRegistrarConfiguration -Identity site:Redmond -EnableDHCPServer $True

## EXAMPLE 2

In Example 2, any Registrar configuration settings that allow users more than 8 endpoints are modified. To accomplish this, the command first calls the **Get-CsRegistrarConfiguration** cmdlet without any parameters; this returns a collection of all the Registrar configuration settings used in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those settings where the MaxEndpointsPerUser property is greater than (-gt) 8. Finally, the filtered collection is piped to the **Set-CsRegistrarConfiguration** cmdlet, which sets the maximum number of endpoints for each item in that collection to 8.

    Get-CsRegistrarConfiguration | Where-Object {$_.MaxEndpointsPerUser -gt 8} | Set-CsRegistrarConfiguration -MaxEndpointsPerUser 8

## EXAMPLE 3

The command shown in Example 3 disables client registration via DHCP for each site in the organization that hosts a collection of Registrar configuration settings. To do this, the command calls the **Get-CsRegistrarConfiguration** cmdlet along with the Filter parameter; the parameter value "site:\*" limits the returned data to settings that have been configured at the site scope. This collection is then piped to the **Set-CsRegistrarConfiguration** cmdlet, which uses the EnableDHCPServer parameter and the parameter value $False to prevent clients from using a DHCP server to locate a Registrar.

    Get-CsRegistrarConfiguration -Filter "site:*"| Set-CsRegistrarConfiguration -EnableDHCPServer $False

## Detailed Description

The Registrar is perhaps the most important component in Lync Server; after all, without a Registrar, users would not be able to log on to the system, and Lync Server would not be able to keep track of users and their current status. When a user logs on to Lync Server, the endpoint the user is logging on from sends a REGISTER request to the Registrar; in turn, the server responds by challenging the client device for authentication credentials. If the client passes the challenge (that is, if the client presents a valid set of credentials), then the user is authenticated and endpoint information such as IP address, port, and user name is logged in the registration database. When a user logs off, this information is then removed from the database. In between log on and log off, the Registrar keeps status information up-to-date and helps to route messages to and from the user.

Registrar configuration settings are used to help manage endpoints and endpoint subscriptions; these settings can be applied at the global, site, or service scope. (Service scoped-settings are only used with the Registrar service.) The **Set-CsRegistrarConfiguration** cmdlet can be used to modify any (or all) of the Registrar configuration collections currently in use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsRegistrarConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsRegistrarConfiguration"}

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
<td><p><em>BackupStoreUnavailableThreshold</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>Specifies the amount of time the system will wait before determining that the backup store is unavailable; at that point, users will be placed in survivability mode. The default value is 30 minutes (00:30:00).</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>DefaultEndpointExpiration</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>When endpoints log on they have the option of requesting an expiration timeout; this specifies the time interval that an endpoint can remain logged onto the system before it must contact the server and request an extension. The DefaultEndpointExpiration property represents the expiration timeout interval for clients that do not request a specific timeout value.</p>
<p>The DefaultEndpointExpiration must be between 300 (5 minutes) and 900 (15 minutes). The default value is 600 (10 minutes).</p></td>
</tr>
<tr class="even">
<td><p><em>EnableDHCPServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether endpoints can use DHCP servers to locate a Registrar. If True, clients will send a DHCP Inform message when they first start; the DHCP server will respond by sending the fully qualified domain name (FQDN) of a Registrar that can be used to log on the user.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the Registrar configuration settings to be modified. To modify the global settings, use this syntax: -Identity global. To modify settings configured at the site scope, use syntax similar to this: -Identity site:Redmond. To modify settings at the service level, use syntax like this: -Identity service:Registrar:atl-cs-001.litwareinc.com. Note that Registrar settings can only be applied to the Registrar service. An error message will occur if you try to apply these settings to any other service.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>RegistrarSettings object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="even">
<td><p><em>MaxEndpointExpiration</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>When endpoints log on they have the option of requesting an expiration timeout; this specifies the time interval that an endpoint can remain logged onto the system before it must contact the server and request an extension. The MaxEndpointExpiration property represents the maximum amount of time that clients can be granted. For example, if the maximum time is set to 600 seconds and a client requests a timeout interval of 800 seconds, the client will be given the maximum allowed expiration period: 600 seconds.</p>
<p>The MaxEndpointExpiration must be between 300 (5 minutes) and 900 (15 minutes). The default value is 900.</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxEndpointsPerUser</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>Indicates the maximum number of endpoints a user can simultaneously have connected to the system. For example, a user who is logged on to Lync Server with both a computer and a mobile phone would be using two endpoints. MaxEndPointsPerUser must be set to a value between 1 and 64, inclusive. The default value is 8.</p>
<p>Although it is possible to allow a user as many as 64 endpoints, it is recommended that the maximum number of endpoints not exceed 8. Values of 9 or more are used for backwards compatibility and, in rare cases, when suggested by Microsoft support personnel. For new deployments, the maximum number of endpoints should be no more than 8.</p>
<p>Note, too, that the maximum number of endpoints is intended to give individual users multiple points of presence. As such, this setting is designed for individual users and not for groups of users (such as an entire department.)</p></td>
</tr>
<tr class="even">
<td><p><em>MaxUserCount</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt64</p></td>
<td><p>Indicates the maximum number of users that can simultaneously be logged on to a Registrar. MaxUserCount can be set to any integer value between 2000 and 100000, inclusive. The default value is 12000.</p></td>
</tr>
<tr class="odd">
<td><p><em>MinEndpointExpiration</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>When endpoints log on they have the option of requesting an expiration timeout; this specifies the time interval that an endpoint can remain logged onto the system before it must contact the server and request an extension. The MinEndpointExpiration property represents the minimum amount of time that clients can be granted. For example, if the minimum time is set to 600 seconds and a client requests a timeout interval of 200 seconds, the client will be given the minimum allowed expiration period: 600 seconds.</p>
<p>The MinEndpointExpiration must be between 300 (5 minutes) and 900 (15 minutes). The default value is 300.</p></td>
</tr>
<tr class="even">
<td><p><em>PoolState</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.Registrar.PoolState</p></td>
<td><p>Current state for the Registrar pool. Allowed values are:</p>
<p>* Active</p>
<p>* FailedOver</p>
<p>* FailingOver</p>
<p>* FailedBack</p>
<p>The default value is Active.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.Registrar.RegistrarSettings object. The **Set-CsRegistrarConfiguration** cmdlet accepts pipelined instances of the Registrar settings object.

## Return Types

The **Set-CsRegistrarConfiguration** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Registrar.RegistrarSettings object.

## 另请参阅

#### 其他资源

[Get-CsRegistrarConfiguration](get-csregistrarconfiguration.md)  
[New-CsRegistrarConfiguration](new-csregistrarconfiguration.md)  
[Remove-CsRegistrarConfiguration](remove-csregistrarconfiguration.md)

