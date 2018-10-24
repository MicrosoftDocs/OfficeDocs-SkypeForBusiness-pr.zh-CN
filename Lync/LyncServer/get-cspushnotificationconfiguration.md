---
title: Get-CsPushNotificationConfiguration
TOCTitle: Get-CsPushNotificationConfiguration
ms:assetid: ec2c17e5-ac4d-4d21-995a-642c5cf5c7bc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690049(v=OCS.15)
ms:contentKeyID: 49314645
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsPushNotificationConfiguration

 

_**上一次修改主题：** 2015-03-09_

Retrieves information about the push notification configuration settings currently in use in your organization. The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) provides a way to send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Lync application on those devices is currently suspended or running in the background. 此 cmdlet 是在 2011 年 11 月版的 Lync Server 2010 累积更新中引入的。

## 语法

    Get-CsPushNotificationConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsPushNotificationConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>] [-Tenant <Guid>]

## Examples

## EXAMPLE 1

Example 1 returns information about all the push notification settings configured for use in your organization.

    Get-CsPushNotificationConfiguration

## EXAMPLE 2

The command shown in Example 2 returns information about a single collection of push notification settings: the settings configured for the Redmond site.

    Get-CsPushNotificationConfiguration -Identity "site:Redmond"

## EXAMPLE 3

In Example 3, the command returns all the push notification settings assigned to the site scope. To do this, the command uses the Filter parameter and the filter value "site:\*"; that filter value returns only those settings that have an Identity that begins with the string value "site:".

    Get-CsPushNotificationConfiguration -Filter "site:*"

## EXAMPLE 4

Example 4 returns all the push notification settings where push notifications for iPhones have been disabled. To do this, the command first uses the **Get-CsPushNotificationConfiguration** cmdlet to return a collection of all the push notification settings currently in use in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those settings where the EnableApplePushNotificationService property is equal to (-eq) False.

    Get-CsPushNotificationConfiguration | Where-Object {$_.EnableApplePushNotificationService -eq $False}

## EXAMPLE 5

In Example 5, information is returned for all the push notification settings where either the Apple Push Notification Service and/or the Microsoft Push Notification Service have been disabled. To carry out this task, the command first uses the **Get-CsPushNotificationConfiguration** cmdlet in order to return a collection of all the push notification settings currently in use. This collection is then piped to the Where-Object cmdlet, which picks out those settings which meet one (or both) of the following criteria: 1) the EnableApplePushNotificationService property is equal to (-eq) False; 2) the EnableMicrosoftPushNotificationService property is equal to False. The –or operator tells Where-Object to look for settings that meet either criteria. To restrict the returned data to settings where both services have been disabled, use the –and operator instead:

Get-CsPushNotificationConfiguration | Where-Object {$\_.EnableApplePushNotificationService –eq $False –and $\_.EnableMicrosoftPushNotificationService –eq $False}

    Get-CsPushNotificationConfiguration | Where-Object {$_.EnableApplePushNotificationService -eq $False -or $_.EnableMicrosoftPushNotificationService -eq $False}

## Detailed Description

The Apple Push Notification Service and the Microsoft Push Notification Service enable users running Lync on their Apple iPhone or Windows Phone to receive notifications about Lync events even when Lync is suspended or running in the background. For example, users can receive notice for events such as these:

\- Invitations to a new instant messaging session or conference

\- New instant messages

\- New voice mail

Without the push notification service users would receive these notices only when Lync was in the foreground and serving as the active application.

Administrators have the ability to enable or disable push notifications for iPhone users and/or Windows Phone users. (By default, push notifications are disabled for both iPhone users and Windows Phone users.) Administrators can enable or disable push notifications at the global scope by using the **Set-CsPushNotificationConfiguration** cmdlet. They can also create custom push notification settings at the site scope by using the **New-CsPushNotificationConfiguration** cmdlet.

The **Get-CsPushNotificationConfiguration** cmdlet provides a way for you to return information about the push notification configuration settings currently in use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsPushNotificationConfiguration** cmdlet locally: RTCUniversalServerAdmins.

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
<td><p>Enables you to use wildcard characters in order to return a collection (or collections) of push notification configuration settings. To return a collection of all the settings configured at the site scope, use this syntax:</p>
<p>-Filter site:*</p>
<p>To return a collection of all the settings that have the string value &quot;Canada&quot; somewhere in their Identity (the only property you can filter on) use this syntax:</p>
<p>-Filter &quot;*Canada*&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Indicates the unique identifier for the collection of push notification settings you want to return. To refer to the global settings use this syntax:</p>
<p>-Identity global</p>
<p>To refer to a collection configured at the site scope, use syntax similar to this:</p>
<p>-Identity site:Redmond</p>
<p>Note that you cannot use wildcards when specifying an Identity. If you need to use wildcards, then include the Filter parameter instead.</p>
<p>If this parameter is not specified, then the <strong>Get-CsPushNotificationConfiguration</strong> cmdlet returns a collection of all the push notification configuration settings in use in the organization.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the push notification configuration data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Office 365 tenant account whose push notification configuration settings are to be modified. For example:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>You can return the tenant ID for each of your tenants by running this command:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p>
<p>If you are using a remote session of Windows PowerShell and are connected only to Skype for Business Online you do not have to include the Tenant parameter. Instead, the tenant ID will automatically be filled in for you based on your connection information. The Tenant parameter is primarily for use in a hybrid deployment.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Get-CsPushNotificationConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsPushNotificationConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.WriteableConfig.Settings.PushNotificationConfiguration.PushNotificationConfiguration object.

