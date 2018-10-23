---
title: New-CsVoiceNormalizationRule
TOCTitle: New-CsVoiceNormalizationRule
ms:assetid: 189809ff-559e-476a-a32c-8b3812371883
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398240(v=OCS.15)
ms:contentKeyID: 49312132
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsVoiceNormalizationRule

 

_**上一次修改主题：** 2015-03-09_

Creates a new voice normalization rule. Voice normalization rules are used to convert a telephone dialing requirement (for example, dialing 9 to access an outside line) to the E.164 phone number format used by Lync Server. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsVoiceNormalizationRule -Name <String> -Parent <String> <COMMON PARAMETERS>

    New-CsVoiceNormalizationRule -Identity <XdsIdentity> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-IsInternalExtension <$true | $false>] [-Pattern <String>] [-Priority <Int32>] [-Translation <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example creates a new voice normalization rule for site Redmond named Prefix Redmond. Because no other parameters are specified, the rule is created with the default values. Notice that the value passed to the Identity parameter is in double quotes; this is because the name of the rule (Prefix Redmond) contains a space. If the rule name does not contain a space you don’t need to enclose the Identity in double quotes.

Keep in mind that a dial plan for the Redmond site must exist for this command to succeed. You can create a new dial plan by calling the **New-CsDialPlan** cmdlet.

    New-CsVoiceNormalizationRule -Identity "site:Redmond/Prefix Redmond"

## EXAMPLE 2

This example creates a new voice normalization rule named SeattleFourDigit that applies to the per-user dial plan with the Identity SeattleUser. (Note: Rather than specifying a Parent and a Name, we could have instead created this same rule by specifying -Identity SeattleUser/SeattleFourDigit.) We’ve included a Description explaining that this rule is for translating numbers dialed internally with only a 4-digit extension. In addition, Pattern and Translation values have been specified. These values translate a four-digit number (specified by the regular expression in the Pattern) to the same four-digit number, but prefixed by the Translation value (+1206555). For example, if the extension 1234 was entered, this rule would translate that extension to the number +12065551234.

Note the single quotes around the Pattern and Translation values. Single quotes are required for these values; double quotes (or no quotes) will not work in this instance.

As in Example 1, a dial plan with the given scope must exist. In this case, that means a dial plan with the Identity SeattleUser must already exist.

    New-CsVoiceNormalizationRule -Parent SeattleUser -Name SeattleFourDigit -Description "Dialing with internal four-digit extension" -Pattern '^(\d{4})$' -Translation '+1206555$1'

## Detailed Description

This cmdlet creates a named voice normalization rule. These rules are a required part of phone authorization and call routing. They define the requirements for converting (or translating) numbers from an internal Lync Server format to a standard (E.164) format. An understanding of regular expressions is helpful in order to define number patterns that will be translated.

Rules that are created by using this cmdlet are part of the dial plan and, in addition to being accessible through the **Get-CsVoiceNormalizationRule** cmdlet, can also be accessed through the NormalizationRules property returned by a call to the **Get-CsDialPlan** cmdlet. You cannot create a normalization rule unless a dial plan with an Identity matching the scope specified in the normalization rule Identity already exists. For example, you can’t create a normalization rule with the Identity site:Redmond/RedmondNormalizationRule unless a dial plan for site:Redmond already exists.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsVoiceNormalizationRule** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsVoiceNormalizationRule"}

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
<td><p>A unique identifier for the rule. The Identity specified must include the scope followed by a slash and then the name; for example: site:Redmond/Rule1, where site:Redmond is the scope and Rule1 is the name. The name portion will automatically be stored in the Name property. You cannot specify values for Identity and Name in the same command.</p>
<p>Voice normalization rules can be created at the following scopes: global, site, service (Registrar and PSTNGateway only), and per user. A dial plan with an Identity matching the scope of the normalization rule must already exist before a new rule can be created. (To retrieve a list of dial plans, call the <strong>Get-CsDialPlan</strong> cmdlet.)</p>
<p>The Identity parameter is required unless the Parent parameter is specified. You cannot include the Identity parameter and the Parent parameter in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>Name</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The name of the rule. This parameter is required if a value has been specified for the Parent parameter. If no value has been specified for the Parent parameter, Name defaults to the name specified in the Identity parameter. For example, if a rule is created with the Identity site:Redmond/RedmondRule, the Name will default to RedmondRule. The Name parameter and the Identity parameter cannot be used in the same command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Parent</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The scope at which the new normalization rule will be created. This value must be global; site:&lt;sitename&gt;, where &lt;sitename&gt; is the name of the Lync Server site; PSTN gateway or Registrar service, such as PSTNGateway:redmond.litwareinc.com; or a string designating a per user rule. A dial plan with the specified scope must already exist or the command will fail.</p>
<p>The Parent parameter is required unless the Identity parameter is specified. You cannot include the Identity parameter and the Parent parameter in the same command. If you include the Parent parameter, the Name parameter is also required.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A friendly description of the normalization rule.</p>
<p>Maximum string length: 512 characters.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="even">
<td><p><em>IsInternalExtension</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If True, the result of applying this rule will be a number internal to the organization. If False, applying the rule results in an external number. This value is ignored if the value of the OptimizeDeviceDialing property of the associated dial plan is set to False.</p>
<p>Default: False</p></td>
</tr>
<tr class="odd">
<td><p><em>Pattern</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A regular expression that the dialed number must match in order for this rule to be applied.</p>
<p>Default: ^(\d{11})$ (The default represents any set of numbers up to 11 digits.)</p></td>
</tr>
<tr class="even">
<td><p><em>Priority</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>The order in which rules are applied. A phone number might match more than one rule. This parameter sets the order in which the rules are tested against the number.</p></td>
</tr>
<tr class="odd">
<td><p><em>Translation</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The regular expression pattern that will be applied to the number to convert it to E.164 format.</p>
<p>Default: +$1 (The default prefixes the number with a plus sign [+].)</p></td>
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

This cmdlet creates an object of type Microsoft.Rtc.Management.WritableConfig.Policy.Voice.NormalizationRule.

## 另请参阅

#### 其他资源

[Remove-CsVoiceNormalizationRule](remove-csvoicenormalizationrule.md)  
[Set-CsVoiceNormalizationRule](set-csvoicenormalizationrule.md)  
[Get-CsVoiceNormalizationRule](get-csvoicenormalizationrule.md)  
[Test-CsVoiceNormalizationRule](test-csvoicenormalizationrule.md)  
[New-CsDialPlan](new-csdialplan.md)  
[Get-CsDialPlan](get-csdialplan.md)

