---
title: New-CsRgsHoursOfBusiness
TOCTitle: New-CsRgsHoursOfBusiness
ms:assetid: 21869ba6-526e-4c70-b84d-de73536d8a43
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398291(v=OCS.15)
ms:contentKeyID: 49312231
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsRgsHoursOfBusiness

 

_**上一次修改主题：** 2015-03-09_

Creates a new set of 响应组应用程序 business hours. Business hour sets are used to indicate the days of the week and the times of day when Response Group agents are typically available to answer phone calls. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsRgsHoursOfBusiness -Name <String> -Parent <RgsIdentity> [-Confirm [<SwitchParameter>]] [-Custom <$true | $false>] [-Force <SwitchParameter>] [-FridayHours1 <TimeRange>] [-FridayHours2 <TimeRange>] [-InMemory <SwitchParameter>] [-MondayHours1 <TimeRange>] [-MondayHours2 <TimeRange>] [-SaturdayHours1 <TimeRange>] [-SaturdayHours2 <TimeRange>] [-SundayHours1 <TimeRange>] [-SundayHours2 <TimeRange>] [-ThursdayHours1 <TimeRange>] [-ThursdayHours2 <TimeRange>] [-TuesdayHours1 <TimeRange>] [-TuesdayHours2 <TimeRange>] [-WednesdayHours1 <TimeRange>] [-WednesdayHours2 <TimeRange>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 creates a new business hours set named Help Desk Business Hours on ApplicationServer:atl-cs-001.litwareinc.com. In this example, no business hours are configured for the set.

    New-CsRgsHoursOfBusiness -Parent "service:ApplicationServer:atl-cs-001.litwareinc.com" -Name "Help Desk Business Hours" 

## EXAMPLE 2

In Example 2, a new business hours set named Help Desk Business Hours is created on ApplicationServer:atl-cs-001.litwareinc.com. In this example, business hours are configured for each day of the week, Monday through Friday. To do this, the first command in the example uses the **New-CsRgsTimeRange** command to create a time range with an OpenTime of 8:00 AM (8:00) and a CloseTime of 6:00 PM (18:00). This time range is stored in a variable named $weekday.

The second command in the example then creates the new business hours set. In addition to specifying the set’s Parent and Name, additional parameters (such as MondayHours1) are used to configure business hours for the weekdays Monday through Friday. In each case, those business hours are set to 8:00 A.M. to 6:00 P.M., and by using the time range variable $weekday.

    $weekday = New-CsRgsTimeRange -Name "Weekday Hours" -OpenTime "8:00" -CloseTime "18:00" 
    
    New-CsRgsHoursOfBusiness -Parent "service:ApplicationServer:atl-cs-001.litwareinc.com" -Name "Help Desk Business Hours" -MondayHours1 $weekday -TuesdayHours1 $weekday -WednesdayHours1 $weekday -ThursdayHours1 $weekday -FridayHours1 $weekday

## Detailed Description

In order to provide callers with the best possible experience, the 响应组应用程序 makes it possible for you to clearly define when Response Group agents are available to answer calls and when they are not available to answer calls. With the 响应组应用程序, you can define business hours; these hours indicate the days of the week and hours of the day that agents are available to answer calls. For example, if your organization is typically open from 9:00 A.M. to 5:00 P.M. Monday through Friday then you would configure business hours that show that agents are available from 9:00 A.M. to 5:00 P.M. Monday through Friday (and, by extension, that agents are not available at, say, 8:00 P.M. on a Thursday or 2:30 P.M. on a Sunday).

New business hour sets are created by using the **New-CsRgsHoursOfBusiness** cmdlet. When configuring business hours within a business hour set, keep in mind that each day of the week has both an Hours1 and an Hours2 property. If your help desk is open from 8:00 A.M to 5:00 P.M., you only need to assign values to the appropriate Hours1 property. However, suppose the help desk is open from 8:00 A.M. to 2:00 P.M., then open again from 5:00 P.M. until 11:00 P.M.. In that case you need to assign the time range 8:00 A.M. to 2:00 P.M. to Hours1 and 5:00 P.M. to 11:00 P.M. to Hours2.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsRgsHoursOfBusiness** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsRgsHoursOfBusiness"}

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
<td><p><em>Name</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Unique name to be assigned to the business hours set. The combination of the Parent property and the Name property enables you to uniquely identify business hour sets without having to refer to the collection’s globally unique identifier (GUID).</p></td>
</tr>
<tr class="even">
<td><p><em>Parent</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.RgsIdentity</p></td>
<td><p>Service where the new business hours set will be hosted. For example: -Parent &quot;service:ApplicationServer:atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Custom</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If set to True, the business hours can only be used by the specified workflow. If set to False (the default value) the business hours can be shared among multiple workflows.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>FridayHours1</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.TimeRange</p></td>
<td><p>First set of opening and closing times for Friday. If your organization is open from, say, 9:00 A.M. to 5:00 P.M. every Friday then you will only need to configure a single time range. However, if your organization is open from 8:00 A.M. to noon, closes for an hour lunch, then is open again from 1:00 P.M. to 5:00 P.M., you will need to create two time ranges for Friday.</p>
<p>If your organization is closed on Fridays, then do not configure a value for either FridayHours1 or FridayHours2.</p></td>
</tr>
<tr class="odd">
<td><p><em>FridayHours2</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.TimeRange</p></td>
<td><p>Second set of opening and closing times for Friday. If your organization is open from, say, 9:00 A.M. to 5:00 P.M. every Friday then you will only need to configure a single time range. However, if your organization is open from 8:00 A.M. to noon, closes for an hour lunch, then is open again from 1:00 P.M. to 5:00 P.M., you will need to create two time ranges for Friday.</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="odd">
<td><p><em>MondayHours1</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.TimeRange</p></td>
<td><p>First set of opening and closing times for Monday. If your organization is open from, say, 9:00 A.M. to 5:00 P.M. every Monday then you will only need to configure a single time range. However, if your organization is open from 8:00 A.M. to noon, closes for an hour lunch, then is open again from 1:00 P.M. to 5:00 P.M., you will need to create two time ranges for Monday.</p>
<p>If your organization is closed on Mondays, then do not configure a value for either MondayHours1 or MondayHours2.</p></td>
</tr>
<tr class="even">
<td><p><em>MondayHours2</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.TimeRange</p></td>
<td><p>Second set of opening and closing times for Monday. If your organization is open from, say, 9:00 A.M. to 5:00 P.M. every Monday then you will only need to configure a single time range. However, if your organization is open from 8:00 A.M. to noon, closes for an hour lunch, then is open again from 1:00 P.M. to 5:00 P.M. you will need to create two time ranges for Monday.</p></td>
</tr>
<tr class="odd">
<td><p><em>SaturdayHours1</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.TimeRange</p></td>
<td><p>First set of opening and closing times for Saturday. If your organization is open from, say, 9:00 A.M. to 5:00 P.M. every Saturday then you will only need to configure a single time range. However, if your organization is open from 8:00 A.M. to noon, closes for an hour lunch, then is open again from 1:00 P.M. to 5:00 P.M., you will need to create two time ranges for Saturday.</p>
<p>If your organization is closed on Saturdays, then do not configure a value for either SaturdayHours1 or SaturdayHours2.</p></td>
</tr>
<tr class="even">
<td><p><em>SaturdayHours2</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.TimeRange</p></td>
<td><p>Second set of opening and closing times for Saturday. If your organization is open from, say, 9:00 A.M. to 5:00 P.M. every Saturday then you will only need to configure a single time range. However, if your organization is open from 8:00 A.M. to noon, closes for an hour lunch, then is open again from 1:00 P.M. to 5:00 P.M., you will need to create two time ranges for Saturday.</p></td>
</tr>
<tr class="odd">
<td><p><em>SundayHours1</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.TimeRange</p></td>
<td><p>First set of opening and closing times for Sunday. If your organization is open from, say, 9:00 A.M. to 5:00 P.M. every Sunday then you will only need to configure a single time range. However, if your organization is open from 8:00 AM to noon, closes for an hour lunch, then is open again from 1:00 P.M. to 5:00 P.M., you will need to create two time ranges for Sunday.</p>
<p>If your organization is closed on Sundays, then do not configure a value for either SundayHours1 or SundayHours2.</p></td>
</tr>
<tr class="even">
<td><p><em>SundayHours2</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.TimeRange</p></td>
<td><p>Second set of opening and closing times for Sunday. If your organization is open from, say, 9:00 A.M. to 5:00 P.M. every Sunday then you will only need to configure a single time range. However, if your organization is open from 8:00 A.M. to noon, closes for an hour lunch, then is open again from 1:00 P.M. to 5:00 P.M. you will need to create two time ranges for Sunday.</p></td>
</tr>
<tr class="odd">
<td><p><em>ThursdayHours1</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.TimeRange</p></td>
<td><p>First set of opening and closing times for Thursday. If your organization is open from, say, 9:00 A.M. to 5:00 P.M. every Thursday then you will only need to configure a single time range. However, if your organization is open from 8:00 A.M. to noon, closes for an hour lunch, then is open again from 1:00 P.M. to 5:00 P.M., you will need to create two time ranges for Thursday.</p>
<p>If your organization is closed on Thursdays, then do not configure a value for either ThursdayHours1 or ThursdayHours2.</p></td>
</tr>
<tr class="even">
<td><p><em>ThursdayHours2</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.TimeRange</p></td>
<td><p>Second set of opening and closing times for Thursday. If your organization is open from, say, 9:00 A.M. to 5:00 P.M. every Thursday then you will only need to configure a single time range. However, if your organization is open from 8:00 A.M. to noon, closes for an hour lunch, then is open again from 1:00 P.M. to 5:00 P.M., you will need to create two time ranges for Thursday.</p></td>
</tr>
<tr class="odd">
<td><p><em>TuesdayHours1</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.TimeRange</p></td>
<td><p>First set of opening and closing times for Tuesday. If your organization is open from, say, 9:00 A.M. to 5:00 P.M. every Tuesday then you will only need to configure a single time range. However, if your organization is open from 8:00 A.M. to noon, closes for an hour lunch, then is open again from 1:00 P.M. to 5:00 P.M., you will need to create two time ranges for Tuesday.</p>
<p>If your organization is closed on Tuesdays, then do not configure a value for either TuesdayHours1 or TuesdayHours2.</p></td>
</tr>
<tr class="even">
<td><p><em>TuesdayHours2</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.TimeRange</p></td>
<td><p>Second set of opening and closing times for Tuesday. If your organization is open from, say, 9:00 A.M. to 5:00 P.M. every Tuesday then you will only need to configure a single time range. However, if your organization is open from 8:00 A.M. to noon, closes for an hour lunch, then is open again from 1:00 P.M. to 5:00 P.M., you will need to create two time ranges for Tuesday.</p></td>
</tr>
<tr class="odd">
<td><p><em>WednesdayHours1</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.TimeRange</p></td>
<td><p>First set of opening and closing times for Wednesday. If your organization is open from, say, 9:00 A.M. to 5:00 P.M. every Wednesday then you will only need to configure a single time range. However, if your organization is open from 8:00 A.M. to noon, closes for an hour lunch, then is open again from 1:00 P.M. to 5:00 P.M., you will need to create two time ranges for Wednesday.</p>
<p>If your organization is closed on Wednesday, then do not configure a value for either WednesdayHours1 or WednesdayHours2.</p></td>
</tr>
<tr class="even">
<td><p><em>WednesdayHours2</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.TimeRange</p></td>
<td><p>Second set of opening and closing times for Wednesday. If your organization is open from, say, 9:00 A.M. to 5:00 P.M. every Wednesday then you will only need to configure a single time range. However, if your organization is open from 8:00 A.M. to noon, closes for an hour lunch, then is open again from 1:00 P.M. to 5:00 P.M., you will need to create two time ranges for Wednesday.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. **New-CsRgsHoursOfBusiness** does not accept pipelined input.

## Return Types

Creates new instances of the Microsoft.Rtc.Rgs.Management.WritableSettings.BusinessHours object.

## 另请参阅

#### 其他资源

[Get-CsRgsHoursOfBusiness](get-csrgshoursofbusiness.md)  
[New-CsRgsTimeRange](new-csrgstimerange.md)  
[Remove-CsRgsHoursOfBusiness](remove-csrgshoursofbusiness.md)  
[Set-CsRgsHoursOfBusiness](set-csrgshoursofbusiness.md)

