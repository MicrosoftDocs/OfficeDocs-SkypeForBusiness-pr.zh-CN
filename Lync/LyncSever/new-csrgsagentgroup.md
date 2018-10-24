---
title: New-CsRgsAgentGroup
TOCTitle: New-CsRgsAgentGroup
ms:assetid: faaf46f9-1063-4d64-a36f-872e657cd869
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413065(v=OCS.15)
ms:contentKeyID: 49314815
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsRgsAgentGroup

 

_**上一次修改主题：** 2015-03-09_

Creates a new Response Group agent group. An agent group is a collection of agents assigned to a Response Group queue. Agents are the users assigned to answer calls directed to a particular queue. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsRgsAgentGroup -Name <String> -Parent <RgsIdentity> [-AgentAlertTime <Int16>] [-AgentsByUri <Collection>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-DistributionGroupAddress <String>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-ParticipationPolicy <Informal | Formal>] [-RoutingMethod <LongestIdle | Serial | Parallel | RoundRobin | Attendant>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 creates a new Response Group agent group named Help Desk Group; this new group is located on the service ApplicationServer:atl-cs-001.litwareinc.com. To create the group, the command calls **New-CsRgsAgentGroup** along with the Parent and Name parameters. In this example, no other group parameters are specified, meaning the group will use all the default property values. Because no agents have been assigned to this group any calls routed to the new agent group will automatically be disconnected.

    New-CsRgsAgentGroup -Parent service:ApplicationServer:atl-cs-001.litwareinc.com -Name "Help Desk Group"

## EXAMPLE 2

In Example 2, a new Response Group agent group is created and, at the same time, a pair of agents is assigned to that group. To do this, the command calls **New-CsRgsAgentGroup** along with the parameters Parent and Name. In addition, this example also includes the parameter AgentsByUri, accompanied by the parameter value "sip:kenmyer@litwareinc.com","sip:pilarackerman@litwareinc.com". This value is a comma-separated list of the SIP addresses to be added to the agent group.

    New-CsRgsAgentGroup -Parent service: ApplicationServer:atl-cs-001.litwareinc.com -Name "Help Desk Group" -AgentsByUri "sip:kenmyer@litwareinc.com","sip:pilarackerman@litwareinc.com"

## Detailed Description

When someone calls a phone number associated with the 响应组应用程序, the application first determines which workflow corresponds to the number called. Based on the configuration of that workflow, the call might be routed to a set of interactive voice response (IVR) questions (in which the caller is asked one or more questions along the lines of "Is this question about hardware support or software support?"). Alternatively, the call might be placed in a Response Group queue; there the caller will be put on hold until a designated person is available to answer the call. The people designated to answer calls are known as agents, and a collected group of agents are referred to as a Response Group agent group. Agent groups are associated with queues, and are further associated with similar job responsibilities: help desk personnel might be grouped in the Help Desk agent group while customer support agents might be grouped in the Customer Support agent group.

If multiple groups are assigned to a queue, the 响应组应用程序 will start by ringing all the available agents in the first group assigned to that queue. If none of those agents answer, the application will then start ringing all the available agents in the next group assigned to the queue.

New agent groups are created by using the **New-CsRgsAgentGroup** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsRgsAgentGroup** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

    Get-CsAdminRole | Where-Object  {$_.Cmdlets -match "New-CsRgsAgentGroup"}

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
<td><p>Unique name to be assigned to the agent group. The combination of the Parent property and the Name property enables you to uniquely identify agent groups without having to refer to the group’s globally unique identifier (GUID).</p></td>
</tr>
<tr class="even">
<td><p><em>Parent</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.RgsIdentity</p></td>
<td><p>Service where the new agent group will be hosted. For example: -Parent &quot;service:ApplicationServer:atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>AgentAlertTime</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int16</p></td>
<td><p>Represents the amount of time (in seconds) that a call can remain unanswered before it is automatically routed to the next agent. The AgentAlertTime can be set to any integer value between 10 and 600 seconds (10 minutes), inclusive. The default value is 20 seconds. <strong>Note:</strong> The Agent alert time setting cannot exceed 180 seconds. If it exceeds 180 seconds, the client application will reject the call due to the SIP transaction timer reaching its maximum wait time. To avoid this, set the Alert Time value to less than 180 seconds.</p></td>
</tr>
<tr class="even">
<td><p><em>AgentsByUri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Collections.ObjectModel.Collection</p></td>
<td><p>Enables you to individually add agents to an agent group. New agents are identified using their SIP addresses.</p>
<p>Note that you can only select users who have been enabled for Enterprise Voice.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables administrators to provide additional, explanatory information about the agent group. For example, the Description might contain information about who to contact if the group does not receive the expected phone calls.</p></td>
</tr>
<tr class="odd">
<td><p><em>DistributionGroupAddress</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to add all the members of a distribution group to an agent group.</p></td>
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
<td><p><em>ParticipationPolicy</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.ParticipationPolicy</p></td>
<td><p>Indicates whether or not agents are required to formally sign on to the system in order to receive phone calls intended for the group. If ParticipationPolicy is set to Informal (the default value) sign-in is not required. If ParticipationPolicy is set to Formal then sign-in is required.</p></td>
</tr>
<tr class="odd">
<td><p><em>RoutingMethod</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.RoutingMethod</p></td>
<td><p>Specifies the method used to route new calls to agents. The RoutingMethod must be set to one of the following values:</p>
<p>LongestIdle – Calls are routed to the agent who has been idle (that is, not involved in a Lync activity) for the longest period of time.</p>
<p>RoundRobin – Calls are routed to the next agent on the list.</p>
<p>Serial – Calls are always routed to the first agent on the list, and are only routed to other agents if this person is not available or does not answer within the allotted time.</p>
<p>Parallel – Calls are routed to all agents at the same time, except for agents whose presence status indicates that they are in a call or otherwise unavailable.</p>
<p>Attendant – Calls are routed to all agents at the same time, even if the agent’s presence status indicates that he or she is in a call or otherwise unavailable. The only exception occurs when an agent has set his or her presence to Do Not Disturb.</p>
<p>The default routing method is Parallel.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. **New-CsRgsAgentGroup** does not accept pipelined input.

## Return Types

**New-CsRgsAgentGroup** creates new instances of the Microsoft.Rtc.Rgs.Management.WritableSettings.AgentGroup object.

## 另请参阅

#### 其他资源

[Get-CsRgsAgentGroup](get-csrgsagentgroup.md)  
[Remove-CsRgsAgentGroup](remove-csrgsagentgroup.md)  
[Set-CsRgsAgentGroup](set-csrgsagentgroup.md)

