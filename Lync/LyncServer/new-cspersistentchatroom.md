---
title: New-CsPersistentChatRoom
TOCTitle: New-CsPersistentChatRoom
ms:assetid: b00d353b-5b5b-40d6-b952-3c35170fbf8a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205166(v=OCS.15)
ms:contentKeyID: 49313937
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsPersistentChatRoom

 

_**上一次修改主题：** 2015-03-09_

Creates a new Persistent Chat chat room. A chat room is a discussion forum that typically revolves around a specific topic. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    New-CsPersistentChatRoom -Category <String> -Name <String> [-Addin <String>] [-Description <String>] [-Disabled <$true | $false>] [-Invitations <False | Inherit>] [-PersistentChatPoolFqdn <String>] [-Privacy <Open | Closed | Secret>] [-Type <Normal | Auditorium>]

## Examples

## Example 1

The command shown in Example 1 creates a new Persistent Chat chat room named ITChatRoom on the pool atl-cs-001.litwareinc.com. In this example, the chat room is added to the IT category.

    New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com"-Category "IT"

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

Persistent Chat discussions take the form of messages posted in individual chat rooms; chat rooms are discussion forums based on specific topics. By design, messages posted in a chat room remain there forever; at any time, users can return to the room and review all the messages that have been previously posted.

The **New-CsPersistentChatRoom** cmdlet enables administrators to create new Persistent Chat chat rooms. Note that not all the properties of a chat room are available using the **New-CsPersistentChatRoom** cmdlet; for example, you cannot assign chat room Managers or Presenters by using this cmdlet. To assign Managers or Presenters, you must create the chat room, then make those assignments using the [Set-CsPersistentChatRoom](set-cspersistentchatroom.md) cmdlet.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsPersistentChatRoom"}

**Lync Server 控制面板:** To create a new Persistent Chat chat room using the Lync Server 控制面板, click **Persistent Chat**, click **Room**, and then click **New**.

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
<td><p><em>Category</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Category under which the room is to be created; for example:</p>
<p>-Category &quot;IT&quot;</p>
<p>Note that the specified category must already exist or the command will fail. Categories, which are collections of Persistent Chat chat rooms, can be created by using the <strong>New-CsPersistentChatCategory</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>Name</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Name of the new Persistent Chat chat room. Names must be unique per Persistent Chat pool.</p></td>
</tr>
<tr class="odd">
<td><p><em>Addin</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Name of the Persistent Chat add-in, if any, associated with the chat room. A Persistent Chat add-in is a customized web page that can be embedded within a Persistent Chat client. Add-ins can be created by using the <strong>New-CsPersistentChatAddin</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables administrators to provide additional information about the new chat room</p></td>
</tr>
<tr class="odd">
<td><p><em>Disabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When present, the new chat room will be disabled and unavailable for use when it is first created. If this parameter is not used then the new chat room will be enabled and available for immediate use.</p></td>
</tr>
<tr class="even">
<td><p><em>Invitations</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Chat.Cmdlets.ChatRoomInvitations</p></td>
<td><p>Specifies whether or not Invitations for the new chat room will be inherited from the category. Among other things, this means that users on the AllowedMembers list will automatically receive an invitation to join a new chat room at the time that new room is created.</p></td>
</tr>
<tr class="odd">
<td><p><em>PersistentChatPoolFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name of the Persistent Chat pool where the new chat room will be located. For example:</p>
<p>-PersistentChatPoolFqdn &quot;atl-gc-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Privacy</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Chat.Cmdlets.ChatRoomPrivacy</p></td>
<td><p>Privacy settings for the new chat room. Allowed values are:</p>
<p>* Open (any user can locate the chat room by doing a directory search, and anyone can participate in chat room activities)</p>
<p>* Secret (only chat room members can locate the room by doing a directory search, and only members can participate in chat room activities)</p>
<p>* Closed (any user can locate the chat room by doing a directory search, but only members can participate in chat room activities)</p></td>
</tr>
<tr class="odd">
<td><p><em>Type</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Chat.Cmdlets.ChatRoomType</p></td>
<td><p>Specifies whether the new chat room should be configured as a Normal chat room (where all members can post messages) or an Auditorium (where only presenters can post messages). For example:</p>
<p>-Type &quot;Auditorium&quot;</p>
<p>The default value is Normal.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsPersistentChatRoom** cmdlet does not accept pipelined input.

## Return Types

The **New-CsPersistentChatRoom** cmdlet creates new instances of the Microsoft.Rtc.Management.PersistentChat.Cmdlets.ChatRoomObject object.

## 另请参阅

#### 其他资源

[Clear-CsPersistentChatRoom](clear-cspersistentchatroom.md)  
[Get-CsPersistentChatRoom](get-cspersistentchatroom.md)  
[Remove-CsPersistentChatRoom](remove-cspersistentchatroom.md)  
[Set-CsPersistentChatRoom](set-cspersistentchatroom.md)

