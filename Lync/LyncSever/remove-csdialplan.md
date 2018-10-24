---
title: Remove-CsDialPlan
TOCTitle: Remove-CsDialPlan
ms:assetid: 99845b82-1730-494a-8f47-2dec5ef177c1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398791(v=OCS.15)
ms:contentKeyID: 49313688
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsDialPlan

 

_**上一次修改主题：** 2015-03-09_

Removes the specified dial plan. This cmdlet can also be used to remove the global dial plan. If you remove the global dial plan, however, the dial plan will not actually be removed; instead, the settings will simply be reset to their default values. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsDialPlan -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 uses the **Remove-CsDialPlan** cmdlet to delete the per-user dial plan with the Identity RedmondDialPlan. Note that when you delete a dial plan, you do not necessarily have to assign a new plan to users who were assigned the now-deleted plan. Instead, those users will use the dial plan assigned to their service or site, or the global plan.

    Remove-CsDialPlan -Identity RedmondDialPlan

## EXAMPLE 2

In Example 2 all the dial plans that include the word Redmond in their description are deleted. To do this, the command first calls the **Get-CsDialPlan** cmdlet to return a collection of all the dial plans configured for use within the organization. That collection is then piped to the **Where-Object** cmdlet, which applies a filter that limits the returned data to profiles that include the word Redmond in their description. After that's done, the filtered collection is passed to the **Remove-CsDialPlan** cmdlet, which removes all the dial plans in the collection.

    Get-CsDialPlan | Where-Object {$_.Description -match "Redmond"} | Remove-CsDialPlan

## Detailed Description

This cmdlet removes an existing dial plan (also known as a location profile). Dial plans provide information required to enable Enterprise Voice users to make telephone calls. Dial plans are also used by the 会议助理应用程序 for dial-in conferencing. A dial plan determines such things as which normalization rules are applied and whether a prefix must be dialed for external calls.

Note: Removing a dial plan will also remove any associated normalization rules. If the global dial plan is removed, any associated normalization rules will also be removed, but a default global normalization rule will be created.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsDialPlan** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsDialPlan"}

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
<td><p>The unique identifier of the dial plan you want to remove.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Policy.Voice.LocationProfile object. The **Remove-CsDialPlan** cmdlet accepts pipelined input of dial plan objects.

## Return Types

This cmdlet removes instances of the Microsoft.Rtc.Management.WritableConfig.Policy.Voice.LocationProfile object.

## 另请参阅

#### 其他资源

[New-CsDialPlan](new-csdialplan.md)  
[Set-CsDialPlan](set-csdialplan.md)  
[Get-CsDialPlan](get-csdialplan.md)  
[Grant-CsDialPlan](grant-csdialplan.md)  
[Test-CsDialPlan](test-csdialplan.md)  
[Remove-CsVoiceNormalizationRule](remove-csvoicenormalizationrule.md)  
[Get-CsVoiceNormalizationRule](get-csvoicenormalizationrule.md)

