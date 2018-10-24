---
title: Test-CsXmppIM
TOCTitle: Test-CsXmppIM
ms:assetid: ffeb05a7-141d-46dc-936f-1f7218521ff8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205423(v=OCS.15)
ms:contentKeyID: 49314868
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsXmppIM

 

_**上一次修改主题：** 2015-03-09_

Verifies whether or not an instant message can be sent across an XMPP gateway. XMPP gateways enable Lync Server 2013 users to exchange instant message and presence information with users belonging to IM and presence providers that employ the extensible Messaging and Presence Protocol (XMPP). 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Test-CsXmppIM -UserCredential <PSCredential> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] <COMMON PARAMETERS>

    Test-CsXmppIM -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-UserSipAddress <String>] <COMMON PARAMETERS>

    Test-CsXmppIM [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] <COMMON PARAMETERS>

    COMMON PARAMETERS: -Receiver <String> [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>]

## Examples

## Example 1

The preceding example verifies the XMPP instant messaging capabilities for the pool atl-cs-001.litwareinc.com. This command will work only if test users have been defined for the pool atl-cs-001.litwareinc.com. If they have, then the command will determine whether or not the first test user is able to send an XMPP instant message to a user with the SIP address adelaney@contoso.com.

If test users have not been defined, then the command will fail because it will not know which user to log on as. If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user that the command should use when trying to log on.

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

## Example 2

The commands shown in Example 2 test the ability of a specific user (litwareinc\\pilar) to log on to send an XMPP instant message to the user adelaney@contoso.com. To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell 命令行接口 credential object containing the name and password of the user Pilar Ackerman. (Because the logon name litwareinc\\pilar has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.

The second command then checks to see if this user can log on to the pool atl-cs-001.litwareinc.com and send the XMPP instant message. To carry out this task, the **Test-CsXmppIm** cmdlet is called, along with four parameters: TargetFqdn (the FQDN of the Registrar pool); Receiver (the SIP address of the user the message is being addressed to); UserCredential (the Windows PowerShell object containing Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address corresponding to the supplied user credentials).

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

## Detailed Description

The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet. XMPP was originally named Jabber, and is supported by a number of Internet messaging and communication applications, including Google Talk and Facebook Chat. The **Test-CsXmppIM** cmdlet verifies that a user can exchange instant messages with a user on an XMPP network. Note that, for this test to succeed, you must have a valid SIP address for the XMPP user, and that SIP address must be on a network that has been configured as an allowed XMPP partner.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsXmppIM"}

**Lync Server 控制面板:** The functions carried out by the **Test-CsXmppIM** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>Receiver</em></p></td>
<td><p>Required</p></td>
<td><p>String</p></td>
<td><p>SIP address of the user who the test message is addressed to.</p></td>
</tr>
<tr class="even">
<td><p><em>TargetFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>String</p></td>
<td><p>Fully qualified domain name of the pool being tested.</p></td>
</tr>
<tr class="odd">
<td><p><em>UserCredential</em></p></td>
<td><p>Required</p></td>
<td><p>PSCredential</p></td>
<td><p>User credential object for the user account to be tested. The value passed to UserCredential should be an object reference obtained by using the <strong>Get-Credential</strong> cmdlet. For example, this code returns a credentials object for the user litwareinc\kenmyer and stores that object in a variable named $x:$x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>You need to supply the user password when running this command.</p>
<p>This parameter is not required if you are conducting the test using the health monitoring configuration settings.</p></td>
</tr>
<tr class="even">
<td><p><em>Authentication</em></p></td>
<td><p>Optional</p></td>
<td><p>SipSyntheticTransaction AuthenticationMechanism</p></td>
<td><p>User credential object for the account to be tested. The value passed to UserCredential must be an object reference obtained by using the <strong>Get-Credential</strong> cmdlet. For example, this code returns a credential object for the user litwareinc\kenmyer and stores that object in a variable named</p>
<p>$x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>You need to supply the user password when running this command. This parameter is not required if you are conducting the test under the health monitoring configuration settings for the pool.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
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
<td><p>When present, detailed output from running the cmdlet will be stored in the specified variable. For example, to store output in a variable named $TestOutput use the following syntax:</p>
<p>-OutVerboseVariable TestOutput</p>
<p>Do not prepend a $ character when specifying the variable name.</p></td>
</tr>
<tr class="even">
<td><p><em>RegistrarPort</em></p></td>
<td><p>Optional</p></td>
<td><p>Int32</p></td>
<td><p>SIP port used by the Registrar service. This parameter is not required if the Registrar uses the default port 5061</p></td>
</tr>
<tr class="odd">
<td><p><em>UserSipAddress</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>SIP address for user account to be tested; for example:</p>
<p>-UserSipAddress &quot;sip:kenmyer@litwareinc.com&quot;</p>
<p>The UserSipAddress parameter must reference the same user account as UserCredential. This parameter is not required if you are conducting the test under the health monitoring configuration settings for the pool.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Test-CsXmppIM** cmdlet does not accept pipelined input.

## Return Types

The **Test-CsXmppIM** cmdlet returns instances of the Microsoft.Rtc.SyntheticTransactions.TaskOutput object.

## 另请参阅

#### 其他资源

[Set-CsXmppGatewayConfiguration](set-csxmppgatewayconfiguration.md)

