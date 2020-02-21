---
title: Lync Server 2013： Lync Server 中的运行状况配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea97a57deba77e0bc5b7f2a77a973bb1fb8c21b7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a>Lync Server 2013 中的运行状况配置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

在各种网站、Microsoft 知识库文章和 Lync Server 资源工具包工具之间，在运行 Lync Server 时遇到问题的管理员永远不会从解决这些问题的方法开始。

显然，无法保证 Lync Server 2013 不会遇到问题，因为 Lync Server 可能会受到许多功能（如网络故障和硬件故障）的影响，产品本身无法控制这些内容。 通过实施运行状况监控，管理员可以先确认潜在的问题，然后再进入实际问题。 例如，管理员可以使用 Lync Server monitoring 识别趋势和 tendencies。 例如，在音频/视频会议数目方面的稳定增长可能暗示着在系统超载之前需要添加容量。

与此类似，管理员可以使用 System Center Operations Manager 执行在指定事件发生时发出实时警报等操作，并运行主动测试系统的综合事务。 在 Lync Server 中使用综合事务，以验证用户是否能够成功完成常见任务，如登录系统、交换即时消息或呼叫位于公用电话交换网（PSTN）的电话。 例如，定期运行这些测试可能会提醒您登录到 Lync Server 时遇到的潜在问题，并使您有机会在您的支持团队耗尽来自用户无法建立连接的呼叫之前解决此问题。 通过使用 System Center Operations Manager 运行这些综合事务，管理员可以定期监视其每日每天24小时的 Lync Server 部署，而无需执行任何其他操作，除了响应可能发出。

<div>


> [!NOTE]  
> 对于 Lync Server 2013，System Center Operations Manager 管理包还能够检测可能对 Lync Server 产生负面影响的 "外部" 问题。 例如，当 Internet 信息服务（IIS）脱机、Lync Server 计算机上的系统资源低于指定的数量或 Lync Server 计算机遇到硬件故障时，可以通知管理员。



</div>

Lync Server 2013 中的运行状况配置是围绕 System Center Operations Manager 和 Lync Server 管理包的使用而构建的。 这些管理包包括许多新的功能和增强功能，其中包括：

  - **任何位置的方案可用性。** Lync Server 2010 管理包引入了使用综合事务监视最终用户方案可用性的概念。 在 Lync Server 2013 中，这些代理具有更多的综合事务，可以从企业内部的不同位置运行，从企业外部的远程地理位置，针对分支机构设备和 Lync Server 2010。用于将覆盖范围添加到旧版边缘部署的部署。

  - **综合事务日志。** 当综合事务失败时，管理员可以访问 HTML 日志以帮助确定什么失败了。 这包括了解哪个操作失败、每个操作的延迟、用来运行测试的命令行，以及所遇到的错误。

  - **增加呼叫可靠性范围。** Lync Server 2010 管理包引入了呼叫可靠性警报，以检测影响最终用户的音频呼叫的严重连接问题。 Lync Server 2013 管理包为对等即时消息（IM）和其他基本会议功能添加了覆盖范围，以最大限度地减少噪音。

  - **依赖关系监控。** 由于各种外部因素（如 IIS 处于脱机状态、有限的 CPU 和内存资源以及磁盘问题），Lync Server 方案可能会失败。 新的管理包会检查多个重要的依赖关系，以确保管理员注意到它们的影响。

  - **增强的报告。** 可帮助管理员估计方案可用性、规划容量并查看哪些组件遇到最多问题的一组报告。

管理包中还包含多种功能，可帮助检测和诊断您的 Lync Server 部署的运行状况的实时可见性。 这些功能在下表中列出。

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
<td><p>可从不同位置运行的 Windows PowerShell cmdlet，以确保最终用户随时可以使用登录、状态、即时消息和会议等最终用户方案。</p></td>
</tr>
<tr class="even">
<td><p>呼叫可靠性警报</p></td>
<td><p>呼叫详细记录 (CDR) 的数据库查询。 前端服务器写入这些记录，以反映最终用户能否连接到呼叫或终止呼叫的原因。 这些查询会产生警报，指示大量的最终用户面向对等呼叫或基本会议功能何时遇到连接问题。</p></td>
</tr>
<tr class="odd">
<td><p>媒体质量警报</p></td>
<td><p>查看每个呼叫结束时由客户端发布的体验质量 (QoE) 报告的数据库查询。这些查询会产生警报，以准确找出用户可能在呼叫和会议期间遇到较差的媒体质量的方案。数据构建在诸如数据包延迟和丢失之类的关键指标，以及已知直接促成呼叫质量的指标的基础之上。</p></td>
</tr>
<tr class="even">
<td><p>组件运行状况</p></td>
<td><p>个别服务器组件会使用事件日志和性能计数器发出警报。这些警报指出可能会对一个或多个最终用户方案造成负面影响的失败条件。这些警报还可以指出各种其他失败条件，包括服务未运行、很高的失败率、很高的消息延迟或连接问题。</p></td>
</tr>
<tr class="odd">
<td><p>依赖关系运行状况</p></td>
<td><p>有多种外部原因可能导致失败。 管理包现在监控并收集可能指示严重问题的一些重要外部依赖关系的数据，包括 IIS 可用性、服务器和处理程序的 CPU 和内存使用情况，以及磁盘指标。</p></td>
</tr>
</tbody>
</table>


已将系统所发出的警报分为三种一般类别：

  - **高优先级警报。** 这些警报指出将导致大型用户组的服务中断的条件。 例如，一台计算机上的组件故障不是高优先级的警报，因为 Lync Server 2013 具有内置的高可用性功能。 而高优先级警报代表严重性程度达到足以“在夜晚唤醒管理员”的问题。 综合事务和脱机服务（例如，音频/视频会议）所检测到的中断会被鉴定为高优先级警报。

  - **中等优先级警报。**。 这些警报表示影响用户子集或指示呼叫质量降级的条件。 其中包括组件故障、呼叫中的延迟或呼叫中的音频质量下降等问题。 此类别中的警报是有状态的，指示问题的当前状态。 例如，假设您的呼叫建立时间超过了警报阈值。 如果呼叫建立时间返回到正常，则会在 System Center Operations Manager 中自动解决这些警报。 这些警报的预期是管理员将在同一工作日查看。

  - **其他警报。** 这些是指来自组件且可能影响特定用户或用户子集的警报。 例如，也许通讯簿服务无法分析给定用户的 Active Directory 条目。 对这些警报的期望值是管理员在有可用时间时对它们进行处理。

<div>

## <a name="in-this-section"></a>本节内容

  - [配置 Lync Server 2013 以使用 System Center Operations Manager](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [在 Lync Server 2013 中对综合事务使用丰富日志记录](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [使用 Microsoft SQL Server 2008 R2 作为 Lync Server 2013 的 System Center Operations Manager 数据库](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

