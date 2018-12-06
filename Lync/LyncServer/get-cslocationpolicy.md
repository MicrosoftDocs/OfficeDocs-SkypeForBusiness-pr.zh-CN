---
title: Get-CsLocationPolicy
TOCTitle: Get-CsLocationPolicy
ms:assetid: d338af1b-3865-4010-a7fc-d5841c515ae6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398911(v=OCS.15)
ms:contentKeyID: 49314336
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsLocationPolicy

 

_**上一次修改主题：** 2015-03-09_

Returns information about how (or if) the Enhanced 9-1-1 (E9-1-1) 位置信息服务 has been configured. The E9-1-1 service enables those who answer emergency calls to determine the caller’s geographic location. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsLocationPolicy [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsLocationPolicy [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

Example 1 returns a collection of all the location policies currently in use in your organization. This is done simply by calling the **Get-CsLocationPolicy** cmdlet without any parameters.

    Get-CsLocationPolicy

## EXAMPLE 2

The command shown in Example 2 returns only those location policies that have an Identity equal to Reno. Because identities must be unique, this command will only return, at most, one location policy.

    Get-CsLocationPolicy -Identity Reno

## EXAMPLE 3

Example 3 uses the Filter parameter to return all the location policies that have been configured at the per-use scope. (Policies configured at the per-user scope can be directly assigned to users and network sites.) The wildcard string tag:\* tells the **Get-CsLocationPolicy** cmdlet that the returned data should be limited to those location policies that have an Identity that begins with the string value tag:. Even though you don’t need to specify the tag: prefix when retrieving an individual policy, you can use that prefix to filter on all per-user policies.

    Get-CsLocationPolicy -Filter tag:*

## EXAMPLE 4

Example 4 returns a collection of all the location policies where enhanced emergency services are disabled. To do this, the command first uses the **Get-CsLocationPolicy** cmdlet to return a collection of all the location policies currently in use in the organization. That collection is then piped to the **Where-Object** cmdlet; in turn, the **Where-Object** cmdlet applies a filter that limits the returned data to those policies where the EnhancedEmergencyServicesEnabled property is equal to (-eq) False ($False).

    Get-CsLocationPolicy | Where-Object {$_.EnhancedEmergencyServicesEnabled -eq $False}

## Detailed Description

The location policy is used to apply settings that relate to E9-1-1 functionality. The location policy determines whether a user is enabled for E9-1-1, and if so what the behavior is of an emergency call. For example, you can use the location policy to define what number constitutes an emergency call (911 in the United States), whether corporate security should be automatically notified, how the call should be routed, and so on. This cmdlet retrieves one or more location policies.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsLocationPolicy** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsLocationPolicy"}

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
<td><p>A string containing wildcard characters that will retrieve location policies based on matching the Identity value of the policy to the wildcard string.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>The unique identifier of the location policy you want to retrieve. To retrieve the global location policy, use a value of Global. For a policy created at the site scope, this value will be in the form site:&lt;site name&gt;, where site name is the name of a site defined in the Lync Server deployment (for example, site:Redmond). For a policy created at the per-user scope, this value will simply be the name of the policy, such as Reno.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the location policy information from the local replica of the 中央管理存储, rather than the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

The **Get-CsLocationPolicy** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Policy.Location.LocationPolicy object.

## 另请参阅

#### 其他资源

[New-CsLocationPolicy](new-cslocationpolicy.md)  
[Remove-CsLocationPolicy](remove-cslocationpolicy.md)  
[Set-CsLocationPolicy](set-cslocationpolicy.md)  
[Grant-CsLocationPolicy](grant-cslocationpolicy.md)  
[Test-CsLocationPolicy](test-cslocationpolicy.md)

