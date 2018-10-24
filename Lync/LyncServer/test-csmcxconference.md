---
title: Test-CsMcxConference
TOCTitle: Test-CsMcxConference
ms:assetid: c6ca9019-1535-489d-a42e-1a50070b2f67
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690045(v=OCS.15)
ms:contentKeyID: 49314210
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsMcxConference

 

_**上一次修改主题：** 2015-03-09_

Tests the ability of three users to participate in a Lync Server 2013 Mobility Service conference. The Mobility Service enables users of mobile phones such as iPhones and Windows Phones to do such things as exchange instant messages and presence information; store and retrieve voice mail internally instead of with their wireless provider; and take advantage of Lync Server capabilities such as Call via Work and dial-out conferencing. 此 cmdlet 是在 2011 年 11 月版的 Lync Server 2010 累积更新中引入的。

## 语法

    Test-CsMcxConference -OrganizerCredential <PSCredential> -OrganizerSipAddress <String> -User2Credential <PSCredential> -User2SipAddress <String> -UserCredential <PSCredential> -UserSipAddress <String> <COMMON PARAMETERS>

    Test-CsMcxConference -OrganizerSipAddress <String> -User2SipAddress <String> -UserSipAddress <String> <COMMON PARAMETERS>

    COMMON PARAMETERS: -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -TargetFqdn <String> [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>] [-RegistrarPort <Int32>]

## Examples

## EXAMPLE 1

The commands shown in Example 1 verify whether a Mobility Service conference can be conducted using three user accounts: Ken Myer (the meeting organizer), Pilar Ackerman, and Aidan Delaney. In order to run this test, the first thing that must be done is to create credentials objects for each user account. Those objects are created in the first three lines of code, and stored in the variables $organizerCred (Ken Myer), $user1Cred (Pilar Ackerman), and $user2Cred (Aidan Delaney).

After the credentials objects have been created, you can then call the **Test-CsMcxConference** cmdlet, making sure to specify the target Registrar pool (atl-cs-001.litwareinc,com), the authentication type (Negotiate), and the SIP addresses and credentials of the three user accounts acting as conference participants.

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

## Detailed Description

The Mobility Service extends many of the capabilities of Lync Server to mobile devices such as Apple iPhones, Windows Phone, Android phones, and Nokia phones. Among other things, users can use these phones to exchange instant message and presence information, and to receive notifications of new voice mails. Thanks to the push notification service (Apple Push Notification Service and Microsoft Push Notification Service, users who have iPhones or Windows Phones can receive these notifications even if Lync is running in the background. The Mobility Service also provides the opportunity for organizations to enable Call via Work. With Call via Work, users can make a call from their mobile phone and make it appear as though the call originated from their work phone; for example, Caller ID systems will see the user's work number instead of his or her mobile phone number.

The **Test-CsMcxConference** cmdlet is used to determine whether or not a set of three users are able to participate in a conference by using the Mobility Service. Note that running this cmdlet does not require the use of mobile phones nor does it actually create a real conference. Instead, the cmdlet verifies that the three users are able to log on to Lync Server and that the Mobility Service is able to make the connections required to conduct and conference. The cmdlet also verifies that the conference organizer is able to send an instant message to the other two conference participants.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Test-CsMcxConference** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsMcxConference"}

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
<td><p><em>OrganizerCredential</em></p></td>
<td><p>Required</p></td>
<td><p>PSCredential</p></td>
<td><p>User credential object for the user account acting as the meeting organizer. The value passed to OrganizerCredential should be an object reference obtained by using the <strong>Get-Credential</strong> cmdlet. For example, this code returns a credentials object for the user litwareinc\adelaney and stores that object in a variable named $z:</p>
<p>$z = Get-Credential &quot;litwareinc\adelaney&quot;</p>
<p>You need to supply the user password when running this command.</p></td>
</tr>
<tr class="odd">
<td><p><em>OrganizerSipAddress</em></p></td>
<td><p>Required</p></td>
<td><p>String</p></td>
<td><p>SIP address for the user account acting as the meeting organizer. For example:</p>
<p>-OrganizerSipAddress &quot;sip:adelaney@litwareinc.com&quot;</p>
<p>The OrganizerSipAddress parameter must reference the same user account as the OrganizerCredential parameter.</p></td>
</tr>
<tr class="even">
<td><p><em>TargetFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>String</p></td>
<td><p>Fully qualified domain name (FQDN) of the pool to be tested.</p></td>
</tr>
<tr class="odd">
<td><p><em>User2Credential</em></p></td>
<td><p>Required</p></td>
<td><p>PSCredential</p></td>
<td><p>User credential object for the second of the two user accounts to be tested. The value passed to Use2rCredential should be an object reference obtained by using the <strong>Get-Credential</strong> cmdlet. For example, this code returns a credentials object for the user litwareinc\kenmyer and stores that object in a variable named $y:</p>
<p>$y = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>You need to supply the user password when running this command.</p></td>
</tr>
<tr class="even">
<td><p><em>User2SipAddress</em></p></td>
<td><p>Required</p></td>
<td><p>String</p></td>
<td><p>SIP address for the second of the two user accounts to be tested. For example:</p>
<p>-User2SipAddress &quot;sip:pilar@litwareinc.com&quot;</p>
<p>The User2SipAddress parameter must reference the same user account as the User2Credential parameter.</p></td>
</tr>
<tr class="odd">
<td><p><em>UserCredential</em></p></td>
<td><p>Required</p></td>
<td><p>PSCredential</p></td>
<td><p>User credentials object for the first of the two user accounts to be tested. The value passed to UserCredential should be an object reference obtained by using the <strong>Get-Credential</strong> cmdlet. For example, this code returns a credentials object for the user litwareinc\pilar and stores that object in a variable named $x:</p>
<p>$x = Get-Credential &quot;litwareinc\pilar&quot;</p>
<p>You need to supply the user password when running this command.</p></td>
</tr>
<tr class="even">
<td><p><em>UserSipAddress</em></p></td>
<td><p>Required</p></td>
<td><p>String</p></td>
<td><p>SIP address for the first of the two user accounts to be tested. For example:</p>
<p>-UserSipAddress &quot;sip:kenmyer@litwareinc.com&quot;</p>
<p>The UserSipAddress parameter must reference the same user account as the UserCredential parameter.</p></td>
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
<td><p>String</p></td>
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
<td><p>When present, detailed output from running the cmdlet will be stored in the specified variable. For example, to store output in a variable named $TestOutput use the following syntax</p>
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

None. The **Test-CsMcxConference** cmdlet does not accept pipelined input.

## Return Types

The **Test-CsMcxConference** cmdlet returns an instance of the Microsoft.Rtc.SyntheticTransactions.TaskOutput object.

