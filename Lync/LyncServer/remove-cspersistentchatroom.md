---
title: Remove-CsPersistentChatRoom
TOCTitle: Remove-CsPersistentChatRoom
ms:assetid: 04cadd5d-13dc-4de5-b0b5-8c2f9bbbc7a7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204639(v=OCS.15)
ms:contentKeyID: 49311854
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsPersistentChatRoom

 

_**上一次修改主题：** 2015-03-09_

Removes one or more Persistent Chat chat rooms. A chat room is a discussion forum that typically revolves around a specific topic. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Remove-CsPersistentChatRoom -Identity <String> <COMMON PARAMETERS>

    Remove-CsPersistentChatRoom -Instance <ChatRoom> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 removes the Persistent Chat chat room RedmondChatRoom.

    Remove-CsPersistentChatRoom -Identity "atl-gc-001.litwareinc.com\RedmondChatRoom"

## Example 2

In Example 2, all the Persistent Chat chat rooms in use in the organization are removed. To do this, the command first calls the **Get-CsPersistentChatRoom** cmdlet without any parameters in order to return a collection of all the available chat rooms. This collection is then piped to the **Remove-CsPersistentChatRoom** cmdlet, which deletes each room in the collection.

    Get-CsPersistentChatRoom  | Remove-CsPersistentChatRoom

## Example 3

Example 3 removes all the "closed" chat rooms. (A closed chat room means that any user can locate the chat room by doing a directory search, but only members can participate in chat room activities.) To accomplish this task, the command first uses the **Get-CsPersistentChatRoom** cmdlet and the Privacy parameter to return a collection of all the closed chat rooms. This collection is then piped to the **Remove-CsPersistentChatConfiguration** cmdlet, which deletes each room in the collection.

    Get-CsPersistentChatRoom -Privacy "Closed"  | Remove-CsPersistentChatRoom

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

Persistent Chat discussions take the form of messages posted in individual chat rooms; chat rooms are discussion forums based on specific topics. By design, messages posted in a chat room remain there forever; at any time, users can return to the room and review all the messages that have been previously posted.

The **Remove-CsPersistentChatRoom** cmdlet provides a way for administrators to remove one or more of the Persistent Chat chat rooms that have been configured for use in the organization.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsPersistentChatRoom"}

**Lync Server 控制面板:** To delete an existing Persistent Chat chat room using the Lync Server 控制面板, click **Persistent Chat**, click **Room**, and then select the room to be deleted. To delete the room, click **Edit**, and then click **Delete**.

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
<td><p>Unique Identifier for the Persistent Chat chat room being removed. The Identity for a chat room consists of the Persistent Chat pool where the room has been configured plus the name of the room; for example:</p>
<p>-Identity &quot;atl-gc-001.litwareinc.com\RedmondChatRoom&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Chat.Cmdlets.ChatRoom</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
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

The **Remove-CsPersistentChatRooms** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.PersistentChat.Cmdlets.ChatRoomObject object.

## Return Types

None. Instead, the **Remove-CsPersistentChatRoom** cmdlet deletes existing instances of the Microsoft.Rtc.Management.PersistentChat.Cmdlets.ChatRoomObject object.

## 另请参阅

#### 其他资源

[Clear-CsPersistentChatRoom](clear-cspersistentchatroom.md)  
[Get-CsPersistentChatRoom](get-cspersistentchatroom.md)  
[New-CsPersistentChatRoom](new-cspersistentchatroom.md)  
[Set-CsPersistentChatRoom](set-cspersistentchatroom.md)

