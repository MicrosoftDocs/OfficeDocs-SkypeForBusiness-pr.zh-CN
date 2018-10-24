---
title: Set-CsUserReplicatorConfiguration
TOCTitle: Set-CsUserReplicatorConfiguration
ms:assetid: 7164960f-8e88-4c8d-9a12-1814aa2b9047
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398540(v=OCS.15)
ms:contentKeyID: 49313214
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsUserReplicatorConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing collection of User Replicator configuration settings. The User Replicator periodically retrieves up-to-date user account information from Active Directory 域服务 and then synchronizes the new information with the current user data stored by Lync Server. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsUserReplicatorConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsUserReplicatorConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-ADDomainNamingContextList <PSListModifier>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-ReplicationCycleInterval <TimeSpan>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 sets the value of the ReplicationCycleInterval of the global User Replicator settings to five minutes (00 hours: 05 minutes: 00 seconds).

    Set-CsUserReplicatorConfiguration -Identity global -ReplicationCycleInterval "00:05:00"

## EXAMPLE 2

The command shown in Example 2 clears the value of the ADDomainNamingContextList property. This task is carried out by including the ADDomainNamingContextList parameter and setting the parameter value to null. By setting this value to null the User Replicator will automatically discover and synchronize with all the available domains.

    Set-CsUserReplicatorConfiguration -Identity global -ADDomainNamingContextList $Null

## EXAMPLE 3

In Example 3 an additional name is added to the ADDomainNamingContextList property of the global User Replicator settings. To do this, the syntax @{Add=} is used, along with the distinguished name of the domain being added. When this command is run, fabrikam.com will be added to the list of domain names. To configure the global settings so that only fabrikam.com is on the list use this syntax:

\-ADDomainNamingContextList @{Replace="dc=fabrikam,dc=com"}

When the AdDomainNamingContextList property is set to anything but a null value, the User Replicator will only synchronize with the domains listed in the property value. This will be the case even if there are other domains in the deployment.

    Set-CsUserReplicatorConfiguration -Identity global -ADDomainNamingContextList @{Add="dc=fabrikam,dc=com"}

## EXAMPLE 4

Example 4 removes the domain fabrikam.com from the ADDomainNamingContextList property of the global User Replicator configuration settings. To do this the syntax @{Remove=} is used, along with the distinguished name (DN) of the domain (dc=fabrikam,dc=com).

    Set-CsUserReplicatorConfiguration -Identity global -ADDomainNamingContextList @{Remove="dc=fabrikam,dc=com"}

## Detailed Description

Although Lync Server maintains its own database of user accounts and user account data, Lync Server still relies on AD DS as the ultimate source for user information. For example, when a new Active Directory user account is created, you must supply basic information about the user account (such the Active Directory display name). When a user is enabled for Lync Server, however, you do not need to specify a new display name. That’s because Lync Server uses the display name already stored in AD DS.

User account information, including the Active Directory display name, is subject to change over time. For example, a user who gets married might change her last name and, in turn, need to change her display name as well. In order to ensure that the Lync Server database and AD DS remain in synch, Lync Server must periodically check in with AD DS, retrieve the latest user account updates, and then modify the Lync Server user database accordingly. This synchronization between AD DS and Lync Server is carried out by the User Replicator.

When you install Lync Server, a global set of User Replicator configuration settings is created for you. By default, these settings are used to manage the User Replicator on an organization-wide basis. Management of the User Replicator consists of identifying the domains that Lync Server needs to synch with in addition to indicating how often the User Replicator checks AD DS for user account updates. By default, the User Replicator discovers and synchs with all available domains. However, by using the AdDomainNamingContextList property you can restrict synchronization to a specific set of domains: the domains that appear in the AdDomainNamingContextList property.

You can also create additional collections at the service scope, but only if you are working with Lync Online.

The **Set-CsUserReplicatorConfiguration** cmdlet enables you to modify any of the User Replicator settings currently in use in your organization. You can use this cmdlet to add or remove domains from the list of domains the User Replicator must synchronize with, and to modify the time interval between replication cycles.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsUserReplicatorConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom role-based access control (RBAC) roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsUserReplicatorConfiguration"}

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
<td><p><em>ADDomainNamingContextList</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Distinguished names of the Active Directory domains that the User Replicator must synchronize with. For example, to add a domain to the list use syntax similar to this:</p>
<p>-ADDomainNamingContextList @{Add=&quot;dc=fabrikam,dc=com&quot;}</p>
<p>If you set this property to a null value the User Replicator will discover and synchronize with all available domains. If this property is not null then the User Replicator will only synchronize with the domains specified in the ADDomainNamingContextList.</p></td>
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
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier of the User Replicator configuration settings to be modified. To modify the global settings, use this syntax: -Identity global.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>UserReplicatorConfiguration object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="even">
<td><p><em>ReplicationCycleInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>Represents the amount of time that the User Replicator waits before checking for user account updates in AD DS. The replication cycle interval can be any time value between 1 second and 23 hours, 59 minutes, and 59 seconds; the default value is 1 minute. The interval must be expressed using the format hours:minutes:seconds. For example, this syntax sets to time interval to one hour and 15 minutes:</p>
<p>-ReplicationCycleInterval 01:15:00</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.UserReplicator.UserReplicatorConfiguration object. The **Set-CsUserReplicatorConfiguration** cmdlet accepts pipelined input of the User Replicator configuration object.

## Return Types

The **Set-CsUserReplicatorConfiguration** cmdlet does not return any objects or values. Instead, the cmdlet modifies the global instance (the only such instance) of the Microsoft.Rtc.Management.WritableConfig.Settings.UserReplicator.UserReplicatorConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsUserReplicatorConfiguration](get-csuserreplicatorconfiguration.md)  
[New-CsUserReplicatorConfiguration](new-csuserreplicatorconfiguration.md)  
[Remove-CsUserReplicatorConfiguration](remove-csuserreplicatorconfiguration.md)

