---
title: Test-CsExUMConnectivity
TOCTitle: Test-CsExUMConnectivity
ms:assetid: 2eb541d2-5f09-483c-adc2-4abb16391ea5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204784(v=OCS.15)
ms:contentKeyID: 49312376
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsExUMConnectivity

 

_**上一次修改主题：** 2015-03-09_

Verifies that a test user can connect to Exchange Unified Messaging. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Test-CsExUMConnectivity -UserCredential <PSCredential> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] <COMMON PARAMETERS>

    Test-CsExUMConnectivity -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-UserSipAddress <String>] <COMMON PARAMETERS>

    Test-CsExUMConnectivity [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>]

## Examples

## Example 1

The preceding example tests Exchange Unified Messaging connectivity for the pool atl-cs-001.litwareinc.com. This command will work only if test users have been defined for the pool atl-cs-001.litwareinc.com. If they have, then the command will determine whether or not the first test user is able to connect to Unified Messaging. If test users have not been configured for the pool then the command will fail.

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com"

## Example 2

The commands shown in Example 2 test Exchange Unified Messaging connectivity for the user litwareinc\\kenmyer. To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell 命令行接口 credentials object for the user litwareinc\\kenmyer. Note that you must supply the password for this account in order to create a valid credentials object and to ensure that the **Test-CsExUMConnectivity** cmdlet can carry out its check.

The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer in order to determine whether or this user can connect to Exchange Unified Messaging.

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

## Example 3

The command shown in Example 3 is a variation of the command shown in Example 2; in this case, however, the OutLoggerVariable parameter is included in order to generate a detailed log of every step undertaken by the **Test-CsExUMConnectivity** cmdlet, as well as the success or failure of each of those steps. To do this, the OutLoggerVariable parameter is added along with the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest. In the final command in the example, the ToXML() method is used to convert the log information to XML format. That XML data is then written to a file named C:\\Logs\\ExumTest.xml by using the Out-File cmdlet.

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest
    
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml

## Detailed Description

The **Test-CsExUMConnectivity** cmdlet verifies that the specified user can connect to the Microsoft Exchange Server 2013 unified messaging service. Note that this cmdlet only verifies that a connection can be made to the service; it does not test the service itself. To test the unified messaging service (by running a synthetic transaction cmdlet that actually leaves a voice mail message in a user's mailbox) use the [Test-CsExUMVoiceMail](test-csexumvoicemail.md) cmdlet.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsExUMConnectivity"}

**Lync Server 控制面板:** The functions carried out by the **Test-CsExUMConnectivity** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>TargetFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>String</p></td>
<td><p>Fully qualified domain name of the pool being tested for Exchange Unified Messaging connectivity.</p></td>
</tr>
<tr class="even">
<td><p><em>UserCredential</em></p></td>
<td><p>Required</p></td>
<td><p>PSCredential</p></td>
<td><p>User credentials object for the user account to be used in the test. The value passed to UserCredential should be an object reference obtained by using the <strong>Get-Credential</strong> cmdlet. For example, this code returns a credentials object for the user litwareinc\kenmyer and stores that object in a variable named $x:</p>
<p>$x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>You need to supply the user password when running this command.</p>
<p>This parameter is not required if you are running the test by using test users configured via the CsHealthMonitoringConfiguration cmdlets.</p></td>
</tr>
<tr class="odd">
<td><p><em>Authentication</em></p></td>
<td><p>Optional</p></td>
<td><p>SipSyntheticTransaction AuthenticationMechanism</p></td>
<td><p>Type of authentication used when running the test. Allowed values are:</p>
<p>* TrustedServer</p>
<p>* Negotiate</p>
<p>* ClientCertificate</p>
<p>* LiveID</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
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
<tr class="even">
<td><p><em>OutVerboseVariable</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>When present, detailed output from running the cmdlet will be stored in the specified variable. For example, to store output in a variable named $TestOutput use the following syntax:</p>
<p>-OutVerboseVariable TestOutput</p>
<p>Do not prepend a $ character when specifying the variable name.</p></td>
</tr>
<tr class="odd">
<td><p><em>RegistrarPort</em></p></td>
<td><p>Optional</p></td>
<td><p>Int32</p></td>
<td><p>SIP port used by the Registrar service. This parameter is not required if the Registrar uses the default port 5061.</p></td>
</tr>
<tr class="even">
<td><p><em>UserSipAddress</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>SIP address of the user to be used in the test. For example:</p>
<p>-UserSipAddress &quot;sip:kenmyer@litwareinc.com&quot;</p>
<p>This parameter is not required if you are running the test by using test users configured via the CsHealthMonitoringConfiguration cmdlets.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Test-CsExUMConnectivity** cmdlet does not accept pipelined input.

## Return Types

The **Test-CsExUMConnectivity** cmdlet returns an instance of the Microsoft.Rtc.SyntheticTransactions.TaskOutput object.

## 另请参阅

#### 其他资源

[Test-CsExUMVoiceMail](test-csexumvoicemail.md)

