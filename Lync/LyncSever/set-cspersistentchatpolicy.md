---
title: Set-CsPersistentChatPolicy
TOCTitle: Set-CsPersistentChatPolicy
ms:assetid: b724bc13-d4fe-4529-9a48-e4cec8b7dce2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205192(v=OCS.15)
ms:contentKeyID: 49314018
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsPersistentChatPolicy

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing Persistent Chat policy. Persistent Chat policies determine whether or not users are allowed access to Persistent Chat chat rooms. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsPersistentChatPolicy [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsPersistentChatPolicy [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Description <String>] [-EnablePersistentChat <$true | $false>] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

In Example 1, Persistent Chat is enabled for the global Persistent Chat policy.

    Set-CsPersistentChatPolicy -Identity "global" -EnablePersistentChat $True

## Example 2

In Example 2, Persistent Chat is enabled for all the Persistent Chat policies in the organization. To do this, the command first uses the **Get-CsPersistentChatPolicy** cmdlet without any parameters in order to return a collection of all the Persistent Chat policies. This collection is then piped to the **Set-CsPersistentChatPolicy** cmdlet, which sets the EnablePersistentChat parameter for each policy in the collection to True ($True).

    Get-CsPersistentChatPolicy | Set-CsPersistentChatPolicy -EnablePersistentChat $True

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

By default, users are not granted access to the Persistent Chat service; that access can only be granted if the user is managed by a Persistent Chat policy that allows for the user of the service. When you install Lync 2013, all your users are managed by a global Persistent Chat policy in which the use of Persistent Chat is disabled. If you want to give all your users access to the service you can simply set the EnablePersistentChat property in this global policy to True. Alternatively, you can create additional policies at the site or at the per-user scope, and thus provide Persistent Chat access to some users while denying this access to other users.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsPersistentChatPolicy"}

**Lync Server 控制面板:** To modify an existing Persistent Chat policy using the Lync Server 控制面板, click **Persistent Chat**, click **Persistent Chat Policy**, then double-click the policy to be modified.

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
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables administrators to provide explanatory text to accompany the policy. For example, the Description might include information about the users the policy should be assigned to.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnablePersistentChat</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True users affected by the policy will be allowed to use Persistent Chat. When set to False (the default value) users affected by the policy will not be allowed to use Persistent Chat.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identity of the Persistent Chat policy to be modified. To modify the global policy, use this syntax:</p>
<p>-Identity global</p>
<p>To modify a site-scoped policy, use this syntax:</p>
<p>-Identity site:Redmond</p>
<p>To modify a per-user policy, use syntax similar to this:</p>
<p>-Identity RedmondPolicy</p>
<p>If you do not include the Identity parameter the <strong>Set-CsPersistentChatPolicy</strong> cmdlet will automatically modify the global policy.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
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

The **Set-CsPersistentChatPolicy** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Policy.PersistentChat.PersistentChatPolicy object.

## Return Types

None. Instead, the **Set-CsPersistentChatPolicy** cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Policy.PersistentChat.PersistentChatPolicy object.

## 另请参阅

#### 其他资源

[Get-CsPersistentChatPolicy](get-cspersistentchatpolicy.md)  
[Grant-CsPersistentChatPolicy](grant-cspersistentchatpolicy.md)  
[New-CsPersistentChatPolicy](new-cspersistentchatpolicy.md)  
[Remove-CsPersistentChatPolicy](remove-cspersistentchatpolicy.md)

