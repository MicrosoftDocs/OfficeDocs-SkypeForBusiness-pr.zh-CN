---
title: Get-CsPstnUsage
TOCTitle: Get-CsPstnUsage
ms:assetid: 9dc82b88-303b-4678-8298-0dbc769f6781
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412734(v=OCS.15)
ms:contentKeyID: 49313748
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsPstnUsage

 

_**上一次修改主题：** 2015-03-09_

返回在组织中使用的公用电话交换网 (PSTN) 用法记录的信息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsPstnUsage [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsPstnUsage [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## 示例

## 示例 1

此命令返回组织内可用的全局 PSTN 用法的列表。

    Get-CsPstnUsage

## 示例 2

此示例中的命令返回所有已定义 PSTN 用法的列表，输出的每一行列出一个用法。调用 **Get-CsPstnUsage** cmdlet 本身将返回 Identity 和用法列表。如果用法列表包含三个或四个以上的条目，则会在输出中缩减该列表，如下所示：

Usage :{Internal, Local, Long Distance, International...}

使用此示例中的命令将仅显示用法列表。输出如下所示：

Internal

Local

Long Distance

International

Restricted

    (Get-CsPstnUsage).Usage

## 示例 3

此命令返回名称中包含字符串“tern”的所有 PSTN 用法名称。例如，此命令将返回“Internal”和“International”，但不返回“Local”或“Long Distance”。

此命令的第一部分是括在括号中的 **Get-CsPstnUsage** cmdlet，它表示首先采取的操作用于要检索的所有 PSTN 用法。属性 .Usage 仅返回 PSTN 用法的用法信息，而不是 Identity。然后，将该用法列表通过管道传递到 **ForEach-Object** cmdlet，该 cmdlet 每次处理一个用法字符串。If 语句将当前用法字符串与字符串“\*tern\*”（\* 是通配符）进行比较，并显示任何与该模式匹配的用法字符串。

    (Get-CsPstnUsage).Usage | ForEach-Object {if ($_ -like "*tern*") {$_}}

## 详细说明

PSTN 用法是用于呼叫授权的字符串值。PSTN 用法将语音策略链接至路由。**Get-CsPstnUsage** cmdlet 可检索组织内所有可用 PSTN 用法的列表。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsPstnUsage** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsPstnUsage"}

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
<td><p>Filter 参数允许只检索那些 Identity 与特定通配符字符串匹配的 PSTN 用法。但是，由于 PSTN 用法的唯一 Identity 是 Global，因此此参数对此 cmdlet 没有用处。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>这些设置的应用级别。可应用于 PSTN 用法的唯一标识是 Global。</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从本地数据存储而不是主中央管理存储检索 PSTN 用法信息。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

**Get-CsPstnUsage** cmdlet 返回 Microsoft.Rtc.Management.WritableConfig.Policy.Voice.PSTNUsages 对象的实例。

## 另请参阅

#### 其他资源

[Set-CsPstnUsage](set-cspstnusage.md)  
[Get-CsVoicePolicy](get-csvoicepolicy.md)  
[Get-CsVoiceRoute](get-csvoiceroute.md)

