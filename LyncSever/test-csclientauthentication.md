---
title: Test-CsClientAuthentication
TOCTitle: Test-CsClientAuthentication
ms:assetid: 6a25b2c6-0cb2-473c-af92-0be5cead8a19
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ619181(v=OCS.15)
ms:contentKeyID: 49313125
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsClientAuthentication

 

_**上一次修改主题：** 2015-03-09_

Determines whether or not a user can log on to Lync Server by using a certificate downloaded from the certificate provisioning service. 此 cmdlet 是在 Lync Server 2013 中引入的。 It replaces the **Test-CSClientAuth** cmdlet used in Lync Server 2010.

## 语法

    Test-CsClientAuthentication -UserCredential <PSCredential> -UserSipAddress <String> [-Force <SwitchParameter>] [-LiveIdAuthentication <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] [-TargetUri <String>]

## Examples

## EXAMPLE 1

The commands shown in Example 1 test the ability of the user litwareinc\\kenmyer to log on to the Registrar pool atl-cs-001.litwareinc.com by using a client certificate. To carry out this task, the first command in the example uses the **Get-Credential** cmdlet to create credential object for the user in question. The resulting credential object (which requires you to enter the password for the user) is stored in a variable named $cred1.

The second command then calls the **Test-CsClientAuthentication** cmdlet, specifying the FQDN of the Registrar pool (TargetFqdn), the user’s SIP address (UserSipAddress) and the credential object created in the initial command (UserCredential).

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsClientAuthentication -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

## Detailed Description

Client certificates provide an alternate way for users to be authenticated by Lync Server. In order to determine whether or not a user can log on to the system by using a client certificate, you can run the **Test-CsClientAuthentication** cmdlet. When you run the **Test-CsClientAuthentication** cmdlet you must specify the Registrar pool and SIP address of the user account being tested; you must also be able to supply the user’s logon name and password. After calling the **Test-CsClientAuthentication** cmdlet, the cmdlet will contact the certificate provisioning service and download a copy of any client certificates for the specified user. If a client certificate can be found and downloaded, the **Test-CsClientAuthentication** cmdlet will then attempt to log on using that certificate. If logon succeeds, the **Test-CsClientAuthentication** cmdlet will log off and report that the test succeeded.

If a certificate cannot be found or downloaded, or if the cmdlet is unable to logon using that certificate, then the **Test-CsClientAuthentication** cmdlet will report that the test failed.

Who can run this cmdlet: To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsClientAuthentication"}

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
<td><p><em>UserCredential</em></p></td>
<td><p>Required</p></td>
<td><p>System.Management.Automation.PSCredential</p></td>
<td><p>User credential object for the user account to be used in the test. The value passed to UserCredential should be an object reference obtained by using the <strong>Get-Credential</strong> cmdlet. For example, this code returns a credentials object for the user litwareinc\kenmyer and stores that object in a variable named $x:</p>
<p>$x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>You need to supply the user password when running this command.</p></td>
</tr>
<tr class="even">
<td><p><em>UserSipAddress</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>SIP address of the user to be used in the test. For example: -UserSipAddress sip:kenmyer@litwareinc.com.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>LiveIdAuthentication</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Verifies the ability of the test user to log on using their OrgId (Business LiveId) credentials.</p></td>
</tr>
<tr class="odd">
<td><p><em>OutLoggerVariable</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>When present, detailed output from running the cmdlet will be stored in the specified variable. This variable includes a pair of methods – ToHTML and ToXML – that can then be used to save that output to either an HTML or an XML file.</p>
<p>To store output in a logger variable named $TestOutput use the following syntax:</p>
<p>-OutLoggerVariable TestOutput</p>
<p>Note: Do not use prepend a $ character when specifying the variable name.To save the information stored in the logger variable to an HTML file, use a command similar to this:</p>
<p>$TestOutput.ToHTML() &gt; C:\Logs\TestOutput.html</p>
<p>To save the information stored in the logger variable to an XML file, use a command similar to this:</p>
<p></p>
<p>$TestOutput.ToXML() &gt; C:\Logs\TestOutput.xml</p></td>
</tr>
<tr class="even">
<td><p><em>OutVerboseVariable</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>When present, detailed output from running the cmdlet will be stored in the specified variable. For example, to store output in a variable named $TestOutput use the following syntax:</p>
<p>-OutVerboseVariable TestOutput</p>
<p>Do not prepend a $ character when specifying the variable name.</p></td>
</tr>
<tr class="odd">
<td><p><em>RegistrarPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>SIP port used by the Registrar service. This parameter is not required if the Registrar uses the default port 5061.</p></td>
</tr>
<tr class="even">
<td><p><em>TargetFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name (FQDN) of the Registrar pool where client authentication is to be tested. For example: -TargetFqdn &quot;atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>TargetUri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL of the certificate provisioning service. If this parameter is not included then the <strong>Test-CsClientAuthentication</strong> cmdlet will use the certificate provisioning service configured for the Registrar pool.</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

The **Test-CsClientAuthentication** cmdlet returns an instance of the Microsoft.Rtc.SyntheticTransactions.TaskOutput object.

## 另请参阅

#### 其他资源

[Get-CsWebServiceConfiguration](get-cswebserviceconfiguration.md)  
[Test-CsRegistration](test-csregistration.md)

