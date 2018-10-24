---
title: Remove-CsPushNotificationConfiguration
TOCTitle: Remove-CsPushNotificationConfiguration
ms:assetid: 77574e30-a75f-4aaa-b2d8-ccbabda31797
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690028(v=OCS.15)
ms:contentKeyID: 49313295
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsPushNotificationConfiguration

 

_**上一次修改主题：** 2015-03-09_

Deletes an existing collection of push notification settings. The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) provides a way to send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Lync application on those devices is currently suspended or running in the background. 此 cmdlet 是在 2011 年 11 月版的 Lync Server 2010 累积更新中引入的。

## 语法

    Remove-CsPushNotificationConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 deletes the collection of push notification settings assigned to the Redmond site.

    Remove-CsPushNotificationConfiguration -Identity "site:Redmond"

## EXAMPLE 2

Example 2 deletes all the push notification settings configured at the site scope. To perform this task, the cmdlet first uses the **Get-CsPushNotificationConfiguration** cmdlet and the Filter parameter to return a collection of all the settings configured at the site scope; the filter value "site:\*" limits the returned items to settings that have an Identity that begins with the string value "site:". The site-scoped settings are then piped to, and deleted by, the **Remove-CsPushNotificationConfiguration** cmdlet.

    Get-CsPushNotificationConfiguration -Filter "site:*" | Remove-CsPushNotificationConfiguration

## EXAMPLE 3

Example 3 shows you how can remove all the push notification configuration settings where push notifications from the Microsoft Push Notification Service have been disabled. To do this, the command first uses the **Get-CsPushNotificationConfiguration** cmdlet to return a collection of all the push notification settings currently in use. That collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableMicrosoftPushNotificationService property is equal to (-eq) False. This filtered collection is then piped to the **Remove-CsPushNotificationConfiguration** cmdlet which, in turn, deletes each item in the collection.

    Get-CsPushNotificationConfiguration | Where-Object {$_.EnableMicrosoftPushNotificationService -eq $False} | Remove-CsPushNotificationConfiguration

## Detailed Description

The Apple Push Notification Service and the Microsoft Push Notification Service enable users running Lync on their Apple iPhone or Windows Phone to receive notifications about Lync events even when Lync is suspended or running in the background. For example, users can receive notice for events such as these:

\- Invitations to a new instant messaging session or conference

\- New instant messages

\- New voice mail

Without the push notification service users would receive these notices only when Lync was in the foreground and serving as the active application.

Administrators have the ability to enable or disable push notifications for iPhone users and/or Windows Phone users. (By default, push notifications are disabled for both iPhone users and Windows Phone users.) Administrators can enable or disable push notifications at the global scope by using the **Set-CsPushNotificationConfiguration** cmdlet. They can also create custom push notification settings at the site scope by using the **New-CsPushNotificationConfiguration** cmdlet.

These custom settings can later be deleted by using the **Remove-CsPushNotificationConfiguration** cmdlet. If you delete settings configured at the site scope, then users in that site will automatically be managed by the global push notification settings.

Note that the **Remove-CsPushNotificationConfiguration** cmdlet can also be run against the global settings. If you do that, however, the global settings will not be removed; instead, the properties in the global settings will all be reset to their default values. In this case, that means that push notifications will be disabled from both the Apple Push Notification Service and the Microsoft Push Notification Service.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsPushNotificationConfiguration** cmdlet locally: RTCUniversalServerAdmins.

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
<td><p>Unique identifier for the collection of push notification configuration settings to be removed. To remove the global collection, use the following syntax:</p>
<p>-Identity global</p>
<p>Note that you cannot actually remove the global settings; instead, you can only reset the properties to their default values.</p>
<p>To remove a site collection, use syntax similar to this:</p>
<p>-Identity site:Redmond</p>
<p>You cannot use wildcards when specifying a policy Identity.</p></td>
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
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account for the push notification configuration settings being deleted. For example:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>You can return the tenant ID for each of your tenants by running this command:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
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

Microsoft.Rtc.Management.WriteableConfig.Settings.PushNotificationConfiguration.PushNotificationConfiguration. The **Remove-CsPushNotificationConfiguration** cmdlet accepts pipelined instances of the PushNotificationConfiguration object.

## Return Types

None. Instead, the **Remove-CsPushNotificationConfiguration** cmdlet deletes instances of the Microsoft.Rtc.Management.WriteableConfig.Settings.PushNotificationConfiguration.PushNotificationConfiguration object.

