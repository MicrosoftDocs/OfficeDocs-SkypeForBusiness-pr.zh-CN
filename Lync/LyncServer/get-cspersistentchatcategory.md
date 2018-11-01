---
title: Get-CsPersistentChatCategory
TOCTitle: Get-CsPersistentChatCategory
ms:assetid: 2ec14091-cb05-4c4c-b091-b7e88f5ca3cf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204771(v=OCS.15)
ms:contentKeyID: 49312377
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsPersistentChatCategory

 

_**上一次修改主题：** 2015-03-09_

Returns information about the Persistent Chat categories in use in your organization. A Persistent Chat category represents a collection of Persistent Chat chat rooms. Each chat room must be associated with a category. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsPersistentChatCategory [-PersistentChatPoolFqdn <String>] <COMMON PARAMETERS>

    Get-CsPersistentChatCategory -Identity <String> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AsObject <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 returns information for all the Persistent Chat categories configured for use in the organization.

    Get-CsPersistentChatCategory

## Example 2

In Example 2, information is returned for all the Persistent Chat categories configured for use on the pool atl-cs-001.litwareinc.com.

    Get-CsPersistentChatCategory -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com"

## Example 3

Example 3 returns information for all the Persistent Chat categories where the Invites property has been set to False. To do this, the command first uses the **Get-CsPersistentChatCategory** cmdlet to return a collection of all the Persistent Chat categories. This collection is then piped to the Where-Object cmdlet, which picks out only those categories where the Invites property is set to False ($False).

    Get-CsPersistentChatCategory | Where-Object {$_.Invites -eq $False}

## Example 4

In Example 4, information is returned for all the Persistent Chat categories where Ken Myer is listed as one of the creators. To do this, the **Get-CsPersistentChatCategory** cmdlet is first used to return a collection of all the Persistent Chat categories. This collection is then piped to the **Where-Object** cmdlet, which picks out any category where the Creators property includes (-contains) the name "Ken Myer".

    Get-CsPersistentChatCategory | Where-Object {$_.Creators -contains "Ken Myer"}

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

Persistent Chat categories provide a way for administrators to organize, and manage, Persistent Chat chat rooms. Categories provide a way for administrators to group related chat rooms; for example, all chat rooms used by the finance department can be grouped in the same category. Likewise, categories provide a way for administrators to manage permissions to these rooms, dictating which users are allowed access to the rooms, which users are denied access to the rooms, and which users are allowed to create new chat rooms within the category.

Note that all chat rooms must belong to a category; you cannot create a chat room without assigning that room to a category. That means that you must create at least one category before you can add any chat rooms to your Persistent Chat implementation.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsPersistentChatCategory"}

**Lync Server 控制面板:** To view Persistent Chat categories in Lync Server 控制面板, click **Persistent Chat** and then click **Category**.

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
<td><p><em>AsObject</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When specified, Active Directory display names are used when showing users who are on the AllowedMembers, DeniedMembers, or Creators lists. When not specified, SIP addresses are used when showing these users.</p></td>
</tr>
<tr class="odd">
<td><p><em>PersistentChatPoolFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name of the Persistent Chat pool that hosts Persistent Chat categories. If you use the PoolFqdn parameter without including the Name parameter, information will be returned for all the Persistent Chat categories on the specified pool. If you leave off both the Name and PoolFqdn parameters, then information will be returned for all your Persistent Chat categories.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsPersistentChatCategory** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsPersistentChatCategory** cmdlet returns instances of the Microsoft.Rtc.Management.PersistentChat.Cmdlets.CategoryObject object.

## 另请参阅

#### 其他资源

[New-CsPersistentChatCategory](new-cspersistentchatcategory.md)  
[Remove-CsPersistentChatCategory](remove-cspersistentchatcategory.md)  
[Set-CsPersistentChatCategory](set-cspersistentchatcategory.md)

