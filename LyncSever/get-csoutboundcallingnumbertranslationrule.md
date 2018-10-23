---
title: Get-CsOutboundCallingNumberTranslationRule
TOCTitle: Get-CsOutboundCallingNumberTranslationRule
ms:assetid: 65589388-f935-4d25-ae74-362be97c8597
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204962(v=OCS.15)
ms:contentKeyID: 49313066
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsOutboundCallingNumberTranslationRule

 

_**上一次修改主题：** 2015-03-09_

Returns information about the outbound calling number translation rules created for use in your organization. An outbound calling number translation rule converts the E.164 phone numbers used by Lync Server 2013 to a format that can be used by trunking peers that do not support E.164 numbers. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsOutboundCallingNumberTranslationRule [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsOutboundCallingNumberTranslationRule [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 returns information about all the outbound calling number translation rules currently configured for use in the organization.

    Get-CsOutboundCallingNumberTranslationRule

## Example 2

In Example 2, information is returned only for the outbound calling number translation rule that has the Identity "site:Redmond/SevenDigit."

    Get-CsOutboundCallingNumberTranslationRule -Identity "site:Redmond/SevenDigit"

## Example 3

Example 3 returns information for all the outbound calling number translation rules configured for the Redmond site. This is done by setting the value of the Identity parameter to the Identity of the Redmond site (site:Redmond).

    Get-CsOutboundCallingNumberTranslationRule -Identity "site:Redmond"

## Example 4

The command shown in Example 4 returns information only for outbound calling number translation rules that are on the Redmond site and have a Priority equal to 0. To do this, the command first uses the **Get-CsOutboundCallingNumberTranslationRule** cmdlet and the Identity parameter to return a collection of all the translation rules assigned to the Redmond site. This collection is then piped to the **Where-Object** cmdlet, which picks out only those rules that have a Priority equal to 0.

    Get-CsOutboundCallingNumberTranslationRule -Identity "site:Redmond" | Where-Object {$_.Priority -eq 0}

## Detailed Description

Outbound calling number translation rules convert the E.164 phone numbers used by Lync 2013 to a format that can be used by trunking peers that do not support E.164 numbers; when you create a translation rule you supply a regular expression representing the outbound E.164 number (the Pattern) as well as a regular expression representing the converted number (the Translation).

Outbound calling number translation rules must be bound to a collection of trunk configuration settings; when you create a new translation rule you must specify both the Identity of the trunking configuration settings and a name for the new rule (for example, site:Redmond/RedmondTranslationRule). Note that the trunking configuration settings do not necessarily have to exist at the time you create a new rule. For example, suppose you create the rule site:Redmond/RedmondTranslationRule but no trunk configuration settings have been created for the Redmond site. If the Redmond site is a valid site, trunk configuration settings will automatically be created for the site and the new translation rule will be assigned to that collection of settings. However, your command will fail if the Redmond site does not exist.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsOutboundCallingNumberTranslationRule"}

**Lync Server 控制面板:** To view outbound calling number translation roles in the Lync Server 控制面板, click Voice Routing and then click Trunk Configuration. Double-click appropriate entry in the Name column and then, in the Edit Trunk Configuration dialog box, scroll down to the section labeled Calling number translation rules.

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
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Performs a wildcard search that allows you to return only those outbound translation rules that have Identities that match the wildcard string. For example, this syntax returns all the translation rules that include the string value &quot;Redmond&quot;:</p>
<p>-Filter &quot;*Redmond*&quot;</p>
<p>To return all the translation rules configured at the site scope use this syntax:</p>
<p>-Filter &quot;site:*&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the outbound calling number translation rule you want to retrieve. The Identity consists of the scope followed by a unique name within each scope; for example:</p>
<p>-Identity &quot;site:Redmond/OutboundRule1&quot;</p>
<p>To return all the translation rules configured for a specific scope (such as the Redmond site) simply set the Identity to the scope itself:</p>
<p>-Identity &quot;site:Redmond&quot;</p>
<p>If neither the Identity parameter nor the Filter parameter is specified the <strong>Get-CsOutboundCallingNumberTranslationRule</strong> cmdlet returns information about all your outbound calling number translation rules.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the outbound calling number translation rule data from the local replica of the Central Management store rather than from the Central Management store itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsOutboundCallingNumberTranslationRule** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsOutboundCallingNumberTranslationRule** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.CallingNumberTranslationRule\#Decorated object.

## 另请参阅

#### 其他资源

[New-CsOutboundCallingNumberTranslationRule](new-csoutboundcallingnumbertranslationrule.md)  
[Remove-CsOutboundCallingNumberTranslationRule](remove-csoutboundcallingnumbertranslationrule.md)  
[Set-CsOutboundCallingNumberTranslationRule](set-csoutboundcallingnumbertranslationrule.md)

