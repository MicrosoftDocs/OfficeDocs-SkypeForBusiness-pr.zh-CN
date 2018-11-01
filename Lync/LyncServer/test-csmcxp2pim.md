---
title: Test-CsMcxP2PIM
TOCTitle: Test-CsMcxP2PIM
ms:assetid: 443a3b31-6f58-4570-9eaa-310e73c39e03
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690020(v=OCS.15)
ms:contentKeyID: 49312688
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsMcxP2PIM

 

_**上一次修改主题：** 2015-03-09_

Tests the ability of a pair of users to exchange instant messages by using the Lync Server Mobility Service. The Mobility Service enables users of mobile phones such as iPhones and Windows Phones to do such things as exchange instant messages and presence information; store and retrieve voice mail internally instead of with their wireless provider; and take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing. 此 cmdlet 是在 2011 年 11 月版的 Lync Server 2010 累积更新中引入的。

## 语法

    Test-CsMcxP2PIM -ReceiverSipAddress <String> -SenderSipAddress <String> <COMMON PARAMETERS>

    Test-CsMcxP2PIM -ReceiverCredential <PSCredential> -ReceiverSipAddress <String> -SenderCredential <PSCredential> -SenderSipAddress <String> <COMMON PARAMETERS>

    COMMON PARAMETERS: -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -TargetFqdn <String> [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>] [-RegistrarPort <Int32>]

## Examples

## EXAMPLE 1

The commands shown in Example 1 test to see whether or not a pair of users – Ken Myer and Pilar Ackerman – are able to exchange instant messages by using the Mobility Service. To do this, the first two commands in the example use the **Get-Credential** cmdlet to create credentials objects for the two users; the credentials for Ken Myer are stored in a variable named $credential1 and the credentials for Pilar Ackerman are stored in a variable named $credential2.

After the credential objects have been created, the final command calls the **Test-CsMcxP2PIM** cmdlet, making sure to specify the target Registrar pool (atl-cs-001.litwareinc,com), the authentication type (Negotiate), and the SIP addresses and credentials of the two users.

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

## Detailed Description

Lync Server Mobility Service extends many of the capabilities of Lync Server to mobile devices such as Apple iPhones, Windows Phone, Android phones, and Nokia phones. Among other things, users can use these phones to exchange instant message and presence information, and to receive notifications of new voice mails. Thanks to the push notification service (Apple Push Notification Service and Microsoft Push Notification Service), users with iPhones or Windows Phones can receive these notifications even if Lync Server is running in the background. The Mobility Service also provides the opportunity for organizations to enable Call via Work. With Call via Work, users can make a call from their mobile phone and make it appear as though the call originated from their work phone; for example, Caller ID systems will display the user's work number instead of his or her mobile phone number.

The **Test-CsMcxP2PIM** cmdlet is used to determine whether or not a pair of users is able to exchange instant messages by using the Mobility Service. Note that running this cmdlet does not require the use of mobile phones nor does it actually send any instant messages. Instead, the cmdlet verifies that the two users are able to log on to Lync Server and that the Mobility Service is able to make the connections required to exchange instant messages between the two users.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Test-CsMcxP2PIM** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsMcxP2PIM"}

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
<td><p><em>Authentication</em></p></td>
<td><p>Required</p></td>
<td><p>SipSyntheticTransaction AuthenticationMechanism</p></td>
<td><p>Allowed values are: TrustedServer; Negotiate; ClientCertificate; and LiveID.</p></td>
</tr>
<tr class="even">
<td><p><em>ReceiverCredential</em></p></td>
<td><p>Required</p></td>
<td><p>PSCredential</p></td>
<td><p>User credentials object for the first of the two user accounts to be tested. The value passed to ReceiverCredential should be an object reference obtained by using the <strong>Get-Credential</strong> cmdlet. For example, this code returns a credentials object for the user litwareinc\pilar and stores that object in a variable named $y:</p>
<p>$y = Get-Credential &quot;litwareinc\pilar&quot;</p>
<p>You need to supply the user password when running this command.</p></td>
</tr>
<tr class="odd">
<td><p><em>ReceiverSipAddress</em></p></td>
<td><p>Required</p></td>
<td><p>String</p></td>
<td><p>SIP address for the first of the two user accounts to be tested. For example:</p>
<p>-ReceiverSipAddress &quot;sip:pilar@litwareinc.com&quot;</p>
<p>The ReceiverSipAddress parameter must reference the same user account as the ReceiverCredential parameter.</p></td>
</tr>
<tr class="even">
<td><p><em>SenderCredential</em></p></td>
<td><p>Required</p></td>
<td><p>PSCredential</p></td>
<td><p>User credentials object for the second of the two user accounts to be tested. The value passed to SenderCredential should be an object reference obtained by using the <strong>Get-Credential</strong> cmdlet. For example, this code returns a credentials object for the user litwareinc\kenmyer and stores that object in a variable named $x:</p>
<p>$x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>You need to supply the user password when running this command.</p></td>
</tr>
<tr class="odd">
<td><p><em>SenderSipAddress</em></p></td>
<td><p>Required</p></td>
<td><p>String</p></td>
<td><p>SIP address for the second of the two user accounts to be tested. For example:</p>
<p>-SenderSipAddress &quot;sip:kenmyer@litwareinc.com&quot;</p>
<p>The SenderSipAddress parameter must reference the same user account as the SenderCredential parameter.</p></td>
</tr>
<tr class="even">
<td><p><em>TargetFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>String</p></td>
<td><p>Fully qualified domain name (FQDN) of the pool to be tested.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
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
<td><p>String</p></td>
<td><p>When present, detailed output from running the cmdlet will be stored in the specified variable. For example, to store output in a variable named $TestOutput use the following syntax:</p>
<p>-OutVerboseVariable TestOutput</p>
<p>Do not use prepend a $ character when specifying the variable name.</p></td>
</tr>
<tr class="even">
<td><p><em>RegistrarPort</em></p></td>
<td><p>Optional</p></td>
<td><p>Int32</p></td>
<td><p>SIP port used by the Registrar service. This parameter is not required if the Registrar uses the default port 5061.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Test-CsMcxP2PIM** cmdlet does not accept pipelined input.

## Return Types

The **Test-CsMcxP2PIM** cmdlet returns an instance of the Microsoft.Rtc.SyntheticTransactions.TaskOutput object.

