---
title: Grant-CsPersistentChatPolicy
TOCTitle: Grant-CsPersistentChatPolicy
ms:assetid: 58889550-167a-4267-9f3d-0f244e898599
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204907(v=OCS.15)
ms:contentKeyID: 49312910
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Grant-CsPersistentChatPolicy

 

_**上一次修改主题：** 2015-03-09_

Assigns a per-user Persistent Chat policy to a user. Persistent Chat policies determine whether or not users are allowed access to Persistent Chat chat rooms. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Grant-CsPersistentChatPolicy -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-DomainController <Fqdn>] [-PassThru <SwitchParameter>] [-PolicyName <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 assigns the per-user policy RedmondUsersPersistentChatPolicy to the user with the Active Directory display name "Ken Myer".

    Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondUsersPersistentChatPolicy"

## Example 2

In Example 2, the per-user policy RedmondUsersPersistentChatPolicy is assigned to all the users who work in the IT department. To do this, the command first calls the **Get-CsUser** cmdlet along with the LdapFilter property; the filter value "Department=IT" limits the returned data to users who work in the IT department. That collection of users is then piped to the **Grant-CsPersistentChatPolicy** cmdlet, which assigns the policy RedmondUsersPersistentChatPolicy to each user in the collection.

    Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## Example 3

In Example 3, the per-user Persistent Chat policy RedmondUsersPersistentChatPolicy is assigned to all the users who do not currently have a per-user Persistent Chat policy assigned to them. To carry out this task, the command first employs the **Get-CsUser** cmdlet and the Filter parameter; the filter value {PersistentChatPolicy –eq $Null} limits the returned data to user accounts in which the PersistentChatPolicy property is currently null ($Null). That collection of users is then piped to the **Grant-CsPersistentChatPolicy** cmdlet, which assigns each user in the collection the policy RedmondUsersPersistentChatPolicy.

    Get-CsUser -Filter {PersistentChatPolicy -eq $Null} | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## Example 4

The command shown in Example 4 unassigns the per-user Persistent Chat policy RedmondUsersPersistentChatPolicy from any user currently assigned that policy. To carry out this task, the command first uses the **Get-CsUser** cmdlet and the Filter parameter to return a collection of users currently assigned the policy RedmondUsersPersistentChatPolicy; the filter value {PersistentChatPolicy –eq "RedmondUsersPersistentChatPolicy"} restricts the returned items to user accounts where the PersistentChatPolicy property is equal to RedmondUsersPersistentChatPolicy. That collection is then piped the **Grant-CsPersistentChatPolicy** cmdlet, which unassigns the per-user policy by setting the PersistentChatPolicy property to a null value ($Null).

After the per-user policy has been unassigned, users will have their Persistent Chat capabilities managed by their Persistent Chat site policy (if it exists) or, if not, by the global Persistent Chat policy.

    Get-CsUser -Filter {PersistentChatPolicy -eq "RedmondUsersPersistentChatPolicy"} | Grant-CsPersistentChatPolicy -PolicyName $Null

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

By default, users are not granted access to the Persistent Chat service; that access can only be granted if the user is managed by a Persistent Chat policy that allows for the user of the service. When you install Lync 2013, all your users are managed by a global Persistent Chat policy in which the use of Persistent Chat is disabled. If you want to give all your users access to the service you can simply set the EnablePersistentChat property in this global policy to True. Alternatively, you can create additional policies at the site or at the per-user scope, and thus provide Persistent Chat access to some users while denying this access to other users.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Grant-CsPersistentChatPolicy"}

**Lync Server 控制面板:** To assign a Persistent Chat policy to a user in the Lync Server 控制面板, double-click the appropriate user account. In the **Edit Lync Server User** dialog box, select a policy from the **Persistent Chat policy** dropdown list and then click **Commit**.

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
<td><p>Indicates the Identity of the user account to be assigned the per-user Persistent Chat policy. User Identities are typically specified using one of four formats: 1) the user's SIP address; 2) the user's user principal name (UPN); 3) the user's domain name and logon name, in the form domain\logon (four example, litwareinc\kenmyer); and, 4) the user's Active Directory display name (for example, Ken Myer). User Identities can also be specified by using the user’s Active Directory distinguished name.</p>
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
<td><p>Enables you to specify the fully qualified domain name of a domain controller to be contacted when assigning the new policy. If this parameter is not specified then the <strong>Grant-CsPersistentChatPolicy</strong> cmdlet will contact the first available domain controller.</p></td>
</tr>
<tr class="even">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to pass a user object through the pipeline that represents the user being assigned the policy. By default, the <strong>Grant-CsPersistentChatPolicy</strong> cmdlet does not pass objects through the pipeline.</p></td>
</tr>
<tr class="odd">
<td><p><em>PolicyName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>&quot;Name&quot; of the policy to be assigned. The PolicyName is simply the policy Identity minus the policy scope (the &quot;tag:&quot; prefix). For example, a policy with the Identity tag:Redmond has a PolicyName equal to Redmond; a policy with the Identity tag:RedmondUsersPersistentChatPolicy has a PolicyName equal to RedmondUsersPersistentChatPolicy. To unassign a per-user policy previously assigned to a user, set the PolicyName to a null value ($Null).</p></td>
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

String value or Microsoft.Rtc.Management.WritableConfig.Policy.PersistentChat.PersistentChatPolicy object. The **Grant-CsPersistentChatPolicy** cmdlet accepts pipelined input of string values representing the Identity of a user account. The cmdlet also accepts pipelined input of user objects.

## Return Types

By default, the **Grant-CsPersistentChatPolicy** cmdlet does not return an objects or values. However, if you include the PassThru parameter, the cmdlet will return instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSUserOrAppContact.

## 另请参阅

#### 其他资源

[Get-CsPersistentChatPolicy](get-cspersistentchatpolicy.md)  
[New-CsPersistentChatPolicy](new-cspersistentchatpolicy.md)  
[Remove-CsPersistentChatPolicy](remove-cspersistentchatpolicy.md)  
[Set-CsPersistentChatPolicy](set-cspersistentchatpolicy.md)

