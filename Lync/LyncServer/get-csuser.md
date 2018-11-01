﻿---
title: Get-CsUser
TOCTitle: Get-CsUser
ms:assetid: 06f36c53-3a5e-4e79-b4f2-8c1aa7e6bf71
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398125(v=OCS.15)
ms:contentKeyID: 49311893
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsUser

 

_**上一次修改主题：** 2015-03-09_

Returns information about all the users in your organization who have been enabled for Lync Server or a previous version of the software (such as Microsoft Office Communications Server 2007 R2). 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsUser [-Identity <UserIdParameter>] [-Credential <PSCredential>] [-DomainController <Fqdn>] [-Filter <String>] [-LdapFilter <String>] [-OnLyncServer <SwitchParameter>] [-OnOfficeCommunicationServer <SwitchParameter>] [-OU <OUIdParameter>] [-ResultSize <Unlimited>] [-UnassignedUser <SwitchParameter>]

## Examples

## EXAMPLE 1

In the preceding example, the **Get-CsUser** cmdlet is called without any parameters in order to return a collection of all the domain users who have been enabled for Lync Server or Office Communications Server.

    Get-CsUser

## EXAMPLE 2

In Example 2, the **Get-CsUser** cmdlet returns a collection of all the domain users who have been enabled for Lync Server or Office Communications Server. By default, the **Get-CsUser** cmdlet returns a very large number of properties and property values, many of which will be of minimal interest in a given situation. Therefore, in this example the retrieved data is piped to the **Format-Table** cmdlet. The **Format-Table** cmdlet then uses the Property parameter to select the properties DisplayName, SipAddress, and EnterpriseVoiceEnabled, and display those properties and their values in a table.

    Get-CsUser | Format-Table -Property DisplayName, SipAddress, EnterpriseVoiceEnabled -AutoSize

## EXAMPLE 3

In Example 3, the Identity parameter is used to limit the returned data to the user account with the Identity (in this case, the display name) Pilar Ackerman.

    Get-CsUser -Identity "Pilar Ackerman"

## EXAMPLE 4

In Example 4, the wildcard character (\*) is used when specifying the user's Identity. That causes the **Get-CsUser** cmdlet to return all the users who have an Identity that begins with the string value "Pilar".

    Get-CsUser -Identity "Pilar*"

## EXAMPLE 5

The command shown in Example 5 returns a collection of users who do not have a per-user voice policy assigned to them. To do this, the command uses the Filter parameter followed by the filter VoicePolicy -eq "$Null. When constructing filters for use with the **Get-CsUser** cmdlet, you need to specify the property name (VoicePolicy) followed by the comparison operator (in this case, "eq", the comparison operator that means " equal to"). Immediately following the comparison operator is the value you are testing for. In this example that value is $Null, a Windows PowerShell 命令行接口 variable that represents a null value.

To return a collection of users who do have a voice policy assigned to them, use this command:

Get-CsUser -Filter {VoicePolicy -ne $Null}

    Get-CsUser -Filter {VoicePolicy -eq $Null}

## EXAMPLE 6

Example 6 uses the LdapFilter parameter to limit the returned data to users who work in the Finance department. This is done by using the LDAP filter value "Department=Finance".

    Get-CsUser -LdapFilter "Department=Finance"

## EXAMPLE 7

Example 7 demonstrates the use of an AND query in conjunction with the LdapFilter parameter. This query (which uses the ampersand character "&" to indicate an AND query) specifies two conditions: "Department=Finance" and "Title=Manager". For a user account to be returned by this query, both conditions must be true: a user must work in the Finance department, and he or she must be a Manager.

    Get-CsUser -LdapFilter "&(Department=Finance)(Title=Manager)"

## EXAMPLE 8

In the command shown in Example 8, an OR query (indicated by the pipe symbol "|") is used with the LdapFilter parameter. In the AND query shown in Example 7, both conditions had to be true in order for a user account to be returned. With an OR query, only one condition must be true for the account to be returned. In this case, a user account will be returned if the user is a Supervisor or if the user is a Manager.

    Get-CsUser -LdapFilter "|(Title=Supervisor)(Title=Manager)"

## EXAMPLE 9

Example 9 returns user account information for all the users with accounts in the Finance OU.

    Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com"

## EXAMPLE 10

Example 10 returns a collection of all the users who have been enabled for Lync Server or Office Communications Server but are not currently assigned to a Registrar pool.

    Get-CsUser -UnassignedUser

## Detailed Description

Used together, the **Get-CsAdUser** cmdlet and the **Get-CsUser** cmdlet enable you to return detailed information about all of your Active Directory user accounts. The **Get-CsAdUser** cmdlet returns information about all your user accounts, including users who have been enabled for Lync Server or Office Communications Server and users who have not been enabled for Lync Server or Office Communications Server. This differs from the **Get-CsUser** cmdlet, which returns information only for users whose accounts have been enabled for Lync Server or Office Communications Server.

Although there is some overlap between the two, the **Get-CsUser** cmdlet and the **Get-CsAdUser** cmdlet differ in the type of information they return. In general, the **Get-CsUser** cmdlet returns values for Active Directory attributes specifically related to Lync Server. For example, the **Get-CsUser** cmdlet returns information such as the Lync Server policies that have been assigned to a user; the line Uniform Resource Identifier (URI) assigned to that user; and details about whether the user has been enabled for Enterprise Voice. These attributes will not be part of a user account unless that user has been enabled for Lync Server.

By contrast, the **Get-CsAdUser** cmdlet returns generic Active Directory attribute values: attributes that are part of the basic Active Directory user account and are present whether or not a user has been enabled for Lync Server. For example, the **Get-CsAdUser** cmdlet returns information such as the department and organization the user works for in addition to the user's job title, and the user’s telephone number and office address.

To see a complete list of the attribute values returned by the **Get-CsUser** cmdlet, type this command at the Windows PowerShell command prompt:

Get-CsUser | Get-Member

The **Get-CsUser** cmdlet provides numerous ways for you to filter the collection of users actually returned when you run the cmdlet. For example, if you don't want to return all your Lync Server user accounts you can apply the optional parameters Filter or LdapFilter. (These parameters are mutually exclusive: if you use Filter in a command you cannot use LdapFilter in that same command, and vice-versa.) The Filter parameter enables you to limit the returned data to users who meet the specified Lync Server criteria; for example, you might decide to return only users with accounts on the specified Registrar pool, or only users who have been enabled for Enterprise Voice. The LdapFilter parameter enables you to limit the returned data to users who fit other Active Directory-based criteria; for example, users who work in a specified state or province, users who do or do not have a pager, or users with a designated job title.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsUser** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins, RTCUniversalReadOnlyAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsUser\\b"}

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
<td><p><em>Credential</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSCredential</p></td>
<td><p>Enables you to run the <strong>Get-CsUser</strong> cmdlet under alternate credentials. This might be required if the account you used to log on to the Windows does not have the necessary privileges required to work with user objects.</p>
<p>To use the Credential parameter you must first create a PSCredential object by using the <strong>Get-Credential</strong> cmdlet. For details, see the <strong>Get-Credential</strong> cmdlet help topic.</p></td>
</tr>
<tr class="even">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables you to connect to the specified domain controller in order to retrieve user information. To connect to a particular domain controller, include the DomainController parameter followed by the fully qualified domain name (FQDN) (for example, atl-cs-001.litwareinc.com).</p></td>
</tr>
<tr class="odd">
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to limit the returned data by filtering on Lync Server-specific attributes. For example, you can limit returned data to users who have been assigned a specific voice policy, or users who have not been assigned a specific voice policy.</p>
<p>The Filter parameter uses the same Windows PowerShell filtering syntax that is used by the <strong>Where-Object</strong> cmdlet. For example, a filter that returns only users who have been enabled for Enterprise Voice would look like this, with EnterpriseVoiceEnabled representing the Active Directory attribute, -eq representing the comparison operator (equal to), and $True (a built-in Windows PowerShell variable) representing the filter value:</p>
<p>{EnterpriseVoiceEnabled -eq $True}</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>Indicates the Identity of the user account to be retrieved. User Identities can be specified using one of four formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the user's Active Directory display name (for example, Ken Myer). You can also reference a user account by using the user’s Active Directory distinguished name.</p>
<p>You can use the asterisk (*) wildcard character when using the Display Name as the user Identity. For example, the Identity &quot;* Smith&quot; returns all the users who have a display name that ends with the string value &quot; Smith&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>LdapFilter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to limit the returned data by filtering on generic Active Directory attributes (that is, attributes that are not specific to Lync Server). For example, you can limit returned data to users who work in a specific department, or users who have a specified manager or job title.</p>
<p>The LdapFilter parameter uses the LDAP query language when creating filters. For example, a filter that returns only users who work in the city of Redmond would look like this: &quot;l=Redmond&quot;, with &quot;l&quot; (a lowercase L) representing the Active Directory attribute (locality); &quot;=&quot; representing the comparison operator (equal to); and &quot;Redmond&quot; representing the filter value.</p></td>
</tr>
<tr class="even">
<td><p><em>OnLyncServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns a collection of users homed on Lync Server. Users with accounts on previous versions of the software will not be returned when you use this parameter.</p></td>
</tr>
<tr class="odd">
<td><p><em>OnOfficeCommunicationServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Returns a collection of users homed on a previous version of Lync Server (for example, Office Communications Server 2007 R2). Users with accounts on the current version of the software will not be returned when you use this parameter.</p></td>
</tr>
<tr class="even">
<td><p><em>OU</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.AD.OUIdParameter</p></td>
<td><p>Enables you to return information about user accounts in a specific organizational unit (OU) or container. The OU parameter returns data from both the specified OU and any of its child OUs. For example, if the Finance OU has two child OUs -- AccountsPayable and AccountsReceivable -- users will be returned from each of these three OUs.</p>
<p>When specifying an OU, use the distinguished name (DN) of that container; for example: -OU &quot;OU=Finance,dc=litwareinc,dc=com&quot;. To return user accounts from the Users container, use this syntax: -OU &quot;cn=Users,dc=litwareinc,dc=com&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>ResultSize</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.Unlimited</p></td>
<td><p>Enables you to limit the number of records returned by the cmdlet. For example, to return seven users (regardless of the number of users that are in your forest) include the ResultSize parameter and set the parameter value to 7. Note that there is no way to guarantee which seven users will be returned.</p>
<p>The result size can be set to any whole number between 0 and 2147483647, inclusive. If set to 0 the command will run, but no data will be returned. If you set the ResultSize to 7 but you have only three users in your forest, the command will return those three users, and then complete without error.</p></td>
</tr>
<tr class="even">
<td><p><em>UnassignedUser</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to return a collection of all the users who have been enabled for Lync Server but are not currently assigned to a Registrar pool. Users are not allowed to log on to Lync Server unless they are assigned to a Registrar pool.</p></td>
</tr>
</tbody>
</table>


## Input Types

String. The **Get-CsUser** cmdlet accepts a pipelined string value representing the Identity of a user account that has been enabled for Lync Server.

## Return Types

The **Get-CsUser** cmdlet returns instances of the Microsoft.Rtc.Management.ADConnect.Schema.ADUser object.

## 另请参阅

#### 其他资源

[Disable-CsUser](disable-csuser.md)  
[Enable-CsUser](enable-csuser.md)  
[Get-CsAdUser](get-csaduser.md)  
[Move-CsUser](move-csuser.md)  
[Set-CsUser](set-csuser.md)

