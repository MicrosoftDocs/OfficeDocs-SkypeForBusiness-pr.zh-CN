---
title: Get-CsRgsHolidaySet
TOCTitle: Get-CsRgsHolidaySet
ms:assetid: eef7c046-088f-4334-808a-9036470919b1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412983(v=OCS.15)
ms:contentKeyID: 49314663
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsRgsHolidaySet

 

_**上一次修改主题：** 2015-03-09_

Returns information about the Response Group holiday sets configured for use in your organization. A Response Group holiday set is a collection of holidays. For example, you might have one holiday set for a United States (U.S.)-based queue (a set which might include a holiday for the Fourth of July) and a different set for a queue based in France. The latter queue might define a holiday for Bastille Day but not for the Fourth of July. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsRgsHolidaySet [-Identity <RgsIdentity>] [-Name <String>] [-Owner <RgsIdentity>] [-ShowAll <SwitchParameter>]

## Examples

## EXAMPLE 1

Example 1 returns information about all the holiday sets configured for use in your organization.

    Get-CsRgsHolidaySet

## EXAMPLE 2

The command shown in Example 2 returns information about all the holiday sets configured for the service ApplicationServer:atl-cs-001.litwareinc.com.

    Get-CsRgsHolidaySet -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com"

## EXAMPLE 3

In Example 3, a single holiday set from the service ApplicationServer:atl-cs-001.litwareinc.com is returned: the set with the Name "2013 Holidays". Because Names must be unique for each service, this command will never return more than one item.

    Get-CsRgsHolidaySet -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" -Name "2013 Holidays"

## EXAMPLE 4

Example 4 displays detailed information for the holidays found in the holiday set "2013 Holidays" (located on the service ApplicationServer:atl-cs-001.litwareinc.com). To do this, the command first uses **Get-CsRgsHolidaySet** to retrieve the specified holiday set. This set is then passed to the **Select-Object** cmdlet, which uses the ExpandProperty parameter to show detailed information for each holiday in the set.

    Get-CsRgsHolidaySet -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" -Name "2013 Holidays"| Select-Object -ExpandProperty HolidayList

## EXAMPLE 5

The command shown in Example 5 reports the Identity of each holiday set on ApplicationServer:atl-cs-001.litwareinc.com that includes a holiday named Christmas Day. To do this, the command first calls **Get-CsRgsHolidaySet** to return a collection of all the holiday sets found on ApplicationServer:atl-cs-001.litwareinc.com. This collection is then piped to the **Select-Object**, which does two things: it selects the Identity property, and it expands the HolidayList property.

These two pieces of information -- Identity, and the expanded value of the HolidayList property -- are then piped to the **Where-Object** cmdlet; in turn, **Where-Object** picks out the items where the Name of the holiday is equal to Christmas Day. Finally, the filtered collection is piped to the **ForEach-Object** cmdlet. This cmdlet takes each Identity in the collection and, one-by-one, uses **Get-CsRgsHolidaySet** to retrieve the corresponding holiday set. The net result is a list of all the holiday sets that include a Christmas Day holiday.

    Get-CsRgsHolidaySet -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" | Select-Object Identity -ExpandProperty HolidayList | Where-Object {$_.Name -eq "Christmas Day"} | ForEach-Object {Get-CsRgsHolidaySet -Identity $_.Identity}

## Detailed Description

In order to provide callers with the best possible experience, the 响应组应用程序 makes it possible for you to clearly define when Response Group agents are available to answer calls and when they are not available to answer calls. With the 响应组应用程序 you can define business hours; these hours indicate the days of the week and hours of the day that agents are available to answer calls. For example, if your organization is typically open from 9:00 A.M. to 5:00 P.M. Monday through Friday, then you would configure business hours that show that agents are available from 9:00 A.M. to 5:00 P.M. Monday through Friday (and, by extension, that agents are not available at, say, 8:00 P.M. on a Thursday or 2:30 P.M. on a Sunday).

However, in many organizations there are exceptions to the typical work week; for example, in the U.S., an organization might be closed on Christmas Day or Thanksgiving Day. In order to accommodate these atypical closures, the 响应组应用程序 enables you to designate certain days as holidays: days when the organization would usually be open but, for whatever reason, is not. Individual holidays (created by using the **New-CsRgsHoliday** cmdlet) are collected in holiday sets; for example, holidays for the U.S. might be collected in a holiday set named US\_Holidays, while holidays for Japan might be collected in a holiday set named Japanese\_Holidays. After they are collected, holiday sets can then be assigned to Response Group workflows.

The **Get-CsRgsHolidaySet** provides a way for you to return information about the Response Group holiday sets configured for use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsRgsHolidaySet** cmdlet locally: RTCUniversalServerAdmins, RTCUniversalReadOnlyAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsRgsHolidaySet"}

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
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.RgsIdentity</p></td>
<td><p>Represents either the Identity of the service where the holiday set is hosted or the full Identity of the holiday set. If you specify the service Identity (for example, service:ApplicationServer:atl-cs-001.litwareinc.com), then all the holiday sets hosted on that service will be returned. If you specify the Identity of the holiday set, then only the specified set will be returned. Note that the Identity of a holiday set consists of the service Identity followed by a globally unique identifier (GUID); for example: service:ApplicationServer:atl-cs-001.litwareinc.com/1987d3c2-4544-489d-bbe3-59f79f530a83.</p>
<p>An alternate way to return a single holiday set is to specify the service Identity, and then include the Name parameter and the holiday set name. That enables you to retrieve a specific holiday set without having to know the GUID assigned to that set.</p>
<p>If called without any parameters, <strong>Get-CsRgsHolidaySet</strong> returns a collection of all the holiday sets configured for use in your organization.</p></td>
</tr>
<tr class="even">
<td><p><em>Name</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Unique name given to the holiday set at the time the set was created.</p></td>
</tr>
<tr class="odd">
<td><p><em>Owner</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.RgsIdentity</p></td>
<td><p>Fully qualified domain name of the pool that &quot;owns&quot; the holiday set. The Owner pool ID and the Pool ID of a holiday set are typically the same. However, if a holiday set needs to temporarily be moved (perhaps in a disaster recovery procedure) then the Pool ID will change. However, the Owner ID will continue to point to the original pool.</p></td>
</tr>
<tr class="even">
<td><p><em>ShowAll</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, shows all the Response Group holiday sets, including those sets where the Owner pool ID and the Pool ID are different. By default, Get-CsRgsHolidaySet only returns information about agent sets where the Owner pool ID and the Pool ID are identical.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. **Get-CsRgsHolidaySet** does not accept pipelined input.

## Return Types

**Get-CsRgsHolidaySet** returns instances of the Microsoft.Rtc.Rgs.Management.WritableSettings.HolidaySet object.

## 另请参阅

#### 其他资源

[New-CsRgsHolidaySet](new-csrgsholidayset.md)  
[Remove-CsRgsHolidaySet](remove-csrgsholidayset.md)  
[Set-CsRgsHolidaySet](set-csrgsholidayset.md)

