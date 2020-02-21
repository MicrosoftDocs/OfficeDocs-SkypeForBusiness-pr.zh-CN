---
title: Lync Server 2013：控制器的硬件和软件要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e0c75135d1ccfbb544c14c5cdc530b4e9a67b47
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a><span data-ttu-id="91afc-102">Lync Server 2013 中的控制器的硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="91afc-102">Hardware and software requirements for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91afc-103">_**上次修改的主题：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="91afc-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="91afc-104">本部分详细介绍了控制器的硬件和软件要求，以及控制器支持的并置方案。</span><span class="sxs-lookup"><span data-stu-id="91afc-104">This section details the hardware and software requirements for the Director, and the supported collocation scenarios for the Director.</span></span>

<div>

## <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="91afc-105">控制器的硬件要求</span><span class="sxs-lookup"><span data-stu-id="91afc-105">Hardware Requirements for the Director</span></span>

<span data-ttu-id="91afc-106">下表列出了控制器的硬件要求：</span><span class="sxs-lookup"><span data-stu-id="91afc-106">The following table lists the hardware requirements for the Director:</span></span>

### <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="91afc-107">控制器的硬件要求</span><span class="sxs-lookup"><span data-stu-id="91afc-107">Hardware Requirements for the Director</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91afc-108">硬件组件</span><span class="sxs-lookup"><span data-stu-id="91afc-108">Hardware component</span></span></th>
<th><span data-ttu-id="91afc-109">最低要求</span><span class="sxs-lookup"><span data-stu-id="91afc-109">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91afc-110">CPU</span><span class="sxs-lookup"><span data-stu-id="91afc-110">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="91afc-111">64 位处理器、四核、2.0 GHz 或更快</span><span class="sxs-lookup"><span data-stu-id="91afc-111">64-bit processor, quad-core, 2.0 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="91afc-112">64 位双处理器、双核、2.0 GHz 或更快</span><span class="sxs-lookup"><span data-stu-id="91afc-112">64-bit dual processor, dual-core, 2.0 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91afc-113">内存</span><span class="sxs-lookup"><span data-stu-id="91afc-113">Memory</span></span></p></td>
<td><p><span data-ttu-id="91afc-114">4 GB</span><span class="sxs-lookup"><span data-stu-id="91afc-114">4 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91afc-115">磁盘</span><span class="sxs-lookup"><span data-stu-id="91afc-115">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="91afc-116">转速为 10K RPM 的硬盘驱动器 (HDD)</span><span class="sxs-lookup"><span data-stu-id="91afc-116">10K RPM hard disk drive (HDD)</span></span></p></li>
<li><p><span data-ttu-id="91afc-117">性能等于或高于 10K RPM HDD 的高性能固态驱动器 (SSD)</span><span class="sxs-lookup"><span data-stu-id="91afc-117">High-performance solid state drive (SSD) with performance equal to or better than 10K RPM HDD</span></span></p></li>
<li><p><span data-ttu-id="91afc-118">2 个 RAID 10（条带和镜像）、转速为 15K RPM 的硬盘，用于存储数据库数据文件</span><span class="sxs-lookup"><span data-stu-id="91afc-118">2x RAID 10 (striped and mirrored) 15K RPM disks for database data files</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91afc-119">网络</span><span class="sxs-lookup"><span data-stu-id="91afc-119">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="91afc-120">双 1 千兆位每秒 (Gbps) 网络适配器（推荐）</span><span class="sxs-lookup"><span data-stu-id="91afc-120">Dual 1 gigabit per second (Gbps) network adapters (recommended)</span></span></p></li>
<li><p><span data-ttu-id="91afc-121">一个 1 Gbps 网络适配器（支持）</span><span class="sxs-lookup"><span data-stu-id="91afc-121">Single 1 Gbps network adapter (supported)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a><span data-ttu-id="91afc-122">控制器的软件要求</span><span class="sxs-lookup"><span data-stu-id="91afc-122">Software Requirements for the Director</span></span>

<span data-ttu-id="91afc-123">Director 角色只能部署在运行 Lync Server 2013 Enterprise Edition 的服务器上。</span><span class="sxs-lookup"><span data-stu-id="91afc-123">The Director role can be deployed only on servers running Lync Server 2013 Enterprise Edition.</span></span>

<span data-ttu-id="91afc-124">控制器需要以下64位操作系统之一：</span><span class="sxs-lookup"><span data-stu-id="91afc-124">One of the following 64-bit operating systems is required for the Directors:</span></span>

  - <span data-ttu-id="91afc-125">Windows Server 2008 R2 Standard 操作系统 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="91afc-125">The Windows Server 2008 R2 Standard operating system with Service Pack 1</span></span>

  - <span data-ttu-id="91afc-126">Windows Server 2008 R2 Enterprise 操作系统 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="91afc-126">The Windows Server 2008 R2 Enterprise operating system with Service Pack 1</span></span>

  - <span data-ttu-id="91afc-127">Windows Server 2008 R2 Datacenter 操作系统 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="91afc-127">The Windows Server 2008 R2 Datacenter operating system with Service Pack 1</span></span>

  - <span data-ttu-id="91afc-128">Windows Server 2012 标准操作系统</span><span class="sxs-lookup"><span data-stu-id="91afc-128">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="91afc-129">Windows Server 2012 Datacenter 操作系统</span><span class="sxs-lookup"><span data-stu-id="91afc-129">The Windows Server 2012 Datacenter operating system</span></span>

<span data-ttu-id="91afc-130">Lync Server 2013 还需要安装以下程序和更新在[Lync Server 2013 中的主题其他服务器支持和要求](lync-server-2013-additional-server-support-and-requirements.md)中详细介绍。</span><span class="sxs-lookup"><span data-stu-id="91afc-130">Lync Server 2013 also requires installation of the following programs and updates detailed in the topic [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="91afc-131">支持的并置</span><span class="sxs-lookup"><span data-stu-id="91afc-131">Supported Collocation</span></span>

<span data-ttu-id="91afc-132">在 Lync Server 2013 中，控制器服务器角色不能与任何其他服务器角色并置。</span><span class="sxs-lookup"><span data-stu-id="91afc-132">The Director server role cannot be collocated with any other server role in Lync Server 2013.</span></span> <span data-ttu-id="91afc-133">但是，如果不部署控制器，前端服务器将承担角色。</span><span class="sxs-lookup"><span data-stu-id="91afc-133">However, if you do not deploy a Director, the Front End Servers will assume the role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

