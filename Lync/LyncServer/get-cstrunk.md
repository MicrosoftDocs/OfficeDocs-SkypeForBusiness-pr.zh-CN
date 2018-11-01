---
title: Get-CsTrunk
TOCTitle: Get-CsTrunk
ms:assetid: c49407f2-2e03-4b8b-b51b-75b12ef87fd1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205244(v=OCS.15)
ms:contentKeyID: 49314188
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsTrunk

 

_**上一次修改主题：** 2015-03-09_

Returns information about the SIP trunks employed by your organization. SIP trunks connect the Lync Server 2013 Voice over IP phone network with the Public Switched Telephone Network. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsTrunk [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsTrunk [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-PoolFqdn <String>]

## Examples

## Example 1

The command shown in Example 1 returns information for all the SIP trunks configured for use in your organization.

    Get-CsTrunk

## Example 2

In Example 2, information is returned for a single SIP trunk: the trunk with the Identity PstnGateway:192.168.0.240.

    Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

## Example 3

The command shown in Example 3 returns information for all the SIP trunks found on the pool atl-cs-001.litwareinc.com.

    Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

## Example 4

Example 4 returns information for all the routable SIP trunks. To do this, the command first calls the **Get-CsTrunk** cmdlet without any parameters in order to return a collection of all the available SIP trunks. This collection is then piped to the **Where-Object** cmdlet, which picks out only those trunks where the Routable property is equal to (-eq) True ($True).

    Get-CsTrunk | Where-Object {$_.Routable -eq $True}

## Detailed Description

In Microsoft Lync Server 2010, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway. Each gateway was limited to a single trunk; among other things this made it difficult for administrators to provide resiliency for outbound calls. However, because trunks and PSTN gateways were essentially identical, you could retrieve information about all your trunks by running this command:

Get-CsService -PstnGateway

In Lync Server 2013, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer essentially identical. In turn, that means that, in Lync Server 2013, you cannot retrieve detailed information about individual trunks by using the **Get-CsService** cmdlet. Instead, detailed information about individual trunks is returned by using the new **Get-CsTrunk** cmdlet.

Note that, as far as the Windows PowerShell 命令行接口 is concerned, trunk information is read-only: you cannot create, delete or modify trunks by using PowerShell. Those operations can only be carried out by using Lync Server Topology Builder.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsTrunk"}

**Lync Server 控制面板:** The functions carried out by the **Get-CsTrunk** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Enables you to use wildcard characters in order to return a SIP trunk (or collection of SIP trunks). For example, to return a collection of all the SIP trunks configured as part of the PSTN gateway service use this syntax:</p>
<p>-Filter &quot;PstnGateway:*&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Unique identifier for the SIP trunk to be returned. For example:</p>
<p>–Identity &quot;PstnGateway:192.168.0.240&quot;</p>
<p>Note that you cannot use wildcards when specifying an Identity. If you need to use wildcards, then include the Filter parameter instead.</p>
<p>If this parameter is not specified, then the <strong>Get-CsTrunk</strong> cmdlet returns a collection of all the SIP trunks in use in the organization.</p></td>
</tr>
<tr class="odd">
<td><p><em>PoolFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Fully qualified domain name for the trunk or PSTN gateway as defined in the topology. For example:</p>
<p>-PoolFqdn &quot;atl-trunk-001.litwareinc.com&quot;</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsTrunk** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsTrunk** cmdlet returns instances of the Microsoft.Rtc.Management.Xds.DisplayPstnGateway\#Decorated object.

## 另请参阅

#### 其他资源

[Get-CsTrunkConfiguration](get-cstrunkconfiguration.md)

