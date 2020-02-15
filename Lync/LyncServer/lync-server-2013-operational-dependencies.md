---
title: Lync Server 2013：操作依赖项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 861d927053e05c395c39118910032df41566b32e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034072"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a>Lync Server 2013 中的操作依赖项

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-05-15_

本文档中讨论的参考体系结构可帮助确保你具有 Lync Server 2013 部署，该部署不仅可扩展到组织的要求，而且根据 Microsoft 最佳做法进行了构建。 请注意，它可能会导致 Lync Server 2013 实现是一个动态服务，与企业中的任何其他服务一样，仍需要监控和主动管理来维护企业的高级别服务可用性和服务质量。

随着 Lync Server 2013 在组织的日常业务中变得深度更深，此服务应由准确而有形的服务级别管理来管理，这一点非常重要。 Lync 系统体系结构可能会变得复杂且非常集成，以便维护有效的服务级别管理并为 Lync Server 2013 建立 Sla。了解系统在其他平台和服务器上的依赖关系至关重要。 同等重要的是，请注意哪些业务服务（如语音和 UC 集成应用程序）依赖 Lync。

必须建立 Lync Server 2013，以记录所有已说出的依赖项。 服务映射将允许您在 Lync 及其相关服务之间制定 SLA，并提供 SLA 协商的起始位置。

下表列出了 Lync 基础结构的典型依赖项服务。 其中的每种技术都应具有自己的主动监控。

### <a name="typical-dependency-services"></a>典型的依赖项服务

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>依赖项服务</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>操作系统</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>服务器硬件</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Active Directory</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>公钥基础结构</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>域命名服务</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>数据库服务</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>存储服务</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>系统管理–监控和分发</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>安全服务-防病毒</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>网络基础结构-Internet</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>网络基础结构–内部（LAN/WAN）</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>电话服务基础结构– IP-PBX 和网关</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>云服务</p></td>
<td></td>
</tr>
</tbody>
</table>


假定组织在执行基本服务级别管理功能（如由 MOF 规定的更改、事件和发布管理）中执行成熟的操作。 Lync 解决方案应由这些函数采用，并遵循相同的操作管理过程。

根据上面获取的信息构建，我们可以更好地了解对企业中的 Lync 服务有何影响。 为了帮助确保 Lync Server 2013 服务可用性和质量，以下监控工具必须附带参考体系结构部署：

### <a name="monitoring-tools"></a>监视工具

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>组件</th>
<th>说明</th>
<th>适用的网站</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 监视服务器</p></td>
<td><p>每个中心站点至少部署一个 Lync Server 2013 监视服务器角色，并配置体验质量（QoE）报告包。</p>
<p>有关详细信息，请参阅 Lync Server 2013 部署文档：</p>
<p><a href="lync-server-2013-deploying-monitoring.md">在 Lync Server 2013 中部署监控</a></p></td>
<td><p>中央站点</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>将每个池 Tether 为其最接近的监视服务器角色实例。</p></td>
<td><p>中央站点</p>
<p>分支站点</p></td>
</tr>
<tr class="odd">
<td><p>System Center Operations Manager 2012</p></td>
<td><p>导入了 Microsoft Lync Server 2013 管理包（MP）的 System Center Operations Manager 2012。</p>
<p>管理包实现传统事件日志和基于性能计数器的规范，并在 Lync Server 2013 中启用新可用的检测。</p></td>
<td><p>中央站点</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>请确保基于读取中央管理数据库中发布的拓扑文档的中央发现脚本自动完成发现需要监视的角色和组件的集中发现。</p></td>
<td><p>中央站点</p>
<p>分支站点</p>
<p>边缘网站</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>将 System 中心 Operations Manager 2007 代理部署到运行 Lync Server 的所有已部署服务器。</p></td>
<td><p>中央站点</p>
<p>分支站点</p>
<p>边缘网站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>请确保为通知配置了已设置优先级的警报：</p>
<p>高优先级警报</p>
<p>中等优先级警报</p>
<p>其他警报。</p></td>
<td><p>中央站点</p>
<p>分支站点</p>
<p>边缘网站</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>为您的部署配置端口监视。</p></td>
<td><p>中央站点</p>
<p>分支站点</p>
<p>边缘网站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>为您的部署配置 URL 监视</p></td>
<td><p>中央站点</p></td>
</tr>
<tr class="odd">
<td><p>Lync 和 System Center Operations Manager 集成</p></td>
<td><p>部署呼叫可靠性和媒体质量 MonitoringCall 可靠性和媒体质量监控使用监视服务器计算机作为其观察程序节点来监视 Lync Server 的呼叫可靠性和媒体质量。 这两种功能都可查询监视服务器数据库以进行分析。</p></td>
<td><p>中央站点</p>
<p>分支站点</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>确保正确配置媒体质量警告阈值。 下表显示编解码器的最大网络平均观点得分。 在生产中，应在设定的期限内监控这些分数，并且必须根据组织特定的 NMOS 得分来建立可接受的阈值。</p></td>
<td><p>中央站点</p>
<p>分支站点</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 综合事务观察程序</p></td>
<td><p>将专用 Lync Server 部署为综合事务观察程序。</p>
<p>综合事务是由管理包根据预定义间隔自动触发的 Lync Server 2013 Windows PowerShell cmdlet。 这些操作在综合事务观察程序节点上执行，这是一种管理员指定的服务器，负责为每个池发现和执行 STs。</p>
<p>建议您不要将现有的 Microsoft Lync Server 2013 服务器用作综合事务观察程序节点。 这是因为运行 STs 的 CPU/内存使用率要求较高。 为综合事务观察程序节点使用新的服务器计算机（或虚拟服务器）。</p></td>
<td><p>中央站点</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>部署综合事务观察程序节点。</p>
<p>请参阅 UCTAP connect 文档中的 MonitoringCS_withSCOM .docx 文档。</p></td>
<td><p>中央站点</p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a>每个编解码器的最大网络 MOS 分数

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>方案</th>
<th>编解码器</th>
<th>最大 NMOS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UC-UC 呼叫</p></td>
<td><p>RTAudio WB</p></td>
<td><p>4.10</p></td>
</tr>
<tr class="even">
<td><p>UC-UC 呼叫</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2.95</p></td>
</tr>
<tr class="odd">
<td><p>电话会议</p></td>
<td><p>Siren</p></td>
<td><p>3.72</p></td>
</tr>
<tr class="even">
<td><p>UC-PSTN 呼叫</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2.95</p></td>
</tr>
<tr class="odd">
<td><p>UC-PSTN 呼叫</p></td>
<td><p>G-711</p></td>
<td><p>3.61</p></td>
</tr>
</tbody>
</table>


在以前的主动预防性监视活动中，应根据 Lync RA 操作指南中定义的每日、每周和每月定期执行维护任务。

</div>

<span> </span>

</div>

</div>

</div>

