﻿---
title: Remove-CsPersistentChatEndpoint
TOCTitle: Remove-CsPersistentChatEndpoint
ms:assetid: 0211850c-b4e7-4bb2-9a82-bfbfbd7de7b7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204626(v=OCS.15)
ms:contentKeyID: 49311810
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsPersistentChatEndpoint

 

_**上一次修改主题：** 2015-03-09_

Removes an existing Persistent Chat endpoint. A Persistent Chat endpoint is an Active Directory contact object provides a friendly URL for a Lync Server 2013 Persistent Chat pool. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Remove-CsPersistentChatEndpoint -Identity <UserIdParameter> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 deletes the Persistent Chat endpoint that has the Identity "sip:pce@litwareinc.com". In this example, the SIP address is used for the Identity

    Remove-CsPersistentChatEndpoint -Identity "sip:pce@litwareinc.com"

## Example 2

Example 2 deletes all the Persistent Chat endpoints configured for the pool atl-pcpool-001.litwareinc.com. To carry out this task, the command first uses the **Get-CsPersistentChatEndpoint** cmdlet and the PoolFqdn parameter to return all the endpoints for the pool atl-pcpool-001.litwareinc.com. The endpoints in that collection are then piped to, and removed by, the **Remove-CsPersistentChatEndpoint** cmdlet.

    Get-CsPersistentChatEndpoint -PoolFqdn "atl-pcpool-001.litwareinc.com" | Remove-CsPersistentChatEndpoint

## Example 3

The command shown in Example 3 deletes all the Persistent Chat endpoints configured for use in the organization. To do this, the command first calls the **Get-CsPersistentChatEndpoint** cmdlet to return a collection of all the Persistent Chat endpoints. This collection is then piped to the **Remove-CsPersistentChatEndpoint** cmdlet, which deletes each endpoint in the collection.

    Get-CsPersistentChatEndpoint | Remove-CsPersistentChatEndpoint

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

However, if you have users running legacy clients (such as Microsoft Lync 2010 these users might find the default Persistent Chat URIs difficult to work with and difficult to use when pointing their legacy client towards the pool. Because of this, administrators can use the [New-CsPersistentChatEndpoint](new-cspersistentchatendpoint.md) cmdlet to create an additional contact object for the pool, a contact object that provides a friendlier, easier-to-use URI. These endpoints can later be removed by using the **Remove-CsPersistentChatEndpoint** cmdlet.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsPersistentChatEndpoint"}

Lync Server 控制面板: The functions carried out by the **Remove-CsPersistentChatEndpoint** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Microsoft.Rtc.Management.AD.UserIdParameter</p></td>
<td><p>Unique identifier for the Persistent Chat endpoint to be removed. Endpoint Identities are typically specified using the endpoint's SIP address or display name; for example:</p>
<p>-Identity &quot;sip:pcEndpoint1@litwareinc.com&quot;</p>
<p>However, you can also use the full Identity of the endpoint; for example:</p>
<p>-Identity &quot;CN={33e5014b-dcba-46b5-9bf7-48f4d5fca69d}, CN=Application Contacts,CN=RTC Service,CN=Services,CN=Configuration,DC=litwareinc,DC=com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command</p></td>
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

The **Remove-CsPersistentChatEndpoint** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.ADConnect.Schema.OCSPersistentChatContact class.

## Return Types

None. The **Remove-CsPersistentChatEndpoint** cmdlet does not return objects or data.

## 另请参阅

#### 其他资源

[Get-CsPersistentChatEndpoint](get-cspersistentchatendpoint.md)  
[New-CsPersistentChatEndpoint](new-cspersistentchatendpoint.md)

