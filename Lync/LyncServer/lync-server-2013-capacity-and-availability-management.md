---
title: Lync Server 2013：容量和可用性管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity and availability management
ms:assetid: 207a2997-f482-4bee-892d-d2b112294481
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720325(v=OCS.15)
ms:contentKeyID: 63969586
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efef66bcac833bb67c67dc453c25f3e0f6d51ba1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512849"
---
# <a name="capacity-and-availability-management-in-lync-server-2013"></a>Lync Server 2013 中的容量和可用性管理

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-08-18_

容量管理和可用性管理的目的是衡量和控制系统性能。 我们建议您实施容量管理和可用性管理过程，以便您能够衡量和控制系统性能。 您必须知道系统是否可用，以及是否可以通过设置基线并监视系统以查找趋势来处理当前和预期的需求。

<div>

## <a name="capacity-management"></a>容量管理

容量管理涉及规划、调整大小和控制服务容量，以帮助确保超出 SLA 中指定的最低性能级别。 良好的容量管理有助于确保您能够以合理的成本提供 IT 服务，并且仍能满足在客户端的 Sla 中定义的性能级别。 这些条件可能包括：

  - **系统响应时间**    这是系统执行典型操作所需的度量时间。 示例包括音频/视频服务器角色处理音频/视频流量所需的时间、客户端创建和加入会议所需的时间或在所有观察程序客户端中更新状态所需的时间。

  - **存储容量**    这是存储系统的容量，无论它是内容数据库、备份设备还是本地驱动器。 示例包括每个站点要提供的最大存储空间量以及备份在覆盖之前应存储的时间。

调整容量通常是指确保有足够的物理资源可用，如磁盘空间和网络带宽。 下表列出了与容量相关的问题的典型解决方案。

### <a name="typical-resolutions-for-capacity-related-issues"></a>与容量相关的问题的典型解决方法

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>问题</th>
<th>可能的解决方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>具有较差音频/视频性能的远程用户</p></td>
<td><p>检查以查看 WAN 链路上是否有合适的带宽，以及是否已启用并正确配置了 QoS。 检查 QoE 数据。</p></td>
</tr>
<tr class="even">
<td><p>Lync 环境的整体响应速度较慢。</p></td>
<td><p>运行测试以检查现有的前端服务器是否可以处理负载。 引入新的前端服务器（如果需要）。检查 SQL 数据库响应时间并修复延迟的原因 (例如，改善磁盘 i/o) 。</p></td>
</tr>
</tbody>
</table>


有关更多详细信息的疑难解答在 Lync Server 网络指南中进行了介绍。

容量受系统配置的影响，并取决于物理资源（如网络带宽）。 例如，如果将 Lync 环境配置为在夜间执行完整备份，则必须小心谨慎，以确保最终用户所需的交互式性能影响最小。

容量管理是在可接受的级别内保持系统容量的过程，并解决以下问题：

  - **对要求**     中的更改做出反应必须调整容量要求以考虑系统或组织中的更改。 例如，如果您的环境决定实现企业语音，中介服务器和公共交换电话网络的数量和位置 (PSTN) 网关将非常重要。 如果你将执行会话初始协议 (SIP) 中继或直接 SIP，整体设计将会显著改变，以提供最佳的企业语音性能。

  - **预测未来要求**    某些容量要求随时间的推移改变了预见性。 通过跟踪趋势，可以提前规划升级。 例如，必须监控各个 Lync 网站之间的可用带宽以创建基线。 此基准将允许您预测何时必须向这些链接添加更多的带宽，因为这些远程网站中的用户计数随着时间的推移而增加。

</div>

<div>

## <a name="availability-management"></a>可用性管理

可用性管理是确保所有 IT 服务持续且经济高效地提供客户所需的一致、可靠服务级别的过程。 可用性管理可尽量减少服务损失，并确保在服务丢失时采取适当的措施。 在 Lync 环境中，您可能关心企业语音服务是否可用，用户是否可以加入预定会议，等等。 SLA 定义了可接受的频率和中断长度，并且在系统不可用于规划维护的特定时段内允许。

如果您必须向管理层提供有关系统可用性的报告，或者如果您有财务或其他与缺少可用性目标相关的处罚，则必须记录可用性数据。 即使您没有这种正式要求，也最好至少知道系统在特定时间段内出现故障的频率。 例如，最近12个月内的系统可用性以及从每个故障中恢复所需的时间。 此信息将帮助您衡量和提高您的团队对系统故障做出响应的有效性。 如果有争议，它还可以为你提供有用的信息。

与可用性相关的度量标准如下所示：

  - **可用性**    这通常表示为系统或服务的访问时间与该时间的相对时间。 它通常表示为一个百分比。  (您可能会看到对 "三个九" 或 "五个九" 的引用。 它们指的是99.9% 或99.999% 的可用性。 ) 

  - **可靠性**    这是对系统故障之间的时间的度量，有时表示为平均 (或平均) 次失败之间的时间 (MTBF) 。

  - **修复时间**    这是在发生故障后恢复服务所需的时间，通常表示为 (表示修复 (MTTR) 的平均时间) 时间。

与修复相关的可用性、可靠性和时间如下所示：

**可用性 = (MTBF – MTTR) /MTBF**    例如，如果服务器在六个月的时间段内失败两次，且平均不可用20分钟，则 MTBF 为三个月或90天，而 MTTR 为20分钟。 因此，可用性 = (90 天–20分钟) /90 天 = 99.985%。

可用性管理是确保可用性已最大化并在 Sla 中定义的参数中保持不被充分利用的过程。 可用性管理包括以下过程：

  - **监控**    检查服务不可用的时间和时间。

  - **报告**    应定期向管理、用户和操作团队提供可用性图。 这些报告应重点介绍趋势，并确定正在进行良好工作的领域以及需要注意的领域。 该报告应汇总针对 Sla 中设置的目标的符合性。

  - **改进**    如果可用性不满足在 Sla 中定义的目标或趋势在降低可用性的位置，则可用性管理过程应规划补救步骤。 这应包括与其他负责的团队合作，以突出显示中断的原因，并规划补救措施以防止中断的重复。

容量和可用性指标是非常适合自动化工具和脚本的重复性任务，如 Microsoft System Center Operations Manager (以前的 Microsoft Operations Manager) ，本文档稍后将对此进行讨论。

</div>

<div>

## <a name="see-also"></a>另请参阅


[使用 System Center Operations Manager 监视 Lync Server 2013](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

