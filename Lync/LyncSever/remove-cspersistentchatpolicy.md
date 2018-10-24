---
title: Remove-CsPersistentChatPolicy
TOCTitle: Remove-CsPersistentChatPolicy
ms:assetid: d6bfe22b-084b-4d7f-8e4a-58f738493b31
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205301(v=OCS.15)
ms:contentKeyID: 49314397
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsPersistentChatPolicy

 

_**上一次修改主题：** 2015-03-09_

Removes an existing Persistent Chat policy. Persistent Chat policies determine whether or not users are allowed access to Persistent Chat chat rooms. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Remove-CsPersistentChatPolicy -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 removes the per-user Persistent Chat policy with the Identity RedmondPersistentChatPolicy.

    Remove-CsPersistentChatPolicy -Identity "RedmondPersistentChatPolicy"

## Example 2

In Example 2, all the Persistent Chat policies applied to the site scope are deleted. To do this, the command first uses the **Get-CsPersistentChatPolicy** cmdlet and the Filter parameter to return all the Persistent Chat policies configured at the site scope. (This is done by using the filter value "site:\*".) These policies are then piped to, and deleted by, the **Remove-CsPersistentChatPolicy** cmdlet.

    Get-CsPersistentChatPolicy -Filter "site:*" | Remove-CsPersistentChatPolicy

## Example 3

In Example 3, all the Persistent Chat policies in which Persistent Chat is enabled are deleted. To carry out this task, the command first calls the **Get-CsPersistentChatPolicy** cmdlet without any parameters; this returns a collection of all the Persistent Chat policies configured for use in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those policies where the EnablePersistentChat property is equal to true ($True). That collection is then piped to the **Remove-CsPersistentChatPolicy** cmdlet, which deletes each policy in the collection.

    Get-CsPersistentChatPolicy | Where-Object {$_.EnablePersistentChat -eq $True} | Remove-CsPersistentChatPolicy

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

By default, users are not granted access to the Persistent Chat service; that access can only be granted if the user is managed by a Persistent Chat policy that allows for the user of the service. When you install Lync 2013, all your users are managed by a global Persistent Chat policy in which the use of Persistent Chat is disabled. If you want to give all your users access to the service you can simply set the EnablePersistentChat property in this global policy to True. Alternatively, you can create additional policies at the site or at the per-user scope, and thus provide Persistent Chat access to some users while denying this access to other users.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsPersistentChatPolicy"}

**Lync Server 控制面板:** To remove a Persistent Chat policy using the Lync Server 控制面板, click **Persistent Chat** and then click **Persistent Chat Policy**. Select the policy to be removed, click **Edit**, and then click **Delete**.

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
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identity of the Persistent Chat policy to be deleted. To remove a site-scoped policy, use syntax similar to this:</p>
<p>-Identity site:Redmond</p>
<p>To delete per-user policy, use syntax similar to this:</p>
<p>-Identity RedmondPolicy</p>
<p>The <strong>Remove-CsPersistentChatPolicy</strong> cmdlet can also be run against the global Persistent Chat policy. In that case, however, the global policy will not actually be deleted. Instead, all the properties in the global policy will be reset to their default values.</p></td>
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
<td><p>If present, causes the <strong>Remove-CsPersistentChatPolicy</strong> cmdlet to delete the per-user policy even if the policy is currently assigned to at least one user. If not present, you will be asked to confirm the deletion request before a policy still in use will be removed.</p></td>
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

The **Remove-CsPersistentChatPolicy** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Policy.PersistentChat.PersistentChatPolicy object.

## Return Types

None. Instead, the **Remove-CsPersistentChatPolicy** cmdlet deletes existing instances of the Microsoft.Rtc.Management.WritableConfig.Policy.PersistentChat.PersistentChatPolicy object.

## 另请参阅

#### 其他资源

[Get-CsPersistentChatPolicy](get-cspersistentchatpolicy.md)  
[Grant-CsPersistentChatPolicy](grant-cspersistentchatpolicy.md)  
[New-CsPersistentChatPolicy](new-cspersistentchatpolicy.md)  
[Set-CsPersistentChatPolicy](set-cspersistentchatpolicy.md)

