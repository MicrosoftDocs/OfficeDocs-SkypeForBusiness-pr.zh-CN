---
title: 'Lync Server 2013: 操作依赖项'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d54ef9959f48c085ad4f5f28f182b86442ebec8c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a>Lync Server 2013 中的操作相关性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2015-05-15_

本文档中讨论的参考体系结构将帮助确保你拥有的 Lync Server 2013 部署不仅可扩展到组织的要求, 还可根据 Microsoft 最佳做法进行构建。 请注意, 它可能是 Lync Server 2013 实现是一种动态服务, 与企业中的任何其他服务一样, 它仍需要监视和主动管理, 以便为企业保持高级别的服务可用性和服务质量。

随着 Lync Server 2013 在组织的日常企业中变得更深 ingrained, 该服务必须通过准确的有形服务级别管理来管理。 Lync 系统体系结构可能会变得复杂且非常集成, 以便维护有效的服务级别管理并建立 Lync Server 2013 的 Sla, 这对了解系统对其他平台和服务器的依赖非常重要。 同样重要的是要注意哪些商业服务 (如语音和 UC 集成应用程序) 依赖于 Lync。

必须建立 Lync Server 2013, 注意所有所说的依赖关系。 服务地图将允许你在 Lync 及其依赖的服务之间制定一个 SLA, 并提供 SLA 协商的起始位置。

下表列出了 Lync 基础结构的典型依赖服务。 其中每种技术都应具有其自己的主动预防性监控。

### <a name="typical-dependency-services"></a>典型的依赖服务

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>依赖服务</th>
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
<td><p>系统管理-监视和分发</p></td>
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
<td><p>网络基础结构-内部 (LAN/WAN)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>电话服务基础结构-IP-PBX 和网关</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>云服务</p></td>
<td></td>
</tr>
</tbody>
</table>


假定组织在使用由 MOF 规定的基本服务级别管理功能 (如更改、事件和发布管理) 中运行成熟。 Lync 解决方案应由这些函数采纳, 并遵循相同的操作管理过程。

根据以上获取的信息构建, 我们现在更深入地了解对企业中的 Lync 服务有哪些影响。 为了帮助确保 Lync Server 2013 服务可用性和质量, 以下监视工具必须附带参考体系结构部署:

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
<th>适用网站</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 监视服务器</p></td>
<td><p>每个中心站点至少部署一个 Lync Server 2013 监视服务器角色, 并配置体验质量 (QoE) 报告包。</p>
<p>有关详细信息, 请参阅 Lync Server 2013 部署文档:</p>
<p><a href="lync-server-2013-deploying-monitoring.md">在 Lync Server 2013 中部署监视</a></p></td>
<td><p>中心网站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>将每个池 Tether 到最接近的监视服务器角色实例。</p></td>
<td><p>中心网站</p>
<p>分支站点</p></td>
</tr>
<tr class="odd">
<td><p>System Center Operations Manager 2012</p></td>
<td><p>已导入 Microsoft Lync Server 2013 管理包 (MP) 的 System Center Operations Manager 2012。</p>
<p>管理包实现传统事件日志和基于性能计数器的检测使用, 并在 Lync Server 2013 中启用新可用的检测。</p></td>
<td><p>中心网站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>确保基于用于读取管理中心数据库中发布的拓扑文档的中心发现脚本, 自动完成发现需要监视的角色和组件的集中发现。</p></td>
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
<td><p>请确保为通知配置了优先警报:</p>
<p>高优先级警报</p>
<p>中等优先级的警报</p>
<p>其他通知。</p></td>
<td><p>中央站点</p>
<p>分支站点</p>
<p>边缘网站</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>为你的部署配置端口监视。</p></td>
<td><p>中央站点</p>
<p>分支站点</p>
<p>边缘网站</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>为你的部署配置 URL 监视</p></td>
<td><p>中央站点</p></td>
</tr>
<tr class="odd">
<td><p>Lync 和 System Center Operations Manager 集成</p></td>
<td><p>部署通话可靠性和媒体质量 MonitoringCall 可靠性和媒体质量监视将监视服务器计算机用作其观察程序节点, 以监视 Lync 服务器的调用可靠性和媒体质量。 这两个功能都可查询监视服务器数据库以进行分析。</p></td>
<td><p>中央站点</p>
<p>分支站点</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>确保准确配置媒体质量警告阈值。 下表显示了编解码器的最大网络平均观点。 在生产中, 这些分数应针对设定的时间段进行监视, 并且必须根据组织特定的 NMOS 分数来建立可接受的阈值。</p></td>
<td><p>中央站点</p>
<p>分支站点</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 合成事务观察程序</p></td>
<td><p>将专用 Lync 服务器部署为合成事务观察程序。</p>
<p>合成事务是 Lync Server 2013 Windows PowerShell cmdlet, 这些 cmdlet 由管理包在预定义的时间间隔内自动触发。 这些操作在综合事务观察程序节点上执行, 该节点是管理员指定的服务器, 负责为每个池发现和执行 STs。</p>
<p>我们不建议使用现有的 Microsoft Lync Server 2013 服务器作为合成事务观察程序节点。 这是由于运行 STs 的 CPU/内存使用要求较高。 将新的服务器计算机 (或虚拟服务器) 用于合成事务观察程序节点。</p></td>
<td><p>中央站点</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>部署合成事务观察程序节点。</p>
<p>请参阅 UCTAP connect 文档中的 MonitoringCS_withSCOM 文档。</p></td>
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
<th>应用场景</th>
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


在以前的 pro 活动监视活动之前和之后, 应根据 Lync RA 操作指南中定义的每天、每周和每月定期执行维护任务。

</div>

<span> </span>

</div>

</div>

</div>

