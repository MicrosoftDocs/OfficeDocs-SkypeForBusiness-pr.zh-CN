---
title: Lync Server 2013：故障列表报告
TOCTitle: 故障列表报告
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615446(v=OCS.15)
ms:contentKeyID: 49314023
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的故障列表报告

 

_**上一次修改主题：** 2015-03-09_

故障列表报告提供有关参加失败的对等会话或会议会话的各个参与者的信息。此信息包括遇到问题的用户的 URI，以及与故障相关联的 SIP 响应代码和诊断 ID。

## 访问故障列表报告

可以通过单击 [Lync Server 2013 中的故障分布报告](lync-server-2013-failure-distribution-report.md)上的以下任一指标来访问故障列表报告：

  - 主要诊断原因（会话）

  - 主要形式（会话）

  - 主要池（会话）

  - 主要来源（会话）

  - 主要组件（会话）

  - 主要来源用户（会话）

  - 主要目标用户（会话）

  - 主要来源用户代理（会话）

从故障列表报告中，您可以单击对等会话的”会话详细信息“指标，以访问 [Lync Server 2013 中的点对点会话详细信息报告](lync-server-2013-peer-to-peer-session-detail-report.md)。也可以单击会议的”会议“指标，以访问会议详细信息报告。

## 充分利用故障列表报告

在故障列表报告中，您只需将鼠标置于每个响应代码或每个诊断 ID 上，即可查看它们的说明。例如，如果您将鼠标置于诊断 ID 7025 上，则将会看到在工具提示中显示以下内容：

为用户创建媒体时发生内部服务器错误。

务必注意，故障列表报告并未提供一种简单直观的方式来直接检索至少参加一次失败会话的所有用户列表，也未提供一种用来确定失败会话中最常涉及哪些用户的方法。（首先，故障列表报告没有筛选功能。）但是，如果导出数据，然后将其转换为逗号分隔值文件，则可以使用 Windows PowerShell 来查找类似上述问题的解答。例如，假设将数据保存到名为 C:\\Data\\Failure\_List.csv 的 .CSV 文件。根据该文件中所保存的数据，以下命令会列出至少一次失败会话中所涉及的所有用户：

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

该命令将返回与以下类似的列表：

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

以下两个命令将返回涉及每个用户的失败会话总数：

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

这将返回与以下类似的数据：

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

## 筛选器

无。您无法筛选故障列表报告。

## 指标

下表列出了各失败呼叫的故障列表报告中提供的信息。

### 故障列表报告指标

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>是否可按此项排序？</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>报告时间</strong></p></td>
<td><p>否</p></td>
<td><p>记录报告的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>请求</strong></p></td>
<td><p>否</p></td>
<td><p>失败的 SIP 请求类型。例如 INVITE 或 BYE。</p></td>
</tr>
<tr class="odd">
<td><p><strong>响应代码</strong></p></td>
<td><p>否</p></td>
<td><p>会议失败时发送的 SIP 响应代码。</p></td>
</tr>
<tr class="even">
<td><p><strong>诊断 ID</strong></p></td>
<td><p>否</p></td>
<td><p>附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。</p></td>
</tr>
<tr class="odd">
<td><p><strong>加入成本时间(毫秒)</strong></p></td>
<td><p>否</p></td>
<td><p>用户加入会议所需的时间量（以毫秒为单位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>来源用户</strong></p></td>
<td><p>否</p></td>
<td><p>发起呼叫的用户的 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>源用户代理</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫发起用户的终结点使用的软件。</p></td>
</tr>
<tr class="even">
<td><p><strong>目标用户</strong></p></td>
<td><p>否</p></td>
<td><p>被呼叫用户的 SIP 地址。</p></td>
</tr>
</tbody>
</table>

