---
title: Get-CsKerberosAccountAssignment
TOCTitle: Get-CsKerberosAccountAssignment
ms:assetid: 6eaba274-1693-42a7-841d-513bc1153647
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398526(v=OCS.15)
ms:contentKeyID: 49313187
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsKerberosAccountAssignment

 

_**上一次修改主题：** 2015-03-09_

Returns information about the Kerberos account assignments configured for use in the organization. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsKerberosAccountAssignment [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsKerberosAccountAssignment [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

The command shown in Example 1 returns information about all the Kerberos account assignments currently in use in the organization.

    Get-CsKerberosAccountAssignment

## EXAMPLE 2

Example 2 returns information about a single Kerberos account assignment: the account assignment for the Redmond site.

    Get-CsKerberosAccountAssignment -Identity "site:Redmond"

## EXAMPLE 3

In Example 3, information is returned for all the Kerberos accounts that have been assigned to sites that have the string value "Redmond" somewhere in their site Identity. To do this, the Filter parameter is included along with the filter value "\*Redmond".

    Get-CsKerberosAccountAssignment -Filter "*Redmond*"

## EXAMPLE 4

Example 4 returns information about all the Kerberos account assignments where the identity of the assigned account includes the string value "litwareinc". To carry out this task, the command first calls the **Get-CsKerberosAccountAssignment** cmdlet without any parameters; that returns a collection of all the Kerberos accounts assignments currently in use. This collection is then piped to the **Where-Object** cmdlet, which picks out only those account assignments where the identity of the account includes the string value "litwareinc". (Note that, despite the parameter name UserAccount, the account in question is actually a computer account.)

    Get-CsKerberosAccountAssignment | Where-Object {$_.UserAccount -match "litwareinc"}

## Detailed Description

In Microsoft Office Communications Server 2007 and Microsoft Office Communications Server 2007 R2, IIS ran under a standard user account. This had the potential to cause issues: if that password expired you could lose your Web 服务, an issue that was often difficult to diagnose. To help avoid the issue of expiring passwords, Lync Server enables you to create a computer account (for a computer that doesn’t actually exist) that can serve as the authentication principal for all the computers in a site that are running IIS. Because these accounts use the Kerberos authentication protocol, the accounts are referred to as Kerberos accounts, and the new authentication process is known as Kerberos web authentication. This enables you to manage all your IIS servers by using a single account.

To run your servers under this new authentication principal, you must first create a computer account by using the **New-CsKerberosAccount** cmdlet; this account is then assigned to one or more sites. After the assignment has been made, the association between the account and the Lync Server site is enabled by running the **Enable-CsTopology** cmdlet. Among other things, this creates the required service principal name (SPN) in Active Directory 域服务. SPNs provide a way for client applications to locate a particular service.

The **Get-CsKerberosAccountAssignment** cmdlet provides a way for you to return information about the Kerberos account assignments currently in use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsKerberosAccountAssignment** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsKerberosAccountAssignment"}

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
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to use wildcard characters when specifying the Kerberos account assignment (or assignments) to be returned. For example, this syntax returns all the account assignments that include the string value &quot;Europe&quot;: -Filter &quot;*Europe*&quot;.</p>
<p>You cannot use both the Identity and the Filter parameters in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier of the site where the Kerberos account was assigned; for example: -Identity &quot;site:Redmond&quot;. (Note that this is the Identity of the site, not of the computer account.) You cannot use wildcards when specifying the site identity. To employ wildcards, use the Filter parameter instead.</p>
<p>If neither the Identity nor the Filter parameter is included, then the <strong>Get-CsKerberosAccountAssignment</strong> cmdlet returns all the Kerberos account assignments configured for use in the organization.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the Kerberos assignment data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsKerberosAccountAssignment** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsKerberosAccountAssignment** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.KerberosAccount.KerberosAccountAssignment object.

## 另请参阅

#### 其他资源

[New-CsKerberosAccountAssignment](new-cskerberosaccountassignment.md)  
[Remove-CsKerberosAccountAssignment](remove-cskerberosaccountassignment.md)  
[Set-CsKerberosAccountAssignment](set-cskerberosaccountassignment.md)

