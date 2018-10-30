---
title: Enable-CsUser
TOCTitle: Enable-CsUser
ms:assetid: 8ceed97b-e802-4844-b509-c6ca9619ec55
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398711(v=OCS.15)
ms:contentKeyID: 49313536
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Enable-CsUser

 

_**上一次修改主题：** 2015-03-09_

Enables one or more users for Lync Server. Users cannot use Lync 2013 or other Lync Server clients until their user accounts have been enabled for Lync Server. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Enable-CsUser -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-HostingProviderProxyFqdn <Fqdn>] [-PassThru <SwitchParameter>] [-ProxyPool <Fqdn>] [-RegistrarPool <Fqdn>] [-SipAddress <String>] [-SipAddressType <FirstLastName | EmailAddress | UserPrincipalName | SAMAccountName | None>] [-SipDomain <Fqdn>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the **Enable-CsUser** cmdlet enables the user account with the display name Pilar Ackerman. In this example, the user is assigned to the Registrar pool atl-cs-001.litwareinc.com, and Lync Server auto-generates the SIP address by using the user's SamAccountName (pilar) followed by the SIP domain litwareinc.com.

    Enable-CsUser -Identity "Pilar Ackerman" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddressType SamAccountName  -SipDomain litwareinc.com

## EXAMPLE 2

In Example 2, the Active Directory user account belonging to Pilar Ackerman is enabled for use with Lync Server. In order to configure the account for Lync Server the following parameters are used along with the **Enable-CsUser** cmdlet: Identity, which identifies the account to be enabled; RegistrarPool, which indicates the Standard Edition server or Enterprise Edition Front End pool on which the user is to be homed; and SipAddress, which specifies the SIP address for the new user. In this case, the SIP address is explicitly assigned instead of using Lync Server to auto-generate the address.

    Enable-CsUser -Identity "Pilar Ackerman" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:pilar@litwareinc.com"

## EXAMPLE 3

In Example 3, all the users who work for the Finance department have their accounts enabled for Lync Server. To carry out this task, the **Get-CsAdUser** cmdlet is used, along with the LdapFilter parameter, to return a collection of all the users who work for the Finance department. That information is then piped to the **Enable-CsUser** cmdlet, which enables each account in the collection for Lync Server.

In order to enable an account, you must specify the user's Registrar pool and the user's SIP address. In this example, the Registrar pool is specified by using the RegistrarPool parameter. The SIP address is not directly assigned, however. Instead, two parameters, SipAddressType and SipDomain, are added to the command. That means that a new SIP address consisting of the user's SamAccountName and the SIP domain name will automatically be generated for each account. For example, a user with the SamAccountName kenmyer will be given the SIP address sip:kenmyer@litwareinc.com.

    Get-CsAdUser -LdapFilter "department=Finance" | Enable-CsUser -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddressType SamAccountName  -SipDomain litwareinc.com

## EXAMPLE 4

Example 4 enables all the Active Directory users who have not yet been enabled for Lync Server. To do this, the **Get-CsAdUser** cmdlet is invoked, along with the Filter parameter. The filter {Enabled -ne $True} returns a collection of all the users who have not been enabled for Lync Server. That collection is then piped to the **Enable-CsUser** cmdlet, which enables each account, assigning the user to the Registrar pool atl-cs-001.litwareinc.com and auto-generating a SIP address for each user.

    Get-CsAdUser -Filter {Enabled -ne $True} | Enable-CsUser -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddressType SamAccountName  -SipDomain litwareinc.com

## Detailed Description

Before a user can log on to Lync Server, that user must meet two requirements: he or she must have a valid Active Directory account, and that account must be enabled for Lync Server. One way to enable a user account for Lync Server is to use the **Enable-CsUser** cmdlet. To use this cmdlet to enable an account for Lync Server, you must: 1) Select the account (or accounts) to be enabled; 2) Select a Registrar pool for the account; and 3) Assign the account a SIP address. Lync Server gives administrators the option of assigning the user a specific SIP address or having Lync Server create a SIP address for you.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Enable-CsUser** cmdlet locally: RTCUniversalUserAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Enable-CsUser"}

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
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>Indicates the Identity of the user account to be enabled for Lync Server. User Identities can be specified by using one of four formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the user's Active Directory display name (for example, Ken Myer). You can also reference a user account by using the user’s Active Directory distinguished name.</p>
<p>You can use the asterisk (*) wildcard character when using the Display Name as the user Identity. For example, the Identity &quot;* Smith&quot; returns all the user who have a display name that ends with the string value &quot; Smith&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables you to connect to the specified domain controller in order to enable a user account. To connect to a particular domain controller, include the DomainController parameter followed by the computer name (for example, atl-cs-001) or its fully qualified domain name (FQDN) (for example, atl-cs-001.litwareinc.com).</p></td>
</tr>
<tr class="even">
<td><p><em>HostingProviderProxyFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>This parameter is used only for Lync Online. It should not be used with an on-premises implementation of Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to pass a user object through the pipeline that represents the user account being enabled for Lync Server. By default, the <strong>Enable-CsUser</strong> cmdlet does not pass objects through the pipeline.</p></td>
</tr>
<tr class="even">
<td><p><em>ProxyPool</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>This parameter is used only for Lync Online. It should not be used with an on-premises implementation of Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><em>RegistrarPool</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Indicates the Registrar pool where the user's Lync Server account will be homed.</p></td>
</tr>
<tr class="even">
<td><p><em>SipAddress</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to assign the user a specific SIP address. When specifying the SIP address, preface the address with &quot;sip:&quot;. That means the value supplied to the SipAddress parameter should look something like this :</p>
<p>sip:kenmyer@litwareinc.com</p>
<p>The SipAddress parameter should not be used if you use the SipAddressType parameter in order to have Lync Server automatically generate a SIP address for the user.</p>
<p>The SipAddress parameter cannot be used if you are attempting to enable multiple users at the same time. Instead, you must auto-generate SIP address for those users by using the SipAddressType parameter.</p></td>
</tr>
<tr class="odd">
<td><p><em>SipAddressType</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.AD.Cmdlets.AddressType</p></td>
<td><p>Instructs Lync Server to auto-generate a SIP address for the new user. In order to have Lync Server auto-generate the SIP address, you must include the SipAddressType parameter and use one of the following parameter values:</p>
<p>FirstLastName. The SIP address is the user's first name and a period followed by the user's last name and the SIP domain. For example, the user Ken Myer would have a SIP address similar to this: Ken.Myer@litwareinc.com. If you use this address type then you must also include the SipDomain parameter.</p>
<p>EmailAddress. The user's email address (as defined in Active Directory) is used as the SIP address.</p>
<p>UserPrincipalName. The user's UPN is used as the SIP address.</p>
<p>SamAccountName. The SIP address is the user's SamAccountName (logon name) followed by the SIP domain. For example, the user with the SamAccountName kmyer will have a SIP address similar to this: kmyer@litwareinc.com. If you use this address type then you must also include the SipDomain parameter.</p>
<p>The SipAddressType parameter is not required if you use the SIPAddress parameter and explicitly assign the user a SIP address.</p></td>
</tr>
<tr class="even">
<td><p><em>SipDomain</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>The SIP domain for the user account being enabled. This parameter is required if you use the SIPAddressType parameter to have Lync Server auto-generate a SIP address for the user and you based SIP addresses on the SamAccountName or the user’s first name and last name. This parameter is not required if you base SIP addresses on the user’s email address or UPN; that’s because the domain name is already included in those attribute values.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

String or Microsoft.Rtc.Management.ADConnect.Schema.ADUser object. The **Enable-CsUser** cmdlet accepts a pipelined string value representing the Identity of a user account that has been enabled for Lync Server. The cmdlet also accepts pipelined instances of the Active Directory user object.

## Return Types

None. The **Enable-CsUser** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.ADConnect.Schema.ADUser object.

## 另请参阅

#### 其他资源

[Disable-CsUser](disable-csuser.md)  
[Get-CsUser](get-csuser.md)

