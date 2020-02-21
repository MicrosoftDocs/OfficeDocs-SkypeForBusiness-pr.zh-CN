---
title: 从 Office Communications Server 2007 R2 迁移至 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 344f15589e113a54b539d351ed8d4745e1fd3a5b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a><span data-ttu-id="21a22-102">从 Office Communications Server 2007 R2 迁移至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21a22-102">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21a22-103">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="21a22-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="21a22-104">本节中的主题将指导您完成从 Office 通信服务器 2007 R2 迁移到 Lync Server 2013 的过程</span><span class="sxs-lookup"><span data-stu-id="21a22-104">The topics in this section guide you through the process of migrating from Office Communications Server 2007 R2 to Lync Server 2013</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="21a22-p101">本文档介绍完成迁移的每个阶段通常需要执行的步骤。它并非适用于每种可能的旧部署拓扑或每种可能的迁移方案。因此，您可能不需要执行所述的每个步骤，也可能需要执行额外步骤，具体取决于您的部署。本文档还提供了验证步骤的示例。提供这些验证步骤是为了帮助您了解需要查看哪些内容，以确保执行迁移时每个阶段都成功完成。请根据您的特定迁移过程定制这些验证步骤。</span><span class="sxs-lookup"><span data-stu-id="21a22-p101">This document describes the steps generally required to accomplish each phase of migration. It does not address every possible legacy deployment topology or every possible migration scenario. Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment. This document also provides examples of verification steps. These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration. Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="21a22-p102">本指南提供专用于升级现有部署的信息。它未解释如何更改现有拓扑。本指南不涉及新功能的实现。如果本指南中的某个过程已在其他文档中得到详细说明，本指南将为您指出相应的文档名称或文档章节。</span><span class="sxs-lookup"><span data-stu-id="21a22-p102">This guide provides information specific to upgrading your existing deployment. It does not explain how to change your existing topology. This guide does not cover the implementation of new features. When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="21a22-115">在本文档中，术语的定义如以下列表所示。</span><span class="sxs-lookup"><span data-stu-id="21a22-115">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="21a22-116">*迁移*</span><span class="sxs-lookup"><span data-stu-id="21a22-116">*migration*</span></span>  
    <span data-ttu-id="21a22-117">将生产部署从 Office 通信服务器 2007 R2 的早期版本移动到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="21a22-117">Moving your production deployment from a previous version of Office Communications Server 2007 R2 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="21a22-118">*升级*</span><span class="sxs-lookup"><span data-stu-id="21a22-118">*upgrade*</span></span>  
    <span data-ttu-id="21a22-119">在服务器或客户端计算机上安装软件的更高版本。</span><span class="sxs-lookup"><span data-stu-id="21a22-119">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="21a22-120">*共存*</span><span class="sxs-lookup"><span data-stu-id="21a22-120">*coexistence*</span></span>  
    <span data-ttu-id="21a22-121">在迁移过程中，如果将某些功能迁移到 Lync Server 2013，并且其他功能仍保留在以前版本的 Office 通信服务器 2007 R2 中，则迁移过程中存在的临时环境。</span><span class="sxs-lookup"><span data-stu-id="21a22-121">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Office Communications Server 2007 R2.</span></span>

<!-- end list -->

  - <span data-ttu-id="21a22-122">*相互*</span><span class="sxs-lookup"><span data-stu-id="21a22-122">*interoperability*</span></span>  
    <span data-ttu-id="21a22-123">在共存阶段部署能够正常运行的能力。</span><span class="sxs-lookup"><span data-stu-id="21a22-123">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="21a22-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="21a22-124">In This Section</span></span>

  - [<span data-ttu-id="21a22-125">开始迁移之前的准备工作</span><span class="sxs-lookup"><span data-stu-id="21a22-125">Before you begin the migration</span></span>](before-you-begin-the-migration_1.md)

  - [<span data-ttu-id="21a22-126">迁移阶段</span><span class="sxs-lookup"><span data-stu-id="21a22-126">Migration phases</span></span>](migration-phases_1.md)

  - [<span data-ttu-id="21a22-127">第1阶段：规划从 Office 通信服务器 2007 R2 迁移</span><span class="sxs-lookup"><span data-stu-id="21a22-127">Phase 1: Plan your migration from Office Communications Server 2007 R2</span></span>](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [<span data-ttu-id="21a22-128">第2阶段：准备迁移</span><span class="sxs-lookup"><span data-stu-id="21a22-128">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration_1.md)

  - [<span data-ttu-id="21a22-129">第3阶段：部署 Lync Server 2013 试点池</span><span class="sxs-lookup"><span data-stu-id="21a22-129">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [<span data-ttu-id="21a22-130">第4阶段：合并拓扑</span><span class="sxs-lookup"><span data-stu-id="21a22-130">Phase 4: Merge topologies</span></span>](phase-4-merge-topologies.md)

  - [<span data-ttu-id="21a22-131">第5阶段：配置引导池</span><span class="sxs-lookup"><span data-stu-id="21a22-131">Phase 5: Configure the pilot pool</span></span>](phase-5-configure-the-pilot-pool.md)

  - [<span data-ttu-id="21a22-132">第6阶段：将用户移动到引导池</span><span class="sxs-lookup"><span data-stu-id="21a22-132">Phase 6: Move users to the pilot pool</span></span>](phase-6-move-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="21a22-133">第7阶段：将 Lync Server 2013 边缘服务器添加到引导池</span><span class="sxs-lookup"><span data-stu-id="21a22-133">Phase 7: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="21a22-134">第8阶段：从试点部署移动到生产环境</span><span class="sxs-lookup"><span data-stu-id="21a22-134">Phase 8: Move from pilot deployment into production</span></span>](phase-8-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="21a22-135">第9阶段：完成迁移后任务</span><span class="sxs-lookup"><span data-stu-id="21a22-135">Phase 9: Complete post-migration tasks</span></span>](phase-9-complete-post-migration-tasks.md)

  - [<span data-ttu-id="21a22-136">阶段10：停止旧版网站</span><span class="sxs-lookup"><span data-stu-id="21a22-136">Phase 10: Decommission legacy site</span></span>](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

