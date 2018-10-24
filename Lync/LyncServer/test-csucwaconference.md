---
title: Test-CsUcwaConference
TOCTitle: Test-CsUcwaConference
ms:assetid: 4e01c4d6-7b81-4932-a8e1-4d14989b71bd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ619178(v=OCS.15)
ms:contentKeyID: 49312802
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsUcwaConference

 

_**上一次修改主题：** 2015-03-09_

Tests the ability of a pair of users to schedule, join, and then conduct an online conference using the Unified Communications Web API (UCWA). 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Test-CsUcwaConference -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-OrganizerSipAddress <String>] [-ParticipantSipAddress <String>] [-RegistrarPort <Int32>] <COMMON PARAMETERS>

    Test-CsUcwaConference -OrganizerCredential <PSCredential> -OrganizerSipAddress <String> -ParticipantCredential <PSCredential> -ParticipantSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] <COMMON PARAMETERS>

    Test-CsUcwaConference [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>] [-ParticipantSipAddress <String>]

## Examples

## Example 1

The command shown in Example 1 verifies that a pair of test users can participate in an UCWA conference on the pool atl-cs-001.litwareinc.com. Note that this command will fail if you have not predefined a pair of health monitoring configuration test users for atl-cs-001.litwareinc.com.

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

## Example 2

The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to participate in an UCWA conference. To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell 命令行接口 credential object containing the name and password of the user Pilar Ackerman. (Because the logon name, litwareinc\\pilar, has been included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1. The second command does the same thing, this time returning a credential object for the Ken Myer account.

With the two credential objects in hand, the third command in the example determines whether or not the two users can participate in an UCWA conference. To carry out this task, the **Test-CsUcwaConference** cmdlet is called, along with the following parameters: TargetFqdn (the FQDN of the Registrar pool); OrganizerSipAddress (the SIP address for the meeting organizer); OrganizerCredential (the Windows PowerShell object containing the credentials for this same user); ParticipantSipAddress (the SIP address for the other test user); and ParticipantCredential (the Windows PowerShell 命令行接口 object containing the credentials for the other user).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

## Detailed Description

The **Test-CsUcwaConference** cmdlet verifies that a pair of test users can schedule, join, and then conduct an online conference using the Unified Communications Web API (UCWA). To do this, the cmdlet uses the Lync Server web ticket service to authenticate the two test users and register them with Lync Server. The cmdlet then starts a conference using the organizer credentials and invites the participant to join the meeting. After the meeting has been joined, the **Test-CsUcwaConference** cmdlet verifies that the users can do such things as exchange instant message and conduct pools, then terminates the conference and unregisters the two test users. The scheduled conference will also be deleted when the test is finished.

The **Test-CsUcwaConference** cmdlet can also be used to determine whether or not anonymous users can join online conferences.

Note that the **Test-CsUcwaConference** cmdlet should not be run against a Microsoft Lync Server 2010 pool unless UCWA has been installed on that pool. If UCWA has not been installed then the call to the **Test-CsUcwaConference** cmdlet will fail.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsUcwaConference"}

**Lync Server 控制面板:** The functions carried out by the **Test-CsUcwaConference** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>OrganizerCredential</em></p></td>
<td><p>Required</p></td>
<td><p>PSCredential</p></td>
<td><p>User credential object for user account acting as the meeting organizer. The value passed to OrganizerCredential should be an object reference obtained by using the <strong>Get-Credential</strong> cmdlet. For example, this code returns a credentials object for the user litwareinc\kenmyer and stores that object in a variable named $x:</p>
<p>$x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>You need to supply the user password when running this command.</p>
<p>The organizer credential is not required if you are running the test under the health monitoring configuration settings for the pool.</p></td>
</tr>
<tr class="even">
<td><p><em>ParticipantCredential</em></p></td>
<td><p>Required</p></td>
<td><p>PSCredential</p></td>
<td><p>User credential object for the user account acting as the meeting participant. The value passed to ParticipantCredential should be an object reference obtained by using the <strong>Get-Credential</strong> cmdlet. For example, this code returns a credentials object for the user litwareinc\pilar and stores that object in a variable named $y:</p>
<p>$y = Get-Credential &quot;litwareinc\pilar&quot;</p>
<p>You need to supply the user password when running this command.</p>
<p>The participant credential is not required if you are running the test under the health monitoring configuration settings for the pool.</p></td>
</tr>
<tr class="odd">
<td><p><em>TargetFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>String</p></td>
<td><p>Fully qualified domain name (FQDN) of the pool to be tested.</p></td>
</tr>
<tr class="even">
<td><p><em>Authentication</em></p></td>
<td><p>Optional</p></td>
<td><p>SipSyntheticTransaction AuthenticationMechanism</p></td>
<td><p>Type of authentication used when running the test. Allowed values are:</p>
<p>* TrustedServer</p>
<p>* Negotiate</p>
<p>* ClientCertificate</p>
<p>* LiveID</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>OrganizerSipAddress</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>SIP address for the meeting organizer. For example: -OrganizerSipAddress &quot;sip:pilar@litwareinc.com&quot;. The OrganizerSIPAddress parameter must reference the same user account as OrganizerCredential.</p>
<p>The SIP address is not required if you are running the test under the health monitoring configuration settings for the pool.</p></td>
</tr>
<tr class="odd">
<td><p><em>OutLoggerVariable</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>When present, detailed output from running the cmdlet will be stored in the specified variable. This variable includes a pair of methods – ToHTML and ToXML – that can then be used to save that output to either an HTML or an XML file.</p>
<p>To store output in a logger variable named $TestOutput use the following syntax:</p>
<p>-OutLoggerVariable TestOutput</p>
<p>Note: Do not prepend a $ character when specifying the variable name.</p>
<p>To save the information stored in the logger variable to an HTML file, use a command similar to this:</p>
<p>$TestOutput.ToHTML() &gt; C:\Logs\TestOutput.html</p>
<p>To save the information stored in the logger variable to an XML file, use a command similar to this:</p>
<p>$TestOutput.ToXML() &gt; C:\Logs\TestOutput.xml</p></td>
</tr>
<tr class="even">
<td><p><em>OutVerboseVariable</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>When present, detailed output from running the cmdlet will be stored in the specified variable. For example, to store output in a variable named $TestOutput use the following syntax:</p>
<p>-OutVerboseVariable TestOutput</p>
<p>Do not prepend a $ character when specifying the variable name.</p></td>
</tr>
<tr class="odd">
<td><p><em>ParticipantSipAddress</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>SIP address for the meeting participant. For example: -ParticipantSipAddress &quot;sip:kenmyer@litwareinc.com&quot;. The ParticipantSIPAddress parameter must reference the same user account as ParticipantCredential.</p>
<p>The SIP address is not required if you are running the test under the health monitoring configuration settings for the pool.</p></td>
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

None. The **Test-CsUcwaConference** cmdlet does not accept pipelined input.

## Return Types

The **Test-CsUcwaConference** cmdlet returns instances of the Microsoft.Rtc.SyntheticTransactions.WebTaskOutput object.

## 另请参阅

#### 其他资源

[Test-CsASConference](test-csasconference.md)  
[Test-CsDataConference](test-csdataconference.md)  
[Test-CsAVConference](test-csavconference.md)

