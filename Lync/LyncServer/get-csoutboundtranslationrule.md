---
title: Get-CsOutboundTranslationRule
TOCTitle: Get-CsOutboundTranslationRule
ms:assetid: 0564df17-dcca-44e1-9341-15521e0fa14b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398104(v=OCS.15)
ms:contentKeyID: 49311865
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsOutboundTranslationRule

 

_**上一次修改主题：** 2015-03-09_

Retrieves one or more outbound translation rules. An outbound translation rule converts phone numbers to the local dialing format for interaction with private branch exchange (PBX) systems and public switched telephone network (PSTN) gateways. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsOutboundTranslationRule [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsOutboundTranslationRule [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

This example retrieves all outbound translation rules for the Lync Server deployment.

    Get-CsOutboundTranslationRule

## EXAMPLE 2

This example retrieves a single outbound translation rule: the rule with Identity site:Redmond/Prefix Redmond.

    Get-CsOutboundTranslationRule -Identity "site:Redmond/Prefix Redmond"

## EXAMPLE 3

This example retrieves all site-level outbound translation rules. The command calls the **Get-CsOutboundTranslationRule** cmdlet with a Filter of site:\*, which will return a collection of all rules with Identity values beginning with the string site:.

    Get-CsOutboundTranslationRule -Filter site:*

## Detailed Description

Call this cmdlet to retrieve an existing outbound translation rule. Lync Server normalizes phone numbers to E.164 format. However, many private branch exchange (PBX) systems aren’t able to work with this format. Outbound translations rules translate the number to the local dialing format prior to sending the number to the 中介服务器 or gateway.

Each outbound translation rule is associated with a trunk configuration. More than one outbound translation rule can be associated with each trunk configuration. Therefore, the Identity for each rule consists of a scope along with a name that is unique within the scope (in the format scope/name, for example site:Redmond/OBR1). The rule is automatically associated with the trunk configuration with the same scope.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsOutboundTranslationRule** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsOutboundTranslationRule"}

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
<td><p>Performs a wildcard search on Identity that allows you to narrow down your results to only those outbound translation rules whose identities match the given wildcard string.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>The unique identifier for the outbound translation rule you want to retrieve. The Identity consists of the scope followed by a unique name within each scope (for example, site:Redmond/OutboundRule1). Specifying a value for Identity will return at most one outbound translation rule.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the outbound translation rule from the local replica of the 中央管理存储, rather than the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

This cmdlet retrieves one or more objects of type Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.TranslationRule.

## 另请参阅

#### 其他资源

[New-CsOutboundTranslationRule](new-csoutboundtranslationrule.md)  
[Remove-CsOutboundTranslationRule](remove-csoutboundtranslationrule.md)  
[Set-CsOutboundTranslationRule](set-csoutboundtranslationrule.md)

