﻿---
title: New-CsRgsCallAction
TOCTitle: New-CsRgsCallAction
ms:assetid: 07b70bbd-8e2e-426f-8c30-29f74b07b55b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398136(v=OCS.15)
ms:contentKeyID: 49311906
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsRgsCallAction

 

_**上一次修改主题：** 2015-03-09_

Creates a new Response Group call action. The 响应组应用程序 uses call actions to determine what the system does when a call is received. For example, a call action might specify that a call be transferred to another queue; that a specific Response Group question be asked; or that the call be ended. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsRgsCallAction -Action <Terminate | TransferToQueue | TransferToQuestion | TransferToUri | TransferToVoicemailUri | TransferToPstn> [-Prompt <Prompt>] [-Question <Question>] [-QueueID <RgsIdentity>] [-Uri <String>]

## Examples

## EXAMPLE 1

The commands shown in Example 1 demonstrate how you can create a new Response Group call action, and then assign that action to an existing Response Group queue; in this case, the call action determines what will happen if the queue overflow is reached. To perform this task, the first step is to use **Get-CsRgsQueue** to retrieve the 响应组应用程序 queue Help Desk Overflow queue from ApplicationServer:atl-cs-001.litwareinc.com; information from this queue is stored in a variable named $x. A similar command is then used to retrieve the Help Desk queue, with that information stored in a variable named $z.

After the queues have been retrieved, the **New-CsRgsPrompt** cmdlet is used to create a text-to-speech prompt to accompany the new call action. That new call action is created by running the **New-CsRgsCallAction** cmdlet. The call action is assigned three parameters: Prompt (the prompt to be used by the call action); Action (which indicates what happens if the new call action is triggered; the parameter value TransferToQueue means that the call will be transferred to a different Response Group queue); and QueueID, the alternate queue the call will be transferred to ($x.Identity, which represents the Identity of the queue Help Desk Overflow queue). The new call action is created in memory and then stored in a variable named $y.

After the call action has been created you can then assign the new call action to the Help Desk queue; this is done by setting the value of the OverflowAction property to $y, the variable that contains the newly created call action. If the Help Desk queue "overflows" (that is, if it reaches the maximum number of allowed callers) any subsequent calls will automatically be transferred to the Help Desk Overflow queue.

Finally, the last command in the example calls **Set-CsRgsQueue** to write the changes to the actual instance of Help Desk Overflow queue on ApplicationServer:atl-cs-001.litwareinc.com.

    $x = Get-CsRgsQueue -Identity service:ApplicationServer:atl-cs-001.litwareinc.com -Name "Help Desk Overflow"
    $z = Get-CsRgsQueue -Identity service:ApplicationServer:atl-cs-001.litwareinc.com -Name "Help Desk"
    
    $w = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we transfer your call."
    $y = New-CsRgsCallAction -Prompt $w -Action TransferToQueue -QueueID $x.Identity
    $z.OverflowAction = $y
    Set-CsRgsQueue $z

## EXAMPLE 2

The commands shown in Example 2 are similar to the commands shown in Example 1. In Example 2, however, the new call action transfers the call to a PSTN phone number. To do this, the new call action’s Action property is set to TransferToPSTN and the Uri property is set to "sip:+14255551298@litwareinc.com".

    $w = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we transfer your call."
    $y = New-CsRgsCallAction -Prompt $w -Action TransferToPSTN -Uri "sip:+14255551298@litwareinc.com"
    $z = Get-CsRgsQueue -Identity service:ApplicationServer:atl-cs-001.litwareinc.com -Name "Help Desk Queue"
    $z.OverflowAction = $y
    Set-CsRgsQueue $z

## Detailed Description

When someone calls a phone number associated with the 响应组应用程序, the application looks up the workflow that corresponds to the telephone number called. After the workflow is found, the service checks to see if the call was received outside business hours or on a holiday. If so, the service takes the action specified for calls received outside business hours or on a holiday. (For example, the call might be directly transferred to voice mail.) If the call was received during business hours, then the 响应组应用程序 takes the action preconfigured for calls received during business hours. All these actions are determined in advance, and all these actions are created by using the **New-CsRgsCallAction** cmdlet. **New-CsRgsCallAction** enables you to have calls placed in a Response Group queue; transferred to voice mail, a SIP address, or a public switched telephone network (PSTN) phone number; transferred to an interactive voice response (IVR) question; or closed.

When you use **New-CsRgsCallAction** you do not directly modify the properties of a workflow, queue, or other 响应组应用程序 element. Instead, the new call action you create initially exists only in memory, and must be stored in an object reference variable (such as $x). When it comes time to modify something (such as the DefaultAction property of a workflow) you then assign the object reference to the appropriate property. For example:

\-DefaultAction $x

It should be noted that the only two call actions that can be assigned to the DefaultAction property are TransferToQueue and TransferToQuestion. All the other call actions except for TransferToQueue and TransferToQuestion are valid for actions that take place on holidays or outside business hours. In addition, all the call actions except for TransferToQuestion can be used for queue timeouts and overflows.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsRgsCallAction** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins, RTCUniversalReadOnlyAdmins. However, because this cmdlet creates an in-memory object and, by itself, makes no changes to the system, it can essentially be run by anyone. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsRgsCallAction"}

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
<td><p><em>Action</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.Action</p></td>
<td><p>Represents the call action to be taken. The Action must be set to one of the following values:</p>
<p>Terminate – The call is terminated.</p>
<p>TransferToQueue – The call is transferred to a Response Group queue.</p>
<p>TransferToQuestion – The call is transferred to a Response Group question.</p>
<p>TransferToUri – The call is transferred to the specified SIP Uniform Resource Identifier (URI).</p>
<p>TransferToVoiceMailUri – The call is transferred to voice mail.</p>
<p>TransferToPSTN – The call is transferred to a public switched telephone network (PSTN) telephone.</p>
<p>The Action must be specified each time you create a new call action; there is no default value.</p></td>
</tr>
<tr class="even">
<td><p><em>Prompt</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.Prompt</p></td>
<td><p>Prompt to be played before the call action takes place. (For example, &quot;Please hold while your call is transferred.&quot;) Prompts must be created by using the <strong>New-CsRgsPrompt</strong> cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>Question</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.Question</p></td>
<td><p>Question to be asked if the Action has been set to TransferToQuestion. The question must be created by using the <strong>New-CsRgsQuestion</strong> cmdlet.</p>
<p>This parameter is required if the Action has been set to TransferToQuestion.</p></td>
</tr>
<tr class="even">
<td><p><em>QueueID</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.RgsIdentity</p></td>
<td><p>Identity of the Response Group queue the call should be transferred to (assuming that the Action has been set to TransferToQueue). The QueueID is best specified by using <strong>Get-CsRgsQueue</strong> to retrieve the Identity of the relevant queue.</p>
<p>This parameter is required if the Action is set to TransferToQueue.</p></td>
</tr>
<tr class="odd">
<td><p><em>Uri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>SIP address, voice mail URI, or PSTN telephone number that the call should be transferred to.</p>
<p>This parameter is required if the Action has been set to TransferToUri; TransferToVoiceMailUri; or TransferToPSTN.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. **New-CsRgsCallAction** does not accept pipelined input.

## Return Types

**New-CsRgsCallAction** creates new instances of the Microsoft.Rtc.Rgs.Management.WritableSettings.CallAction object.

## 另请参阅

#### 其他资源

[New-CsRgsQueue](new-csrgsqueue.md)  
[Set-CsRgsQueue](set-csrgsqueue.md)

