---
title: Set-CsPersistentChatAddin
TOCTitle: Set-CsPersistentChatAddin
ms:assetid: 1badd6b5-e519-47a1-9434-9fa5a00b79ff
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204721(v=OCS.15)
ms:contentKeyID: 49312166
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsPersistentChatAddin

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing Persistent Chat add-in. A Persistent Chat add-in is a customized web page that can be embedded within a Persistent Chat client. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsPersistentChatAddin -Instance <Addin> <COMMON PARAMETERS>

    Set-CsPersistentChatAddin -Identity <String> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Name <String>] [-Url <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

Example 1 modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin. In this case, the URL is changed to http://atl-cs-001.litwareinc.com/itchat2.

    Set-CsPersistentChatAddin -Identity "atl-cs-001.litwareinc.com\ITPersistentChatAddin" -Url "http://atl-cs-001.litwareinc.com/itchat2"

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

Add-ins serve as extensions to a Persistent Chat chat room. Add-ins are external applications (that is, items not built into Persistent Chat itself) that are associated with a particular chat room. For example, a help desk chat room might include a URL that links to a Web page or to a Silverlight application that shows the status of the day's help requests. The Lync Server Windows PowerShell 命令行接口 cmdlets do not provide the ability to create these add-ins. Instead, the **CsPersistentChatAddin** cmdlets are used to associate (or disassociate) an add-in from a chat room.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsPersistentChatAddin"}

**Lync Server 控制面板:** To modify an existing Persistent Chat add-in using the Lync Server 控制面板, click **Persistent Chat**, click **Add-in**, then double-click the add-in to be modified.

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
<td><p>Unique identifier for the Persistent Chat add-in. The Identity is composed of the fully qualified domain name of the Persistent Chat pool where the add-in is located, a &quot;\&quot; character, and the add-in name. For example:</p>
<p>-Identity &quot;atl-gc-001.litwareincom\ITPersistentChatAddin&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Chat.Cmdlets.Addin</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Name</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Friendly name given to the Persistent Chat add-in. Names must be unique per Persistent Chat pool.</p></td>
</tr>
<tr class="odd">
<td><p><em>Url</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL of the Web page to be displayed by the Persistent Chat add-in.</p></td>
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

The **Set-CsPersistentChatAddin** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.PersistentChat.Cmdlets.AddinObject object.

## Return Types

None. Instead, the **Set-CsPersistentChatAddin** cmdlet modifies existing instances of the Microsoft.Rtc.Management.PersistentChat.Cmdlets.AddinObject object.

## 另请参阅

#### 其他资源

[Get-CsPersistentChatAddin](get-cspersistentchataddin.md)  
[New-CsPersistentChatAddin](new-cspersistentchataddin.md)  
[Remove-CsPersistentChatAddin](remove-cspersistentchataddin.md)

