---
title: Lync Server 2013：控制器的硬件和软件要求
description: Lync Server 2013：控制器的硬件和软件要求。
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
ms.openlocfilehash: 6dd868a3a566f1d89b4ada5a16695f8eb02b3b21
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552928"
---
# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a><span data-ttu-id="17407-103">Lync Server 2013 中的控制器的硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="17407-103">Hardware and software requirements for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17407-104">_**上次修改的主题：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="17407-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="17407-105">本部分详细介绍了控制器的硬件和软件要求，以及控制器支持的并置方案。</span><span class="sxs-lookup"><span data-stu-id="17407-105">This section details the hardware and software requirements for the Director, and the supported collocation scenarios for the Director.</span></span>

<div>

## <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="17407-106">控制器的硬件要求</span><span class="sxs-lookup"><span data-stu-id="17407-106">Hardware Requirements for the Director</span></span>

<span data-ttu-id="17407-107">下表列出了控制器的硬件要求：</span><span class="sxs-lookup"><span data-stu-id="17407-107">The following table lists the hardware requirements for the Director:</span></span>

### <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="17407-108">控制器的硬件要求</span><span class="sxs-lookup"><span data-stu-id="17407-108">Hardware Requirements for the Director</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17407-109">硬件组件</span><span class="sxs-lookup"><span data-stu-id="17407-109">Hardware component</span></span></th>
<th><span data-ttu-id="17407-110">最低要求</span><span class="sxs-lookup"><span data-stu-id="17407-110">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17407-111">CPU</span><span class="sxs-lookup"><span data-stu-id="17407-111">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="17407-112">64 位处理器、四核、2.0 GHz 或更快</span><span class="sxs-lookup"><span data-stu-id="17407-112">64-bit processor, quad-core, 2.0 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="17407-113">64 位双处理器、双核、2.0 GHz 或更快</span><span class="sxs-lookup"><span data-stu-id="17407-113">64-bit dual processor, dual-core, 2.0 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17407-114">内存</span><span class="sxs-lookup"><span data-stu-id="17407-114">Memory</span></span></p></td>
<td><p><span data-ttu-id="17407-115">4 GB</span><span class="sxs-lookup"><span data-stu-id="17407-115">4 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17407-116">磁盘</span><span class="sxs-lookup"><span data-stu-id="17407-116">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="17407-117">转速为 10K RPM 的硬盘驱动器 (HDD)</span><span class="sxs-lookup"><span data-stu-id="17407-117">10K RPM hard disk drive (HDD)</span></span></p></li>
<li><p><span data-ttu-id="17407-118">性能等于或高于 10K RPM HDD 的高性能固态驱动器 (SSD)</span><span class="sxs-lookup"><span data-stu-id="17407-118">High-performance solid state drive (SSD) with performance equal to or better than 10K RPM HDD</span></span></p></li>
<li><p><span data-ttu-id="17407-119">2 个 RAID 10（条带和镜像）、转速为 15K RPM 的硬盘，用于存储数据库数据文件</span><span class="sxs-lookup"><span data-stu-id="17407-119">2x RAID 10 (striped and mirrored) 15K RPM disks for database data files</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17407-120">网络</span><span class="sxs-lookup"><span data-stu-id="17407-120">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="17407-121">双 1 千兆位每秒 (Gbps) 网络适配器（推荐）</span><span class="sxs-lookup"><span data-stu-id="17407-121">Dual 1 gigabit per second (Gbps) network adapters (recommended)</span></span></p></li>
<li><p><span data-ttu-id="17407-122">一个 1 Gbps 网络适配器（支持）</span><span class="sxs-lookup"><span data-stu-id="17407-122">Single 1 Gbps network adapter (supported)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a><span data-ttu-id="17407-123">控制器的软件要求</span><span class="sxs-lookup"><span data-stu-id="17407-123">Software Requirements for the Director</span></span>

<span data-ttu-id="17407-124">Director 角色只能部署在运行 Lync Server 2013 Enterprise Edition 的服务器上。</span><span class="sxs-lookup"><span data-stu-id="17407-124">The Director role can be deployed only on servers running Lync Server 2013 Enterprise Edition.</span></span>

<span data-ttu-id="17407-125">控制器需要以下64位操作系统之一：</span><span class="sxs-lookup"><span data-stu-id="17407-125">One of the following 64-bit operating systems is required for the Directors:</span></span>

  - <span data-ttu-id="17407-126">Windows Server 2008 R2 Standard 操作系统 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="17407-126">The Windows Server 2008 R2 Standard operating system with Service Pack 1</span></span>

  - <span data-ttu-id="17407-127">Windows Server 2008 R2 Enterprise 操作系统 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="17407-127">The Windows Server 2008 R2 Enterprise operating system with Service Pack 1</span></span>

  - <span data-ttu-id="17407-128">Windows Server 2008 R2 Datacenter 操作系统 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="17407-128">The Windows Server 2008 R2 Datacenter operating system with Service Pack 1</span></span>

  - <span data-ttu-id="17407-129">Windows Server 2012 标准操作系统</span><span class="sxs-lookup"><span data-stu-id="17407-129">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="17407-130">Windows Server 2012 Datacenter 操作系统</span><span class="sxs-lookup"><span data-stu-id="17407-130">The Windows Server 2012 Datacenter operating system</span></span>

<span data-ttu-id="17407-131">Lync Server 2013 还需要安装以下程序和更新在 [Lync Server 2013 中的主题其他服务器支持和要求](lync-server-2013-additional-server-support-and-requirements.md)中详细介绍。</span><span class="sxs-lookup"><span data-stu-id="17407-131">Lync Server 2013 also requires installation of the following programs and updates detailed in the topic [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="17407-132">支持的并置</span><span class="sxs-lookup"><span data-stu-id="17407-132">Supported Collocation</span></span>

<span data-ttu-id="17407-133">在 Lync Server 2013 中，控制器服务器角色不能与任何其他服务器角色并置。</span><span class="sxs-lookup"><span data-stu-id="17407-133">The Director server role cannot be collocated with any other server role in Lync Server 2013.</span></span> <span data-ttu-id="17407-134">但是，如果不部署控制器，前端服务器将承担角色。</span><span class="sxs-lookup"><span data-stu-id="17407-134">However, if you do not deploy a Director, the Front End Servers will assume the role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

