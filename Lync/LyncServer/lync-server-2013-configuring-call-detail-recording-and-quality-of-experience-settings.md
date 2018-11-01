---
title: 配置呼叫详细信息记录和启用体验质量设置
TOCTitle: 配置呼叫详细信息记录和用户体验质量设置
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204621(v=OCS.15)
ms:contentKeyID: 49311800
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置呼叫详细信息记录和启用体验质量设置

 

_**上一次修改主题：** 2015-03-09_

将监控存储与前端池关联，设置监控存储，然后安装和配置 SQL Server Reporting Services 和监控报告后，即可使用 Lync Server 命令行管理程序管理呼叫详细记录 (CDR) 和用户体验质量 (QoE) 监控。Lync Server 命令行管理程序 cmdlet 允许您对某个特定站点或整个 Lync Server 部署启用或禁用 CDR 和/或 QoE 监控；可以用下面这样简单的命令来完成：

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

在安装 Microsoft Lync Server 2013 时，将会同时安装 CDR 和 QoE 的全局配置设置的预定义集合。下表显示了呼叫详细记录使用的一些较常用设置的默认值：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>属性</th>
<th>说明</th>
<th>默认值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableCDR</p></td>
<td><p>指示是否启用 CDR。如果为 True，将收集所有 CDR 记录并写入监控数据库。</p></td>
<td><p>True</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>指示是否定期从数据库中删除 CDR 记录。如果为 True，则将在属性 KeepCallDetailForDays（对于 CDR 记录）和 KeepErrorReportForDays（对于 CDR 错误）指定的时间段后删除记录。如果为 False，则将无限期保留 CDR 记录。</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>KeepCallDetailForDays</p></td>
<td><p>指示 CDR 记录在数据库中保留的天数；超过指定天数的任何记录将自动删除。但是，只有在启用了清除时才会发生这种情况。</p>
<p>KeepCallDetailForDays 可以设置为 1 到 2562 天（大约 7 年）之间的任意整数值。</p></td>
<td><p>60 天</p></td>
</tr>
<tr class="even">
<td><p>KeepErrorReportForDays</p></td>
<td><p>指示保留 CDR 错误报告的天数；超过指定天数的任何报告将自动删除。CDR 错误报告是由客户端应用程序（如 Microsoft Lync 2013）上载的诊断报告。</p>
<p>您可以将此属性设置为 1 到 2562 天之间的任意整数值。</p></td>
<td><p>60 天</p></td>
</tr>
</tbody>
</table>


类似地，此表中也显示了选定 QoE 设置的默认值：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>属性</th>
<th>说明</th>
<th>默认值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableQoE</p></td>
<td><p>指示是否启用 QoE 监控。如果为 True，将收集所有 QoE 记录并写入监控数据库。</p></td>
<td><p>True</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>指示是否定期从数据库中删除 QoE 记录。如果为 True，则将在属性 KeepQoEDataForDays 指定的时间段后删除记录。如果为 False，则将无限期保留 QoE 记录。</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>KeepQoEDataForDays</p></td>
<td><p>指示 QoE 记录在数据库中保留的天数；超过指定天数的任何记录将自动删除。但是，只有在启用了清除时才会发生这种情况。</p>
<p>可将 KeepCallDetailForDays 设置为 1 到 2562 天之间的任意整数值。</p></td>
<td><p>60 天</p></td>
</tr>
</tbody>
</table>


如果您需要修改这些全局设置，可以使用 Set-CsCdrConfiguration 和 Set-CsQoEConfiguration cmdlet 来完成。例如，以下命令（从 Lync Server 命令行管理程序运行）在全局范围内禁用 CDR 监控；这是通过将 EnableCDR 属性设置为 False ($False) 来实现的：

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

请注意，禁用监控不会从前端池解除监控存储关联，也不卸载或以其他方式影响后端监控数据库。当您使用 Lync Server 命令行管理程序禁用 CDR 或 QoE 监控时，实际上是暂时停止 Lync Server 收集和存档监控数据。如果要恢复收集和存档 CDR 数据，只需要将 EnableCDR 属性重新设置为 True ($True) 即可：

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

类似地，以下命令在全局范围内禁止清除 QoE 记录：

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

除了全局设置，也可将 CDR 和 QoE 配置设置分配给站点范围。这样，在实施监控时可提供更大的管理灵活性；例如，管理员可以对 Redmond 站点启用 CDR 监控，而对 Dublin 站点禁用 CDR 监控。要在站点范围创建新的 CDR 配置设置，请使用类似如下的命令：

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

请记住，在站点范围配置的设置优先于在全局范围配置的设置。例如，假设在全局范围启用了 CDR 监控，但在站点范围（对于 Redmond 站点）禁用了 CDR 监控。这意味着将不为 Redmond 站点中的用户存档呼叫详细记录信息。但是，其他站点中的用户（即，由全局设置而非 Redmond 站点设置管理的用户）的呼叫详细记录仍将存档。

可以使用类似如下的命令在站点范围创建新的 QoE 配置设置：

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

有关更多信息，请在 Lync Server 命令行管理程序 内键入以下命令：

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

