---
title: 使用用户模型的 Lync Server 2013 容量规划
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d315de4f8b18a5ecbeabe7ba29231c70ff893e8a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508139"
---
# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a>使用用户模型对 Lync Server 2013 进行容量规划

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-01-14_

本节根据在 [Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)中所述的使用情况，为网站上的用户数提供有关网站上所需的服务器数量的指南。

<div>

## <a name="tested-hardware-platform"></a>测试的硬件平台

本节中的所有性能结果和部署建议都基于运行下表中所述的硬件的服务器上的性能测试。 建议使用类似的硬件。 如果使用性能不足的硬件，可能会遇到功能问题或性能下降。 请注意，这些硬件建议高于早期版本的 Lync Server。

### <a name="hardware-used-in-performance-testing"></a>性能测试中使用的硬件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>硬件组件</th>
<th>建议</th>
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
<li><p>8个或更多的 10000 RPM 硬盘，至少有 72 GB 的可用磁盘空间。</p>
<p>其中两个磁盘驱动器应使用 RAID 1，另外六个磁盘驱动器应使用 RAID 10。</p>
<p>- 和</p></li>
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
<td><p>前端池具有十二个前端服务器和一台后端服务器或一对后端服务器。</p></td>
<td><p>80000唯一用户同时登录，加上50% 的状态 (MPOP) 代表非移动实例，加上40% 的用户为移动计算总152000终结点而启用的用户。</p></td>
</tr>
<tr class="even">
<td><p>A/V 会议</p></td>
<td><p>前端池提供的 A/V 会议服务支持池的会议，假定最大会议大小为250个用户，并且一次仅运行一个这样的大型会议。</p>
<div>

> [!NOTE]  
> 此外，可以通过部署单独的前端池和两台前端服务器来托管大型会议，从而支持250和1000用户之间的大型会议。 有关详细信息，请参阅 <A href="lync-server-2013-supporting-large-meetings.md">使用 Lync Server 2013 支持大型会议</A>。


</div></td>
</tr>
<tr class="odd">
<td><p>一台边缘服务器</p></td>
<td><p>12000并发远程用户</p></td>
</tr>
<tr class="even">
<td><p>一台控制器</p></td>
<td><p>12000并发远程用户</p></td>
</tr>
<tr class="odd">
<td><p>监控和存档</p></td>
<td><p>在 Lync Server 2013 中，监视和存档前端服务现在在每台前端服务器上运行，而不是在单独的服务器角色上运行。</p>
<p>监视和存档每个仍需要自己的数据库存储。 如果还运行 Exchange 2013，则可以将存档数据保存在 Exchange 中，而不是保存在专用 SQL 数据库中。</p></td>
</tr>
<tr class="even">
<td><p>一台中介服务器</p></td>
<td><p>使用前端服务器的中介服务器并置在池中的每台前端服务器上运行，并且应为池中的用户提供足够的容量。 对于独立的中介服务器，请参阅本主题后面的 "中介服务器" 一节。</p></td>
</tr>
<tr class="odd">
<td><p>一台 Standard Edition Server</p></td>
<td><p>强烈建议如果您使用 Standard Edition 服务器来托管用户，则始终使用两台服务器，并使用在 <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Lync Server 2013 中规划高可用性和灾难恢复中</a>的建议进行配对。 对中的每台服务器都可以承载多达2500个用户，如果一台服务器发生故障，则其他服务器可以在故障转移方案中支持5000用户。</p>
<p>如果您的部署包括大量的音频或视频流量，则服务器性能可能会受到每台服务器超过2500个用户的影响。 在这种情况下，应考虑添加更多 Standard Edition 服务器或移动到 Lync Server Enterprise Edition。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a>Front End Server － 前端服务器

<div>


> [!NOTE]  
> 此服务器角色不支持延伸池。



</div>

在前端池中，应为驻留在池中的每个6660用户安装一个前端服务器，假设池中的所有服务器上都启用了超线程，并且服务器硬件满足 [Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的建议。 一个前端池中的最大用户数为80000，假定在池中的所有服务器上启用了超线程。 如果站点上的用户数超过 80,000，则可部署多个前端池。

在计算前端池中的用户数时，请将分支机构中与此前端池关联的 Survivable Branch Appliance 和 Survivable Branch Server 上驻留的用户包括在内。

活动服务器不可用时，其连接会自动转接给池中的其他服务器。 例如，如果您有30000个用户和五台前端服务器，那么，如果一台服务器不可用，则需要将6000用户的连接转移到其他四台服务器。 其余四台服务器每个都有7500个用户，这比建议的数量更大。

如果您已开始为30000用户使用6台前端服务器，并且后来的服务器变得不可用，则总共5000个用户将移至其余的5台服务器。 这五台服务器将每台主机6000用户，在建议的范围内。

前端池的最大用户数是 80,000。 池中的最大前端服务器数为12个。

对于80000用户的前端池，在采用 [Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)的典型部署中，12前端服务器的性能就足够了。 旨在支持灾难恢复故障转移的部署假定最多可以在两个配对的前端池（其中每个池都有足够的前端服务器以容纳两个池中的用户）中的每个主机都有足够40000的前端服务器转移到另一个池。

因特定前端池而支持的用户数与这些数字不同，原因可能有以下几种：

  - 前端服务器的硬件不符合 [Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的建议。

  - 组织的用法与用户模型明显不同，如明显具有更多的会议流量。

<div>


> [!IMPORTANT]  
> 在 Lync Server 2013 中，状态数据库现在托管在前端服务器上，而不是驻留在后端服务器上的 Lync Server 2010 中。 这意味着，无论前端服务器托管的用户数如何，您的前端服务器的磁盘性能和容量不应从本部分前面列出的建议中和在 <A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 的服务器硬件平台</A>中受到损害。



</div>

下表显示了在给定用户模型（在 [Lync Server 2013 的用户模型](lync-server-2013-user-models.md)中定义）的 IM 和状态的平均带宽。


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
> 若要改善在前端服务器上归置的 A/V 会议和中介服务器功能的媒体性能，应在前端服务器上的网络适配器上启用接收端扩展 (RSS) 。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息，请参阅中的 "在 Windows Server 2008 中接收端扩展功能增强" <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> 。 有关如何启用 RSS 的详细信息，请参阅网络适配器文档。



</div>

</div>

<div>

## <a name="conferencing-maximums"></a>会议最大值

假定用户模型为池中 5% 的用户可能会在任何时候参加会议，则拥有 80,000 个用户的池一次可能会有大约 4,000 个用户参加会议。 这些会议可能混合多种媒体（如一些仅含 IM、一些含有 IM 和音频、一些含有音频/视频）并拥有大量参与者。 允许的实际会议数没有硬限制，但实际用法决定了实际性能。 例如，如果组织中具有的混合模式会议的数量多于用户模型中假定的混合模式会议的数量，则可能需要部署的前端服务器或 A/V 会议服务器的数量会多于本文档中推荐的数量。 有关用户模型中的假设的详细信息，请参阅 [Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)。

由常规 Lync Server 2013 前端池托管的受支持的最大会议大小（也承载用户）是250参与者。 当发生 250-用户会议时，该池仍支持其他会议，从而使总池用户数达5% 的池用户处于并发会议中。 例如，在12台前端服务器和80000用户的池中，当 250-用户会议发生时，Lync Server 支持对参与小型会议的其他用户进行3750。

无论驻留在前端池或 Standard Edition 服务器上的用户数是多少，Lync Server 至少支持125在承载250用户会议的同一池或服务器上参与小型会议的其他用户。

若要启用介于250和1000用户之间的会议，您可以设置单独的前端池，只需承载这些会议即可。 此前端池不会承载任何用户。 有关详细信息，请参阅 [使用 Lync Server 2013 支持大型会议](lync-server-2013-supporting-large-meetings.md)。

如果您的组织的混合模式会议比用户模型中的假设多，则您可能需要部署更多前端服务器，而不是此文档中的建议 (最多 12 FEs) 的限制。 有关用户模型中的假设的详细信息，请参阅 [Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)。

</div>

<div>

## <a name="edge-server"></a>边缘服务器

<div>


> [!NOTE]  
> 此服务器角色不支持延伸池。



</div>

应为将同时访问网站的每个12000远程用户部署一台边缘服务器。 为实现高可用性，建议至少部署两台边缘服务器。 这些建议假定您的边缘服务器的硬件满足 [Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的建议。

在计算边缘服务器的用户数时，请将分支机构中与此站点的前端池关联的 Survivable Branch Appliance 和 Survivable Branch Server 上驻留的用户包括在内。

<div>


> [!NOTE]  
> 要提高边缘服务器上的 A/V 会议边缘服务的性能，应在边缘服务器的网络适配器上启用接收方缩放 (RSS)。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息，请参阅中的 "在 Windows Server 2008 中接收端扩展功能增强" <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> 。 有关如何启用 RSS 的详细信息，请参阅网络适配器文档。



</div>

</div>

<div>

## <a name="director"></a>控制器

<div>


> [!NOTE]  
> 此服务器角色不支持延伸池。



</div>

如果部署控制器服务器角色，建议您为将同时访问网站的每个12000远程用户部署一个控制器。 为实现高可用性，建议至少部署两台控制器。 这些建议假定您的边缘服务器的硬件满足 [Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的建议。

在计算控制器的用户数时，请将分支机构中与此站点的前端池关联的 Survivable Branch Appliance 和 Survivable Branch Server 上驻留的用户包括在内。

</div>

<div>

## <a name="mediation-server"></a>中介服务器

<div>


> [!NOTE]  
> 此服务器角色不支持延伸池。



</div>

如果您并置中介服务器与前端服务器，中介服务器将在池中的每台前端服务器上运行，并应为池中的用户提供足够的容量。

如果部署独立的中介服务器池，则要部署多少个中介服务器取决于许多因素，包括用于中介服务器的硬件、拥有的 VoIP 用户数、每个中介服务器池控制的网关对等方的数量、通过这些网关的繁忙小时流量，以及绕过中介服务器的媒体的呼叫百分比。

下表提供了对中介服务器可以处理的并发呼叫数的指导，假定中介服务器的硬件满足 [Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md) 中的要求，并且启用了超线程。 有关中介服务器可伸缩性的详细信息，请参阅[在 Lync server 2013 中](lync-server-2013-deployment-guidelines-for-mediation-server.md)[估计适用于 lync server 2013 的语音使用情况和流量](lync-server-2013-estimating-voice-usage-and-traffic.md)和中介服务器的部署指南。

下表假定 [Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)中汇总了使用率。

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a>独立中介服务器容量：70% 内部用户、30% 外部用户和非绕过呼叫容量 (由中介服务器执行的媒体转码) 

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
<td><p>双处理器，hex core，2.26 GHz 超线程 CPU， <strong>禁用超线程</strong>，使用 32 GB 内存和一个双端口网络适配器卡。</p></td>
<td><p>1100</p></td>
<td><p>46</p></td>
<td><p>35</p></td>
</tr>
<tr class="even">
<td><p>双处理器，十六核，2.26 GHz 超线程 CPU，带 32 GB 内存和一个双端口网络适配器卡。</p></td>
<td><p>1500</p></td>
<td><p>63</p></td>
<td><p>47</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 虽然性能测试使用的是内存为 32 GB 的服务器，但内存为 16 GB 的服务器也可用作独立中介服务器，并且足以提供此表中显示的性能。



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a>中介服务器容量 (中介服务器并置与前端服务器) 70% 内部用户、30% 外部用户、非绕过呼叫容量 (中介服务器执行的媒体处理) 

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
<td><p>双处理器，十六核，2.26 GHz 超线程 CPU，含 32 GB 内存和2个1GB 网络适配器卡。</p></td>
<td><p>150</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 此数字比独立中介服务器的编号要小得多，因为前端服务器除了语音呼叫所需的转码之外，还必须为驻留在其上的6600用户处理其他特性和功能。



</div>

<div>


> [!NOTE]  
> 若要提高中介服务器的性能，应在中介服务器上的网络适配器上启用接收端扩展 (RSS) 。 通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。 有关详细信息，请参阅中的 "在 Windows Server 2008 中接收端扩展功能增强" <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> 。 有关如何启用 RSS 的详细信息，请参阅网络适配器文档。



</div>

</div>

<div>

## <a name="back-end-server"></a>后端服务器

在 Lync Server 2013 中，状态数据库位于前端服务器上，而不是位于后端服务器上。 这为 Lync Server 2013 中的每台后端服务器带来了更简单的要求，相当于前端服务器的硬件要求。 与 Lync Server 2010 相比，需要将后端服务器设为具有25个磁盘的更高等级服务器。 但是，后端服务器的工作负荷仍为无法满足本部分以及 [Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中列出的硬件建议。

若要提供您的后端服务器的高可用性，建议部署服务器镜像。 有关详细信息，请参阅 [Lync server 2013 中的后端服务器高可用性](lync-server-2013-back-end-server-high-availability.md)。

</div>

<div>

## <a name="monitoring-and-archiving"></a>监控和存档

在 Lync Server 2013 中，如果您部署监控或存档，这些服务的前端功能将在前端服务器上运行，而不是在单独的服务器角色上运行。 监视和存档每个仍使用自己的数据库存储，与后端存储分开。 或者，如果部署了 Exchange 2013，则可以在 Exchange 中（而不是在专用的 SQL 存储中）存储即时消息存档数据。

下表指出了每个用户每天需要多少数据库存储来监视和存档数据。


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
<td><p><strong>CDR (监视) </strong></p></td>
<td><p><strong>QoE (监控) </strong></p></td>
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


Microsoft 将下表中的硬件用于数据库服务器，以便在其性能测试期间进行监控和存档。 测试收集了两个前端池的数据，其中每个都包含80000个用户。

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a>监控和存档性能测试中使用的硬件

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>硬件组件</th>
<th>建议</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>64 位双处理器、六核、2.26 GHz 或更快</p></td>
</tr>
<tr class="even">
<td><p>内存</p></td>
<td><p>48 gb (GB) </p></td>
</tr>
<tr class="odd">
<td><p>磁盘</p></td>
<td><p>每个磁盘上有 300 GB 的 25 10000-RPM 硬盘，使用以下配置</p>
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
<td><p><strong>Drive</strong></p></td>
<td><p><strong>RAID 配置</strong></p></td>
<td><p><strong>磁盘数</strong></p></td>
</tr>
<tr class="even">
<td><p>单个驱动器上的 CDR、QoE 和存档数据库数据文件</p></td>
<td><p>1 + 0</p></td>
<td><p>16 </p></td>
</tr>
<tr class="odd">
<td><p>CDR 数据库日志文件</p></td>
<td><p>1</p></td>
<td><p>双面</p></td>
</tr>
<tr class="even">
<td><p>QoE 数据库日志文件</p></td>
<td><p>1</p></td>
<td><p>双面</p></td>
</tr>
<tr class="odd">
<td><p>存档数据库日志文件</p></td>
<td><p>1</p></td>
<td><p>双面</p></td>
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

## <a name="in-this-section"></a>本部分内容

  - [估计 Lync Server 2013 的语音使用和流量](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [Lync Server 2013 中的中介服务器的部署指南](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

