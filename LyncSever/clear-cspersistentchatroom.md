---
title: Clear-CsPersistentChatRoom
TOCTitle: Clear-CsPersistentChatRoom
ms:assetid: 6b7801d8-d924-4e97-9b17-ceb6a263a7a7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204976(v=OCS.15)
ms:contentKeyID: 49313162
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Clear-CsPersistentChatRoom

 

_**上一次修改主题：** 2015-03-09_

Removes all the content from a Persistent Chat chat room beginning with the oldest item in the room and continuing through the specified end date. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Clear-CsPersistentChatRoom -Identity <String> <COMMON PARAMETERS>

    Clear-CsPersistentChatRoom -Instance <ChatRoom> <COMMON PARAMETERS>

    COMMON PARAMETERS: -EndDate <DateTime> [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example removes all the content from the Persistent Chat chat room ITChatRoom that was added to the room on or before March 1, 2012.

    Clear-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -EndDate "3/1/2012"

## Example 2

In Example 2, content added on or before March 1, 2012 is removed from all the chat rooms in the organization. To do this, the command first calls the **Get-CsPersistentChatRoom** cmdlet without any parameters in order to return a collection of all the chat rooms in the organization. That collection is then piped to the **Clear-CsPersistentChatRoom** cmdlet, which removes content added on or before March 1, 2012 from each room in the collection. Note that, in order to suppress the confirmation prompt which would otherwise appear each time you tried to clear a different chat room, the Confirm parameter is added using this syntax:

\-Confirm:$False

    Get-CsPersistentChatRoom | Clear-CsPersistentChatRoom -EndDate "3/1/2012" -Confirm:$False

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

Persistent Chat discussions take the form of messages posted in individual chat rooms; chat rooms are discussion forums based on specific topics. By design, messages posted in a chat room remain there forever; at any time, users can return to the room and review all the messages that have been previously posted.

However, there might be times when administrators need to clear a chat room of all (or at least some) of its messages; this might done to free up space in the database or because the chat room is changing its focus. Regardless, the **Clear-CsPersistentChatRoom** cmdlet provides a way for you to delete all the messages in a chat room or to delete all the message posted during a specified period of time (for example, all the messages posted before August 1, 2012).

**Note**. To remove a more finely-targeted set of messages (for example, all the messages posted by a specific user) use the [Remove-CsPersistentChatMessage](remove-cspersistentchatmessage.md) cmdlet.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Clear-CsPersistentChatRoom"}

**Lync Server 控制面板:** The functions carried out by the **Clear-CsPersistentChatRoom** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>EndDate</em></p></td>
<td><p>Required</p></td>
<td><p>System.DateTime</p></td>
<td><p>Indicates the last date for which content should be removed. For example, if you specify an EndDate of 3/1/2012 (March 1, 2012 in US English) then all the Persistent Chat content added to the room on or before 3/1/2012 will be deleted.</p>
<p>You must specify an EndDate when running the <strong>Clear-CsPersistentChatRoom</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Identity of the chat room whose content is to be removed. For example:</p>
<p>-Identity &quot;atl-cs-001.litwareinc.com\ITChatRoom&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Chat.Cmdlets.ChatRoom</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command. If you set the value of this parameter to False then you will not get a confirmation prompt when you run the cmdlet:</p>
<p>-Confirm:$False</p></td>
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

The **Clear-CsPersistentChatRoom** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.GroupChat.Cmdlets.ChatRoomObject object.

## Return Types

None.

## 另请参阅

#### 其他资源

[Remove-CsPersistentChatMessage](remove-cspersistentchatmessage.md)

