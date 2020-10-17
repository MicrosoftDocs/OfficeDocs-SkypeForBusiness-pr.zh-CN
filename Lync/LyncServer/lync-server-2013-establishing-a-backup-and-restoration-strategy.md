---
title: Lync Server 2013：建立备份和还原策略
description: Lync Server 2013：建立备份和还原策略。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4fdefed873d1fd69d82f8ecebceeb92f06f65f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555038"
---
# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="9eed8-103">为 Lync Server 2013 建立备份和还原策略</span><span class="sxs-lookup"><span data-stu-id="9eed8-103">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9eed8-104">_**上次修改的主题：** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="9eed8-104">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="9eed8-105">在您可以为 Lync Server 开发备份和还原计划之前，您需要制定符合组织目标的策略。</span><span class="sxs-lookup"><span data-stu-id="9eed8-105">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="9eed8-106">若要制定有效的备份和还原策略，您将需要：</span><span class="sxs-lookup"><span data-stu-id="9eed8-106">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="9eed8-107">建立业务优先级。</span><span class="sxs-lookup"><span data-stu-id="9eed8-107">Establish business priorities.</span></span>

  - <span data-ttu-id="9eed8-108">确定备份和还原要求。</span><span class="sxs-lookup"><span data-stu-id="9eed8-108">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="9eed8-109">建立业务优先级</span><span class="sxs-lookup"><span data-stu-id="9eed8-109">Establishing Business Priorities</span></span>

<span data-ttu-id="9eed8-p102">评估组织的业务优先级。通常情况下，影响您的备份和还原策略的主要业务优先级包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="9eed8-p102">Evaluate the business priorities of your organization. Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="9eed8-112">业务连续性要求</span><span class="sxs-lookup"><span data-stu-id="9eed8-112">Business continuity requirements</span></span>

  - <span data-ttu-id="9eed8-113">数据完整性</span><span class="sxs-lookup"><span data-stu-id="9eed8-113">Data completeness</span></span>

  - <span data-ttu-id="9eed8-114">数据关键程度</span><span class="sxs-lookup"><span data-stu-id="9eed8-114">Data criticality</span></span>

  - <span data-ttu-id="9eed8-115">可移植性要求</span><span class="sxs-lookup"><span data-stu-id="9eed8-115">Portability requirements</span></span>

  - <span data-ttu-id="9eed8-116">成本约束</span><span class="sxs-lookup"><span data-stu-id="9eed8-116">Cost constraints</span></span>

<span data-ttu-id="9eed8-117">这些业务需求（如以下帮助）可确定您与客户一起开发 (Sla) 的服务级别协议。</span><span class="sxs-lookup"><span data-stu-id="9eed8-117">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="9eed8-118">服务级别协议极大地影响了备份和恢复策略。</span><span class="sxs-lookup"><span data-stu-id="9eed8-118">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="9eed8-119">确定备份和还原要求</span><span class="sxs-lookup"><span data-stu-id="9eed8-119">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="9eed8-120">你的业务优先级和服务级别协议在确定组织对备份和还原 Lync Server 的要求时起作用。</span><span class="sxs-lookup"><span data-stu-id="9eed8-120">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="9eed8-121">请确定和记录您对以下项的要求：</span><span class="sxs-lookup"><span data-stu-id="9eed8-121">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="9eed8-122">**备份频率**    有关备份频率的最佳实践的详细信息，请参阅[Lync Server 2013 的备份和还原最佳实践](lync-server-2013-best-practices-for-backup-and-restoration.md)。</span><span class="sxs-lookup"><span data-stu-id="9eed8-122">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="9eed8-123">**备份和还原工具**    包括谁是使用这些工具，以及在哪些计算机上。</span><span class="sxs-lookup"><span data-stu-id="9eed8-123">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="9eed8-124">有关本主题中讨论的工具和必要权限的详细信息，请参阅 [Lync Server 2013 中的备份和还原要求：工具和权限](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="9eed8-124">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="9eed8-125">**备份位置**    确定是否在本地或远程保存备份，并考虑安全性和可访问性。</span><span class="sxs-lookup"><span data-stu-id="9eed8-125">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="9eed8-126">指定用于备份的介质。</span><span class="sxs-lookup"><span data-stu-id="9eed8-126">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="9eed8-127">**硬件和软件要求**    确定并记录您的特定硬件和软件要求，包括备份存储的硬件和特定组件的还原以及支持备份和还原所需的任何软件和网络连接。</span><span class="sxs-lookup"><span data-stu-id="9eed8-127">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="9eed8-128">在确定硬件和软件要求时，请记住下面的各种还原方案。</span><span class="sxs-lookup"><span data-stu-id="9eed8-128">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="9eed8-129">**还原方案**    以下是以下方案的还原过程：</span><span class="sxs-lookup"><span data-stu-id="9eed8-129">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="9eed8-130">Lync Server 池失败。</span><span class="sxs-lookup"><span data-stu-id="9eed8-130">A Lync Server pool fails.</span></span> <span data-ttu-id="9eed8-131">此方案要求重新构建池中的每台服务器。</span><span class="sxs-lookup"><span data-stu-id="9eed8-131">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="9eed8-132">Standard Edition server 失败。</span><span class="sxs-lookup"><span data-stu-id="9eed8-132">A Standard Edition server fails.</span></span> <span data-ttu-id="9eed8-133">此方案要求在新的或干净的计算机上重新构建服务器和还原数据库。</span><span class="sxs-lookup"><span data-stu-id="9eed8-133">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="9eed8-134">中央管理存储丢失。</span><span class="sxs-lookup"><span data-stu-id="9eed8-134">Loss of the Central Management store.</span></span> <span data-ttu-id="9eed8-135">此方案至少需要还原和发布中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="9eed8-135">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="9eed8-136">中央管理存储仍正常运行时，失去后端服务器。</span><span class="sxs-lookup"><span data-stu-id="9eed8-136">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="9eed8-137">此方案要求在新的或干净的计算机上重新构建服务器和还原数据库。</span><span class="sxs-lookup"><span data-stu-id="9eed8-137">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="9eed8-138">作为 Lync Server 池成员的服务器出现故障。</span><span class="sxs-lookup"><span data-stu-id="9eed8-138">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="9eed8-139">此方案要求在新的或干净的计算机上重新构建服务器。</span><span class="sxs-lookup"><span data-stu-id="9eed8-139">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="9eed8-140">文件存储失败。</span><span class="sxs-lookup"><span data-stu-id="9eed8-140">A File Store fails.</span></span> <span data-ttu-id="9eed8-141">此方案要求还原文件服务器或文件群集。</span><span class="sxs-lookup"><span data-stu-id="9eed8-141">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="9eed8-142">存档、监视或持久聊天数据库失败。</span><span class="sxs-lookup"><span data-stu-id="9eed8-142">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="9eed8-143">此方案要求重新创建数据库和还原数据（如果该数据对贵组织十分重要）。</span><span class="sxs-lookup"><span data-stu-id="9eed8-143">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="9eed8-144">无需存档、监视和持久聊天数据即可恢复并运行 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="9eed8-144">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

