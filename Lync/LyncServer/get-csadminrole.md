---
title: Get-CsAdminRole
TOCTitle: Get-CsAdminRole
ms:assetid: ea15ee37-f7a1-4e67-afe8-08e63e8ca765
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399050(v=OCS.15)
ms:contentKeyID: 49314619
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsAdminRole

 

_**上一次修改主题：** 2015-03-09_

Returns information about the role-based access control (RBAC) roles used in your organization. RBAC roles are used to specify the management tasks that users are allowed to carry out, and to determine the scope in which users will be allowed to perform these tasks. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsAdminRole [-Identity <String>] <COMMON PARAMETERS>

    Get-CsAdminRole [-Sid <String>] <COMMON PARAMETERS>

    Get-CsAdminRole [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

The command shown in Example 1 returns information about all the RBAC roles configured for use in your organization. This is done by calling the **Get-CsAdminRole** cmdlet without any parameters.

    Get-CsAdminRole

## EXAMPLE 2

In Example 2, a single RBAC role is returned: the role that has the Identity CsHelpDesk.

    Get-CsAdminRole -Identity "CsHelpDesk"

## EXAMPLE 3

Example 3 returns all the RBAC roles that have the string value "Voice" somewhere in their Identity (for example, CsVoiceAdministrator; RedmondVoiceAdministrators). To do this, **Get-CsAdminRole** is called along with the Filter parameter; the filter value "\*Voice\*" limits the returned data to RBAC roles that have the string value "Voice" somewhere in their Identity.

    Get-CsAdminRole -Filter "*Voice*"

## EXAMPLE 4

Example 4 returns all the custom RBAC roles that have been created for use in your organization. To carry out this task, the command first uses the **Get-CsAdminRole** cmdlet to return a collection of all the RBAC roles currently in use. This collection is then piped to the **Where-Object** cmdlet, which selects only those roles where the IsStandardRole property is equal to False. By definition, any role that meets that criterion is a custom RBAC role.

    Get-CsAdminRole | Where-Object {$_.IsStandardRole -eq $False}

## EXAMPLE 5

The command shown in Example 5 returns all the RBAC roles that include the **Set-CsUser** cmdlet. To do this, the command first calls the **Get-CsAdminRole** cmdlet without any parameters in order to return a collection of all the RBAC roles in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out any role where the Cmdlets property includes the string value "Set-CsUser\\b". (The \\b is a word boundary marker that indicates that "Set-CsUser" represents the entire string value.)

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsUser\b"}

## EXAMPLE 6

Example 6 returns information about all the RBAC roles that include the specified OU (ou=Redmond, dc=litwareinc, dc=com) in the UserScopes property. To perform this task, the command first calls the **Get-CsAdminRole** cmdlet in order to return a collection of all the RBAC roles currently configured for use. This collection is then piped to the **Where-Object** cmdlet, which selects all of the roles that include the string value "OU:ou=Redmond,dc=litwareinc,dc=com" in the UserScopes property.

    Get-CsAdminRole | Where-Object {$_.UserScopes -match "OU: ou=Redmond,dc=litwareinc,dc=com"}

## EXAMPLE 7

The command shown in Example 7 returns a list of all the cmdlets included in the CsVoiceAdministrator role. To do this, the command first uses the **Get-CsAdminRole** cmdlet to return all the properties and property values for CsVoiceAdministrator. This information is then piped to the **Select-Object** cmdlet, which uses the ExpandProperty parameter to display all of the items contained in the Cmdlets property.

    Get-CsAdminRole -Identity "CsVoiceAdministrator" | Select-Object -ExpandProperty Cmdlets

## Detailed Description

Role-based access control (RBAC) enables administrators to delegate control of specific management tasks in Lync Server. For example, instead of granting your organization’s help desk full administrator privileges, you can give these employees very specific rights, such as the right to manage only user accounts; the right to manage only Enterprise Voice components; and the right to manage only archiving and 存档服务器. In addition, these rights can be limited in scope: someone can be given the right to manage Enterprise Voice, but only in the Redmond site; someone else can be given the right to manage users, but only if those user accounts are in the Finance organizational unit (OU).

The Lync Server implementation of RBAC is based on two key elements: Active Directory security groups and Windows PowerShell cmdlets. When you install Lync Server, a number of universal security groups such as CsAdministrator, CsArchivingAdministrator, and CsViewOnlyAdministrator are created for you. These universal security groups have a one-to-one correspondence with RBAC roles, which means that any user who is in the CsArchivingAdministrator security group has all of the rights granted to the CsArchivingAdministrator RBAC role. In turn, the rights granted to an RBAC role are based on the cmdlets assigned to that role (cmdlets can be assigned to multiple RBAC roles). For example, suppose a role has been assigned the following cmdlets:

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

The preceding list represents the only cmdlets that a user assigned a hypothetical RBAC role is allowed to run in a remote Windows PowerShell 命令行接口 session. If the user tries to run the **Disable-CsUser** cmdlet that command will fail because users assigned the hypothetical role do not have the right to run the **Disable-CsUser** cmdlet. This applies to the Lync Server 控制面板 as well. For example, an Archiving Administrator cannot disable a user by using Lync Server 控制面板 because the Lync Server 控制面板 abides by RBAC roles. (Any time you run a command in Lync Server 控制面板 you are actually calling a Windows PowerShell cmdlet.) If you are not allowed to run the **Disable-CsUser** cmdlet, it won’t matter whether you directly run that cmdlet from a remote session of Windows PowerShell or if you indirectly run the cmdlet from within Lync Server 控制面板; the command will fail.

Note that RBAC applies only to remote management. If you are logged on to a computer running Lync Server and you open Lync Server 命令行管理程序, RBAC roles will not be enforced. Instead, security is enforced primarily through the security groups RTCUniversalServerAdmins; RTCUniversalUserAdmins; and RTCUniversalReadOnlyAdmins.

When you install Lync Server, Setup creates several built-in RBAC roles. These roles cover common administrative areas such as voice administration, user management, and Response Group administration. These built-in roles cannot be modified in any way: you cannot add to or remove cmdlets from the roles, and you cannot delete these roles. (Any attempt to delete a built-in role will result in an error message.) However, you can use the built-in roles to create custom RBAC roles. These custom roles can then be modified by changing the administrative scopes. For example, you can limit the role to managing user accounts with a particular Active Directory OU.

The **Get-CsAdminRole** cmdlet returns information about all the RBAC roles available for use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsAdminRole** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins, RTCUniversalReadOnlyAdmins. To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself) run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsAdminRole\\b"}

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
<td><p>Enables you to use wildcards in order to specify the RBAC role (or roles) to be returned. For example, to return all the roles that include the string value &quot;Redmond&quot; in their Identity, you can use this syntax: -Filter &quot;*Redmond*&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Unique identifier for the RBAC role to be returned. The Identity for an RBAC role must be the same as the SamAccountName for the Active Directory universal security group associated with that role. For example, the help desk role has an Identity equal to CsHelpDesk; CsHelpDesk is also the SamAccountName of the Active Directory security group associated with that role.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the RBAC data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
<tr class="even">
<td><p><em>Sid</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to use a security identifier (SID) to specify the RBAC role to be retrieved. SIDs are assigned by Lync Server at the time that the RBAC role is created, and look similar to this: S-1-5-21-1573807623-1597889489-1765977225-1145.</p>
<p>This same SID can also be found on the corresponding Active Directory security group.</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

The **Get-CsAdminRole** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Roles.Role object.

