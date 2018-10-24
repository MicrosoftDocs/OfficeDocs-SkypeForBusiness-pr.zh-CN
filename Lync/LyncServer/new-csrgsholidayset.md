---
title: New-CsRgsHolidaySet
TOCTitle: New-CsRgsHolidaySet
ms:assetid: 5c110dcf-f596-44ae-8d40-bfafc6701550
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398403(v=OCS.15)
ms:contentKeyID: 49312971
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsRgsHolidaySet

 

_**上一次修改主题：** 2015-03-09_

Creates a new Response Group holiday set. A Response Group holiday set is a collection of holidays. For example, you might have one holiday set for a United States (U.S.)-based queue (a set which might include a holiday for the Fourth of July) and a different set for a queue based in France. The latter queue might define a holiday for Bastille Day but not for the Fourth of July. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsRgsHolidaySet -HolidayList <Collection> -Name <String> -Parent <RgsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The commands shown in Example 1 create a new holiday set named 2013 Holidays and then assign this holiday set a new holiday (New Year’s Day). In order to do this, the first command uses **New-CsRgsHoliday** to create a holiday for New Year’s Day. **New-CsRgsHoliday** takes three parameters: StartDate, which indicates the starting date for the holiday (1/1/2013 12:00 A.M.); EndDate, which represents the end date for the holiday (1/2/2013 12:00 A.M.); and Name, used to store the name assigned to the holiday. The resulting holiday object is stored in the variable $x.

After the new holiday has been created in memory, **New-CsRgsHolidaySet** is employed to create a new holiday set on the service ApplicationServer:atl-cs-001.litwareinc.com. This holiday set is given the name 2013 Holidays (-Name "2013 Holidays") and is assigned the holiday stored in the variable $x: -HolidayList ($x). If you want to assign multiple holidays to the holiday set simply create the new holidays, assigning each to a unique variable. You can then include all those variable names as the parameter value passed to HolidayList:

\-HolidayList($x, $y, $z)

    $x = New-CsRgsHoliday -StartDate "1/1/2013 12:00 AM" -EndDate "1/2/2013 12:00 AM" -Name "New Year's Day"
    New-CsRgsHolidaySet -Parent "service:ApplicationServer:atl-cs-001.litwareinc.com" -Name "2013 Holidays" -HolidayList($x)

## Detailed Description

In order to provide callers with the best possible experience, the 响应组应用程序 makes it possible for you to clearly define when Response Group agents are available to answer calls and when they are not available to answer calls. With the 响应组应用程序, you can define business hours; these business hours indicate the days of the week and hours of the day that agents are available to answer calls. For example, if your organization is typically open from 9:00 A.M. to 5:00 P.M. Monday through Friday then you would configure business hours that show that agents are available from 9:00 A.M. to 5:00 P.M. Monday through Friday (and, by extension, that agents are not available at, say, 8:00 P.M. on a Thursday or 2:30 P.M. on a Sunday).

However, in many organizations there are exceptions to the typical work week; for example, in the U.S. an organization might be closed on Christmas Day or Thanksgiving Day. In order to accommodate for atypical closures, the 响应组应用程序 enables you to designate certain days as holidays: days when the organization would usually be open but, for whatever reason, is not. Individual holidays (created using the **New-CsRgsHoliday** cmdlet) are collected in holiday sets; for example, holidays for the U.S. might be collected in a holiday set named US\_Holidays, while holidays for Japan might be collected in a holiday set named Japanese\_Holidays. After they are collected, holidays and their corresponding holiday sets can then be assigned to Response Group workflows.

The **New-CsRgsHolidaySet** cmdlet provides a way for you to configure new holiday sets for use in your organization. Note that, when you create a new holiday set, you must include at least one holiday; these individual holidays must be created by using the **New-CsRgsHoliday** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsRgsHolidaySet** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsRgsHolidaySet"}

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
<td><p><em>HolidayList</em></p></td>
<td><p>Required</p></td>
<td><p>System.Collections.ObjectModel.Collection</p></td>
<td><p>One or more holidays to be added to the holiday set. Holidays must be created by using the <strong>New-CsRgsHoliday</strong> cmdlet and then stored in an object reference. These object references are then passed to the Holidays parameter in order to add the holidays to the holiday set. For example, this command creates a holiday named New Year’s Day and then stores the resulting value in an object reference named $x:</p>
<p>$x = New-CsRgsHoliday -StartDate &quot;1/1/2013 12:00 AM&quot; -EndDate &quot;1/2/2013 12:00 AM&quot; -Name &quot;New Year's Day&quot;</p>
<p>Note that the format used for specifying dates and times will depend on your Regional and Language options. The examples shown in this topic use U.S. English.</p></td>
</tr>
<tr class="even">
<td><p><em>Name</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Unique name to be assigned to the holiday set. The combination of the Parent property and the Name property enables you to uniquely identify holiday sets without having to refer to the set’s globally unique identifier (GUID).</p></td>
</tr>
<tr class="odd">
<td><p><em>Parent</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.RgsIdentity</p></td>
<td><p>Service where the new holiday set will be hosted. For example: -Parent &quot;service:ApplicationServer:atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
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
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. **New-CsRgsHolidaySet** does not accept pipelined input.

## Return Types

**New-CsRgsHolidaySet** creates new instances of the Microsoft.Rtc.Rgs.Management.WritableSettings.HolidaySet object.

## 另请参阅

#### 其他资源

[Get-CsRgsHolidaySet](get-csrgsholidayset.md)  
[New-CsRgsHoliday](new-csrgsholiday.md)  
[Remove-CsRgsHolidaySet](remove-csrgsholidayset.md)  
[Set-CsRgsHolidaySet](set-csrgsholidayset.md)

