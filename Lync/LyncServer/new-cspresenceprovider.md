---
title: New-CsPresenceProvider
TOCTitle: New-CsPresenceProvider
ms:assetid: 55110f49-f8d5-4287-89d3-ae069d8090d3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204895(v=OCS.15)
ms:contentKeyID: 49312880
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsPresenceProvider

 

_**上一次修改主题：** 2015-03-09_

Authorizes a new presence provider for use in the organization. Presence providers represent the PresenceProviders property of a collection of user services configuration settings. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    New-CsPresenceProvider -Fqdn <String> -Parent <String> <COMMON PARAMETERS>

    New-CsPresenceProvider -Identity <XdsIdentity> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 creates a new presence provider (with the fully qualified domain name "fabrikam.com") that will be added to the global collection of user services configuration settings.

    New-CsPresenceProvider -Parent "global" -Fqdn "fabrikam.com"

## Example 2

Example 2 adds a presence provider with the Fqdn "fabrikam.com" to all the user services configuration collections in the organization. To do this, the command first uses the **Get-CsUserServicesConfiguration** cmdlet to return a collection of all the user services settings. Those settings are then piped to the ForEach-Object, which takes each item in the collection and a creates a new presence provider for that collection, using "fabrikam.com" as the presence provider Fqdn and the Identity of the user services collection as the presence provider Parent.

    Get-CsUserServicesConfiguration | ForEach-Object {New-CsPresenceProvider -Parent $_.Identity -Fqdn "fabrikam.com"}

## Detailed Description

The **CsPresenceProvider** cmdlets are used to manage the PresenceProviders property found in the User Services configuration settings. Among other things, these settings are used to maintain presence information, including a collection of authorized presence providers. That collection is stored in the PresenceProviders property. You can use the **New-CsPresenceProvider** cmdlet to add an authorized presence provider to a collection of User Services configuration settings.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsPresenceProvider"}

**Lync Server 控制面板:** The functions carried out by the **New-CsPresenceProvider** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>Fqdn</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name for the presence provider. For example:</p>
<p>-Fqdn &quot;fabrikam.com&quot;</p>
<p>If you use the Fqdn parameter you must also use the Parent parameter. However, the Fqdn parameter cannot be used in the same command as the Identity parameter.</p>
<p>Note that FQDNs must be unique at a given scope.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the new presence provider. The Identity of a presence provider is composed of two parts: the scope (Parent) where the rule has been applied (for example, service:UserServer:atl-cs-001.litwareinc.com) and the provider's fully qualified domain name. To create a new provider at the global scope use syntax similar to this:</p>
<p>-Identity &quot;global/fabrikam.com&quot;</p>
<p>To create a provider at the site scope, use syntax like this:</p>
<p>-Identity &quot;site:Redmond/fabrikam.com&quot;</p>
<p>To create a provider at the service scope (for the UserServer service only), use syntax similar to this:</p>
<p>-Parent &quot;UserServer:atl-cs-001.litwareinc.com&quot;</p>
<p>You cannot use the Identity parameter in the same command as the Fqdn or the Parent parameter.</p></td>
</tr>
<tr class="odd">
<td><p><em>Parent</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Scope where the new presence provider will be created. To create a new presence provider at the global scope, use syntax similar to this:</p>
<p>-Parent &quot;global&quot;</p>
<p>To create a new provider at the site scope use syntax like this:</p>
<p>-Parent &quot;site:Redmond&quot;</p>
<p>To create a provider at the service scope (for the UserServer service only), use syntax similar to this:</p>
<p>-Parent &quot;UserServer:atl-cs-001.litwareinc.com&quot;</p>
<p>If you use the Parent parameter you must also include the Fqdn parameter. However, the Parent parameter cannot be used in conjunction with the Identity parameter.</p></td>
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
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Creates an object reference without actually committing the object as a permanent change. If you assign the output of this cmdlet called with this parameter to a variable, you can make changes to the properties of the object reference and then commit those changes by calling this cmdlet’s matching Set- cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsPresenceProvider** cmdlet does not accept pipelined input.

## Return Types

The **New-CsPresenceProvider** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.UserServices.PresenceProvider\#Decorated object.

## 另请参阅

#### 其他资源

[Get-CsPresenceProvider](get-cspresenceprovider.md)  
[Get-CsUserServicesConfiguration](get-csuserservicesconfiguration.md)  
[Remove-CsPresenceProvider](remove-cspresenceprovider.md)  
[Set-CsPresenceProvider](set-cspresenceprovider.md)

