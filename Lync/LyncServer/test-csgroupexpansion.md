---
title: Test-CsGroupExpansion
TOCTitle: Test-CsGroupExpansion
ms:assetid: e41db33d-d028-4171-9418-ec04885be2fc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399009(v=OCS.15)
ms:contentKeyID: 49314531
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsGroupExpansion

 

_**上一次修改主题：** 2015-03-09_

Tests the ability of a user to employ group expansion. Lync Server enables users to configure an Active Directory distribution group as a contact. When you "expand" a group you will see the name and presence information for each member of the group. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Test-CsGroupExpansion -TargetFqdn <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-External <SwitchParameter>] [-RegistrarPort <Int32>] [-UserSipAddress <String>] <COMMON PARAMETERS>

    Test-CsGroupExpansion -UserCredential <PSCredential> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-External <SwitchParameter>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] <COMMON PARAMETERS>

    Test-CsGroupExpansion -TargetUri <String> -UserSipAddress <String> [-Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID>] [-WebCredential <PSCredential>] <COMMON PARAMETERS>

    COMMON PARAMETERS: -GroupEmailAddress <String> [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>]

## Examples

## EXAMPLE 1

The command shown in Example 1 connects to the Registrar pool atl-cs-001.litwareinc.com in order to verify group expansion. To run the test, the command uses the group FinanceGroup@litwareinc.com.

    Test-CsGroupExpansion -TargetFqdn atl-cs-001.litwareinc.com -GroupEmailAddress FinanceGroup@litwareinc.com 

## Detailed Description

Users sometimes need to communicate on a regular basis with all the members of an Active Directory distribution group; for example, that group might comprise all the members of a team or all the people assigned to a particular project. In recognition of this, Lync Server allows you to configure a distribution group as a contact. If you do this, you can then send the same instant message to all the group members simply by addressing the message to the group rather than each individual member of that group.

There might also be times when you need to communicate with (or check the presence of) certain individuals in the group. Group expansion enables you to quickly and easily view all the group members and their current status. In addition to that, you can also select one or more group members, and then send an instant message just to those users rather than to all the members of the group.

Group expansion is enabled and disabled by using the **Set-CsWebServiceConfiguration** cmdlet. If group expansion is enabled, you can determine whether the feature is working by running the **Test-CsGroupExpansion** cmdlet. With this cmdlet, you specify an Active Directory distribution group by using the group’s email address. The **Test-CsGroupExpansion** cmdlet then uses group expansion to retrieve the group membership and compare the retrieved list with the membership of the group email address that you supplied. If the two lists match, then group expansion is working correctly.

Note that you can test group expansion in two different ways: by testing the service itself or by testing the associated web service.

Who can run this cmdlet: To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsGroupExpansion"}

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
<td><p><em>GroupEmailAddress</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Email address of the targeted distribution group. For example: -GroupEmailAddress &quot;FinanceGroup@litwareinc.com&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>TargetFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name (FQDN) of the Registrar pool where group expansion is to be tested. For example: -TargetFqdn &quot;atl-cs-001.litwareinc.com&quot;.</p>
<p>Note that you cannot use both the TargetUri parameter and the TargetFqdn parameter in the same command.</p></td>
</tr>
<tr class="odd">
<td><p><em>TargetUri</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Uniform Resource Identifier (URI) of the Group Expansion Web service. For example: -TargetUri &quot;https://atl-cs-001.litwareinc.com/groupexpansion&quot;.</p>
<p>Note that you cannot use both the TargetUri parameter and the TargetFqdn parameter in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>UserCredential</em></p></td>
<td><p>Required</p></td>
<td><p>System.Management.Automation.PSCredential</p></td>
<td><p>User credential object for the user account to be used in the test. The value passed to UserCredential should be an object reference obtained by using the <strong>Get-Credential</strong> cmdlet. For example, this code returns a credentials object for the user litwareinc\kenmyer and stores that object in a variable named $x:</p>
<p>$x = Get-Credential &quot;litwareinc\kenmyer&quot;</p>
<p>You will need to supply the user password when running this command.</p>
<p>The user credential is not required if you are running the test under the credentials of the logged-on user and using the TargetFqdn parameter. The user credential is required if you are using the TargetUri parameter.</p></td>
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
<td><p><em>External</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to verify that external users can use group expansion.</p></td>
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
<p>Note: Do not use prepend a $ character when specifying the variable name.To save the information stored in the logger variable to an HTML file, use a command similar to this:</p>
<p>$TestOutput.ToHTML() &gt; C:\Logs\TestOutput.html</p>
<p>To save the information stored in the logger variable to an XML file, use a command similar to this:</p>
<p></p>
<p>$TestOutput.ToXML() &gt; C:\Logs\TestOutput.xml</p></td>
</tr>
<tr class="odd">
<td><p><em>OutVerboseVariable</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>When present, detailed output from running the cmdlet will be stored in the specified variable. For example, to store output in a variable named $TestOutput use the following syntax:</p>
<p>-OutVerboseVariable TestOutput</p>
<p>Do not prepend a $ character when specifying the variable name.</p></td>
</tr>
<tr class="even">
<td><p><em>RegistrarPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>SIP port used by the Registrar service. This parameter is not required if the Registrar uses the default port 5061.</p></td>
</tr>
<tr class="odd">
<td><p><em>UserSipAddress</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>SIP address of the user to be used in the test. If this parameter is not specified, then the <strong>Test-CsGroupExpansion</strong> cmdlet will conduct its checks using the account of the logged-on user.</p></td>
</tr>
<tr class="even">
<td><p><em>WebCredential</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSCredential</p></td>
<td><p>An object containing user credentials for accessing the Location Information service. This object can be retrieved by calling the <strong>Get-Credential</strong> cmdlet and supplying the appropriate credentials.</p>
<p>This parameter is required if the TargetUri and UserSipAddress parameters are specified, and the computer on which the command is run does not have a server certificate.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Test-CsGroupExpansion** cmdlet does not accept pipelined input.

## Return Types

The **Test-CsGroupExpansion** cmdlet returns an instance of the Microsoft.Rtc.SyntheticTransactions.TaskOutput object.

## 另请参阅

#### 其他资源

[Test-CsAddressBookService](test-csaddressbookservice.md)  
[Test-CsAddressBookWebQuery](test-csaddressbookwebquery.md)

