---
title: 'Lync Server 2013: 海报: 关键运行状况指示器'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9454197642ac87f5d8bc0d768795854d792f9a31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a>Lync Server 2013 中的关键运行状况指示器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-02-10_

本文介绍了[关键运行状况指示器: 维护正常的 Lync 服务器海报的基础](http://go.microsoft.com/fwlink/?linkid=391838), 您可以从下载中心下载。

![描述使用 KHI 数据进行疑难解答的海报](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "描述使用 KHI 数据进行疑难解答的海报")

你可以使用此海报了解有关关键运行状况指示器 (KHIs) 的性能计数器, 其阈值旨在展示用户体验问题。 收集 KHI 数据通常是实现呼叫质量方法 (CQM) 的第一步, 它侧重于确保 Lync 用户的音质音频体验。

如果对如何使用 CQM 有疑问, 可以将问题提交到 cqmfeedback@microsoft.com。

海报介绍以下方面:

  - 什么是关键运行状况指示器？

  - 收集 KHI 数据

  - 所有服务器角色的更新流

  - 词条

  - 前端服务器

  - 后端 SQL 服务器

  - 中介服务器

  - 边缘服务器

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a>什么是关键运行状况指示器？

关键运行状况指示器是性能计数器, 其阈值旨在展示用户体验问题。 收集 KHI 数据通常是实现呼叫质量方法 (CQM) 的第一步, 它侧重于确保 Lync 用户的音质音频体验。

除了标准 Lync 监视解决方案 (如 System Center Operations Manager、合成事务、监视服务器) 之外, 还可使用 KHIs, 而不是使用这些解决方案。

收集 KHI 性能计数器并填充网络指南随附的 KHI 电子表格, 以生成可帮助你确定 Lync 部署的服务器运行状况的记分卡。 填充后, 它将引导你修复环境并向其他利益干系人提供进一步的洞察力。 按月评估 KHIs, 并将它们合并到任何部署的日常操作流程中。

下载[Lync Server 网络指南](http://go.microsoft.com/fwlink/p/?linkid=390677)以查看完整的 KHIs 列表和获取相关的电子表格。

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a>收集 KHI 数据

1.  在每个 Lync 服务器上运行 Lync Server 网络指南附带的 KHI 脚本。 这将在性能监视器内创建一个数据收集器, 并将其命名为 KHI。 默认情况下, 将每隔15秒对数据进行轮询。

2.  在公司的工作日内开始之前, 请转到每个 Lync 服务器并启动 KHI 数据收集器。

3.  在该日期结束时, 停止 KHI 数据收集器并将数据复制到一个中心位置。

4.  使用性能监视器填充 Lync Server 网络指南附带的 KHI 电子表格后, 将结果与推荐的目标进行比较。

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a>所有服务器角色的更新流

对于 Lync 实现中的每个服务器, 首先验证服务器的组件运行状况和系统性能是否在所需级别或更高级别。 只有在该情况之后, 才应查看整个 Lync 实现中与服务器角色相关的指示器。

首先收集所有服务器的 KHI 性能数据。 对于每个系统角色 (本文档后面部分讨论的详细信息) 确定基本系统组件是否满足推荐的目标。 如果不是这样, 请先补救系统性能, 然后重新收集 KHI 数据并确保系统运行状况, 然后再查看特定于 Lync 实现中的服务器角色的指标。 所有角色的组件运行状况定义如下:

  - CPU 利用率\< 80%

  - 平均磁盘写入\< 10 毫秒

  - 平均磁盘读取\< 10 毫秒

  - 可用内存\>20% 系统总 MB

  - 网络队列长度\< 2

  - 已丢弃的数据包 (in/out) = 0

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a>词条

本海报中使用下列术语和首字母缩写:

作为 MCU = 应用程序共享多点控制单元

AV MCU = 音频/视频 MCU

IM MCU = 即时消息 MCU

UCWA = 统一通信 Web API

AV 边缘 = 通过边缘遍历音频/视频

AV 身份验证 = 音频/视频身份验证

SIP 堆栈 = 包含 Lync 的核心 SIP 实现

数据代理 = 用于边缘会议

LySS = Lync 存储服务

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a>前端服务器

除了基本组件运行状况之外, 以下建议的 KHI 目标还特定于前端服务器:


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
<td><p>MCU 运行状态&lt;2</p></td>
</tr>
<tr class="even">
<td><p>Web 组件</p></td>
<td><p>通讯组列表展开广告&lt;超时0</p>
<p>ABWQ 失败 = 0</p>
<p>.LIS 故障 = 0</p>
<p>身份验证&lt;错误 1/sec</p>
<p>ASP.NET v4 请求被拒绝 = 0</p></td>
</tr>
<tr class="odd">
<td><p>SIP 堆栈</p></td>
<td><p>平均传入消息处理&lt; 1 秒</p>
<p>传入响应丢弃&lt; 1/秒传入的请求&lt;已丢弃 1/秒</p>
<p>队列延迟&lt; 100 ms</p>
<p>过程延迟&lt; 100 ms</p>
<p>限制的请求数 = 0</p>
<p>身份验证&lt;错误 1/sec</p>
<p>传入消息超时&lt; 2</p>
<p>平均传入消息保留&lt; 1 秒</p>
<p>流控制的&lt;连接2</p>
<p>平均超时排队延迟&lt; 2 秒</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>存储服务数据库&lt; 80 占用的空间百分比</p>
<p>#复制副本复制失败次数 = 0</p>
<p>#数据丢失事件数 = 0</p></td>
</tr>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>页生命预期&gt; 300 秒。</p>
<p>批处理请求/秒&lt; 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a>后端 SQL 服务器

除了基本组件运行状况之外, 以下建议的 KHI 目标还特定于 SQL server:


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
<p>批处理请求/秒&lt; 2500</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a>中介服务器

除了基本组件运行状况之外, 以下建议的 KHI 目标还特定于中介服务器:


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
<p>由于代理&lt;10 导致的呼叫失败</p>
<p>由于网关&lt;10 导致的呼叫失败</p>
<p>通话 (拨入或拨出) 被拒绝 = 0</p>
<p>缺少媒体候选人 = 0</p>
<p>媒体连接检查失败 = 0</p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a>边缘服务器

除了基本组件运行状况之外, 以下建议的 KHI 目标还特定于边缘服务器:


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
<td><p>验证失败&lt;20/秒</p>
<p>分配失败&lt;20/秒</p>
<p>每秒&lt;丢弃的数据包</p></td>
</tr>
<tr class="odd">
<td><p>数据代理</p></td>
<td><p>已限制的&lt;服务器连接3</p>
<p>系统为带宽&lt;限制1</p></td>
</tr>
<tr class="even">
<td><p>SIP 堆栈</p></td>
<td><p>超过极限的连接&lt;降1</p>
<p>发送超时&lt;10</p>
<p>流控制的&lt;连接100</p>
<p>传入的请求&lt;已丢弃 1/秒</p>
<p>平均邮件处理&lt; 3 秒</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 网络指南](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[关键运行状况指示器: 用于维护正常 Lync 服务器的基础](http://go.microsoft.com/fwlink/?linkid=391838)  
[Lync 通话质量方法](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

