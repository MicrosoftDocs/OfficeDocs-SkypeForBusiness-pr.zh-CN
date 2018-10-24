---
title: Remove-CsVoiceNormalizationRule
TOCTitle: Remove-CsVoiceNormalizationRule
ms:assetid: 6a1bf26c-d95b-4a03-8d2d-c17159dcb9be
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398501(v=OCS.15)
ms:contentKeyID: 49313124
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsVoiceNormalizationRule

 

_**上一次修改主题：** 2015-03-09_

Removes a voice normalization rule. Voice normalization rules are used to convert telephone dialing requirements (for example, dialing 9 to access an outside line) to the E.164 phone number format used by Lync Server. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsVoiceNormalizationRule -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example removes the voice normalization rule with the Identity site:Redmond/SeattleRule1.

    Remove-CsVoiceNormalizationRule -Identity site:Redmond/SeattleRule1

## EXAMPLE 2

This example removes all voice normalization rules from site Redmond.

    Remove-CsVoiceNormalizationRule -Identity site:Redmond

## Detailed Description

This cmdlet removes a named voice normalization rule. These rules are a required part of phone authorization and call routing. They define the requirements for converting (or translating) numbers from an internal Lync Server format to a standard (E.164) format. An understanding of regular expressions is helpful in order to define number patterns that will be translated.

Rules that are removed by using this cmdlet will be deleted from the dial plans of the organization, so they won’t be returned by the **Get-CsVoiceNormalizationRule** cmdlet and will not appear in the NormalizationRules property returned by a call to the **Get-CsDialPlan** cmdlet. This means that calling the **Remove-CsVoiceNormalizationRule** cmdlet could leave a dial plan with no normalization rules.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsVoiceNormalizationRule** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsVoiceNormalizationRule"}

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
<td><p>The unique identity of the rule to be removed. If the Identity specified includes the scope followed by a slash and then the name (for example: site:Redmond/Rule1, where site:Redmond is the scope and Rule1 is the name), the one rule with that unique Identity will be removed. If the value passed to the Identity contains only the scope (site:Redmond), all normalization rules at that scope will be removed.</p></td>
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
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Policy.Voice.NormalizationRule object. Accepts pipelined input of voice normalization rule objects.

## Return Types

This cmdlet deletes an object of type Microsoft.Rtc.Management.WritableConfig.Policy.Voice.NormalizationRule.

## 另请参阅

#### 其他资源

[New-CsVoiceNormalizationRule](new-csvoicenormalizationrule.md)  
[Set-CsVoiceNormalizationRule](set-csvoicenormalizationrule.md)  
[Get-CsVoiceNormalizationRule](get-csvoicenormalizationrule.md)  
[Test-CsVoiceNormalizationRule](test-csvoicenormalizationrule.md)  
[Remove-CsDialPlan](remove-csdialplan.md)  
[Get-CsDialPlan](get-csdialplan.md)

