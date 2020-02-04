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
ms.openlocfilehash: 169c2e383a1799f5f3ab7ca810de32f86350e51b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-and-availability-management-in-lync-server-2013"></a>Lync Server 2013 中的容量和可用性管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-08-18_

容量管理和可用性管理的目的是衡量和控制系统性能。 我们建议你实施容量管理和可用性管理过程，以便你可以测量和控制系统性能。 你必须知道系统是否可用，以及它是否可以通过设置基线并监视系统以查找趋势来处理当前和所投影的请求。

<div>

## <a name="capacity-management"></a>容量管理

容量管理涉及规划、调整大小和控制服务容量，以帮助确保超过你的 SLA 中指定的最低性能级别。 良好的容量管理有助于确保你能够以合理的成本提供 IT 服务，并且仍能满足你在你的 Sla 中定义的性能级别和客户端。 这些条件可以包括以下内容：

  - **系统响应时间**   这是系统执行典型操作所需的测量时间。 示例包括音频/视频服务器角色处理音频/视频流量所需的时间、客户创建和加入会议所需的时间或在所有观察者客户端中更新状态所需的时间。

  - **存储容量**   这是存储系统的容量，无论它是内容数据库、备份设备还是本地驱动器。 示例包括每个网站提供的最大存储空间量以及备份在覆盖之前应存储的时间。

调整容量通常是指确保有足够的物理资源可用，例如磁盘空间和网络带宽。 下表列出了与容量相关的问题的典型分辨率。

### <a name="typical-resolutions-for-capacity-related-issues"></a>与容量相关的问题的典型解决方案

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
<td><p>音频/视频性能较差的远程用户</p></td>
<td><p>检查以查看 WAN 链接是否提供合适的带宽，以及是否已启用和正确配置 QoS。 检查 QoE 数据。</p></td>
</tr>
<tr class="even">
<td><p>Lync 环境的整体响应速度较慢。</p></td>
<td><p>运行测试以检查现有前端服务器是否可以处理负载。 引入新的前端服务器（如果需要）。检查 SQL 数据库响应时间并修复延迟的原因（例如，改善磁盘输入/输出）。</p></td>
</tr>
</tbody>
</table>


有关更多详细信息的疑难解答将在 Lync Server 网络指南中介绍。

容量受系统配置的影响，取决于物理资源（如网络带宽）。 例如，如果将 Lync 环境配置为在夜间执行完整备份，则必须小心，以帮助确保对最终用户体验的交互式性能的影响最小。

容量管理是在可接受的级别内保持系统容量并解决以下问题的过程：

  - **对需求**   产能要求做出的更改必须进行调整，以考虑系统或组织中的更改。 例如，如果你的环境决定实现企业语音，则中介服务器和公共交换电话网络（PSTN）网关的数量和位置将非常重要。 如果你将执行会话初始协议（SIP）中继或直接 SIP，整体设计将显著改变，以提供最佳的企业语音性能。

  - **预测未来需求**   某些容量要求随时间的推移而变化。 通过跟踪趋势，你可以提前规划升级。 例如，必须监视各种 Lync 网站之间的可用带宽才能创建基线。 此基线将允许你预测何时必须为这些链接添加更多带宽，因为这些远程网站中的用户计数会随着时间的增加而增加。

</div>

<div>

## <a name="availability-management"></a>可用性管理

可用性管理是确保任何 IT 服务一致、经济高效地提供客户所需的一致、可靠服务级别的过程。 可用性管理处理的服务损失最小，并确保在服务丢失时采取相应措施。 在 Lync 环境中，你可能关心企业语音服务是否可用、用户是否可以加入计划的会议等。 SLA 定义了可接受的频率和中断长度，并允许在系统不可用于计划维护时获得特定时间段。

如果你必须向管理层提供有关系统可用性的报表，或者如果你有财务或与缺少可用性目标相关的其他处罚，则必须记录可用性数据。 即使你没有这种正式的要求，也最好至少知道系统在特定时间段内失败的频率。 例如，过去12个月中的系统可用性以及从每次失败恢复所需的时间。 此信息将帮助你衡量和改进你的团队对系统故障做出响应的有效性。 如果存在争议，它还可以提供有用的信息。

与可用性相关的度量标准如下所示：

  - **可用性**   通常表示为系统或服务可以访问的时间，与它处于关闭状态的时间相比较。 它通常表示为百分比。 （你可能会看到 "三个 9" 或 "五个 9" 的引用。 这是99.9% 或99.999% 的可用容量。）

  - **可靠性**   这是一个系统故障之间的时间度量，有时在两次失败之间（MTBF）表示为平均值（或平均）时间。

  - **修复时间这**   是在发生故障后恢复服务所用的时间，通常表示为平均修复时间（即 "MTTR"）。

可用性、可靠性和修复时间相关，如下所示：

**可用性 = （MTBF-MTTR）/MTBF**   例如，如果服务器在六个月的时间段内失败两次，并且平均不超过20分钟，则 MTBF 为3个月或90天，并且 MTTR 为20分钟。 因此，可用性 = （90天-20 分钟）/90 days = 99.985%。

可用性管理是确保可用性最大化并保留在 Sla 中定义的参数中的过程。 可用性管理包括以下过程：

  - **监视**   检查服务不可用的时间和时间。

  - **报告**   可用性数据应定期提供给管理层、用户和操作团队。 这些报表应突出显示趋势并确定正在进行良好工作的区域以及需要注意的区域。 该报告应总结 Sla 中设置的目标合规性。

  - **改进**   如果可用性不满足在 sla 中定义的目标或趋势在降低可用性的位置，则可用性管理过程应计划补救步骤。 这应包括与其他责任团队协作，以突出显示中断的原因并计划补救措施以防止中断的重复。

容量和可用性度量是重复性任务，非常适合于自动工具和脚本，如 Microsoft System Center Operations Manager （以前称为 Microsoft Operations Manager），本文档后面部分将进行讨论。

</div>

<div>

## <a name="see-also"></a>另请参阅


[通过 System Center Operations Manager 监视 Lync Server 2013](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

