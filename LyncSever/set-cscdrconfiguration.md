---
title: Set-CsCdrConfiguration
TOCTitle: Set-CsCdrConfiguration
ms:assetid: 977f0d3e-796b-43a3-bc0c-82ea91741c52
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398774(v=OCS.15)
ms:contentKeyID: 49313673
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsCdrConfiguration

 

_**上一次修改主题：** 2015-03-09_

修改现有的呼叫详细信息记录 (CDR) 设置集合。通过 CDR 可以跟踪对等即时消息会话、IP 语音 (VoIP) 呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsCdrConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsCdrConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-EnableCDR <$true | $false>] [-EnablePurging <$true | $false>] [-Force <SwitchParameter>] [-KeepCallDetailForDays <UInt32>] [-KeepErrorReportForDays <UInt32>] [-PurgeHourOfDay <UInt32>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 设置一天中清除旧记录的时间。在此示例中，该时间设置为 23（24 小时制的晚上 11:00）。参数 Identity 用于确保仅对 Identity 为 site:Redmond 的 CDR 设置进行这些更改。

    Set-CsCdrConfiguration -Identity site:Redmond -PurgeHourOfDay 23 

## 示例 2

示例 2 是示例 1 中显示的命令的变体。在此示例中，将修改组织中当前使用的每个 CDR 配置设置集合的 PurgeHourOfDay 属性。为执行此操作，该命令首先调用 **Get-CsCdrConfiguration** cmdlet（不带任何参数），以返回当前使用的所有 CDR 设置的集合。然后，将此集合通过管道传递到 **Set-CsCdrConfiguration** cmdlet，后者会选取集合中的每一项，并将 PurgeHourOfDay 属性的值更改为 11:00 PM (23)。

    Get-CsCdrConfiguration | Set-CsCdrConfiguration -PurgeHourOfDay 23 

## 示例 3

示例 3 中显示的是示例 1 中使用的命令的另一种变体。在此示例中，将更改在站点范围配置的所有 CDR 设置的 PurgeHourOfDay 属性。为执行此任务，该命令首先调用带有 Filter 参数的 **Get-CsCdrConfiguration** cmdlet；筛选器值“site:\*”确保仅返回 Identity 以字符串值“site:”开头的 CDR 设置。然后，将筛选出的集合通过管道传递到 **Set-CsCdrConfiguration** cmdlet，后者将更改该集合中的每一项的 PurgeHourOfDay 属性。

    Get-CsCdrConfiguration -Filter "site:*"| Set-CsCdrConfiguration -PurgeHourOfDay 23

## 详细说明

呼叫详细信息记录 (CDR) 提供了一种方法，用于跟踪 Lync Server 功能（如 IP 语音 (VoIP) 电话呼叫、即时消息 (IM)、文件传输、音频/视频 (A/V) 会议和应用程序共享会话）的使用情况。CDR（仅当部署了监控服务时才可用）会保留使用情况信息：它记录的信息包括呼叫中涉及的各方、呼叫的长度、是否传输了任何文件等。但是，CDR 不会记录呼叫本身。

此外，CDR 还会记录呼叫错误信息：对等会话和会议呼叫的详细诊断数据。

作为管理员，您可以决定是否在组织中使用 CDR；假如已部署监控服务，则可以轻松地启用或禁用 CDR。此外，您还可以在全局（在这种情况下，将在整个组织内启用或禁用 CDR），或者以每个站点为基础做出此决定。例如，可在 Redmond 站点中使用 CDR，而不在 Paris 站点中使用 CDR。

管理员也可以管理 CDR 数据库，例如，可以指定从数据库中清除 CDR 记录前保留这些记录的天数。使用 **Set-CsCdrConfiguration** cmdlet 可以进行此类更改。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsCdrConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsCdrConfiguration"}

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
<td><p><em>EnableCDR</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>指示是否启用 CDR。默认值为 True。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnablePurging</em></p></td>
<td><p>可选</p></td>
<td><p>System.Boolean</p></td>
<td><p>指示是否将定期从 CDR 数据库中删除 CDR 记录。如果为 True（默认值），则将在属性 KeepCallDetailForDays（针对 CDR 记录）和 KeepErrorReportForDays（针对 CDR 错误）指定的时间段之后删除这些记录。如果为 False，则将无限期保留 CDR 记录。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>分配给 CDR 配置设置集合的唯一标识符。要引用全局设置，请使用以下语法：-Identity global。要引用在站点范围配置的集合，请使用类似如下的语法：-Identity site:Redmond。请注意，在指定 Identity 时不能使用通配符。</p>
<p>如果省略此参数，则 <strong>Set-CsCdrConfiguration</strong> cmdlet 将会修改全局设置。</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>CdrSettings 对象</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="odd">
<td><p><em>KeepCallDetailForDays</em></p></td>
<td><p>可选</p></td>
<td><p>System.UInt32</p></td>
<td><p>指示 CDR 记录将在 CDR 数据库中保留的天数；超过指定天数的任何记录将自动删除。（请注意，只有 EnablePurging 属性已设置为 True 时，才会执行清除操作。）</p>
<p>您可以将此属性设置为 1 到 2562 天（大约 7 年）之间的任意整数值。默认值为 60。</p></td>
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
<td><p>指示从 CDR 数据库中删除过期记录时的当地时间。该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。请注意，只能指定一天中的小时时间；这意味着您可以计划在凌晨 4:00 进行清除，但是无法计划在凌晨 4:30 或凌晨 4:15 进行清除。默认值是 2（凌晨 2:00）。建议在非工作时间进行清除。</p>
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

Microsoft.Rtc.Management.WritableConfig.Settings.CallDetailRecording.CdrSettings。**Set-CsCdrConfiguration** cmdlet 接受通过管道传递的呼叫详细信息记录配置对象的输入。

## 返回类型

**Set-CsCdrConfiguration** cmdlet 不会返回值或对象。此 cmdlet 会配置 Microsoft.Rtc.Management.WritableConfig.Settings.CallDetailRecording.CDRSettings 对象的实例。

## 另请参阅

#### 其他资源

[Get-CsCdrConfiguration](get-cscdrconfiguration.md)  
[New-CsCdrConfiguration](new-cscdrconfiguration.md)  
[Remove-CsCdrConfiguration](remove-cscdrconfiguration.md)

