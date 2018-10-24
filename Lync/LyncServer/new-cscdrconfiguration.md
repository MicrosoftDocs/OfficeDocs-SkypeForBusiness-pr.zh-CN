---
title: New-CsCdrConfiguration
TOCTitle: New-CsCdrConfiguration
ms:assetid: e5890ac3-7a6c-4609-a866-84c39b76d3a9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399018(v=OCS.15)
ms:contentKeyID: 49314551
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsCdrConfiguration

 

_**上一次修改主题：** 2015-03-09_

创建一组新的呼叫详细信息记录 (CDR) 设置。通过 CDR 可以跟踪对等即时消息会话、IP 语音 (VoIP) 呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsCdrConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-EnableCDR <$true | $false>] [-EnablePurging <$true | $false>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-KeepCallDetailForDays <UInt32>] [-KeepErrorReportForDays <UInt32>] [-PurgeHourOfDay <UInt32>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 中的命令使用 **New-CsCdrConfiguration** cmdlet 来创建 Identity 为 site:Redmond 的一组新 CDR 设置。除了 Identity 为 site:Redmond 之外，新设置还将 EnableCDR 属性设置为 False。由于站点设置优先于全局设置，因此这意味着，无论是否已在全局范围启用 CDR，Redmond 站点中都不会使用 CDR。

    New-CsCdrConfiguration -Identity site:Redmond -EnableCDR $False

## 示例 2

示例 2 使用 InMemory 参数演示如何创建一个最初仅存在于内存中的新 CDR 配置设置集合。为执行此操作，该示例首先使用 **New-CsCdrConfiguration** cmdlet 和 InMemory 参数创建一个 Identity 为 site:Redmond 的虚拟设置集合。此虚拟集合存储在变量 $x 中；如果此集合未存储在变量中，则会在创建之后立即消失。

创建虚拟集合之后，第 2 行中显示的命令会将 EnableCDR 属性的值设置为 False ($False)。在第 3 行中，**Set-CsCdrConfiguration** cmdlet 用于将虚拟集合 $x 转换为应用于 Redmond 站点的实际 CDR 配置设置集合。如果未调用 **Set-CsCdrConfiguration** cmdlet，则一旦终止 Windows PowerShell 会话或删除变量 $x，此虚拟集合将立即消失。

    $x = New-CsCdrConfiguration -Identity site:Redmond -InMemory
    $x.EnableCDR = $False
    Set-CsCdrConfiguration -Instance $x

## 详细说明

呼叫详细信息记录 (CDR) 提供了一种方法，用于跟踪 Lync Server 功能（如 IP 语音 (VoIP) 电话呼叫、即时消息 (IM)、文件传输、音频/视频 (A/V) 会议和应用程序共享会话）的使用情况。CDR（仅当部署了监控服务时才可用）会跟踪使用情况信息：它记录的信息包括呼叫中涉及的各方、呼叫的长度、是否传输了任何文件等。（但是，CDR 不会记录呼叫本身。）

此外，CDR 还会记录呼叫错误信息：对等会话和会议呼叫的详细诊断数据。

作为管理员，您可以决定是否在组织中使用 CDR；如果已部署监控服务，则可以轻松地启用或禁用 CDR。此外，您可以在全局（在这种情况下 CDR 将在整个组织内启用或禁用），或者以每个站点为基础做出此决定。例如，您可以在 Redmond 站点中使用 CDR，但不在 Paris 站点中使用 CDR。

**New-CsCdrConfiguration** cmdlet 用于在站点范围创建新的 CDR 设置集合。（无法在全局范围创建新设置。）请注意，每个站点只能托管一个 CDR 设置集合。这意味着，如果站点已有一组 CDR 配置设置，则无法为 Redmond 站点创建新的集合。如果尝试这样做，命令将失败。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **New-CsCdrConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsCdrConfiguration"}

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
<td><p><em>Identity</em></p></td>
<td><p>必需</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>表示要分配给新的 CDR 配置设置集合的唯一标识符。由于您只能在站点范围中创建新集合，因此 Identity 将始终为前缀“site:”后跟站点名称；例如，“site:Redmond”。</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableCDR</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>指示是否启用 CDR。默认值为 True。</p></td>
</tr>
<tr class="even">
<td><p><em>EnablePurging</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>指示是否将定期从 CDR 数据库中删除 CDR 记录。如果为 True（默认值），则将在属性 KeepCallDetailForDays（CDR 记录）和 KeepErrorReportForDays（CDR 错误）指定的时间段之后删除这些记录。如果为 False，则将无限期保留 CDR 记录。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。</p></td>
</tr>
<tr class="even">
<td><p><em>InMemory</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="odd">
<td><p><em>KeepCallDetailForDays</em></p></td>
<td><p>可选</p></td>
<td><p>System.UInt32</p></td>
<td><p>指示 CDR 记录将在 CDR 数据库中保留的天数；超过指定天数的任何记录将自动删除。（请注意，只有 EnablePurging 属性已设置为 True 时，才会执行清除操作。）</p>
<p>KeepCallDetailForDays 可以设置为 1 到 2562 天（大约 7 年）之间的任意整数值。默认值为 60。</p></td>
</tr>
<tr class="even">
<td><p><em>KeepErrorReportForDays</em></p></td>
<td><p>可选</p></td>
<td><p>System.UInt32</p></td>
<td><p>指示保留 CDR 错误报告的天数；超过指定天数的任何报告将自动删除。CDR 错误报告是由客户端应用程序（如 Lync 2013）上载的诊断报告。</p>
<p>您可以将此属性设置为 1 到 2562 天（大约 7 年）之间的任意整数值。默认值为 60。</p></td>
</tr>
<tr class="odd">
<td><p><em>PurgeHourOfDay</em></p></td>
<td><p>可选</p></td>
<td><p>System.UInt32</p></td>
<td><p>指示从 CDR 数据库中删除过期记录时的当地时间。该时间使用 24 小时制格式指定，0 代表午夜（午夜 12:00），23 代表晚上 11:00。请注意，只能指定整点时间；这意味着，您可以计划在凌晨 4:00 进行清除，但是不能计划在凌晨 4:30 或凌晨 4:15 进行清除。默认值是 2（凌晨 2:00）。建议在非工作时间进行清除。</p>
<p>只有 EnablePurging 属性设置为 True 时，才可进行数据库清除。</p></td>
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

无。**New-CsCdrConfiguration** cmdlet 不接受通过管道传递的输入。

## 返回类型

创建 Microsoft.Rtc.Management.WritableConfig.Settings.CallDetailRecording.CdrSettings 对象的实例。

## 另请参阅

#### 其他资源

[Get-CsCdrConfiguration](get-cscdrconfiguration.md)  
[Remove-CsCdrConfiguration](remove-cscdrconfiguration.md)  
[Set-CsCdrConfiguration](set-cscdrconfiguration.md)

