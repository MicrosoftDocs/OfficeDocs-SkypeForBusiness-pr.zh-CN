---
title: Lync Server 2013 服务器硬件平台
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2682d0d8636c024dee4151842a143e65b11d48c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a>Lync Server 2013 的服务器硬件平台

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2016-07-28_

Lync Server 2013 服务器角色和运行 Lync Server 管理工具的计算机需要64位硬件。

用于 Lync Server 2013 部署的特定硬件可能会有所不同, 具体取决于大小和使用要求。 本节介绍推荐的硬件。 虽然是建议（不是要求），但是使用不满足这些建议的硬件可能会导致重大性能问题和其他问题。

<div>

## <a name="recommended-hardware-platform"></a>推荐的硬件平台

为了获得最佳性能, 我们建议你在具有满足下表中的要求的硬件的服务器上运行 Lync 服务器。 如果使用性能不足的硬件，可能会遇到功能问题或性能下降。 请注意, 这些硬件要求比以前版本的 Lync Server 更高, 主要是因为在 Lync Server 2013 中, 所有前端服务器都运行 SQL Server。

<div>


> [!NOTE]  
> NIC 组合受支持, 并且对于 Lync 服务器而言应该是透明的。 有关详细信息, 请参阅<A href="http://go.microsoft.com/fwlink/p/?linkid=389910">通信服务器或 Lync 服务器和网络适配器分组</A>。



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a>前端服务器、后端服务器、Standard Edition 服务器、持久聊天存储和持久聊天合规性存储（持久聊天服务器的后端服务器角色）的推荐硬件

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
<td><p>64 位双处理器、六核、2.26 GHz 或更快。</p>
<p>Lync Server 服务器角色不支持英特尔安腾处理器。</p></td>
</tr>
<tr class="even">
<td><p>内存</p></td>
<td><p>32 GB。</p></td>
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
<li><p>1 个双端口网络适配器，1 Gbps 或更高（建议为 2 Gbps，这要求与一个 MAC 地址和一个 IP 地址结合使用）。</p>
<div>

> [!NOTE]  
> 前端服务器、后端服务器、标准版服务器和持久聊天服务器不支持双重或多穴配置。<BR>ILO/DRAC/更高的连接。未向操作系统公开的连接以及用于监视和管理服务器硬件的连接不构成多穴服务器, 因此受支持。


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
<th>推荐</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><ul>
<li><p>64位双处理器、四核、2.0 千兆位 (GHz) 或更高版本。</p>
<p>-或</p></li>
<li><p>64位4路处理器、双核、2.0 GHz 或更高版本。</p></li>
</ul>
<p>Lync Server 服务器角色不支持英特尔安腾处理器。</p></td>
</tr>
<tr class="even">
<td><p>内存</p></td>
<td><p>16千兆字节 (GB)。</p></td>
</tr>
<tr class="odd">
<td><p>磁盘</p></td>
<td><ul>
<li><p>4个或更多 10000 RPM 硬盘, 至少有 72 GB 的可用磁盘空间。</p>
<p>磁盘应使用 2x RAID 1 配置。</p>
<p>-或</p></li>
<li><p>性能类似于 4 个 10,000 RPM 机械磁盘驱动器的固态驱动器 (SSD)。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>网络</p></td>
<td><ul>
<li><p>1 个双端口网络适配器，1 Gbps 或更高（建议为 2 Gbps，这要求与一个 MAC 地址和一个 IP 地址结合使用）。 两个网络接口在 Edge 服务器上是必需的, 并且在独立中介服务器上受支持。</p></li>
</ul>
<div>

> [!NOTE]  
> 控制器不支持双穴或多穴配置。<BR>ILO/DRAC/更高的连接。未向操作系统公开的连接以及用于监视和管理服务器硬件的连接不构成多穴服务器, 因此受支持。


</div>
<p>边缘服务器需要两个两个网络接口: 双端口网络适配器、1 Gbps 或更高版本 (或两个配对网络适配器, 共4个), 每对都使用一个 MAC 地址和一个 IP 地址, 共两对。</p>
<p>安装其他网络接口卡 (Nic) 以允许特定 PSTN IP 地址的配置在独立中介服务器上受支持。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

