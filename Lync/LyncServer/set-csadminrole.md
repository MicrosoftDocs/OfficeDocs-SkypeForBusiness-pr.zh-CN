---
title: Set-CsAdminRole
TOCTitle: Set-CsAdminRole
ms:assetid: ec927ce6-a37b-4876-a6df-a347404f4e84
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399066(v=OCS.15)
ms:contentKeyID: 49314647
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsAdminRole

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing role-based access control (RBAC) role. RBAC roles are used to specify the management tasks that users are allowed to carry out, and to determine the scope in which users will be allowed to perform these tasks. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsAdminRole -Identity <String> [-Cmdlets <PSListModifier>] [-ConfigScopes <PSListModifier>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-ScriptModules <PSListModifier>] [-UserScopes <PSListModifier>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 adds a new OU (Portland) to the UserScopes property for the RBAC role RedmondVoiceAdministrators. To do this, the command includes the UserScopes parameter and the following parameter value: @{Add="OU:ou=Portland,dc=litwareinc,dc=com"}. This syntax adds the OU with the distinguished name "ou=Portland,dc=litwareinc,dc=com" to the OUs already in the UserScopes property.

    Set-CsAdminRole -Identity "RedmondVoiceAdministrators" -UserScopes @{Add="OU:ou=Portland,dc=litwareinc,dc=com"}

## EXAMPLE 2

The command shown in Example 2 removes the Portland OU from the RBAC role RedmondVoiceAdministrators. To do this, the command includes the UserScopes parameter and the following parameter value: @{Remove="OU:ou=Portland,dc=litwareinc,dc=com"}. This syntax deletes the OU with the distinguished name "ou=Portland,dc=litwareinc,dc=com" from the collection of OUs already in the UserScopes property.

    Set-CsAdminRole -Identity "RedmondVoiceAdministrators" -UserScopes @{Remove="OU:ou=Portland,dc=litwareinc,dc=com"}

## EXAMPLE 3

In Example 3, a new site (one with the SiteId Redmond) is added to the ConfigScopes property for the RBAC role RedmondVoiceAdministrators. To do this, the command includes the ConfigScopes parameter and the following parameter value: @{Add="OU:ou=Portland,dc=litwareinc,dc=com"}. This syntax adds the Redmond site to any items already in the ConfigScopes property.

    Set-CsAdminRole -Identity "RedmondVoiceAdministrators" -ConfigScopes @{Add="site:Redmond"}

## EXAMPLE 4

The command shown in Example 4 removes the Redmond site from the RBAC role RedmondVoiceAdministrators. To do this, the command includes the ConfigScopes parameter and the following parameter value: @{Remove="site:Redmond"}. This parameter deletes the Redmond site from the collection of items already in the ConfigScopes property. Note that this command will fail if the Redmond site is the only site in the ConfigScopes property. If you are removing the only site in the ConfigScopes property you should use a command similar to this, which replaces all the items in ConfigScopes with the Global property:

Set-CsAdminRole -Identity "RedmondVoiceAdministrators" -ConfigScopes @{Replace="Global"}

    Set-CsAdminRole -Identity "RedmondVoiceAdministrators" -ConfigScopes @{Remove="siteRedmond"}

## Detailed Description

RBAC enables administrators to delegate control of specific management tasks in Lync Server. For example, instead of granting your organization’s help desk full administrator privileges you can give these employees very specific rights: the right to manage only user accounts; the right to manage only Enterprise Voice components; the right to manage only archiving and 存档服务器. In addition, these rights can be limited in scope: someone can be given the right to manage Enterprise Voice, but only in the Redmond site; someone else can be given the right to manage users, but only if those user accounts are in the Finance organizational unit (OU).

The Lync Server implementation of RBAC is based on two key elements: Active Directory security groups and Windows PowerShell cmdlets. When you install Lync Server, a number of universal security groups, such as CsAdministrator, CsArchivingAdministrator, and CsViewOnlyAdministrator, are created for you. These universal security groups have a one-to-one correspondence with RBAC roles, which means that any user who is in the CsArchivingAdministrator security group has all the rights granted to the CsArchivingAdministrator RBAC role. In turn, the rights granted to an RBAC role are based on the cmdlets assigned to that role (cmdlets can be assigned to multiple RBAC roles). For example, suppose a role has been assigned the following cmdlets:

Get-ArchivingPolicy

Grant-ArchivingPolicy

New-ArchivingPolicy

Remove-ArchivingPolicy

Set-ArchivingPolicy

Get-ArchivingConfiguration

New-ArchivingConfiguration

Remove-ArchivingConfiguration

Set-ArchivingConfiguration

Get-CsUser

Export-CsArchivingData

Get-CsComputer

Get-CsPool

Get-CsService

Get-CsSite

The preceding list represents the only cmdlets that a user assigned a hypothetical RBAC role is allowed to run in a remote Windows PowerShell 命令行接口 session. If the user tries to run the **Disable-CsUser** cmdlet, that command will fail because users assigned the hypothetical role do not have the right to run the **Disable-CsUser** cmdlet. This also applies to Lync Server 控制面板. For example, an Archiving Administrator cannot disable a user by using Lync Server 控制面板 because Lync Server 控制面板 abides by RBAC roles. (Any time you run a command in Lync Server 控制面板, you are actually calling a Windows PowerShell cmdlet.) If you are not allowed to run the **Disable-CsUser** cmdlet, it won’t matter whether you directly run that cmdlet from Windows PowerShell or if you indirectly run the cmdlet from within Lync Server 控制面板: the command will fail.

Note that RBAC applies only to remote management. If you are logged on to a computer running Lync Server and you open Lync Server 命令行管理程序, RBAC roles will not be enforced. Instead, security is enforced primarily through the security groups RTCUniversalServerAdmins; RTCUniversalUserAdmins; and RTCUniversalReadOnlyAdmins.

When you install Lync Server, Setup creates several built-in RBAC roles that cover common administrative areas such as voice administration, user management, and Response Group administration. These built-in roles cannot be modified in any way: you cannot add or remove cmdlets to the roles and you cannot delete these roles. (Any attempt to delete a built-in role will result in an error message.) However, you can use the built-in roles to create custom RBAC roles. These custom roles can then be modified by changing the administrative scopes; for example, you can limit the role to managing user accounts in a particular Active Directory OU.

Any custom role you create must be based on a template: an existing RBAC role. For example, to create a Dial-In Conferencing Administrator role you must effectively clone an existing RBAC role (for example, you might base the Dial-In Conferencing Administrator role on the existing Voice Administrator role). After the custom role has been created, you can then use the **Set-CsAdminRole** cmdlet to modify the properties of that new role.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsAdminRole cmdlet** locally: RTCUniversalServerAdmins. To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself) run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsAdminRole"}

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
<td><p>System.String</p></td>
<td><p>Unique identifier for the RBAC role to be modified. The Identity for an RBAC role must be the same as the SamAccountName for the Active Directory universal security group associated with that role. For example, the help desk role has an Identity equal to CsHelpDesk; CsHelpDesk is also the SamAccountName of the Active Directory security group associated with that role.</p></td>
</tr>
<tr class="even">
<td><p><em>Cmdlets</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Enables you to specify the cmdlets that will be available to users who hold the RBAC role. For example, to provide access to just one cmdlet (the <strong>Export-CsArchivingData</strong> cmdlet) use syntax like this:</p>
<p>-Cmdlets &quot;Export-CsArchivingData&quot;</p>
<p>The preceding syntax replaces all the items currently stored in the Cmdlets property with the single item Export-CsArchivingData. If you want to add the <strong>Export-CsArchivingData</strong> cmdlet to the cmdlets already stored in that property, use this syntax instead:</p>
<p>-Cmdlets @{Add=&quot;Export-CsArchivingData&quot;}</p>
<p>Multiple cmdlets can be added by separated the cmdlet names using commas:</p>
<p>-Cmdlets @{Add=&quot;Export-CsArchivingData&quot;,&quot;Invoke-CsArchivingDatabasePurge&quot;}</p>
<p>To remove a cmdlet from a role, use this syntax:</p>
<p>-Cmdlets @{Remove=&quot;Export-CsArchivingData&quot;}</p></td>
</tr>
<tr class="odd">
<td><p><em>ConfigScopes</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Limits the scope of the cmdlet to configuration settings within the specified site. To limit the cmdlet scope to a single site, use syntax similar to this: -ConfigScopes site:Redmond. Multiple sites can be specified by using a comma-separated list: -ConfigScopes &quot;site:Redmond, &quot;site:Dublin&quot;. You can also set the ConfigScopes property to &quot;global&quot;.</p>
<p>When assigning a value to the ConfigScopes parameter you must use the &quot;site:&quot; prefix followed by the value of the site’s SiteId property; the SiteId is not necessarily the same value as the site’s Identity or the site’s DisplayName. To determine the SiteId for a given site you can use a command similar to this:</p>
<p>Get-CsSite &quot;Redmond&quot; | Select-Object SiteId</p>
<p>You must specify a value for either (or both) the ConfigScopes and UserScopes properties.</p></td>
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
<td><p><em>ScriptModules</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Enables you to specify a function within a Windows PowerShell script that will then be available to users who hold the new RBAC role. For example, this syntax provides access to a function named Reset in a script named UpdateDatabase.ps1 :</p>
<p>-ScriptCmdlets &quot;UpdateDatabase.ps1:Reset&quot;</p>
<p>The preceding command replaces any scripts currently stored in the ScriptCmdlets property with the Reset function and the UpdateDatabase.ps1 script. To add this script/function to items currently stored in the ScriptCmdlets property use this syntax:</p>
<p>-ScriptCmdlets @{Add=&quot;UpdateDatabase.ps1:Reset&quot;}</p>
<p>To remove a script/function use this syntax:</p>
<p>-ScriptCmdlets @{Add=&quot;UpdateDatabase.ps1:Reset&quot;}</p>
<p>You can delete all the ScriptCmdlets assigned to a role by using this syntax:</p>
<p>-ScriptCmdlets $Null</p></td>
</tr>
<tr class="odd">
<td><p><em>UserScopes</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Limits the scope of the cmdlet to user management activities within the specified OU. To limit the cmdlet scope to a single OU, use syntax similar to this: -UserScopes &quot;OU:ou=Redmond,dc=litwareinc,dc=com&quot;. Multiple OUs can be specified by using a comma-separated list: -UserScopes &quot;OU:ou=Redmond,dc=litwareinc,dc=com&quot;, &quot;OU:ou=Dublin,dc=litwareinc,dc=com&quot;. To add new scopes (or remove existing scopes) from a role, use the Windows PowerShell list modifiers syntax. For details, see the Examples section in this Help topic.</p>
<p>You must specify a value for either (or both) the ConfigScopes and UserScopes properties.</p></td>
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

None.

## Return Types

The **Set-CsAdminRole** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Roles.Role object.

