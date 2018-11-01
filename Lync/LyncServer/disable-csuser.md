---
title: Disable-CsUser
TOCTitle: Disable-CsUser
ms:assetid: 92e7e29e-2620-4852-9e4a-2fd3569bb095
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398747(v=OCS.15)
ms:contentKeyID: 49313625
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Disable-CsUser

 

_**上一次修改主题：** 2015-03-09_

Modifies the Active Directory account of the specified user or users; this modification prevents users from using Lync Server clients such as Lync 2013. The **Disable-CsUser** cmdlet only restricts activity related to Lync Server; it does not disable or remove a user’s Active Directory account. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Disable-CsUser -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-PassThru <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 disables the Lync Server account for the user Ken Myer. In this example, the user's display name is used to indicate his Identity.

    Disable-CsUser -Identity "Ken Myer"

## EXAMPLE 2

In Example 2, all the users in the Finance department have their Lync Server accounts disabled. To carry out this task, the command first uses the **Get-CsUser** cmdlet and the LdapFilter parameter to return a collection of all the users who belong to the Finance department. That collection is then piped to the **Disable-CsUser** cmdlet, which disables each account in the collection.

    Get-CsUser -LdapFilter "Department=Finance" | Disable-CsUser

## EXAMPLE 3

In this example, all the user accounts not currently assigned to a Registrar pool are disabled. To do this, the **Get-CsUser** cmdlet is called, along with the UnassignedUser parameter. This parameter restricts the returned data to users who have valid user accounts but are not assigned to a Registrar pool. That collection is then piped to the Disable-CsUser cmdlet, which disables each account in the collection.

    Get-CsUser -UnassignedUser | Disable-CsUser

## Detailed Description

The **Disable-CsUser** cmdlet deletes all the attribute information related to Lync Server from an Active Directory user account; this prevents the user from logging on to Lync Server. When you run the **Disable-CsUser** cmdlet all the Lync Server-related attributes are removed from an account, including the Identities of any per-user policies that have been assigned to that account. You can later re-enable the account by using the **Enable-CsUser** cmdlet. However, all the Lync Server-related information (such as policy assignments) previously associated with that account will have to be re-created. If you want to prevent a user from logging on to Lync Server, but do not want to lose all of their account information, use the **Set-CsUser** cmdlet instead. For details, see the [Set-CsUser](set-csuser.md) cmdlet help topic.

After an account has been disabled with the **Disable-CsUser** cmdlet, the affected user will no longer be returned by the **Get-CsUser** cmdlet; that’s because that user no longer has a valid Lync Server account. To retrieve information for the disabled user account, use the **Get-CsAdUser** cmdlet.

In addition, user data belonging to the deleted user account will be removed from the backend databases; for example, the user will be removed from Contacts lists in the organization, and any conferences scheduled by that user will be deleted.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Disable-CsUser** cmdlet locally: RTCUniversalUserAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Disable-CsUser"}

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
<td><p>Indicates the Identity of the user account to be disabled. User Identities can be specified by using one of four formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the user's Active Directory display name (for example, Ken Myer). You can also reference a user account by using the Active Directory distinguished name.</p>
<p>You can use the asterisk (*) wildcard character when using the Display Name as the user Identity. For example, the Identity &quot;* Smith&quot; returns all the users who have a display name that ends with the string value &quot; Smith&quot;.</p></td>
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
<td><p>Enables you to connect to the specified domain controller in order to disable a user account. To connect to a particular domain controller, include the DomainController parameter followed by the computer name (for example, atl-cs-001) or its fully qualified domain name (FQDN) (for example, atl-cs-001.litwareinc.com).</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to pass a user object through the pipeline that represents the user account being disabled. By default, the <strong>Disable-CsUser</strong> cmdlet does not pass objects through the pipeline.</p></td>
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

String or Microsoft.Rtc.Management.ADConnect.Schema.ADUser object. The **Disable-CsUser** cmdlet accepts a pipelined string value representing the Identity of a user account that has been enabled for Lync Server. The cmdlet also accepts pipelined instances of the Active Directory user object.

## Return Types

The **Disable-CsUser** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.ADConnect.Schema.ADUser object.

## 另请参阅

#### 其他资源

[Enable-CsUser](enable-csuser.md)  
[Get-CsUser](get-csuser.md)

