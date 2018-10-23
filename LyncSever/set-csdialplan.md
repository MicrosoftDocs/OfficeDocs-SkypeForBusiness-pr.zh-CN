---
title: Set-CsDialPlan
TOCTitle: Set-CsDialPlan
ms:assetid: 80277dc6-8853-4cbd-87cb-e64f9e135d5f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398644(v=OCS.15)
ms:contentKeyID: 49313408
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsDialPlan

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing dial plan. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsDialPlan [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsDialPlan [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-City <String>] [-Confirm [<SwitchParameter>]] [-CountryCode <String>] [-Description <String>] [-DialinConferencingRegion <String>] [-ExternalAccessPrefix <String>] [-Force <SwitchParameter>] [-NormalizationRules <PSListModifier>] [-OptimizeDeviceDialing <$true | $false>] [-SimpleName <String>] [-State <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the **Set-CsDialPlan** cmdlet is used to modify the dial plan with the Identity RedmondDialPlan. In this case, the only property being modified is the Description; this modification is performed by specifying the Description parameter followed by the text for the new description.

    Set-CsDialPlan -Identity RedmondDialPlan -Description "This plan is for Redmond-based users only."

## EXAMPLE 2

In this example, the **Set-CsDialPlan** cmdlet is used to change the value of the ExternalAccessPrefix property for all the dial plans configured for use in the organization. To do this, the command first uses the **Get-CsDialPlan** cmdlet to return a collection of all the dial plans in the organization. That collection is then piped to the **Set-CsDialPlan** cmdlet, which assigns the value 8 to the ExternalAccessPrefix property for each profile in the collection.

    Get-CsDialPlan | Set-CsDialPlan -ExternalAccessPrefix 8

## Detailed Description

This cmdlet modifies an existing dial plan (also known as a location profile). Dial plans provide information required to enable Enterprise Voice users to make telephone calls. Dial plans are also used by the 会议助理应用程序 for dial-in conferencing. A dial plan determines such things as which normalization rules are applied and whether a prefix must be dialed for external calls.

Note: While normalization rules of a dial plan can be modified with this cmdlet, it is recommended that the **New-CsVoiceNormalizationRule** cmdlet, the**Set-CsVoiceNormalizationRule** cmdlet, or the **Remove-CsVoiceNormalizationRule** cmdlet be used instead. The changes made with those cmdlets will be reflected in the corresponding dial plan.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsDialPlan** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsDialPlan"}

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
<td><p><em>City</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>This parameter is not used with this cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>CountryCode</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>This parameter is not used with this cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A description of this dial plan--what it’s for, what type of user it applies to, or any other information that will be helpful in identifying the purpose of the dial plan.</p>
<p>Maximum characters: 512</p></td>
</tr>
<tr class="odd">
<td><p><em>DialinConferencingRegion</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The name of the region associated with this dial plan. Specify a value for this parameter if the dial plan will be used for dial-in conferencing. This allows the correct access number to be assigned when the conference organizer sets up the conference. Available regions can be retrieved by calling the <strong>Get-CsNetworkRegion</strong> cmdlet.</p>
<p>Maximum characters: 512</p></td>
</tr>
<tr class="even">
<td><p><em>ExternalAccessPrefix</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A number (or set of numbers) that designates the call as external to the organization. (For example, to dial an outside line, first press 9.) This prefix will be ignored by the normalization rules, although these rules will be applied to the rest of the number.</p>
<p>The OptimizeDeviceDialing parameter must be set to True for this value to take effect.</p>
<p>The value of this parameter must match the regular expression [0-9]{1,4}. This means it must be a value one to four digits in length, each digit being a number 0 through 9.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts before making changes.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>The unique identifier designating the scope, or, for per-user plans, a name, to identify the dial plan you want to modify. For example, a site Identity will be in the format site:&lt;sitename&gt;, where sitename is the name of the site. A dial plan at the service scope will be a Registrar or PSTN gateway service, where the Identity value is formatted like this: Registrar:Redmond.litwareinc.com. A per-user Identity will be a unique string value.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>LocationProfile</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。 You can retrieve this object reference by calling the <strong>Get-CsDialPlan</strong> cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>NormalizationRules</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>A list of normalization rules that are applied to this dial plan.</p>
<p>While this list and these rules can be modified directly with this cmdlet, it is recommended that you create normalization rules with the <strong>New-CsVoiceNormalizationRule</strong> cmdlet, which creates the rule and assigns it to the specified dial plan, and modify them with the <strong>Set-CsVoiceNormalizationRule</strong> cmdlet.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>OptimizeDeviceDialing</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Setting this parameter to True will apply the prefix in the ExternalAccessPrefix parameter to calls made outside the organization. This value can be set to True only if a value has been specified for the ExternalAccessPrefix parameter.</p></td>
</tr>
<tr class="even">
<td><p><em>SimpleName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A friendly name for the dial plan. Dial plan names must be unique among all dial plans within a Lync Server deployment.</p>
<p>This string can be up to 256 characters long. Valid characters are alphabetic or numeric characters, hyphen (-), dot (.), plus (+), underscore (_), and parentheses (()).</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>State</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>This parameter is not used with this cmdlet.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Policy.Voice.LocationProfile object. Accepts pipelined input of dial plan objects.

## Return Types

The **Set-CsDialPlan** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Policy.Voice.LocationProfile object.

## 另请参阅

#### 其他资源

[New-CsDialPlan](new-csdialplan.md)  
[Remove-CsDialPlan](remove-csdialplan.md)  
[Get-CsDialPlan](get-csdialplan.md)  
[Grant-CsDialPlan](grant-csdialplan.md)  
[Test-CsDialPlan](test-csdialplan.md)  
[New-CsVoiceNormalizationRule](new-csvoicenormalizationrule.md)  
[Set-CsVoiceNormalizationRule](set-csvoicenormalizationrule.md)  
[Remove-CsVoiceNormalizationRule](remove-csvoicenormalizationrule.md)  
[Get-CsVoiceNormalizationRule](get-csvoicenormalizationrule.md)

