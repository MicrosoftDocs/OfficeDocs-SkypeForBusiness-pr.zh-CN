---
title: New-CsKerberosAccount
TOCTitle: New-CsKerberosAccount
ms:assetid: 67ffa1b1-0ca5-410b-81f7-2375b9dbef3c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398485(v=OCS.15)
ms:contentKeyID: 49313108
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsKerberosAccount

 

_**上一次修改主题：** 2015-03-09_

Creates a new Kerberos account used for Internet Information Services (IIS) authentication. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsKerberosAccount -UserAccount <String> [-Confirm [<SwitchParameter>]] [-ContainerDN <String>] [-Force <SwitchParameter>] [-Report <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The commands shown in Example 1 create a new Kerberos account (litwareinc\\kerberostest), and then assign that account to the Redmond site. To do this, the first command in the example creates an account with the account name "litwareinc\\kerberostest". This account will be created in the Computers container in the Litwareinc.com domain. After the account has been created, the second command uses the **New-CsKerberosAccountAssignment** cmdlet to assign that Kerberos account to the Redmond site.

After you make the new account assignment, the final command calls the **Enable-CsTopology** cmdlet in order to enable the changes.

    New-CsKerberosAccount -UserAccount "litwareinc\kerberostest" -ContainerDN "cn=Computers,dc=litwareinc,dc=com"
    
    New-CsKerberosAccountAssignment -UserAccount "litwareinc\kerberostest" -Identity "site:Redmond"
    Enable-CsTopology

## Detailed Description

In Microsoft Office Communications Server 2007 and Microsoft Office Communications Server 2007 R2, IIS ran under a standard user account. This had the potential to cause issues: if that password expired you could lose your Web 服务, an issue that was often difficult to diagnose. To help avoid the issue of expiring passwords, Lync Server enables you to create a computer account (for a computer that doesn’t actually exist) that can serve as the authentication principal for all the computers in a site that are running IIS. Because these accounts use the Kerberos authentication protocol, the accounts are referred to as Kerberos accounts, and the new authentication process is known as Kerberos web authentication. This enables you to manage all your IIS servers by using a single account.

To run your servers under this authentication principal, you must first create a computer account by using the **New-CsKerberosAccount** cmdlet; this account is then assigned to one or more sites. After the assignment has been made, the association between the account and the Lync Server site is enabled by running the **Enable-CsTopology** cmdlet. Among other things, this creates the required service principal name (SPN) in Active Directory 域服务. SPNs provide a way for client applications to locate a particular service.

Who can run this cmdlet: You must be a domain administrator in order to run the **New-CsKerberosAccount** cmdlet locally. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsKerberosAccount\\b"}

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
<td><p><em>UserAccount</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Account name for the new account, using the format domain_name\user_name. For example: -UserAccount &quot;litwareinc\kerberostest&quot;. Note that your command will fail if the specified account already exists.</p>
<p>Note, too that, despite the name UserAccount, the account created by running the <strong>New-CsKerberosAccount</strong> cmdlet is actually a computer account, not a user account.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>ContainerDN</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Distinguished name of the Active Directory container where the new account is to be created. For example: -ContainerDN &quot;ou=Finance,dc=litwareinc,dc=com&quot;. If this parameter is not specified, then the <strong>New-CsKerberosAccount</strong> cmdlet will create the new account in the Computers container in Active Directory.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Report</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to specify a file path for the log file created when the cmdlet runs. For example: -Report &quot;C:\Logs\KerberosAccount.html&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsKerberosAccount** cmdlet does not accept pipelined input.

## Return Types

The **New-CsKerberosAccount** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.KerberosAccount.KerberosAccount object.

## 另请参阅

#### 其他资源

[New-CsKerberosAccountAssignment](new-cskerberosaccountassignment.md)

