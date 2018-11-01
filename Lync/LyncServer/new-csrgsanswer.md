---
title: New-CsRgsAnswer
TOCTitle: New-CsRgsAnswer
ms:assetid: aba521db-1741-4da3-aaf0-2d78fda4c4d2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412812(v=OCS.15)
ms:contentKeyID: 49313895
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsRgsAnswer

 

_**上一次修改主题：** 2015-03-09_

Creates a new Response Group answer. Response Group answers are used to associate a caller response with the appropriate action. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsRgsAnswer -Action <CallAction> [-DtmfResponse <String>] [-Name <String>] [-VoiceResponseList <PSListModifier>]

## Detailed Description

In order to process calls, the 响应组应用程序 often makes a statement or poses a question, then takes action based on the customer response. For example, the service might ask a caller to press 1 for English or press 2 for Spanish. After a question l has been posed, the system must wait for the caller to respond, and then take the appropriate action. In this case, that means transferring the call to an English language queue if the caller presses 1 on the telephone keypad, or transferring the call to a Spanish language queue if the caller presses 2 on the keypad.

Response Group answers are used to analyze caller responses and then take the appropriate action. For example, if callers are given the option of pressing 1 or 2, then two Response Group answers are required in order to address the situation: one answer to specify the action to be taken if the caller presses 1, and a second answer to specify the action to be taken if the caller presses 2. These two answers are created by using the **New-CsRgsAnswer** cmdlet and must then be added to the appropriate Response Group question (the question that asked the callers to press 1 or 2). Response Group answers must include a set of allowed voice responses (for example, the word "English") or the appropriate telephone keypad response (for example, pressing 1). Alternatively, you can give customers the option of using either a voice response or a keypad response: either say the word "English" or press 1 on the keypad. (The speech recognition used in these situations is the language used in the parent workflow.)

Response Group answers cannot be saved and reused with other questions. For example, suppose you have an answer that transfers a call to voice mail any time a caller presses 9. You associate that answer with a Response Group question. Later, you create a new question that also gives callers the option to transfer a call to voice mail by pressing 9. In that case, you will need to create a new instance of the Response Group answer; there is no way to save answers and then use that saved answer over and over.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsRgsAnswer** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins, RTCUniversalReadOnlyAdmins. However, because this cmdlet creates an in-memory object and, by itself, makes no changes to the system, it can essentially be run by anyone. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsRgsAnswer"}

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
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.CallAction</p></td>
<td><p>Indicates the action to be taken any time a caller provides this answer. The Action parameter must be specified using an object reference created by using the <strong>New-CsRgsCallAction</strong> cmdlet. For details, see the Examples section in this topic.</p></td>
</tr>
<tr class="even">
<td><p><em>DtmfResponse</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Indicates the key on the telephone keypad to be pressed in order to match the answer. For example, if callers are told to press 1 for hardware, then DtmfResponse would be configured like this: -DtmfResponse 1.</p>
<p>A single answer can include both a voice response and a dual-tone multifrequency (DTMF) response. Each answer must have at least one of these two response types.</p></td>
</tr>
<tr class="odd">
<td><p><em>Name</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Name given to the Response Group answer. Names do not have to be unique.</p></td>
</tr>
<tr class="even">
<td><p><em>VoiceResponseList</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Array of keywords callers can say that will match the answer. For example, if one option available to callers is &quot;Hardware&quot; then the VoiceResponseList property might be set to this: -VoiceResponseList &quot;Hardware&quot;. Multiple keywords can be specified by using comma-separated values. For example, this parameter value causes either Hardware or Devices to match the answer: -VoiceResponseList Hardware, Devices. Voice responses should not contain double quote marks, because that character is not recognized by the speech engine.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. **New-CsRgsAnswer** does not accept pipelined input.

## Return Types

Creates new instances of the Microsoft.Rtc.Rgs.Management.WritableSettings.Answer object.

## Examples

## EXAMPLE 1

The commands shown in Example 1 show how you can create a new Response Group answer that is associated with both a Response Group queue and a Response Group call action. The first command in the example uses the **New-CsRgsPrompt** cmdlet to create a TextToSpeechPrompt for the new answer. After that, the **Get-CsRgsQueue** cmdlet is called to return an object reference ($x) to the Response Group queue Help Desk. That object reference is then used in the next command, one that employs **New-CsRgsCallAction** to create a call action that transfers the caller to the Help Desk queue. This call action is stored in a variable named $y

The final command in the example creates a Response Group answer (stored in the variable $a). This answer accepts either the DTMF response 1 (pressing 1 on the telephone keypad) or the voice response "Yes".

After this answer has been created, it can then be associated with a Response Group question. For details, see the [New-CsRgsQuestion](new-csrgsquestion.md) help topic.

    $w = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we transfer your call."
    $x = Get-CsRgsQueue -Identity service:ApplicationServer:atl-cs-001.litwareinc.com -Name "Help Desk"
    
    $y = New-CsRgsCallAction -Prompt $w -Action TransferToQueue -QueueID $x.Identity
    
    $a = New-CsRgsAnswer -Action $y -DtmfResponse 1 -VoiceResponseList Yes -Name "New Service Request"

## 另请参阅

#### 其他资源

[New-CsRgsQuestion](new-csrgsquestion.md)

