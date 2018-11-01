---
title: Set-CsPushNotificationConfiguration
TOCTitle: Set-CsPushNotificationConfiguration
ms:assetid: 3aacdb2b-b6dd-4615-a3f9-68360f3ae483
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690013(v=OCS.15)
ms:contentKeyID: 49312543
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsPushNotificationConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing collection of push notification configuration settings. The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) provides a way to send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Lync application on those devices is currently suspended or running in the background. 此 cmdlet 是在 2011 年 11 月版的 Lync Server 2010 累积更新中引入的。

## 语法

    Set-CsPushNotificationConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsPushNotificationConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-EnableApplePushNotificationService <$true | $false>] [-EnableMicrosoftPushNotificationService <$true | $false>] [-Force <SwitchParameter>] [-Tenant <Guid>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 disables push notifications from the Apple Push Notification Service for the Redmond site.

    Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

## EXAMPLE 2

Example 2 disables push notifications from the Apple Push Notification Service for all the sites currently hosting push notification settings. To do this, the command first uses the **Get-CsPushNotificationConfiguration** cmdlet and the Filter parameter to return all the push notification settings configured at the site scope; the filter value "site:\*" limits the returned settings to those that have an Identity that begins with the string value "site:". That collection of settings is then piped to the **Set-CsPushNotificationConfiguration** cmdlet, which takes each item in the collection and sets the EnableApplePushNotificationService property to False.

    Get-CsPushNotificationConfiguration -Filter "site:*" | Set-CsPushNotificationService -EnableApplePushNotificationService $False

## EXAMPLE 3

Example 3 demonstrates how you can locate all the push notification settings where push notifications from the Microsoft Push Notification Service are disabled, and then disable push notifications from the Apple Push Notification Service for each of those settings as well. To carry out this task, the command first uses the **Get-CsPushNotificationConfiguration** cmdlet to return a collection of all the push notification settings currently in use the organization. This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableMicrosoftPushNotificationService property is equal to (-eq) False. That filtered collection is then piped to the **Set-CsPushNotificationConfiguration** cmdlet, which takes each item in the filtered collection and sets the EnableApplePushNotificationService property to False.

    Get-CsPushNotificationConfiguration | Where-Object {$_.EnableMicrosoftPushNotificationService -eq $False} | Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $False

## Detailed Description

The Apple Push Notification Service and the Microsoft Push Notification Service enable users running Lync on their Apple iPhone or Windows Phone to receive notifications about Lync events even when Lync is suspended or running in the background. For example, users can receive notice for events such as these:

\- Invitations to a new instant messaging session or conference

\- New instant messages

\- New voice mail

Without the push notification service users would receive these notices only when Lync was in the foreground and serving as the active application.

Administrators have the ability to enable or disable push notifications for iPhone users and/or Windows Phone users. (By default, push notifications are disabled for both iPhone users and Windows Phone users.) Administrators can enable or disable push notifications at the global scope by using the **Set-CsPushNotificationConfiguration** cmdlet. They can also create custom push notification settings at the site scope by using the **New-CsPushNotificationConfiguration** cmdlet. These custom settings can also be modified by using the **Set-CsPushNotificationConfiguration** cmdlet.

With the push notification configuration settings there are only two property values for Administrators to manage: EnableApplePushNotificationService, which determines whether push notifications are sent to iPhone users; and EnableMicrosoftPushNotificationService, which determines whether push notifications are sent to Windows Phone users. Note that these property values do not have to be set to the same value. For example, you could enable push notifications to Windows Phone users (by setting EnableMicrosoftPushNotificationService to True) yet, at the same, disable notifications to iPhone users by setting EnableApplePushNotificationService to False.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsPushNotificationConfiguration** cmdlet locally: RTCUniversalServerAdmins.

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
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableApplePushNotificationService</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, iPhone users will receive push notifications from the Apple Push Notification Service. When set to False, iPhone users will not receive these notifications.</p>
<p>The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableMicrosoftPushNotificationService</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, Windows Phone users will receive push notifications from the Microsoft Push Notification Service. When set to False, Windows Phone users will not receive these notifications.</p>
<p>The default value is False.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Indicates the Identity of the push notification configuration settings to be modified. To refer to the global settings, use this syntax:</p>
<p>-Identity global</p>
<p>To refer to site settings, use syntax similar to this:</p>
<p>-Identity site:Redmond</p>
<p>Note that you cannot use wildcards when specifying an Identity.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>Push configuration object</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
</tr>
<tr class="odd">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account for the push notification settings being modified. For example:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>You can return the tenant ID for each of your tenants by running this command:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p>
<p>If you are using a remote session of Windows PowerShell and are connected only to Skype for Business Online you do not have to include the Tenant parameter. Instead, the tenant ID will automatically be filled in for you based on your connection information. The Tenant parameter is primarily for use in a hybrid deployment.</p></td>
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

Microsoft.Rtc.Management.WriteableConfig.Settings.PushNotificationConfiguration.PushNotificationConfiguration. The **Set-CsPushNotificationConfiguration** cmdlet accepts pipelined instances of the PushNotificationConfiguration object.

## Return Types

None. Instead, the **Set-CsPushNotificationConfiguration** cmdlet modifies existing instances of the Microsoft.Rtc.Management.WriteableConfig.Settings.PushNotificationConfiguration.PushNotificationConfiguration object.

