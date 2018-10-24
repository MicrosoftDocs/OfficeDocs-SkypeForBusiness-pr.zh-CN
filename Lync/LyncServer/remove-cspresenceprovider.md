---
title: Remove-CsPresenceProvider
TOCTitle: Remove-CsPresenceProvider
ms:assetid: 7e8b540e-484f-4003-8665-18e2b3974f33
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205036(v=OCS.15)
ms:contentKeyID: 49313378
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsPresenceProvider

 

_**上一次修改主题：** 2015-03-09_

Removes a presence provider previously configured for use in the organization. Presence providers represent the PresenceProviders property of a collection of user services configuration settings. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Remove-CsPresenceProvider -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 removes the presence provider with the Identity "global/fabrikam.com".

    Remove-CsPresenceProvider -Identity "global/fabrikam.com"

## Example 2

In Example 2, all the presence providers configured for use in the organization are removed. To do this, the command first calls the **Get-CsPresenceProvider** cmdlet without any parameters; that returns a collection of all the configured presence providers. That collection is then piped to the **Remove-CsPresenceProvider** cmdlet, which deletes each item (that is, each provider) in the collection.

    Get-CsPresenceProvider | Remove-CsPresenceProvider

## Example 3

Example 3 shows how you can delete all the presence providers that have an Fqdn that includes the string value "fabrikam.com". To carry out this task, the command first uses the **Get-CsPresenceProvider** cmdlet to return a collection of all the available presence providers. That collection is then piped to the **Where-Object** cmdlet, which picks out only those providers where the Fqdn property includes (-match) the string value "fabrikam.com". In turn, that filtered collection is then piped to the **Remove-CsPresenceProvider** cmdlet, which deletes each provider in the filtered collection.

    Get-CsPresenceProvider | Where-Object {$_.Fqdn -match "fabrikam.com"} | Remove-CsPresenceProvider

## Detailed Description

The **CsPresenceProvider** cmdlets are used to manage the PresenceProviders property found in the User Services configuration settings. Among other things, these settings are used to maintain presence information, including a collection of authorized presence providers. That collection is stored in the PresenceProviders property.

The **Remove-CsPresenceProvider** cmdlet enables you to remove a presence provider from the PresenceProviders property of one or more collections of User Services configuration settings.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsPresenceProvider"}

**Lync Server 控制面板:** The functions carried out by the **Remove-CsPresenceProvider** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Unique identifier of the presence provider to be removed. To remove a single provider, use the actual Identity of the provider, which includes both the scope and the provider Fqdn:</p>
<p>-Identity &quot;global/fabrikam.com&quot;</p>
<p>To remove all the presence providers configured at a particular scope, simply use the scope as the Identity. This syntax removes all the providers configured at the global scope:</p>
<p>-Identity &quot;global&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
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
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Remove-CsPresenceProvider** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.UserServices.PresenceProvider\#Decorated object.

## Return Types

None. Instead, the **Remove-CsPresenceProvider** cmdlet deletes instances of the Microsoft.Rtc.Management.WritableConfig.Settings.UserServices.PresenceProvider\#Decorated object.

## 另请参阅

#### 其他资源

[Get-CsPresenceProvider](get-cspresenceprovider.md)  
[Get-CsUserServicesConfiguration](get-csuserservicesconfiguration.md)  
[New-CsPresenceProvider](new-cspresenceprovider.md)  
[Set-CsPresenceProvider](set-cspresenceprovider.md)

