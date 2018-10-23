---
title: Get-CsPersistentChatEligiblePrincipal
TOCTitle: Get-CsPersistentChatEligiblePrincipal
ms:assetid: 541de778-3aca-4d3f-9d46-d9b6d8212987
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204891(v=OCS.15)
ms:contentKeyID: 49312866
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsPersistentChatEligiblePrincipal

 

_**上一次修改主题：** 2015-03-09_

Returns the eligible principals for a Persistent Chat category or chat room. Eligible principals include allowed members or managers (for a category of chat room) as well as allowed presenters (chat room only). 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsPersistentChatEligiblePrincipal -Category <String> <COMMON PARAMETERS>

    Get-CsPersistentChatEligiblePrincipal -Room <String> [-Presenters <SwitchParameter>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Filter <String>] [-PersistentChatPoolFqdn <String>] [-ResultSize <Int32>]

## Examples

## Example 1

The command shown in Example 1 returns information about the eligible principals for the Persistent Chat category ITChat.

    Get-CsPersistentChatEligiblePrincipal -PersistentChatPoolFqdn "atl-persistentchat-001.litwareinc.com" -Category "ITChat"

## Example 2

In Example 2, information is returned for all the eligible presenters for the chat room HelpDeskChatRoom.

    Get-CsPersistentChatEligiblePrincipal -PersistentChatPoolFqdn "atl-persistentchat-001.litwareinc.com" -Room "HelpDeskChatRoom" -Presenters

## Example 3

Example 3 is a variation on the command shown in Example 2; in this example, however, information is returned only for Persistent Chat presenters which do not represent user accounts. To do this, the **Get-CsPersistentChatEligiblePrincipal** cmdlet is first used to return all the presenters for the chat room HelpDeskChatRoom. That collection is then piped to the **Where-Object** cmdlet, which selects only those presenters where the PersistentChatPrincipalType property is not equal to (-ne) "user".

    Get-CsPersistentChatEligiblePrincipal -PersistentChatPoolFqdn "atl-persistentchat-001.litwareinc.com" -Room "HelpDeskChatRoom" -Presenters | Where-Object {$_.PersistentChatPrincipalType -ne "user"}

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

Chat categories provide the option of specifying certain users as Creators; that is, users who are allowed to create chat rooms within the category. Likewise, chat rooms provide the option of specifying users as Managers and/or Presenters. In order to be assigned any of these roles, however, the users in question must appear on the AllowedMembers list for the specified category/room. You can retrieve the list of allowed members for a room or category by using the [Get-CsPersistentChatRoom](get-cspersistentchatroom.md) cmdlet and the [Get-CsPersistentChatCategory](get-cspersistentchatcategory.md) cmdlets However, if a security group, OU, or domain has been added to the allowed members list you will not see the names of the users in that security group, OU, or domain. For example, if the security group FinanceManagers is on the allowed list you will not see the names of the users who belong to FinanceManagers; instead, you will only see the name of the group.

To view the names of all the users in that group (as well as the names of all the users on the allowed members list for a category or room) use the **Get-CsPersistentChatEligiblePrincipal** room instead.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsPersistentChatEligiblePrincipal"}

Lync Server 控制面板: The functions carried out by the **Get-CsPersistentChatEligiblePrincipal** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Name of the Group Chat category for which eligible principals are to be returned. You must use either the Category or the Room parameter when calling the <strong>Get-CsPersistentChatEligiblePrincipal</strong> cmdlet; however, you cannot use both of those parameters in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>Room</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Name of the Group Chat room for which eligible principals are to be returned. You must use either the Category or the Room parameter when calling the <strong>Get-CsPersistentChatEligiblePrincipal</strong> cmdlet; however, you cannot use both of those parameters in the same command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Provides a way to filter for eligible principals by using a wildcard search. For example:</p>
<p>-Filter &quot;*smith*&quot;</p>
<p>Note that the Filter parameter can only filter on user SIP addresses.</p></td>
</tr>
<tr class="even">
<td><p><em>PersistentChatPoolFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name of the persistent Chat pool. For example:</p>
<p>-PersistentChatPoolFqdn &quot;atl-persistentchat-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>Presenters</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When included in the command, returns the eligible presenters for a Persistent Chat chat room. When not included in the command, the <strong>Get-CsPersistentChatEligiblePrincipal</strong> cmdlet returns eligible members and managers instead.</p>
<p>This parameter can only be used along with the Room parameter, and can only return information for rooms configured as auditoriums.</p></td>
</tr>
<tr class="even">
<td><p><em>ResultSize</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Enables you to limit the number of records returned by the cmdlet. For example, to return seven Persistent Chat principals (regardless of the number of users that are in your forest) include the ResultSize parameter and set the parameter value to 7. Note that there is no way to guarantee which seven principals will be returned.</p>
<p>The result size can be set to any whole number between 0 and 2147483647, inclusive. If set to 0 the command will run, but no data will be returned. If you set the ResultSize to 7 but you have only three principals in your forest, the command will return those three principals, and then complete without error.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsPersistentChatEligiblePrincipal** cmdlet does not accept pipelined data.

## Return Types

The **Get-CsPersistentChatEligiblePrincipal** cmdlet returns instances of the Microsoft.Rtc.Management.GroupChat.Cmdlets.ADPersistentChatPrincipal object.

## 另请参阅

#### 其他资源

[Set-CsPersistentChatCategory](set-cspersistentchatcategory.md)  
[New-CsPersistentChatRoom](new-cspersistentchatroom.md)

