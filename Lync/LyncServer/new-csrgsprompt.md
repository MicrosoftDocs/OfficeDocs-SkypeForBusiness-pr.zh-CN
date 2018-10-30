﻿---
title: New-CsRgsPrompt
TOCTitle: New-CsRgsPrompt
ms:assetid: 6812acbf-ae56-43a6-a2d7-e28a930f81c7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398486(v=OCS.15)
ms:contentKeyID: 49313126
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsRgsPrompt

 

_**上一次修改主题：** 2015-03-09_

Creates a new workflow prompt for the 响应组应用程序. A workflow prompt is either an audio file that is played or text that is read aloud in order to supply callers with additional information. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsRgsPrompt [-AudioFilePrompt <AudioFile>] [-TextToSpeechPrompt <String>]

## Examples

## EXAMPLE 1

The commands shown in Example 1 demonstrate how a workflow prompt (and a Response Group queue) can be included in a new call action. In the first command, the **Get-CsRgsQueue** cmdlet is used to return an object reference ($queue) to the Response Group queue Help Desk. In the second command, the **New-CsRgsPrompt** cmdlet is then used to create a new text-to-speech prompt, "Welcome to the help desk. Please hold." This new prompt is stored in a variable named $prompt.

The final command in the example uses **New-CsRgsCallAction** to create a new Response Group call action ($z). When creating the call action, the object reference $prompt (which contains the newly-created workflow prompt) is used as the value for the Prompt parameter; the object reference $queue is likewise used in conjunction with the QueueID parameter. After running this command, the new call action and its new workflow prompt are ready to be added to a Response Group workflow.

    $queue = Get-CsRgsQueue -Identity service:ApplicationServer:atl-cs-001.litwareinc.com -Name "Help Desk"
    
    $prompt = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to the help desk. Please hold."
    
    $z = New-CsRgsCallAction -Prompt $prompt -Action TransferToQueue -QueueID $queue.Identity

## EXAMPLE 2

The commands shown in Example 2 are a variation of the commands shown in Example 1. In this case, however, the new workflow prompt includes an audio file prompt in addition to a text-to-speech prompt. To include an audio file in a workflow prompt, the second command in the example uses the **Import-CsRgsAudioFile** cmdlet to import the audio file C:\\Media\\Welcome.wav. The imported file is then stored in a variable named $audioFile.

After the audio file has been imported, both it and a text-to-speech prompt are added to a new workflow prompt ($prompt). To do this, the AudioFilePrompt parameter is set to $audioFile, and the TextToSpeechPrompt parameter is set to the text value "Welcome to the help desk. Please hold."

    $queue = Get-CsRgsQueue -Identity service:ApplicationServer:atl-cs-001.litwareinc.com -Name "Help Desk Queue"
    
    $audioFile = Import-CsRgsAudioFile -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" -FileName "welcome.wav" -Content (Get-Content C:\Media\Welcome.wav -Encoding byte -ReadCount 0)
    
    $prompt = New-CsRgsPrompt -AudioFilePrompt $audioFile -TextToSpeechPrompt "Welcome to the help desk. Please hold."
    
    $z = New-CsRgsCallAction -Prompt $prompt -Action TransferToQueue -QueueID $queue.Identity

## Detailed Description

Keeping callers well informed about what’s going on, and why, is an important part of a Response Group workflow. For example, you might have the workflow configured to answer the phone and then immediately place the call on hold until an agent is available. This is fine, but it also requires you to inform the caller that: 1) the phone has been answered; and, 2) the call will be put on hold until an agent is available. Providing information such as this is the job of the workflow prompt.

The 响应组应用程序 supports two different kinds of workflow prompts. First, you can pre-record and then play back an audio file. To do this, you must record the prompt ("Please hold. Your call is important to us.") in either the .WAV or .WMA format; import the file by using the **Import-CsRgsAudioFile** cmdlet; and then assign the file to a workflow prompt. Alternatively, you can simply provide the text to be read and, when the prompt is needed, the 响应组应用程序 will use its text-to-speech capabilities to "read" the text aloud. Text-to-speech prompts are easier to configure: there are no audio files to record and import. However, audio file prompts are typically of higher quality and fidelity.

Note that the language used in a text-to-speech prompt is the same as the language used in the parent workflow.

The **New-CsRgsPrompt** cmdlet provides a way for you to create workflow prompts. Each time you need to use a prompt it must be created from scratch; there is no way to save and reuse prompts. (This means you will also have to re-import audio files.) When you create a new workflow prompt you must provide a text-to-speech prompt; if you want, you can provide an audio file prompt as well. If you provide both a text-to-speech and an audio file prompt, the 响应组应用程序 will use the audio file by default, and will rely on the text-to-speech prompt only if the audio file is unavailable. After new prompts are created in memory, the corresponding object reference is then typically added to a Response Group call action.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsRgsPrompt** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins, RTCUniversalReadOnlyAdmins. However, because this cmdlet creates an in-memory object and, by itself, makes no changes to the system, it can essentially be run by anyone. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsRgsPrompt"}

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
<td><p><em>AudioFilePrompt</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.AudioFile</p></td>
<td><p>Audio file to be played when the workflow is activated. The audio file must be imported by using the <strong>Import-CsRgsAudioFile</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>TextToSpeechPrompt</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Text-to-speech (TTS) prompt to be read when the workflow is activated. The TTS prompt, which is used only if an audio file is not specified, can contain a maximum of 4096 characters.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. **New-CsRgsPrompt** does not accept pipelined input.

## Return Types

**New-CsRgsPrompt** creates instances of the Microsoft.Rtc.Management.WritableSettings.Prompt object.

## 另请参阅

#### 其他资源

[Import-CsRgsAudioFile](import-csrgsaudiofile.md)  
[New-CsRgsCallAction](new-csrgscallaction.md)

