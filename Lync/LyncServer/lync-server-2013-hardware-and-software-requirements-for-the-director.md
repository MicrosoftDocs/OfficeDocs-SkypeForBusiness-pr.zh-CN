---
title: Lync Server 2013：控制器的软硬件要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3b1b2a3f642c01d3a4743281554834e9ddda55f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a><span data-ttu-id="79c46-102">Lync Server 2013 中控制器的软硬件要求</span><span class="sxs-lookup"><span data-stu-id="79c46-102">Hardware and software requirements for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79c46-103">_**主题上次修改时间:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="79c46-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="79c46-104">本部分详细介绍了 Director 的硬件和软件要求, 以及 Director 支持的 collocation 方案。</span><span class="sxs-lookup"><span data-stu-id="79c46-104">This section details the hardware and software requirements for the Director, and the supported collocation scenarios for the Director.</span></span>

<div>

## <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="79c46-105">控制器的硬件要求</span><span class="sxs-lookup"><span data-stu-id="79c46-105">Hardware Requirements for the Director</span></span>

<span data-ttu-id="79c46-106">下表列出了 Director 的硬件要求:</span><span class="sxs-lookup"><span data-stu-id="79c46-106">The following table lists the hardware requirements for the Director:</span></span>

### <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="79c46-107">控制器的硬件要求</span><span class="sxs-lookup"><span data-stu-id="79c46-107">Hardware Requirements for the Director</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79c46-108">硬件组件</span><span class="sxs-lookup"><span data-stu-id="79c46-108">Hardware component</span></span></th>
<th><span data-ttu-id="79c46-109">最低要求</span><span class="sxs-lookup"><span data-stu-id="79c46-109">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79c46-110">CPU</span><span class="sxs-lookup"><span data-stu-id="79c46-110">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="79c46-111">64位处理器、四核、2.0 GHz 或更高版本</span><span class="sxs-lookup"><span data-stu-id="79c46-111">64-bit processor, quad-core, 2.0 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="79c46-112">64位双处理器、双核、2.0 GHz 或更高版本</span><span class="sxs-lookup"><span data-stu-id="79c46-112">64-bit dual processor, dual-core, 2.0 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c46-113">内存</span><span class="sxs-lookup"><span data-stu-id="79c46-113">Memory</span></span></p></td>
<td><p><span data-ttu-id="79c46-114">4千兆字节 (GB)</span><span class="sxs-lookup"><span data-stu-id="79c46-114">4 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79c46-115">磁盘</span><span class="sxs-lookup"><span data-stu-id="79c46-115">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="79c46-116">10K RPM 硬盘 (HDD)</span><span class="sxs-lookup"><span data-stu-id="79c46-116">10K RPM hard disk drive (HDD)</span></span></p></li>
<li><p><span data-ttu-id="79c46-117">高性能稳定状态驱动器 (SSD), 性能等于或优于 10K RPM HDD</span><span class="sxs-lookup"><span data-stu-id="79c46-117">High-performance solid state drive (SSD) with performance equal to or better than 10K RPM HDD</span></span></p></li>
<li><p><span data-ttu-id="79c46-118">2倍的 RAID 10 (条带化和镜像) 数据库数据文件的 15K RPM 磁盘</span><span class="sxs-lookup"><span data-stu-id="79c46-118">2x RAID 10 (striped and mirrored) 15K RPM disks for database data files</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79c46-119">网络</span><span class="sxs-lookup"><span data-stu-id="79c46-119">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="79c46-120">双核1千兆位/秒 (Gbps) 网络适配器 (推荐)</span><span class="sxs-lookup"><span data-stu-id="79c46-120">Dual 1 gigabit per second (Gbps) network adapters (recommended)</span></span></p></li>
<li><p><span data-ttu-id="79c46-121">单个 1 Gbps 网络适配器 (支持)</span><span class="sxs-lookup"><span data-stu-id="79c46-121">Single 1 Gbps network adapter (supported)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a><span data-ttu-id="79c46-122">董事的软件要求</span><span class="sxs-lookup"><span data-stu-id="79c46-122">Software Requirements for the Director</span></span>

<span data-ttu-id="79c46-123">Director 角色只能部署在运行 Lync Server 2013 企业版的服务器上。</span><span class="sxs-lookup"><span data-stu-id="79c46-123">The Director role can be deployed only on servers running Lync Server 2013 Enterprise Edition.</span></span>

<span data-ttu-id="79c46-124">控制器需要以下64位操作系统之一:</span><span class="sxs-lookup"><span data-stu-id="79c46-124">One of the following 64-bit operating systems is required for the Directors:</span></span>

  - <span data-ttu-id="79c46-125">Windows Server 2008 R2 标准操作系统, Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="79c46-125">The Windows Server 2008 R2 Standard operating system with Service Pack 1</span></span>

  - <span data-ttu-id="79c46-126">Windows Server 2008 R2 企业版操作系统 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="79c46-126">The Windows Server 2008 R2 Enterprise operating system with Service Pack 1</span></span>

  - <span data-ttu-id="79c46-127">Windows Server 2008 R2 Datacenter 操作系统 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="79c46-127">The Windows Server 2008 R2 Datacenter operating system with Service Pack 1</span></span>

  - <span data-ttu-id="79c46-128">Windows Server 2012 标准操作系统</span><span class="sxs-lookup"><span data-stu-id="79c46-128">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="79c46-129">Windows Server 2012 Datacenter 操作系统</span><span class="sxs-lookup"><span data-stu-id="79c46-129">The Windows Server 2012 Datacenter operating system</span></span>

<span data-ttu-id="79c46-130">Lync Server 2013 还要求安装以下程序和更新, 详细信息请参阅[Lync Server 2013 中的其他服务器支持和要求](lync-server-2013-additional-server-support-and-requirements.md)主题。</span><span class="sxs-lookup"><span data-stu-id="79c46-130">Lync Server 2013 also requires installation of the following programs and updates detailed in the topic [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="79c46-131">支持的 Collocation</span><span class="sxs-lookup"><span data-stu-id="79c46-131">Supported Collocation</span></span>

<span data-ttu-id="79c46-132">Director 服务器角色不能与 Lync Server 2013 中的任何其他服务器角色 collocated。</span><span class="sxs-lookup"><span data-stu-id="79c46-132">The Director server role cannot be collocated with any other server role in Lync Server 2013.</span></span> <span data-ttu-id="79c46-133">但是, 如果您不部署 Director, 前端服务器将承担该角色。</span><span class="sxs-lookup"><span data-stu-id="79c46-133">However, if you do not deploy a Director, the Front End Servers will assume the role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

