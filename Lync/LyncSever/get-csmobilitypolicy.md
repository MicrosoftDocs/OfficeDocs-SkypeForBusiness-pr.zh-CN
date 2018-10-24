---
title: Get-CsMobilityPolicy
TOCTitle: Get-CsMobilityPolicy
ms:assetid: 51ef83de-9cc2-4df8-b4f1-8d816b8de431
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690017(v=OCS.15)
ms:contentKeyID: 49312846
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsMobilityPolicy

 

_**上一次修改主题：** 2015-03-09_

Retrieves information about the mobility policies currently in use in an organization. Mobility policies determine whether or not a user can use Lync Mobile. These policies also manage a user's ability to employ Call via Work, a feature that enables users to make and receive phone calls on their mobile phone by using their work phone number instead of their mobile phone number. Mobility policies can also be used to require Wi-Fi connections when making or receiving calls. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsMobilityPolicy [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsMobilityPolicy [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

The command shown in Example 1 returns information about all the mobility policies configured for use in your organization.

    Get-CsMobilityPolicy

## EXAMPLE 2

Example 2 returns information about a single mobility policy: the policy with the Identity site:Redmond.

    Get-CsMobilityPolicy -Identity "site:Redmond"

## EXAMPLE 3

In Example 3, information is returned for all of your per-user mobility policies. To do this, the Filter parameter is included along with the filter value "tag:\*"; this returns any policy that has an Identity that begins with the string value "tag:". By definition, any policy that has an identity beginning with that string value is a per-user policy.

    Get-CsMobilityPolicy -Filter "tag:*"

## EXAMPLE 4

The command shown in Example 4 limits the returned data to mobility policies where Call via Work has been disabled. To carry out this task, the command first calls the **Get-CsMobilityPolicy** cmdlet without any parameters; that returns a collection of all the mobility policies configured for use in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those policies where the EnableOutsideVoice property is equal to (-eq) False.

    Get-CsMobilityPolicy | Where-Object {$_.EnableOutsideVoice -eq $False}

## Detailed Description

Lync Mobile is a client application that enables users to run Lync on their mobile phones. Call via Work provides a way for users to make calls on their mobile phone and yet have it appear as though the call originated from their work phone number instead of their mobile phone number. Users who have been enabled for Call via Work can achieve this either by dialing directly from their mobile phone or by using the dial-out conferencing option. With dial-out conferencing, a user effectively asks the Lync Server Mobility Service server to make a call for them. The server will set up the call, and then call the user back on their mobile phone. After the user has answered, the server will then dial the party being called. Both of these capabilities can be managed using mobility policies.

With Lync Server 2013 mobile devices can make or receive phone calls by using either the standard cellular phone network. or by using Wi-Fi connections. Mobility policies can be used to require Wi-Fi connections and to prevent calls over the cellular network.

Mobility policies can be configured at the global, site, or the per-user scope, and information about those policies can be retrieved by using the **Get-CsMobilityPolicy** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsMobilityPolicy** cmdlet locally: RTCUniversalServerAdmins.

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
<td><p>Enables you to use wildcard characters when indicating the policy (or policies) to be returned. For example, to return all the policies configured at the site scope use this syntax:</p>
<p>-Filter &quot;site:*&quot;</p>
<p>To return a collection of all the per-user policies, use this syntax:</p>
<p>-Filter &quot;tag:*&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier of the mobility policy to be returned. To refer to the global policy, use this syntax:</p>
<p>-Identity global</p>
<p>To refer to a site policy, use syntax similar to this:</p>
<p>-Identity site:Redmond</p>
<p>To refer to a per-user policy, use syntax similar to this:</p>
<p>-Identity SalesDepartmentPolicy</p>
<p>If this parameter is not specified, then the <strong>Get-CsMobilityPolicy</strong> cmdlet returns a collection of all the mobility policies in use in the organization.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the mobility policy data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Get-CsMobilityPolicy** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsMobilityPolicy** cmdlet returns instances of the Microsoft.Rtc.Management.WriteableConfig.Policy.Mobility.Mobility object.

