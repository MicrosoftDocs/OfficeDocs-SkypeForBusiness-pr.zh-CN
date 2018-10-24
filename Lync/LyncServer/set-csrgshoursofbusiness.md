---
title: Set-CsRgsHoursOfBusiness
TOCTitle: Set-CsRgsHoursOfBusiness
ms:assetid: be976e84-00aa-46d5-94d3-527c4c9f3963
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412929(v=OCS.15)
ms:contentKeyID: 49314105
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsRgsHoursOfBusiness

 

_**上一次修改主题：** 2015-03-09_

Configures an existing set of Response Group business hours. Business hour sets are used to indicate the days of the week and the times of day when Response Group agents are typically available to answer phone calls. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsRgsHoursOfBusiness -Instance <BusinessHours> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 shows you can assign a new time range value to the SaturdayHours1 and SundayHours1 properties of the business hours set Help Desk Business Hours. To do this, the first command in the example uses **New-CsRgsTimeRange** to create a new time range object (Weekend Hours) with an opening time of 12:00 P.M. (12:00) and a closing time of 5:00 P.M. (17:00). This object is stored in a variable named $weekend.

The next command creates an object reference ($x) to the Help Desk Business Hours business hours set on ApplicationServer:atl-cs-001.litwareinc.com. When that command is finished, commands 3 and 4 are used to set the SaturdayHours1 and SundayHours1 properties to the time range value stored in $weekend. Finally, the last command in the example then uses **Set-CsRgsHoursOfBusiness** to write these changes back to the actual business hours set.

    $weekend = New-CsRgsTimeRange -Name "Weekend Hours" -OpenTime "12:00" -CloseTime "17:00"
    
    $x = Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" -Name "Help Desk Business Hours"
    $x.SaturdayHours1 = $weekend
    $x.SundayHours1 = $weekend
    Set-CsRgsHoursOfBusiness -Instance $x

## EXAMPLE 2

The commands shown in Example 2 delete the values configured for the SaturdayHours1 and the SaturdayHours2 properties in the business hours set Help Desk Business Hours. To do, this, first command creates an object reference ($x) to the Help Desk Business Hours business hours set on ApplicationServer:atl-cs-001.litwareinc.com. After the object reference has been created, the second command sets the SaturdayHours1 property to a null value ($Null); this effectively erases any value previously assigned to SaturdayHours1. A similar command is then used to erase any value previously assigned to SaturdayHours2.

The final command in the example then uses **Set-CsRgsHoursOfBusiness** to write these changes back to the actual business hours set. When the command finishes running, there will no longer be any Saturday business hours assigned to Help Desk Business Hours.

    $x = Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" -Name "Help Desk Business Hours"
    $x.SaturdayHours1 = $Null
    $x.SaturdayHours2 = $Null
    
    Set-CsRgsHoursOfBusiness -Instance $x

## Detailed Description

In order to provide callers with the best possible experience, the 响应组应用程序 makes it possible for you to clearly define when Response Group agents are available to answer calls and when they are not available to answer calls. With the 响应组应用程序, you can define business hours; these hours indicate the days of the week and hours of the day that agents are available to answer calls. For example, if your organization is typically open from 9:00 A.M. to 5:00 P.M. Monday through Friday, then you would configure business hours that show that agents are available from 9:00 A.M. to 5:00 P.M. Monday through Friday (and, by extension, that agents are not available at, say, 8:00 P.M. on a Thursday or 2:30 P.M. on a Sunday).

Business hour sets are created by using the **New-CsRgsHoursOfBusiness** cmdlet. After these sets have been created, they can be modified by using the **Set-CsRgsHoursOfBusiness** cmdlet. Typically, this will mean changing the business hours for one or more days of the week. For example, if the help desk used to stay open until 5:00 P.M. on Fridays but now stays open until 7:00 P.M. on Fridays, then you will need to modify the business hours for Friday. If the help desk used to be open on Saturdays but is now closed on Saturdays, you will likewise need to modify the Saturday business hours. (To indicate that a group is not available on a particular day, simply set the business hours for that day to a null value: -SundayTimeRange1 $Null.)

When configuring business hours within a business hours set, keep in mind that each day of the week has both a Hours1 and a Hours2 property. If your help desk is open from 8:00 A.M. to 5:00 P.M., you only need to assign values to the appropriate Hours1 property. However, suppose the help desk is open from 8:00 A.M. to 2:00 P.M., then open again from 5:00 P.M. until 11:00 P.M.. In that case you need to assign the time range 8:00 A.M. to 2:00 P.M. to Hours1 and 5:00 P.M. to 11:00 P.M. to Hours2.

Note that **Set-CsRgsHoursOfBusiness** does not directly modify a business hours set. Instead, you must use **Get-CsRgsHoursOfBusiness** to create an object reference to the set to be modified. (When you create an object reference you simply retrieve a copy of the business hours set and then store that copy in a variable.) After you have created an object reference, you modify the properties of that in-memory-only object. When your modifications are complete, you then use **Set-CsRgsHoursOfBusiness** to write those changes to the actual business hours set.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsRgsHoursOfBusiness** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsRgsHoursOfBusiness"}

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
<td><p>Object reference to the business hours set to be modified. An object reference is typically retrieved by using the <strong>Get-CsRgsHoursOfBusiness</strong> cmdlet and assigning the returned value to a variable; for example, this command returns an object reference to the Help Desk business hours set, and stores that object reference in a variable named $x:</p>
<p>$x = Get-CsRgsHoursOfBusiness -Identity service:ApplicationServer:atl-cs-001.litwareinc.com -Name &quot;Help Desk&quot;</p></td>
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
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

Microsoft.Rtc.Rgs.Management.WritableSettings.BusinessHours object. **Set-CsRgsHoursOfBusiness** accepts pipelined instances of the Response Group business hours object.

## Return Types

Modifies existing instances of the Microsoft.Rtc.Rgs.Management.WriteableSettings.BusinessHours object.

## 另请参阅

#### 其他资源

[Get-CsRgsHoursOfBusiness](get-csrgshoursofbusiness.md)  
[New-CsRgsHoursOfBusiness](new-csrgshoursofbusiness.md)  
[New-CsRgsTimeRange](new-csrgstimerange.md)  
[Remove-CsRgsHoursOfBusiness](remove-csrgshoursofbusiness.md)

