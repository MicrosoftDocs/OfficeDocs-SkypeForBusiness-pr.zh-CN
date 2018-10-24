---
title: New-CsBlockedDomain
TOCTitle: New-CsBlockedDomain
ms:assetid: c7b49baf-759b-485f-9391-58584b227fd5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398822(v=OCS.15)
ms:contentKeyID: 49314212
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsBlockedDomain

 

_**上一次修改主题：** 2015-03-09_

Adds a new domain to the list of domains blocked for federation. By definition, your users are not allowed to use Lync Server applications to communicate with people from the blocked domain; for example, users cannot use Lync to exchange instant messages with anyone with a SIP account in a domain that appears on the blocked list. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsBlockedDomain -Domain <String> <COMMON PARAMETERS>

    New-CsBlockedDomain -Identity <XdsGlobalRelativeIdentity> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Comment <String>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the domain fabrikam.com is added to the list of blocked domains. To do this, the **New-CsBlockedDomain** cmdlet is called, along with the Identity parameter, which is assigned the name of the domain to be blocked. In addition, the Comment parameter is included in order to add a comment to the blocked domain. Note that this command will fail if fabrikam.com is already on the blocked list or on the allowed list.

    New-CsBlockedDomain -Identity "fabrikam.com" -Comment "Blocked per Ken Myer."

## EXAMPLE 2

Example 2 demonstrates how you can use the InMemory parameter to create a new blocked domain that initially exists only in memory. After you modify the property values of this in-memory-only domain you can then call the **Set-CsBlockedDomain** cmdlet to add the domain to the blocked list.

To perform this task, the first line in the command uses the **New-CsBlockedDomain** cmdlet and the InMemory parameter to create a blocked domain with the Identity fabrikam.com. Upon creation, this virtual domain is stored in the variable $x.

In the second line, the Comment property of the virtual domain is modified. After that, line 3 uses the **Set-CsBlockedDomain** cmdlet to add the virtual domain to the blocked list. Without line 3, the virtual domain would exist only in memory and would never be added to the blocked list. Instead, the virtual domain will disappear as soon as you end your Windows PowerShell session or delete the variable $x.

    $x = New-CsBlockedDomain -Identity "fabrikam.com" -InMemory
    $x.Comment = "Blocked per Ken Myer."
    Set-CsBlockedDomain -Instance $x

## Detailed Description

Federation is a means by which two organizations can set up a trust relationship that facilitates communication between the two groups. When federation has been established, users in the two organizations can send each other instant messages, subscribe for presence notifications, and otherwise communicate with one another by using SIP applications such as Lync. Lync Server allows for three types of federation: 1) direct federation between your organization and another; 2) federation between your organization and a public provider; and, 3) federation between your organization and a third-party hosting provider.

Setting up direct federation with another organization involves several tasks. To begin with, you must enable your servers running the Lync Server Access Edge service to allow federation. In addition, the other organization must enable federation with you; federation cannot be established unless both parties agree to the relationship.

To establish a federated relationship you might also need to manage two federation-related lists: the allowed list and the blocked list. The allowed list represents the organizations you have chosen to federate with; if a domain appears on the allowed list then (depending on your configuration settings) your users will be able to exchange instant messages and presence information with users who have accounts in that federated domain. Conversely, the blocked list represents domains that users are expressly forbidden from federating with; for example, messages sent from a blocked domain will automatically be rejected by Lync Server.

The **New-CsBlockedDomain** cmdlet enables you to add a domain to the list of blocked domains.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsBlockedDomain** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsBlockedDomain"}

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
<td><p><em>Domain</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>FQDN (for example, fabrikam.com) of the domain to be added to the blocked list. You can use either the Identity or the Domain parameter (but not both) in order to specify the domain name. If you use Identity, the Domain property will be set to the same value that is assigned to Identity. If you use Domain, the Identity property will be set to the same value that is assigned to Domain.</p>
<p>Note that Domains must be unique: if the specified domain already exists on either the blocked or the allowed list, the command will fail.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Fully qualified domain name (FQDN) of the domain to be added to the blocked list; for example, &quot;fabrikam.com&quot;. You can use either the Identity or the Domain parameter (but not both) in order to specify the domain name. If you use Identity, the Domain property will be set to the same value assigned to Identity. If you use Domain, the Identity property will be set to the same value that is assigned to Domain.</p>
<p>Note that Identities must be unique: if the specified domain already exists on either the blocked or the allowed list, the command will fail.</p></td>
</tr>
<tr class="odd">
<td><p><em>Comment</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Optional string value that provides additional information about the blocked domain. For example, you might add a Comment that explains why the domain has been blocked.</p></td>
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
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **New-CsBlockedDomain** cmdlet does not accept pipelined input.

## Return Types

Creates instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Edge.BlockedDomain object.

## 另请参阅

#### 其他资源

[Get-CsBlockedDomain](get-csblockeddomain.md)  
[Remove-CsBlockedDomain](remove-csblockeddomain.md)  
[Set-CsAccessEdgeConfiguration](set-csaccessedgeconfiguration.md)  
[Set-CsBlockedDomain](set-csblockeddomain.md)

