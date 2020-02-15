---
title: Lync Server 2013：海报：关键运行状况指示器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6b67c4843cc0c1039bee48aa6b7c4620b77ce08
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a>Lync Server 2013 中的关键运行状况指示器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-10_

本文是与[关键运行状况指示器的伴随：维护正常的 Lync server 海报的基础](http://go.microsoft.com/fwlink/?linkid=391838)，可以从下载中心下载。

![描述使用 KHI 数据进行故障排除的海报](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "描述使用 KHI 数据进行故障排除的海报")

您可以使用此海报了解关键运行状况指示器（KHIs）、性能计数器，其阈值旨在暴露用户体验问题。 收集 KHI 数据通常是实施呼叫质量方法（CQM）的第一步，它侧重于确保 Lync 用户的高质量音频体验。

如果您对如何使用 CQM 有疑问，可以将问题提交到 cqmfeedback@microsoft.com。

海报对以下方面进行了说明：

  - 关键运行状况指示器是什么？

  - 收集 KHI 数据

  - 所有服务器角色的修正流

  - 术语表

  - 前端服务器

  - 后端 SQL 服务器

  - 中介服务器

  - 边缘服务器

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a>关键运行状况指示器是什么？

关键运行状况指示器是性能计数器，其阈值旨在暴露用户体验问题。 收集 KHI 数据通常是实施呼叫质量方法（CQM）的第一步，它侧重于确保 Lync 用户的高质量音频体验。

除了标准 Lync 监视解决方案（例如 System Center Operations Manager、合成事务、监视服务器）之外，还使用 KHIs，而不是使用这些解决方案。

收集 KHI 性能计数器，并填充 "网络指南" 附带的 KHI 电子表格，以生成可帮助您确定 Lync 部署的服务器运行状况的记分卡。 填充后，它将指导您修复环境，并向其他利益干系人提供进一步的洞察力。 按月评估 KHIs，并将其合并到任何部署的日常操作过程中。

下载[Lync Server 网络指南](http://go.microsoft.com/fwlink/p/?linkid=390677)以查看完整的 KHIs 列表，并获取相关的电子表格。

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a>收集 KHI 数据

1.  在每个 Lync Server 上运行 Lync Server 网络指南附带的 KHI 脚本。 这将在性能监视器中创建一个数据收集器，并将其命名为 KHI。 默认情况下，将每15秒轮询一次数据。

2.  在公司的工作日开始之前，请转到每个 Lync Server 并启动 KHI 数据收集器。

3.  在那天结束时，停止 KHI 数据收集器并将数据复制到一个中心位置。

4.  使用性能监视器填充 Lync Server 网络指南中附带的 KHI 电子表格后，将结果与建议的目标进行比较。

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a>所有服务器角色的修正流

对于 Lync 实施中的每台服务器，首先验证服务器的组件运行状况和系统性能是否在所需级别或更高级别。 只有在此之后，才应查看整个 Lync 实现中与服务器角色相关的指示器。

首先，收集所有服务器的 KHI 性能数据。 对于每个系统角色（本文档后面讨论的详细信息），确定基本系统组件是否符合建议的目标。 如果没有，则先修正系统性能，然后重新收集 KHI 数据，并确保系统运行状况，然后再在 Lync 实现中查看特定于服务器角色的指标。 所有角色的组件运行状况均定义为：

  - CPU 使用率\< 80%

  - 平均磁盘写入\< 10 毫秒

  - 平均磁盘读取\< 10 毫秒

  - 可用内存\>20% 系统总 MB

  - 网络队列长度\< 2

  - 丢弃的数据包（in/out） = 0

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a>术语表

此海报中使用以下术语和首字母缩写词：

AS MCU = 应用程序共享多点控制单元

AV MCU = 音频/视频 MCU

IM MCU = 即时消息 MCU

UCWA = 统一通信 Web API

AV 边缘 = 通过边缘遍历音频/视频

AV Auth = 音频/视频身份验证

SIP 堆栈 = 包含 Lync 的核心 SIP 实现

数据代理 = 用于边缘会议

LySS = Lync Storage Service

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a>前端服务器

除了基本组件运行状况之外，以下建议的 KHI 目标还特定于前端服务器：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>功能区域</th>
<th>目标指标</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AS/AV/IM MCU</p></td>
<td><p>MCU 运行状况&lt;状态2</p></td>
</tr>
<tr class="even">
<td><p>Web 组件</p></td>
<td><p>通讯组列表展开 AD &lt;超时0</p>
<p>ABWQ 失败 = 0</p>
<p>IIS 故障 = 0</p>
<p>身份验证&lt;错误 1/秒</p>
<p>已拒绝的 ASP.NET v4 请求 = 0</p></td>
</tr>
<tr class="odd">
<td><p>SIP 堆栈</p></td>
<td><p>平均传入邮件处理&lt; 1 秒</p>
<p>传入响应丢弃&lt; 1/秒传入的请求&lt;丢弃 1/秒</p>
<p>队列延迟&lt; 100 毫秒</p>
<p>过程延迟&lt; 100 毫秒</p>
<p>限制的请求数 = 0</p>
<p>身份验证&lt;错误 1/秒</p>
<p>传入邮件超时&lt; 2</p>
<p>平均传入邮件保留&lt; 1 秒</p>
<p>流控制的&lt;连接2</p>
<p>平均超时队列延迟&lt; 2 秒</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>存储服务 DB &lt; 80 使用的空间百分比</p>
<p>#副本复制失败的次数 = 0</p>
<p>#数据丢失事件数 = 0</p></td>
</tr>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>页生命预期&gt; 300 秒。</p>
<p>批处理请求数/ &lt;秒2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a>后端 SQL 服务器

除了基本组件运行状况之外，以下建议的 KHI 目标也是特定于 SQL server 的：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>功能区域</th>
<th>目标指标</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>页生命预期&gt; 300 秒。</p>
<p>批处理请求数/ &lt;秒2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a>中介服务器

除了基本组件运行状况之外，以下建议的 KHI 目标特定于中介服务器：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>功能区域</th>
<th>目标指标</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>中介服务器服务</p></td>
<td><p>加载呼叫失败索引 = 0</p>
<p>因代理&lt;10 导致的失败呼叫</p>
<p>由于网关&lt;10 导致的失败呼叫</p>
<p>已拒绝的呼叫（in 或传出） = 0</p>
<p>缺少媒体候选人 = 0</p>
<p>媒体连接检查故障 = 0</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a>边缘服务器

除了基本组件运行状况之外，以下建议的 KHI 目标还特定于边缘服务器：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>功能区域</th>
<th>目标指标</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AV 身份验证</p></td>
<td><p>错误请求&lt; 20/秒</p></td>
</tr>
<tr class="even">
<td><p>AV 边缘</p></td>
<td><p>Auth 失败&lt;20/秒</p>
<p>分配失败&lt;20/秒</p>
<p>丢弃&lt;300/秒的数据包</p></td>
</tr>
<tr class="odd">
<td><p>数据代理</p></td>
<td><p>限制的服务器&lt;连接3</p>
<p>系统为限制&lt;1</p></td>
</tr>
<tr class="even">
<td><p>SIP 堆栈</p></td>
<td><p>超过极限的连接&lt;丢弃1</p>
<p>发送超时&lt;10</p>
<p>流控制的&lt;连接100</p>
<p>传入请求丢弃&lt; 1/秒</p>
<p>平均邮件处理&lt; 3 秒</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 网络指南](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[关键运行状况指示器：用于维护正常运行的 Lync 服务器的基础](http://go.microsoft.com/fwlink/?linkid=391838)  
[Lync 呼叫质量方法](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

