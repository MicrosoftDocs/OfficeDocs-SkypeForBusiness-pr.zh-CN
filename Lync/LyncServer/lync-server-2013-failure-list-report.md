---
title: Lync Server 2013：故障列表报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure List Report
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48185194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 010e8314eb7d2cbb33354461bdc2a1eb2c5b2cf1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a>Lync Server 2013 中的故障列表报告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-07-02_

故障列表报告提供了有关在发生故障的对等会话或会议会话中参与的各个参与者的信息。 此信息包括遇到问题的用户的 URI，以及与故障相关联的 SIP 响应代码和诊断 ID。

<div>

## <a name="accessing-the-failure-list-report"></a>访问故障列表报告

可通过[在 Lync Server 2013 的故障分布报告中](lync-server-2013-failure-distribution-report.md)单击以下任一指标来访问故障列表报告：

  - 主要诊断原因（会话）

  - 主要形式（会话）

  - 主要池（会话）

  - 主要来源（会话）

  - 主要组件（会话）

  - 主要来源用户（会话）

  - 主要目标用户（会话）

  - 主要来源用户代理（会话）

从故障列表报告中，您可以通过单击对等会话的会话详细信息指标，[在 Lync Server 2013 中访问对等会话详细信息报告](lync-server-2013-peer-to-peer-session-detail-report.md)。 您还可以通过单击会议的会议指标来访问会议详细信息报告。

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a>充分利用故障列表报告

在故障列表报告中，您只需将鼠标悬停在此值上即可查看每个响应代码或每个诊断 ID 的说明。 例如，如果将鼠标悬停在诊断 ID 7025 上，则会看到工具提示中显示以下内容：

为用户创建媒体时出现内部服务器错误。

请务必注意，故障列表报告不提供直接检索至少参与一个失败会话的所有用户的列表的简单方法，也不会提供一种方法来确定哪些用户在发生故障时最常参与本次. （一件事，故障列表报告没有筛选功能。）但是，如果导出数据，然后将其转换为逗号分隔值文件，则可以使用 Windows PowerShell 查找类似问题的答案。 例如，假设您将数据保存到。名为 C：\\数据\\故障\_列表 .csv 的 CSV 文件。 根据保存在该文件中的数据，此命令将列出至少一个失败的会话中涉及的所有用户：

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

该命令将返回类似于以下的列表：

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

这两个命令返回每个用户参与的失败会话总数：

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

这将返回与以下内容类似的数据：

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a>筛选器

无。 无法筛选故障列表报告。

</div>

<div>

## <a name="metrics"></a>指标

下表列出了每个失败呼叫的故障列表报告中提供的信息。

### <a name="failure-list-report-metrics"></a>故障列表报告指标

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
<td><p>失败的 SIP 请求类型。 例如 INVITE 或 BYE。</p></td>
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
<td><p><strong>加入成本时间（毫秒）</strong></p></td>
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
<td><p>启动呼叫的用户的终结点使用的软件。</p></td>
</tr>
<tr class="even">
<td><p><strong>目标用户</strong></p></td>
<td><p>否</p></td>
<td><p>被呼叫的用户的 SIP 地址。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

