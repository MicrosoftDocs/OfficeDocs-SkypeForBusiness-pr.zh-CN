﻿---
title: Remove-CsRgsHoursOfBusiness
TOCTitle: Remove-CsRgsHoursOfBusiness
ms:assetid: 753b2cd7-709b-455b-85a3-8b80ea35d4e0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398568(v=OCS.15)
ms:contentKeyID: 49313270
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsRgsHoursOfBusiness

 

_**上一次修改主题：** 2015-03-09_

Removes an existing set of Response Group business hours. Business hours are used to indicate the days of the week and the times of day when Response Group agents are typically available to answer phone calls. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsRgsHoursOfBusiness -Instance <BusinessHours> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 removes all the business hour sets found on the service ApplicationServer:atl-cs-001.litwareinc.com. To do this, the command first calls **Get-CsRgsHoursOfBusiness** to return all the business hour sets found on the service ApplicationServer:atl-cs-001.litwareinc.com. These sets are then piped to the **Remove-CsRgsHoursOfBusiness** cmdlet, which deletes each business hours set that is passed to it.

    Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" | Remove-CsRgsHoursOfBusiness

## EXAMPLE 2

In Example 2, a single set of business hours is removed from ApplicationServer:atl-cs-001.litwareinc.com: the collection named Help Desk Business Hours.

    Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" -Name "Help Desk Business Hours" | Remove-CsRgsHoursOfBusiness

## EXAMPLE 3

Example 3 deletes all the business hour sets that have business hours configured for Sundays. To do this, the command first calls **Get-CsRgsHoursOfBusiness** to return all the business hour sets found on ApplicationServer:atl-cs-001.litwareinc.com. These sets are then piped to the **Where-Object** cmdlet, which selects only those items where one of the following criteria is true: the SundayTimeRange1 property is not equal to a null value, or the SundayTimeRange2 property is not equal to a null value. (If a time range property is not null, then that means business hours have been configured for that time interval.) Any set that meets at least one of those criteria is then piped to the **Remove-CsRgsHoursOfBusiness** cmdlet, which removes that set of business hours.

    Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" | Where-Object {$_.SundayTimeRange1 -ne $Null -or $_.SundayTimeRange2 -ne $Null} | Remove-CsRgsHoursOfBusiness

## EXAMPLE 4

The command shown in Example 4 deletes all the custom business hour sets (that is, sets that cannot be shared among workflows). To carry out this task, the command first uses **Get-CsRgsHoursOfBusiness** to return all the business hour sets found on ApplicationServer:atl-cs-001.litwareinc.com. This data is then piped to the **Where-Object** cmdlet, which picks out only those sets where the Custom property is equal to True. These sets are then piped to, and deleted by, **Remove-CsRgsHoursOfBusiness**.

    Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" | Where-Object {$_.Custom -eq $True} | Remove-CsRgsHoursOfBusiness -Force

## Detailed Description

In order to provide callers with the best possible experience, the 响应组应用程序 makes it possible for you to clearly define when Response Group agents are available to answer calls and when they are not available to answer calls. With the 响应组应用程序, you can define business hours; these hours indicate the days of the week and the hours of the day that agents are available to answer calls. For example, if your organization is typically open from 9:00 A.M. to 5:00 P.M. Monday through Friday, then you would configure business hours that show that agents are available from 9:00 A.M. to 5:00 P.M. Monday through Friday (and, by extension, that agents are not available at, say, 8:00 P.M. on a Thursday or 2:30 P.M. on a Sunday).

New business hour sets can be created by using the **New-CsRgsHoursOfBusiness** cmdlet; these sets can later be removed by using the **Remove-CsRgsHoursOfBusiness** cmdlet. Note that, when you call **Remove-CsRgsHoursOfBusiness**, the entire set of hours is removed and is no longer available for use. If all you want to do is remove business hours for a particular day (for example, because your help desk is no longer open on Sundays), you should use **Set-CsRgsHoursOfBusiness** to remove only the applicable values from a collection.

By default, **Remove-CsRgsHoursOfBusiness** prompts you if you attempt to delete a business hours set currently in use by an active workflow. That prompt asks you to verify that you want to remove the collection, and no action will be taken until you respond to the prompt. To bypass this prompt, and to silently delete business hour sets, even if those sets are currently assigned to an active workflow, add the Force parameter. For example:

Get-CsRgsHoursOfBusiness –Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" | Remove-CsRgsHoursOfBusiness –Force

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsRgsHoursOfBusiness** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsRgsHoursOfBusiness"}

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
<td><p><em>Instance</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.BusinessHours</p></td>
<td><p>Object reference pointing to the business hours set to be removed. When piping workflow objects to <strong>Remove-CsRgsHoursOfBusiness</strong> you can leave off the Instance parameter.</p>
<p>To use the Instance parameter use commands similar to this:</p>
<p>$x = Get-CsRgsHoursOfBusiness –Identity ApplicationServer:atl-cs-001.litwareinc.com /1987d3c2-4544-489d-bbe3-59f79f530a83</p>
<p>Remove-CsRgsHoursOfBusiness –Instance $x</p>
<p>Note that you can only remove a single business hours set at a time when using the Instance parameter. That means that your object reference ($x) cannot contain multiple business hour objects.</p></td>
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
<td><p>Forces the deletion of a business hours set. If this parameter is present, the set will be deleted without warning, even if the set is currently assigned to an active workflow. If this parameter is not present then you will be asked to confirm the deletion of any business hours set currently assigned to an active workflow.</p></td>
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

Microsoft.Rtc.Rgs.Management.WritableSettings.BusinessHours object. **Remove-CsRgsHoursOfBusiness** accepts pipelined instances of the Response Group business hours object.

## Return Types

Deletes existing instances of the Microsoft.Rtc.Rgs.Management.WritableSettings.BusinessHours object.

## 另请参阅

#### 其他资源

[Get-CsRgsHoursOfBusiness](get-csrgshoursofbusiness.md)  
[New-CsRgsHoursOfBusiness](new-csrgshoursofbusiness.md)  
[Set-CsRgsHoursOfBusiness](set-csrgshoursofbusiness.md)

