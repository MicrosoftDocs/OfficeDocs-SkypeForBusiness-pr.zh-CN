﻿---
title: New-CsDialPlan
TOCTitle: New-CsDialPlan
ms:assetid: 3889c696-1070-47bd-beb9-da7e18ec90f0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425860(v=OCS.15)
ms:contentKeyID: 49312503
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsDialPlan

 

_**上一次修改主题：** 2015-03-09_

Creates a new dial plan. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsDialPlan -Identity <XdsIdentity> [-City <String>] [-Confirm [<SwitchParameter>]] [-CountryCode <String>] [-Description <String>] [-DialinConferencingRegion <String>] [-ExternalAccessPrefix <String>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-NormalizationRules <PSListModifier>] [-OptimizeDeviceDialing <$true | $false>] [-SimpleName <String>] [-State <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 creates a new dial plan with the Identity RedmondDialPlan. (The absence of a scope in the Identity value indicates that this is a per-user policy. Dial plans created at the per-user scope can be directly assigned to users and groups.) All other properties of the dial plan will be assigned default values.

    New-CsDialPlan -Identity RedmondDialPlan

## EXAMPLE 2

The commands shown in Example 2 create a new dial plan with the Identity site:Redmond (meaning the dial plan applies to all users on the Redmond site who do not have a per-user or service-level dial plan assigned to them) and the SimpleName RedmondSiteDialPlan. The next line in the example then creates a new normalization rule associated with that plan. A default normalization rule is created for a dial plan, but this is created mostly as a placeholder--the values are of limited use. So after calling the **New-CsDialPlan** cmdlet to create a new dial plan, you should call the **New-CsVoiceNormalizationRule** cmdlet to create a named rule that is functional for your organization. That’s exactly what line 2 of this example does: it calls the **New-CsVoiceNormalizationRule** cmdlet and creates a rule for the Redmond site with the name SeattlePrefix and specifying the Pattern and Translation properties for the rule. No further steps need to be taken to modify the dial plan; the changes to the normalization rule are automatically applied to the dial plan with the identity matching that of the normalization rule. (The site:Redmond portion of the Identity matches the dial plan Identity; SeattlePrefix is the name of the normalization rule. Multiple normalization rules can be applied to one dial plan, so each normalization rule needs a unique name within a given scope.)

    New-CsDialPlan -Identity site:Redmond -SimpleName RedmondSiteDialPlan
    New-CsVoiceNormalizationRule -Identity "site:Redmond/SeattlePrefix" -Pattern "^9(\d*){1,5}$" -Translation "+1206$1"

## EXAMPLE 3

The command shown in Example 3 creates a new dial plan with the Identity RedmondDialPlan and specifies a Description to explain what the dial plan is for. (Dial plans created at the per-user scope can be directly assigned to users and groups.) The default values will be assigned for all other parameters.

    New-CsDialPlan -Identity RedmondDialPlan -Description "Dial plan for Redmond users"

## Detailed Description

This cmdlet creates a new dial plan (also known as a location profile). Dial plans provide information required to enable Enterprise Voice users to make telephone calls. Dial plans are also used by the 会议助理应用程序 for dial-in conferencing. A dial plan determines such things as which normalization rules are applied and whether a prefix must be dialed for external calls.

Creating a dial plan automatically creates a default voice normalization rule. Normalization rules can be modified by calling the **Set-CsVoiceNormalizationRule** cmdlet. New normalization rules can be added to a dial plan by calling the **New-CsVoiceNormalizationRule** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsDialPlan** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsDialPlan"}

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
<td><p>A unique identifier designating the scope and name (site), the service role and FQDN, or the name (per user) to identify the dial plan. For example, a site Identity would be entered in the format site:&lt;sitename&gt;, where sitename is the name of the site. A dial plan at the service scope must be a Registrar or PSTN gateway service, where the Identity value is formatted like this: Registrar:Redmond.litwareinc.com. A per-user Identity would be entered simply as a unique string value.</p></td>
</tr>
<tr class="even">
<td><p><em>City</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>This parameter is not used with this cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>CountryCode</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>This parameter is not used with this cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A description of this dial plan--what it’s for, what type of user it applies to, or any other information that will be helpful in identifying the purpose of the dial plan.</p>
<p>Maximum characters: 512</p></td>
</tr>
<tr class="even">
<td><p><em>DialinConferencingRegion</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>The name of the region associated with this dial plan. Specify a value for this parameter if the dial plan will be used for dial-in conferencing. This allows the correct access number to be assigned when the conference organizer sets up the conference. Available regions can be retrieved by calling the <strong>Get-CsNetworkRegion</strong> cmdlet.</p>
<p>Maximum characters: 512</p></td>
</tr>
<tr class="odd">
<td><p><em>ExternalAccessPrefix</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A number (or set of numbers) that designates the call as external to the organization. (For example, to dial an outside line, first press 9.) This prefix will be ignored by the normalization rules, although these rules will be applied to the rest of the number.</p>
<p>The OptimizeDeviceDialing parameter must be set to True for this value to take effect.</p>
<p>This parameter must match the regular expression [0-9]{1,4}. This means it must be a value 0 through 9, one to four digits in length.</p>
<p>Default: 9</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts before making changes.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="even">
<td><p><em>NormalizationRules</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>A list of normalization rules that are applied to this dial plan.</p>
<p>While this list and these rules can be created directly with this cmdlet, we recommend that you create the normalization rules with the <strong>New-CsVoiceNormalizationRule</strong> cmdlet, which creates the rule and assigns it to the specified dial plan.</p>
<p>Each time a new dial plan is created, a new voice normalization rule with default settings is also created for that site, service, or per-user dial plan. By default the Identity of the new voice normalization rule is the dial plan Identity followed by a slash followed by the name Prefix All. For example, site:Redmond/Prefix All.</p>
<p>Default: {Description=;Pattern=^(\d11)$;Translation=+$1;Name=Prefix All;IsInternalExtension=False } Note: This default is only a placeholder. For the dial plan to be useful, you should either modify the normalization rule created by the dial plan or create a new rule for the site, service, or user. You can create a new normalization rule by calling the <strong>New-CsVoiceNormalizationRule</strong> cmdlet; modify a normalization rule by calling the <strong>Set-CsVoiceNormalizationRule</strong> cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>OptimizeDeviceDialing</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Setting this parameter to True will apply the prefix in the ExternalAccessPrefix parameter to calls made outside the organization. This value can be set to True only if a value has been specified for the ExternalAccessPrefix parameter.</p>
<p>Default: False</p></td>
</tr>
<tr class="even">
<td><p><em>SimpleName</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A display name for the dial plan. This name must be unique among all dial plans within the Lync Server deployment.</p>
<p>This string can be up to 256 characters long. Valid characters are alphabetic or numeric characters, hyphen (-), dot (.), plus (+), underscore (_), and parentheses (()).</p>
<p>This parameter must contain a value. However, if you don’t provide a value in the call to the <strong>New-CsDialPlan</strong> cmdlet, a default value will be supplied. The default value for a Global dial plan is Prefix All. The default for a site-level dial plan is the name of the site. The default for a service is the name of the service (Registrar or PSTN gateway) followed by an underscore, followed by the service fully qualified domain name (FQDN). For example, Registrar_pool0.litwareinc.com. The default for a per-user dial plan is the Identity of the dial plan.</p></td>
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

None.

## Return Types

This cmdlet creates an object of type Microsoft.Rtc.Management.WritableConfig.Policy.Voice.LocationProfile.

## 另请参阅

#### 其他资源

[Remove-CsDialPlan](remove-csdialplan.md)  
[Set-CsDialPlan](set-csdialplan.md)  
[Get-CsDialPlan](get-csdialplan.md)  
[Grant-CsDialPlan](grant-csdialplan.md)  
[Test-CsDialPlan](test-csdialplan.md)  
[New-CsVoiceNormalizationRule](new-csvoicenormalizationrule.md)  
[Set-CsVoiceNormalizationRule](set-csvoicenormalizationrule.md)  
[Remove-CsVoiceNormalizationRule](remove-csvoicenormalizationrule.md)  
[Get-CsVoiceNormalizationRule](get-csvoicenormalizationrule.md)

