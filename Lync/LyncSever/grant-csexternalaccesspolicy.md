﻿---
title: Grant-CsExternalAccessPolicy
TOCTitle: Grant-CsExternalAccessPolicy
ms:assetid: 451fef34-3021-4261-8494-b36420b04c82
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425942(v=OCS.15)
ms:contentKeyID: 49312699
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Grant-CsExternalAccessPolicy

 

_**上一次修改主题：** 2015-03-09_

Enables you to assign an external access policy to a user or a group of users. External access policies determine whether or not your users can: 1) communicate with users who have Session Initiation Protocol (SIP) accounts with a federated organization; 2) communicate with users who have SIP accounts with a public instant messaging (IM) provider such as MSN; and, 3) access Lync Server over the Internet, without having to log on to your internal network. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Grant-CsExternalAccessPolicy -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-PassThru <SwitchParameter>] [-PolicyName <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 assigns the external access policy RedmondAccessPolicy to the user with the Active Directory display name Ken Myer.

    Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName RedmondAccessPolicy

## EXAMPLE 2

The command shown in Example 2 assigns the external access policy RedmondAccessPolicy to all the users who work in the city of Redmond. To do this, the command first uses the **Get-CsUser** cmdlet and the LdapFilter parameter to return a collection of all the users who work in Redmond; the filter value "l=Redmond" limits returned data to those users who work in the city of Redmond (the l in the filter, a lowercase L, represents the locality). That collection is then piped to the **Grant-CsExternalAccessPolicy** cmdlet, which assigns the policy RedmondAccessPolicy to each user in the collection.

    Get-CsUser -LdapFilter "l=Redmond" | Grant-CsExternalAccessPolicy -PolicyName RedmondAccessPolicy

## EXAMPLE 3

In Example 3, all the users who have the job title "Sales Representative" are assigned the external access policy SalesAccessPolicy. To perform this task, the command first uses the **Get-CsUser** cmdlet and the LdapFilter parameter to return a collection of all the Sales Representatives; the filter value "Title=Sales Representative" restricts the returned collection to users who have the job title "Sales Representative". This filtered collection is then piped to the **Grant-CsExternalAccessPolicy** cmdlet, which assigns the policy SalesAccessPolicy to each user in the collection.

    Get-CsUser -LdapFilter "Title=Sales Representative" | Grant-CsExternalAccessPolicy -PolicyName SalesAccessPolicy

## EXAMPLE 4

The command shown in Example 4 assigns the external access policy BasicAccessPolicy to all the users who have not been explicitly assigned a per-user policy. (That is, users currently being governed by a site policy or by the global policy.) To do this, the **Get-CsUser** cmdlet and the Filter parameter are used to return the appropriate set of users; the filter value {ExternalAccessPolicy -eq $Null} limits the returned data to user accounts where the ExternalAccessPolicy property is equal to (-eq) a null value ($Null). By definition, ExternalAccessPolicy will be null only if users have not been assigned a per-user policy.

    Get-CsUser -Filter {ExternalAccessPolicy -eq $Null} | Grant-CsExternalAccessPolicy -PolicyName BasicAccessPolicy

## EXAMPLE 5

Example 5 assigns the external access policy USAccessPolicy to all the users who have accounts in the US organizational unit (OU). The command starts off by calling the **Get-CsUser** cmdlet and the OU parameter; the parameter value "ou=US,dc=litwareinc,dc=com" limits the returned data to user accounts found in the US OU. The returned collection is then piped to the **Grant-CsExternalAccessPolicy** cmdlet, which assigns the policy USAccessPolicy to each user in the collection.

    Get-CsUser -OU "ou=US,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName USAccessPolicy

## EXAMPLE 6

Example 6 unassigns any per-user external access policy previously assigned to any of the users enabled for Lync Server. To do this, the command calls the **Get-CsUser** cmdlet (without any additional parameters) in order to return a collection of all the users enabled for Lync Server. That collection is then piped to the **Grant-CsExternalAccessPolicy** cmdlet, which uses the syntax "-PolicyName $Null" to remove any per-user external access policy previously assigned to these users.

    Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName $Null

## Detailed Description

When you install Lync Server your users are only allowed to exchange instant messages and presence information among themselves: by default, they can only communicate with other people who have SIP accounts in your Active Directory 域服务. In addition, users are not allowed to access Lync Server over the Internet; instead, they must be logged on to your internal network before they will be able to log on to Lync Server.

That might be sufficient to meet your communication needs. If it doesn’t meet your needs you can use external access policies to extend the ability of your users to communicate and collaborate. External access policies can grant (or revoke) the ability of your users to do any or all of the following:

1\. Communicate with people who have SIP accounts with a federated organization. Note that enabling federation will not automatically provide users with this capability. Instead, you must enable federation, and then assign users an external access policy that gives them the right to communicate with federated users.

2\. Communicate with people who have SIP accounts with a public instant messaging service such as MSN.

3\. Access Lync Server over the Internet, without having to first log on to your internal network. This enables your users to use Lync and log on to Lync Server from an Internet café or other remote location.

When you install Lync Server, a global external access policy is automatically created for you. In addition to this global policy, you can use the **New-CsExternalAccessPolicy** cmdlet to create additional external access policies configured at either the site or the per-user scope.

When a policy is created at the site scope, it is automatically assigned to the site in question; for example, an external access policy with the Identity site:Redmond will automatically be assigned to the Redmond site. By contrast, policies created at the per-user scope are not automatically assigned to anyone. Instead, these policies must be explicitly assigned to a user or a group of users. Assigning per-user policies is the job of the **Grant-CsExternalAccessPolicy** cmdlet.

Note that per-user policies always take precedent over site policies and the global policy. For example, suppose you create a per-user policy that allows communication with federated users, and you assign that policy to Ken Myer. As long as that policy is in force, Ken will be allowed to communicate with federated users even if this type of communication is not allowed by Ken’s site policy or by the global policy. That’s because the settings in the per-user policy take precedence.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Grant-CsExternalAccessPolicy** cmdlet locally: RTCUniversalUserAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Grant-CsExternalAccessPolicy"}

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
<td><p>Identity of the user account the policy should be assigned to. User Identities can be specified by using one of four formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the user's Active Directory display name (for example, Ken Myer). User Identities can also be referenced by using the user’s Active Directory distinguished name.</p>
<p>In addition, you can use the asterisk (*) wildcard character when specifying the user Identity. For example, the Identity &quot;* Smith&quot; returns all the users with a display name that ends with the string value &quot; Smith.&quot;</p></td>
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
<td><p>Enables you to specify the fully qualified domain name (FQDN) of a domain controller to be contacted when assigning the new policy. If this parameter is not specified, then the <strong>Grant-CsExternalAccessPolicy</strong> cmdlet will contact the first available domain controller.</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to pass a user object through the pipeline that represents the user being assigned the policy. By default, the <strong>Grant-CsExternalAccessPolicy</strong> cmdlet does not pass objects through the pipeline.</p></td>
</tr>
<tr class="odd">
<td><p><em>PolicyName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>&quot;Name&quot; of the policy to be assigned. The PolicyName is simply the policy Identity minus the policy scope (the &quot;tag:&quot; prefix). For example, a policy with the Identity tag:Redmond has a PolicyName equal to Redmond; a policy with the Identity tag:RedmondAccessPolicy has a PolicyName equal to RedmondAccessPolicy.</p>
<p>To unassign a per-user policy previously assigned to a user, set the PolicyName parameter to $Null.</p></td>
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

String value or Microsoft.Rtc.Management.ADConnect.Schema.ADUser object. The **Grant-CsExternalAccessPolicy** cmdlet accepts pipelined input of string values representing the Identity of a user account. The cmdlet also accepts pipelined input of user objects.

## Return Types

By default, the **Grant-CsExternalAccessPolicy** cmdlet does not return a value or object. However, if you include the PassThru parameter, the cmdlet will return instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSUserOrAppContact object.

## 另请参阅

#### 其他资源

[Get-CsExternalAccessPolicy](get-csexternalaccesspolicy.md)  
[New-CsExternalAccessPolicy](new-csexternalaccesspolicy.md)  
[Remove-CsExternalAccessPolicy](remove-csexternalaccesspolicy.md)  
[Set-CsExternalAccessPolicy](set-csexternalaccesspolicy.md)

