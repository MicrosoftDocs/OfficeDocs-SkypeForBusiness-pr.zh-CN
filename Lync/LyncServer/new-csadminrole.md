---
title: New-CsAdminRole
TOCTitle: New-CsAdminRole
ms:assetid: 1e46c02e-0937-4e3b-b02e-e7507189f6aa
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398271(v=OCS.15)
ms:contentKeyID: 49312197
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsAdminRole

 

_**上一次修改主题：** 2015-03-09_

Creates a new role-based access control (RBAC) role. RBAC roles are used to define the management tasks that users are allowed to carry out, and to determine the scope in which users will be allowed to perform these tasks. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsAdminRole -Identity <String> -Template <String> [-Cmdlets <PSListModifier>] [-ConfigScopes <PSListModifier>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-ScriptModules <PSListModifier>] [-UserScopes <PSListModifier>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command in Example 1 duplicates the RBAC role CsVoiceAdministrator. Because no additional parameters are used, the new role -- RedmondVoiceAdministrators -- will be an exact duplicate of CsVoiceAdministrator, which includes both the UserScopes and ConfigScopes properties being set to "global".

    New-CsAdminRole -Identity "RedmondVoiceAdministrator" -Template "CsVoiceAdministrator"

## EXAMPLE 2

Example 2 creates a new RBAC role (RedmondVoiceAdministrator) and then configures the role to allow a single user scope: the Redmond OU. To do this, the UserScopes parameter is included along with the following parameter value: "OU:ou=Redmond,dc=litwareinc,dc=com". This parameter value replaces the current value of the UserScopes property with one item: the OU with the distinguished name (DN) "ou=Redmond,dc=litwareinc,dc=com".

    New-CsAdminRole -Identity "RedmondVoiceAdministrator" -Template "CsVoiceAdministrator" -UserScopes "OU:ou=Redmond,dc=litwareinc,dc=com"

## EXAMPLE 3

The command shown in Example 3 is a variation of the command shown in Example 2; the only difference is that, in this example, two OUs are added to the UserScopes property. This is done by assigning a comma-separated list to the Replace method: the two items in the list represent the identifiers for the two OUs (Redmond and Portland) to be assigned to the new RBAC role.

    New-CsAdminRole -Identity "RedmondVoiceAdministrator" -Template "CsVoiceAdministrator" -UserScopes "OU:ou=Redmond,dc=litwareinc,dc=com","OU:ou=Portland,dc=litwareinc,dc=com"

## EXAMPLE 4

In Example 4, the site with the SiteId Redmond is assigned to the ConfigScopes property for a new RBAC role. Note that the syntax for the ConfigScopes property requires the use of the "site:" prefix followed by the value of the SiteId property for the site being added.

    New-CsAdminRole -Identity "RedmondVoiceAdministrator" -Template "CsVoiceAdministrator" -ConfigScopes "site:Redmond"

## Detailed Description

Role-based access control (RBAC) enables administrators to delegate control of specific management tasks in Lync Server. For example, instead of granting your organization’s help desk full administrator privileges you can give these employees very specific rights: the right to manage only user accounts; the right to manage only Enterprise Voice components; the right to manage only archiving and 存档服务器. In addition, these rights can be limited in scope: someone can be given the right to manage Enterprise Voice, but only in the Redmond site; someone else can be given the right to manage users, but only if those user accounts are in the Finance organizational unit (OU).

The Lync Server implementation of RBAC is based on two key elements: Active Directory security groups and Windows PowerShell cmdlets. When you install Lync Server, a number of universal security groups, such as CsAdministrator, CsArchivingAdministrator, and CsHelpDesk are created for you. These universal security groups have a one-to-one correspondence with RBAC roles; that means that any user who is in the CsArchivingAdministrator security group has all of the rights granted to the CsArchivingAdministrator RBAC role. In turn, the rights granted to an RBAC role are based on the cmdlets assigned to that role (cmdlets can be assigned to multiple RBAC roles). For example, suppose a role has been assigned the following cmdlets:

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

The preceding list represents the only cmdlets that a user assigned a hypothetical RBAC role is allowed to run during a remote Windows PowerShell 命令行接口 session. If the user tries to run the **Disable-CsUser** cmdlet that command will fail because users assigned the hypothetical role do not have the right to run the **Disable-CsUser** cmdlet. This applies to the Lync Server 控制面板 as well. For example, an Archiving administrator cannot disable a user by using the Lync Server 控制面板; that’s because the Lync Server 控制面板 abides by RBAC roles. Any time you run a command in Lync Server 控制面板 you are actually calling a Windows PowerShell cmdlet. If you are not allowed to run the **Disable-CsUser** cmdlet, it won’t matter whether you directly run that cmdlet from Windows PowerShell or if you indirectly run the cmdlet from within the Lync Server 控制面板: the command will fail.)

Note that RBAC applies only to remote management. If you are logged on to a computer running Lync Server and you open Lync Server 命令行管理程序, RBAC roles will not be enforced. Instead, security is enforced primarily through the security groups RTCUniversalServerAdmins; RTCUniversalUserAdmins; and RTCUniversalReadOnlyAdmins.

When you install Lync Server, Setup creates several built-in RBAC roles. These roles cover common administrative areas such as voice administration, user management, and Response Group administration. The built-in roles cannot be modified in any way: you cannot add or remove cmdlets to the roles and you cannot delete these roles. (Any attempt to delete a built-in role will result in an error.) However, you can use the built-in roles to create custom RBAC roles. These custom roles can then be modified by changing the administrative scopes; for example, you could limit the role to managing user accounts in a particular Active Directory OU.

To create a new role, you must first create a universal security group in Active Directory 域服务 that shares a name with the role; for example to create a new role named DialInConferencingAdministrator, you must create a security group with the SamAccountName DialInConferencingAdministrator. Note that the **New-CsAdminRole** cmdlet will not create this group for you. If the DialInConferencingAdministrator group does not exist when you call the **New-CsAdminRole** cmdlet then your command will fail. The Identity you assign to your new role must be the SamAccountName of the corresponding Active Directory group.

After creating the Active Directory security group, you must then select a built-in RBAC role to serve as the template for your new custom role. You cannot create a blank RBAC role by using the **New-CsAdminRole** cmdlet. Instead, all custom roles must be based on one of the built-in RBAC roles. This means that a custom role must have the same assigned cmdlets as one of the built-in roles. However, you can use the **Set-CsAdminRole** cmdlet to change the administrative scope of this custom role.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsAdminRole** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsAdminRole"}

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
<td><p>Unique identifier for the RBAC role to be created. The Identity for an RBAC role must be the same as the SamAccountName for the Active Directory universal security group associated with that role. For example, the help desk role has an Identity equal to CsHelpDesk; CsHelpDesk is also the SamAccountName of the Active Directory security group associated with that role.</p></td>
</tr>
<tr class="even">
<td><p><em>Template</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Name of the built-in RBAC role that will serve as a template for the custom RBAC role being created. All new RBAC roles must be based on an existing role; it is not possible to create a blank RBAC role (that is, a role with no cmdlets assigned to it or without values assigned to either the ConfigScopes or UserScopes properties). However, after the custom role has been created, you can then use the <strong>Set-CsAdminRole</strong> cmdlet to modify the properties of the new role.</p></td>
</tr>
<tr class="odd">
<td><p><em>Cmdlets</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Enables you to specify the cmdlets that will be available to users who hold the new RBAC role. For example, to create a new role that provides access only to one cmdlet (the <strong>Export-CsArchivingData</strong> cmdlet) use syntax like this:</p>
<p>-Cmdlets &quot;Export-CsArchivingData&quot;</p>
<p>To allow access to multiple cmdlets, separate the cmdlet names using commas:</p>
<p>-Cmdlets &quot;Export-CsArchivingData&quot;,&quot;Invoke-CsArchivingDatabasePurge&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>ConfigScopes</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Used to limit the scope of the cmdlet to configuration settings within the specified site. To limit the cmdlet scope to a single site, use syntax similar to this: -ConfigScopes site:Redmond. Multiple sites can be specified by using a comma-separated list: -ConfigScopes &quot;site:Redmond, &quot;site:Dublin&quot;. You can also set the ConfigScopes property to &quot;global&quot;.</p>
<p>When assigning a value to the ConfigScopes parameter you must use the &quot;site:&quot; prefix followed by the value of the site’s SiteId property; note that the SiteID is not necessarily the same value as the site’s Identity or the site’s DisplayName. To determine the SiteId for a given site you can use a command similar to this:</p>
<p>Get-CsSite &quot;Redmond&quot; | Select-Object SiteId</p>
<p>You must specify a value for either (or both) the ConfigScopes and UserScopes properties.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="even">
<td><p><em>ScriptModules</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Enables you to specify a function within a Windows PowerShell script that will then be available to users who hold the new RBAC role. For example, this syntax provides access to a function named Reset in a script named UpdateDatabase.ps1 :</p>
<p>-ScriptModules &quot;UpdateDatabase.ps1:Reset&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>UserScopes</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Used to limit the scope of the cmdlet to user management activities within the specified organizational unit. To limit the cmdlet scope to a single organizational unit, use syntax similar to this: -UserScopes &quot;OU:ou=Redmond,dc=litwareinc,dc=com&quot;. Multiple OUs can be specified by using a comma-separated list: -UserScopes &quot;OU:ou=Redmond,dc=litwareinc,dc=com&quot;, &quot;OU:ou=Dublin,dc=litwareinc,dc=com&quot;. To add new scopes (or remove existing scopes) from a role, use the Windows PowerShell list modifiers syntax. For details, see the Examples section of this Help topic.</p>
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

The **New-CsAdminRole** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Roles.Role object.

