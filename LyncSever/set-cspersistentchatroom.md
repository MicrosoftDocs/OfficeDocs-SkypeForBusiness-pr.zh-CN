---
title: Set-CsPersistentChatRoom
TOCTitle: Set-CsPersistentChatRoom
ms:assetid: 3774931e-74a9-4189-9dde-3baae2293138
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204801(v=OCS.15)
ms:contentKeyID: 49312490
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsPersistentChatRoom

 

_**上一次修改主题：** 2015-03-09_

Modifies and existing Persistent Chat chat room. A chat room is a discussion forum that typically revolves around a specific topic. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsPersistentChatRoom -Instance <ChatRoom> <COMMON PARAMETERS>

    Set-CsPersistentChatRoom -Identity <String> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Addin <String>] [-AsObject <SwitchParameter>] [-Category <String>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-Disabled <$true | $false>] [-Force <SwitchParameter>] [-Invitations <False | Inherit>] [-Managers <PSListModifier>] [-Members <PSListModifier>] [-Name <String>] [-Presenters <PSListModifier>] [-Privacy <Open | Closed | Secret>] [-Type <Normal | Auditorium>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 disables the Persistent Chat chat room with the Identity atl-cs-001.litwareinc.com\\ITChatRoom.

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

## Example 2

In Example 2, all the Persistent Chat chat rooms on the pool atl-cs-001.litwareinc.com are disabled. This task is performed by first using the **Get-CsPersistentChatRoom** cmdlet and the Identity parameter to return all the chat rooms configured for the pool atl-cs-001.litwareinc.com. These chat rooms are then piped to the **Set-CsPersistentChatRoom** cmdlet, which sets the Disabled property of each room to True ($True).

    Get-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com" | Set-CsPersistentChatRoom -Disabled $True

## Example 3

Example 3 disables all the Persistent Chat chat rooms in the organization. To do this, the command first calls the **Get-CsPersistentChatRoom** cmdlet without any parameters in order to return a collection of all the Persistent Chat chat rooms. This collection is then piped to the **Set-CsPersistentChatRoom** cmdlet, which disables each room in the collection.

    Get-CsPersistentChatRoom | Set-CsPersistentChatRoom -Disabled $True

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

Persistent Chat discussions take the form of messages posted in individual chat rooms; chat rooms are discussion forums based on specific topics. By design, messages posted in a chat room remain there forever; at any time, users can return to the room and review all the messages that have been previously posted.

The **Set-CsPersistentChatRoom** cmdlet enables you to modify any (or all) of the chat rooms that have been configured for use in your organization. This includes assigning Managers and Presenters to a room.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsPersistentChatRoom"}

**Lync Server 控制面板:** To modify an existing Persistent Chat chat room using the Lync Server 控制面板, click **Persistent Chat**, click **Room**, then double-click the chat room to be modified.

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
<td><p>Unique Identifier for the Persistent Chat chat room being modified. The Identity for a chat room consists of the Persistent Chat pool where the room has been configured plus the name of the room; for example:</p>
<p>-Identity &quot;atl-gc-001.litwareinc.com\RedmondChatRoom&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Chat.Cmdlets.ChatRoom</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
</tr>
<tr class="odd">
<td><p><em>Addin</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Name of the Persistent Chat add-in, if any, associated with the chat room. A Persistent Chat add-in is a customized web page that can be embedded within a Persistent Chat client. Add-ins can be created by using the <strong>New-CsPersistentChatAddin</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>AsObject</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When specified, Active Directory display names are used when adding users to or removing users from the Managers or Presenters lists. When not specified, SIP addresses are used when managing these lists.</p></td>
</tr>
<tr class="odd">
<td><p><em>Category</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Category under which the room is located; for example:</p>
<p>-Category &quot;IT&quot;</p>
<p>Note that the specified category must already exist or the command will fail. Categories, which are a collection of chat rooms, can be created by using the <strong>New-CsPersistentChatCategory</strong> cmdlet.</p></td>
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
<td><p>Enables administrators to provide additional information about the new chat room.</p></td>
</tr>
<tr class="even">
<td><p><em>Disabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True ($True), the new chat room will be disabled and unavailable for use when it is first created. If this parameter is not used then the new chat room will be enabled and available for immediate use.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Invitations</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Chat.Cmdlets.ChatRoomInvitations</p></td>
<td><p>Specifies whether or not invitations for the chat room will be inherited from the category. Among other things, this means that users on the Members list will automatically receive an invitation to join a new chat room at the time that new room is created. If set to False, invitations will not be used for the room. If set to Inherit, the room will use the Invitations setting specified for its Category.</p></td>
</tr>
<tr class="odd">
<td><p><em>Managers</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>List of users allowed to define the membership of the chat room as well as configure other settings for the room.</p>
<p>To add a new user to the Managers list, use syntax similar to this:</p>
<p>-Managers @{Add=&quot;sip:kenmyer@litwareinc.com&quot;}</p>
<p>Multiple users can be added by separating the user SIP addresses with commas:</p>
<p>-Managers @{Add=&quot;sip:kenmyer@litwareinc.com&quot;, &quot;sip:pilar@litwareinc.com&quot;}</p>
<p>To remove a user from the Managers list use the Remove method:</p>
<p>-Managers @{Remove=&quot;sip:kenmyer@litwareinc.com&quot;}</p>
<p>To remove all the users from the Managers list, set the value of the Managers property to null:</p>
<p>-Managers $Null</p>
<p>In addition to working with individual users you can also work with entire OUs. For example, this command adds all the users in the IT OU to the managers list:</p>
<p>-Managers @{Add=&quot;OU=IT,DC=litwareinc,DC=com&quot;}</p>
<p>To make all the users in a distribution list chat room managers, use the Active Directory distinguished name of that distribution list:</p>
<p>-Managers @{Add=&quot;CN=ChatSupportGroup,OU=IT,DC=litwareinc,DC=com&quot;}</p></td>
</tr>
<tr class="even">
<td><p><em>Members</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>List of users who are allowed to access the chat room. If the Members property is null then the chat room inherits the membership list from its Persistent Chat category.</p>
<p>To add a new user to the Members list, use syntax similar to this:</p>
<p>-Members @{Add=&quot;sip:kenmyer@litwareinc.com&quot;}</p>
<p>Multiple users can be added by separating the user SIP addresses with commas:</p>
<p>-Members @{Add=&quot;sip:kenmyer@litwareinc.com&quot;, &quot;sip:pilar@litwareinc.com&quot;}</p>
<p>To remove a user from the Members list use the Remove method:</p>
<p>-Members @{Remove=&quot;sip:kenmyer@litwareinc.com&quot;}</p>
<p>To remove all the users from the Members list, set the value of the Members property to null:</p>
<p>-Members $Null</p>
<p>In addition to working with individual users you can also work with entire OUs. For example, this command adds all the users in the IT OU to the Members list:</p>
<p>-Members @{Add=&quot;OU=IT,DC=litwareinc,DC=com&quot;}</p>
<p>To make all the users in a distribution list chat room members, use the Active Directory distinguished name of that distribution list:</p>
<p>-Members @{Add=&quot;CN=ChatSupportGroup,OU=IT,DC=litwareinc,DC=com&quot;}</p></td>
</tr>
<tr class="odd">
<td><p><em>Name</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Name of the Persistent Chat chat room. Names must be unique per Persistent Chat pool.</p></td>
</tr>
<tr class="even">
<td><p><em>Presenters</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>List of users who are allowed to post messages in an auditorium chat room.</p>
<p>To add a new user to the Presenters list, use syntax similar to this:</p>
<p>-Presenters @{Add=&quot;sip:kenmyer@litwareinc.com&quot;}</p>
<p>Multiple users can be added by separating the user SIP addresses with commas:</p>
<p>-Presenters @{Add=&quot;sip:kenmyer@litwareinc.com&quot;, &quot;sip:pilar@litwareinc.com&quot;}</p>
<p>To remove a user from the Presenters list use the Remove method:</p>
<p>-Presenters @{Remove=&quot;sip:kenmyer@litwareinc.com&quot;}</p>
<p>To remove all the users from the Presenters list, set the value of the Presenters property to null:</p>
<p>-Presenters $Null</p>
<p>In addition to working with individual users you can also work with entire OUs. For example, this command adds all the users in the IT OU to the Presenters list:</p>
<p>-Presenters @{Add=&quot;OU=IT,DC=litwareinc,DC=com&quot;}</p>
<p>To make all the users in a distribution list chat room presenters, use the Active Directory distinguished name of that distribution list:</p>
<p>-Presenters @{Add=&quot;CN=ChatSupportGroup,OU=IT,DC=litwareinc,DC=com&quot;}</p></td>
</tr>
<tr class="odd">
<td><p><em>Privacy</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Chat.Cmdlets.ChatRoomPrivacy</p></td>
<td><p>Privacy settings for the chat room. Allowed values are:</p>
<p>* Open (any user can locate the chat room by doing a directory search, and anyone can participate in chat room activities)</p>
<p>* Secret (only chat room members can locate the room by doing a directory search, and only members can participate in chat room activities)</p>
<p>* Closed (any user can locate the chat room by doing a directory search, but only members can participate in chat room activities)</p></td>
</tr>
<tr class="even">
<td><p><em>Type</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Chat.Cmdlets.ChatRoomType</p></td>
<td><p>Specifies whether the chat room is configured as a Normal chat room (where all members can post messages) or an Auditorium (where only presenters can post messages). For example:</p>
<p>-Type &quot;Auditorium&quot;</p>
<p>The default value is Normal.</p></td>
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

The **Set-CsPersistentChatRoom** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.PersistentChat.Cmdlets.ChatRoomObject object.

## Return Types

None. Instead, the **Set-CsPersistentChatRoom** cmdlet modifies existing instances of the Microsoft.Rtc.Management.PersistentChat.Cmdlets.ChatRoomObject object.

## 另请参阅

#### 其他资源

[Clear-CsPersistentChatRoom](clear-cspersistentchatroom.md)  
[Get-CsPersistentChatRoom](get-cspersistentchatroom.md)  
[New-CsPersistentChatRoom](new-cspersistentchatroom.md)  
[Remove-CsPersistentChatRoom](remove-cspersistentchatroom.md)

