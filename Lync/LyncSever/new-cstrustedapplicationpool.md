﻿---
title: New-CsTrustedApplicationPool
TOCTitle: New-CsTrustedApplicationPool
ms:assetid: 30117225-d82b-494b-8bc2-da5d539bdd6b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425804(v=OCS.15)
ms:contentKeyID: 49312388
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsTrustedApplicationPool

 

_**上一次修改主题：** 2015-03-09_

Creates a new pool that will contain the computers that host trusted applications. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsTrustedApplicationPool -Identity <XdsGlobalRelativeIdentity> [-AppSharingPortCount <UInt16>] [-AppSharingPortStart <UInt16>] [-AudioPortCount <UInt16>] [-AudioPortStart <UInt16>] [-ComputerFqdn <Fqdn>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-OutboundOnly <$true | $false>] [-Registrar <String>] [-RequiresReplication <$true | $false>] [-Site <String>] [-ThrottleAsServer <$true | $false>] [-TreatAsAuthenticated <$true | $false>] [-VideoPortCount <UInt16>] [-VideoPortStart <UInt16>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example creates a new pool with the FQDN TrustPool.litwareinc.com. We use the Identity parameter to specify the new FQDN. We use the Registrar parameter with a value of pool0.litwareinc.com to associate the new pool with the Registrar service at that FQDN. Finally, we use the Site parameter with a value of Redmond to specify that this pool will be part of the Redmond site.

Note that the Site value is the SiteId (which can be retrieved by calling the **Get-CsSite** cmdlet). However, the site Identity will be stored with the new trusted application pool. For example, if a site has an Identity of site:Redmond1 and a SiteId of NA, you must use NA as the value of the Site parameter in your call to the **New-CsTrustedApplicationPool** cmdlet. However, if you want to later find all trusted application pools for the NA site, you would use the Identity value in your where clause, like this:

Get-CsTrustedApplicationPool | Where-Object {$\_.SiteId –eq "site:Redmond1"}

    New-CsTrustedApplicationPool -Identity TrustPool.litwareinc.com -Registrar pool0.litwareinc.com -Site Redmond

## EXAMPLE 2

Example 2 is identical to Example 1 except that instead of specifying an FQDN for the Registrar service we’ve used the service ID, Registrar:redmond.litwareinc.com. In addition, we’ve specified a value for the ComputerFqdn parameter. When a pool is created, a computer is also created within that pool. By default the computer will have the same FQDN as the pool. We’ve specified a different FQDN, AppServer.litwareinc.com, for the computer that is in this pool.

    New-CsTrustedApplicationPool -Identity TrustPool.litwareinc.com -Registrar Registrar:redmond.litwareinc.com -Site Redmond -ComputerFqdn AppServer.litwareinc.com

## Detailed Description

We recommend that the computers that are running trusted applications within a Lync Server deployment be added to a separate pool that is only for trusted applications. However, you can add trusted application computers to an existing pool that is also used for other purposes. If the pool already exists as part of the topology, this cmdlet creates the external service associated with that pool (with a service role of ExternalServer). If the pool does not exist, this cmdlet creates the pool and the corresponding service. (You can find a list of all existing pools by calling the **Get-CsPool** cmdlet.)

Creating a new trusted application pool (a new external service) also creates a new trusted application computer assigned to that pool. By default the computer will be assigned the same fully qualified domain name (FQDN) as the pool. However, you can specify your own value for the FQDN by using the ComputerFqdn parameter of this cmdlet. If you plan to add more computers to the pool, you must specify a ComputerFqdn value that is different from the FQDN of the pool. To add more computers to the pool, call the **New-CsTrustedApplicationComputer** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsTrustedApplicationPool** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsTrustedApplicationPool"}

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
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>The FQDN of the new pool. Note that while the Identity value for creating a pool is the pool FQDN, the value that will be stored as the Identity with the new pool is actually an automatically generated service ID of the pool. The Identity entered here will be saved as the PoolFqdn.</p></td>
</tr>
<tr class="even">
<td><p><em>AppSharingPortCount</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>The number of ports available in the port range for application sharing connections.</p>
<p>Default: 0</p></td>
</tr>
<tr class="odd">
<td><p><em>AppSharingPortStart</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>The number of the first port in the port range available for application sharing connections.</p></td>
</tr>
<tr class="even">
<td><p><em>AudioPortCount</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>The number of ports available in the port range for audio connections.</p>
<p>Default: 0</p></td>
</tr>
<tr class="odd">
<td><p><em>AudioPortStart</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>The number of the first port in the port range available for audio connections.</p></td>
</tr>
<tr class="even">
<td><p><em>ComputerFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Creating a trusted application pool will automatically create a trusted application computer that is part of that pool. By default the computer will receive the same FQDN as the pool. Enter a value in this parameter to specify an FQDN for the computer that is different from the pool FQDN. If you plan to add more computers to the pool, you must enter a value for this parameter that is different from the pool FQDN.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="odd">
<td><p><em>OutboundOnly</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Specifies whether a trusted application can initiate a connection to a server within the pool. Set this value to True if you want all connections to be initiated by the server rather than the application.</p>
<p>Default: False</p></td>
</tr>
<tr class="even">
<td><p><em>Registrar</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The service ID or FQDN of the Registrar service for the pool.</p>
<p>Note that even though this parameter is optional, if you attempt to create a new trusted application endpoint (by using the <strong>New-CsTrustedApplicationEndpoint</strong> cmdlet) and assign the endpoint to a pool that does not have a Registrar dependency, you'll receive an error and the endpoint will not be created. In addition, you cannot remove a trusted application pool that is not associated with a Registrar.</p></td>
</tr>
<tr class="odd">
<td><p><em>RequiresReplication</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Determines whether replication is required for this pool. Set this value to False if replication is not required. You would usually set this parameter to False for Microsoft Outlook Web Access and manually-provisioned applications.</p>
<p>Default: True</p></td>
</tr>
<tr class="even">
<td><p><em>Site</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The Site ID of the site on which this pool is homed. Call the <strong>Get-CsSite</strong> cmdlet to retrieve the SiteId property of a site. Keep in mind that you must use the SiteId property rather than the Identity of the site. Also note that you must not precede the SiteId with the string “site:”, you must enter only the SiteId. In addition, although you enter the SiteId retrieved from the <strong>Get-CsSite</strong> cmdlet, the SiteId property of the new trusted application pool will contain the site Identity. For example, if the SiteId for the site is Main and the site Identity is site:Redmond1, you must enter -Site Main in your call to the <strong>New-CsTrustedApplicationPool</strong> cmdlet, but a subsequent call to the <strong>Get-CsTrustedApplicationPool</strong> cmdlet will show the SiteId as site:Redmond1.</p>
<p>If the pool specified in the Identity already exists you do not need to specify a Site. If the pool doesn’t exist, this parameter is required.</p></td>
</tr>
<tr class="odd">
<td><p><em>ThrottleAsServer</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Set this parameter to false to throttle connections between the servers within the pool and trusted applications as clients. This places greater restrictions on the connections than the default True, which throttles connections as servers. Throttling a connection places restrictions on the number of transactions that can occur at once.</p>
<p>Default: True</p></td>
</tr>
<tr class="even">
<td><p><em>TreatAsAuthenticated</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Determines whether authentication is required for trusted applications connecting to servers within the pool. Set this parameter to False if you want to require trusted applications to be authenticated. The default value of True allows the trusted applications to connect under the assumption they’ve already been authenticated.</p>
<p>Default: True</p></td>
</tr>
<tr class="odd">
<td><p><em>VideoPortCount</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>The number of ports available in the port range for video connections.</p>
<p>Default: 0</p></td>
</tr>
<tr class="even">
<td><p><em>VideoPortStart</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>The number of the first port in the port range available for video connections.</p></td>
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

None.

## Return Types

Creates an object of type Microsoft.Rtc.Management.Xds.DisplayExternalServer.

## 另请参阅

#### 其他资源

[Remove-CsTrustedApplicationPool](remove-cstrustedapplicationpool.md)  
[Set-CsTrustedApplicationPool](set-cstrustedapplicationpool.md)  
[Get-CsTrustedApplicationPool](get-cstrustedapplicationpool.md)  
[New-CsTrustedApplicationComputer](new-cstrustedapplicationcomputer.md)  
[Get-CsSite](get-cssite.md)

