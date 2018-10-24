---
title: New-CsMcxConfiguration
TOCTitle: New-CsMcxConfiguration
ms:assetid: 9eebea4a-64a3-424c-9b05-0579c4e8111e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690035(v=OCS.15)
ms:contentKeyID: 49313762
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsMcxConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates a new collection of Lync Server 2013 Mobility Service configuration settings at the site or the service scope. The Mobility Service enables users of mobile phones such as iPhones and Windows Phones to do such things as exchange instant messages and presence information; store and retrieve voice mail internally instead of with their wireless provider; and take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing. 此 cmdlet 是在 2011 年 11 月版的 Lync Server 2010 累积更新中引入的。

## 语法

    New-CsMcxConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-ExposedWebURL <External | Internal>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-PushNotificationProxyUri <String>] [-SessionExpirationInterval <UInt32>] [-SessionShortExpirationInterval <UInt32>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, a new collection of Mobility Service configuration settings is created for (and automatically assigned to) the Redmond site. In this example, two changes are made to the default Mobility Service configuration settings: the ExposedWebURL property is to Internal, and the SessionShortExpirationInterval property is set to 7200 seconds.

    New-CsMcxConfiguration -Identity "site:Redmond" -ExposedWebURL Internal -SessionShortExpirationInterval 7200

## EXAMPLE 2

In Example 2, an identical set of Mobility Service configuration settings is created for each Web server currently in use in an organization. To perform this task, the **Get-CsService** cmdlet is used, along with the WebServer parameter, to return a collection of all the existing Web servers; this collection is then piped to the **For-Each** object cmdlet. In turn, the **ForEach-Object** cmdlet takes each server in the collection and runs the **New-CsMcxConfiguration** cmdlet in order to create new Mobility Service configuration settings on that server.

    Get-CsService -WebServer | ForEach-Object {New-CsMcxConfiguration -Identity $_.Identity -ExposedWebURL Internal -SessionShortExpirationInterval 7200}

## EXAMPLE 3

Example 3 demonstrates how the InMemory parameter enables you to create a new collection of Mobility Service configuration settings in memory, modify the property values of that collection, and then save the collection to Lync Server. To do this, the first command in the collection creates a new collection of Mobility Service configuration settings that have the Identity site:Redmond. However, instead of being automatically created and assigned to the Redmond site, these settings are created in memory only (because of the InMemory parameter) and are then stored in a variable named $x.

Commands 2 and 3 in the example show how you can modify the property values of this virtual Mobility Service configuration collection. After you have finished modifying the property values, you can then use the **Set-CsMcxConfiguration** cmdlet, and the Instance parameter, to turn the virtual settings into an actual collection of Mobility Service configuration settings assigned to the Redmond site. Note that if you do not call the **Set-CsMcxConfiguration** cmdlet, no settings will ever be assigned to the Redmond site and your virtual collection will disappear as soon as you exit your Windows PowerShell session or delete the variable $x.

    $x = New-CsMcxConfiguration -Identity "site:Redmond" -InMemory
    $x.ExposedWebURL = "Internal"
    $x.SessionShortExpirationInterval = 7200
    Set-CsMcxConfiguration -Instance $x

## Detailed Description

The Mobility Service extends many of the capabilities of Lync Server to mobile devices such as Apple iPhones, Windows Phone, Android phones, and Nokia phones. Among other things, users can use these phones to exchange instant message and presence information, and to receive notifications of new voice mails. Thanks to the push notification service (Apple Push Notification Service and Microsoft Push Notification Service), users with iPhones or Windows Phones can receive these notifications even if Lync is running in the background. The Mobility Service also provides the opportunity for organizations to enable Call via Work. With Call via Work, users can make a call from their mobile phone and make it appear as though the call originated from their work phone; for example, Caller ID systems will display the user's work number instead of his or her mobile phone number.

The Mobility Service itself is managed by using Mobility Service configuration settings that can be applied to the global scope, the site scope, or the service scope (for the Web server service only). These settings control such things as the maximum length of time for a Mobility Service session; whether or not the Lync Server Autodiscovery Service (which directs Mobility Service users to the appropriate Registrar pool) is available to users who log on outside the organization's firewall); and the location of the push notification service provider.

When you install Lync Server, a single collection of Mobility Service configuration settings is created at the global scope; however, administrators can use the **New-CsMcxConfiguration** cmdlet to create custom configuration settings at either the site or the service scope.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsMcxConfiguration** cmdlet locally: RTCUniversalServerAdmins.

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
<td><p>Unique identifier of the collection of Mobility Service configuration settings to be created. To create settings at the site scope, use the prefix &quot;site:&quot; followed by the site name. For example:</p>
<p>-Identity &quot;site:Redmond&quot;</p>
<p>To create settings configured at the service scope, use syntax like this:</p>
<p>-Identity service:WebServer:atl-cs-001.litwareinc.com</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>ExposedWebURL</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.McxConfiguration.ExposedWebURL</p></td>
<td><p>Indicates whether the URL used by the Autodiscovery Service is accessible to users both inside and outside the organization firewall (External) or only accessible to users inside the firewall (Internal).</p>
<p>Allowed values are: Internal or External. The default value is External.</p></td>
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
<td><p>Creates an object reference without actually committing the object as a permanent change. If you assign the output of a command called with this parameter to a variable, you can make changes to the properties of the object reference and then commit those changes by calling this cmdlet’s matching Set- cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>PushNotificationProxyUri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URI of a service provider that can forward push notification requests to the Apple Push Notification Service and the Microsoft Push Notification Service. The PushNotificationProxyUri must be in the form of a SIP address; for example:</p>
<p>-PushNotificationProxyUri &quot;sip:push@push.lync.com&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>SessionExpirationInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Length of time, in seconds, of a mobile session for iPhone or Widows Phone users. If Lync is running in the background on these phones, users will receive push notifications as long as the session expiration interval has not expired.</p>
<p>The mobile device must send a notice to the server indicating that the device is still active before the session timeout is reached. If it does not, the device will be listed as inactive and the user will have to log back on to the system.</p>
<p>This property can be set to any integer value between 120 and 4294967295, inclusive. The default value is 259200 seconds (3 days). Note that the value of the SessionExpirationInterval property must be greater than the value of the SessionShortExpirationInterval property.</p></td>
</tr>
<tr class="even">
<td><p><em>SessionShortExpirationInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Length of time, in seconds, of a mobile session for Android or Nokia phone users.</p>
<p>The mobile device must send a notice to the server indicating that the device is still active before the session timeout is reached. If it does not, the device will be listed as inactive and the user will have to log back on to the system.</p>
<p>This property can be set to any integer value between 120 and 4294967295, inclusive. The default value is 3600 seconds (1 hour). Note that the value of the SessionExpirationInterval property must be greater than the value of the SessionShortExpirationInterval property.</p></td>
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

None. The **New-CsMcxConfiguration** cmdlet does not accept pipelined input.

## Return Types

Creates new instances of the Microsoft.Rtc.Management.WriteableConfig.Settings.McxConfiguration.McxConfiguration object.

