---
title: Set-CsPersistentChatCategory
TOCTitle: Set-CsPersistentChatCategory
ms:assetid: 61f44b61-c1bb-46a8-af12-8d1c543fcda5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204952(v=OCS.15)
ms:contentKeyID: 49313033
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsPersistentChatCategory

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing Persistent Chat category. A Persistent Chat category represents a collection of Persistent Chat chat rooms. Each chat room must be associated with a category. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsPersistentChatCategory -Instance <Category> <COMMON PARAMETERS>

    Set-CsPersistentChatCategory -Identity <String> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AllowedMembers <PSListModifier>] [-AsObject <SwitchParameter>] [-ChatHistory <$true | $false>] [-Confirm [<SwitchParameter>]] [-Creators <PSListModifier>] [-DeniedMembers <PSListModifier>] [-Description <String>] [-FileUpload <$true | $false>] [-Invitations <$true | $false>] [-Name <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

In Example 1, file uploads are disabled for the Persistent Chat category atl-cs-001.litwareinc.com\\helpdesk.

    Set-CsPersistentChatCategory -Identity "atl-cs-001.litwareinc.com\helpdesk" -FileUpload $False

## Example 2

Example 2 disables file uploads for all the Persistent Chat categories currently in use in the organization. To carry out this task, the command first calls the **Get-CsPersistentChatCategory** cmdlet without any parameters in order to return a collection of all the Persistent Chat categories. The categories in this collection are then piped to the **Set-CsPersistentChatCategory** cmdlet to disable file uploads for each category.

    Get-CsPersistentChatCategory | Set-CsPersistentChatCategory-FileUpload $False

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

Persistent Chat categories provide a way for administrators to organize, and manage, Persistent Chat chat rooms. Categories provide a way for administrators to group related chat rooms; for example, all chat rooms used by the finance department can be grouped in the same category. Likewise, categories provide a way for administrators to manage permissions to these rooms, dictating which users are allowed access to the rooms, which users are denied access to the rooms, and which users are allowed to create new chat rooms within the category.

Note that all chat rooms must belong to a category; you cannot create a chat room without assigning that room to a category. That means that you must create at least one category before you can add any chat rooms to your Persistent Chat implementation.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsPersistentChatCategory"}

**Lync Server 控制面板:** To modify an existing Persistent Chat category using the Lync Server 控制面板, click **Persistent Chat**, click **Category**, then double-click the category to be modified.

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
<td><p>Unique identifier for the chat room category. The Identity consists of the Persistent Chat pool were the category is located followed by the category Name; for example:</p>
<p>-Identity &quot;atl-gc-001.litwareinc.com\ITChat&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Chat.Cmdlets.Category</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
</tr>
<tr class="odd">
<td><p><em>AllowedMembers</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Lists the users who are allowed to access chat rooms within the category. To add a new user to the Members list, use syntax similar to this:</p>
<p>-Members @{Add=&quot;sip:kenmyer@litwareinc.com&quot;}</p>
<p>Multiple users can be added by separating the user SIP addresses with commas:</p>
<p>-Members @{Add=&quot;sip:kenmyer@litwareinc.com&quot;, &quot;sip:pilar@litwareinc.com&quot;}</p>
<p>To remove a user from the Members list use the Remove method:</p>
<p>-Members @{Remove=&quot;sip:kenmyer@litwareinc.com&quot;}</p>
<p>To remove all the users from the Members list, set the value of the Members property to null:</p>
<p>-AllowedMembers $Null</p>
<p>In addition to working with individual users you can also work with entire OUs. For example, this command enables all the users in the IT OU to access chat rooms:</p>
<p>-Members @{Add=&quot;OU=IT,DC=litwareinc,DC=com&quot;}</p>
<p>To add all the users in a distribution list, use the Active Directory distinguished name of that distribution list:</p>
<p>-Members @{Add=&quot;CN=ChatSupportGroup,OU=IT,DC=litwareinc,DC=com&quot;}</p></td>
</tr>
<tr class="even">
<td><p><em>AsObject</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When specified, Active Directory display names are used when adding users to or removing users from the AllowedMembers, DeniedMembers, and Creators lists. When not specified, SIP addresses are used when managing these lists.</p></td>
</tr>
<tr class="odd">
<td><p><em>ChatHistory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set the False ($False), the chat history feature will be disabled for the new category. Typically, chat history is only disabled for chat rooms that are used for announcements that are posted once and then never need to be referred to again.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Creators</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Lists the users who are allowed to create chat rooms within the category. To add a new user to the Creators list, use syntax similar to this:</p>
<p>-Creators @{Add=&quot;sip:kenmyer@litwareinc.com&quot;}</p>
<p>Multiple users can be added by separating the user SIP addresses with commas:</p>
<p>-Creators @{Add=&quot;sip:kenmyer@litwareinc.com&quot;, &quot;sip:pilar@litwareinc.com&quot;}</p>
<p>To remove a user from the Creators list use the Remove method:</p>
<p>-Creators @{Remove=&quot;sip:kenmyer@litwareinc.com&quot;}</p>
<p>To remove all the users from the Creators list, set the value of the Creators property to null:</p>
<p>-Creators $Null</p>
<p>In addition to working with individual users you can also work with entire OUs. For example, this command enables all the users in the IT OU to create chat rooms:</p>
<p>-Creators @{Add=&quot;OU=IT,DC=litwareinc,DC=com&quot;}</p>
<p>To add all the users in a distribution list, use the Active Directory distinguished name of that distribution list:</p>
<p>-Creators @{Add=&quot;CN=ChatSupportGroup.OU=IT,DC=litwareinc,DC=com&quot;}</p></td>
</tr>
<tr class="even">
<td><p><em>DeniedMembers</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Lists the users who are not allowed to access chat rooms within the category. To add a new user to the DeniedMembers list, use syntax similar to this:</p>
<p>-DeniedMembers @{Add=&quot;sip:kenmyer@litwareinc.com&quot;}</p>
<p>Multiple users can be added by separating the user SIP addresses with commas:</p>
<p>-DeniedMembers @{Add=&quot;sip:kenmyer@litwareinc.com&quot;, &quot;sip:pilar@litwareinc.com&quot;}</p>
<p>To remove a user from the DeniedMembers list use the Remove method:</p>
<p>-DeniedMembers @{Remove=&quot;sip:kenmyer@litwareinc.com&quot;}</p>
<p>To remove all the users from the DeniedMembers list, set the value of the DeniedMembers property to null:</p>
<p>-DeniedMembers $Null</p>
<p>In addition to working with individual users you can also work with entire OUs. For example, this command denies chat room access to all the users in the IT OUs:</p>
<p>-DeniedMembers @{Add=&quot;OU=IT,DC=litwareinc,DC=com&quot;}</p>
<p>To deny access to all the users in a distribution list, use the Active Directory distinguished name of that distribution list:</p>
<p>-DeniedMembers @{Add=&quot;CN=ChatSupportGroup.OU=IT,DC=litwareinc,DC=com&quot;}</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Additional text accompanying the Persistent Chat category. For example, the Description might explain the purpose of the category and what type of rooms you can expect to find within the category.</p></td>
</tr>
<tr class="even">
<td><p><em>FileUpload</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True ($True), allows file uploads to the chat rooms in the category.</p></td>
</tr>
<tr class="odd">
<td><p><em>Invitations</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to False ($False), Invitations will be enabled for the category. Among other things, this means that users on the AllowedMembers list will automatically receive an invitation to join a new chat room at the time that new room is created.</p></td>
</tr>
<tr class="even">
<td><p><em>Name</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Name given to the Persistent Chat category. Names must be unique per Persistent Chat pool.</p></td>
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

The **Set-CsPersistentChatCategory** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.PersistentChat.Cmdlets.CategoryObject object.

## Return Types

None. Instead, the **Set-CsPersistentChatCategory** cmdlet modifies existing instances of the Microsoft.Rtc.Management.PersistentChat.Cmdlets.CategoryObject object.

## 另请参阅

#### 其他资源

[Get-CsPersistentChatCategory](get-cspersistentchatcategory.md)  
[New-CsPersistentChatCategory](new-cspersistentchatcategory.md)  
[Remove-CsPersistentChatCategory](remove-cspersistentchatcategory.md)

