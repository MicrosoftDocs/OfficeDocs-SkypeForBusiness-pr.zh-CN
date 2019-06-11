---
title: 'Lync Server 2013: Lync Server 中的健康配置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a719a5e8695dbbd0705aa649d72a32a2bfdc7d38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a>Lync Server 2013 中的健康配置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-22_

在各种网站、Microsoft 知识库文章和 Lync 服务器资源工具包工具之间, 在运行 Lync Server 时遇到问题的管理员永远不会从解决这些问题的方法开始。

很明显, 没有办法保证 Lync Server 2013 不会遇到问题, 因为 Lync Server 可能受许多功能 (如网络崩溃和硬件故障) 的影响, 产品本身无法控制。 通过执行运行状况监视, 管理员可以在转换为实际问题之前识别潜在问题。 例如, 管理员可以使用 Lync Server monitoring 识别趋势和趋势。 例如, 音频/视频会议数的稳定增加可能会建议在系统过载之前增加容量的需要。

在类似方式下, 管理员可以使用 System Center Operations Manager 执行以下操作: 在发生指定事件时发出实时警报, 并运行主动测试系统的合成事务。 在 Lync Server 中使用合成事务验证用户是否能够成功完成常见任务, 如登录到系统、交换即时消息或拨打位于公共交换电话网络 (PSTN) 的电话。 例如, 定期运行这些测试可提醒你登录 Lync Server 时遇到潜在问题, 并让你有机会在你的支持团队遇到无法建立连接的呼叫的情况下解决问题。 通过使用 System Center Operations Manager 运行这些合成事务, 管理员可以定期监控每天24小时内的 Lync Server 部署, 而无需对任何可能出现的警报执行任何其他操作。被颁发。

<div>


> [!NOTE]  
> 对于 Lync Server 2013, System Center Operations Manager 管理包还可以检测可能对 Lync Server 产生负面影响的 "外部" 问题。 例如, 如果 Internet 信息服务 (IIS) 脱机、Lync Server 计算机上的系统资源低于指定的数量或 Lync 服务器计算机遇到硬件故障, 则可以通知管理员。



</div>

Lync Server 2013 中的健康配置是围绕 System Center Operations Manager 和 Lync Server 管理包的使用而构建的。 这些管理包包含许多新功能和增强功能, 包括:

  - **任何位置的方案可用性。** Lync Server 2010 管理包引入了通过综合事务监视最终用户方案可用性的概念。 在 Lync Server 2013 中, 这些代理具有更多综合事务, 并且可以从企业内的各种位置运行, 从企业外的远程地理位置, 再到分支机构装置和 Lync Server 2010用于将覆盖范围添加到旧版 Edge 部署的部署。

  - **综合事务日志。** 当合成事务失败时, 管理员有权访问 HTML 日志以帮助确定失败的内容。 这包括了解哪些操作失败、每个操作的延迟、用于运行测试的命令行以及遇到的错误。

  - **增加了通话可靠性覆盖范围。** Lync Server 2010 管理包引入了调用可靠性警报以检测严重连接问题, 这些问题会影响最终用户的音频呼叫。 Lync Server 2013 管理包添加对等即时消息 (IM) 和其他基本会议功能的覆盖范围, 以最大限度地减少干扰, 同时减少噪音。

  - **依赖关系监视。** 由于各种外部因素 (如 IIS 处于离线状态、有限 CPU 和内存资源和磁盘问题), Lync Server 方案可能会失败。 新的管理包检查几个重要的依赖关系, 以确保管理员知道其影响。

  - **增强的报告。** 一组报表, 可帮助管理员估计方案可用性、计划容量, 并查看遇到最多问题的组件。

管理包中还包含多种功能, 可帮助检测和诊断你的 Lync Server 部署是否能够实时查看运行状况。 下表列出了这些功能。

### <a name="management-pack-features"></a>管理包功能

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>功能</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>综合事务</p></td>
<td><p>可从不同位置运行的 Windows PowerShell cmdlet, 以确保最终用户随时可以使用登录、联机状态、即时消息和会议等最终用户方案。</p></td>
</tr>
<tr class="even">
<td><p>呼叫可靠性警报</p></td>
<td><p>通话详细记录 (CDR) 的数据库查询。 这些记录由前端服务器编写, 用于反映最终用户是否能够连接到呼叫或终止通话的原因。 这些查询将导致警告, 这些警报表明各种最终用户遇到连接性问题 (针对对等呼叫或基本会议功能)。</p></td>
</tr>
<tr class="odd">
<td><p>媒体质量警报</p></td>
<td><p>查看每次调用结束时客户端发布的体验质量 (QoE) 报告的数据库查询。 这些查询将产生警报, 这些警报可查明用户在呼叫和会议期间可能遇到较差媒体质量的情况。 数据基于关键指标 (如数据包延迟和丢失) 构建, 这些指标是直接参与通话质量的已知指标。</p></td>
</tr>
<tr class="even">
<td><p>组件运行状况</p></td>
<td><p>单个服务器组件通过使用事件日志和性能计数器来引发警报。 这些警报指示可能严重影响一个或多个最终用户方案的失败条件。 这些警报还可以指示各种其他故障条件, 包括未运行的服务、高故障率、高消息延迟或连接问题。</p></td>
</tr>
<tr class="odd">
<td><p>依赖运行状况</p></td>
<td><p>由于各种外部原因, 可能会发生故障。 管理包现在监视和收集一些关键外部依赖项的数据, 这些依赖项可能表明存在严重问题, 包括 IIS 可用性、服务器和进程的 CPU 和内存使用率以及磁盘指标。</p></td>
</tr>
</tbody>
</table>


系统发出的通知分为三个常规类别:

  - **高优先级警报。** 这些警报指示将导致大型用户组的服务中断的条件。 例如, 单个计算机上的组件故障不是高优先级警报, 因为 Lync Server 2013 具有内置的高可用性功能。 相反, 高优先级的警报表示的问题非常严重, 无法在晚间唤醒管理员。 综合事务和脱机服务 (例如, 音频/视频会议) 检测到的中断是高优先级的警报。

  - **中等优先级的警报 ...** 这些警报指示影响用户子集或指示通话质量降级的条件。 其中包括组件故障、呼叫建立延迟或通话中的音频质量下降等问题。 此类别中的警报是有状态的, 表明问题的当前状态。 例如, 假设您的通话时间超过了报警阈值。 如果通话建立时间返回到正常, 则系统中心运营经理将自动解决这些警报。 这些警报的预期结果是管理员将在同一工作日查看。

  - **其他通知。** 这些是来自可能影响特定用户或用户子集的组件的警报。 例如, 通讯簿服务可能无法分析给定用户的 Active Directory 条目。 这些警报的预期是, 管理员在有时间可用时就会访问他们。

<div>

## <a name="in-this-section"></a>本节内容

  - [配置 Lync Server 2013 以与 System Center Operations Manager 配合使用](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [在 Lync Server 2013 中对综合事务使用丰富日志记录](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [使用 Microsoft SQL Server 2008 R2 作为 Lync Server 2013 的 System Center Operations Manager 数据库](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

