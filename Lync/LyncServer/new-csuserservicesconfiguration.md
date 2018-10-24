---
title: New-CsUserServicesConfiguration
TOCTitle: New-CsUserServicesConfiguration
ms:assetid: bdcb11b5-b8bf-4d63-a8a5-11f2b43686dd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412926(v=OCS.15)
ms:contentKeyID: 49314099
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsUserServicesConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new collection of 用户服务 configuration settings. The User Services service is used to help maintain presence information and manage conferencing. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsUserServicesConfiguration -Identity <XdsIdentity> [-AnonymousUserGracePeriod <TimeSpan>] [-Confirm [<SwitchParameter>]] [-DeactivationGracePeriod <TimeSpan>] [-DefaultSubscriptionExpiration <Int64>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-MaintenanceTimeOfDay <DateTime>] [-MaxContacts <UInt16>] [-MaxPersonalNotes <UInt32>] [-MaxScheduledMeetingsPerOrganizer <UInt32>] [-MaxSubscriptionExpiration <Int64>] [-MaxSubscriptions <UInt16>] [-MinSubscriptionExpiration <Int64>] [-PresenceProviders <PSListModifier>] [-SubscribeToCollapsedDG <$true | $false>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 creates a new collection of User Services configuration settings for the Redmond site (-Identity site:Redmond). In addition to specifying the Identity, the command also sets the maximum number of contacts (-MaxContacts 500) and the time of day when maintenance occurs (-MaintenanceTimeOfDay "11:00 PM"). Note that this command will fail if User Services settings have already been configured for the Redmond site. That is because you are limited to one collection of settings per site.

    New-CsUserServicesConfiguration -Identity site:Redmond -MaxContacts 500 -MaintenanceTimeOfDay "11:00 PM"

## EXAMPLE 2

Example 2 also creates a new collection of User Services configuration settings for the Redmond site. However, in this example the collection is initially created in memory and is only later applied to the Redmond site. To do this, the first command in the example uses the **New-CsUserServicesConfiguration** cmdlet and the InMemory parameter to create a new collection (with the Identity site:Redmond) that exists only in memory. Because this collection exists only in memory, the User Services object must be stored in a variable. In this case, that’s a variable named $x.

After the virtual collection has been created, commands 2 and 3 are used to modify the values of the MaxContacts and the MaintenanceTimeOfDay properties. The final command in the example then uses the **Set-CsUserServicesConfiguration** cmdlet to transform these virtual settings into an actual collection of 用户服务 configuration settings applied to the Redmond site. This final step is crucial: if you do not call the **Set-CsUserServicesConfiguration** cmdlet no settings will be applied to the Redmond site, and your virtual settings will disappear as soon as you terminate your Windows PowerShell session or delete the variable $x.

    $x = New-CsUserServicesConfiguration -Identity site:Redmond -InMemory
    $x.MaxContacts = 500 
    $x.MaintenanceTimeOfDay = "11:00 PM"
    Set-CsUserServicesConfiguration -Instance $x

## Detailed Description

Lync Server relies on the User Services service to help maintain presence information for users and to manage meetings and conferences. In turn, the **CsUserServicesConfiguration** cmdlets are used to administer User Services configuration settings at the global, site, and service scope. (Note that the only service that can host User Services configuration settings is the User Services service itself.) These settings help determine such things as the number of contacts a user can have, the number of meetings a user can have scheduled at any one time, and the length of time that a given meeting can remain active.

The **New-CsUserServicesConfiguration** cmdlet provides a way for administrators to create a new collection of User Services configuration settings at the site or service scope. (New collections cannot be created at the global scope.) Note that any given site or service can only have, at most, a single collection of User Services configuration settings. Your command will fail if you try to create settings for, say, the Redmond site, and that site already hosts a collection of User Services configuration settings.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsUserServicesConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself) run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsUserServicesConfiguration"}

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
<td><p>Unique identifier for the User Services configuration settings to be created. To create settings at the site scope, use syntax similar to this: -Identity site:Redmond. To create settings at the service level, use syntax like this: -Identity service:UserServer:atl-cs-001.litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p><em>AnonymousUserGracePeriod</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>Represents the amount of time an anonymous (unauthenticated) user can remain in a meeting without an authenticated user being present in that same meeting. For example, if this value is set to 15 minutes an anonymous user can stay in the meeting for, at most, 15 minutes before an authenticated user must join. If an authenticated user does not join before the grace period expires then the anonymous user will be removed from the meeting. This setting applies to both scheduled meetings and to ad-hoc meetings created by clicking Meet Now in Microsoft Lync.</p>
<p>The AnonymousUserGracePeriod must be specified using the following format: days.hours:minutes:seconds (for example, 0.00:30:00 for 30 minutes). The grace period can be set to any value between 0 second and 1 day; the default value is 90 minutes (01:30:00).</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>DeactivationGracePeriod</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>The maximum amount of time that a meeting can remain active. This value must be specified using the following format: days.hours:minutes:seconds. For example, to enable a meeting to last for 60 hours you would use this format: 2.12:00:00 (2 days. 12 hours: 00 minutes: 00 seconds.)</p>
<p>The DeactivationGracePeriod must be between 8 hours and 365 days, inclusive. The default value is 1 day (1.00:00:00).</p></td>
</tr>
<tr class="odd">
<td><p><em>DefaultSubscriptionExpiration</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int64</p></td>
<td><p>Subscriptions are created any time a user makes a request for data such as presence information. When the request is made, the user (or, more correctly, the user’s client application) can request the length of time that the subscription remains valid before it must be renewed. If no such request is issued, then the subscription is set to the value specified by the DefaultSubscriptionExpiration property.</p>
<p>The default subscription time must be expressed as an integer value between 300 seconds (5 minutes) and 86400 seconds (24 hours), inclusive. The default value is 28800 seconds (8 hours).</p></td>
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
<td><p><em>MaintenanceTimeOfDay</em></p></td>
<td><p>Optional</p></td>
<td><p>System.DateTime</p></td>
<td><p>Indicates the time of day when regularly-scheduled database maintenance (such as the purging of outdated records) takes place. This value must be specified as a date-time value. You can use either the 24-hour format (for example, &quot;14:00&quot;) or the 12-hour format (for example, &quot;2:00 PM&quot;).</p>
<p>The default value for MaintenanceTimeOfDay is 1:00 AM (01:00:00).</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxContacts</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>The maximum number of contacts a user can have; the default value is 250. The MaxContacts property represents the absolute maximum number of contacts a user can have. However, you can use the CsClientPolicy cmdlets to limit certain users to a maximum number of contacts lower than the value of MaxContacts.</p></td>
</tr>
<tr class="even">
<td><p><em>MaxPersonalNotes</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Indicates the maximum number of personal notes that are stored in the user’s note history. By default, the last 3 personal notes are maintained in the note history. The maximum number of notes that can be maintained in the history is 10.</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxScheduledMeetingsPerOrganizer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>The maximum number of meetings that a single user can serve as organizer for at a given time. The default value is 1000. This means that, if a user is already the organizer for 1000 meetings, his or her attempt to schedule a new meeting (meeting number 1001) will fail.</p></td>
</tr>
<tr class="even">
<td><p><em>MaxSubscriptionExpiration</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int64</p></td>
<td><p>Subscriptions are created any time a user makes a request for data such as presence information. When the request is made, the user (or, more correctly, the user’s client application) can request the length of time that the subscription remains valid before it must be renewed. The MaxSubscriptionExpiration property represents the maximum amount of time that clients can be granted. For example, if the maximum time is set to 28800 seconds and a client requests a timeout interval of 86400 seconds, the client will be given the maximum allowed expiration period: 28800 seconds.</p>
<p>The maximum subscription time must be expressed as an integer value between 300 seconds (5 minutes) and 86400 seconds (24 hours), inclusive. The default value is 43200 seconds (12 hours).</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxSubscriptions</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>The maximum number of SIP subscribe dialogs that a user can have open at any one time. A subscribe dialog represents a request for SIP resources. The default value is 200.</p></td>
</tr>
<tr class="even">
<td><p><em>MinSubscriptionExpiration</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int64</p></td>
<td><p>Subscriptions are created any time a user makes a request for data such as presence information. When the request is made, the user (or, more correctly, the user’s client application) can request the length of time that the subscription remains valid before it must be renewed. The MinSubscriptionExpiration property represents the minimum amount of time that clients can be granted. For example, if the minimum time is set to 1200 seconds and a client requests a timeout interval of 200 seconds, the client will be given the minimum allowed expiration period: 1200 seconds.</p>
<p>The minimum subscription time must be expressed as an integer value between 300 seconds (5 minutes) and 86400 seconds (24 hours), inclusive. The default value is 1200 seconds (20 minutes).</p></td>
</tr>
<tr class="odd">
<td><p><em>PresenceProviders</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Collection of presence providers for the new User Service configuration settings. Presence providers are best added to a collection of User Service configuration settings by using the <strong>New-CsPresenceProvider</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>SubscribeToCollapsedDG</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If set to True (the default value), client applications will be allowed to subscribe to distribution groups that are not currently expanded in the Contacts list. This enables the client to maintain up-to-minute presence information for each member of the group. If set to False, client applications will not be allowed to subscribe to “collapsed” groups.</p></td>
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

None. The **New-CsUserServicesConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **New-CsUserServicesConfiguration** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.UserServices.UserServicesSettings object.

## 另请参阅

#### 其他资源

[Get-CsUserServicesConfiguration](get-csuserservicesconfiguration.md)  
[Remove-CsUserServicesConfiguration](remove-csuserservicesconfiguration.md)  
[Set-CsUserServicesConfiguration](set-csuserservicesconfiguration.md)

