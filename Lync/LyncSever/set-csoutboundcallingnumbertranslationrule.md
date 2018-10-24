---
title: Set-CsOutboundCallingNumberTranslationRule
TOCTitle: Set-CsOutboundCallingNumberTranslationRule
ms:assetid: e9a7190a-a50d-4d01-8f33-66ed88a52b9e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205400(v=OCS.15)
ms:contentKeyID: 49314615
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsOutboundCallingNumberTranslationRule

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing outbound calling number translation rule. An outbound calling number translation rule converts the E.164 phone numbers used by Lync Server 2013 to a format that can be used by trunking peers that do not support E.164 numbers. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsOutboundCallingNumberTranslationRule [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsOutboundCallingNumberTranslationRule [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-Pattern <String>] [-Priority <Int32>] [-Translation <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 changes the Priority of the outbound calling number translation rule with the Identity site:Redmond/SevenDigit. In this example, the Priority is set to 0.

    Set-CsOutboundCallingNumberTranslationRule -Identity "site:Redmond/SevenDigit" -Priority 0

## Detailed Description

Outbound calling number translation rules convert the E.164 phone numbers used by Lync 2013 to a format that can be used by trunking peers that do not support E.164 numbers; when you create a translation rule you supply a regular expression representing the outbound E.164 number (the Pattern) as well as a regular expression representing the converted number (the Translation).

Outbound calling number translation rules must be bound to a collection of trunk configuration settings; when you create a new translation rule you must specify both the Identity of the trunking configuration settings and a name for the new rule (for example, site:Redmond/RedmondTranslationRule). Note that the trunking configuration settings do not necessarily have to exist at the time you create a new rule. For example, suppose you create the rule site:Redmond/RedmondTranslationRule but no trunk configuration settings have been created for the Redmond site. If the Redmond site is a valid site, trunk configuration settings will automatically be created for the site and the new translation rule will be assigned to that collection of settings. However, your command will fail if the Redmond site does not exist.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsOutboundCallingNumberTranslationRule"}

**Lync Server 控制面板:** To edit an existing outbound calling number translation rule using the Lync Server 控制面板, click Voice Routing, click Trunk Configuration, and then double-click the configuration settings containing the rule to be modified. In the Edit Trunk Configuration dialog box, scroll down to the section labeled Calling number translation rules and then double-click the rule to be modified.

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
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables administrators to provide additional text to accompany a translation rule. This description can be used to help administrators clearly identify the purpose of the rule.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier of the translation rule to be modified. The Identity consists of the scope followed by a unique name within each scope. For example:</p>
<p>-Identity &quot;site:Redmond/OutboundRule1&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
</tr>
<tr class="even">
<td><p><em>Pattern</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A regular expression representing the number pattern to which the Translation will be applied.</p></td>
</tr>
<tr class="odd">
<td><p><em>Priority</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int32</p></td>
<td><p>Priority assigned to the rule. If a number matches the Pattern of more than one outbound translation rule, rules are applied in priority order. Rules are processed in order of their assigned priority; the first rule to be processed has a priority of 0; the second rule to be processed has a priority of 1; and so on.</p></td>
</tr>
<tr class="even">
<td><p><em>Translation</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>A regular expression that will be applied to the number matching the Pattern to prepare that number for outbound calling.</p></td>
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

The **Set-CsOutboundCallingNumberTranslationRule** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.CallingNumberTranslationRule\#Decorated object.

## Return Types

None. Instead, the **Set-CsOutboundCallingNumberTranslationRule** cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.CallingNumberTranslationRule\#Decorated object.

## 另请参阅

#### 其他资源

[Get-CsOutboundCallingNumberTranslationRule](get-csoutboundcallingnumbertranslationrule.md)  
[New-CsOutboundCallingNumberTranslationRule](new-csoutboundcallingnumbertranslationrule.md)  
[Remove-CsOutboundCallingNumberTranslationRule](remove-csoutboundcallingnumbertranslationrule.md)

