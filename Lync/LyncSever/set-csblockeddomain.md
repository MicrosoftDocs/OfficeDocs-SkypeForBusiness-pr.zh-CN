---
title: Set-CsBlockedDomain
TOCTitle: Set-CsBlockedDomain
ms:assetid: 03f9443c-4c99-4338-bbf0-7b2f40a30ea5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398090(v=OCS.15)
ms:contentKeyID: 49311847
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsBlockedDomain

 

_**上一次修改主题：** 2015-03-09_

Modifies the Comment property for one or more of the domains included on the list of domains that are blocked for federation. By definition, your users are not allowed to use Lync Server applications to communicate with people from the blocked domain; for example, users cannot employ Lync to exchange instant messages with anyone with a SIP account in a domain that appears on the blocked list. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsBlockedDomain [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsBlockedDomain [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Comment <String>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 modifies the Comment for the blocked domain with the Identity "fabrikam.com". In this example, the Comment parameter is included along with the parameter value, "Block this domain pending legal review."

    Set-CsBlockedDomain -Identity fabrikam.com -Comment "Block this domain pending legal review."

## EXAMPLE 2

In Example 2, the Comment property is updated for all the domains included on the blocked domains list. To do this, the command first calls the **Get-CsBlockedDomain** cmdlet, which returns a collection of all the domains currently on the blocked domain list. That collection is then piped to the **Set-CsBlockedDomain** cmdlet, which proceeds to modify the Comment property for each domain in the collection.

    Get-CsBlockedDomain | Set-CsBlockedDomain -Comment "Block this domain pending legal review."

## EXAMPLE 3

In Example 3, a new comment ("Block this domain pending legal review.") is added to each domain on the blocked list that doesn’t already have a value configured for the Comment property. To carry out this task, the command first uses the **Get-CsBlockedDomain** cmdlet to return a collection of all the domains currently on the blocked list. This collection is then piped to the **Where-Object** cmdlet, which picks out only those domains where the Comment property is equal to a null value. The filtered collection is then piped to the **Set-CsBlockedDomain** cmdlet, which assigns the same comment to the Comment property of each domain in the filtered collection.

    Get-CsBlockedDomain | Where-Object {$_.Comment -eq $Null} | Set-CsBlockedDomain -Comment "Block this domain pending legal review."

## Detailed Description

Federation is a means by which two organizations can set up a trust relationship that facilitates communication between the two groups. When federation has been established, users in the two organizations can send each other instant messages, subscribe for presence notifications, and otherwise communicate with one another by using SIP applications such as Lync Server. Lync Server allows for three types of federation: 1) direct federation between your organization and another; 2) federation between your organization and a public provider; and, 3) federation between your organization and a third-party hosting provider.

Setting up direct federation with another organization involves several tasks. To begin with, you must enable your Access Edge servers to allow federation. In addition, the other organization must enable federation with you; federation cannot be established unless both parties agree to the relationship.

To set up a federated relationship you might also need to manage two federation-related lists: the allowed list and the blocked list. The allowed list represents the organizations you have chosen to federate with; if a domain appears on the allowed list then (depending on your configuration settings) your users will be able to exchange instant messages and presence information with users who have accounts in that federated domain. Conversely, the blocked list represents domains that users are expressly forbidden from federating with; for example, messages sent from a blocked domain will automatically be rejected by Lync Server.

The Comment property, the only property of a blocked domain that can be modified, is used to store additional information about a domain on the blocked list (for example, why the domain is being blocked; when the domain can be removed from the blocked list; or who to contact if you would like to have the domain removed from the blocked list). If you need to change the Comment property for any domain on the list of blocked domains, use the **Set-CsBlockedDomain** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsBlockedDomain** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsBlockedDomain"}

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
<td><p><em>Comment</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to provide additional information about the domain being modified. For example, you might add a Comment that indicates why the domain has been placed on the blocked list.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Fully qualified domain name (FQDN) of the blocked domain for which the Comment property is being modified. For example: fabrikam.com</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>BlockedDomain object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

Microsoft.Rtc.Management.WritableConfig.Settings.Edge.BlockedDomain object. The **Set-CsBlockedDomain** cmdlet accepts pipelined instances of the blocked domain object.

## Return Types

The **Set-CsBlockedDomain** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Edge.BlockedDomain object.

## 另请参阅

#### 其他资源

[Get-CsBlockedDomain](get-csblockeddomain.md)  
[New-CsBlockedDomain](new-csblockeddomain.md)  
[Remove-CsBlockedDomain](remove-csblockeddomain.md)  
[Set-CsAccessEdgeConfiguration](set-csaccessedgeconfiguration.md)

