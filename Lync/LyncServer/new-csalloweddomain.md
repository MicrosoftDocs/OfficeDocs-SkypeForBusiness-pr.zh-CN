---
title: New-CsAllowedDomain
TOCTitle: New-CsAllowedDomain
ms:assetid: 7e040cf8-8e6f-4293-b7c4-1be76053d43d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398628(v=OCS.15)
ms:contentKeyID: 49313384
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsAllowedDomain

 

_**上一次修改主题：** 2015-03-09_

Adds a domain to the list of domains approved for federation. After a domain has been approved for federation (by being added to the allowed list), your users can exchange instant messages and presence information with people who have accounts in the federated domain. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsAllowedDomain -Identity <XdsGlobalRelativeIdentity> <COMMON PARAMETERS>

    New-CsAllowedDomain -Domain <String> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Comment <String>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-MarkForMonitoring <$true | $false>] [-ProxyFqdn <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the domain fabrikam.com is added to the list of allowed domains. To do this, the **New-CsAllowedDomain** cmdlet is called, along with the Identity parameter; this parameter is assigned the name of the domain to be added to the allowed list. Note that this command will fail if fabrikam.com is already on the allowed list or on the blocked list.

    New-CsAllowedDomain -Identity "fabrikam.com"

## EXAMPLE 2

Example 2 is a variation of the command shown in Example 1. In this case, however, two additional parameters are included along with Identity: ProxyFqdn is used to specify the FQDN of the proxy server for fabrikam.com, and MarkForMonitoring is used to add this federation connection to the list of items monitored by 监控服务器.

    New-CsAllowedDomain -Identity "fabrikam.com" -ProxyFqdn "proxyserver.fabrikam.com" -MarkForMonitoring $True -Comment "Contact: Ken Myer (kenmyer@fabrikam.com)"

## EXAMPLE 3

Example 3 demonstrates how you can use the InMemory parameter to create a new allowed domain that initially exists only in memory. After you modify the property values of this in-memory-only domain, you can then call the **Set-CsAllowedDomain** cmdlet to add the domain to the allowed list.

In order to do this, the first command in the example uses the **New-CsAllowedDomain** cmdlet and the InMemory parameter to create an allowed domain that has the Identity fabrikam.com. After that, the virtual domain is stored in the variable $x.

Lines 2, 3, and 4 are used to modify the values of the ProxyFqdn, MarkForMonitoring, and Comment properties, respectively. After all of the property values have been modified, the final command uses the **Set-CsAllowedDomain** cmdlet to add the virtual domain to the allowed domain list. Keep in mind that, until the **Set-CsAllowedDomain** cmdlet is called, fabrikam.com exists only in memory: if you run the **Get-CsAllowedDomain** cmdlet any time prior to the last line in the example, fabrikam.com will not appear on the list of allowed domains. Fabrikam.com will not show up on the allowed list until after you have called the **Set-CsAllowedDomain** cmdlet.

    $x = New-CsAllowedDomain -Identity "fabrikam.com" -InMemory
    $x.ProxyFqdn = "proxyserver.fabrikam.com" 
    $x.MarkForMonitoring = $True 
    $x.Comment = "Contact: Ken Myer (kenmyer@fabrikam.com)"
    Set-CsAllowedDomain -Instance $x

## Detailed Description

Federation is a means by which two organizations can set up a trust relationship that facilitates communication between the two groups. When federation has been established, users in the two organizations can send each other instant messages, subscribe for presence notifications, and otherwise communicate with one another by using SIP applications such as Lync. Lync Server allows for three types of federation: 1) direct federation between your organization and another; 2) federation between your organization and a public provider; and, 3) federation between your organization and a third-party hosting provider.

Setting up direct federation with another organization involves several tasks. To begin with, you must enable your servers running the Lync Server Access Edge service to allow federation. In addition, the other organization must enable federation with you; federation cannot be established unless both parties agree to the relationship.

To establish a federated relationship you might also need to manage two federation-related lists: the allowed list and the blocked list. The allowed list represents the organizations you have chosen to federate with; if a domain appears on the allowed list then (depending on your configuration settings) your users will be able to exchange instant messages and presence information with users who have accounts in that federated domain. Conversely, the blocked list represents domains that users are expressly forbidden from federating with; for example, messages sent from a blocked domain will automatically be rejected by Lync Server.

If you want to create a new federation relationship, you can use the **New-CsAllowedDomain** cmdlet to add a domain to the list of allowed domains.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsAllowedDomain** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsAllowedDomain"}

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
<td><p>FQDN (for example, fabrikam.com) of the domain to be added to the allowed list. You can use either the Identity or the Domain parameter (but not both) in order to specify the domain name. If you use Identity, the Domain property will be set to the same value assigned to Identity. If you use Domain, the Identity property will be set to the same value assigned to Domain.</p>
<p>Note that Domains must be unique: if the specified domain already exists on either the blocked or the allowed list, your command will fail.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Fully qualified domain name (FQDN) of the domain to be added to the allowed list; for example, fabrikam.com. You can use either the Identity or the Domain parameter (but not both) in order to specify the domain name. If you use Identity, the Domain property will be set to the same value assigned to Identity. If you use Domain, the Identity property will be set to the same value assigned to Domain.</p>
<p>Note that Identities must be unique: if the specified domain already exists on either the blocked or the allowed list, your command will fail.</p></td>
</tr>
<tr class="odd">
<td><p><em>Comment</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Optional string value that provides additional information about the domain being added to the allowed list. For example, you might add a Comment that provides contact information for the federated domain.</p></td>
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
<td><p><em>MarkForMonitoring</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or not the federation connection between your domain and the remote domain will be monitored by Monitoring Server. By default, MarkForMonitoring is set to False, meaning that the connection will not be monitored.</p>
<p>This property will be ignored if you have not deployed Monitoring Server.</p></td>
</tr>
<tr class="even">
<td><p><em>ProxyFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>FQDN (for example, proxy-server.fabrikam.com) of the SIP proxy server deployed in the domain being added to the allowed list. This property is optional: if it is not specified then DNS SRV discovery procedures will be used to determine the location of the SIP proxy server.</p></td>
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

None. The **New-CsAllowedDomain** cmdlet does not accept pipelined input.

## Return Types

Creates instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Edge.AllowedDomain object.

## 另请参阅

#### 其他资源

[Get-CsAllowedDomain](get-csalloweddomain.md)  
[Remove-CsAllowedDomain](remove-csalloweddomain.md)  
[Set-CsAccessEdgeConfiguration](set-csaccessedgeconfiguration.md)  
[Set-CsAllowedDomain](set-csalloweddomain.md)

