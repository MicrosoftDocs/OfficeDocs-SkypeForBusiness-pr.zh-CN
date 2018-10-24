---
title: New-CsUserReplicatorConfiguration
TOCTitle: New-CsUserReplicatorConfiguration
ms:assetid: eb4dee9e-9ba4-4726-8f7c-b355433ed594
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399059(v=OCS.15)
ms:contentKeyID: 49314637
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsUserReplicatorConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new collection of User Replicator configuration settings. The User Replicator periodically retrieves up-to-date user account information from Active Directory and then synchronizes the new information with the current user data stored by Lync Server. This cmdlet is designed for use with Lync Online and will not work with the on-premises version of Lync Server.

## 语法

``` PowerShell
New-CsUserReplicatorConfiguration
    -Identity <XdsIdentity>
    [-ADDomainNamingContextList <PSListModifier>]
    [-Confirm [<SwitchParameter>]]
    [-Force <SwitchParameter>]
    [-InMemory <SwitchParameter>]
    [-ReplicationCycleInterval <TimeSpan>]
    [-WhatIf [<SwitchParameter>]]
```

## Examples

## EXAMPLE 1

The command shown in Example 1 creates a new collection of User Replicator configuration settings for the service Registrar:atl-cs-001.litwareinc.com. Because no additional parameters are specified, the new collection will use the default user replicator values.

``` PowerShell
New-CsUserReplicatorConfiguration -Identity "service:Registrar:atl-cs-001.litwareinc.com"
```

## EXAMPLE 2

Example 2 also creates a new collection of user replicator configuration settings for the service Registrar:atl-cs-001.litwareinc.com. In this case, however, the ADDomainNamingContextList is added, along with the distinguished names of the two domains to synchronize with: fabrikam.com and contoso.com. This new collection of user replicator configuration settings will only configure with those two domains, even if other domains are available.

``` PowerShell
New-CsUserReplicatorConfiguration -Identity "service:Registrar:atl-cs-001.litwareinc.com" -ADDomaiNamingContextList @{Add="dc=fabrikam,dc=com","dc=contoso.com"}
```

## Detailed Description

Although Lync Server maintains its own database of user accounts and user account data, Lync Server still relies on Active Directory as the ultimate source for user information. For example, when a new Active Directory user account is created, you must supply basic information about the user account (such as the Active Directory display name). When a user is enabled for Lync Server, however, you do not need to specify a new display name. That’s because Lync Server uses the display name already stored in Active Directory.

User account information, including the Active Directory display name, is subject to change over time. For example, a user who gets married might change her last name and, in turn, need to change her display name as well. In order to ensure that the Lync Server database and Active Directory remain in synch, Lync Server must periodically check in with Active Directory, retrieve the latest user account updates, and then modify the Lync Server user database accordingly. This synchronization between Active Directory and Lync Server is carried out by the User Replicator.

When you install Lync Server a global set of User Replicator configuration settings is created for you. By default, these settings are used to manage the User Replicator on an organization-wide basis. Management of the User Replicator consists of identifying the domains that Lync Server needs to synch with as well as indicating how often the User Replicator checks Active Directory for user account updates. You can also create additional collections at the service scope, but only if you are working with Lync Online.

New User Replicator configurations settings are created using the **New-CsUserReplicatorConfiguration** cmdlet. Note that these settings can only be created at the service scope and only for Lync Online. You cannot create new User Replicator settings for the on-premises version of Lync Server.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsUserReplicatorConfiguration** cmdlet: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself) run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsUserReplicatorConfiguration"}

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
<td><p>Unique identifier of the User Replicator configuration settings to be created. Settings can only be created at the service scope, and only for the Registrar service. That means that new settings must have an Identity similar to this: -Identity &quot;service:Registrar:atl-cs-001.litwareinc.com&quot;.</p>
<p>Note that this applies only to Lync Server.</p></td>
</tr>
<tr class="even">
<td><p><em>ADDomainNamingContextList</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Distinguished names of the Active Directory domains that the User Replicator must synchronize with. For example, to add a domain to the list use syntax similar to this:</p>
<p>-ADDomainNamingContextList @{Add=&quot;dc=fabrikam,dc=com&quot;}</p>
<p>You can add more than one domain name when calling the <strong>New-CsUserReplicatorConfiguration</strong> cmdlet. To do this, simply separate the domain names by using a comma:</p>
<p>-ADDomainNamingContextList @{Add=&quot;dc=fabrikam,dc=com&quot;,&quot;dc=contoso,dc=com&quot;}</p>
<p></p>
<p>If you set this property to a null value the user replicator will discover and synchronize with all available domains. If this property is not null then the replicator will only synchronize with the domains specified in the ADDomainNamingContextList.</p></td>
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
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="even">
<td><p><em>ReplicationCycleInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>Represents the amount of time that the User Replicator waits before checking for user account updates in Active Directory. The replication cycle interval can be any time value between 1 second, and 23 hours, 59 minutes, and 59 seconds; the default value is 1 minute. The interval must be expressed using the format hours:minutes:seconds. For example, this syntax sets to time interval to one hour and 15 minutes: -ReplicationCycleInterval 01:15:00.</p></td>
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

None. The **New-CsUserReplicatorConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **New-CsUserReplicatorConfiguration** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.UserReplicator.UserReplicatorConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsUserReplicatorConfiguration](get-csuserreplicatorconfiguration.md)  
[Remove-CsUserReplicatorConfiguration](remove-csuserreplicatorconfiguration.md)  
[Set-CsUserReplicatorConfiguration](set-csuserreplicatorconfiguration.md)

