---
title: Set-CsVoiceNormalizationRule
TOCTitle: Set-CsVoiceNormalizationRule
ms:assetid: 68850abb-4ac7-4ae1-bb6e-d991385f92a4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398491(v=OCS.15)
ms:contentKeyID: 49313113
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsVoiceNormalizationRule

 

_**上一次修改主题：** 2015-03-09_

修改语音规范化规则。语音规范化规则用于将电话拨号要求（例如，拨 9 可接入外线）转换为可供 Lync Server 使用的 E.164 电话号码格式。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsVoiceNormalizationRule [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsVoiceNormalizationRule [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-IsInternalExtension <$true | $false>] [-Pattern <String>] [-Priority <Int32>] [-Translation <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例将站点 Redmond 上的 Prefix Redmond 规则的描述设置为“Add a prefix to all numbers on site Redmond”。

    Set-CsVoiceNormalizationRule -Identity "site:Redmond/Prefix Redmond" -Description "Add a prefix to all numbers on site Redmond"

## 示例 2

此示例修改 Identity 为 global/SeattleFourDigit 的语音规范化规则。指定了一个新的 Description 以反映对规则所做的修改。此外，指定了一个 Translation 值以修改规则，以便将与此规则的现有模式匹配的所有号码转换为带有前缀 +1206556 的同一号码。例如，如果现有模式与任何四位号码相匹配，而输入的号码为 1234，则此规则会将该分机转换为号码 +12065561234。

    Set-CsVoiceNormalizationRule -Identity global/SeattleFourDigit -Description "Translate an internal four-digit extension" -Translation '+1206556$1'

## 示例 3

示例 3 更改规范化规则的名称。请记住，更改规范化规则的名称也会更改 Identity 的名称部分。**Set-CsVoiceNormalizationRule** cmdlet 没有 Name 参数，因此为了更改名称，首先调用 **Get-CsVoiceNormalizationRule** cmdlet 检索 Identity 为 global/RedmondFourDigit 的规则，并将返回的对象分配给变量 $a。然后将字符串 RedmondRule 分配给该对象的 Name 属性。接下来，将该变量传递到 **Set-CsVoiceNormalizationRule** cmdlet 的 Instance 参数进行永久性更改。

    $a = Get-CsVoiceNormalizationRule -Identity global/RedmondFourDigit
    $a.name = "RedmondRule"
    Set-CsVoiceNormalizationRule -Instance $a

## 详细说明

此 cmdlet 可修改命名语音规范化规则。这些规则是电话授权和呼叫路由所必需的部分。它们定义了将号码从内部 Lync Server 格式转换为标准 (E.164) 格式的要求。了解正则表达式对定义要转换的号码模式会有所帮助。

使用此 cmdlet 修改的规则是拨号计划的一部分，这些规则不仅可以通过 **Get-CsVoiceNormalizationRule** cmdlet 访问，还可以通过调用 **Get-CsDialPlan** cmdlet 时所返回的 NormalizationRules 属性进行访问。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsVoiceNormalizationRule** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsVoiceNormalizationRule"}

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
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>容易理解的规范化规则描述。</p>
<p>最大字符串长度：512 个字符。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>规则的唯一标识符。指定的 Identity 必须包含范围，后跟一个斜线，然后是名称；例如：site:Redmond/Rule1，其中 site:Redmond 是范围，而 Rule1 是名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>NormalizationRule</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。此对象必须为 NormalizationRule 类型，并且可以通过调用 <strong>Get-CsVoiceNormalizationRule</strong> cmdlet 来检索</p></td>
</tr>
<tr class="even">
<td><p><em>IsInternalExtension</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>如果值为 True，则应用此规则产生的号码为企业内部号码。如果值为 False，则应用此规则将产生外部号码。如果关联的拨号计划的 OptimizeDeviceDialing 属性值设置为 False，则会忽略此值。</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>Pattern</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>一个正则表达式，所拨号码必须与该表达式匹配才能应用该规则。</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>Priority</em></p></td>
<td><p>可选</p></td>
<td><p>System.Int32</p></td>
<td><p>规则应用的顺序。一个号码可能匹配多个规则。此参数设置了针对该号码测试这些规则时所采用的顺序。</p></td>
</tr>
<tr class="odd">
<td><p><em>Translation</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>将应用于号码以便将其转换为 E.164 格式的正则表达式模式。</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.WritableConfig.Policy.Voice.NormalizationRule 对象。**Set-CsVoiceNormalizationRule** cmdlet 接受通过管道传递的语音规范化规则对象的输入。

## 返回类型

**Set-CsVoiceNormalizationRule** cmdlet 不会返回值或对象。此 cmdlet 会配置 Microsoft.Rtc.Management.WritableConfig.Policy.Voice.NormalizationRule 对象的实例。

## 另请参阅

#### 其他资源

[New-CsVoiceNormalizationRule](new-csvoicenormalizationrule.md)  
[Remove-CsVoiceNormalizationRule](remove-csvoicenormalizationrule.md)  
[Get-CsVoiceNormalizationRule](get-csvoicenormalizationrule.md)  
[Test-CsVoiceNormalizationRule](test-csvoicenormalizationrule.md)  
[Set-CsDialPlan](set-csdialplan.md)  
[Get-CsDialPlan](get-csdialplan.md)

