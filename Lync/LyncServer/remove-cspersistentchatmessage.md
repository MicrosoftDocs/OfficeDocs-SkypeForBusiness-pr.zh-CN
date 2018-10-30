---
title: Remove-CsPersistentChatMessage
TOCTitle: Remove-CsPersistentChatMessage
ms:assetid: 0cb53905-4608-44a9-ba3d-ba51fc90d65e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204668(v=OCS.15)
ms:contentKeyID: 49311982
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsPersistentChatMessage

 

_**上一次修改主题：** 2015-03-09_

Replaces one or more Persistent Chat messages in the Persistent Chat database with a default message or with an administrator-provided message. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Remove-CsPersistentChatMessage -ReplaceMessage <String> [-CaseSensitive <$true | $false>] [-EndDate <DateTime>] [-Filter <String>] [-MatchClause <And | Or | Exact>] [-StartDate <DateTime>] [-UserUri <String>] <COMMON PARAMETERS>

    Remove-CsPersistentChatMessage -Remove <SwitchParameter> [-CaseSensitive <$true | $false>] [-EndDate <DateTime>] [-Filter <String>] [-MatchClause <And | Or | Exact>] [-StartDate <DateTime>] [-UserUri <String>] <COMMON PARAMETERS>

    Remove-CsPersistentChatMessage [-CaseSensitive <$true | $false>] [-EndDate <DateTime>] [-Filter <String>] [-MatchClause <And | Or | Exact>] [-StartDate <DateTime>] [-UserUri <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: -Identity <String> [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 removes all the Persistent Chat messages posted on or before April 1, 2012 from the ITChatRoom chat room on the server atl-persistentchat-001.litwareinc.com.

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -EndDate "4/1/2012"

## Example 2

In Example 2, all Persistent Chat messages posted by the user kenmyer@litwareinc.com are removed from the ITChatRoom chat room on the server atl-persistentchat-001.litwareinc.com.

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

Persistent Chat discussions take the form of messages posted in individual chat rooms; chat rooms are discussion forums based on specific topics. By design, messages posted in a chat room remain there forever; at any time, users can return to the room and review all the messages that have been previously posted.

However, there might be times when administrators need to remove messages from a chat room; for example, perhaps a user posted a series of messages with erroneous information regarding the forthcoming company meeting. The **Remove-CsPersisentChatMessage** cmdlet enables administrators to remove a single chat message, or to remove an entire set of chat messages based on criteria such as the user who posted the message or keywords found in that message.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsPersistentChatMessage"}

**Lync Server 控制面板:** The functions carried out by the **Remove-CsPersistentChatMessage** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Unique identifier for the chat room containing the message to be deleted. For example:</p>
<p>-Identity &quot;atl-persistentchat-001.litwareinc.com\ITChatRoom&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Remove</em></p></td>
<td><p>Required</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, removes the Persistent Chat message without leaving a replacement message.</p>
<p>You cannot use both the Remove parameter and the ReplaceMessage parameter in the same command.</p></td>
</tr>
<tr class="odd">
<td><p><em>ReplaceMessage</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Enables administrators to specify the text of the replacement message. By default, the replacement message reads &quot;This message was replaced by the Persistent Chat administrator.&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>CaseSensitive</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When present, indicates that case sensitivity should be used when searching for messages to be removed. (In other words, an uppercase &quot;A&quot; will be treated as a different character than a lowercase &quot;a&quot;.) By default, searches are not case sensitive.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>EndDate</em></p></td>
<td><p>Optional</p></td>
<td><p>System.DateTime</p></td>
<td><p>Enables you to filter for messages that were posted on or before the specified date.</p></td>
</tr>
<tr class="odd">
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Keywords that can be used to help identify the messages to be deleted. For example, to search for all messages that include the keyword &quot;Fabrikam&quot; use this syntax:</p>
<p>-Filter &quot;Fabrikam&quot;</p>
<p>To search for multiple keywords, put all the keywords in a single string, separated by using blank spaces:</p>
<p>-Filter &quot;Fabrikam Contoso TailspinToys&quot;</p>
<p>By default, the <strong>Remove-CsPersistentChatMessage</strong> cmdlet will look for messages using all the specified keywords. To look for messages using any one of the provided keywords, use the MatchClause parameter and set the parameter value to &quot;Or&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>MatchClause</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Chat.Cmdlets.RemoveOcsMessageChatCmdlet+AndOr</p></td>
<td><p>Specifies how the <strong>Remove-CsPersistentChatMessage</strong> cmdlet handles multiple keywords. Allowed values are:</p>
<p>* All (A message must include all the specified keywords in order to be a match)</p>
<p>* Or (A message containing one or more of the specified keywords will be considered a match)</p>
<p>* Exact (Messages must exactly match the specified phrase, including the word order, in order to be a match)</p>
<p>For example, this syntax searches for messages that have the exact phrase &quot;For internal use only) in the message text:</p>
<p>-Filter &quot;For internal use only&quot; –MatchClause &quot;Exact&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>StartDate</em></p></td>
<td><p>Optional</p></td>
<td><p>System.DateTime</p></td>
<td><p>Enables you to filter for messages that were posted on or after the specified date.</p></td>
</tr>
<tr class="even">
<td><p><em>UserUri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>SIP address of the user who posted the message (or messages) that should be removed.</p></td>
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

None. The **Remove-CsPersistentChatMessage** cmdlet does not accept pipelined input.

## Return Types

None.

## 另请参阅

#### 其他资源

[Clear-CsPersistentChatRoom](clear-cspersistentchatroom.md)

