---
title: Test-CsMcxPushNotification
TOCTitle: Test-CsMcxPushNotification
ms:assetid: db81339b-f79a-418a-b29d-8596dff7a210
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690043(v=OCS.15)
ms:contentKeyID: 49314445
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsMcxPushNotification

 

_**上一次修改主题：** 2015-03-09_

Verifies that the push notification service is working. The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) provides a way to send notifications about events such as new instant messages or new voice mail to mobile devices like iPhones and Windows Phones, even if the Lync application on those devices is currently suspended or running in the background. 此 cmdlet 是在 2011 年 11 月版的 Lync Server 2010 累积更新中引入的。

## 语法

    Test-CsMcxPushNotification -AccessEdgeFqdn <String> [-Certificate <X509Certificate2>] [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>]

## Examples

## EXAMPLE 1

The command shown in Example 1 tests the push notification service accessed through the Edge server atl-edge-001.litwareinc.com. The AccessEdgeFqdn must point to the internal edge of the proxy server to which push notification traffic is directed.

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

## Detailed Description

The Apple Push Notification Service and the Lync Server Push Notification Service enable users running Lync on their Apple iPhone or Windows Phone to receive notifications about Lync events even when Lync Server is suspended or running in the background. For example, users can receive notice for events such as these:

\- Invitations to a new instant messaging session or conference

\- New instant messages

\- New voice mail

Without the push notification service, users would receive these notices only when Lync Server was in the foreground and serving as the active application.

The Test-CsMcxPushNotification cmdlet provides a way for administrators to verify that the push notification service is working. When calling this cmdlet, make sure that the AccessEdgeFqdn parameter points to the internal edge of the proxy server to which push notification traffic is directed.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Test-CsMcxPushNotification** cmdlet locally: RTCUniversalServerAdmins.

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
<td><p><em>AccessEdgeFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name of the Access Edge server used to connect to the push notification service. The AccessedgeFqdn must point to the internal edge of the proxy server to which push notification traffic is directed.</p></td>
</tr>
<tr class="even">
<td><p><em>Certificate</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Security.Cryptography.X509Certificates.X509Certificate2</p></td>
<td><p>Enables you to specify an X509 certificate to use for authentication purposes</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>OutLoggerVariable</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>When present, detailed output from running the cmdlet will be stored in the specified variable. This variable includes a pair of methods – ToHTML and ToXML – that can then be used to save that output to either an HTML or an XML file.</p>
<p>To store output in a logger variable named $TestOutput use the following syntax:</p>
<p>-OutLoggerVariable TestOutput</p>
<p>Note: Do not use prepend a $ character when specifying the variable name.</p>
<p>To save the information stored in the logger variable to an HTML file, use a command similar to this:</p>
<p>$TestOutput.ToHTML() &gt; C:\Logs\TestOutput.html</p>
<p>To save the information stored in the logger variable to an XML file, use a command similar to this:</p>
<p>$TestOutput.ToXML() &gt; C:\Logs\TestOutput.xml</p></td>
</tr>
<tr class="odd">
<td><p><em>OutVerboseVariable</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>When present, detailed output from running the cmdlet will be stored in the specified variable. For example, to store output in a variable named $TestOutput use the following syntax</p>
<p>-OutVerboseVariable TestOutput</p>
<p>Do not prepend a $ character when specifying the variable name.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Test-CsMcxPushNotification** cmdlet does not accept pipelined input.

## Return Types

The **Test-CsMcxPushNotification** cmdlet returns an instance of the Microsoft.Rtc.SyntheticTransactions.TaskOutput object.

