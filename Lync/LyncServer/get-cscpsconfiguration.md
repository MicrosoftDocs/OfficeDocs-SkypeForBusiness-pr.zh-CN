---
title: Get-CsCpsConfiguration
TOCTitle: Get-CsCpsConfiguration
ms:assetid: d81ee8fe-d02b-4f60-a4d5-6aa84f65d156
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398948(v=OCS.15)
ms:contentKeyID: 49314408
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsCpsConfiguration

 

_**上一次修改主题：** 2015-03-09_

返回有关呼叫寄存服务的信息。呼叫寄存是一项允许用户寄存来电的服务。寄存某个呼叫会将该呼叫转接到指定范围或轨道中的一个号码，然后立即将它置于保持状态。任何人（不只是最初接听电话的人员）都可以通过输入正确的号码，来从系统中的任何电话恢复对话。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsCpsConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsCpsConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## 示例

## 示例 1

示例 1 检索所有定义为在组织中使用的呼叫寄存服务配置的集合。

    Get-CsCpsConfiguration

## 示例 2

示例 2 仅检索 Identity 为 site:Redmond1 的呼叫寄存服务配置。

    Get-CsCpsConfiguration -Identity site:Redmond1

## 示例 3

在示例 3 中，使用 Filter 参数返回在站点范围配置的所有呼叫寄存服务配置。通配符字符串 site:\* 通知 **Get-CsCpsConfiguration** cmdlet 仅返回标识以字符串值 site: 开头的设置。

    Get-CsCpsConfiguration -Filter site:*

## 示例 4

与示例 3 一样，在此示例中，我们也使用 Filter 参数来检索所有定义的呼叫寄存服务配置的子集。在此示例中，按字符串 \*:re\* 来筛选，这会返回名称以字母“re”开头的所有站点（如 Redmond1、Redmond2 和 RemoteComputer）的呼叫寄存配置。

    Get-CsCpsConfiguration -Filter *:re*

## 示例 5

示例 5 返回在呼叫者置于呼叫等待状态时不播放音乐的所有呼叫寄存服务设置。为执行此操作，该命令首先使用 **Get-CsCpsConfiguration** cmdlet 检索配置为在组织中使用的所有呼叫寄存服务设置。然后，将此集合通过管道传递到 **Where-Object** cmdlet，而后该 cmdlet 会应用筛选器将返回的数据限制为 EnableMusicOnHold 属性等于 (-eq) False 的项。

    Get-CsCpsConfiguration | Where-Object {$_.EnableMusicOnHold -eq $False}

## 详细说明

此 cmdlet 用于检索一个或多个呼叫寄存服务配置。呼叫寄存服务配置指定呼叫寄存后的事项。例如，如果寄存呼叫在一段时间后仍然无人接听，则会将该呼叫自动转接到其他人，如管理员或响应组。还可以将呼叫配置为在一段时间后响铃，以确保不会将其遗忘。此外，可以将呼叫寄存服务配置为在呼叫寄存时为呼叫者播放呼叫等待音乐。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsCpsConfiguration** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsCpsConfiguration"}

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
<td><p>允许执行通配符搜索以便仅检索标识值与通配符字符串匹配的配置。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>要检索的呼叫寄存服务配置的唯一标识符。此标识符将为 Global 或 site:&lt;站点名称&gt;，其中 &lt;站点名称&gt; 是应用该配置的站点的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本，而不是从中央管理存储本身检索呼叫寄存服务信息。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

检索一个或多个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.CallParkServiceSettings.CallParkServiceSettings 的对象。

## 另请参阅

#### 其他资源

[New-CsCpsConfiguration](new-cscpsconfiguration.md)  
[Remove-CsCpsConfiguration](remove-cscpsconfiguration.md)  
[Set-CsCpsConfiguration](set-cscpsconfiguration.md)  
[Set-CsCallParkServiceMusicOnHoldFile](set-cscallparkservicemusiconholdfile.md)

