---
title: Lync Server 2013 服务器硬件平台
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e352153e4cc2386a159ac11f27f8ba4f5beb09f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a>Lync Server 2013 的服务器硬件平台

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-07-28_

Lync Server 2013 服务器角色和运行 Lync Server 管理工具的计算机需要64位硬件。

用于 Lync Server 2013 部署的特定硬件可能会有所不同，具体取决于大小和使用要求。 本节介绍推荐的硬件。 虽然是建议（不是要求），但是使用不满足这些建议的硬件可能会导致明显的性能问题和其他问题。

<div>

## <a name="recommended-hardware-platform"></a>推荐的硬件平台

为了获得最佳性能，建议您在具有符合下表中要求的硬件的服务器上运行 Lync Server。 如果使用性能不足的硬件，可能会遇到功能问题或性能下降。 请注意，这些硬件要求高于以前版本的 Lync Server，主要是因为在 Lync Server 2013 中，所有前端服务器都运行 SQL Server。

<div>


> [!NOTE]  
> 支持 NIC 组合，并且对于 Lync Server 而言应是透明的。 有关详细信息，请参阅<A href="http://go.microsoft.com/fwlink/p/?linkid=389910">通信服务器或 Lync server 和网络适配器组合</A>。



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a>适用于前端服务器、后端服务器、Standard Edition 服务器、持久聊天服务器以及持久聊天服务器和持久聊天合规存储（持久聊天服务器的后端服务器角色）的推荐硬件

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
<td><p>64位双处理器、hex-core、2.26 千兆赫兹（GHz）或更高版本。</p>
<p>Lync Server 服务器角色不支持 Intel Itanium 处理器。</p></td>
</tr>
<tr class="even">
<td><p>内存</p></td>
<td><p>32千兆字节（GB）。</p></td>
</tr>
<tr class="odd">
<td><p>磁盘</p></td>
<td><ul>
<li><p>8 个或 8 个以上具有至少 72 GB 可用磁盘空间的 10,000 RPM 硬盘驱动器</p>
<p>其中两个磁盘驱动器应使用 RAID 1，另外六个磁盘驱动器应使用 RAID 10。</p>
<p>-和</p></li>
<li><p>性能类似于 8 个 10,000 RPM 机械磁盘驱动器的固态驱动器 (SSD)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>网络</p></td>
<td><ul>
<li><p>1个双端口网络适配器，1 Gbps 或更高（建议2个，这需要使用一个 MAC 地址和一个 IP 地址进行分组）。</p>
<div>

> [!NOTE]  
> 前端服务器、后端服务器、Standard Edition 服务器和持久聊天服务器不支持双宿主或多宿主配置。<BR>ILO/DRAC/etc。未向操作系统公开且用于监视和管理服务器硬件的连接不构成多穴服务器，因此受支持。


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a>边缘服务器、独立中介服务器和控制器的推荐硬件

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
<td><ul>
<li><p>64位双处理器、四核、2.0 千兆位（GHz）或更高版本。</p>
<p>-和</p></li>
<li><p>64位4路处理器、双核、2.0 GHz 或更高版本。</p></li>
</ul>
<p>Lync Server 服务器角色不支持 Intel Itanium 处理器。</p></td>
</tr>
<tr class="even">
<td><p>内存</p></td>
<td><p>16千兆字节（GB）。</p></td>
</tr>
<tr class="odd">
<td><p>磁盘</p></td>
<td><ul>
<li><p>4个或更多 10000 RPM 硬盘，至少有 72 GB 的可用磁盘空间。</p>
<p>磁盘应采用 2x RAID 1 配置。</p>
<p>-和</p></li>
<li><p>性能类似于 8 个 10,000 RPM 机械磁盘驱动器的固态驱动器 (SSD)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>网络</p></td>
<td><ul>
<li><p>1个双端口网络适配器，1 Gbps 或更高（建议2个，这需要使用一个 MAC 地址和一个 IP 地址进行分组）。 两个网络接口在边缘服务器上是必需的，并且在独立中介服务器上受支持。</p></li>
</ul>
<div>

> [!NOTE]  
> 控制器不支持双宿主或多宿主配置。<BR>ILO/DRAC/etc。未向操作系统公开且用于监视和管理服务器硬件的连接不构成多穴服务器，因此受支持。


</div>
<p>边缘服务器需要两个分别为双端口网络适配器、1 Gbps 或更高（或两个配对的网络适配器）的网络接口（或两个配对的网络适配器），每个端口包含一个 MAC 地址和一个 IP 地址，共有两对。</p>
<p>安装其他网络接口卡（Nic）以允许在独立中介服务器上支持特定 PSTN IP 地址的配置。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

