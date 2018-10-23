---
title: 使用用户模型的 Lync Server 2013 容量规划
TOCTitle: 使用用户模型的容量规划
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49888512
ms.date: 07/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 使用用户模型的 Lync Server 2013 容量规划

 

_**上一次修改主题：** 2016-12-08_

本节根据 [Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)中所述的用法，针对某个站点需要多少台服务器来适应该站点的用户数提供指导。

## 受测试的硬件平台

本节中的所有性能结果和部署建议都基于对运行下表中所述的硬件的服务器的性能测试。建议使用相似的硬件。如果使用功能欠佳的硬件，则可能出现性能问题或遇到功能下降的情况。请注意，这些硬件建议高于以前版本的 Lync Server 的建议。

### 性能测试中使用的硬件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>硬件组件</th>
<th>推荐</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>64 位双处理器、六核、2.26 GHz 或更快</p>
<p>Lync Server 服务器角色不支持 Intel Itanium 处理器。</p></td>
</tr>
<tr class="even">
<td><p>内存</p></td>
<td><p>32 GB</p></td>
</tr>
<tr class="odd">
<td><p>磁盘</p></td>
<td><ul>
<li><p>8 个或 8 个以上具有至少 72 GB 可用磁盘空间的 10,000 RPM 硬盘驱动器。</p>
<p>其中两个磁盘驱动器应使用 RAID 1，另外六个磁盘驱动器应使用 RAID 10。</p>
<p>- 或者 -</p></li>
<li><p>性能类似于 8 个 10,000 RPM 机械磁盘驱动器的固态驱动器 (SSD)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>网络</p></td>
<td><ul>
<li><p>1 个双端口网络适配器，1 Gbps 或更高（建议为 2 Gbps，这要求与一个 MAC 地址和一个 IP 地址结合使用）</p></li>
</ul></td>
</tr>
</tbody>
</table>


## 结果摘要

下表总结了这些建议。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>服务器角色</th>
<th>受支持的最大用户数</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>带有 12 个 前端服务器和 1 个 后端服务器或 1 对镜像的 后端服务器的 前端池。</p></td>
<td><p>80,000 个同时登录的唯一用户、表示非移动实例的 50% 多点登录 (MPOP) 以及为 Mobility 启用的 40% 的用户，共 152,000 个终结点。</p></td>
</tr>
<tr class="even">
<td><p>A/V 会议</p></td>
<td><p>假定最大会议大小为 250 个用户，并且一次只运行一个此类大型会议，那么 前端池提供的 A/V 会议服务支持池的会议。</p>
<div>

> [!NOTE]  
> 此外，您还可以支持用户数在 250 和 1000 个之间的大型会议，方法是部署带有两个 前端服务器的单独 前端池以承载大型会议。有关详细信息，请参阅 <a href="lync-server-2013-supporting-large-meetings.md">使用 Lync Server 2013 支持大型会议</a>。


</div></td>
</tr>
<tr class="odd">
<td><p>一个边缘服务器</p></td>
<td><p>12,000 个并发远程用户</p></td>
</tr>
<tr class="even">
<td><p>一个控制器</p></td>
<td><p>12,000 个并发远程用户</p></td>
</tr>
<tr class="odd">
<td><p>监控和存档</p></td>
<td><p>在 Lync Server 2013 中，监控和存档前端服务器现在在每个 前端服务器上运行，而不是在单独的服务器角色上运行。</p>
<p>监控和存档仍需要其自己各自的数据库存储。如果还运行了 Exchange 2013，则可以将存档数据保存在 Exchange 中，而不是在专用 SQL 数据库中。</p></td>
</tr>
<tr class="even">
<td><p>一个中介服务器</p></td>
<td><p>与前端服务器并置的中介服务器在池中的每个前端服务器中运行，并且应该为池中的用户提供足够的容量。对于单独的中介服务器，请参阅本主题中后面的“中介服务器”一节。</p></td>
</tr>
<tr class="odd">
<td><p>一个 标准版 服务器</p></td>
<td><p>如果您使用 标准版 服务器承载用户，强烈建议始终使用按照<a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">在 Lync Server 2013 中规划高可用性和灾难恢复</a>中的建议进行配对的两台服务器。服务器对中的每台服务器最多可承载 2,500 个用户，如果一台服务器出现故障，则另一台服务器在进行故障转移时可支持 5,000 个用户。</p>
<p>如果您的部署包含大量音频或视频流量，当每台服务器用户数超过 2,500 个时，服务器性能可能下降。在这种情况下，应考虑添加更多的 标准版 服务器或移动到 Lync Server企业版。</p></td>
</tr>
</tbody>
</table>


## 前端服务器

> [!NOTE]  
> 此服务器角色不支持扩展池。



在 前端池中，假如对该池中的所有用户都启用了该超线程，并且服务器硬件符合 [适用于 Lync Server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的建议，则应为驻留在该池中的每 6,660 个用户部署一台 前端服务器。假如对一个 前端池中的所有用户都启用了该超线程，则该池中的最大用户数为 80,000。如果站点上的用户数超过 80,000，则可部署多个 前端池。

在计算 前端池中的用户数时，请将分支机构中与此 前端池关联的 Survivable Branch Appliance 和 Survivable Branch Server 上驻留的用户包括在内。

活动服务器不可用时，其连接会自动转接给池中的其他服务器。例如，如果您拥有 30,000 个用户和五台 前端服务器，则在一台服务器不可用时，需要将 6000 个用户的连接转接到其他四台服务器。其余四台服务器中的每台服务器将拥有 7500 个用户，此数量大于推荐的数量。

如果您一开始为 30,000 个用户提供了六台 前端服务器，但后来有一台服务器变得不可用，则共有 5000 个用户会移动到其余五台服务器。这五台服务器将各承载 6000 个用户，这没有超出推荐的范围。

前端池的最大用户数是 80,000。池中 前端服务器的最大数量是 12。

对于具有 80,000 个用户的 前端池，在按照 [Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)进行的典型部署中，12 台 前端服务器可满足性能的需要。专用于支持灾难恢复故障转移的部署假定两个配对的 前端池的每个前端池最多可承载 40,000 个用户，配对的池中的每个池都具有足以容纳这两个池中的用户的 前端服务器（如果需要将一个池故障转移到另一个池）。

特定 前端池支持的具有良好性能的用户的数量应该不同于这些数量，原因如下：

  - 前端服务器的硬件与 [适用于 Lync Server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的建议不符。

  - 组织的用法与用户模型明显不同，如明显具有更多的会议流量。

> [!IMPORTANT]  
> 在 Lync Server 2013 中，状态数据库现在承载于 前端服务器上，而在 Lync Server 2010 中，该数据库承载于 后端服务器上，两者不同。这意味着无论 前端服务器承载的用户数如何， 前端服务器的磁盘性能和容量都不应低于本主题前面列出的建议和 <a href="lync-server-2013-server-hardware-platforms.md">适用于 Lync Server 2013 的服务器硬件平台</a>中的建议。


鉴于如 [Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)中所定义的用户模型，下表显示了 IM 和状态的平均带宽。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>每个用户的平均带宽</th>
<th>每个拥有 6,660 个用户的 前端服务器的带宽要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.3 Kpbs</p></td>
<td><p>13 Mbps</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> 要提高前端服务器上的并置 A/V 会议和中介服务器功能的媒体性能，应在前端服务器的网络适配器上启用接收方缩放 (RSS)。通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。有关详细信息，请参阅“Windows Server 2008 中的接收方伸缩改进”，网址为 <a href="http://go.microsoft.com/fwlink/?linkid=268731" class="uri">http://go.microsoft.com/fwlink/?linkid=268731</a>。有关如何启用 RSS 的详细信息，请参阅网络适配器文档。



## 会议最大值

假定用户模型为池中 5% 的用户可能会在任何时候参加会议，则拥有 80,000 个用户的池一次可能会有大约 4,000 个用户参加会议。这些会议可能混合多种媒体（如一些仅含 IM、一些含有 IM 和音频、一些含有音频/视频）并拥有大量参与者。允许的实际会议数没有硬限制，但实际用法决定了实际性能。例如，如果组织中具有的混合模式会议的数量多于用户模型中假定的混合模式会议的数量，则可能需要部署的 前端服务器或 A/V 会议服务器的数量会多于本文档中推荐的数量。有关用户模型中的假定的详细信息，请参阅 [Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)。

由常规 Lync Server 2013前端池（也承载用户）承载的支持的最大会议大小是 250 个参与者。在进行拥有 250 个用户的会议时，该池同时还可支持其他会议，从而使总数为 5% 的池用户参加并发会议。例如，在拥有 12 台 前端服务器和 80,000 个用户的池中，当进行拥有 250 个用户的会议时， Lync Server 还支持另外 3,750 个用户参加规模较小的会议。

无论驻留在 前端池或 Standard Edition Server 上的用户数是多少， Lync Server 都至少支持另外 125 个用户参加同一池中或承载拥有 250 个用户的会议的服务器上的规模较小的会议。

若要启用具有 250 至 1000 个用户的会议，您可以设置单独的 前端池来专门承载这些会议。此 前端池不会承载任何用户。有关详细信息，请参阅 [使用 Lync Server 2013 支持大型会议](lync-server-2013-supporting-large-meetings.md)。

如果组织中具有的混合模式会议的数量多于用户模型中假定的混合模式会议的数量，则可能需要部署的 前端服务器的数量会多于本文档中推荐的数量（最多达到 12 个 FE 的限制）。有关用户模型中的假定的详细信息，请参阅 [Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)。

## 边缘服务器

> [!NOTE]  
> 此服务器角色不支持扩展池。



应为将远程访问站点的每 12,000 个用户部署一台 边缘服务器。为实现高可用性，建议至少部署两台 边缘服务器。这些建议假定 边缘服务器的硬件符合 [适用于 Lync Server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的建议。

在计算 边缘服务器的用户数时，请将分支机构中与此站点的 前端池关联的 Survivable Branch Appliance 和 Survivable Branch Server 上驻留的用户包括在内。

> [!NOTE]  
> 要提高边缘服务器上的 A/V 会议边缘服务的性能，应在边缘服务器的网络适配器上启用接收方缩放 (RSS)。通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。有关详细信息，请参阅“Windows Server 2008 中的接收方伸缩改进”，网址为 <a href="http://go.microsoft.com/fwlink/?linkid=268731" class="uri">http://go.microsoft.com/fwlink/?linkid=268731</a>。有关如何启用 RSS 的详细信息，请参阅网络适配器文档。



## 控制器

> [!NOTE]  
> 此服务器角色不支持扩展池。



如果部署了 控制器服务器角色，则建议为将并行访问站点的每 12,000 个远程用户部署一台 控制器。为实现高可用性，建议至少部署两台 控制器。这些建议假定 边缘服务器的硬件符合 [适用于 Lync Server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的建议。

在计算 控制器的用户数时，请将分支机构中与此站点的 前端池关联的 Survivable Branch Appliance 和 Survivable Branch Server 上驻留的用户包括在内。

## 中介服务器

> [!NOTE]  
> 此服务器角色不支持扩展池。



如果将 中介服务器与 前端服务器并置， 中介服务器将在池中的每台 前端服务器上运行，并且应为池中的用户提供足够的容量。

如果部署了独立的 中介服务器池，那么要部署多少台 中介服务器取决于许多因素，包括用于 中介服务器的硬件、所拥有的 VoIP 用户数、每个 中介服务器池控制的对等网关数、通过这些网关的忙碌时间流量和使用绕过 中介服务器的媒体发出的呼叫的百分比。

下表针对 中介服务器可以处理的并发呼叫数提供指南，前提是 中介服务器的硬件符合 [适用于 Lync Server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的要求且启用了超线程。有关 中介服务器可伸缩性的详细信息，请参阅 [估计 Lync Server 2013 的语音使用和流量](lync-server-2013-estimating-voice-usage-and-traffic.md)和 [Lync Server 2013 中介服务器部署准则](lync-server-2013-deployment-guidelines-for-mediation-server.md)。

下表中的所有内容都将用法假定为 [Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)中总结的用法。

### 独立的 中介服务器容量：70% 内部用户，30% 外部用户，带有无绕过呼叫容量（由 中介服务器执行的媒体转码）

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>服务器硬件</th>
<th>最大呼叫数</th>
<th>最大 T1 线路数</th>
<th>最大 E1 线路数</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>双处理器，十六核， <strong>禁用超线程的</strong> 2.26 GHz 超线程 CPU，带 32 GB 内存和 1 个双端口网络适配器卡。</p></td>
<td><p>1100</p></td>
<td><p>46</p></td>
<td><p>35</p></td>
</tr>
<tr class="even">
<td><p>双处理器，十六核，2.26 GHz 超线程 CPU，带 32 GB 内存和 1 个双端口网络适配器卡。</p></td>
<td><p>1500</p></td>
<td><p>63</p></td>
<td><p>47</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> 虽然性能测试使用的是内存为 32 GB 的服务器，但内存为 16 GB 的服务器也可用作独立 中介服务器，并且足以提供此表中显示的性能。



### 中介服务器容量（与 前端服务器并置的 中介服务器）70% 内部用户，30% 外部用户，无绕过呼叫容量（由 中介服务器执行的媒体处理）

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>服务器硬件</th>
<th>最大呼叫数</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>双处理器，十六核，2.26 GHz 超线程 CPU，带 32 GB 内存和 2 个 1GB 网络适配器卡。</p></td>
<td><p>150</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> 此数量远小于独立的 中介服务器的数量，因为除语音呼叫所需的转码之外， 前端服务器还必须处理驻留在其上的 6600 个用户的其他功能。



> [!NOTE]  
> 要提高中介服务器的性能，应在中介服务器的网络适配器上启用接收方缩放 (RSS)。通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。有关详细信息，请参阅“Windows Server 2008 中的接收方伸缩改进”，网址为 <a href="http://go.microsoft.com/fwlink/?linkid=268731" class="uri">http://go.microsoft.com/fwlink/?linkid=268731</a>。有关如何启用 RSS 的详细信息，请参阅网络适配器文档。



## 后端服务器

在 Lync Server 2013 中，状态数据库位于 前端服务器上，而不是 后端服务器上。这极大简化了 Lync Server 2013 中的每个 后端服务器的要求（相当于 前端服务器的硬件要求）。将此与 Lync Server 2010 对比，后者的 后端服务器必须是级别高很多的服务器（具有 25 个磁盘）。但是， 后端服务器的工作负荷仍是如此，以至于您不应与本节的前面所列的硬件建议和 [适用于 Lync Server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的建议不符。

要提高 后端服务器的高可用性，建议部署服务器镜像。有关更多信息，请参阅 [Lync Server 2013 中的后端服务器高可用性](lync-server-2013-back-end-server-high-availability.md)。

## 监控和存档

在 Lync Server 2013 中，如果部署了监控和存档，这些服务的前端功能将在 前端服务器上运行，而不是在单独的服务器角色上运行。监控和存档仍使用其各自的数据库存储（独立于后端存储）。或者，如果您部署了 Exchange 2013，则可以在 Exchange 中（而非专用 SQL 存储中）存储即时消息存档数据。

下表说明了每个用户每天监控和存档数据所需的数据库存储的大致数量。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><strong>CDR（监控）</strong></p></td>
<td><p><strong>QoE（监控）</strong></p></td>
<td><p><strong>存档</strong></p></td>
</tr>
<tr class="even">
<td><p>每个用户每天所需的磁盘空间</p></td>
<td><p>49 KB</p></td>
<td><p>28 KB</p></td>
<td><p>57 KB</p></td>
</tr>
</tbody>
</table>


Microsoft 在其性能测试期间对用于监控和存档的数据库服务器使用了下表中的硬件。该测试收集了两个 前端池的数据，每个前端池包含 80,000 个用户。

### 监控和存档性能测试中使用的硬件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>硬件组件</th>
<th>推荐</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>64 位双处理器、六核、2.26 GHz 或更快</p></td>
</tr>
<tr class="even">
<td><p>内存</p></td>
<td><p>48 GB</p></td>
</tr>
<tr class="odd">
<td><p>磁盘</p></td>
<td><p>25 个 10,000 RPM 硬盘驱动器，每个磁盘具有 300 GB 的内存，配置如下</p>
<h3 id="section-3"> </h3>
<div>
<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>驱动器</strong></p></td>
<td><p><strong>RAID 配置</strong></p></td>
<td><p><strong>磁盘数</strong></p></td>
</tr>
<tr class="even">
<td><p>单个驱动器上的 CDR、QoE 和存档数据库数据文件</p></td>
<td><p>1+0</p></td>
<td><p>16</p></td>
</tr>
<tr class="odd">
<td><p>CDR 数据库日志文件</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>QoE 数据库日志文件</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>存档数据库日志文件</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p>网络</p></td>
<td><ul>
<li><p>1 个双端口网络适配器，1 Gbps 或更高（建议为 2 Gbps，这要求与一个 MAC 地址和一个 IP 地址结合使用）</p></li>
</ul></td>
</tr>
</tbody>
</table>


## 本节内容

  - [估计 Lync Server 2013 的语音使用和流量](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [Lync Server 2013 中介服务器部署准则](lync-server-2013-deployment-guidelines-for-mediation-server.md)

