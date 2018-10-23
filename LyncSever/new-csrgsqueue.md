---
title: New-CsRgsQueue
TOCTitle: New-CsRgsQueue
ms:assetid: e013533b-6845-44c6-ae5e-e75187b43181
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398989(v=OCS.15)
ms:contentKeyID: 49314510
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsRgsQueue

 

_**上一次修改主题：** 2015-03-09_

Creates a new Response Group queue. With the 响应组应用程序, phone calls are put in a queue and callers are placed on hold until a Response Group agent is available to answer that call. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsRgsQueue -Name <String> -Parent <RgsIdentity> [-AgentGroupIDList <Collection>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-OverflowAction <CallAction>] [-OverflowCandidate <NewestCall | OldestCall>] [-OverflowThreshold <Int16>] [-TimeoutAction <CallAction>] [-TimeoutThreshold <Int32>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 creates a new Response Group queue for the service ApplicationServer:atl-cs-001.litwareinc.com. The first command in the example uses the **New-CsRgsCallAction cmdlet** to create a call action for the queue; in this example, any time the overflow threshold is exceeded calls will automatically be transferred to voice mail. This is configured by setting the Action parameter to TransferToVoicemailUri and the URI property to the voice mail SIP URI "sip:+14255551298@litwareinc.com".

After the call action has been configured (and stored in the variable $x), **New-CsRgsQueue** is then used to create a new queue named Help Desk. In addition to specifying the OverflowAction, this command also configures values for the OverflowCandidate and OverflowThreshold properties.

    $x = New-CsRgsCallAction -Action TransferToVoicemailUri -Uri "sip:+14255551298@litwareinc.com"
    
    New-CsRgsQueue -Parent service:ApplicationServer:atl-cs-001.litwareinc.com -Name "Help Desk" -OverflowCandidate "OldestCall" -OverflowAction $x -OverflowThreshold 25

## Detailed Description

When someone calls a phone number associated with the 响应组应用程序, one of two things typically happens: either the call is transferred to a question that the caller must answer in order to continue (for example, "Press 1 for hardware support; press 2 for software support") or the call is placed in a queue until an agent is available to answer the call.

Instead of having a single queue for all phone calls, the 响应组应用程序 enables you to create multiple queues that can be associated with different workflows and different Response Group agent groups. In turn, this means queues can respond differently to events such as a designated number of calls being simultaneously held in the queue, or to callers that have been on hold for a specified amount of time.

The **New-CsRgsQueue** cmdlet provides an easy way for administrators to create new Response Group queues.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsRgsQueue** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsRgsQueue"}

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
<td><p>Unique name to be assigned to the queue. The combination of the Parent property and the Name property enables you to uniquely identify Response Group queues without having to refer to the queue’s globally unique identifier (GUID).</p></td>
</tr>
<tr class="even">
<td><p><em>Parent</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.RgsIdentity</p></td>
<td><p>Service where the new queue will be hosted. For example: -Parent &quot;service:ApplicationServer:atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>AgentGroupIDList</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Collections.ObjectModel.Collection</p></td>
<td><p>Identity of the Response Group agent groups to be added to the queue. The agent group Identities can be retrieved using the <strong>Get-CsRgsAgentGroup</strong> cmdlet. For details, see the Examples section in this topic.</p>
<p>If a call is routed to a queue that has no agent groups assigned to it (or has only been assigned agent groups that do not have any agents) then that call will automatically be disconnected.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables administrators to provide additional information about the Response Group queue.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="even">
<td><p><em>OverflowAction</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.CallAction</p></td>
<td><p>Action to be taken if the overflow threshold is reached. The OverflowAction must be created using the <strong>New-CsRgsCallAction</strong> cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>OverflowCandidate</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.OverflowCandidate</p></td>
<td><p>Indicates which call will be acted upon should the overflow threshold be reached. The OverflowCandidate property must be set to one of the following two values:</p>
<p>NewestCall</p>
<p>OldestCall</p>
<p>The default value is NewestCall.</p></td>
</tr>
<tr class="even">
<td><p><em>OverflowThreshold</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int16</p></td>
<td><p>Number of simultaneous calls that can be in the queue at any one time before the overflow action is triggered. The OverflowThreshold can be any integer value between 0 and 1000, inclusive. The default value is Null, meaning that an unlimited number of calls can be in the queue at any given time.</p></td>
</tr>
<tr class="odd">
<td><p><em>TimeoutAction</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.CallAction</p></td>
<td><p>Action to be taken if the timeout threshold is reached. The TimeoutAction must be created using the <strong>New-CsRgsCallAction</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>TimeoutThreshold</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Amount of time (in seconds) that a call can be in the queue before that call times out. At that point, the system will take the action specified by the TimeoutAction parameter.</p>
<p>The timeout threshold can be any integer value between 10 and 65535 seconds (approximately 18 hours), inclusive; the default value is null, meaning that the queue never times out.</p></td>
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

None. **New-CsRgsQueue** does not accept pipelined input.

## Return Types

**New-CsRgsQueue** creates new instances of the Microsoft.Rtc.Rgs.Management.WritableSettings.Queue object.

## 另请参阅

#### 其他资源

[Get-CsRgsQueue](get-csrgsqueue.md)  
[Remove-CsRgsQueue](remove-csrgsqueue.md)  
[Set-CsRgsQueue](set-csrgsqueue.md)

