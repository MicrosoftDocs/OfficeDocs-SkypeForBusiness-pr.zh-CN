---
title: Set-CsRgsWorkflow
TOCTitle: Set-CsRgsWorkflow
ms:assetid: 36cffa89-e5bb-48fd-bd6e-da67066fd273
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425845(v=OCS.15)
ms:contentKeyID: 49312482
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsRgsWorkflow

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing Response Group workflow. Workflows determine the actions that are taken when the 响应组应用程序 receives a phone call. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsRgsWorkflow -Instance <Workflow> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The commands shown in Example 1 retrieve an existing set of business hours, and then assign those business hours to a workflow named Help Desk. To do this, the first command in the example uses **Get-CsRgsHoursOfBusiness** to retrieve the business hours collection named U.S. Business Hours from the service ApplicationServer:atl-cs-001.litwareinc.com. These business hours are stored in a variable named $businessHours.

After the business hours have been retrieved the **Get-CsRgsWorkflow** cmdlet is used to retrieve the Help Desk workflow from ApplicationServer:atl-cs-001.litwareinc.com. This object is stored in a variable named $y.

In the third command in the example, the BusinessHoursId property of the Help Desk workflow is set to the retrieved collection of business hours; that’s done by setting BusinessHoursId to the Identity of the retrieved collection ($businessHours.Identity). In the final command, **Set-CsRgsWorkflow** is used to write the new business hours to the actual Help Desk workflow on ApplicationServer:atl-cs-001.litwareinc.com. This last step is important because, until this point, all the changes have taken place only in memory. To actually save these changes to the Help Desk workflow, you must call **Set-CsRgsWorkflow**, passing the cmdlet the object reference ($y) containing the virtual copy of the workflow.

    $businessHours = Get-CsRgsHoursOfBusiness service:ApplicationServer:atl-cs-001.litwareinc.com -Name "US Business Hours"
    $y = Get-CsRgsWorkflow Service:ApplicationServer:atl-cs-001.litwareinc.com -Name "Help Desk"
    $y.BusinessHoursId = $businessHours.Identity
    Set-CsRgsWorkflow -Instance $y

## EXAMPLE 2

Example 2 assigns a new description to the Help Desk workflow found on the service ApplicationServer:atl-cs-001.litwareinc.com. To do this, the first command in the example retrieves the specified workflow (-Name "Help Desk") and stores the retrieved object in a variable named $x. In command 2, a new description ("Workflow for the Redmond Help Desk") is added to the virtual copy of the Help Desk workflow. After the description has been changed, command 3 uses the **Set-CsRgsWorkflow** to write these changes back to the actual Help Desk workflow located on ApplicationServer:atl-cs-001.litwareinc.com.

    $x = Get-CsRgsWorkflow service:ApplicationServer:atl-cs-001.litwareinc.com -Name "Help Desk"
    $x.Description = "Workflow for the Redmond Help Desk" 
    Set-CsRgsWorkflow -Instance $x

## EXAMPLE 3

The commands shown in Example 3 import a new Response Group audio file, then assign this audio file to an existing workflow. To do this, the first command in the example imports the new audio file. This is done by calling the **Get-Content** cmdlet in order to read in the audio file (C:\\MediaFiles\\Hold.wav) byte-by-byte; to ensure that the audio file is read in correctly, you must include the ReadCount parameter (set to 0) and the Encoding parameter (set to Byte). After the audio file has been read in, the data is piped to **New-CsRgsAudioFile**, which creates a new file on ApplicationServer:atl-cs-001.litwareinc.com. An object reference to this file(which has the name HelpDeskHoldMusic.wav), is stored in a variable named $musicFile.

After the audio file has been created, command 2 retrieves the workflow Help Desk from ApplicationServer:atl-cs-001.litwareinc.com, storing the returned object in a variable named $y. In command 3, the CustomMusicOnHoldFile property for this workflow is assigned the value $musicFile, which is the variable containing the newly-created audio file.

After $musicFile has been assigned to CustomMusicOnHoldFile, the final command uses the **Set-CsRgsWorkflow** cmdlet to write these changes back to the Help Desk. workflow

    $musicFile = Get-Content -ReadCount 0 -Encoding Byte C:\MediaFiles\Hold.wav | Import-CsRgsAudioFile -Identity Service:ApplicationServer:atl-cs-001.litwareinc.com -FileName "HelpDeskHoldMusic.wav"
    $y = Get-CsRgsWorkflow -Identity Service:ApplicationServer:atl-cs-001.litwareinc.com -Name "Help Desk"
    $y.CustomMusicOnHoldFile = $musicFile
    Set-CsRgsWorkflow -Instance $y

## Detailed Description

Workflows are perhaps the key element in the 响应组应用程序. Each workflow is uniquely associated with a phone number; when someone calls that number, the workflow determines how the call will be handled. For example, the call might be routed to a series of interactive voice response (IVR) questions that prompt the caller to enter additional information (for example, "Press 1 for hardware support. Press 2 for software support.") Alternatively, the call might be placed in a queue and the caller put on hold until an agent is available to answer the call. The availability of agents to answer calls is also dictated by the workflow: workflows are used to configure both business hours (the days of the week and the times of day when agents are available to answer calls) and holidays (days when no agents are available to answer calls).

The **Set-CsRgsWorkflow** cmdlet provides a way for you to modify the properties of an existing workflow; for example, you can change the phone number for a workflow, the agents groups associated with a workflow, or the default action to be taken any time the workflow is triggered (that is, any time someone calls the phone number associated with the workflow).

**Set-CsRgsWorkflow** does not directly modify a workflow itself. Instead, if you need to make changes to a workflow, you must first use **Get-CsRgsWorkflow** to create an object reference to that workflow; this simply means that you retrieve the workflow of interest and then store the returned object in a variable. After the object reference has been created, you modify the properties of the object in memory, and then use **Set-CsRgsWorkflow** to write these changes back to actual 响应组应用程序 workflow. If you do not call **Set-CsRgsWorkflow** then your changes will exist only in memory, and will disappear as soon as you close Windows PowerShell or delete the object reference variable.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsRgsWorkflow** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsRgsWorkflow"}

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
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.Workflow</p></td>
<td><p>Object reference to the 响应组应用程序 workflow to be modified. An object reference is typically retrieved by using the <strong>Get-CsRgsWorkflow</strong> cmdlet and assigning the returned value to a variable; for example, this command returns an object reference to the Help Desk workflow and stores that object reference in a variable named $x:</p>
<p>$x = Get-CsRgsWorkflow service:ApplicationServer:atl-cs-001.litwareinc.com -Name &quot;Help Desk&quot;</p>
<p>The Instance parameter is a positional parameter: it can be omitted as long as the object reference to the workflow is the first parameter value used in your command. That means that the following two commands are functionally identical:</p>
<p>Set-CsRgsWorkflow –Instance $x</p>
<p>Set-CsRgsWorkflow $x</p></td>
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

Microsoft.Rtc.Rgs.Management.WritableSettings.Workflow object. **Set-CsRgsWorkflow** accepts pipelined instances of the Response Group workflow object.

## Return Types

**Set-CsRgsWorkflow** does not return any objects or values. Instead, the cmdlet modifies existing instances of the Microsoft.Rtc.Rgs.Management.WritableSettings.Workflow object.

## 另请参阅

#### 其他资源

[Get-CsRgsWorkflow](get-csrgsworkflow.md)  
[New-CsRgsWorkflow](new-csrgsworkflow.md)  
[Remove-CsRgsWorkflow](remove-csrgsworkflow.md)

