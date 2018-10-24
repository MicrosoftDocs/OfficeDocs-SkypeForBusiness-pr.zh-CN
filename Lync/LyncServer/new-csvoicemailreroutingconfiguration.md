---
title: New-CsVoicemailReroutingConfiguration
TOCTitle: New-CsVoicemailReroutingConfiguration
ms:assetid: 37750c6d-9b75-4dde-aa52-79210afe34c2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425849(v=OCS.15)
ms:contentKeyID: 49312519
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsVoicemailReroutingConfiguration

 

_**上一次修改主题：** 2015-03-09_

Creates settings that, when enabled, provide phone numbers that Lync Server routes to over public switched telephone network (PSTN) if IP connectivity from Lync Server in the branch site to the Exchange UM Server located in the data center is not available. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsVoicemailReroutingConfiguration -Identity <XdsIdentity> [-AutoAttendantNumber <String>] [-Confirm [<SwitchParameter>]] [-Enabled <$true | $false>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-SubscriberAccessNumber <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example creates new voice mail rerouting settings that apply to the site Redmond1. The Enabled parameter is set to True to turn on this configuration, and a phone number (+14255551212) is supplied to specify the Auto-Attendant to which calls will be rerouted.

    New-CsVoicemailReroutingConfiguration -Identity site:Redmond1 -Enabled $True -AutoAttendantNumber "+14255551212"

## EXAMPLE 2

This example creates new voice mail rerouting settings that apply to the site Redmond1. A phone number (+14255551213) is supplied to specify the Subscriber Access number to which calls will be rerouted. Notice that the Enabled parameter has not been set. Enabled is set to False by default, so Subscriber Access calls will not be rerouted to this number until the Enabled property is set to True.

    New-CsVoicemailReroutingConfiguration -Identity site:Redmond1 -SubscriberAccessNumber "+14255551213"

## Detailed Description

This cmdlet allows you to create settings that are applied at either the global or site level that determine where Auto-Attendant and Subscriber Access calls are rerouted to over PSTN when IP connectivity is lost.

Auto-Attendant and Subscriber Access are features of Exchange UM. The Auto-Attendant feature provides voice recognition and touch-tone control (dual-tone multifrequency, or DTMF) for outside callers to navigate a company’s phone system to reach the department or employee that they want or, in Message Taking Mode, to accept messages for users. (Voice rerouting for Message Taking Mode is recommended.) Subscriber Access allows internal users to access their Microsoft Outlook mailbox from a phone. The numbers provided by these settings allow callers to leave voice mail messages for Enterprise Voice users (the AutoAttendantNumber setting) and for those users to retrieve voice mail even if the IP connectivity from the Lync Server deployment at a remote site to Exchange UM in the data center is unavailable (the SubscriberAccessNumber setting).

Note that these settings are not available unless the Enabled property has been set to True.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsVoicemailReroutingConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsVoicemailReroutingConfiguration"}

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
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>This parameter contains a unique identifier specifying the scope at which this configuration is applied. New voice mail rerouting configurations can be created only at the site level, so the Identity would be in the format Site:&lt;site name&gt;, where &lt;site name&gt; is the name of the site to which the settings are applied. A global voice mail rerouting configuration exists by default and cannot be re-created by calling the <strong>New-CsVoicemailReroutingConfiguration</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>AutoAttendantNumber</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Phone number of the Auto-Attendant to which the voice mail deposit attempts should be re-routed.</p>
<p>The number supplied to this parameter must be a LineUri of an existing contact object.</p>
<p>Value must be a number beginning with a digit 1 through 9, optionally preceded by a plus (+), followed by any number of digits.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Enabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether attempts to access voice mail should be re-routed through PSTN when IP connectivity is down.</p>
<p>Default: False</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="odd">
<td><p><em>SubscriberAccessNumber</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Subscriber Access number to which the voice mail retrieval attempts should be re-routed.</p>
<p>The number supplied to this parameter must be a LineUri of an existing contact object.</p>
<p>Value must be a number beginning with a digit 1 through 9, optionally preceded by a plus (+), followed by any number of digits.</p></td>
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

None.

## Return Types

Creates an object of type Microsoft.Rtc.Management.WritableConfig.Settings.ExumRouting.VoicemailReroutingConfiguration.

## 另请参阅

#### 其他资源

[Remove-CsVoicemailReroutingConfiguration](remove-csvoicemailreroutingconfiguration.md)  
[Set-CsVoicemailReroutingConfiguration](set-csvoicemailreroutingconfiguration.md)  
[Get-CsVoicemailReroutingConfiguration](get-csvoicemailreroutingconfiguration.md)

