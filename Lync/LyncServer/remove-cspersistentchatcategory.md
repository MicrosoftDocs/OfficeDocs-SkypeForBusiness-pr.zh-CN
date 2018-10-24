---
title: Remove-CsPersistentChatCategory
TOCTitle: Remove-CsPersistentChatCategory
ms:assetid: 09d2c1e6-07b6-47c2-b48f-f0c8bdfa1507
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204660(v=OCS.15)
ms:contentKeyID: 49311940
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsPersistentChatCategory

 

_**上一次修改主题：** 2015-03-09_

Removes an existing Persistent Chat category. A Persistent Chat category represents a collection of Persistent Chat chat rooms, and each chat room must be associated with a category. 此 cmdlet 是在 Lync Server 2013 中引入的。 Note that categories cannot be removed unless they are empty (that is, all the rooms within that category must be removed before you can remove the category).

## 语法

    Remove-CsPersistentChatCategory -Identity <String> <COMMON PARAMETERS>

    Remove-CsPersistentChatCategory -Instance <Category> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 removes the Persistent Chat category that has the Identity "atl-cs-001.litwareinc.com\\helpdesk".

    Remove-CsPersistentChatCategory -Identity "atl-cs-001.litwareinc.com\helpdesk"

## Example 2

In Example 2, all the Persistent Chat categories currently in use in the organization are removed. To do this, the command first uses the **Get-CsPersistentChatCategory** cmdlet to retrieve a collection of all the Persistent Chat categories. This collection is piped to the **Remove-CsPersistentChatCategory** cmdlet, which then deletes each category in the collection.

    Get-CsPersistentChatCategory | Remove-CsPersistentChatCategory

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

Persistent Chat categories provide a way for administrators to organize, and manage, Persistent Chat chat rooms. Categories provide a way for administrators to group related chat rooms; for example, all chat rooms used by the finance department can be grouped in the same category. Likewise, categories provide a way for administrators to manage permissions to these rooms, dictating which users are allowed access to the rooms, which users are denied access to the rooms, and which users are allowed to create new chat rooms within the category.

Note that all chat rooms must belong to a category; you cannot create a chat room without assigning that room to a category. That means that you must create at least one category before you can add any chat rooms to your Persistent Chat implementation.

The **Remove-CsPersistentChatCategory** cmdlet provides a way to remove Persistent Chat categories. Keep in mind that categories cannot be removed unless they are empty. That means that all the rooms within that category must be removed before you can remove the category itself.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsPersistentChatCategory"}

**Lync Server 控制面板:** To remove a Persistent Chat category using the Lync Server 控制面板, click **Persistent Chat** and then click **Category**. Select the category to be removed, click **Edit** and then click **Delete**.

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
<td><p>System.String</p></td>
<td><p>Unique identifier for the Persistent Chat category to be removed. An Identity consists of the PoolFqdn plus the category Name; for example:</p>
<p>-Identity &quot;atl-cs-001.litwareinc.com\helpdesk&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Chat.Cmdlets.Category</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
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

The **Remove-CsPersistentChatCategory** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.PersistentChat.Cmdlets.CategoryObject object. The cmdlet will also accept string values representing the Identity of an existing Persistent Chat category.

## Return Types

None. Instead, the **Remove-CsPersistentChatCategory** cmdlet deletes existing instances of the Microsoft.Rtc.Management.PersistentChat.Cmdlets.CategoryObject object.

## 另请参阅

#### 其他资源

[Get-CsPersistentChatCategory](get-cspersistentchatcategory.md)  
[New-CsPersistentChatCategory](new-cspersistentchatcategory.md)  
[Set-CsPersistentChatCategory](set-cspersistentchatcategory.md)

