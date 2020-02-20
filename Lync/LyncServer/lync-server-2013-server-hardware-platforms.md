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
ms.openlocfilehash: a1a1dddb7fe87ebc877ed16048a42a17760c2053
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a><span data-ttu-id="439f7-102">Lync Server 2013 的服务器硬件平台</span><span class="sxs-lookup"><span data-stu-id="439f7-102">Server hardware platforms for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="439f7-103">_**上次修改的主题：** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="439f7-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="439f7-104">Lync Server 2013 服务器角色和运行 Lync Server 管理工具的计算机需要64位硬件。</span><span class="sxs-lookup"><span data-stu-id="439f7-104">Lync Server 2013 server roles and computers running Lync Server administrative tools require 64-bit hardware.</span></span>

<span data-ttu-id="439f7-105">用于 Lync Server 2013 部署的特定硬件可能会有所不同，具体取决于大小和使用要求。</span><span class="sxs-lookup"><span data-stu-id="439f7-105">The specific hardware used for Lync Server 2013 deployment can vary, depending on size and usage requirements.</span></span> <span data-ttu-id="439f7-106">本节介绍推荐的硬件。</span><span class="sxs-lookup"><span data-stu-id="439f7-106">This section describes the recommended hardware.</span></span> <span data-ttu-id="439f7-107">虽然是建议（不是要求），但是使用不满足这些建议的硬件可能会导致明显的性能问题和其他问题。</span><span class="sxs-lookup"><span data-stu-id="439f7-107">Although these are recommendations, not requirements, using hardware that does not meet these recommendations may result in significant performance issues and other issues.</span></span>

<div>

## <a name="recommended-hardware-platform"></a><span data-ttu-id="439f7-108">推荐的硬件平台</span><span class="sxs-lookup"><span data-stu-id="439f7-108">Recommended Hardware Platform</span></span>

<span data-ttu-id="439f7-109">为了获得最佳性能，建议您在具有符合下表中要求的硬件的服务器上运行 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="439f7-109">For best performance, we recommend that you run Lync Server on servers with hardware that meets the requirements in the following table.</span></span> <span data-ttu-id="439f7-110">如果使用性能不足的硬件，可能会遇到功能问题或性能下降。</span><span class="sxs-lookup"><span data-stu-id="439f7-110">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="439f7-111">请注意，这些硬件要求高于以前版本的 Lync Server，主要是因为在 Lync Server 2013 中，所有前端服务器都运行 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="439f7-111">Note that these hardware requirements are higher than those of previous versions of Lync Server, primarily because in Lync Server 2013, all Front End Servers run SQL Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="439f7-112">支持 NIC 组合，并且对于 Lync Server 而言应是透明的。</span><span class="sxs-lookup"><span data-stu-id="439f7-112">NIC teaming is supported and should be transparent to Lync Server.</span></span> <span data-ttu-id="439f7-113">有关详细信息，请参阅<A href="https://go.microsoft.com/fwlink/p/?linkid=389910">通信服务器或 Lync server 和网络适配器组合</A>。</span><span class="sxs-lookup"><span data-stu-id="439f7-113">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming</A>.</span></span>



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a><span data-ttu-id="439f7-114">适用于前端服务器、后端服务器、Standard Edition 服务器、持久聊天服务器以及持久聊天服务器和持久聊天合规存储（持久聊天服务器的后端服务器角色）的推荐硬件</span><span class="sxs-lookup"><span data-stu-id="439f7-114">Recommended Hardware for Front End Servers, Back End Servers, Standard Edition Servers, Persistent Chat Servers, and Persistent Chat Store and Persistent Chat Compliance Store (Back End Server Roles for Persistent Chat Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="439f7-115">硬件组件</span><span class="sxs-lookup"><span data-stu-id="439f7-115">Hardware component</span></span></th>
<th><span data-ttu-id="439f7-116">建议</span><span class="sxs-lookup"><span data-stu-id="439f7-116">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="439f7-117">CPU</span><span class="sxs-lookup"><span data-stu-id="439f7-117">CPU</span></span></p></td>
<td><p><span data-ttu-id="439f7-118">64位双处理器、hex-core、2.26 千兆赫兹（GHz）或更高版本。</span><span class="sxs-lookup"><span data-stu-id="439f7-118">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="439f7-119">Lync Server 服务器角色不支持 Intel Itanium 处理器。</span><span class="sxs-lookup"><span data-stu-id="439f7-119">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="439f7-120">内存</span><span class="sxs-lookup"><span data-stu-id="439f7-120">Memory</span></span></p></td>
<td><p><span data-ttu-id="439f7-121">32千兆字节（GB）。</span><span class="sxs-lookup"><span data-stu-id="439f7-121">32 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="439f7-122">磁盘</span><span class="sxs-lookup"><span data-stu-id="439f7-122">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="439f7-123">8 个或 8 个以上具有至少 72 GB 可用磁盘空间的 10,000 RPM 硬盘驱动器</span><span class="sxs-lookup"><span data-stu-id="439f7-123">8 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="439f7-124">其中两个磁盘驱动器应使用 RAID 1，另外六个磁盘驱动器应使用 RAID 10。</span><span class="sxs-lookup"><span data-stu-id="439f7-124">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="439f7-125">-和</span><span class="sxs-lookup"><span data-stu-id="439f7-125">- OR -</span></span></p></li>
<li><p><span data-ttu-id="439f7-126">性能类似于 8 个 10,000 RPM 机械磁盘驱动器的固态驱动器 (SSD)</span><span class="sxs-lookup"><span data-stu-id="439f7-126">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="439f7-127">网络</span><span class="sxs-lookup"><span data-stu-id="439f7-127">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="439f7-128">1个双端口网络适配器，1 Gbps 或更高（建议2个，这需要使用一个 MAC 地址和一个 IP 地址进行分组）。</span><span class="sxs-lookup"><span data-stu-id="439f7-128">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="439f7-129">前端服务器、后端服务器、Standard Edition 服务器和持久聊天服务器不支持双宿主或多宿主配置。</span><span class="sxs-lookup"><span data-stu-id="439f7-129">Dual or multi-homed configurations are not supported for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers.</span></span><BR><span data-ttu-id="439f7-130">ILO/DRAC/etc。未向操作系统公开且用于监视和管理服务器硬件的连接不构成多穴服务器，因此受支持。</span><span class="sxs-lookup"><span data-stu-id="439f7-130">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a><span data-ttu-id="439f7-131">边缘服务器、独立中介服务器和控制器的推荐硬件</span><span class="sxs-lookup"><span data-stu-id="439f7-131">Recommended Hardware for Edge Servers, Standalone Mediation Servers, and Directors</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="439f7-132">硬件组件</span><span class="sxs-lookup"><span data-stu-id="439f7-132">Hardware component</span></span></th>
<th><span data-ttu-id="439f7-133">建议</span><span class="sxs-lookup"><span data-stu-id="439f7-133">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="439f7-134">CPU</span><span class="sxs-lookup"><span data-stu-id="439f7-134">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="439f7-135">64位双处理器、四核、2.0 千兆位（GHz）或更高版本。</span><span class="sxs-lookup"><span data-stu-id="439f7-135">64-bit dual processor, quad-core, 2.0 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="439f7-136">-和</span><span class="sxs-lookup"><span data-stu-id="439f7-136">- OR -</span></span></p></li>
<li><p><span data-ttu-id="439f7-137">64位4路处理器、双核、2.0 GHz 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="439f7-137">64-bit 4-way processor, dual-core, 2.0 GHz or higher.</span></span></p></li>
</ul>
<p><span data-ttu-id="439f7-138">Lync Server 服务器角色不支持 Intel Itanium 处理器。</span><span class="sxs-lookup"><span data-stu-id="439f7-138">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="439f7-139">内存</span><span class="sxs-lookup"><span data-stu-id="439f7-139">Memory</span></span></p></td>
<td><p><span data-ttu-id="439f7-140">16千兆字节（GB）。</span><span class="sxs-lookup"><span data-stu-id="439f7-140">16 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="439f7-141">磁盘</span><span class="sxs-lookup"><span data-stu-id="439f7-141">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="439f7-142">4个或更多 10000 RPM 硬盘，至少有 72 GB 的可用磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="439f7-142">4 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="439f7-143">磁盘应采用 2x RAID 1 配置。</span><span class="sxs-lookup"><span data-stu-id="439f7-143">The disks should be in a 2x RAID 1 configuration.</span></span></p>
<p><span data-ttu-id="439f7-144">-和</span><span class="sxs-lookup"><span data-stu-id="439f7-144">- OR -</span></span></p></li>
<li><p><span data-ttu-id="439f7-145">性能类似于 8 个 10,000 RPM 机械磁盘驱动器的固态驱动器 (SSD)</span><span class="sxs-lookup"><span data-stu-id="439f7-145">Solid state drives (SSDs) which provide performance similar to 4 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="439f7-146">网络</span><span class="sxs-lookup"><span data-stu-id="439f7-146">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="439f7-147">1个双端口网络适配器，1 Gbps 或更高（建议2个，这需要使用一个 MAC 地址和一个 IP 地址进行分组）。</span><span class="sxs-lookup"><span data-stu-id="439f7-147">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span> <span data-ttu-id="439f7-148">两个网络接口在边缘服务器上是必需的，并且在独立中介服务器上受支持。</span><span class="sxs-lookup"><span data-stu-id="439f7-148">2 network interfaces are required on Edge Servers, and are supported on standalone Mediation Servers.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="439f7-149">控制器不支持双宿主或多宿主配置。</span><span class="sxs-lookup"><span data-stu-id="439f7-149">Dual or multi-homed configurations are not supported for Directors.</span></span><BR><span data-ttu-id="439f7-150">ILO/DRAC/etc。未向操作系统公开且用于监视和管理服务器硬件的连接不构成多穴服务器，因此受支持。</span><span class="sxs-lookup"><span data-stu-id="439f7-150">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div>
<p><span data-ttu-id="439f7-151">边缘服务器需要两个分别为双端口网络适配器、1 Gbps 或更高（或两个配对的网络适配器）的网络接口（或两个配对的网络适配器），每个端口包含一个 MAC 地址和一个 IP 地址，共有两对。</span><span class="sxs-lookup"><span data-stu-id="439f7-151">Edge Servers will require two network interfaces that are dual-port network adapters, 1 Gbps or higher (or two paired network adapters, for a total of four, each pair being teamed with a single MAC address and a single IP address, for a total of two pairs).</span></span></p>
<p><span data-ttu-id="439f7-152">安装其他网络接口卡（Nic）以允许在独立中介服务器上支持特定 PSTN IP 地址的配置。</span><span class="sxs-lookup"><span data-stu-id="439f7-152">Installation of additional network interface cards (NICs) to allow the configuration of a specific PSTN IP address is supported on standalone Mediation Servers.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

