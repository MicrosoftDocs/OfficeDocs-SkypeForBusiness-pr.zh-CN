---
title: New-CsPersistentChatEndpoint
TOCTitle: New-CsPersistentChatEndpoint
ms:assetid: 3a3a7acc-3239-4140-8005-ef72ab2f61e1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204811(v=OCS.15)
ms:contentKeyID: 49312523
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsPersistentChatEndpoint

 

_**上一次修改主题：** 2015-03-09_

Creates a new Persistent Chat endpoint. A Persistent Chat endpoint is an Active Directory contact object provides a friendly URL for a Lync Server 2013 Persistent Chat pool. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    New-CsPersistentChatEndpoint -PersistentChatPoolFqdn <Fqdn> -SipAddress <String> [-Confirm [<SwitchParameter>]] [-DisplayName <String>] [-PassThru <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 creates a new Persistent Chat endpoint for the pool atl-pcpool-001.litwareinc.com. This new endpoint has the SIP address "sip:pce@litwareinc.com" and the display name of "Persistent Chat Endpoint 1".

    New-CsPersistentChatEndpoint -SipAddress "sip:pce@litwareinc.com" -PersistentChatPoolFqdn "atl-pcpool-001.litwareinc.com" -DisplayName "Persistent Chat Endpoint 1"

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

However, if you have users running legacy clients (such as Microsoft Lync 2010 these users might find the default Persistent Chat URIs difficult to work with and difficult to use when pointing their legacy client towards the pool. Because of this, administrators can use the **New-CsPersistentChatEndpoint** cmdlet to create an additional contact object for the pool, a contact object that provides a friendlier, easier-to-use URI.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsPersistentChatEndpoint"}

**Lync Server 控制面板:** The functions carried out by the **New-CsPersistentChatEndpoint** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>PersistentChatPoolFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name of the Persistent Chat pool that the new endpoint will be associated with. For example:</p>
<p>-PersistentChatPoolFqdn &quot;atl-pc-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>SipAddress</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Unique identifier that allows the endpoint to communicate with SIP devices such as Lync 2013. The SIP address must use the sip: prefix as well as a valid SIP domain; for example:</p>
<p>-SipAddress &quot;sip:pcEndpoint1@litwareinc.com&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>DisplayName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Active Directory display name for the new contact object.</p></td>
</tr>
<tr class="odd">
<td><p><em>PassThru</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Enables you to pass a contact object through the pipeline that represents the new Persistent Chat endpoint. By default, the <strong>New-CsPersistentChatEndpoint</strong> cmdlet does not pass objects through the pipeline.</p></td>
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

None. The **New-CsPersistentChatEndpoint** cmdlet does not accept pipelined input.

## Return Types

The **New-CsPersistentChatEndpoint** cmdlet creates new instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSPersistentChatContact class.

## 另请参阅

#### 其他资源

[Get-CsPersistentChatEndpoint](get-cspersistentchatendpoint.md)  
[Remove-CsPersistentChatEndpoint](remove-cspersistentchatendpoint.md)

