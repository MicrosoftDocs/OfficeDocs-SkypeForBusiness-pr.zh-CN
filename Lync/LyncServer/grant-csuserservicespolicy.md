﻿---
title: Grant-CsUserServicesPolicy
TOCTitle: Grant-CsUserServicesPolicy
ms:assetid: f68b5c61-9820-4b49-954a-2dd61156bc02
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205388(v=OCS.15)
ms:contentKeyID: 49314767
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Grant-CsUserServicesPolicy

 

_**上一次修改主题：** 2015-03-09_

Assigns a per-user User Services policy to one or more users. User Services policies determine whether or not a user's contacts are stored in Lync Server 2013 or in the Unified Contact Store. The Unified Contact Store provides a way for users to maintain a single set of contacts that can be accessed using Lync 2013, Microsoft Outlook, and/or Microsoft Outlook Web Access. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Grant-CsUserServicesPolicy -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-PassThru <SwitchParameter>] [-PolicyName <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 assigns the per-user User Services policy RedmondUserServicesPolicy to the user with the Identity (in this example, the Active Directory display name) Ken Myer.

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "RedmondUserServicesPolicy"

## Example 2

Example 2 unassigns any per-user Users Services policy previously assigned to Ken Myer. Per-user policies are unassigned by setting the PolicyName parameter to a Null value ($Null).

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName $Null

## Example 3

In Example 3, all the users on the RegistrarPool atl-cs-001.litwareinc.com are assigned the per-user Users Services policy RedmondUserServicesPolicy. To do this, the **Get-CsUser** cmdlet is first called along with the Filter parameter; the filter value {RegistrarPool –eq "atl-cs-001.litwareinc.com" limits the returned data to users who have been homed on the Registrar pool atl-cs-001.litwareinc.com. This collection of users is then piped to the **Grant-CsUserServicesPolicy** cmdlet, which, in turn assigns the policy RedmondUserServicesPolicy to each user in the collection.

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsUserServicesPolicy -PolicyName "RedmondUserServicesPolicy"

## Detailed Description

The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server; in turn that allows the user to access the same set of contacts in Microsoft Outlook and Outlook Web Access as well as in Lync 2013. (Alternatively, you can continue to store contacts in Lync Server 2013. In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)

In order to take advantage of the unified contact store you must (among other things) assign the user a user services policy that enables the use of the unified contact store. User service policies (which can be configured at the global, site, or the per-user scope) contain only a single property: UcsAllowed. When this property is set to True then (assuming all the other prerequisites have been met) the next time a user logs on to Lync Server 2013 his or her contacts will automatically be migrated to the unified contact store.

If this property is set to False this automatic migration will not take place. However, simply setting UcsAllowed will not cause a user's contacts to be moved from the unified contact store back to Lync Server. In order to do that, you must first assign the user a user services policy that does not allow the use of the unified contact store. After that, you must then use the I**nvoke-UcsRollback** cmdlet to "manually" migrate the contacts from the unified contact store back to Lync Server.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Grant-CsUserServicesPolicy"}

**Lync Server 控制面板:** The functions carried out by the **Grant-CsUserServicesPolicy** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Indicates the Identity of the user account to be assigned the per-user user experience policy. User Identities are typically specified using one of four formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (four example, litwareinc\kenmyer); and, 4) the user's Active Directory display name (for example, Ken Myer).</p>
<p>User Identities can also be specified by using the user’s Active Directory distinguished name.</p>
<p>In addition, you can use the asterisk (*) wildcard character when using the Display Name as the user Identity. For example, the Identity &quot;* Smith&quot; returns all the users who have a display name that ends with the string value &quot; Smith&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables you to connect to the specified domain controller in order to retrieve user information. To connect to a particular domain controller, include the DomainController parameter followed by the computer name (for example, atl-dc-001) or its fully qualified domain name (FQDN) (for example, atl-dc-001.litwareinc.com).</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to pass a user object through the pipeline that represents the user account being assigned the policy. By default, the <strong>Grant-CsUserServicesPolicy</strong> cmdlet does not pass objects through the pipeline.</p></td>
</tr>
<tr class="odd">
<td><p><em>PolicyName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>&quot;Name&quot; of the policy to be assigned. The PolicyName is simply the policy Identity minus the policy scope (the &quot;tag:&quot; prefix). For example, a policy with the Identity tag:Redmond has a PolicyName equal to Redmond; likewise, a policy with the Identity tag:RedmondUserExperiencePolicy has a PolicyName equal to RedmondUserExperiencePolicy.</p>
<p>To unassign a per-user policy previously assigned to a user, set the PolicyName to a null value ($Null).</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

String value or Microsoft.Rtc.Management.ADConnect.Schema.ADUser object. The **Grant-CsUserServicesPolicy** cmdlet accepts pipelined input of string values representing the Identity of a user account. The cmdlet also accepts pipelined input of user objects.

## Return Types

By default, the **Grant-CsUserServicesPolicy** cmdlet does not return a value or object. However, if you include the PassThru parameter, the cmdlet will return instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSUserOrAppContact.

## 另请参阅

#### 其他资源

[Get-CsUserServicesPolicy](get-csuserservicespolicy.md)  
[New-CsUserServicesPolicy](new-csuserservicespolicy.md)  
[Remove-CsUserServicesPolicy](remove-csuserservicespolicy.md)  
[Set-CsUserServicesPolicy](set-csuserservicespolicy.md)

