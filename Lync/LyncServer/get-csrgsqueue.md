---
title: Get-CsRgsQueue
TOCTitle: Get-CsRgsQueue
ms:assetid: a2e786b7-5096-4011-8108-2b56ae768c1d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412759(v=OCS.15)
ms:contentKeyID: 49313812
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsRgsQueue

 

_**上一次修改主题：** 2015-03-09_

Retrieves information about the Response Group queues in use in your organization. With the 响应组应用程序, phone calls are put in a queue and calls are placed on hold until a Response Group agent is available to answer that call. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsRgsQueue [-Identity <RgsIdentity>] [-Name <String>] [-Owner <RgsIdentity>] [-ShowAll <SwitchParameter>]

## Examples

## EXAMPLE 1

The command shown in Example 1 returns information about all the Response Group queues configured for use in the organization. This is done by calling **Get-CsRgsQueue** without any parameters.

    Get-CsRgsQueue

## EXAMPLE 2

The command shown in Example 2 returns information about all the Response Group queues located on the service ApplicationServer:atl-cs-001.litwareinc.com.

    Get-CsRgsQueue -Identity service:ApplicationServer:atl-cs-001.litwareinc.com

## EXAMPLE 3

In Example 3, information is returned for a single Response Group queue: the queue named "Help Desk" located on the service ApplicationServer:atl-cs-001.litwareinc.com.

    Get-CsRgsQueue -Identity service:ApplicationServer:atl-cs-001.litwareinc.com -Name "Help Desk"

## EXAMPLE 4

The command shown in Example 4 displays detailed information about the TimeoutAction property for each Response Group queue found on the service ApplicationServer:atl-cs-001.litwareinc.com. To carry out this task, **Get-CsRgsQueue** is first used to return information about all the queues found on ApplicationServer:atl-cs-001.litwareinc.com. This information is then passed to the **Select-Object** cmdlet, which "expands" the value stored in the TimeoutAction property. When you expand the TimeoutAction property, you see the individual properties of the embedded object that make up the property value: Prompt; TargetQuestion; Target; TargetQueueID; and TargetUri.

    Get-CsRgsQueue -Identity service:ApplicationServer:atl-cs-001.litwareinc.com | Select-Object -ExpandProperty TimeoutAction

## EXAMPLE 5

Example 5 returns information about all the Response Group queues on ApplicationServer:atl-cs-001.litwareinc.com where the OverflowCandidate property is set to NewestCall. To accomplish this task, the command first uses **Get-CsRgsQueue** to return a collection of all the Response Group queues found on the specified service. That collection is then piped to the **Where-Object** cmdlet, which selects only those queues where the OverflowCandidate property is equal to "NewestCall".

    Get-CsRgsQueue -Identity service:ApplicationServer:atl-cs-001.litwareinc.com | Where-Object {$_.OverflowCandidate -eq "NewestCall"}

## Detailed Description

When someone calls a phone number associated with the 响应组应用程序, one of two things typically happens: either the call is transferred to a question that the caller must answer in order to continue (for example, "Press 1 for hardware support; press 2 for software support") or the call is placed in a queue until a Response Group agent is available to answer the call.

Instead of having a single queue for all phone calls, the 响应组应用程序 enables you to create multiple queues that can be associated with different workflows and different Response Group agent groups. In turn, this means queues can respond differently to events such as a designated number of calls being simultaneously held in the queue, or to callers that have been on hold for a specified number of seconds.

The **Get-CsRgsQueue** cmdlet provides a way for you to return information about the Response Group queues configured for use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsRgsQueue** cmdlet locally: RTCUniversalServerAdmins, RTCUniversalReadOnlyAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsRgsQueue"}

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
<td><p>Represents either the Identity of the service where the Response Group queue is hosted or the full Identity of the queue itself. If you specify the service Identity (for example, service:ApplicationServer:atl-cs-001.litwareinc.com), then all the Response Group queues hosted on that service will be returned. If you specify the Identity of the queue, then only the specified Response Group queue will be returned. Note that the Identity of a queue consists of the service Identity followed by a globally unique identifier (GUID); for example: service:ApplicationServer:atl-cs-001.litwareinc.com /1987d3c2-4544-489d-bbe3-59f79f530a83.</p>
<p>An alternate way to return a single Response Group queue is to specify the service Identity, then include the Name parameter and the queue name. That enables you to retrieve a specific Response Group queue without having to know the GUID assigned to that queue.</p>
<p>If called without any parameters, <strong>Get-CsRgsQueue</strong> returns all the Response Group queues configured for use in your organization.</p></td>
</tr>
<tr class="even">
<td><p><em>Name</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Unique name given to the Response Group queue at the time the queue was created.</p></td>
</tr>
<tr class="odd">
<td><p><em>Owner</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.RgsIdentity</p></td>
<td><p>Fully qualified domain name of the pool that &quot;owns&quot; the queue. The Owner pool ID and the Pool ID of a queue are typically the same. However, if a queue needs to temporarily be moved (perhaps in a disaster recovery procedure) then the Pool ID will change. However, the Owner ID will continue to point to the original pool.</p></td>
</tr>
<tr class="even">
<td><p><em>ShowAll</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, shows all the Response Group queues, including those queues where the Owner pool ID and the Pool ID are different. By default, Get-CsRgsQueue only returns information about queues where the Owner pool ID and the Pool ID are identical.</p></td>
</tr>
</tbody>
</table>


## Input Types

String. **Get-CsRgsQueue** accepts a string value representing the Identity of the Response Group queue.

## Return Types

**Get-CsRgsQueue** returns instances of the Microsoft.Rtc.Rgs.Management.WritableSettings.Queue object.

## 另请参阅

#### 其他资源

[New-CsRgsQueue](new-csrgsqueue.md)  
[Remove-CsRgsQueue](remove-csrgsqueue.md)  
[Set-CsRgsQueue](set-csrgsqueue.md)

