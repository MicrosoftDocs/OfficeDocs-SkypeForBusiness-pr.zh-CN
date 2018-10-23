---
title: Remove-CsRegistrarConfiguration
TOCTitle: Remove-CsRegistrarConfiguration
ms:assetid: 67ee01a1-fdfe-4994-b03a-57a332aa45be
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398482(v=OCS.15)
ms:contentKeyID: 49313105
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsRegistrarConfiguration

 

_**上一次修改主题：** 2015-03-09_

Removes an existing collection of Registrar configuration settings. Registrars are used to authenticate logon requests and to maintain information about user status and availability. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsRegistrarConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 deletes the Registrar configuration settings assigned to the Redmond site. When these settings are deleted, Registrars in the Redmond site will automatically use the global Registrar settings.

    Remove-CsRegistrarConfiguration -Identity site:Redmond

## EXAMPLE 2

Example 2 deletes all the Registrar configuration settings that have been assigned to the service scope. To do this, the command first calls the **Get-CsRegistrarConfiguration** cmdlet along with the Filter parameter; the filter value "service:\*" limits the returned data to settings where the Identity begins with the characters "service:". The filtered collection is then piped to the **Remove-CsRegistrarConfiguration** cmdlet, which deletes each item in that collection.

    Get-CsRegistrarConfiguration -Filter "service:*" | Remove-CsRegistrarConfiguration

## EXAMPLE 3

In Example 3, all the Registrar configuration settings where the EnableDHCPServer property is True are deleted. To carry out this task, the command first calls the **Get-CsRegistrarConfiguration** cmdlet without any parameters; this returns a collection of all the Registrar configuration settings currently in use. That collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableDHCPServer property is equal to True. In turn, the filtered collection is piped to the **Remove-CsRegistrarConfiguration** cmdlet, which deletes each item in the collection.

    Get-CsRegistrarConfiguration | Where-Object {$_.EnableDHCPServer -eq $True} | Remove-CsRegistrarConfiguration

## Detailed Description

The Registrar is perhaps the most important component in Lync Server; after all, without a Registrar, users would not be able to log on to the system, and Lync Server would not be able to keep track of users and their current status. When a user logs on to Lync Server, the endpoint the user is logging on from sends a REGISTER request to the Registrar; in turn, the server responds by challenging the client device for authentication credentials. If the client passes the challenge (that is, if the client presents a valid set of credentials), then the user is authenticated and endpoint information such as IP address, port, and user name is logged in the registration database. When a user logs off, this information is then removed from the database. In between log on and log off, the Registrar keeps status information up-to-date and helps to route messages to and from the user.

Registrar configuration settings are used to help manage endpoints and endpoint subscriptions; these settings can be applied at the global, site, or service scope. (Service scoped-settings can only be used with the Registrar service.)

The **Remove-CsRegistrarConfiguration** cmdlet enables you to remove Registrar configuration settings that have been applied at the site or service scope. Note that this does not delete or uninstall any Registrars; it simply removes the configuration settings that govern those Registrars. If these settings do not exist at either the site or the service scope, then a Registrar will be managed using the global settings.

The **Remove-CsRegistrarConfiguration** cmdlet can also be run against the global Registrar configuration settings. In that case, however, the settings will not be removed; that’s because the global settings cannot be deleted. Instead, all the properties in that global collection will be reset to their default values. For example, if you have changed the value of the MinEndpointExpiration property to 500 that value will be reset back to 300.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsRegistrarConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsRegistrarConfiguration e"}

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
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the Registrar configuration settings to be removed. To remove settings configured at the site scope, use syntax similar to this: -Identity site:Redmond. To remove settings at the service level, use syntax like this: -Identity service:Registar:atl-cs-001.litwareinc.com.</p>
<p>Note that the <strong>Remove-CsRegistrarConfiguration</strong> cmdlet can also be run against the global settings (-Identity global). In that case, however, the global settings will not be removed. Instead, all the properties in the global collection will be reset to their default values.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

Microsoft.Rtc.Management.WritableConfig.Settings.Registrar.RegistrarSettings object. The **Remove-CsRegistrarConfiguration** cmdlet accepts pipelined instances of the Registrar settings object.

## Return Types

None. Instead, the **Remove-CsRegistrarConfiguration** cmdlet deletes existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Registrar.RegistrarSettings object.

## 另请参阅

#### 其他资源

[Get-CsRegistrarConfiguration](get-csregistrarconfiguration.md)  
[New-CsRegistrarConfiguration](new-csregistrarconfiguration.md)  
[Set-CsRegistrarConfiguration](set-csregistrarconfiguration.md)

