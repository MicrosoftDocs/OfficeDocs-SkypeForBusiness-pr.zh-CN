---
title: Get-CsCdrConfiguration
TOCTitle: Get-CsCdrConfiguration
ms:assetid: 4af8ffa2-63d3-4873-8dac-5afede090d4f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398298(v=OCS.15)
ms:contentKeyID: 49312772
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsCdrConfiguration

 

_**上一次修改主题：** 2015-03-09_

返回与呼叫详细信息记录 (CDR) 设置有关的信息。通过 CDR 可以跟踪对等即时消息会话、IP 语音 (VoIP) 呼叫和会议呼叫等的使用情况。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsCdrConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsCdrConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## 示例

## 示例 1

此示例使用 **Get-CsCdrConfiguration** cmdlet 返回配置为在组织中使用的所有 CDR 设置的集合。

    Get-CsCdrConfiguration

## 示例 2

示例 2 使用 Identity 参数以返回 CDR 设置的单个集合：Identity 为 site:Redmond 的设置。

    Get-CsCdrConfiguration -Identity site:Redmond

## 示例 3

在示例 3 中，Filter 参数用于返回在站点范围配置的所有 CDR 配置。筛选器值“site:\*”返回 Identity 以字符串值“site:”开头的所有 CDR 设置。根据定义，这些都是已在站点范围配置的设置。

    Get-CsCdrConfiguration -Filter site:*

## 示例 4

示例 4 返回 KeepCallDetailForDays 属性少于 30 天的所有 CDR 设置的集合。为此，该命令首先使用 **Get-CsCdrConfiguration** cmdlet 返回组织中配置的所有 CDR 设置的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，后者会仅选取 KeepCallDetailForDays 值小于 30 天的设置。

    Get-CsCdrConfiguration | Where-Object {$_.KeepCallDetailForDays -lt 30}

## 详细说明

呼叫详细信息记录 (CDR) 提供了一种方法，用于跟踪 Lync Server 功能（如 IP 语音 (VoIP) 电话呼叫、即时消息 (IM)、文件传输、音频/视频 (A/V) 会议和应用程序共享会话）的使用情况。CDR（仅当已部署监控服务时才可用）可保留使用情况信息：它记录的信息包括呼叫中涉及的各方、呼叫的长度、是否传输了任何文件等。（然而，CDR 不会记录呼叫本身。）

CDR 还会跟踪呼叫错误信息：对等会话和会议呼叫的详细诊断数据。

作为管理员，您可以确定是否在组织中使用 CDR。如果已部署了监控服务，则可以启用或禁用 CDR。此外，您可以在全局（在这种情况下 CDR 将在整个组织内启用或禁用），或者以每个站点为基础做出此决定。例如，您可以在 Redmond 站点中使用 CDR，但不在 Paris 站点中使用 CDR。

通过 **Get-CsCdrConfiguration** cmdlet，您可以返回有关如何在组织中使用 CDR 的详细信息。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsCdrConfiguration** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsCdrConfiguration"}

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
<td><p>使您能够使用通配符，以便返回 CDR 配置设置的集合。例如，要返回在站点范围配置的所有设置的集合，请使用以下语法：-Filter site:*。要返回在 Identity 中包含字符串值“Western”的所有设置的集合，请使用语法：-Filter *Western*。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>指示要返回的 CDR 配置设置集合的唯一标识符。要引用全局设置，请使用此语法：-Identity global。要引用在站点范围配置的集合，请使用类似语法：-Identity site:Redmond。请注意，指定 Identity 时不能使用通配符。如果需要使用通配符，请改用 Filter 参数。</p>
<p>如果不指定该参数，则 <strong>Get-CsCdrConfiguration</strong> cmdlet 将返回当前在组织中使用的所有 CDR 配置设置的集合。</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本，而不是从中央管理存储本身检索 CDR 配置数据。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Get-CsCdrConfiguration** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Get-CsCdrConfiguration** cmdlet 返回 Microsoft.Rtc.Management.WritableConfig.Settings.CallDetailRecording.CdrSettings 对象的实例。

## 另请参阅

#### 其他资源

[New-CsCdrConfiguration](new-cscdrconfiguration.md)  
[Remove-CsCdrConfiguration](remove-cscdrconfiguration.md)  
[Set-CsCdrConfiguration](set-cscdrconfiguration.md)

