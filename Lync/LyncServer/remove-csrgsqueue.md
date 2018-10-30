---
title: Remove-CsRgsQueue
TOCTitle: Remove-CsRgsQueue
ms:assetid: 7613e72c-f330-4560-88d4-a7386cd18975
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398576(v=OCS.15)
ms:contentKeyID: 49313278
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsRgsQueue

 

_**上一次修改主题：** 2015-03-09_

Deletes an existing Response Group queue. With the 响应组应用程序, phone calls are put in a queue and callers are placed on hold until a Response Group agent is available to answer that call. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsRgsQueue -Instance <Queue> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 deletes all the Response Group queues found on the service ApplicationServer:atl-cs-001.litwareinc.com. To do this, the command first uses **Get-CsRgsQueue** to return a collection of all the queues found on ApplicationServer:atl-cs-001.litwareinc.com. This collection is then piped to **Remove-CsRgsQueue**, which deletes each queue in the collection.

    Get-CsRgsQueue -Identity service:ApplicationServer:atl-cs-001.litwareinc.com | Remove-CsRgsQueue

## EXAMPLE 2

In Example 2, a single Response Group queue is deleted: the queue named "Help Desk Queue", located on the service ApplicationServer:atl-cs-001.litwareinc.com. To delete this queue, **Get-CsRgsQueue** is called along with the Identity and Name parameters; the single queue returned by this call is then piped to, and deleted by, **Remove-CsRgsQueue**.

    Get-CsRgsQueue -Identity service:ApplicationServer:atl-cs-001.litwareinc.com -Name "Help Desk Queue" | Remove-CsRgsQueue

## EXAMPLE 3

Example 3 deletes all the Response Group queues found on the service ApplicationServer:atl-cs-001.litwareinc.com, provided those queues have their OverflowCandidate property set to NewestCall. To do this, **Get-CsRgsQueue** is first called in order to return a collection of all the Response Group queues found on ApplicationServer:atl-cs-001.litwareinc.com. This collection is then piped to the **Where-Object** cmdlet, which selects only those queues where the OverflowCandidate property is equal to "NewestCall". The filtered collection is then piped to **Remove-CsRgsQueue**, which deletes each queue in the collection.

    Get-CsRgsQueue -Identity service:ApplicationServer:atl-cs-001.litwareinc.com | Where-Object {$_.OverflowCandidate -eq "NewestCall"} | Remove-CsRgsQueue

## Detailed Description

When someone calls a phone number associated with the 响应组应用程序 one of two things typically happens: either the call is transferred to a question that the caller must answer in order to continue (for example, "Press 1 for hardware support; press 2 for software support") or the call is placed in a queue until a Response Group agent is available to answer the call.

Instead of having a single queue for all phone calls, the 响应组应用程序 enables you to create multiple queues that can be associated with different workflows and different Response Group agent groups. In turn, this means queues can respond differently to events such as a designated number of calls being simultaneously held in the queue, or to callers that have been on hold for specified amount of time.

In addition to creating new queues you can also remove existing queues; that’s what the **Remove-CsRgsQueue** cmdlet is for. Note that, by default, you will be prompted if you try to remove a queue that is currently assigned to an active workflow; the prompt will ask you to verify that you want to delete the queue, and Windows PowerShell will pause (and no queue will be deleted) until you answer the prompt. To bypass the prompt, and to delete queues that are being used by an active workflow, add the Force parameter. For example:

Get-CsRgsQueue –Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" | Remove-CsRgsQueue –Force

**Remove-CsRgsQueue** always checks to see if a queue is being used by an active workflow before it will delete that queue. However, the cmdlet does not verify whether or not the queue is being used by another queue as either the timeout or overflow queue. That means it is possible to delete a queue that is needed by another queue. Because of that, you might want to use the **Get-CsRgsQueue** cmdlet to check the OverflowAction and TimeoutAction properties of your other Response Group queues before running **Remove-CsRgsQueue** to delete a queue.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsRgsQueue** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsRgsQueue"}

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
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.Queue</p></td>
<td><p>Object reference pointing to the queue to be removed. When piping workflow objects to <strong>Remove-CsRgsQueue</strong> you can leave off the Instance parameter.</p>
<p>To use the Instance parameter use commands similar to this:</p>
<p>$x = Get-CsRgsQueue –Identity ApplicationServer:atl-cs-001.litwareinc.com /1987d3c2-4544-489d-bbe3-59f79f530a83</p>
<p>Remove-CsRgsQueue –Instance $x</p>
<p>Note that you can only remove a single queue at a time when using the Instance parameter. That means that your object reference ($x) cannot contain multiple queue objects.</p></td>
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
<td><p>Forces the deletion of a Response Group queue. If this parameter is present, the queue will be deleted without warning, even if the queue is assigned to an active workflow. If this parameter is not present then you will be asked to confirm the deletion of any queue currently in use by an active workflow.</p></td>
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

Microsoft.Rtc.Rgs.Management.WritableSettings.Queue object. **Remove-CsRgsQueue** accepts pipelined instances of the Response Group queue object.

## Return Types

**Remove-CsRgsQueue** deletes existing instances of the Microsoft.Rtc.Rgs.Management.WritableSettings.Queue object.

## 另请参阅

#### 其他资源

[Get-CsRgsQueue](get-csrgsqueue.md)  
[New-CsRgsQueue](new-csrgsqueue.md)  
[Set-CsRgsQueue](set-csrgsqueue.md)

