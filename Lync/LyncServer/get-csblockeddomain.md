﻿---
title: Get-CsBlockedDomain
TOCTitle: Get-CsBlockedDomain
ms:assetid: 5fa2c2a3-b5e4-430c-970a-0c506a6924b5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398424(v=OCS.15)
ms:contentKeyID: 49313007
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsBlockedDomain

 

_**上一次修改主题：** 2015-03-09_

Returns information about the domains that are included on the list of domains blocked for federation. By definition, your users are not allowed to use Lync Server applications to communicate with people from the blocked domain; for example, users cannot use Lync to exchange instant messages with anyone with a Session Initiation Protocol (SIP) account in a domain on the blocked list. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsBlockedDomain [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsBlockedDomain [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

The command shown in Example 1 returns a collection of all the domains included on the blocked domain list. This is done by calling the**Get-CsBlockedDomain** cmdlet without any additional parameters.

    Get-CsBlockedDomain

## EXAMPLE 2

In Example 2, the only blocked domain returned is the one with the Identity "fabrikam.com". Because domains on the blocked list must have unique identities, this command will return, at most, a single item.

    Get-CsBlockedDomain -Identity fabrikam.com

## EXAMPLE 3

Example 3 uses the Filter parameter to return a collection of all the blocked domains that have an identity that ends in the string value ".net". This sample command returns such domains as northwindtraders.net, contoso.net, and fabrikam.net.

    Get-CsBlockedDomain -Filter *.net

## EXAMPLE 4

Example 4 returns a collection of all the domains where the Comment property has no value. To do this, the command first uses the **Get-CsBlockedDomain** cmdlet to return a collection of all the domains on the blocked list. This collection is then piped to the **Where-Object** cmdlet, which selects only those domains where the Comment property is equal to a null value.

    Get-CsBlockedDomain | Where-Object {$_.Comment -eq $Null}

## EXAMPLE 5

In Example 5, all the blocked domains that include the string value "Ken Myer" somewhere in the Comment property are returned. To carry out this task, the **Get-CsBlockedDomain** cmdlet is first called in order to return a collection of all the domains on the blocked domains list. This collection is then piped to the **Where-Object** cmdlet, which picks out those domains where the Comment property contains the string value "Ken Myer".

    Get-CsBlockedDomain | Where-Object {$_.Comment -match "Ken Myer"}

## Detailed Description

Federation is a means by which two organizations can set up a trust relationship that facilitates communication between the two groups. When federation has been established, users in the two organizations can send each other instant messages, subscribe for presence notifications, and otherwise communicate with one another by using SIP applications such as Lync. Lync Server allows for three types of federation: 1) direct federation between your organization and another; 2) federation between your organization and a public provider; and, 3) federation between your organization and a third-party hosting provider.

Setting up direct federation with another organization involves several tasks. To begin with, you must configure the Lync Server Access Edge service to allow federation. In addition, the other organization must enable federation with you; federation cannot be established unless both parties agree to the relationship.

To set up a federated relationship you might also need to manage two federation-related lists: the allowed list and the blocked list. The allowed list represents the organizations you have chosen to federate with; if a domain appears on the allowed list then (depending on your configuration settings) your users will be able to exchange instant messages and presence information with users who have accounts in that federated domain. Conversely, the blocked list represents domains that users are expressly forbidden from federating with; for example, messages sent from a blocked domain will automatically be rejected by Lync Server.

The **Get-CsBlockedDomain** cmdlet enables you to return information about the domains that appear on the blocked domain list.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsBlockedDomain** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsBlockedDomain"}

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
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to use wildcard characters in order to return one or more domains from the list of blocked domains. To return all the domains that have an Identity that begins with the letter &quot;r&quot; use this syntax: -Filter r*. To return all the domains that have an Identity that ends with &quot;.net&quot; use this syntax: -Filter &quot;*.net&quot;. To return all the domains that have an Identity that begins with the letter &quot;f&quot; or with the letter &quot;g&quot; use this syntax: -Filter [fg]*.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Name of the domain to be returned. Domains are listed on the blocked list by their fully qualified domain name (FQDN); thus the Identity for a given domain will be similar to fabrikam.com or contoso.net. Note that you cannot use wildcards when specifying a domain Identity. To use wildcards to return a given domain (or set of domains), use the Filter parameter instead.</p>
<p>If this parameter is not specified, then all the domains on the blocked domain list will be returned.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the blocked domain data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsBlockedDomain** cmdlet does not accept pipelined input.

## Return Types

Returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Edge.BlockedDomain object.

## 另请参阅

#### 其他资源

[New-CsBlockedDomain](new-csblockeddomain.md)  
[Remove-CsBlockedDomain](remove-csblockeddomain.md)  
[Set-CsAccessEdgeConfiguration](set-csaccessedgeconfiguration.md)  
[Set-CsBlockedDomain](set-csblockeddomain.md)

