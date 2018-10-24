---
title: Get-CsRegistrarConfiguration
TOCTitle: Get-CsRegistrarConfiguration
ms:assetid: 67f2caf6-84a8-46d8-b034-7161e9841ab8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398483(v=OCS.15)
ms:contentKeyID: 49313117
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsRegistrarConfiguration

 

_**上一次修改主题：** 2015-03-09_

Returns information about the Registrar configuration settings currently in use in your organization. Registrars are used to authenticate logon requests and to maintain information about user status and availability. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsRegistrarConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsRegistrarConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

The command shown in Example 1 returns a collection of all the Registrar configuration settings currently in use in the organization.

    Get-CsRegistrarConfiguration

## EXAMPLE 2

Example 2 returns a single collection of Registrar configuration settings: the settings configured for the Redmond site (-Identity site:Redmond).

    Get-CsRegistrarConfiguration -Identity site:Redmond

## EXAMPLE 3

In Example 3, information is returned for all the Registrar configuration settings assigned at the service scope. To do this, the command uses the Filter parameter and the filter value "service:\*"; that filter value ensures that only settings that have an Identity that begins with the string value "service:" will be returned.

    Get-CsRegistrarConfiguration -Filter "service:*"

## EXAMPLE 4

Example 4 returns information about the Registrar configuration settings that enable the use of DHCP servers in order to register clients. To carry out this task, the command first calls the **Get-CsRegistrarConfiguration** cmdlet without any parameters; that returns a collection of all the Registrar configuration settings currently in use. This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableDHCPServer property is equal to True.

    Get-CsRegistrarConfiguration | Where-Object {$_.EnableDHCPServer -eq $True}

## EXAMPLE 5

In Example 5, information is returned for all the Registrar configuration settings that allow more than eight endpoints per user. To accomplish this, the command first uses the **Get-CsRegistrarConfiguration** cmdlet to return a collection of all the Registrar configuration settings used in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out those settings where the MaxEndpointsPerUser property is greater than 8.

    Get-CsRegistrarConfiguration | Where-Object {$_.MaxEndpointsPerUser -gt 8}

## Detailed Description

The Registrar is perhaps the most important component in Lync Server; after all, without a Registrar, users would not be able to log on to the system, and Lync Server would not be able to keep track of users and their current status. When a user logs on to Lync Server, the endpoint the user is logging on from sends a REGISTER request to the Registrar; in turn, the server responds by challenging the client device for authentication credentials. If the client passes the challenge (that is, if the client presents a valid set of credentials), then the user is authenticated and endpoint information such as IP address, port, and user name is logged in the registration database. When a user logs off, this information is then removed from the database. In between log on and log off, the Registrar keeps status information up-to-date and helps to route messages to and from the user.

Registrar configuration settings are used to help manage endpoints and endpoint subscriptions; these settings can be applied at the global, site, or service scope. (Service scoped-settings can only be used with the Registrar service.) The **Get-CsRegistrarConfiguration** cmdlet is used to return information about all the Registrar configurations collections currently in use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsRegistrarConfiguration** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsRegistrarConfiguration"}

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
<td><p>Enables you to use wildcards in order to return one or more collections of Registrar configuration settings. For example, to return all the settings configured at the site scope, use this syntax: -Filter &quot;site:*&quot;. To return all the settings configured at the service scope, use this syntax: -Filter &quot;service:*&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the Registrar configuration settings to be returned. To return the global settings, use this syntax: -Identity global. To return settings configured at the site scope, use syntax similar to this: -Identity site:Redmond. To return settings at the service level, use syntax like this: -Identity service:Registrar:atl-cs-001.litwareinc.com.</p>
<p>If this parameter is omitted then the <strong>Get-CsRegistrarConfiguration</strong> cmdlet returns all of the Registrar configuration settings currently in use in your organization.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the Registrar configuration settings data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsRegistrarConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsRegistrarConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Registrar.RegistrarSettings object.

## 另请参阅

#### 其他资源

[New-CsRegistrarConfiguration](new-csregistrarconfiguration.md)  
[Remove-CsRegistrarConfiguration](remove-csregistrarconfiguration.md)  
[Set-CsRegistrarConfiguration](set-csregistrarconfiguration.md)

