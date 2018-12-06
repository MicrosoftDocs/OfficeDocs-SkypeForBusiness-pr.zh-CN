﻿---
title: Invoke-CsUcsRollback
TOCTitle: Invoke-CsUcsRollback
ms:assetid: 0aed0286-e552-4d47-93bc-3375cab48a03
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204661(v=OCS.15)
ms:contentKeyID: 49311955
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Invoke-CsUcsRollback

 

_**上一次修改主题：** 2015-03-09_

Removes a user's contacts from the Unified Contact Store and, instead, stores that contact information in Lync Server 2013. The Unified Contact Store provides a way for users to maintain a single set of contacts that can be accessed using Lync 2013, Microsoft Outlook, and/or Microsoft Outlook Web Access. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Invoke-CsUcsRollback -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-Force <SwitchParameter>] [-PassThru <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 removes the user Ken Myer from the unified contact store.

    Invoke-CsUcsRollback -Identity "Ken Myer"

## Example 2

In Example 2, all the users homed on the Registrar pool atl-cs-001.litwareinc.com are removed from the unified contact store. To do this, the command first calls the **Get-CsUser** cmdlet along with the Filter parameter; the filter value {RegistrarPool –eq "atl-cs-001.litwareinc.com"} limits the returned data to users homed on the pool atl-cs-001.litwareinc.com. Those user accounts are then piped to the **Invoke-CsUcsRollback** cmdlet, which removes each user from the unified contact store. In order to suppress the confirmation prompt that would otherwise occur each time the cmdlet rolls back a user account, the Confirm parameter is included using this syntax:-Confirm:$False

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Invoke-CsUcsRollback -Confirm:$False

## Detailed Description

The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server; in turn that allows the user to access the same set of contacts in Microsoft Outlook and Outlook Web Access as well as in Lync 2013. (Alternatively, you can continue to store contacts in Lync Server. In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)

In order to take advantage of the unified contact store you must (among other things) assign the user a user services policy that enables the use of the unified contact store; if all the other prerequisites have been met, then the next time the user logs on using Lync Server 2013 his or her contacts will automatically be moved from Lync Server to the unified contact store. See the help topic for the Set-CsUserServicesPolicy cmdlet for more information.

If later decide to move those contacts back to Lync Server (and out of the unified contact store) then you need to do two things. First, you must assign the user a new user services policy, one that prohibits the use of the unified contact store. Second, you must use the **Invoke-CsUcsRollback** cmdlet to "manually" migrate the contacts from the unified contact store back to Lync Server. Simply changing the user services policy will not remove the user's contacts from the unified contact store; that can only be done by calling the **Invoke-CsUcsRollback** cmdlet.

Note. Technically, calling the **Invoke-CsUcsRollback** cmdlet by itself, without modifying the user services policy, will remove a user's contacts from the unified contact store. However, this change will only be temporary: if you do not change the user services policy then, after a 7-day waiting period, the user's contacts will automatically be moved back into the unified contact store.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Invoke-CsUcsRollback"}

**Lync Server 控制面板:** The functions carried out by the **Invoke-CsUcsRollback** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Indicates the Identity of the user account to be rolled back. User Identities are typically specified using one of four formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (for example, litwareinc\kenmyer); and, 4) the user's Active Directory display name (for example, Ken Myer).</p>
<p>You can also reference a user account by using the user’s Active Directory distinguished name.</p>
<p>You can use the asterisk (*) wildcard character when using the Display Name as the user Identity. For example, the Identity &quot;* Smith&quot; returns all the users who have a display name that ends with the string value &quot; Smith&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command. To prevent a confirmation prompt from appearing each time you roll back a user account use this syntax:</p>
<p>-Confirm:$False</p></td>
</tr>
<tr class="odd">
<td><p><em>DomainController</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Enables you to connect to the specified domain controller in order to retrieve user information. To connect to a particular domain controller, include the DomainController parameter followed by the computer name (for example, atl-dc-001) or its fully qualified domain name (FQDN) (for example, atl-dc-001.litwareinc.com).</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to pass a user object through the pipeline that represents the user account being removed from the Unified Contact Store. By default, the <strong>Invoke-CsUcsRollback</strong> cmdlet does not pass objects through the pipeline.</p></td>
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

String value or Microsoft.Rtc.Management.ADConnect.Schema.ADUser object. The **Invoke-CsUcsRollback** cmdlet accepts pipelined input of string values representing the Identity of a user account. The cmdlet also accepts pipelined input of user objects.

## Return Types

None.

## 另请参阅

#### 其他资源

[New-CsUserServicesPolicy](new-csuserservicespolicy.md)  
[Set-CsUserServicesPolicy](set-csuserservicespolicy.md)  
[Test-CsUnifiedContactStore](test-csunifiedcontactstore.md)

