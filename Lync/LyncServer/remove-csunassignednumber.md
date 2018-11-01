---
title: Remove-CsUnassignedNumber
TOCTitle: Remove-CsUnassignedNumber
ms:assetid: 13095593-92d3-4790-99a5-5df4610652cb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398209(v=OCS.15)
ms:contentKeyID: 49312066
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsUnassignedNumber

 

_**上一次修改主题：** 2015-03-09_

Removes an existing range of unassigned numbers and the routing rules that apply to those numbers. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsUnassignedNumber -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In this example, the unassigned number settings with the Identity UNSet1 are removed.

    Remove-CsUnassignedNumber -Identity UNSet1

## EXAMPLE 2

Example 2 removes all unassigned number settings where the name of the assigned announcement contains the string Welcome. The command begins with a call to the **Get-CsUnassignedNumber** cmdlet, which returns a collection of all unassigned number settings. This collection is then passed to the **Where-Object** cmdlet, which narrows down the collection to only those unassigned number settings with an AnnouncementName that includes (-match) the string Welcome. Finally, the narrowed-down collection is passed to the **Remove-CsUnassignedNumber** cmdlet, which removes everything left in the collection.

    Get-CsUnassignedNumber | Where-Object {$_.AnnouncementName -match "Welcome"} | Remove-CsUnassignedNumber

## Detailed Description

Unassigned numbers are phone numbers that have been assigned to an organization but that have not been assigned to specific users or phones. Lync Server can be set up to route calls to appropriate destinations when an unassigned number is called. This cmdlet removes the settings that define that routing.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsUnassignedNumber** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsUnassignedNumber"}

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
<td><p>The unique name for the range of unassigned numbers you want to remove.</p></td>
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
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
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

Microsoft.Rtc.Management.Voice.Helpers.DisplayAnnouncementVacantNumberRange object. Accepts pipelined input of unassigned number objects.

## Return Types

This cmdlet does not return a value. It removes an object of type Microsoft.Rtc.Management.Voice.Helpers.DisplayAnnouncementVacantNumberRange.

## 另请参阅

#### 其他资源

[New-CsUnassignedNumber](new-csunassignednumber.md)  
[Set-CsUnassignedNumber](set-csunassignednumber.md)  
[Get-CsUnassignedNumber](get-csunassignednumber.md)  
[Get-CsAnnouncement](get-csannouncement.md)  
[Get-CsExUmContact](get-csexumcontact.md)

