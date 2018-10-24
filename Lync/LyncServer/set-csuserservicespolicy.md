﻿---
title: Set-CsUserServicesPolicy
TOCTitle: Set-CsUserServicesPolicy
ms:assetid: fbe18ddf-5094-4d8b-ad27-75b73173b8c4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205414(v=OCS.15)
ms:contentKeyID: 49314832
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsUserServicesPolicy

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing User Services policy. User Services policies determine whether or not a user's contacts are stored in Lync Server 2013 or in the Unified Contact Store. The Unified Contact Store provides a way for users to maintain a single set of contacts that can be accessed using Lync 2013, Outlook, and/or Outlook Web Access. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsUserServicesPolicy [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsUserServicesPolicy [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Tenant <Guid>] [-UcsAllowed <$true | $false>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 disables the use of the Unified Contact Store for the per-user User Services policy RedmondUserServicesPolicy. This means that users managed by this policy will not have their contacts stored in the Unified Contact Store.

    Set-CsUserServicesPolicy -Identity "RedmondUserServicesPolicy" -UcsAllowed $False

## Example 2

In Example 2, all the User Services policies configured at the site scope are modified to disable the use of the Unified Contact Store. To do this, the command first calls the **Get-CsUserServicesPolicy** cmdlet and the Filter parameter to return a collection of all the policies configured at the site scope. This collection is then piped to the **Set-CsUserServicesPolicy** cmdlet, which takes each policy in the collection and sets the UcsAllowed property to False ($False).

    Get-CsUserServicesPolicy -Filter "site:*" | Set-CsUserServicesPolicy -UcsAllowed $False

## Detailed Description

The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server; in turn that allows the user to access the same set of contacts in Outlook and Outlook Web Access as well as in Lync 2013. (Alternatively, you can continue to store contacts in Lync Server 2013. In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)

In order to take advantage of the unified contact store you must (among other things) assign the user a user services policy that enables the use of the unified contact store. User service policies (which can be configured at the global, site, or the per-user scope) contain only a single property: UcsAllowed. When this property is set to True then (assuming all the other prerequisites have been met) the next time a user logs on to Lync Server 2013 his or her contacts will automatically be migrated to the unified contact store.

If this property is set to False this automatic migration will not take place. However, simply setting UcsAllowed will not cause a user's contacts to be moved from the unified contact store back to Lync Server. In order to do that, you must first assign the user a user services policy that does not allow the use of the unified contact store. After that, you must then use the **Invoke-CsUcsRollback** cmdlet to "manually" migrate the contacts from the unified contact store back to Lync Server.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsUserServicesPolicy"}

**Lync Server 控制面板:** The functions carried out by the **Set-CsUserServicesPolicy** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command. Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the policy to be modified. To modify the global policy, use this syntax:</p>
<p>-Identity &quot;global&quot;</p>
<p>To modify a policy configured at the site scope, use syntax similar to this:</p>
<p>-Identity &quot;site:Redmond&quot;</p>
<p>To modify a policy configured at the service scope, use syntax similar to this:</p>
<p>-Identity &quot;UserServer:atl-cs-001.litwareinc.com&quot;</p>
<p>Note that the UserServer service is the only service that can host a user services policy.</p>
<p>If this parameter is not included then the <strong>Set-CsUserServicesPolicy</strong> cmdlet will automatically modify the global policy.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
</tr>
<tr class="odd">
<td><p><em>Tenant</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Guid</p></td>
<td><p>Globally unique identifier (GUID) of the Skype for Business Online tenant account for which the user services policy being modified. For example:</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>You can return the tenant ID for each of your tenants by running this command:</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
</tr>
<tr class="even">
<td><p><em>UcsAllowed</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True (the default value) users affected by the policy will automatically be migrated to the unified contact store (assuming that they have an account on Microsoft Exchange Server 2013 and that they log on using Lync 2013). When set to False, users can be removed from the unified contact store, but only if they are &quot;manually&quot; removed by the <strong>Invoke-CsUcsRollback</strong> cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Set-CsUserServicesPolicy** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Policy.UserServices.UserServicesPolicy object.

## Return Types

None. Instead, the **Set-CsUserServicesPolicy** cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Policy.UserServices.UserServicesPolicy object.

## 另请参阅

#### 其他资源

[Get-CsUserServicesPolicy](get-csuserservicespolicy.md)  
[Grant-CsUserServicesPolicy](grant-csuserservicespolicy.md)  
[New-CsUserServicesPolicy](new-csuserservicespolicy.md)  
[Remove-CsUserServicesPolicy](remove-csuserservicespolicy.md)

