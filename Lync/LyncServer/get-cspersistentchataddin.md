---
title: Get-CsPersistentChatAddin
TOCTitle: Get-CsPersistentChatAddin
ms:assetid: 0d6b3283-c73d-4b83-b0f8-8f03aa4bba14
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204670(v=OCS.15)
ms:contentKeyID: 49311990
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsPersistentChatAddin

 

_**上一次修改主题：** 2015-03-09_

Returns information about all the Persistent Chat add-ins configured for use in the organization. A Persistent Chat add-in is a customized web page that can be embedded within a Persistent Chat client. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsPersistentChatAddin [-PersistentChatPoolFqdn <String>] <COMMON PARAMETERS>

    Get-CsPersistentChatAddin -Identity <String> <COMMON PARAMETERS>

    COMMON PARAMETERS:

## Examples

## Example 1

Example 1 returns information about all the Persistent Chat add-ins configured for use in the organization.

    Get-CsPersistentChatAddin

## Example 2

In Example 2, information is returned for a specific Persistent Chat add-in: the add-in with the Identity atl-cs-001.litwareinc.com\\ITPersistentChatAddin.

    Get-CsPersistentChatAddin -Identity "atl-cs-001.litwareinc.com\ITPersistentChatAddin"

## Example 3

Example 3 returns information for all the Persistent Chat add-ins configured for use on the pool atl-cs-001.litwareinc.com.

    Get-CsPersistentChatAddin -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com"

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

Add-ins serve as extensions to a Persistent Chat chat room. Add-ins are external applications (that is, items not built into Persistent Chat itself) that are associated with a particular chat room. For example, a help desk chat room might include a URL that links to a Web page or to a Silverlight application that shows the status of the day's help requests. The Lync Server Windows PowerShell 命令行接口 cmdlets do not provide the ability to create these add-ins. Instead, the **CsPersistentChatAddin** cmdlets are used to associate (or disassociate) an add-in from a chat room.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsPersistentChatAddin"}

**Lync Server 控制面板:** To view Persistent Chat add-in information in Lync Server 控制面板, click **Persistent Chat** and then click **Add-in**.

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
<td><p>Unique identifier for the Persistent Chat add-in to be returned. The Identity is composed of the fully qualified domain name of the Persistent Chat pool where the add-in is located, a &quot;\&quot; character, and the add-in name. For example:</p>
<p>-Identity &quot;atl-gc-001.litwareincom\ITPersistentChatAddin&quot;</p>
<p>If this parameter is not specified then the <strong>Get-CsPersistentChatAddin</strong> cmdlet returns information about all your Persistent Chat add-ins.</p></td>
</tr>
<tr class="even">
<td><p><em>PersistentChatPoolFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name for the Persistent Chat pool. If this parameter is used then only Persistent Chat add-ins found on the specified pool will be returned. If this parameter is not used then the <strong>Get-CsPersistentChatAddin</strong> cmdlet will return add-ins from all your Persistent Chat pools. For example:</p>
<p>–PoolFqdn &quot;atl-cs-001.litwareinc.com&quot;</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsPersistentChatAddin** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsPersistentChatAddin** cmdlet returns instances of the Microsoft.Rtc.Management.PersistentChat.Cmdlets.AddinObject object.

## 另请参阅

#### 其他资源

[New-CsPersistentChatAddin](new-cspersistentchataddin.md)  
[Remove-CsPersistentChatAddin](remove-cspersistentchataddin.md)  
[Set-CsPersistentChatAddin](set-cspersistentchataddin.md)

