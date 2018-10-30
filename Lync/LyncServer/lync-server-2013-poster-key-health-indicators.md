---
title: 关键运行状况指示器
TOCTitle: 招贴：关键运行状况指示器
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084818
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 关键运行状况指示器

 

_**上一次修改主题：** 2016-12-08_

本文是[关键运行状况指示器：维护正常运行的 Lync 服务器的基础](http://go.microsoft.com/fwlink/?linkid=391838)招贴的配套文章，可从下载中心下载此招贴。

![说明使用 KHI 数据进行故障排除的海报](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "说明使用 KHI 数据进行故障排除的海报")

您可以使用此招贴了解关键运行状况指示器 (KHI) - 旨在揭示用户体验问题的性能计数器和阈值。通常，收集 KHI 数据是实施呼叫质量方法 (Call Quality Methodology, CQM) 的第一步，CQM 专用于确保 Lync 用户的优质音频体验。

如果您有关于如何使用 CQM 的问题，您可以将问题提交到 cqmfeedback@microsoft.com。

此招贴解释了以下方面的内容：

  - 什么是关键运行状况指示器？

  - 收集 KHI 数据

  - 适用于所有服务器角色的修正流

  - 词汇表

  - 前端服务器

  - 后端 SQL 服务器

  - 中介服务器

  - 边缘服务器

## 什么是关键运行状况指示器？

关键运行状况指示器 (KHI) 是旨在揭示用户体验问题的性能计数器和阈值。通常，收集 KHI 数据是实施呼叫质量方法 (Call Quality Methodology, CQM) 的第一步，CQM 专用于确保 Lync 用户的优质音频体验。

KHI 作为标准 Lync 监控解决方案的补充使用（例如 System Center Operations Manager、Synthetic Transactions、Monitoring Server），不能代替这些解决方案。

收集 KHI 性能计数器并填充网络连接指南附带的 KHI 电子表格，以生成有助于您确定 Lync 部署的服务器运行状况的计分卡。填完后，会指导您修复环境，并提供关于其他相关方的更多信息。每月评估一次 KHI，将其纳入任何部署的当前运行流程中。

下载 Lync Server 网络连接指南以查看 KHI 的完整列表并获取相关电子表格。

## 收集 KHI 数据

1.  在每台 Lync 服务器上运行《Lync Server 网络连接指南》附带的 KHI 脚本。这将在性能计数器内部创建一个数据收集器并将其命名为 KHI。默认情况下将每隔 15 秒钟调查一次数据。

2.  在开始公司一天的工作之前，请先到每台 Lync 服务器上启动 KHI 数据收集器。

3.  一天的工作结束时，停止 KHI 数据收集器并将数据复制到一个中央位置。

4.  使用性能监视器填充下载的《Lync Server 网络连接指南》附带的 KHI 电子表格后，将结果与建议的目标值进行比较。

## 适用于所有服务器角色的修正流

对于您的 Lync 实施中的每台服务器，先验证服务器组件的运行状况和系统性能恰处于或高于所需的级别。只有经过该验证后，您才应查看与总体 Lync 实施中的服务器角色相关的指示器。

首先收集所有服务器的 KHI 性能数据。针对每个系统角色（本文档后面部分将详加讨论），确定基本系统组件是否符合建议的目标值。如果不符合，修复系统性能，然后重新收集 KHI 数据，确保系统运行状况正常，然后再查看特定于 Lync 实施中的服务器角色的指标。适用于所有角色的组件正常运行状况的定义如下：

  - CPU 使用率 \< 80%

  - 平均磁盘写入时间 \< 10 ms

  - 平均磁盘读取时间 \< 10 ms

  - 可用内存 \> 系统总内存量的 20%

  - 网络队列长度 \< 2

  - 丢弃数据包数（入/出）= 0

## 词汇表

此招贴中使用的术语和缩写词如下：

AS MCU = 应用程序共享多点控制单元

AV MCU = 音频/视频 MCU

IM MCU = 即时消息 MCU

UCWA = 统一通信 Web API

AV 边缘 = 通过边缘的音频/视频的通道

AV Auth = 音频/视频身份验证

SIP 堆栈 = 包含 Lync 的核心 SIP 实施

数据代理 = 用于边缘会议

LySS = Lync 存储服务

## 前端服务器

以下建议的 KHI 目标值特定于前端服务器，补充基本组件运行状况信息：


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
<td><p>MCU 运行状况 &lt;2</p></td>
</tr>
<tr class="even">
<td><p>Web 组件</p></td>
<td><p>通讯组列表扩展 AD 超时 &lt;0</p>
<p>ABWQ 失败次数 = 0</p>
<p>LIS 失败次数 = 0</p>
<p>身份验证错误次数 &lt; 1 个/秒</p>
<p>被拒绝的 ASP.NET v4 请求数 = 0</p></td>
</tr>
<tr class="odd">
<td><p>SIP 堆栈</p></td>
<td><p>平均传入消息处理时间 &lt; 1 秒</p>
<p>丢弃的传入响应数 &lt; 1 个/秒 丢弃的传入请求数 &lt; 1 个/秒</p>
<p>队列延迟 &lt; 100 ms</p>
<p>存储过程延迟 &lt; 100 ms</p>
<p>阻止的请求数 = 0</p>
<p>身份验证错误次数 &lt; 1 个/秒</p>
<p>传入消息超时 &lt; 2</p>
<p>平均传入消息挂起时间 &lt; 1 秒</p>
<p>流控制的连接 &lt; 2</p>
<p>平均推出队列延迟 &lt; 2 秒</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>存储服务 DB 已用的空间百分比 &lt; 80%</p>
<p>副本复制失败次数 = 0</p>
<p>数据丢失事件的数量 = 0</p></td>
</tr>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>页面平均寿命 &gt; 300 秒</p>
<p>批处理请求数/秒 &lt; 2500</p></td>
</tr>
</tbody>
</table>


## 后端 SQL 服务器

以下建议的 KHI 目标值特定于 SQL 服务器，补充基本组件运行状况信息：


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
<td><p>页面平均寿命 &gt; 300 秒</p>
<p>批处理请求数/秒 &lt; 2500</p></td>
</tr>
</tbody>
</table>


## 中介服务器

以下建议的 KHI 目标值特定于中介服务器，补充基本组件运行状况信息：


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
<td><p>负载呼叫失败索引 = 0</p>
<p>由于代理原因失败的呼叫数量 &lt;10</p>
<p>由于网关原因失败的呼叫数量 &lt;10</p>
<p>被拒绝的呼叫（进或出）数量 = 0</p>
<p>缺少的候选介质数量 = 0</p>
<p>介质连接性检查失败次数 = 0</p></td>
</tr>
</tbody>
</table>


## 边缘服务器

以下建议的 KHI 目标值特定于边缘服务器，补充基本组件运行状况信息：


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
<td><p>AV Auth</p></td>
<td><p>错误请求数 &lt; 20 个/秒</p></td>
</tr>
<tr class="even">
<td><p>AV 边缘</p></td>
<td><p>身份验证失败次数 &lt; 20 个/秒</p>
<p>分配失败次数 &lt; 20 个/秒</p>
<p>丢弃的数据包数量 &lt; 300 个/秒</p></td>
</tr>
<tr class="odd">
<td><p>数据代理</p></td>
<td><p>被阻止的服务器连接数 &lt; 3</p>
<p>处于被阻止状态的系统数量 &lt; 1</p></td>
</tr>
<tr class="even">
<td><p>SIP 堆栈</p></td>
<td><p>丢弃的超过限制的连接数 &lt; 1</p>
<p>超时发送的数量 &lt;10</p>
<p>流控制的连接数 &lt;100</p>
<p>丢弃的传入请求数量 &lt; 1 个/秒</p>
<p>平均消息处理时间 &lt; 3 秒</p></td>
</tr>
</tbody>
</table>


## 另请参阅

#### 其他资源

[Lync Server 网络连接指南](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[关键运行状况指示器：维护正常运行的 Lync 服务器的基础](http://go.microsoft.com/fwlink/?linkid=391838)  
[Lync 呼叫质量方法](http://go.microsoft.com/fwlink/?linkid=391841)

