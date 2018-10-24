---
title: Get-CsVoiceNormalizationRule
TOCTitle: Get-CsVoiceNormalizationRule
ms:assetid: 59fe1370-1cec-4cf9-8f65-029a7c2454d1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398393(v=OCS.15)
ms:contentKeyID: 49312948
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsVoiceNormalizationRule

 

_**上一次修改主题：** 2015-03-09_

返回有关您组织中使用的语音规范化规则的信息。语音规范化规则可将电话拨号要求（例如，拨 9 以接入外线）转换为可供 Lync Server 使用的 E.164 电话号码格式。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsVoiceNormalizationRule [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsVoiceNormalizationRule [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## 示例

## 示例 1

此示例检索为组织定义的所有语音规范化规则。

    Get-CsVoiceNormalizationRule

## 示例 2

示例 2 检索为所有站点指定的所有语音规范化规则。

    Get-CsVoiceNormalizationRule -Filter site*

## 示例 3

示例 3 检索范围中包含字母 s 的所有语音规范化规则。例如，这将返回所有站点和服务级别规则，以及范围名称中含有 s 的每用户规则，比如 RedmondEastUsers。

    Get-CsVoiceNormalizationRule -Filter *s*

## 示例 4

示例 2 和示例 3 中使用的 Filter 参数仅与 Identity 的范围部分进行匹配。此示例对名称部分执行匹配以返回 Name 中包含字符串“seattle”的所有规则。为此，首先调用 **Get-CsVoiceNormalizationRule** cmdlet 以检索组织的所有规范化规则。然后，将此集合通过管道传递到 **Where-Object** cmdlet，以找出集合中 Name 属性与字符串“seattle”匹配的所有项。

    Get-CsVoiceNormalizationRule | Where-Object {$_.Name -match "seattle"}

## 详细说明

此 cmdlet 返回一个命名语音规范化规则或语音规范化规则集合。这些规则是电话授权和呼叫路由所必需的部分。它们定义了将号码从内部 Lync Server 格式转换为标准 (E.164) 格式的要求。了解正则表达式对定义要转换的号码模式会有所帮助。

此 cmdlet 访问的规则也可以通过调用 **Get-CsDialPlan** cmdlet 时返回的 NormalizationRules 属性进行访问。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsVoiceNormalizationRule** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsVoiceNormalizationRule"}

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
<td><p><em>Filter</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>基于 Identity 使用通配符字符串返回规范化规则集合。请注意，Filter 仅对 Identity 的范围部分起作用，对名称部分不起作用。例如，筛选器值 *lob* 将返回全局范围（包含字母 lob 的范围）的所有规则，但不返回标识为 site:Redmond/lobby 的规则，其中 lob 仅在 Identity 的名称部分，而不在范围中。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>规则的唯一标识符。如果为此参数指定了值，则必须采用“范围/名称”格式；例如，site:Redmond/Rule1，其中 site:Redmond 是范围，而 Rule1 是名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本，而非中央管理存储本身检索语音规范化规则。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

**Get-CsVoiceNormalizationRule** cmdlet 返回 Microsoft.Rtc.Management.WritableConfig.Policy.Voice.NormalizationRule 对象的实例。

## 另请参阅

#### 其他资源

[New-CsVoiceNormalizationRule](new-csvoicenormalizationrule.md)  
[Remove-CsVoiceNormalizationRule](remove-csvoicenormalizationrule.md)  
[Set-CsVoiceNormalizationRule](set-csvoicenormalizationrule.md)  
[Test-CsVoiceNormalizationRule](test-csvoicenormalizationrule.md)  
[Get-CsDialPlan](get-csdialplan.md)

