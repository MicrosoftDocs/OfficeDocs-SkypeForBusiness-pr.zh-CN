---
title: Lync Server 2013 中的运行状况配置
TOCTitle: Lync Server 2013 中的运行状况配置
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205234(v=OCS.15)
ms:contentKeyID: 49314119
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的运行状况配置

 

_**上一次修改主题：** 2015-03-09_

在各个网站、Microsoft 知识库文章和 Lync Server 资源工具包之间，运行 Lync Server 时遇到问题的管理员从不缺乏解决这些问题的方法。

很明显，无法保证您永远不会遇到 Lync Server 2013 方面的问题，因为 Lync Server 可能会受到产品本身无法控制的很多方面的影响，如网络崩溃和硬件故障。通过实施运行状况监控，管理员可以先确认潜在的问题，然后再进入实际问题。例如，管理员可以使用 Lync Server 监控来确认趋势和倾向。例如，在音频/视频会议数目方面的稳定增长可能暗示着在系统超载之前需要添加容量。

类似地，管理员可以使用 System Center Operations Manager 执行诸如在发生指定事件时发出实时警报之类的事情，并运行主动测试系统的综合事务。Lync Server 中使用综合事务来验证用户是否能够成功完成常见任务，如登录到系统、交换即时消息，或者拨打位于公用电话交换网 (PSTN) 中的电话。例如，定期运行这些测试会针对用户登录到 Lync Server 的潜在问题向您发出警报，并在支持团队收到无法进行连接的用户打来的大量电话之前为您提供更正问题的机会。通过使用 System Center Operations Manager 运行这些综合事务，管理员可以每天连续 24 小时定期监控 Lync Server 的部署情况，而无需执行除对可能发出的任何警报作出响应以外的一些事情。

> [!NOTE]  
> 针对 Lync Server 2013，System Center Operations Manager 的管理包还能够检测可能对 Lync Server 产生负面影响的“外部”问题。例如，如果 Internet Information Services (IIS) 脱机，Lync Server 计算机上的系统资源降低到指定的数量以下，或者 Lync Server 计算机遇到硬件故障，则可以通知给管理员。



Lync Server 2013 中的运行状况配置是围绕 System Center Operations Manager 和 Lync Server 管理包的使用情况构建的。这些管理包包括许多新的功能和增强功能，其中包括：

  - **任何位置的方案可用性。** Lync Server 2010 管理包引入了利用综合事务监控最终用户方案可用性的概念。在 Lync Server 2013 中，这些代理具有更多的综合事务，并且可以从企业内部的各个位置、从企业外部的远程地理位置、针对分支办公室设备以及针对 Lync Server 2010 部署加以运行，以增加旧的边缘部署的范围。

  - **综合事务日志。** 当综合事务失败时，管理员可以访问 HTML 日志以帮助确定什么失败了。这包括了解哪个操作失败、每个操作的延迟、用来运行测试的命令行，以及所遇到的错误。

  - **增加呼叫可靠性范围。** Lync Server 2010 管理包引入了呼叫可靠性警报，以检测影响最终用户音频呼叫的严重连接问题。Lync Server 2013 管理包增加了对等即时消息 (IM) 和其他基本会议功能的范围，以最大程度上扩大范围，同时减少噪音。

  - **依赖关系监控。** Lync Server 方案可能会因各种外部因素（如 IIS 脱机、有限的 CPU 和内存资源和磁盘问题）而发生失败。新的管理包会检查多个重要的依赖关系，以确保管理员注意到它们的影响。

  - **增强的报告。** 可帮助管理员估计方案可用性、规划容量并查看哪些组件遇到最多问题的一组报告。

管理包还包括可帮助检测和诊断并允许实时查看 Lync Server 部署运行状况的各种功能。这些功能在下表中列出。

### 管理包功能

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
<td><p>可以从各个位置运行以确保最终用户方案（如登录、状态、IM 和会议）随时可供最终用户使用的 Windows PowerShell cmdlet。</p></td>
</tr>
<tr class="even">
<td><p>呼叫可靠性警报</p></td>
<td><p>呼叫详细记录 (CDR) 的数据库查询。前端服务器写入这些记录以反映最终用户是否能够连接到呼叫或为何终止呼叫。这些查询会产生警报，指示大量的最终用户面向对等呼叫或基本会议功能何时遇到连接问题。</p></td>
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
<td><p>有多种外部原因可能导致失败。管理包现在监控并收集可能指示严重问题的一些重要外部依赖关系的数据，包括 IIS 可用性、服务器和处理程序的 CPU 和内存使用情况，以及磁盘指标。</p></td>
</tr>
</tbody>
</table>


已将系统所发出的警报分为三种一般类别：

  - **高优先级警报。** 这些警报指出将导致大型用户组的服务中断的条件。例如，单台机器上的组件故障并非高优先级警报，因为 Lync Server 2013 具有内置的高可用性功能。而高优先级警报代表严重性程度达到足以“在夜晚唤醒管理员”的问题。综合事务和脱机服务（例如，音频/视频会议）所检测到的中断会被鉴定为高优先级警报。

  - **中优先级警报。** 这些警报指出影响用户子集或指示呼叫质量下降的条件。这包括诸如组件故障、呼叫建立延迟或呼叫中音频质量下降之类的问题。此类别中的警报是全状态的并指出问题的当前状态。例如，假设您的呼叫建立次数超出警报阈值。如果呼叫建立次数返回正常状态，则将在 System Center Operations Manager 中对这些警报进行自动解析。对这些警报的期望值是管理员将在同一工作日对它们进行查看。

  - **其他警报。** 这些是指来自组件且可能影响特定用户或用户子集的警报。例如，也许通讯簿服务无法分析给定用户的 Active Directory 条目。对这些警报的期望值是管理员在有可用时间时对它们进行处理。

## 本节内容

  - [配置 Lync Server 以使用 System Center Operations Manager](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [使用综合事务的富日志记录](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [将 Microsoft SQL Server 2008 R2 用作 System Center Operations Manager 数据库](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

