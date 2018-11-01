---
title: Get-CsAllowedDomain
TOCTitle: Get-CsAllowedDomain
ms:assetid: 0b693788-2270-4bf3-b899-f5cf4321351b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398164(v=OCS.15)
ms:contentKeyID: 49311960
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsAllowedDomain

 

_**上一次修改主题：** 2015-03-09_

Returns information about the domains included on the list of domains approved for federation. After a domain has been approved for federation (by being added to the allowed list), your users can exchange instant messages and presence information with people who have accounts in that domain. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsAllowedDomain [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsAllowedDomain [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

The command shown in Example 1 returns a collection of all the domains included in the list of domains approved for federation. Calling the **Get-CsAllowedDomain** cmdlet without any additional parameters always returns the complete collection of approved domains.

    Get-CsAllowedDomain

## EXAMPLE 2

Example 2 returns information about the allowed domain with the Identity "fabrikam.com". Because identities must be unique, this command will never return more than one item.

    Get-CsAllowedDomain -Identity fabrikam.com

## EXAMPLE 3

The command shown in Example 3 returns a collection of all the allowed domains that have the string value "fabrikam" anywhere in their Identity. To do this, the command uses the Filter parameter and the filter value "\*fabrikam\*". This filter value tells the **Get-CsAllowedDomain** cmdlet to return only those domains where the Identity (the only property you can filter on) includes the string value "fabrikam". Domains such as fabrikam.com, fabrikam.net, and africa.fabrikam.org will all be returned by this command.

    Get-CsAllowedDomain -Filter *fabrikam*

## EXAMPLE 4

In Example 4, the **Get-CsAllowedDomain** cmdlet and the **Where-Object** cmdlet are used to return a collection of all the domains where no value has been entered for the ProxyFqdn property. To carry out this task, the **Get-CsAllowedDomain** cmdlet is first called without any additional parameters in order to return a collection of all the allowed domains. This collection is then piped to the **Where-Object** cmdlet, which selects only those allowed domains where the ProxyFqdn property is equal to a null value; a null value means that no value has been entered for ProxyFqdn. To find all the domains that have a value of some kind configured for the ProxyFqdn property, use this syntax instead:

Where-Object {$\_.ProxyFqdn -ne $Null}

    Get-CsAllowedDomain | Where-Object {$_.ProxyFqdn -eq $Null}

## EXAMPLE 5

Example 5 returns all the allowed domains that have their health status checked by the 监控服务器. To do this, the **Get-CsAllowedDomain** cmdlet is first used to return a collection of all the domains on the allowed domains list. That collection is then piped to the **Where-Object** cmdlet, which picks out only those domains where the MarkForMonitoring property is equal to True.

    Get-CsAllowedDomain | Where-Object {$_.MarkForMonitoring -eq $True}

## Detailed Description

Federation is a means by which two organizations can set up a trust relationship that facilitates communication between the two groups. When federation has been established, users in the two organizations can send each other instant messages, subscribe for presence notifications, and otherwise communicate with one another by using SIP applications such as Lync. Lync Server allows for three types of federation: 1) direct federation between your organization and another; 2) federation between your organization and a public provider; and, 3) federation between your organization and a third-party hosting provider.

Setting up direct federation with another organization involves several tasks. To begin with, you must enable your Access Edge servers to allow federation. In addition, the other organization must enable federation with you; federation cannot be established unless both parties agree to the relationship.

To set up a federated relationship you might also need to manage two federation-related lists: the allowed list and the blocked list. The allowed list (required if EnablePartnerDiscovery has been disabled) represents the organizations you have chosen to federate with. If a domain appears on the allowed list then (depending on your configuration settings) your users will be able to exchange instant messages and presence information with users who have accounts in that federated domain. Conversely, the blocked list represents domains that users are expressly forbidden from federating with; for example, messages sent from a blocked domain will automatically be rejected by Lync Server.

The **Get-CsAllowedDomain** cmdlet provides a way for you to return information about all the domains on the allowed domains list.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsAllowedDomain** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsAllowedDomain"}

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
<td><p>Enables you to use wildcard characters in order to return one or more domains from the list of allowed domains. To return all of the domains that have an Identity that begins with the letter &quot;r&quot;, use this syntax: -Filter r*. To return all of the domains that have an Identity that ends with &quot;.net&quot;, use this syntax: -Filter &quot;*.net&quot;. To return all of the domains that have an Identity that begins with the letter &quot;r&quot; or with the letter &quot;g&quot;, use this syntax: -Filter [rg]*.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Name of the domain to be returned. Domains are listed on the allowed list by their fully qualified domain name (FQDN); that means that the Identity for a given domain will be similar to fabrikam.com or contoso.net. Note that you cannot use wildcards when specifying a domain Identity. To use wildcards to return a given domain (or set of domains), use the Filter parameter instead.</p>
<p>If this parameter is not specified, then all of the domains on the allowed domain list will be returned.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the allowed domains from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsAllowedDomain** cmdlet does not accept pipelined input.

## Return Types

Returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Edge.AllowedDomain object.

## 另请参阅

#### 其他资源

[New-CsAllowedDomain](new-csalloweddomain.md)  
[Remove-CsAllowedDomain](remove-csalloweddomain.md)  
[Set-CsAccessEdgeConfiguration](set-csaccessedgeconfiguration.md)  
[Set-CsAllowedDomain](set-csalloweddomain.md)

