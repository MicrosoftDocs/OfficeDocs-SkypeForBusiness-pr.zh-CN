---
title: Lync Server 2013 服务器硬件平台
TOCTitle: 服务器硬件平台
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398835(v=OCS.15)
ms:contentKeyID: 49314244
ms.date: 07/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 适用于 Lync Server 2013 的服务器硬件平台

 

_**上一次修改主题：** 2016-12-08_

运行 Lync Server 管理工具的 Lync Server 2013服务器角色和计算机要求使用 64 位硬件。

用于 Lync Server 2013部署的特定硬件会因大小和使用要求而异。本节介绍推荐的硬件。虽然是建议（不是要求），但是使用不满足这些建议的硬件可能会导致重大性能问题和其他问题。

## 推荐的硬件平台

为实现最佳性能，建议在采用满足下表要求的硬件的服务器上运行 Lync Server。如果使用性能不足的硬件，可能会遇到功能问题或性能下降。请注意，这些硬件要求高于早期版本的 Lync Server的硬件要求，主要是因为在 Lync Server 2013中，所有前端服务器都运行 SQL Server。

> [!NOTE]  
> NIC 组合受支持，且应对 Lync Server透明。有关详细信息，请参阅<a href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming (通信服务器或 Lync Server 和网络适配器组合)</a>。



### 前端服务器、后端服务器、Standard Edition 服务器、持久聊天服务器、持久聊天存储和持久聊天合规性存储（持久聊天服务器的后端服务器角色）的推荐硬件

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
<p>Lync Server 服务器角色不支持 Intel Itanium 处理器。</p></td>
</tr>
<tr class="even">
<td><p>内存</p></td>
<td><p>32 GB。</p></td>
</tr>
<tr class="odd">
<td><p>磁盘</p></td>
<td><ul>
<li><p>8 个或 8 个以上具有至少 72 GB 可用磁盘空间的 10,000 RPM 硬盘驱动器。</p>
<p>两个磁盘应使用 RAID 1，其余六个应使用 RAID 10。</p>
<p>- 或 -</p></li>
<li><p>性能类似于 8 个 10,000 RPM 机械磁盘驱动器的固态驱动器 (SSD)。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>网络</p></td>
<td><ul>
<li><p>1 个双端口网络适配器，1 Gbps 或更高（建议为 2 Gbps，这要求与一个 MAC 地址和一个 IP 地址结合使用）。</p>
<div>

> [!NOTE]  
> 前端服务器、后端服务器、Standard Edition 服务器和 持久聊天服务器不支持双宿主或多宿主配置。<br />
ILO/DRAC 等连接不对操作系统公开，用于监视和管理不属于多宿主服务器的服务器硬件，因此这些连接受支持。


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### 边缘服务器、独立中介服务器和控制器的推荐硬件

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
<li><p>64 位双处理器、四核、2.0 GHz 或更快。</p>
<p>- 或 -</p></li>
<li><p>64 位 4 路处理器、双核、2.0 GHz 或更快。</p></li>
</ul>
<p>Lync Server 服务器角色不支持 Intel Itanium 处理器。</p></td>
</tr>
<tr class="even">
<td><p>内存</p></td>
<td><p>16 GB。</p></td>
</tr>
<tr class="odd">
<td><p>磁盘</p></td>
<td><ul>
<li><p>4 个或 4 个以上具有至少 72 GB 可用磁盘空间的 10,000 RPM 硬盘驱动器。</p>
<p>磁盘应使用 2x RAID 1 配置。</p>
<p>- 或 -</p></li>
<li><p>性能类似于 4 个 10,000 RPM 机械磁盘驱动器的固态驱动器 (SSD)。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>网络</p></td>
<td><ul>
<li><p>1 个双端口网络适配器，1 Gbps 或更高（建议为 2 Gbps，这要求与一个 MAC 地址和一个 IP 地址结合使用）。边缘服务器上需有 2 个网络接口，且这 2 个网络接口在独立中介服务器上受支持。</p></li>
</ul>
<div>

> [!NOTE]  
> 控制器不支持双宿主或多宿主配置。<br />
ILO/DRAC 等连接不对操作系统公开，用于监视和管理不属于多宿主服务器的服务器硬件，因此这些连接受支持。


</div>
<p>边缘服务器需要两个作为双端口网络适配器的网络接口、1 Gbps 或更高（或者两个成对的网络适配器，总共四个，每对与一个 MAC 地址和一个 IP 地址结合使用，总共两对）。</p>
<p>独立中介服务器上支持安装其他网络接口卡以允许配置特定的 PSTN IP 地址。</p></td>
</tr>
</tbody>
</table>

