---
title: Remove-CsAdminRole
TOCTitle: Remove-CsAdminRole
ms:assetid: f676d3d5-2d4c-4095-a174-9278bc0852df
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413036(v=OCS.15)
ms:contentKeyID: 49314766
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsAdminRole

 

_**上一次修改主题：** 2015-03-09_

Removes an existing role-based access control (RBAC) role. RBAC roles are used to specify the management tasks that users are allowed to carry out, and to determine the scope in which users will be allowed to perform these tasks. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsAdminRole -Identity <String> <COMMON PARAMETERS>

    Remove-CsAdminRole -Sid <String> <COMMON PARAMETERS>

    Remove-CsAdminRole [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 deletes the RBAC role with the Identity RedmondHelpDesk.

    Remove-CsAdminRole -Identity "RedmondHelpDesk"

## EXAMPLE 2

Example 2 deletes all of the RBAC roles that have the string value "Redmond" somewhere in their Identity.

    Remove-CsAdminRole -Filter "*Redmond*"

## EXAMPLE 3

In Example 3, the command deletes all of the custom RBAC roles that have been created for use in your organization. To do this, the command first calls the **Get-CsAdminRole** cmdlet without any parameters; that returns a collection of the RBAC roles. This collection is then piped to the **Where-Object** cmdlet, which selects only those roles where the IsStandardRole property is equal to False. By definition, any role meeting that criterion is a custom role. In turn, those custom roles are piped to, and deleted by, the **Remove-CsAdminRole** cmdlet.

    Get-CsAdminRole | Where-Object {$_.IsStandardRole -eq $False} | Remove-CsAdminRole

## Detailed Description

RBAC enables administrators to delegate control of specific management tasks in Lync Server. For example, instead of granting your organization’s help desk full administrator privileges you can give these employees very specific rights: the right to manage only user accounts; the right to manage only Enterprise Voice components; and the right to manage only archiving and 存档服务器. In addition, these rights can be limited in scope: someone can be given the right to manage Enterprise Voice, but only in the Redmond site; someone else can be given the right to manage users, but only if those user accounts are in the Finance organizational unit (OU).

The Lync Server implementation of RBAC is based on two key elements: Active Directory security groups and Windows PowerShell cmdlets. When you install Lync Server, a number of universal security groups, such as CsAdministrator, CsArchivingAdministrator, and CsViewOnlyAdministrator, are created for you. These universal security groups have a one-to-one correspondence with RBAC roles, which means that any user who is in the CsArchivingAdministrator security group has all of the rights granted to the CsArchivingAdministrator RBAC role. In turn, the rights granted to an RBAC role are based on the cmdlets assigned to that role (cmdlets can be assigned to multiple RBAC roles). For example, suppose a role has been assigned the following cmdlets:

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

The preceding list represents the only cmdlets that a user assigned a hypothetical RBAC role is allowed to run in a remote session of the Windows PowerShell 命令行接口. If the user tries to run the **Disable-CsUser** cmdlet that command will fail because users assigned the hypothetical role do not have the right to run the **Disable-CsUser** cmdlet. This applies to the Lync Server 控制面板 as well. For example, an Archiving Administrator cannot disable a user by using the Lync Server 控制面板 because the Lync Server 控制面板 abides by RBAC roles. (Any time you run a command in Lync Server 控制面板 you are actually calling a Windows PowerShell cmdlet.) If you are not allowed to run the **Disable-CsUser** cmdlet, it won’t matter whether you directly run that cmdlet from Windows PowerShell or if you indirectly run the cmdlet from within the Lync Server 控制面板: the command will fail.)

Note that RBAC applies only to remote management. If you are logged on to a computer running Lync Server and you open the Lync Server 命令行管理程序, RBAC roles will not be enforced. Instead, security is enforced primarily through the security groups RTCUniversalServerAdmins; RTCUniversalUserAdmins; and RTCUniversalReadOnlyAdmins.

When you install Lync Server, Setup creates several built-in RBAC roles that cover common administrative areas such as voice administration, user management, and Response Group administration. These built-in roles cannot be modified in any way: you cannot add or remove cmdlets to the roles and you cannot delete these roles. (Any attempt to delete a built-in role will result in an error message.) However, you can use the built-in roles to create custom RBAC roles. These custom roles can then be modified by changing the administrative scopes; for example, you can limit the role to managing user accounts with a particular Active Directory OU.

Any custom roles you create can be deleted by using the **Remove-CsAdminRole** cmdlet. Note that the **Remove-CsAdminRole** cmdlet will not delete the Active Directory security group that corresponds to the custom role, nor will it remove any of the members who have been assigned to the group. Instead, the cmdlet simply ensures that this custom role cannot be used to delegate control of Lync Server.

When you delete an RBAC role, Windows PowerShell will respond by asking if you are sure you want to delete this role; if you do not respond to this prompt (or do not respond by saying Yes) then the role will not be deleted. To avoid these confirmation prompts, use the Confirm parameter and set the parameter value to $False:

Remove-CsAdminRole RedmondAdministrators –Confirm:$False

Who can run this cmdlet: By default, members of the following groups are authorized to run the Remove-CsAdminRole cmdlet locally: RTCUniversalServerAdmins. To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself) run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsAdminRole"}

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
<td><p>Unique identifier for the RBAC role to be deleted. The Identity for an RBAC role must be the same as the SamAccountName for the Active Directory universal security group associated with that role. For example, the Help Desk role has an Identity equal to CsHelpDesk; CsHelpDesk is also the SamAccountName of the Active Directory security group associated with that role.</p></td>
</tr>
<tr class="even">
<td><p><em>Sid</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to use a Security Identifier (SID) to specify the RBAC role to be deleted. SIDs are assigned by Lync Server at the time that the RBAC role is created; and look similar to this: S-1-5-21-1573807623-1597889489-1765977225-1145. The SID for a given RBAC role can be retrieved by using the <strong>Get-CsAdminRole</strong> cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to bypass the confirmation prompt that appears when you try to delete an RBAC role. To bypass the prompt, include the Confirm parameter and set the parameter value to $False:</p>
<p>Remove-CsAdminRole RedmondAdministrators –Confirm:$False</p></td>
</tr>
<tr class="even">
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to use wildcards in order to specify the custom RBAC roles to be removed. For example, to remove all the custom roles that include the string value &quot;Redmond&quot; in their Identity, you can use this syntax: -Filter &quot;*Redmond*&quot;.</p></td>
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

Microsoft.Rtc.Management.ADConnect.Schema.ADUser object. The **Remove-CsAdminRole** cmdlet accepts pipelined input of user objects.

## Return Types

The **Remove-CsAdminRole** cmdlet deletes existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Roles.Role object.

