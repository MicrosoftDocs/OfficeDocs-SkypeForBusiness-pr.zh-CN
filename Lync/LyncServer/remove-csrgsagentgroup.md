﻿---
title: Remove-CsRgsAgentGroup
TOCTitle: Remove-CsRgsAgentGroup
ms:assetid: dc185da9-0ae0-4f89-8ef8-7cb680d5dc51
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398969(v=OCS.15)
ms:contentKeyID: 49314461
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsRgsAgentGroup

 

_**上一次修改主题：** 2015-03-09_

Removes an existing Response Group agent group. An agent group is a collection of agents assigned to a Response Group queue. Agents are the users assigned to answer calls directed to a particular queue. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsRgsAgentGroup -Instance <AgentGroup> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 deletes all the Response Group agent groups configured for use on the service ApplicationServer:atl-cs-001.litwareinc.com. To do this, the command first uses **Get-CsRgsAgentGroup** to return all the agent groups for ApplicationServer:atl-cs-001.litwareinc.com. Those groups are then piped to, and removed by, the **Remove-CsRgsAgentGroup** cmdlet.

    Get-CsRgsAgentGroup -Identity service:ApplicationServer:atl-cs-001.litwareinc.com | Remove-CsRgsAgentGroup

## EXAMPLE 2

In Example 2, a single Response Group agent group is removed: the group named Help Desk. To do this, **Get-CsRgsAgentGroup** is first used to return the Help Desk agent group (-Name "Help Desk") from ApplicationServer:atl-cs-001.litwareinc.com. This group is then piped to **Remove-CsRgsAgentGroup**, which removes the group from the service.

    Get-CsRgsAgentGroup -Identity service:ApplicationServer:atl-cs-001.litwareinc.com -Name "Help Desk" | Remove-CsRgsAgentGroup

## EXAMPLE 3

Example 3 deletes all the Response Group agent groups on ApplicationServer:atl-cs-001.litwareinc.com that do not use the round robin routing method. To do this, **Get-CsRgsAgentGroup** is first called in order to return a collection of all the agent groups found on the service ApplicationServer:atl-cs-001.litwareinc.com. This collection is then piped to the **Where-Object** cmdlet, which picks out only those groups where the RoutingMethod property is not equal to (-ne) RoundRobin. The filtered collection is then piped to **Remove-CsRgsAgentGroup**, which deletes each item in that collection.

    Get-CsRgsAgentGroup -Identity service:ApplicationServer:atl-cs-001.litwareinc.com | Where-Object {$_.RoutingMethod -ne "RoundRobin"} | Remove-CsRgsAgentGroup

## Detailed Description

When someone calls a phone number associated with the 响应组应用程序, the service starts by determining which workflow corresponds to the number called. Based on the configuration of that workflow, the call might be routed to a set of interactive voice response (IVR) questions (in which the caller is asked one or more questions along the lines of "Is this question about hardware support or software support?"). Alternatively, the call might be placed in a Response Group queue; there the caller will remain on hold until someone is available to answer the call. The people designated to answer calls are known as agents, and a collected group of agents are referred to as a Response Group agent group. Agent groups are associated with workflows, and are further associated with like job responsibilities; for example, help desk personnel might be grouped in the Help Desk agent group while customer support agents might be grouped in the Customer Support agent group.

New agent groups are created by using the **New-CsRgsAgentGroup** cmdlet. If you need to delete an agent group, this can be done by calling the **Remove-CsRgsAgentGroup** cmdlet. Note that this cmdlet deletes the entire group, and all the agents in that group. If you only want to remove a single agent from a group, use the **Set-CsRgsAgentGroup** cmdlet instead.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsRgsAgentGroup** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsRgsAgentGroup"}

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
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.AgentGroup</p></td>
<td><p>Object reference pointing to the agent group to be removed. When piping workflow objects to <strong>Remove-CsRgsAgentGroup</strong> you can leave off the Instance parameter.</p>
<p>To use the Instance parameter use commands similar to this:</p>
<p>$x = Get-CsRgsAgentGroup –Identity ApplicationServer:atl-cs-001.litwareinc.com /1987d3c2-4544-489d-bbe3-59f79f530a83</p>
<p>Remove-CsRgsAgentGroup –Instance $x</p>
<p>Note that you can only remove a single agent group at a time when using the Instance parameter. That means that your object reference ($x) cannot contain multiple agent group objects.</p></td>
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
<td><p>Forces removal of the agent group. If this parameter is present, the agent group will be deleted without warning, even if it is used by an active workflow. If this parameter is not present, then you will be asked to confirm the deletion of any agent group currently being used by an active workflow.</p></td>
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

Microsoft.Rtc.Rgs.Management.WritableSettings.AgentGroup object. **Remove-CsRgsAgentGroup** accepts pipelined instances of the Response Group agent group object.

## Return Types

**Remove-CsRgsAgentGroup** deletes existing instances of the Microsoft.Rtc.Rgs.Management.WritableSettings.AgentGroup object.

## 另请参阅

#### 其他资源

[Get-CsRgsAgentGroup](get-csrgsagentgroup.md)  
[New-CsRgsAgentGroup](new-csrgsagentgroup.md)  
[Set-CsRgsAgentGroup](set-csrgsagentgroup.md)

