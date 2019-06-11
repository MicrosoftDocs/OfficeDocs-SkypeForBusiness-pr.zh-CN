---
title: 从 Office Communications Server 2007 R2 迁移至 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43064d265bc08cab3721d0f19fd7f89184871f0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a><span data-ttu-id="39dbe-102">从 Office Communications Server 2007 R2 迁移至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39dbe-102">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39dbe-103">_**主题上次修改时间:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="39dbe-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="39dbe-104">本部分中的主题将指导你完成从 Office 通信服务器 2007 R2 迁移到 Lync Server 2013 的过程</span><span class="sxs-lookup"><span data-stu-id="39dbe-104">The topics in this section guide you through the process of migrating from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="39dbe-105">本文档介绍了完成迁移的每个阶段通常需要执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="39dbe-105">This document describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="39dbe-106">它不能解决每个可能的旧部署拓扑或每种可能的迁移方案。</span><span class="sxs-lookup"><span data-stu-id="39dbe-106">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="39dbe-107">因此, 你可能不需要执行所述的每个步骤, 或者你可能需要执行其他步骤, 具体取决于你的部署。</span><span class="sxs-lookup"><span data-stu-id="39dbe-107">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="39dbe-108">本文档还提供了验证步骤的示例。</span><span class="sxs-lookup"><span data-stu-id="39dbe-108">This document also provides examples of verification steps.</span></span> <span data-ttu-id="39dbe-109">提供这些验证步骤旨在帮助你了解需要查找的内容, 以确保每个阶段在你的迁移过程中成功完成。</span><span class="sxs-lookup"><span data-stu-id="39dbe-109">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="39dbe-110">将这些验证步骤定制到特定迁移过程。</span><span class="sxs-lookup"><span data-stu-id="39dbe-110">Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="39dbe-111">本指南提供有关升级现有部署的特定信息。</span><span class="sxs-lookup"><span data-stu-id="39dbe-111">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="39dbe-112">它不介绍如何更改现有拓扑。</span><span class="sxs-lookup"><span data-stu-id="39dbe-112">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="39dbe-113">本指南不介绍新功能的实现。</span><span class="sxs-lookup"><span data-stu-id="39dbe-113">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="39dbe-114">当详细过程记录在其他位置时, 本指南将指导你使用相应的文档或文档部分。</span><span class="sxs-lookup"><span data-stu-id="39dbe-114">When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="39dbe-115">此文档定义了下表中指定的术语。</span><span class="sxs-lookup"><span data-stu-id="39dbe-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="39dbe-116">*移植*</span><span class="sxs-lookup"><span data-stu-id="39dbe-116">*migration*</span></span>  
    <span data-ttu-id="39dbe-117">将生产部署从早期版本的 Office 通信服务器 2007 R2 迁移到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="39dbe-117">Moving your production deployment from a previous version of Office Communications Server 2007 R2 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="39dbe-118">*升级*</span><span class="sxs-lookup"><span data-stu-id="39dbe-118">*upgrade*</span></span>  
    <span data-ttu-id="39dbe-119">在服务器或客户端计算机上安装较新版本的软件。</span><span class="sxs-lookup"><span data-stu-id="39dbe-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="39dbe-120">*既*</span><span class="sxs-lookup"><span data-stu-id="39dbe-120">*coexistence*</span></span>  
    <span data-ttu-id="39dbe-121">在迁移过程中, 如果将某些功能迁移到 Lync Server 2013 且其他功能仍保留在以前版本的 Office 通信服务器 2007 R2 中, 则迁移期间存在的临时环境。</span><span class="sxs-lookup"><span data-stu-id="39dbe-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Office Communications Server 2007 R2.</span></span>

<!-- end list -->

  - <span data-ttu-id="39dbe-122">*交互性*</span><span class="sxs-lookup"><span data-stu-id="39dbe-122">*interoperability*</span></span>  
    <span data-ttu-id="39dbe-123">部署在共存期间成功运行的能力。</span><span class="sxs-lookup"><span data-stu-id="39dbe-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="39dbe-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="39dbe-124">In This Section</span></span>

  - [<span data-ttu-id="39dbe-125">开始迁移之前的准备工作</span><span class="sxs-lookup"><span data-stu-id="39dbe-125">Before you begin the migration</span></span>](before-you-begin-the-migration_1.md)

  - [<span data-ttu-id="39dbe-126">迁移阶段</span><span class="sxs-lookup"><span data-stu-id="39dbe-126">Migration phases</span></span>](migration-phases_1.md)

  - [<span data-ttu-id="39dbe-127">第1阶段: 规划从 Office 通信服务器 2007 R2 迁移</span><span class="sxs-lookup"><span data-stu-id="39dbe-127">Phase 1: Plan your migration from Office Communications Server 2007 R2</span></span>](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [<span data-ttu-id="39dbe-128">第 2 阶段：准备迁移</span><span class="sxs-lookup"><span data-stu-id="39dbe-128">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration_1.md)

  - [<span data-ttu-id="39dbe-129">第3阶段: 部署 Lync Server 2013 试验池</span><span class="sxs-lookup"><span data-stu-id="39dbe-129">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [<span data-ttu-id="39dbe-130">第4阶段: 合并拓扑</span><span class="sxs-lookup"><span data-stu-id="39dbe-130">Phase 4: Merge topologies</span></span>](phase-4-merge-topologies.md)

  - [<span data-ttu-id="39dbe-131">第5阶段: 配置试行池</span><span class="sxs-lookup"><span data-stu-id="39dbe-131">Phase 5: Configure the pilot pool</span></span>](phase-5-configure-the-pilot-pool.md)

  - [<span data-ttu-id="39dbe-132">第6阶段: 将用户移动到 "引导" 池</span><span class="sxs-lookup"><span data-stu-id="39dbe-132">Phase 6: Move users to the pilot pool</span></span>](phase-6-move-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="39dbe-133">第7阶段: 将 Lync Server 2013 边缘服务器添加到试验池</span><span class="sxs-lookup"><span data-stu-id="39dbe-133">Phase 7: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="39dbe-134">第8阶段: 从试验部署迁移到生产环境</span><span class="sxs-lookup"><span data-stu-id="39dbe-134">Phase 8: Move from pilot deployment into production</span></span>](phase-8-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="39dbe-135">第9阶段: 完成迁移后任务</span><span class="sxs-lookup"><span data-stu-id="39dbe-135">Phase 9: Complete post-migration tasks</span></span>](phase-9-complete-post-migration-tasks.md)

  - [<span data-ttu-id="39dbe-136">第10阶段: 停止旧版网站</span><span class="sxs-lookup"><span data-stu-id="39dbe-136">Phase 10: Decommission legacy site</span></span>](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

