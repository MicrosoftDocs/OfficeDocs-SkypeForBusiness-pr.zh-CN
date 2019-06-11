---
title: 使用用户模型的 Lync Server 2013 容量规划
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b7db58e8c6f3e84f95a51ddd393ddca5ec18091
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a>使用用户模型对 Lync Server 2013 进行容量规划

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-01-14_

本部分根据[Lync Server 2013 的用户模式](lync-server-2013-user-models.md)中所述的使用情况, 为网站上的用户数提供了有关在网站上所需的服务器数的指南。

<div>

## <a name="tested-hardware-platform"></a>受测试的硬件平台

本部分中的所有性能结果和部署建议都基于运行下表中所述硬件的服务器上的性能测试。 我们建议你使用类似的硬件。 如果使用性能不足的硬件，可能会遇到功能问题或性能下降。 请注意, 这些硬件建议高于以前版本的 Lync Server。

### <a name="hardware-used-in-performance-testing"></a>性能测试中使用的硬件

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
<p>Lync Server 服务器角色不支持英特尔安腾处理器。</p></td>
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
<p>-或</p></li>
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


</div>

<div>

## <a name="summary-of-results"></a>结果摘要

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
<td><p>带有十二个前端服务器和一台后端服务器的前端池, 或一对后端服务器的镜像对。</p></td>
<td><p>80,000 个同时登录的唯一用户、表示非移动实例的 50% 多点登录 (MPOP) 以及为 Mobility 启用的 40% 的用户，共 152,000 个终结点。</p></td>
</tr>
<tr class="even">
<td><p>A/V 会议</p></td>
<td><p>由前端池提供的 A/V 会议服务支持池中的会议, 其会议最大为250用户, 并且一次仅运行一个这样的大型会议。</p>
<div>

> [!NOTE]  
> 此外, 你可以通过部署一个单独的前端池和两个前端服务器来支持250和1000用户之间的大型会议, 从而托管大型会议。 有关详细信息, 请参阅<A href="lync-server-2013-supporting-large-meetings.md">使用 Lync Server 2013 支持大型会议</A>。


</div></td>
</tr>
<tr class="odd">
<td><p>一台边缘服务器</p></td>
<td><p>12000并发远程用户</p></td>
</tr>
<tr class="even">
<td><p>一个控制器</p></td>
<td><p>12000并发远程用户</p></td>
</tr>
<tr class="odd">
<td><p>监控和存档</p></td>
<td><p>在 Lync Server 2013 中, 监视和存档前端服务现在在每个前端服务器上运行, 而不是在单独的服务器角色上运行。</p>
<p>监控和存档仍需要其自己各自的数据库存储。 如果您还运行 Exchange 2013, 则可以在 Exchange 中保留存档数据, 而不是在专用 SQL 数据库中。</p></td>
</tr>
<tr class="even">
<td><p>一个中介服务器</p></td>
<td><p>使用前端服务器的中介服务器 collocated 在池中的每个前端服务器上运行, 并且应该为池中的用户提供足够的容量。 对于独立的中介服务器, 请参阅本主题后面的 "中介服务器" 一节。</p></td>
</tr>
<tr class="odd">
<td><p>一个标准版服务器</p></td>
<td><p>我们强烈建议, 如果您使用标准版服务器托管用户, 则始终使用两台服务器, 并使用在<a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Lync Server 2013 中规划高可用性和灾难恢复</a>的建议进行配对。 服务器对中的每台服务器最多可承载 2,500 个用户，如果一台服务器出现故障，则另一台服务器在进行故障转移时可支持 5,000 个用户。</p>
<p>如果您的部署包含大量音频或视频流量，当每台服务器用户数超过 2,500 个时，服务器性能可能下降。 在这种情况下, 应考虑添加更多标准版服务器或迁移到 Lync Server 企业版。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a>前端服务器

<div>


> [!NOTE]  
> 此服务器角色不支持延伸池。



</div>

在前端池中, 假设在池中的所有服务器上都启用了超线程, 并且服务器硬件满足[Lync 的服务器硬件平台中的建议, 则为驻留在池中的每个6660用户提供一个前端服务器服务器 2013](lync-server-2013-server-hardware-platforms.md)。 一个前端池中的最大用户数为 80000, 假设在池中的所有服务器上启用了超线程。 如果网站上有超过80000的用户, 则可以部署多个前端池。

当你考虑前端池中的用户数时, 请将驻留在 Survivable 分支装置和 Survivable 分支机构的用户包括在与此前端池关联的分支机构。

活动服务器不可用时，其连接会自动转接给池中的其他服务器。 例如, 如果您有30000用户和5个前端服务器, 则如果一台服务器不可用, 则6000用户的连接需要转移到其他四台服务器。 其余四台服务器每个都有7500用户, 这比推荐的数量更大。

如果您已开始对30000用户使用6个前端服务器, 随后一个服务器变为不可用, 则共5000个用户将被移到其余的五台服务器。 这五台服务器将每台主机6000用户, 该用户位于推荐的范围内。

前端池中的最大用户数是80000。 池中的最大前端服务器数是12。

对于80000用户的前端池, 在[Lync Server 2013 中遵循用户模型](lync-server-2013-user-models.md)的典型部署中, 12 前端服务器的性能就足够了。 为支持灾难恢复故障转移而设计的部署假设最多可以在两个配对的前端池中托管每个用户, 其中每个池都有足够40000的前端服务器以容纳两个池中的用户, 因此一个池需要失败转移到另一个。

由于以下原因, 特定前端池支持的具有良好性能的用户数可能与这些数字不同:

  - 前端服务器的硬件不符合[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的建议。

  - 你的组织的使用情况与用户模型显著不同, 如更大的会议流量。

<div>


> [!IMPORTANT]  
> 在 Lync Server 2013 中, 状态数据库现在托管在前端服务器上, 而不是在 Lync Server 2010 中托管在后端服务器上。 这意味着你的前端服务器的磁盘性能和容量不应受到本部分前面列出的建议以及<A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 的服务器硬件平台</A>中列出的建议, 无论托管的用户数是多少前端服务器。



</div>

下表显示了根据用户模型 (在[Lync Server 2013 中的用户](lync-server-2013-user-models.md)模型中定义) 提供的 IM 和状态的平均带宽。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>每个用户的平均带宽</th>
<th>每个具有6660用户的前端服务器的带宽要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.3 Kpbs</p></td>
<td><p>13 Mbps</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 若要提高前端服务器上归置的 A/V 式会议和中介服务器功能的媒体性能, 应在前端服务器上的网络适配器上启用接收端缩放 (RSS)。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息, 请参阅中的 "Windows Server 2008 中的接收端<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>缩放增强功能"。 有关如何启用 RSS 的详细信息，请参阅网络适配器文档。



</div>

</div>

<div>

## <a name="conferencing-maximums"></a>会议最大值

如果用户模型中有 5% 的用户在一次会议中可能处于会议中, 则80000用户一次可以在会议中拥有4000用户。 这些会议可能混合多种媒体（如一些仅含 IM、一些含有 IM 和音频、一些含有音频/视频）并拥有大量参与者。 实际使用的会议数没有硬性限制, 实际使用情况确定实际性能。 例如, 如果您的组织具有的混合模式会议的数量比用户模型中假定的多, 则您可能需要部署更多的前端服务器或 A/V 会议服务器, 而不是本文档中的建议。 有关用户模型中的假设的详细信息, 请参阅[Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)。

由常规 Lync Server 2013 前端池托管的最大受支持的会议大小也是250参与者。 在进行拥有 250 个用户的会议时，该池同时还可支持其他会议，从而使总数为 5% 的池用户参加并发会议。 例如, 在一个由十二个前端服务器和80000用户组成的池中, 当 250-用户的会议发生时, Lync Server 支持3750其他参与小型会议的用户。

无论驻留在前端池或标准版服务器上的用户数如何, Lync Server 至少支持125在托管250用户会议的同一池或服务器上参与小型会议的其他用户。

若要启用与250和1000用户之间的会议, 您可以设置单独的前端池, 只需托管这些会议。 此前端池不会托管任何用户。 有关详细信息, 请参阅[使用 Lync Server 2013 支持大型会议](lync-server-2013-supporting-large-meetings.md)。

如果您的组织具有的混合模式会议的数量比用户模型中假定的多, 则您可能需要部署比本文档中的建议更多的前端服务器 (最大限制为 12 FEs)。 有关用户模型中的假设的详细信息, 请参阅[Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)。

</div>

<div>

## <a name="edge-server"></a>边缘服务器

<div>


> [!NOTE]  
> 此服务器角色不支持延伸池。



</div>

你应该为将同时访问网站的每个12000远程用户部署一个 Edge 服务器。 至少我们建议使用两个边缘服务器来实现高可用性。 这些建议假定你的 Edge 服务器的硬件满足[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的建议。

当你考虑 Edge 服务器的用户数时, 请将驻留在 Survivable 分支装置和 Survivable 分支机构的用户包括在与此站点上的前端池关联的分支机构。

<div>


> [!NOTE]  
> 若要提高边缘服务器上的 A/V 会议边缘服务的性能, 应在边缘服务器上的网络适配器上启用接收端缩放 (RSS)。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息, 请参阅中的 "Windows Server 2008 中的接收端<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>缩放增强功能"。 有关如何启用 RSS 的详细信息，请参阅网络适配器文档。



</div>

</div>

<div>

## <a name="director"></a>控制器

<div>


> [!NOTE]  
> 此服务器角色不支持延伸池。



</div>

如果你部署 Director 服务器角色, 建议你为将同时访问网站的每个12000远程用户部署一个 Director。 至少我们建议使用两个控制器来实现高可用性。 这些建议假定你的 Edge 服务器的硬件满足[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的建议。

当你考虑控制器的用户数时, 请将驻留在 Survivable 分支机构和 Survivable 分支机构的用户包括在与此站点上的前端池关联的分支机构。

</div>

<div>

## <a name="mediation-server"></a>中介服务器

<div>


> [!NOTE]  
> 此服务器角色不支持延伸池。



</div>

如果您 collocate 中介服务器与前端服务器, 则中介服务器在池中的每个前端服务器上运行, 并且应该为池中的用户提供足够的容量。

如果你部署独立的中介服务器池, 则要部署多少个中介服务器取决于多个因素, 包括用于中介服务器的硬件、你拥有的 VoIP 用户数、每个中介服务器池的网关对等数量控件、通过这些网关的繁忙工时流量以及绕过中介服务器的媒体的通话百分比。

下表提供了一个有关中介服务器的并发调用数的准则, 假定中介服务器的硬件满足[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的要求和超线程处理已启用。 有关中介服务器可伸缩性的详细信息, 请参阅在 Lync server 2013 中[估计 lync server 2013 的语音使用情况和流量](lync-server-2013-estimating-voice-usage-and-traffic.md)以及[中介服务器的部署指南](lync-server-2013-deployment-guidelines-for-mediation-server.md)。

下表假设使用的是[Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)中汇总的用法。

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a>独立中介服务器容量:70% 内部用户, 具有非绕过呼叫容量的 30% 外部用户 (由中介服务器执行的媒体转码)

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
<td><p>双处理器，十六核，<strong>禁用超线程的</strong> 2.26 GHz 超线程 CPU，带 32 GB 内存和 1 个双端口网络适配器卡。</p></td>
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


<div>


> [!NOTE]  
> 尽管使用 32 GB 内存的服务器用于性能测试, 但具有 16 GB 内存的服务器对于独立的中介服务器受支持, 并且足以提供此表中所示的性能。



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a>中介服务器容量 (中介服务器 Collocated 前端服务器) 70% 内部用户、30% 外部用户、非绕过呼叫容量 (由中介服务器执行的媒体处理)

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


<div>


> [!NOTE]  
> 此数字比独立中介服务器的编号小得多, 因为前端服务器除了语音通话所需的转换代码外, 还必须处理其他6600用户的功能和功能。



</div>

<div>


> [!NOTE]  
> 若要提高中介服务器的性能, 应在中介服务器上的网络适配器上启用接收端缩放 (RSS)。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息, 请参阅中的 "Windows Server 2008 中的接收端<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>缩放增强功能"。 有关如何启用 RSS 的详细信息，请参阅网络适配器文档。



</div>

</div>

<div>

## <a name="back-end-server"></a>后端服务器

在 Lync Server 2013 中, 状态数据库位于前端服务器上, 而不是在后端服务器上。 这使得 Lync Server 2013 中的每台后端服务器的要求比前端服务器的硬件要求更简单。 将其与 Lync Server 2010 进行比较, 在这种情况下, 需要将后端服务器用作高达25个磁盘的服务器级别。 但是, 后端服务器的工作负荷仍使您不能满足本部分和[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中列出的硬件建议。

为了提供您的后端服务器的高可用性, 我们建议部署服务器镜像。 有关详细信息, 请参阅[Lync server 2013 中的后端服务器高可用性](lync-server-2013-back-end-server-high-availability.md)。

</div>

<div>

## <a name="monitoring-and-archiving"></a>监控和存档

在 Lync Server 2013 中, 如果你部署监视或存档, 这些服务的前端功能将在前端服务器上运行, 而不是在单独的服务器角色上运行。 监视和存档每个仍使用其自己的数据库存储, 与后端存储分开。 或者, 如果已部署 Exchange 2013, 则可以在 Exchange 中 (而不是在专用的 SQL 应用商店中) 存储即时消息存档数据。

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
<td></td>
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


Microsoft 在其性能测试期间对用于监控和存档的数据库服务器使用了下表中的硬件。 测试收集了两个前端池的数据, 每个池包含80000用户。

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a>监控和存档性能测试中使用的硬件

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
<td><p>utf-16</p></td>
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


</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [估计 Lync Server 2013 的语音使用和流量](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [Lync Server 2013 中的中介服务器部署指南](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

