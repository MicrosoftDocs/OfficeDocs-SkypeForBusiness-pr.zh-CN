---
title: New-CsPersistentChatCategory
TOCTitle: New-CsPersistentChatCategory
ms:assetid: 37a6f55d-0fec-480f-8d96-60c313a48c74
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204803(v=OCS.15)
ms:contentKeyID: 49312497
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsPersistentChatCategory

 

_**上一次修改主题：** 2015-03-09_

Creates a new Persistent Chat category. A Persistent Chat category represents a collection of Persistent Chat chat rooms. Each chat room must be associated with a category. Note that you cannot assign chat rooms to a category when you create that category. Instead, existing rooms must later be assigned to a category by using the **Set-CsPersistentChatRoom** cmdlet. However, new chat rooms can be assigned to the category at the same time the room is created. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    New-CsPersistentChatCategory -Name <String> [-Description <String>] [-EnableFileUpload <SwitchParameter>] [-EnableInvitations <SwitchParameter>] [-PersistentChatPoolFqdn <String>] [-RemoveChatHistory <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 creates a new Persistent Chat category named HelpDesk on the pool atl-cs-001.litwareinc.com. In this example, file upload is enabled (by including the parameter EnableFileUpload).

    New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com" -EnableFileUpload 

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

Persistent Chat categories provide a way for administrators to organize, and manage, Persistent Chat chat rooms. Categories provide a way for administrators to group related chat rooms; for example, all chat rooms used by the finance department can be grouped in the same category. Likewise, categories provide a way for administrators to manage permissions to these rooms, dictating which users are allowed access to the rooms, which users are denied access to the rooms, and which users are allowed to create new chat rooms within the category.

Note that all chat rooms must belong to a category; you cannot create a chat room without assigning that room to a category. That means that you must create at least one category before you can add any chat rooms to your Persistent Chat implementation.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsPersistentChatCategory"}

**Lync Server 控制面板:** To create a new Persistent Chat category using the Lync Server 控制面板, click **Persistent Chat**, click **Category**, and then click **New**.

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
<td><p><em>Name</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Name given to the Persistent Chat category. Names must be unique per Persistent Chat pool.</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Additional text accompanying the Persistent Chat category. For example, the Description might explain the purpose of the category and what type of rooms you can expect to find within the category.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableFileUpload</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, allows file uploads to the chat rooms in the category.</p></td>
</tr>
<tr class="even">
<td><p><em>EnableInvitations</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When this parameter is included, Invitations will be enabled for the category. Among other things, this means that users on the AllowedMembers list will automatically receive an invitation to join a new chat room at the time that new room is created.</p></td>
</tr>
<tr class="odd">
<td><p><em>PersistentChatPoolFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name of the Persistent Chat pool where the category should be created.</p></td>
</tr>
<tr class="even">
<td><p><em>RemoveChatHistory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When this parameter is included, the chat history feature will be disabled for the new category. Typically, chat history is only disabled for chat rooms that are used for announcements that are posted once and then never need to be referred to again.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsPersistentChatCategory** cmdlet does not accept pipelined input.

## Return Types

The **New-CsPersistentChatCategory** cmdlet creates new instances of the Microsoft.Rtc.Management.PersistentChat.Cmdlets.CategoryObject object.

## 另请参阅

#### 其他资源

[Get-CsPersistentChatCategory](get-cspersistentchatcategory.md)  
[Remove-CsPersistentChatCategory](remove-cspersistentchatcategory.md)  
[Set-CsPersistentChatCategory](set-cspersistentchatcategory.md)

