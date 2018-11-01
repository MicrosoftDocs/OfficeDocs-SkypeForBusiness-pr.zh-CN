﻿---
title: Get-CsMcxConfiguration
TOCTitle: Get-CsMcxConfiguration
ms:assetid: a09c0d49-5377-4a22-89e6-2751030ccf20
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690031(v=OCS.15)
ms:contentKeyID: 49313786
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsMcxConfiguration

 

_**上一次修改主题：** 2015-03-09_

Retrieves information about the Lync Server Mobility Service configuration settings currently in use in your organization. The Mobility Service enables users of mobile phones such as iPhones and Windows Phones to do such things as exchange instant messages and presence information; store and retrieve voice mail internally instead of with their wireless provider; and take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing. 此 cmdlet 是在 2011 年 11 月版的 Lync Server 2010 累积更新中引入的。

## 语法

    Get-CsMcxConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsMcxConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

The command shown in Example 1 returns information about all the Mobility Service configuration settings currently in use in your organization.

    Get-CsMcxConfiguration

## EXAMPLE 2

In Example 2, information is returned only for the global collection of Mobility Service configuration settings.

    Get-CsMcxConfiguration -Identity "global"

## EXAMPLE 3

Example 3 returns information about all the Mobility Service configuration settings assigned to the service scope. To do this, the Filter parameter is included along with the string value "service:\*". That filter value returns all the Mobility Service configuration settings that have an Identity that begins with the string value "service:".

    Get-CsMcxConfiguration -Filter "service:*"

## EXAMPLE 4

In Example 4, the only Mobility Service configuration settings returned are those where the ExposedWebURL property is equal to External. To do this, the command first calls the **Get-CsMcxConfiguration** cmdlet without any parameters in order to return a collection of all the Mobility Service configuration settings currently in use in the organization. That collection is then piped to the **Where-Object** cmdlet, which picks out only those settings where the ExposedWebURL property is equal to (-eq) External.

    Get-CsMcxConfiguration | Where-Object {$_.ExposedWebURL -eq "External"}

## EXAMPLE 5

Example 5 returns any and all of the Mobility Service configuration settings where the SessionExpirationInterval property is set to a value less than the default value of 259200 seconds (72 hours). This is done by first using the **Get-CsMcxConfiguration** cmdlet to return a collection of all the existing Mobility Service configuration settings. That collection is then piped to the **Where-Object** cmdlet, which, in turn, selects only those settings where the SessionExpirationInterval property is less than 259200.

    Get-CsMcxConfiguration | Where-Object {$_.SessionExpirationInterval -lt 259200}

## Detailed Description

Lync Server Mobility Service extends many of the capabilities of Lync Server to mobile devices such as Apple iPhones, Windows Phone, Android phones, and Nokia phones. Among other things, users can use these phones to exchange instant message and presence information, and to receive notifications of new voice mails. Thanks to the push notification service (Apple Push Notification Service and Microsoft Push Notification Service), users with iPhones or Windows Phones can receive these notifications even if Lync is running in the background. The Mobility Service also provides the opportunity for organizations to enable Call via Work. With Call via Work, users can make a call from their mobile phone and make it appear as though the call originated from their work phone; for example, Caller ID systems will see the user's work number instead of his or her mobile phone number.

The Mobility Service itself is managed by using Mobility Service configuration settings that can be applied to the global scope, the site scope, or the service scope (for the Web server service only). These settings control such things as the maximum length of time for a Mobility Service session; whether or not the Lync Server Autodiscovery Service (which directs Mobility Service users to the appropriate Registrar pool) is available to users who log on outside the organization's firewall; and the location of the push notification service provider. The **Get-CsMcxConfiguration** cmdlet provides a way for administrators to retrieve information about all the Mobility Service configuration settings currently in use in their organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsMcxConfiguration** cmdlet locally: RTCUniversalServerAdmins.

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
<td><p>Enables you to use wildcard characters in order to return a collection of Mobility Service configuration settings. For example, to return a collection of all the settings configured at the site scope, use this syntax:</p>
<p>-Filter site:*</p>
<p>To return a collection of all the settings configured at the service scope, use this syntax:</p>
<p>-Filter service:*</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Indicates the unique identifier for the collection of Mobility Service configuration settings you want to return. To refer to the global settings, use this syntax:</p>
<p>-Identity global</p>
<p>To refer to a collection configured at the site scope, use syntax similar to this:</p>
<p>-Identity site:Redmond</p>
<p>To refer to a collection configured at the service scope, use syntax like this:</p>
<p>-Identity service:WebServer:atl-cs-001.litwareinc.com</p>
<p>Note that you cannot use wildcards when specifying an Identity. If you need to use wildcards then use the Filter parameter instead.</p>
<p>If this parameter is not specified, then the <strong>Get-CsMcxConfiguration</strong> cmdlet returns a collection of all the Mobility Service configuration settings in use in the organization.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the Mobility Service configuration data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Get-CsMcxConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsMcxConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.WriteableConfig.Settings.McxConfiguration.McxConfiguration object.

