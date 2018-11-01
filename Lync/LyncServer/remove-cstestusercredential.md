﻿---
title: Remove-CsTestUserCredential
TOCTitle: Remove-CsTestUserCredential
ms:assetid: 49290251-276d-41d5-bcfd-077018d74f59
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204870(v=OCS.15)
ms:contentKeyID: 49312750
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsTestUserCredential

 

_**上一次修改主题：** 2015-03-09_

Removes the specified user from the set of users configured as watcher node test users. Watcher nodes are computers that periodically use Microsoft System Center Operations Manager and Lync Server 2013 synthetic transactions to verify that Lync Server components are working as expected. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Remove-CsTestUserCredential -SipAddress <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 removes the user with the SIP address sip:kenmyer@litwareinc.com from the collection of users configured as watcher node test users.

    Remove-CsTestUserCredential "sip:kenmyer@litwareinc.com"

## Example 2

The commands shown in Example 2 remove all the users who have configured as watcher node test users. (Note that this does not delete the user accounts; it merely deletes their status as watcher node test users.) To do this, the first command in the example sets the value of the Windows PowerShell $ErrorActionPreference variable to "SilentlyContinue"; this suppresses the display of an error message that would otherwise appear any time the **Remove-CsTestUserCredential** cmdlet tried to remove test credentials from user who has not been configured as a watcher node test user.

With error messages suppressed, the second command in the example uses the **Get-CsUser** cmdlet to return a collection of all the users who have been enabled for Lync Server 2013. This collection is then piped to the **ForEach-Object** cmdlet. The **ForEach-Object cmdlet** loops through each user account in the collection, running the **Remove-CsTestUserCredential** cmdlet against each account in order to remove that user as a watcher node test user.

The final command in the example resets the value of $ErrorActionPreference to "Continue".

    $ErrorActionPreference = "SilentlyContinue"
    
    Get-CsUser | ForEach-Object {Remove-CsTestUserCredential -SipAddress $_.SipAddress}
    
    $ErrorActionPreference = "Continue"

## Detailed Description

If you are using System Center Operations Manager in conjunction with Lync Server 2013, you have the option of configuring "watcher node" computers. Watcher nodes are computers that periodically (and automatically) run synthetic transactions. Synthetic transactions are cmdlets that test various features of Lync Server; for example, there are synthetic transactions that verify that users can register with Lync Server; that users can exchange instant messages and presence information using Lync Server; that users can conduct data collaboration and application sharing conferences; and that users can make phone calls across the public switched telephone network. As noted, these synthetic transactions run periodically and, if they fail, issue alerts notifying administrators that the system might be experiencing difficulties.

Many synthetic transactions require test users; for example, you cannot test the ability of two users to exchange instant messages unless you have a pair of user accounts and you attempt to exchange instant messages using those accounts. When you configure a watcher node you must assign at least two test users to that node. These test users can be any valid Active Directory user accounts that have been enabled for Lync Server 2013 and have been registered as test accounts. Accounts are registered as test accounts by using the [Set-CsTestUserCredential](set-cstestusercredential.md) cmdlet. If you later decide not to use an account as a test account you can unregister the by using the **Remove-CsTestUserCredential** cmdlet. This cmdlet simply prevents the account from being used as a watcher node test account; it does not delete, disable, or otherwise modify the account.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsTestUserCredential"}

**Lync Server 控制面板:** The functions carried out by the **Remove-CsTestUserCredential** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>SipAddress</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>SIP address of the account whose test user credentials are being removed. For example:</p>
<p>-SipAddress &quot;sip:kenmyer@litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
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

None. The **Remove-CsTestUserCredential** cmdlet does not accept pipelined input.

## Return Types

None. Instead, the **Remove-CsTestUserCredential** cmdlet deletes existing instances of the System.Management.Automation.PSCredential object.

## 另请参阅

#### 其他资源

[Get-CsTestUserCredential](get-cstestusercredential.md)  
[Set-CsTestUserCredential](set-cstestusercredential.md)

