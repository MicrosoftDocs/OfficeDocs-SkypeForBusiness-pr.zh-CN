---
title: Set-CsPstnUsage
TOCTitle: Set-CsPstnUsage
ms:assetid: ecba9ed6-4845-4035-933e-0c540d530b72
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399069(v=OCS.15)
ms:contentKeyID: 49314649
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsPstnUsage

 

_**上一次修改主题：** 2015-03-09_

修改用于标识允许的公用电话交换网 (PSTN) 用法的字符串集。此 cmdlet 可用于将用法添加到 PSTN 用法列表或从列表中删除用法。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsPstnUsage [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsPstnUsage [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Usage <PSListModifier>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此命令将字符串“International”添加至当前的可用 PSTN 用法列表中。

    Set-CsPstnUsage -Identity global -Usage @{add="International"}

## 示例 2

此命令将字符串“Local”从可用 PSTN 用法列表中删除。

    Set-CsPstnUsage -Identity global -Usage @{remove="Local"}

## 示例 3

此示例中的命令执行与示例 2 中的命令完全相同的操作：删除“Local”PSTN 用法。此示例显示未指定 Identity 参数的命令。**Set-CsPstnUsage** cmdlet 可以使用的唯一 Identity 是 Global 标识符，因此省略 Identity 参数将默认使用 Global。

    Set-CsPstnUsage -Usage @{remove="Local"}

## 示例 4

此命令将用法列表中的所有内容替换为值“International”和“Restricted”。先前存在的所有用法都被删除。

    Set-CsPstnUsage -Usage @{replace="International","Restricted"}

## 详细说明

PSTN 用法是用于呼叫授权的字符串值。PSTN 用法将语音策略链接至路由。**Set-CsPstnUsage** cmdlet 用于在用法列表中添加或删除电话用法。此列表是一个全局列表，因此在整个 Lync Server 部署过程中，策略和路由都可以使用此列表。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsPstnUsage** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsPstnUsage"}

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
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>这些设置的应用范围。此 cmdlet 的 Identity 始终为 Global。</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>PstnUsages</p></td>
<td><p>对 PSTN 用法对象的引用。此对象必须为 PstnUsages 类型，并且可以通过调用 <strong>Get-CsPstnUsage</strong> cmdlet 来检索。</p></td>
</tr>
<tr class="odd">
<td><p><em>Usage</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>包含允许的用法字符串的列表。这些条目可以是任意字符串值。</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Policy.Voice.PstnUsages 对象。接受通过管道传递的 PSTN 用法对象的输入。

## 返回类型

此 cmdlet 不会返回值或对象。它会配置 Microsoft.Rtc.Management.WritableConfig.Policy.Voice.PstnUsages 对象的实例。

## 另请参阅

#### 其他资源

[Get-CsPstnUsage](get-cspstnusage.md)

