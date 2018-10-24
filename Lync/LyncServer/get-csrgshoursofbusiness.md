---
title: Get-CsRgsHoursOfBusiness
TOCTitle: Get-CsRgsHoursOfBusiness
ms:assetid: 2008d55c-fd53-4004-b6e6-08cdf0175af8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398284(v=OCS.15)
ms:contentKeyID: 49312215
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsRgsHoursOfBusiness

 

_**上一次修改主题：** 2015-03-09_

Retrieves information about the Response Group business hour collections configured for use in your organization. Business hour collections are used to indicate the days of the week and the times of day when Response Group agents are typically available to answer phone calls. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsRgsHoursOfBusiness [-Identity <RgsIdentity>] [-Name <String>] [-Owner <RgsIdentity>] [-ShowAll <SwitchParameter>]

## Examples

## EXAMPLE 1

Example 1 returns information about all the business hour collections configured for use in your organization. This is done by calling **Get-CsRgsHoursOfBusiness** without any parameters.

    Get-CsRgsHoursOfBusiness

## EXAMPLE 2

The command shown in Example 2 returns all the business hour collections configured for use on atl-cs-001.litwareinc.com.

    Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com"

## EXAMPLE 3

Example 3 returns a single collection of business hours from atl-cs-001.litwareinc.com: the collection with the Name "Help Desk Business Hours".

    Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" -Name "Help Desk Business Hours"

## EXAMLE 4

The command shown in Example 4 returns all the business hour collections that have business hours configured for Sundays. To do this, the command first calls **Get-CsRgsHoursOfBusiness** to return all the business hour collections found on atl-cs-001.litwareinc.com. This data is then piped to the **Where-Object** cmdlet, which selects only those items where one of the following two criteria is true: the SundayTimeRange1 property is not equal to a null value and/or the SundayTimeRange2 property is not equal to a null value. If a time range property is not null, then that means business hours have been configured for that time period.

    Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" | Where-Object {$_.SundayTimeRange1 -ne $Null -or $_.SundayTimeRange2 -ne $Null}

## EXAMPLE 5

The command shown in Example 5 returns all the business hour collections from atl-cs-001.litwareinc.com where the opening time for the MondayTimeRange1 property is equal to (or earlier than) 8:00 A.M. In order to do this, the command first uses **Get-CsRgsHoursOfBusiness** to return all the business hour collections from atl-cs-001.litwareinc.com. This data is then piped to the **Where-Object** cmdlet, which selects only those collections where the value of the MondayTimeRange1.OpenTime property is less than or equal to 8:00 A.M. (08:00:00).

    Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" | Where-Object {$_.MondayTimeRange1.OpenTime -le "08:00:00"}

## EXAMPLE 6

The command shown in Example 6 returns all the public business hour collections; that is, collections that can be shared among workflows. To do this, the command first uses **Get-CsRgsHoursOfBusiness** to return all the business hour collections found on atl-cs-001.litwareinc.com. This data is then piped to the **Where-Object** cmdlet, which picks out only those collections where the Custom property is equal to False.

    Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" | Where-Object {$_.Custom -eq $False}

## Detailed Description

In order to provide callers with the best possible experience, the 响应组应用程序 makes it possible for you to clearly define when Response Group agents are available to answer calls and when they are not available to answer calls. With the 响应组应用程序, you can define business hours that indicate the days of the week and hours of the day that agents are available to answer calls. For example, if your organization is typically open from 9:00 A.M. to 5:00 P.M. Monday through Friday, then you would configure business hours that show that agents are available from 9:00 A.M. to 5:00 P.M. Monday through Friday (and, by extension, that agents are not available at, say, 8:00 P.M. on a Thursday or 2:30 P.M. on a Sunday).

The **Get-CsRgsHoursOfBusiness** cmdlet provides a way for you to retrieve information about the business hour collections configured for use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsRgsHoursOfBusiness** cmdlet locally: RTCUniversalServerAdmins, RTCUniversalReadOnlyAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsRgsHoursOfBusiness"}

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
<td><p>Represents either the Identity of the service where the business hours collection is hosted or the full Identity of the collection itself. If you specify the service Identity (for example, service:ApplicationServer:atl-cs-001.litwareinc.com), then all the business hours collections hosted on that service will be returned. If you specify the Identity of the collection, then only the specified business hours collection will be returned. Note that the Identity of a business hours collection consists of the service Identity followed by a globally unique identifier (GUID); for example: service:ApplicationServer-1/1987d3c2-4544-489d-bbe3-59f79f530a83.</p>
<p>An alternate way to return business hours collection is to specify the service Identity, then include the Name parameter and the collection name. That enables you to retrieve a specific business hours collection without having to know the GUID assigned to that collection.</p>
<p>If called without any parameters, <strong>Get-CsRgsHoursOfBusiness</strong> returns all the business hour collections configured for use in your organization.</p></td>
</tr>
<tr class="even">
<td><p><em>Name</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Unique name given to the business hours collection at the time the collection was created.</p></td>
</tr>
<tr class="odd">
<td><p><em>Owner</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.RgsIdentity</p></td>
<td><p>Fully qualified domain name of the pool that &quot;owns&quot; the business hours. The Owner pool ID and the Pool ID of a collection of business hours are typically the same. However, if a collection needs to temporarily be moved (perhaps in a disaster recovery procedure) then the Pool ID will change. However, the Owner ID will continue to point to the original pool.</p></td>
</tr>
<tr class="even">
<td><p><em>ShowAll</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, shows all the Response Group business hour collections, including those collections where the Owner pool ID and the Pool ID are different. By default, Get-CsRgsHoursOfBusiness only returns information about business hour collections where the Owner pool ID and the Pool ID are identical.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. **Get-CsRgsHoursOfBusiness** does not accept pipelined input.

## Return Types

Returns instances of the Microsoft.Rtc.Rgs.Management.WritableSettings.BusinessHours object.

## 另请参阅

#### 其他资源

[New-CsRgsHoursOfBusiness](new-csrgshoursofbusiness.md)  
[Remove-CsRgsHoursOfBusiness](remove-csrgshoursofbusiness.md)  
[Set-CsRgsHoursOfBusiness](set-csrgshoursofbusiness.md)

