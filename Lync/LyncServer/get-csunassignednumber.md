---
title: Get-CsUnassignedNumber
TOCTitle: Get-CsUnassignedNumber
ms:assetid: a8e5cfc1-e7a0-4917-9cd9-f541fedb3a61
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412792(v=OCS.15)
ms:contentKeyID: 49313866
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsUnassignedNumber

 

_**上一次修改主题：** 2015-03-09_

Retrieves one or more ranges of unassigned numbers and the routing rules that apply to those numbers. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsUnassignedNumber [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsUnassignedNumber [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

Example 1 returns a collection of all the unassigned numbers configured for use in your organization.

    Get-CsUnassignedNumber

## EXAMPLE 2

In Example 2, the Identity parameter is used to limit the retrieved data to unassigned numbers that have the Identity UNSet1. Because identities must be unique, this command will return only the specified unassigned number range.

    Get-CsUnassignedNumber -Identity UNSet1

## EXAMPLE 3

This example uses the Filter parameter to return a collection of all the unassigned number settings with Identity values that include the string Redmond. For example, this command would return unassigned number setting with identities such as Redmond Numbers, Unassigned Redmond Numbers, UNRedmond, etc.

    Get-CsUnassignedNumber -Filter *Redmond*

## EXAMPLE 4

In Example 4, the **Get-CsUnassignedNumber** cmdlet and the **Where-Object** cmdlet are used to retrieve a collection of all the unassigned number settings that include the word Welcome in the name of the Announcement. To do this, the command first uses the **Get-CsUnassignedNumber** cmdlet to retrieve all the unassigned number settings. That collection is then piped to the **Where-Object**cmdlet, which applies a filter that limits the returned data to unassigned numbers that have the word Welcome somewhere in the name of the assigned announcement.

    Get-CsUnassignedNumber | Where-Object {$_.AnnouncementName -match "Welcome"}

## Detailed Description

Unassigned numbers are phone numbers that have been assigned to an organization but that have not been assigned to specific users or phones. Lync Server can be set up to route calls to appropriate destinations when an unassigned number is called. This cmdlet retrieves one or more unassigned number ranges that define that routing.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsUnassignedNumber** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins, RTCUniversalReadOnlyAdmin. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsUnassignedNumber"}

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
<td><p>Performs a wildcard search that allows you to narrow down your results to only those unassigned number settings whose identities match the given wildcard string.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>The unique name of the unassigned number range to retrieve.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the unassigned number information from the local replica of the 中央管理存储, rather than the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

Returns an object of type Microsoft.Rtc.Management.Voice.Helpers.DisplayAnnouncementVacantNumberRange.

## 另请参阅

#### 其他资源

[New-CsUnassignedNumber](new-csunassignednumber.md)  
[Remove-CsUnassignedNumber](remove-csunassignednumber.md)  
[Set-CsUnassignedNumber](set-csunassignednumber.md)

