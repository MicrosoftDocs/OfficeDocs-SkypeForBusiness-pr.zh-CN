---
title: Set-CsOutboundTranslationRule
TOCTitle: Set-CsOutboundTranslationRule
ms:assetid: fbf82146-7884-418c-8239-66c0ca0f2ba6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413073(v=OCS.15)
ms:contentKeyID: 49314834
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsOutboundTranslationRule

 

_**上一次修改主题：** 2015-03-09_

修改现有的出站转换规则。出站转换规则将电话号码转换成本地拨号格式，以便与专用交换机 (PBX) 系统进行交互。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsOutboundTranslationRule [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsOutboundTranslationRule [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-Pattern <String>] [-Priority <Int32>] [-Translation <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例修改 Identity 为 site:Redmond/Prefix Redmond 的全局出站转换规则。我们提供了一个 Description 来解释此规则，即此规则用于将 E.164 格式的号码转换成七位电话号码。此外，还指定了 Pattern 和 Translation 的值，这将修改这些属性的现有值。这些值通过删除根据 Pattern 中的正则表达式指定的 E.164 号码（此示例中是以 +1425 开头的 12 位号码）的前五位，将其转换成七位号码。例如，号码 +14255551212 将转换为 5551212。

    Set-CsOutboundTranslationRule -Identity "site:Redmond/Prefix Redmond" -Description "Convert to seven digits" -Pattern '^\+1425(\d{7})$' -Translation '$1'

## 示例 2

此示例修改出站转换规则的 Name 属性。请注意，这将导致更改此规则的 Identity。此示例中的第一个命令将调用 **Get-CsOutboundTranslationRule** cmdlet。指定 Identity site:Redmond\\OBR1，将返回一条转换规则，即该 Identity 对应的规则。不显示此规则，而是将其分配给变量 $a。此示例的第二行将字符串“Outbound Rule 1”分配给变量 $a 的 Name 属性，该变量包含对规则 site:Redmond/OBR1 的引用。在此示例的最后一行中，调用 **Set-CsOutboundTranslationRule** cmdlet，指定 Instance 参数并为其传递变量 $a。如果现在调用 Identity 值为 site:Redmond/OBR1 的 **Get-CsOutboundTranslationRule** cmdlet，将不会返回任何内容。这是因为已不存在具有该 Identity 的规则，该规则已替换为 Identity 为 site:Redmond/Outbound Rule 1 的相同规则。

    $a = Get-CsOutboundTranslationRule -Identity "site:Redmond/OBR1"
    $a.Name = "Outbound Rule 1"
    Set-CsOutboundTranslationRule -Instance $a

## 详细说明

Lync Server 将电话号码规范化为 E.164 格式。但是，许多专用交换机 (PBX) 系统无法使用此格式。在将电话号码发送到中介服务器或网关之前，出站转换规则将该号码转换为本地拨号格式。调用此 cmdlet 可修改现有的出站转换规则。

每个出站转换规则都与一种中继配置关联。这意味着，使用此 cmdlet 修改规则将影响对应的中继配置。每种配置可关联有多个出站转换规则。因此，每个规则的标识都包含一个范围以及一个在该范围唯一的名称（格式为“范围/名称”，例如 site:Redmond/OBR1）。该规则自动与同一范围中的中继配置关联。建议通过调用 **Set-CsOutboundTranslationRule** cmdlet 来更改中继配置中的出站转换规则。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsOutboundTranslationRule** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsOutboundTranslationRule"}

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
<th>参数</th>
<th>是否必需</th>
<th>类型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>出站转换规则的友好描述。使用此描述有助于管理员明确地确定规则的用途。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>XdsIdentity</p></td>
<td><p>要修改的出站转换规则的唯一标识符。Identity 由范围后跟各范围中的唯一名称组成。例如，site:Redmond/OutboundRule1。</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>TranslationRule</p></td>
<td><p>出站转换规则的对象引用。该对象的类型必须是 Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.TranslationRule，可以通过调用 <strong>Get-CsOutboundTranslationRule</strong> cmdlet 来检索该对象类型。</p></td>
</tr>
<tr class="even">
<td><p><em>Pattern</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>代表将应用 Translation 的号码格式的正则表达式。</p></td>
</tr>
<tr class="odd">
<td><p><em>Priority</em></p></td>
<td><p>可选</p></td>
<td><p>Int32</p></td>
<td><p>如果号码与多个出站转换规则的 Pattern 相匹配，将按照优先级顺序应用规则。使用此参数指定规则的优先级。</p></td>
</tr>
<tr class="even">
<td><p><em>Translation</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>将应用于匹配 Pattern 的号码以准备该号码进行出站路由的正则表达式。</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.TranslationRule 对象。接受通过管道传递的出站转换规则对象的输入。

## 返回类型

此 cmdlet 不会返回值。它可修改类型为 Microsoft.Rtc.Management.WritableConfig.Settings.TrunkConfiguration.TranslationRule 的对象。

## 另请参阅

#### 其他资源

[New-CsOutboundTranslationRule](new-csoutboundtranslationrule.md)  
[Remove-CsOutboundTranslationRule](remove-csoutboundtranslationrule.md)  
[Get-CsOutboundTranslationRule](get-csoutboundtranslationrule.md)

