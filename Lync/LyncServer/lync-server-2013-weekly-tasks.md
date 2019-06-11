---
title: Lync Server 2013：周任务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d3128780c456c3f38f306d31f258ce903eb50a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a>Lync Server 2013 中的周任务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2015-08-17_

每周任务通常与收集和分析日志和报告相关。

<div>

## <a name="archive-event-logs"></a>存档事件日志

如果事件日志未配置为根据需要覆盖事件, 则必须定期存档并删除这些事件。 此操作对安全日志特别重要, 在调查尝试的安全违规时可能需要这样做。

您的组织将必须定义日志存档的策略和过程。

</div>

<div>

## <a name="create-reports"></a>创建报表

创建状态报告以帮助进行容量规划、SLA 审查和性能分析。 使用事件日志和系统监视器中的每日数据创建有关磁盘、内存和 CPU 使用率的报告。 使用 System Center Operations Manager 生成正常运行时间和可用性报告。

您的组织将必须定义状态报告的策略和过程。

</div>

<div>

## <a name="incident-reports"></a>事件报告

对与 Lync Server 相关的组织事件报告执行每周审核。 本审核应包括以下内容:

  - 最热门的生成、已解决和挂起事件。

  - 未解决的事件的解决方案。

  - 将报表更新为包含新的故障票证。

  - 为疑难解答指南更新文档存储库并发布有关中断的剖析。

由于组织的事件跟踪系统是独立于 Lync Server 的选项, 因此特定说明或指针不可用。 请参阅你的组织选择的系统的文档。

</div>

<div>

## <a name="check-iis-logs-and-performance"></a>检查 IIS 日志和性能

对 Internet 信息服务 (IIS) 日志和性能执行每周查看。 有关如何监视 IIS 日志和性能的详细信息, 请参阅[Windows Server 2003 Internet Information Services (IIS) 事件日志记录概述](http://go.microsoft.com/fwlink/?linkid=36077)。 评审应包括以下内容:

  - 用于监视 WWW 服务缓存的 Web 服务缓存计数器。

  - Active Server Page (Asp) 计数器, 用于监视以 Asp 形式运行的应用程序。

</div>

<div>

## <a name="generate-database-reports"></a>生成数据库报告

**生成 SQL 数据库报表**

1.  打开 Lync Server 2013。

2.  在控制台树中, 展开 "林" 节点, 展开 "**企业版池**", 然后单击要为其生成数据库报告的池。

3.  在 "详细信息" 窗格中, 单击 "**数据库**" 选项卡。

4.  在 "**数据库**" 选项卡上, 执行下列操作:
    
    1.  若要查看数据库的名称, 请展开 "**常规设置**", 然后查看数据库名称。
    
    2.  若要检索池的当前用户汇总统计信息, 请展开 "**用户摘要报告**", 单击 "**转到**", 然后查看结果。
    
    3.  若要检索池的单个用户的当前每用户数据, 请展开 "**每用户报告**", 键入用户的 SIP URI, 单击 "**转到**", 然后查看结果。

若要检索池的当前会议摘要统计信息, 请展开 "**会议摘要" 报表**, 单击 "**转到**", 然后查看结果。

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a>检查安全和 Lync 服务器更新

标识任何新服务包、修补程序或更新。 如果适用, 请在测试实验室中测试这些项, 并使用更改控制过程安排部署到生产服务器。 此外, Lync Server 组件更新现已作为 Windows 更新的一部分提供。 所有 Lync Server 组件更新都必须在运行 Lync Server 的所有服务器上同时更新, 这些更新均适用于这些更新。

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a>运行 Lync Server 2013 最佳做法分析器

Lync Server 2013 最佳做法分析器工具是一种诊断工具, 用于收集配置信息并确定是否根据 Microsoft 最佳做法设置配置。 此工具的文档位于[Lync Server 2013 最佳做法分析器](lync-server-2013-lync-server-best-practices-analyzer.md)中。

该工具将部署的配置数据与 Lync Server 的一组预定义的规则进行比较, 并报告潜在问题。 对于报告的每个问题, 该工具都提供了 Lync Server 环境中的当前配置和推荐的配置。

使用正确的网络访问, 该工具可以检查运行 Lync Server 2013 的 AD DS 和服务器, 以执行以下操作:

  - 主动执行运行状况检查, 验证是否根据推荐的最佳做法设置了配置

  - 生成问题列表, 如 "最优" 配置设置或不支持或不推荐的选项

  - 判断系统的常规运行状况

  - 帮助解决特定问题

  - 提示您下载更新 (如果有)

  - 提供有关报告问题的联机文档和本地文档, 包括疑难解答提示

  - 生成可供将来查看的配置信息

确保 RTCBPA 已安装在所有 Lync Server 2013 服务器上, 并生成每周运行状况检查报告。 注意结果并更正错误 (如有必要)。

</div>

<div>

## <a name="review-sla-performance-figures"></a>查看 SLA 性能数据

检查上一周的关键性能数据。 根据 SLA 的要求查看性能。 确定未满足其目标的趋势和项目。

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a>查看 System Center Operations Manager 管理包和体验报告质量

获取和查看 Lync Server 2013 管理包和体验报告质量。

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a>生成和查看企业版池的数据库报告

**生成池报告**

1.  打开 Lync Server 2013。

2.  在控制台树中, 展开 "林" 节点, 展开 "**企业版池**", 然后单击要为其生成数据库报告的池。

3.  在 "详细信息" 窗格中, 单击 "**数据库**" 选项卡。

4.  在 "**数据库**" 选项卡上, 执行下列操作:
    
    1.  若要查看数据库的名称, 请展开 "**常规设置**", 然后查看数据库名称。
    
    2.  若要检索池的当前用户汇总统计信息, 请展开 "**用户摘要报告**", 单击 "**转到**", 然后查看结果。
    
    3.  若要检索池的单个用户的当前每用户数据, 请展开 "**每用户报告**", 键入用户的 SIP URI, 单击 "**转到**", 然后查看结果。

若要检索池的当前会议摘要统计信息, 请展开 "**会议摘要" 报表**, 单击 "**转到**", 然后查看结果。

对于每个企业版池, 管理员可以使用 "**数据库**" 选项卡查看数据库名称, 并从数据库中检索和查看报表。

### <a name="database-reports-and-descriptions"></a>数据库报告和说明

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>部分</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>用户摘要报告</p></td>
<td><p>Dbanalyze/v/report:/sqlserver: value]</p>
<p>此部分显示有关池中用户的聚合信息, 例如启用的用户数、每位用户的平均联系人数以及特定功能的用户数。</p>
<p>使用这些报表时, 以下信息可能会有所帮助:</p>
<ul>
<li><p>已启用的用户是通过使用 Active Directory 用户和计算机管理单元启用 Lync Server 2013 的用户。</p></li>
<li><p>活动用户是已登录或已注册的用户。</p></li>
<li><p>摘要报告还提供了一组有关联系人的统计信息。 这些统计信息仅适用于至少已登录过一次且至少有一个联系人的用户的人口。 因此, 你通常看不到最少数量的联系人。 由于此行为, 如果用户没有联系人 (但在用户已注册的情况下处于活动状态), 您可能会看到: &lt;对于某些&gt;统计信息字段为空。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>每用户报告</p></td>
<td><p>Dbanalyze/v/report: disk [/sqlserver: value]</p>
<p>与通过用户填充计算的摘要报表不同, 这些报表是有关特定用户的报表。</p></td>
</tr>
<tr class="odd">
<td><p>会议摘要报告</p></td>
<td><p>Dbanalyze/v/report: 会议 [/sqlserver: value]</p>
<p>此部分显示有关池的会议摘要统计信息 (例如活动会议数和参与者总数) 的聚合信息。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a>运行带宽利用率分析器

带宽用量分析器工具可创建有关企业网络中各个 WAN 链路上 UC 端点的带宽消耗的各种视图的报告。 这些报告可用于了解当前带宽使用模式, 并有助于进行带宽容量规划。 它还会循环访问分配给各个链路的带宽容量。

此工具可执行以下操作：

  - 通过网络生成特定于音频使用情况的报告

  - 帮助更高效地进行容量规划并循环访问分配给各个链路的带宽容量

带宽利用率分析器可生成带宽容量和使用情况报告的图形化图形。 它们如下所示:

  - 企业网络中的所有 WAN 链路

  - 已选择的所选 WAN 链接进行筛选

  - 按已超过链路容量的 WAN 链路进行筛选

  - 使用预配带宽下的 WAN 链接进行筛选

  - 按关键级别的 WAN 链接进行筛选 (带宽使用率大于 WAN 链接带宽容量的 90%)

  - 按 WAN 链接类型 (网络-网站链接、interregional 链接和网站内的链接) 进行筛选

  - 按网络区域进行筛选

有关此工具的文档在[Lync Server 2013 资源工具包工具文档](http://go.microsoft.com/fwlink/?linkid=623245)中提供。

</div>

<div>

## <a name="see-also"></a>另请参阅


[每周任务清单](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

