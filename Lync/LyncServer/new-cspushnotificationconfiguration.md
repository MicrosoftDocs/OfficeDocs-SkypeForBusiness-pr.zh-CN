---
title: New-CsPushNotificationConfiguration
TOCTitle: New-CsPushNotificationConfiguration
ms:assetid: 8bf61c72-7902-4075-9388-47a7dd4e649c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690027(v=OCS.15)
ms:contentKeyID: 49313527
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsPushNotificationConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new collection of push notification configuration settings at the site scope. The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) provides a way to send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Lync application on those devices is currently suspended or running in the background. 此 cmdlet 是在 2011 年 11 月版的 Lync Server 2010 累积更新中引入的。

## 语法

    New-CsPushNotificationConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-EnableApplePushNotificationService <$true | $false>] [-EnableMicrosoftPushNotificationService <$true | $false>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 creates a new collection of push notification settings for the Redmond site, and enables push notifications from both the Apple Push Notification Service and the Microsoft Push Notification Service. The latter is done by setting both the EnableApplePushNotificationService and the EnableMicrosoftPushNotificationService properties to True.

    New-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService -$True

## EXAMPLE 2

Example 2 shows how you can create a set of push configuration settings for each of your Lync Server sites. To do this, the command first uses the **Get-CsSite** cmdlet to return a collection of all your Lync Server sites. That collection is then piped to the **ForEach-Object** cmdlet, which takes each site in the collection, calls the **New-CsPushNotificationConfiguration** cmdlet, and creates a new set of push notification configuration settings for that site. Note that this command will fail for any site that already hosts a collection of push notification configuration settings.

    Get-CsSite | ForEach-Object {New-CsPushConfigurationNotification -Identity $_.Identity}

## EXAMPLE 3

Example 3 demonstrates the use of the InMemory parameter to create a collection of push notification configuration settings that initially exist only in memory. To do this, the example creates a new collection of settings (with the Identity site:Redmond) and stores this collection in a variable named $x. Note that, after this first command executes, the collection exists only in memory; if you run the **Get-CsPushNotificationConfiguration** cmdlet, you will not see an entry for site:Redmond.

In the next two commands, both the EnableApplePushNotificationService and the EnableMicrosoftPushNotificationService properties for this virtual collection of settings are set to True, which enables push notifications from both the Apple Push Notification Service and the Microsoft Push Notification Service. Finally, the last command uses the **Set-CsPushNotificationConfiguration** cmdlet to transform the virtual push notification settings into an actual collection of settings applied to the Redmond site. If you do not call the **Set-CsPushNotificationConfiguration** cmdlet, these settings will remain in memory only and will disappear when your Windows PowerShell session is terminated or the variable $x is deleted.

    $x = New-CsPushNotificationConfiguration -Identity "site:Redmond" -InMemory
    $x.EnableApplePushNotificationService = $True 
    $x.EnableMicrosoftPushNotificationService = $True
    Set-CsPushNotificationConfiguration -Instance $x

## Detailed Description

The Apple Push Notification Service and the Microsoft Push Notification Service enable users running Lync on their Apple iPhone or Windows Phone to receive notifications about Lync events even when Lync is suspended or running in the background. For example, users can receive notice for events such as these:

\- Invitations to a new instant messaging session or conference

\- New instant messages

\- New voice mail

Without the push notification service, users would receive these notices only when Lync was in the foreground and serving as the active application.

Administrators have the ability to enable or disable push notifications for iPhone users and/or Windows Phone users. (By default, push notifications are disabled for both iPhone users and Windows Phone users.) Administrators can enable or disable push notifications at the global scope by using the **Set-CsPushNotificationConfiguration** cmdlet. They can also create custom push notification settings at the site scope by using the **New-CsPushNotificationConfiguration** cmdlet. That gives Administrators the ability to provide push notifications to users in some sites (for example, Redmond) while restricting the use of these notifications in other sites.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsPushNotificationConfiguration** cmdlet locally: RTCUniversalServerAdmins.

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
<td><p>Push notification settings can only be created at the site scope. To specify a new collection of settings for a site, use syntax similar to this:</p>
<p>-Identity &quot;site:Redmond&quot;</p>
<p>Note that this command will fail if the Redmond site already hosts a collection of push notification settings.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableApplePushNotificationService</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, iPhone users will receive push notifications from the Apple Push Notification Service. When set to False, iPhone users will not receive these notifications.</p>
<p>The default value is False.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableMicrosoftPushNotificationService</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, Windows Phone users will receive push notifications from the Microsoft Push Notification Service. When set to False, Windows Phone users will not receive these notifications.</p>
<p>The default value is False.</p></td>
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
<td><p>Creates an object reference without actually committing the object as a permanent change. If you assign the output of a command called with this parameter to a variable, you can make changes to the properties of the object reference and then commit those changes by calling this cmdlet’s matching Set- cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account for which the new push notification configuration settings are being created. For example:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>You can return the tenant ID for each of your tenants by running this command:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
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

None. The **New-CsPushNotificationConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **New-CsPushNotificationConfiguration** cmdlet creates new instances of the Microsoft.Rtc.Management.WriteableConfig.Settings.PushNotificationConfiguration.PushNotificationConfiguration object.

