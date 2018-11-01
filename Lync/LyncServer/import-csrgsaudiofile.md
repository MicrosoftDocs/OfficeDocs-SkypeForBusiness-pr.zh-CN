﻿---
title: Import-CsRgsAudioFile
TOCTitle: Import-CsRgsAudioFile
ms:assetid: ae9dfd76-9b3e-4c51-9692-39d1fe8e430b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412830(v=OCS.15)
ms:contentKeyID: 49313918
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Import-CsRgsAudioFile

 

_**上一次修改主题：** 2015-03-09_

Imports a new audio file for use with the 响应组应用程序. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Import-CsRgsAudioFile -Content <Byte[]> -FileName <String> -Identity <RgsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The commands shown in Example 1 import an audio file (C:\\Media\\WhileYouWait.wav) and then assign that file to the CustomMusicOnHold property of a workflow. To perform this task, the first command uses **Import-CsRgsAudioFile** to import the audio file to the 响应组应用程序 found on ApplicationServer:atl-cs-001.litwareinc.com. In addition to the Identity parameter (which specifies the service location) the FileName parameter is used to specify the file name of the file being imported.

At the same time, the Content parameter is used to import the audio file. File importing is carried out by calling the **Get-Content** cmdlet followed by the path to the file being imported. **Get-Content** also requires you to set the encoding type to byte and the ReadCount to 0. (Setting the ReadCount to 0 ensures that the entire file is read in in a single operation.) The imported file is then stored in a variable named $x.

In the second command, **Get-CsRgsWorkflow** is used to create an object reference ($y) to the workflow Help Desk Workflow. After this object reference has been created, command 3 sets the value of the CustomMusicOnHoldFile property to $x, the variable containing the imported audio file. Finally, the last command in the example uses **Set-CsRgsWorkflow** to write these changes to the actual workflow Help Desk Workflow. If you do not call **Set-CsRgsWorkflow**, your modifications will exist only in memory, and will disappear as soon as you close Windows PowerShell or delete the variables $x or $y.

    $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" -FileName "WhileYouWait.wav" -Content (Get-Content C:\Media\WhileYouWait.wav -Encoding byte -ReadCount 0)
    
    $y = Get-CsRgsWorkflow -Identity "service:ApplicationServer:atl-cs-001.litwareinc.com" -Name "Help Desk Workflow"
    $y.CustomMusicOnHoldFile = $x
    
    Set-CsRgsWorkflow $y

## Detailed Description

The 响应组应用程序 can use audio files (.WAV or .WMA formats only) in at least two different ways. For one, the service can play music (or an announcement of some type) any time callers are placed on hold. Alternatively, the 响应组应用程序 occasionally "talks" to callers; for example, with interactive voice response (IVR) the service might ask callers a question such as "Are you calling about an existing order?" You can have the service read these questions using text-to-speech technology or you can play an audio recording of an actual person asking the question.

Regardless of how you choose to use audio files, the files themselves must be imported into the 响应组应用程序 by using the **Import-CsRgsAudioFile** cmdlet. Note that you must run **Import-CsRgsAudioFile** each time you want to use an audio file, even if that file is already being used elsewhere in the 响应组应用程序. For example, suppose Workflow A uses a given audio file as its custom music on hold file and you now want to use that same audio file as the custom music on hold for Workflow B. Even though the audio file is already used by the Response Group application you will still need to import the file in order to use it with Workflow B.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Import-CsRgsAudioFile** cmdlet locally: RTCUniversalServerAdmins. You must also have write access to the target computer file store. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Import-CsRgsAudioFile"}

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
<td><p><em>Content</em></p></td>
<td><p>Required</p></td>
<td><p>System.Byte[]</p></td>
<td><p>Actual content of the audio file being imported. The Content property is populated by calling the <strong>Get-Content</strong> cmdlet. When calling <strong>Get-Content</strong>, set the Encoding parameter to byte and the ReadCount parameter to 0 (for details, see the Examples section in this topic).</p></td>
</tr>
<tr class="even">
<td><p><em>FileName</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>File name for the audio file being imported. For example, the file name for the file C:\Media\Welcome.wav is this: Welcome.wav.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.RgsIdentity</p></td>
<td><p>Identity of the service where the audio file is to be imported. (This must be the same service that hosts the 响应组应用程序.) For example: -Identity &quot;service:ApplicationServer:atl-cs-001.litwareinc.com&quot;.</p></td>
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
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
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

None. **Import-CsRgsAudioFile** does not accept pipelined input.

## Return Types

Creates new instances of the Microsoft.Rtc.Rgs.Management.WritableSettings.AudioFile object.

## 另请参阅

#### 其他资源

[New-CsRgsWorkflow](new-csrgsworkflow.md)  
[Set-CsRgsWorkflow](set-csrgsworkflow.md)

