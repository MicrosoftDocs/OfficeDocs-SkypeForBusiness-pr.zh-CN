---
title: Test-CsWebAppAnonymous
TOCTitle: Test-CsWebAppAnonymous
ms:assetid: acfb28c1-8db6-4d2b-95ad-5c824660ea71
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690041(v=OCS.15)
ms:contentKeyID: 49313905
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsWebAppAnonymous

 

_**上一次修改主题：** 2015-03-09_

Verifies that anonymous users can use the Lync Web App to join a Lync Server conference. 此 cmdlet 是在 Lync Server 2010 中引入的。

This cmdlet has been deprecated for use with the on-premises version of Lync Server 2013. Instead, administrators should use the [Test-CsUcwaConference](test-csucwaconference.md) cmdlet to perform these tests.

## 语法

    Test-CsWebAppAnonymous -UserCredential <PSCredential> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-External <SwitchParameter>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] <COMMON PARAMETERS>

    Test-CsWebAppAnonymous -TargetUri <String> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-WebCredential <PSCredential>] <COMMON PARAMETERS>

    Test-CsWebAppAnonymous -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-External <SwitchParameter>] [-RegistrarPort <Int32>] [-UserSipAddress <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>]

## Examples

## EXAMPLE 1

The command shown in Example 1 verifies whether or not a test user configured for the pool atl-cs-001.litwareinc.com can use Lync Web App to anonymously join a conference. This command will only succeed if you have configured a test user for the pool by using the **CsHealthMonitoringConfiguration** cmdlets.

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

## EXAMPLE 2

The commands shown in Example 2 verify whether or not the user Ken Myer can use Lync Web App to anonymously join a conference. To use an actual user account, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell credentials object for the user litwareinc\\kenmyer. That credentials object (stored in a variable named $cred1) is then passed to the UserCredential parameter in the second command in the example. In addition to the UserCredential parameter, the UserSipAddress parameter is also included, along with Ken Myer’s SIP address.

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 

## Detailed Description

The **Test-CsWebAppAnonymous** cmdlet enables administrators to verify that anonymous users can employ Microsoft Exchange Server 2013 in order to join conferences. When you run the **Test-CsWebAppAnonymous** cmdlet, the cmdlet attempts to obtain an anonymous web ticket by using the Web Ticket service. If the ticket can be obtained, the **Test-CsWebAppAnonymous** cmdlet will then try to connect to by Lync Server using Lync Web App. If the connection is made, the cmdlet will then attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.

Many administrators will use the **CsHealthMonitoringConfiguration** cmdlets to set up test users for each of their Registrar pools. These test users represent a pair of user accounts that have been preconfigured for use with synthetic transactions. (Typically these are test accounts and not accounts that belong to actual users.) If test users are configured for a pool, administrators can run the **Test-CsWebAppAnonymous** cmdlet against that pool without having to specify the identity of (and supply the credentials for) the user account involved in the test.

Alternatively, administrators can run the **Test-CsWebAppAnonymous** cmdlet using an actual user account. If you decide to conduct the test using an actual user account you will need to supply the logon name and password for that account.

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
<td><p>Fully qualified domain name (FQDN) of the pool to be tested. For example:</p>
<p>-TargetFqdn atl-cs-001.litwareinc.com</p></td>
</tr>
<tr class="even">
<td><p><em>TargetUri</em></p></td>
<td><p>Required</p></td>
<td><p>String</p></td>
<td><p>Uniform Resource Identifier (URI) of the Reach server. For example:</p>
<p>-TargetUri &quot;https://atl-cs-001.litwareinc.com/reach&quot;</p>
<p>You cannot use both the TargetUri parameter and the TargetFqdn parameter in the same command.</p></td>
</tr>
<tr class="odd">
<td><p><em>UserCredential</em></p></td>
<td><p>Required</p></td>
<td><p>PSCredential</p></td>
<td><p>User credentials object for the first of the two user accounts to be tested. The value passed to UserCredential should be an object reference obtained by using the <strong>Get-Credential</strong> cmdlet. For example, this code returns a credentials object for the user litwareinc\pilar and stores that object in a variable named $x:</p>
<p>$x = Get-Credential &quot;litwareinc\pilar&quot;</p>
<p>You need to supply the user password when running this command.</p>
<p>This parameter is not required if you are running the test by using test users configured via the <strong>CsHealthMonitoringConfiguration</strong> cmdlets.</p></td>
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
<td><p><em>External</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>When present, causes the <strong>Test-CsWebAppAnonymous</strong> cmdlet to test the Reach server’s external web relay. If this parameter is not present, the cmdlet will test the internal web relay. The web relay serves as an intermediary between the internal network and the Internet.</p></td>
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
<td><p>When present, detailed output from running the cmdlet will be stored in the specified variable. For example, to store output in a variable named $TestOutput use the following syntax</p>
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
<td><p>SIP address for the first of the two user accounts to be tested. For example:</p>
<p>-UserSipAddress &quot;sip:kenmyer@litwareinc.com&quot;</p>
<p>This parameter is not required if you are running the test by using test users configured via the CsHealthMonitoringConfiguration cmdlets.</p></td>
</tr>
<tr class="odd">
<td><p><em>WebCredential</em></p></td>
<td><p>Optional</p></td>
<td><p>PSCredential</p></td>
<td><p>User credential object for the user account to be used in the test. The value passed to UserCredential should be an object reference obtained by using the <strong>Get-Credential</strong> cmdlet. For example, this code returns a credentials object for the user litwareinc\kenmyer and stores that object in a variable named $x:</p>
<p>$x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>This parameter is required if either the TargetUri parameter or the UserSipAddress parameters are specified and the computer on which the command is run does not have a server certificate.</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

The **Test-CsWebAppAnonymous** cmdlet returns an instance of the Microsoft.Rtc.SyntheticTransactions.TaskOutput object.

