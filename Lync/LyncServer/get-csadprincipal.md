---
title: Get-CsAdPrincipal
TOCTitle: Get-CsAdPrincipal
ms:assetid: df2c3714-4064-4113-861f-95ce0ae8da81
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205326(v=OCS.15)
ms:contentKeyID: 49314478
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsAdPrincipal

 

_**上一次修改主题：** 2015-03-09_

Returns information about Active Directory principals. These principals include Active Directory objects such as users, groups, contacts, containers, and organizational units. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsAdPrincipal [-Identity <UserIdParameter>] [-Credential <PSCredential>] [-DomainController <Fqdn>] [-Filter <String>] [-LDAPFilter <String>] [-OU <OUIdParameter>] [-ResultSize <Unlimited>]

## Examples

## Example 1

The command shown in Example 1 returns all the Active Directory principals in the organization.

    Get-CsAdPrincipal

## Example 2

In Example 2, information is returned for a single Active Directory principal: the principal with the SIP address "sip:RedmondMeetingRoom@litwareinc.com". This is done by including the Filter parameter and a filter value that looks for principals where the SipAddress property is equal to (-eq) "sip:RedmondMeetingRoom@litwareinc.com".

    Get-CsAdPrincipal -Filter {SipAddress -eq "sip:RedmondMeetingRoom@litwareinc.com"}

## Example 3

In the preceding example, information is returned for all the Active Directory objects. To carry out this task, the command first calls the **Get-CsAdPrincipal** cmdlet without any parameters; this returns a collection of all the Active Directory principals. That collection is then piped to the **Where-Object** cmdlet, which selects only those principals where the ObjectClass property contains the string value "contact".

    Get-CsAdPrincipal | Where-Object {$_.ObjectClass -contains "contact"}

## Detailed Description

The **Get-CsAdPrincipa**l cmdlet returns a collection of Active Directory principals that can be used when constructing Persistent Chat membership lists (see the help information for the AllowedMembers and DeniedMembers parameters for the **Set-CsPersistentChatCategory** cmdlet for more details). **Get-CsPrincipal** returns information for Active Directory objects such as:

  - **Users** (object class = {top, person, organizationalPerson, user})

  - **Groups** (object class = {top, group})

  - **Contacts** (object class = {top, person, organizationalPerson, contact})

  - **Containers** (object class = {top, container})

  - **Organizational Units** (object class = {top, organizationalUnit})

  - **Domains** (object class = {top, domain, domainDNS})

Among other things, this means that you can use the **Get-CsAdPrincipal** cmdlet (and the objectClass property) to quickly return information about Active Directory objects such as groups or organizational units. For example, this command returns the names of all your Active Directory OUs:

Get-CsAdPrincipal | Where-Object {$\_.ObjectClass –match "organizationalUnit"} | Select-Object Name

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsAdPrincipal"}

**Lync Server 控制面板:** The functions carried out by the Get-CsAdPrincipal cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Enables you to run the <strong>Get-CsAdPrincipal</strong> cmdlet under alternate credentials. This might be required if the account you used to log on to Windows does not have the necessary privileges required to work with user objects.</p>
<p>To use the Credential parameter you must first create a PSCredential object by using the <strong>Get-Credential</strong> cmdlet. For details, see the <strong>Get-Credential</strong> cmdlet help topic.</p></td>
</tr>
<tr class="even">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables you to connect to the specified domain controller in order to retrieve Active Directory principal information. To connect to a particular domain controller, include the DomainController parameter followed by the computer name (for example, atl-dc-001) or its fully qualified domain name (FQDN) (for example, atl-dc-001.litwareinc.com).</p></td>
</tr>
<tr class="odd">
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to limit the returned data by filtering on attributes specific to Lync Server.</p>
<p>The Filter parameter uses the much of the same Windows PowerShell filtering syntax used by the <strong>Where-Object</strong> cmdlet. For example, a filter that returns only principals who are not enabled for Lync Server would look like this:</p>
<p>-Filter {Enabled -ne $True}</p>
<p>In that example. Enabled represents the Active Directory attribute, -ne represents the comparison operator (not equal to), and $True (a built-in Windows PowerShell variable) represents the value True.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>Indicates the Identity of the principal account to be retrieved. Identities are typically specified by using one of four formats: 1) the account SIP address; 2) the user's user principal name (UPN); 3) the account domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the account Active Directory display name (for example, Ken Myer).</p>
<p>You can also reference a user account by using the user’s Active Directory distinguished name.</p>
<p>You can use the asterisk (*) wildcard character when using the Display Name as the Identity. For example, the Identity &quot;* Smith&quot; returns all the users who have a display name that ends with the string value &quot; Smith&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>LDAPFilter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to limit the returned data by filtering on generic Active Directory attributes (that is, attributes that are not specific to Lync Server). For example, you can limit returned data to principals who belong to a specific department or who have a specific manager or job title.</p>
<p>The LdapFilter parameter uses the LDAP query language when creating filters. For example, a filter that returns only principals located in the city of Redmond would look like this:</p>
<p>-LdapFilter &quot;l=Redmond&quot;</p>
<p>In that example, the &quot;l&quot; (a lowercase L) represents the Active Directory attribute (locality); &quot;=&quot; represents the comparison operator (equal to); and &quot;Redmond&quot; represents the filter value.</p></td>
</tr>
<tr class="even">
<td><p><em>OU</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.AD.OUIdParameter</p></td>
<td><p>Enables you to return information about principals in a specific organizational unit (OU) or container. The OU parameter returns data from both the specified OU and any of its child OUs. For example, if the Finance OU has two child OUs -- AccountsPayable and AccountsReceivable – principals will be returned from each of these three OUs.</p>
<p>When specifying an OU, use the distinguished name (DN) of that container; for example:</p>
<p>-OU &quot;OU=Finance,dc=litwareinc,dc=com&quot;</p>
<p>To return principals from the Users container, use this syntax:</p>
<p>-OU &quot;cn=Users,dc=litwareinc,dc=com&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>ResultSize</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.ADConnect.Core.Unlimited</p></td>
<td><p>Enables you to limit the number of records returned by the cmdlet. For example, to return seven principals (regardless of the number of principals that are in your forest) include the ResultSize parameter and set the parameter value to 7. Note that there is no way to guarantee which seven principals will be returned.</p>
<p>The result size can be set to any whole number between 0 and 2147483647, inclusive. If set to 0 the command will run, but no data will be returned. If you set the ResultSize to 7 but you have only three principals in your forest, the command will return those three principals, and then complete without error.</p></td>
</tr>
</tbody>
</table>


## Input Types

String value or object representing an Active Directory user, group, contact, container, and organizational unit. For example, this syntax returns Active Directory principal information for the Redmond and Dublin OUs:

"OU=Redmond,DC=litwareinc,DC=com", "OU=Dublin,DC=litwareinc,DC=com" | Get-CsAdPrincipal

## Return Types

The **Get-CsAdPrincipal** cmdlet returns instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSADPrincipal object.

## 另请参阅

#### 其他资源

[New-CsPersistentChatCategory](new-cspersistentchatcategory.md)  
[Set-CsPersistentChatCategory](set-cspersistentchatcategory.md)

