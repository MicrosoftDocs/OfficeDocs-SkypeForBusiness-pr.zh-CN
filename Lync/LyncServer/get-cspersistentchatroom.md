---
title: Get-CsPersistentChatRoom
TOCTitle: Get-CsPersistentChatRoom
ms:assetid: 9826c44b-35a6-473e-97d4-952415d640d1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205123(v=OCS.15)
ms:contentKeyID: 49313690
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsPersistentChatRoom

 

_**上一次修改主题：** 2015-03-09_

Returns information about the Persistent Chat chat rooms configured for use in your organization. A chat room is a discussion forum that typically revolves around a specific topic. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsPersistentChatRoom [-Addin <String>] [-Category <String>] [-ChatContentExceedsMB <Int32>] [-Disabled <$true | $false>] [-Filter <String>] [-Invitations <False | Inherit>] [-Manager <String>] [-Member <String>] [-PersistentChatPoolFqdn <String>] [-Privacy <Open | Closed | Secret>] [-ResultSize <Int32>] [-SearchDescription <SwitchParameter>] [-Type <Normal | Auditorium>] <COMMON PARAMETERS>

    Get-CsPersistentChatRoom [-Identity <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AsObject <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 returns information about the Persistent Chat chat rooms configured for use in the organization.

    Get-CsPersistentChatRoom

## Example 2

Example 2 returns information for a single Persistent Chat chat room: the room with the Identity atl-cs-001.litwareinc.com\\ITChatRoom.

    Get-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom"

## Example 3

In Example 3, information is returned for all the Persistent Chat chat rooms configured for the pool atl-cs-001.litwareinc.com.

    Get-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com"

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

Persistent Chat discussions take the form of messages posted in individual chat rooms; chat rooms are discussion forums based on specific topics. By design, messages posted in a chat room remain there forever; at any time, users can return to the room and review all the messages that have been previously posted.

The **Get-CsPersistentChatRoom** cmdlet provides a way to return information about all the chat rooms configured for use in your organization.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsPersistentChatRoom"}

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
<td><p><em>Addin</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Returns chat rooms associated with the specified chat room add-in.</p>
<p>Note that you can only specify one add-in per command.</p></td>
</tr>
<tr class="even">
<td><p><em>AsObject</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When specified, Active Directory display names are used when showing users who are on the Managers or Presenters lists. When not specified, SIP addresses are used when showing these users.</p></td>
</tr>
<tr class="odd">
<td><p><em>Category</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Returns information for all the Persistent Chat chat rooms in the specified category. For example:</p>
<p>-Category &quot;ITChat&quot;</p>
<p>You can only specify a single category when using the Category parameter. In addition, you cannot use the PersistentChatPoolFqdn, Filter, or Identity parameters in any command that uses the Category parameter.</p></td>
</tr>
<tr class="even">
<td><p><em>ChatContentExceedsMB</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Returns chat rooms whose cumulative chat content exceeds the specified value (in megabytes).</p></td>
</tr>
<tr class="odd">
<td><p><em>Disabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Enables you to search for active chat rooms (by using the parameter value $False) or disabled chat rooms (by using the parameter value $True).</p></td>
</tr>
<tr class="even">
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to return information for Persistent Chat chat rooms based on the Name and/or the Description of the room. To return information for a chat room with a specific name, use syntax similar to this:</p>
<p>-Filter {Name –like &quot;ITChat&quot;}</p>
<p>That syntax returns information only for chat rooms that have the name ITChat.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Unique Identifier for the Persistent Chat chat room being returned. The Identity for a chat room consists of the Persistent Chat pool where the room has been configured plus the name of the room; for example:</p>
<p>-Identity &quot;atl-gc-001.litwareinc.com\RedmondChatRoom&quot;</p>
<p>You cannot use the Category, Filter, or PersistentChatPoolFqdn parameters in any command that uses the Identity parameter. If you call the <strong>Get-CsPersistentChatRoom</strong> cmdlet without any parameters the cmdlet will return information about all the chat rooms configured for use in your organization.</p></td>
</tr>
<tr class="even">
<td><p><em>Invitations</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Chat.Cmdlets.ChatRoomInvitations</p></td>
<td><p>Returns chat rooms that use invitations (by using the parameter value Inherit) or chat rooms that do not use inivtations (by using the parameter value False).</p></td>
</tr>
<tr class="odd">
<td><p><em>Manager</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Returns chat rooms managed by the specified user. For example:</p>
<p>-Manager &quot;sip:kenmyer@litwareinc.com&quot;</p>
<p>Note that you can only specify a single manager per command.</p></td>
</tr>
<tr class="even">
<td><p><em>Member</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Returns chat rooms that the specified user is a member of. For example:</p>
<p>-Member &quot;sip:kenmyer@litwareinc.com&quot;</p>
<p>Note that you can only specify a single member per command.</p></td>
</tr>
<tr class="odd">
<td><p><em>PersistentChatPoolFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Returns information about all the Persistent Chat chat rooms configured on the specified Persistent Chat pool. For example:</p>
<p>-PersistentChatPoolFqdn &quot;atl-gc-001.litwareinc.com&quot;</p>
<p>You cannot use the Category, Filter, or Identity parameters in any command that uses the PersistentChatPoolFqdn parameter.</p></td>
</tr>
<tr class="even">
<td><p><em>Privacy</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Chat.Cmdlets.ChatRoomPrivacy</p></td>
<td><p>Enables you to return chat rooms that meet the specified privacy setting. Allowed values are:</p>
<p>* Open (any user can locate the chat room by doing a directory search, and anyone can participate in chat room activities)</p>
<p>* Secret (only chat room members can locate the room by doing a directory search, and only members can participate in chat room activities)</p>
<p>* Closed (any user can locate the chat room by doing a directory search, but only members can participate in chat room activities)</p></td>
</tr>
<tr class="odd">
<td><p><em>ResultSize</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Enables you to limit the number of records returned by the cmdlet. For example, to return seven chat rooms (regardless of the number of rooms in your forest) include the ResultSize parameter and set the parameter value to 7. Note that there is no way to guarantee which seven rooms will be returned.</p>
<p>The result size can be set to any whole number between 0 and 2147483647, inclusive. If set to 0 the command will run, but no data will be returned. If you set the ResultSize to 7 but you have only three rooms in your forest, the command will return those three rooms, and then complete without error.</p></td>
</tr>
<tr class="even">
<td><p><em>SearchDescription</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to search for the specified text value in either the chat room Name or the chat room Description. To search both the Name and the Description, include the SearchDescription parameter along with the Filter parameter. For example:</p>
<p>-SearchDescription –Filter &quot;IT chat room&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>Type</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Chat.Cmdlets.ChatRoomType</p></td>
<td><p>Returns chat rooms by room type. Allowed values are:</p>
<p>* Normal (chat rooms where all members can post messages)</p>
<p>* Auditorium (chat rooms where only presenters can post messages)</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsPersistentChatRoom** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsPersistentChatRoom** cmdlet returns instances of the Microsoft.Rtc.Management.PersistentChat.Cmdlets.ChatRoomObject object.

## 另请参阅

#### 其他资源

[Clear-CsPersistentChatRoom](clear-cspersistentchatroom.md)  
[New-CsPersistentChatRoom](new-cspersistentchatroom.md)  
[Remove-CsPersistentChatRoom](remove-cspersistentchatroom.md)  
[Set-CsPersistentChatRoom](set-cspersistentchatroom.md)

