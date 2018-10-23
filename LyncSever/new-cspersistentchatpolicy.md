---
title: New-CsPersistentChatPolicy
TOCTitle: New-CsPersistentChatPolicy
ms:assetid: f7d42a24-598a-4ea3-8a0f-25575b5235ea
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205396(v=OCS.15)
ms:contentKeyID: 49314791
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsPersistentChatPolicy

 

_**上一次修改主题：** 2015-03-09_

Creates a new Persistent Chat policy at the site or the per-user scope. Persistent Chat policies determine whether or not users are allowed access to Persistent Chat chat rooms. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    New-CsPersistentChatPolicy -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Description <String>] [-EnablePersistentChat <$true | $false>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 creates a new per-user Persistent Chat policy with the Identity RedmondPersistentChatPolicy. In this example, Persistent Chat is enabled by using the parameter EnablePersistentChat and the parameter value $True.

    New-CsPersistentChatPolicy -Identity "RedmondPersistentChatPolicy" -EnablePersistentChat $True

## Example 2

Example 2 is a variation of the command shown in Example 1; the only difference is that the new policy is applied to the site scope instead of the per-user scope. That's done by setting the Identity to the string value "site:" followed by the name of the site itself; in this case, site:Redmond.

    New-CsPersistentChatPolicy -Identity "site:Redmond" -EnablePersistentChat $True

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

By default, users are not granted access to the Persistent Chat service; that access can only be granted if the user is managed by a Persistent Chat policy that allows for the user of the service. When you install Lync 2013, all your users are managed by a global Persistent Chat policy in which the use of Persistent Chat is disabled. If you want to give all your users access to the service you can simply set the EnablePersistentChat property in this global policy to True. Alternatively, you can create additional policies at the site or at the per-user scope, and thus provide Persistent Chat access to some users while denying this access to other users.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsPersistentChatPolicy"}

**Lync Server 控制面板:** To create a new Persistent Chat policy using the Lync Server 控制面板, click **Persistent Chat**, click **Persistent Chat Policy**, click **New**, and then click either **Site policy** or **User policy**.

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
<td><p>Unique identifier to be assigned to the policy. New Persistent Chat policies can be created at the site scope or the per-user scope. To create a new site policy, use the prefix &quot;site:&quot; and the name of the site as your Identity. For example, use this syntax to create a new policy for the Redmond site:</p>
<p>-Identity site:Redmond</p>
<p>To create a new per-user policy, use an Identity similar to this:</p>
<p>-Identity SalesPersistentChatPolicy</p>
<p>Note that you cannot create a new global policy; if you want to make changes to the global policy, use the <strong>Set-CsPersistentChatPolicy</strong> cmdlet instead. Likewise, you cannot create a new site or per-user policy if a policy with that Identity already exists. If you need to make changes to an existing policy, use the <strong>Set-CsPersistentChatPolicy</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables administrators to provide explanatory text to accompany the policy. For example, the Description might include information about the users the policy should be assigned to.</p></td>
</tr>
<tr class="even">
<td><p><em>EnablePersistentChat</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True, users affected by the policy will be allowed to use Persistent Chat. When set to False (the default value) users affected by the policy will not be allowed to use Persistent Chat.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Creates an object reference without actually committing the object as a permanent change. If you assign the output of this cmdlet called with this parameter to a variable, you can make changes to the properties of the object reference and then commit those changes by calling this cmdlet’s matching Set- cmdlet.</p></td>
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

None. The **New-CsPersistentChatPolicy** cmdlet does not accept pipelined input.

## Return Types

The **New-CsPersistentChatPolicy** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Policy.PersistentChat.PersistentChatPolicy object.

## 另请参阅

#### 其他资源

[Get-CsPersistentChatPolicy](get-cspersistentchatpolicy.md)  
[Grant-CsPersistentChatPolicy](grant-cspersistentchatpolicy.md)  
[Remove-CsPersistentChatPolicy](remove-cspersistentchatpolicy.md)  
[Set-CsPersistentChatPolicy](set-cspersistentchatpolicy.md)

