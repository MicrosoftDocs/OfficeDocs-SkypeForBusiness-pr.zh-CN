---
title: New-CsRgsWorkflow
TOCTitle: New-CsRgsWorkflow
ms:assetid: 1a2ac5b7-cb1d-4a83-801f-f27671e71743
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398246(v=OCS.15)
ms:contentKeyID: 49312154
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsRgsWorkflow

 

_**上一次修改主题：** 2015-03-09_

Creates a new Response Group workflow. Workflows determine the actions that are taken when the 响应组应用程序 receives a phone call. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsRgsWorkflow -Name <String> -Parent <RgsIdentity> -PrimaryUri <Uri> [-Active <$true | $false>] [-Anonymous <$true | $false>] [-BusinessHoursID <RgsIdentity>] [-Confirm [<SwitchParameter>]] [-CustomMusicOnHoldFile <AudioFile>] [-DefaultAction <CallAction>] [-Description <String>] [-DisplayNumber <String>] [-EnabledForFederation <$true | $false>] [-Force <SwitchParameter>] [-HolidayAction <CallAction>] [-HolidaySetIDList <Collection>] [-InMemory <SwitchParameter>] [-Language <String>] [-LineUri <Uri>] [-Managed <$true | $false>] [-ManagersByUri <Collection>] [-NonBusinessHoursAction <CallAction>] [-TimeZone <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 creates a new workflow on the service ApplicationServer:atl-cs-001.litwareinc.com. This workflow is given the Name Help Desk and is assigned a primary URI of sip:helpdesk@litwareinc.com.

    New-CsRgsWorkflow -Parent service:ApplicationServer:atl-cs-001.litwareinc.com -Name "Help Desk" -PrimaryUri "sip:helpdesk@litwareinc.com" 

## EXAMPLE 2

The command shown in Example 2 create a new workflow prompt and call action, then assigns those items to a new Response Group workflow. In the first command, the **New-CsRgsPrompt** cmdlet is used to create a text-to-speech prompt “Welcome to the help desk.” This new prompt is stored in a variable named $prompt.

The second command uses the **Get-CsRgsQueue** cmdlet to retrieve the Identity of an existing Response Group queue named Help Desk; the returned Identity is stored in a variable named $queue.

Command 3 then creates a new call action (stored in a variable named $callAction) that references both the new prompt ($prompt) and the retrieved queue ($queue). Finally, the last command in the example creates a new workflow named Help Desk. This command sets the PrimaryUri to sip:helpdesk@litwareinc.com and sets the value of the DefaultAction property to the call action created in the previous step.

    $prompt = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to the help desk."
    $queue = (Get-CsRgsQueue -Identity service:ApplicationServer:atl-cs-001.litwareinc.com -Name "Help Desk").Identity
    $callAction = New-CsRgsCallAction -Prompt $prompt -Action TransferToQueue -QueueId $queue
    New-CsRgsWorkflow -Parent service:ApplicationServer:atl-cs-001.litwareinc.com -Name "Help Desk" -PrimaryUri "sip:helpdesk@litwareinc.com" -DefaultAction $callAction

## Detailed Description

Workflows are a key element in the 响应组应用程序. Each workflow is uniquely associated with a phone number; when someone calls that number, the workflow determines how the call will be handled. For example, the call might be routed to a series of interactive voice response (IVR) questions that prompt the caller to enter additional information ("Press 1 for hardware support. Press 2 for software support.") Alternatively, the call might be placed in a queue and the caller placed on hold until an agent is available to answer the call. The availability of agents to answer calls is also dictated by the workflow: workflows are used to configure business hours (the days of the week and the times of day when agents are available to answer calls) and also holidays (days when no agents are available to answer calls).

New workflows are created by using the **New-CsRgsWorkflow** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsRgsWorkflow** cmdlet: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsRgsWorkflow"}

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
<td><p>Unique name to be assigned to the workflow. The combination of the Parent property and the Name property enables you to uniquely identify workflows without having to refer to the workflow’s globally unique identifier (GUID).</p></td>
</tr>
<tr class="even">
<td><p><em>Parent</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.RgsIdentity</p></td>
<td><p>Service where the new workflow will be hosted. For example: -Parent &quot;service:ApplicationServer:atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>PrimaryUri</em></p></td>
<td><p>Required</p></td>
<td><p>System.Uri</p></td>
<td><p>SIP address for the workflow. For example: -PrimaryUri &quot;sip:helpdesk@litwareinc.com&quot;. The PrimaryUri must begin with the &quot;sip:&quot; prefix.</p></td>
</tr>
<tr class="even">
<td><p><em>Active</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If set to True, this means that the workflow is active and available to take phone calls. If set to False (the default value), the workflow is not available to take phone calls.</p>
<p>When the Active property is set to True then the workflow will be validated before it is created. For example, the workflow will not be created if a DefaultAction has not been specified. If Active is set to False (or not configured) then no validation will take place, and the workflow will be created even if a DefaultAction has not been specified.</p></td>
</tr>
<tr class="odd">
<td><p><em>Anonymous</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If set to True, the identities of individual Response Group agents will be masked any time these agents answer a call. If set to False (the default value), agent identities will be available to callers.</p></td>
</tr>
<tr class="even">
<td><p><em>BusinessHoursID</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.RgsIdentity</p></td>
<td><p>Days of the week and times of the day that workflow agents are available to answer calls. The business hour Identities can be retrieved by using the <strong>Get-CsRgsHoursOfBusiness</strong> cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>CustomMusicOnHoldFile</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.AudioFile</p></td>
<td><p>Represents custom music to be played when callers are placed on hold. (If not defined, callers will hear the default music when placed on hold.) Custom music must be imported by using the <strong>Import-CsRgsAudioFile</strong> cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>DefaultAction</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.CallAction</p></td>
<td><p>Indicates the action to be taken when a workflow is opened during business hours. DefaultAction must be defined by using the <strong>New-CsRgsCallAction</strong> cmdlet, and must either direct the call to a queue or to a question. The DefaultAction parameter is mandatory if the workflow is active, but can be omitted if the workflow is inactive.</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables administrators to add additional information about a Response Group workflow. For example, the Description might include contact information for the owner of the workflow. This description appears in the Lync contact card for the workflow.</p></td>
</tr>
<tr class="odd">
<td><p><em>DisplayNumber</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Phone number for the workflow as displayed in Lync. The DisplayNumber can be formatted any way you want; for example:</p>
<p>-DisplayNumber &quot;555-1219&quot;</p>
<p>-DisplayNumber &quot;1-(425)-555-1219&quot;</p>
<p>-DisplayNumber &quot;1.425.555.1219&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>EnabledForFederation</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether the workflow is available to users from a federated domain. If set to False, only users within your organization will have access to the workflow.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>HolidayAction</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.CallAction</p></td>
<td><p>Action to be taken if a call is received on a holiday. The HolidayAction must be defined by using the <strong>New-CsRgsCallAction</strong> cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>HolidaySetIDList</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Collections.ObjectModel.Collection</p></td>
<td><p>Represents days when workflow agents are not available to answer calls. The holiday set Identities can be retrieved by using the <strong>Get-CsRgsHolidaySet</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="odd">
<td><p><em>Language</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Language that is used to read workflow text-to-speech prompts. The language parameter is optional as long as the operating system is using one of the supported languages shown in the list below. (Note that supported speech languages represent a subset of the languages that can be used on the operating system.)</p>
<p>If the operating system is not using a supported language, then the Language parameter becomes mandatory, and the parameter must specify the language code for a supported language. If your operating system is using a non-supported language on the operating system, and you run the <strong>New-CsRgsWorkflow</strong> cmdlet without including the Language parameter, your command will fail.</p>
<p>For example, suppose your operating system is running under the Faroese language. This language is supported by the Windows operating system, but not by the 响应组应用程序. Therefore, you must include the Language parameter and a supported language when creating a new workflow.</p>
<p>This is required because, if no language is specified, the workflow uses the operating system language. However, that language can be used in a workflow only if it is a language supported by the 响应组应用程序.</p>
<p>The language must be specified using one of the following language codes:</p>
<p>ca-ES – Catalan (Spain)</p>
<p>da-DK – Danish (Denmark)</p>
<p>de-DE – German (Germany)</p>
<p>en-AU – English (Australia)</p>
<p>en-CA – English (Canada)</p>
<p>en-GB – English (United Kingdom)</p>
<p>en-IN – English (India)</p>
<p>en-US – English (United States)</p>
<p>es-ES – Spanish (Spain)</p>
<p>es-MX – Spanish (Mexico)</p>
<p>fi-FI – Finnish (Finland)</p>
<p>fr-CA – French (Canada)</p>
<p>fr-FR – French (France)</p>
<p>it-IT – Italian (Italy)</p>
<p>ja-JP – Japanese (Japan)</p>
<p>ko-KR – Korean (Korea)</p>
<p>nb-NO – Norwegian, Bokmal (Norway)</p>
<p>nl-NL – Dutch (Netherlands)</p>
<p>pl-PL – Polish (Poland)</p>
<p>pt-BR – Portuguese (Brazil)</p>
<p>pt-PT – Portuguese (Portugal)</p>
<p>ru-RU – Russian (Russia)</p>
<p>sv-SE – Swedish (Sweden)</p>
<p>zh-CN – Chinese (People’s Republic of China)</p>
<p>zh-HK – Chinese (Hong Kong SAR)</p>
<p>zh-TW – Chinese (Taiwan)</p>
<p>For example: -Language &quot;nl-NL&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>LineUri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Uri</p></td>
<td><p>Phone number for the workflow. The line Uniform Resource Identifier (URI) must be specified by using the following format: the TEL: prefix followed by a plus sign, followed by the country/region calling code, area code, and phone number (using only digits: no blank spaces, periods, or hyphens). For example: -LineUri &quot;TEL:+14255551219&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>Managed</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>When set to True indicates that the workflow will be managed by one or more users. Those users can be specified by using the ManagedByUri parameter.</p></td>
</tr>
<tr class="even">
<td><p><em>ManagersByUri</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Collections.ObjectModel.Collection</p></td>
<td><p>SIP addresses of the user (or users) who will manage the workflow. For example:</p>
<p>-ManagedByUri &quot;sip:kenmyer@litwareinc.com&quot;</p>
<p>To specify multiple managers separate the manager SIP addresses by using commas:</p>
<p>-ManagedByUri &quot;sip:kenmyer@litwareinc.com&quot;, &quot;sip:pilar@litwareinc.com&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>NonBusinessHoursAction</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.WritableSettings.CallAction</p></td>
<td><p>Action to be taken if a call is received outside the workflow’s business hours. The NonBusinessHoursAction must be defined by using the <strong>New-CsRgsCallAction</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>TimeZone</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Time zone information used when determining holidays and business hours. For example: -TimeZone &quot;Pacific Standard Time&quot;</p></td>
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

None. The **New-CsRgsWorkflow** cmdlet does not accept pipelined input.

## Return Types

The **New-CsRgsWorkflow** cmdlet creates new instances of the Microsoft.Rtc.Rgs.Management.WritableSettings.Workflow object.

## 另请参阅

#### 其他资源

[Get-CsRgsWorkflow](get-csrgsworkflow.md)  
[Remove-CsRgsWorkflow](remove-csrgsworkflow.md)  
[Set-CsRgsWorkflow](set-csrgsworkflow.md)

