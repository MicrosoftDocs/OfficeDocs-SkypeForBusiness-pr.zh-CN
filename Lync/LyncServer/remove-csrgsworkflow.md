﻿---
title: Remove-CsRgsWorkflow
TOCTitle: Remove-CsRgsWorkflow
ms:assetid: 9626df55-e3ed-478a-a485-f2a9abcf493b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398765(v=OCS.15)
ms:contentKeyID: 49313656
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsRgsWorkflow

 

_**上一次修改主题：** 2015-03-09_

Deletes an existing Response Group workflow. Workflows determine the actions that are taken when the 响应组应用程序 receives a phone call. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsRgsWorkflow -Instance <Workflow> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 removes all the Response Group workflows from the service ApplicationServer:atl-cs-001.litwareinc.com. To do this, the command first calls **Get-CsRgsWorkflow** to return a collection of all the workflows found on ApplicationServer:atl-cs-001.litwareinc.com. That collection is then piped to **Remove-CsRgsWorkflow**, which deletes each workflow in the collection.

    Get-CsRgsWorkflow -Identity Service:ApplicationServer:atl-cs-001.litwareinc.com | Remove-CsRgsWorkflow

## EXAMPLE 2

The command shown in Example 2 deletes a single Response Group workflow: the workflow named "Help Desk Workflow" located on the service ApplicationServer:atl-cs-001.litwareinc.com. To do this, **Get-CsRgsWorkflow** is first used to return the workflow named Help Desk Workflow from the service ApplicationServer:atl-cs-001.litwareinc.com. That workflow is then piped to, and deleted by, **Remove-CsRgsWorkflow**.

    Get-CsRgsWorkflow service:ApplicationServer:atl-cs-001.litwareinc.com -Name "Help Desk Workflow" | Remove-CsRgsWorkflow

## EXAPMLE 3

Example 3 deletes all the United States (U.S.) English language workflows from the service ApplicationServer:atl-cs-001.litwareinc.com. To do this, **Get-CsRgsWorkflow** is first used to retrieve all workflows found on ApplicationServer:atl-cs-001.litwareinc.com. This collection is then piped to the **Where-Object** cmdlet, which selects only those workflows where the language is equal to U.S. English (en-us). This filtered collection is then piped to the **Remove-CsRgsWorkflow** cmdlet, which deletes each item in the collection.

    Get-CsRgsWorkflow service:ApplicationServer:atl-cs-001.litwareinc.com | Where-Object {$_.Language -eq "en-us"} | Remove-CsRgsWorkflow

## EXAMPLE 4

The command shown in Example 4 deletes all the Response Group workflows on the service ApplicationServer:atl-cs-001.litwareinc.com that have a value configured for the CustomMusicOnHoldFile property. In order to accomplish this, the command first uses **Get-CsRgsWorkflow** to return a collection of all the workflows found on ApplicationServer:atl-cs-001.litwareinc.com. That collection is then piped to the **Where-Object** cmdlet, which selects only those workflows where the CustomMusicOnHoldFile property is not equal to a null value. (If the property is not equal to a null value, that means that custom music has been defined for this workflow.) The filtered collection is then piped to **Remove-CsRgsWorkflow**, which removes each item in the collection.

    Get-CsRgsWorkflow service:ApplicationServer:atl-cs-001.litwareinc.com | Where-Object {$_.CustomMusicOnHoldFile -ne $Null} | Remove-CsRgsWorkflow

## Detailed Description

Workflows are a key element in the 响应组应用程序. Each workflow is uniquely associated with a phone number; when someone calls that number, the workflow determines how the call will be handled. For example, the call might be routed to a series of interactive voice response (IVR) questions that prompt the caller to enter additional information ("Press 1 for hardware support. Press 2 for software support.") Alternatively, the call might be placed in a queue and the caller placed on hold until an agent is available to answer the call. The availability of agents to answer calls is also dictated by the workflow: workflows are used to maintain both the business hours (the days of the week and the times of day when agents are available to answer calls) and the holidays (days when no agents are available to answer calls).

New workflows are created by using the **New-CsRgsWorkflow** cmdlet. After these workflows have been created, they can later be deleted by using **Remove-CsRgsWorkflow**. Note that, when you delete a workflow, the workflow is completely removed from the 响应组应用程序. If you want to temporarily disable a workflow, don’t use **Remove-CsRgsWorkflow**; instead, use the **Set-CsRgsWorkflow** cmdlet to disable (and then later re-enable) the workflow.

If you try to delete an active workflow, **Remove-CsRgsWorkflow** will prompt you to verify that you really want to delete the workflow; **Remove-CsRgsWorkflow** will take no further action until you respond to the prompt. To bypass this prompt, and to silently delete an active workflow, use the Force parameter. For example:

Get-CsRgsWorkflow –Identity "service:ApplicationServer:atl-cs-001.litwareinc.com " | Remove-CsRgsWorkflow –Force

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsRgsWorkflow** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsRgsWorkflow"}

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
<td><p>Object reference pointing to the workflow to be removed. When piping workflow objects to <strong>Remove-CsRgsWorkflow</strong> you can leave off the Instance parameter.</p>
<p>To use the Instance parameter use commands similar to this:</p>
<p>$x = Get-CsRgsWorkflow –Identity ApplicationServer:atl-cs-001.litwareinc.com /1987d3c2-4544-489d-bbe3-59f79f530a83</p>
<p>Remove-CsRgsWorkflow –Instance $x</p>
<p>Note that you can only remove a single workflow at a time when using the Instance parameter. That means that your object reference ($x) cannot contain multiple workflow objects.</p></td>
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
<td><p>Forces removal of the workflow. If this parameter is present, the workflow will be deleted without warning, even if it is currently active. If this parameter is not present then you will be asked to confirm the deletion of any active workflow.</p></td>
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

Microsoft.Rtc.Rgs.Management.WritableSettings.Workflow object**. Remove-CsRgsWorkflow** accepts pipelined instances of the Response Group workflow object.

## Return Types

**Remove-CsRgsWorkflow** deletes existing instances of the Microsoft.Rtc.Rgs.Management.WritableSettings.Workflow object.

## 另请参阅

#### 其他资源

[Get-CsRgsWorkflow](get-csrgsworkflow.md)  
[New-CsRgsWorkflow](new-csrgsworkflow.md)  
[Set-CsRgsWorkflow](set-csrgsworkflow.md)

