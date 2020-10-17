---
title: Lync Server 2013：每周任务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8177cf0a647ec5155a32a91c6e764e9c13e1dcb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518219"
---
# <a name="weekly-tasks-in-lync-server-2013"></a>Lync Server 2013 中的每周任务

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-08-17_

每周任务通常与收集和分析日志和报告有关。

<div>

## <a name="archive-event-logs"></a>存档事件日志

如果未将事件日志配置为根据需要覆盖事件，则必须定期存档并删除它们。 此操作对于安全日志尤其重要，在调查尝试的安全违规时，这可能是必需的。

您的组织将必须定义日志存档的策略和过程。

</div>

<div>

## <a name="create-reports"></a>创建报表

创建状态报告以帮助进行容量规划、SLA 审查和性能分析。 使用事件日志和系统监视器中的日常数据来创建有关磁盘、内存和 CPU 使用率的报告。 使用 System Center Operations Manager 生成正常运行时间和可用性报告。

您的组织将必须定义状态报告的策略和过程。

</div>

<div>

## <a name="incident-reports"></a>事件报告

对与 Lync Server 相关的组织事件报告执行每周审核。 此审核应包括以下内容：

  - 最上面生成、解析和挂起的事件。

  - 未解决事件的解决方案。

  - 将报告更新为包含新的故障单。

  - 更新用于故障排除指南和 post 剖析的文档存储库关于中断。

由于您组织的事件跟踪系统是独立于 Lync Server 的选择，因此特定说明或指针不可用。 请参阅您的组织选择的系统的相关文档。

</div>

<div>

## <a name="check-iis-logs-and-performance"></a>检查 IIS 日志和性能

对 Internet 信息服务 (IIS) 日志和性能进行每周的审阅。 有关如何监视 IIS 日志和性能的详细信息，请参阅 [Windows Server 2003 Internet Information Services (IIS) 事件日志概述](https://go.microsoft.com/fwlink/?linkid=36077)。 评审应包括以下内容：

  - 用于监视 WWW 服务缓存的 Web 服务缓存计数器。

  -  (Asp) 计数器中的 Active Server Pages 可监视以 Asp 的形式运行的应用程序。

</div>

<div>

## <a name="generate-database-reports"></a>生成数据库报告

**生成 SQL 数据库的报告**

1.  打开 Lync Server 2013。

2.  在控制台树中，展开 "林" 节点，展开 " **企业版池**"，然后单击要为其生成数据库报告的池。

3.  在详细信息窗格中，单击 " **数据库** " 选项卡。

4.  在 " **数据库** " 选项卡上，执行以下操作：
    
    1.  若要查看数据库的名称，请展开 " **常规设置**"，然后查看数据库名称。
    
    2.  若要检索池的当前用户汇总统计信息，请展开 " **用户摘要报告**"，单击 " **开始**"，然后查看结果。
    
    3.  若要检索池的单个用户的当前每用户数据，请展开 " **每用户报告**"，键入用户的 SIP URI，单击 " **开始**"，然后查看结果。

若要检索池的当前会议摘要统计信息，请展开 " **会议摘要报告**"，单击 " **开始**"，然后查看结果。

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a>检查安全和 Lync Server 更新

确定任何新的 service pack、修补程序或更新。 如果适用，请在测试实验室中进行测试，并使用更改控制过程安排部署到生产服务器。 此外，Lync Server 组件更新现已作为 Windows 更新的一部分提供。 必须同时在运行 Lync Server 且适用这些更新的所有服务器上同时更新所有 Lync Server 组件更新。

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a>运行 Lync Server 2013 最佳实践分析工具

Lync Server 2013 最佳实践分析工具是一种诊断工具，它收集配置信息，并根据 Microsoft 最佳实践确定是否设置配置。 此工具的文档位于 [Lync Server 2013 最佳实践分析](lync-server-2013-lync-server-best-practices-analyzer.md)工具中。

该工具会将部署的配置数据与 Lync Server 的一组预定义的规则进行比较，并报告潜在问题。 对于报告的每个问题，该工具都提供了 Lync Server 环境中的当前配置以及建议的配置。

使用正确的网络访问，该工具可以检查运行 Lync Server 2013 的 AD DS 和服务器，以执行以下操作：

  - 主动执行运行状况检查，验证是否根据建议的最佳实践设置了配置

  - 生成问题列表，如最佳配置设置或不受支持的或建议的选项

  - 判断系统的常规运行状况

  - 帮助解决特定问题

  - 提示您下载更新（如果有）

  - 提供有关报告问题的联机和本地文档，并包括故障排除提示

  - 生成可被捕获以供以后查看的配置信息

确保在所有 Lync Server 2013 服务器上安装 RTCBPA.msi，并生成每周运行状况检查报告。 如果需要，请记下结果并更正。

</div>

<div>

## <a name="review-sla-performance-figures"></a>查看 SLA 性能图

检查上一周的关键性能数据。 查看针对 SLA 要求的性能。 确定未满足其目标的趋势和项目。

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a>查看 System Center Operations Manager 管理包和体验质量报告

获取并查看 Lync Server 2013 管理包和体验质量报告。

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a>生成和查看企业版池的数据库报告

**生成池报告**

1.  打开 Lync Server 2013。

2.  在控制台树中，展开 "林" 节点，展开 " **企业版池**"，然后单击要为其生成数据库报告的池。

3.  在详细信息窗格中，单击 " **数据库** " 选项卡。

4.  在 " **数据库** " 选项卡上，执行以下操作：
    
    1.  若要查看数据库的名称，请展开 " **常规设置**"，然后查看数据库名称。
    
    2.  若要检索池的当前用户汇总统计信息，请展开 " **用户摘要报告**"，单击 " **开始**"，然后查看结果。
    
    3.  若要检索池的单个用户的当前每用户数据，请展开 " **每用户报告**"，键入用户的 SIP URI，单击 " **开始**"，然后查看结果。

若要检索池的当前会议摘要统计信息，请展开 " **会议摘要报告**"，单击 " **开始**"，然后查看结果。

对于每个企业版池，管理员可以使用 " **数据库** " 选项卡查看数据库名称，并从数据库中检索和查看报告。

### <a name="database-reports-and-descriptions"></a>数据库报告和说明

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>分区</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>用户摘要报告</p></td>
<td><p>Dbanalyze/v/report：/sqlserver： value]</p>
<p>此部分显示有关池中用户的聚合信息，例如已启用的用户数、每个用户的平均联系人数以及特定功能的用户数。</p>
<p>在使用这些报告时，以下信息可能很有帮助：</p>
<ul>
<li><p>已启用的用户是通过使用 Active Directory 用户和计算机管理单元启用了 Lync Server 2013 的用户。</p></li>
<li><p>"活动用户" 是已登录或已注册的用户。</p></li>
<li><p>摘要报告还提供了有关联系人的一组统计信息。 这些统计信息仅对至少已登录一次且至少有一个联系人的用户群体有效。 因此，您通常不会看到最小数量为0的联系人。 由于此行为，如果用户没有联系人 (但处于活动状态，则表明用户已注册) ，您可能会看到： &lt; &gt; 对于某些统计信息字段为空。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Per-User 报告</p></td>
<td><p>Dbanalyze/v/report： disk [/sqlserver： value]</p>
<p>与通过用户群体计算的摘要报告不同，这些报告是有关特定用户的报告。</p></td>
</tr>
<tr class="odd">
<td><p>会议摘要报告</p></td>
<td><p>Dbanalyze/v/report：会议 [/sqlserver： value]</p>
<p>此部分显示有关池的会议摘要统计信息的聚合信息，例如活动会议数和参与者总数。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a>运行带宽使用率分析器

带宽利用率分析器是一种工具，该工具通过企业网络中的多个 WAN 链接的 UC 终结点创建有关带宽消耗的各种视图的报告。 这些报告可用于了解当前的带宽使用模式，并可帮助进行带宽容量规划。 它还会对分配给各个链路的带宽容量进行迭代。

此工具执行以下操作：

  - 通过网络生成音频使用情况的特定报告

  - 有助于在分配给各个链路的带宽容量中进行更有效的容量规划和迭代

带宽利用率分析器可生成带宽容量和使用情况报告的图形化绘图。 它们分别为：

  - 企业网络中的所有 WAN 链路

  - 通过选定的已选择的 WAN 链接进行筛选

  - 通过已超出链接容量的 WAN 链路进行筛选

  - 使用预配带宽下的 WAN 链路进行筛选

  - 按 WAN 链路进行筛选，达到关键级别 (WAN 链路的带宽使用率大于 90%) 

  - 按 WAN 链接类型（网络站点链接、区域间链接和站点内的链接）进行筛选

  - 按网络区域筛选

此工具的文档在 [Lync Server 2013 资源工具包工具文档](https://go.microsoft.com/fwlink/?linkid=623245)中提供。

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

