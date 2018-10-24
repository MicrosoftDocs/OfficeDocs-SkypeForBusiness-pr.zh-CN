---
title: Test-CsAVEdgeConnectivity
TOCTitle: Test-CsAVEdgeConnectivity
ms:assetid: 9f3b2c70-9239-4085-a108-43e0b7a308b5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205138(v=OCS.15)
ms:contentKeyID: 49313764
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsAVEdgeConnectivity

 

_**上一次修改主题：** 2015-03-09_

Verifies connectivity through the A/V Edge server. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Test-CsAVEdgeConnectivity -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-UserSipAddress <String>] <COMMON PARAMETERS>

    Test-CsAVEdgeConnectivity -UserCredential <PSCredential> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] <COMMON PARAMETERS>

    Test-CsAVEdgeConnectivity [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>]

## Examples

## Example 1

The command shown in Example 1 verifies that a preconfigured test user can connect to the A/V Edge server configured for the pool atl-cs-001.litwareinc.com Note that this command will fail if you have not defined at least one health monitoring test user for atl-cs-001.litwareinc.com.

    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com"

## Example 2

In Example 2, the **Test-CsAVEdgeConnectivity** cmdlet verifies that the user with the SIP address sip:kenmyer@litwareinc.com is able to connect to the AV Edge server. To do this, the first command in the example uses the Get-Credential cmdlet to retrieve a Windows PowerShell credentials object for the user litwareinc\\kenmyer; note that you supply the password for this account when obtaining this object. After the credentials object has been obtained, the second command uses the **Test-CsAVEdgeConnectivity** cmdlet to verify that the user can connect to the AV Edge server.

    $cred = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred

## Detailed Description

The **Test-CsAVEdgeConnectivity** cmdlet verifies that a user can connect to the AV Edge Server assigned to a Registrar pool.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsAVEdgeConnectivity"}

**Lync Server 控制面板:** The functions carried out by the **Test-CsAVEdgeConnectivity** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>System.String</p></td>
<td><p>Fully qualified domain name (FQDN) of the pool to be tested.</p></td>
</tr>
<tr class="even">
<td><p><em>UserCredential</em></p></td>
<td><p>Required</p></td>
<td><p>System.Management.Automation.PSCredential</p></td>
<td><p>User credentials object for the account to be tested. The value passed to UserCredential must be an object reference obtained by using the <strong>Get-Credential</strong> cmdlet. For example, this code returns a credential object for the user litwareinc\kenmyer and stores that object in a variable named</p>
<p>$x: $x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>You need to supply the user password when running this command. This parameter is not required if you are conducting the test under the health monitoring configuration settings for the pool.</p></td>
</tr>
<tr class="odd">
<td><p><em>Authentication</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction+AuthenticationMechanism</p></td>
<td><p>Type of authentication used in the test. Allowed values are:</p>
<p>* TrustedServer</p>
<p>* Negotiate</p>
<p>* ClientCertificate</p>
<p>* LiveID</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
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
<p>Do not use prepend a $ character when specifying the variable name.</p></td>
</tr>
<tr class="odd">
<td><p><em>RegistrarPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>SIP port used by the Registrar service. This parameter is not required if the Registrar uses the default port 5061.</p></td>
</tr>
<tr class="even">
<td><p><em>UserSipAddress</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>SIP address for user account to be tested; for example: -UserSipAddress &quot;sip:kenmyer@litwareinc.com&quot;. The UserSipAddress parameter must reference the same user account as UserCredential. This parameter is not required if you are conducting the test under the health monitoring configuration settings for the pool.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Test-CsAVEdgeConnectivity** cmdlet does not accept pipelined input.

## Return Types

The **Test-CsAVEdgeConnectivity** cmdlet returns instances of the Microsoft.Rtc.SyntheticTransactions.TaskOutput object.

## 另请参阅

#### 其他资源

[Get-CsAVEdgeConfiguration](get-csavedgeconfiguration.md)

