---
title: Test-CsPhoneBootstrap
TOCTitle: Test-CsPhoneBootstrap
ms:assetid: b132446b-f264-405e-8e3a-971ab1c37694
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412852(v=OCS.15)
ms:contentKeyID: 49313951
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsPhoneBootstrap

 

_**上一次修改主题：** 2015-03-09_

Verifies that a user can log on to Lync Server using a Lync Phone Edition-compatible device. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Test-CsPhoneBootstrap -PhoneOrExt <String> -PIN <String> [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>] [-RegistrarPort <Int32>] [-TargetFqdn <String>] [-TargetUri <String>] [-UserSipAddress <String>]

## Examples

## EXAMPLE 1

The command shown in Example 1 verifies that the user with the specified phone number and PIN can connect to Lync Server using a Lync Phone Edition-compatible device. In order to run the test, the user’s phone number (+14255551219) and the user’s PIN (0712) must be supplied.

    Test-CsPhoneBootstrap -PhoneOrExt "+14255551219" -Pin "0712"

## EXAMPLE 2

Example 2 verifies whether or not the user with the specified phone number and PIN can connect to Lync Server using a Lync Phone Edition-compatible device. In this example, the UserSipAddress parameter is included as an additional check: the test will fail if the user with the SIP address is not the same as the user with the specified phone number and PIN.

    Test-CsPhoneBootstrap -PhoneOrExt "+14255551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

## Detailed Description

In order to connect to Lync Server, Lync Phone Edition-compatible devices need to use Dynamic Host Configuration Protocol (DHCP) to retrieve the address of a Lync Server Registrar; these devices must also provide a valid phone number and associated personal identification number (PIN) in order to be authenticated by the system. (This process is known as "bootstrapping".) The **Test-CsPhoneBootstrap** cmdlet enables administrators to verify that a given user -- using the phone number and PIN assigned to him or her -- is able to log on to the system from a Lync Phone Edition-compatible device. (No device is actually needed in order to run the test.)

In order for the **Test-CsPhoneBootstrap** cmdlet to make its check, the Registrar pool that hosts the user account being tested must be discoverable using DHCP. To determine whether a Registrar is discoverable in this manner, use the [Get-CsRegistrarConfiguration](get-csregistrarconfiguration.md) cmdlet and check the value of the EnableDHCPServer property. If this property is set to False, you will need to use the [Set-CsRegistrarConfiguration](set-csregistrarconfiguration.md) cmdlet to set the property value to True and make the Registrar discoverable using DHCP. This can also be done by using Enterprise DHCP Server and configuring the Lync Server-specific options.

Who can run this cmdlet: To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsPhoneBootstrap"}

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
<td><p><em>PhoneOrExt</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Telephone number or extension of the user account being tested. For example: -PhoneOrExt &quot;+14255551219&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>PIN</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>PIN of the user account being tested.</p></td>
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
<td><p><em>TargetFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name (FQDN) of the Registrar pool that hosts the user account to be tested. If not specified, then DHCP discovery will be used to locate the Registrar pool.</p></td>
</tr>
<tr class="even">
<td><p><em>TargetUri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL of the certificate provisioning service. If this parameter is not included, then the DHCP discovery will be used to locate the target URI.</p></td>
</tr>
<tr class="odd">
<td><p><em>UserSipAddress</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>SIP address for the user account used in the text; for example: -UserSipAddress &quot;sip:kenmyer@litwareinc.com&quot;. The UserSipAddress parameter must reference the supplied phone number and PIN; the test will fail if the included phone number and PIN do not belong to the user specified by the UserSipAddress parameter. Note that the SIP address must include the &quot;sip:&quot; prefix.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Test-CsPhoneBootstrap** cmdlet does not accept pipelined input.

## Return Types

The **Test-CsPhoneBootstrap** cmdlet returns an instance of the Microsoft.Rtc.SyntheticTransactions.TaskOutput object.

## 另请参阅

#### 其他资源

[Test-CsRegistration](test-csregistration.md)

