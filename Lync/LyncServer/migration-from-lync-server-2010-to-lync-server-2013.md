---
title: 从 Lync Server 2010 迁移到 Lync Server 2013
description: 从 Lync Server 2010 迁移到 Lync Server 2013。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbe1bc1b7745c5ddc89a7f8fb64295a82f52c9bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543198"
---
# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a><span data-ttu-id="2c539-103">从 Lync Server 2010 迁移到 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c539-103">Migration from Lync Server 2010 to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c539-104">_**上次修改的主题：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="2c539-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="2c539-105">本节中的主题将指导您完成从 Lync Server 2010 迁移到 Lync Server 2013 的过程。</span><span class="sxs-lookup"><span data-stu-id="2c539-105">The topics in this section guide you through the process of migrating from Lync Server 2010 to Lync Server 2013.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2c539-p101">本文档介绍完成迁移的每个阶段通常需要执行的步骤。它并非适用于每种可能的旧部署拓扑或每种可能的迁移方案。因此，您可能不需要执行所述的每个步骤，也可能需要执行额外步骤，具体取决于您的部署。本文档还提供了验证步骤的示例。提供这些验证步骤是为了帮助您了解需要查看哪些内容，以确保执行迁移时每个阶段都成功完成。请根据您的特定迁移过程定制这些验证步骤。</span><span class="sxs-lookup"><span data-stu-id="2c539-p101">This document describes the steps generally required to accomplish each phase of migration. It does not address every possible legacy deployment topology or every possible migration scenario. Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment. This document also provides examples of verification steps. These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration. Tailor these verification steps to your specific migration process.</span></span>



</div>

<span data-ttu-id="2c539-p102">本指南提供专用于升级现有部署的信息。它未解释如何更改现有拓扑。本指南不涉及新功能的实现。如果本指南中的某个过程已在其他文档中得到详细说明，本指南将为您指出相应的文档名称或文档章节。</span><span class="sxs-lookup"><span data-stu-id="2c539-p102">This guide provides information specific to upgrading your existing deployment. It does not explain how to change your existing topology. This guide does not cover the implementation of new features. When a detailed procedure is documented elsewhere, this guide directs you to the appropriate document or document section.</span></span>

<span data-ttu-id="2c539-116">在本文档中，术语的定义如以下列表所示。</span><span class="sxs-lookup"><span data-stu-id="2c539-116">This document defines terms as specified in the following list.</span></span>

  - <span data-ttu-id="2c539-117">*迁移*</span><span class="sxs-lookup"><span data-stu-id="2c539-117">*migration*</span></span>  
    <span data-ttu-id="2c539-118">将你的生产部署从以前版本的 Lync Server 2010 迁移到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="2c539-118">Moving your production deployment from a previous version of Lync Server 2010 to Lync Server 2013.</span></span>

<!-- end list -->

  - <span data-ttu-id="2c539-119">*升级*</span><span class="sxs-lookup"><span data-stu-id="2c539-119">*upgrade*</span></span>  
    <span data-ttu-id="2c539-120">在服务器或客户端计算机上安装软件的更高版本。</span><span class="sxs-lookup"><span data-stu-id="2c539-120">Installing a newer version of software on a server or client computer.</span></span>

<!-- end list -->

  - <span data-ttu-id="2c539-121">*共存*</span><span class="sxs-lookup"><span data-stu-id="2c539-121">*coexistence*</span></span>  
    <span data-ttu-id="2c539-122">在迁移过程中，如果将某些功能迁移到 Lync Server 2013，并且其他功能仍保留在以前版本的 Lync Server 2010 中，则在迁移过程中存在的临时环境。</span><span class="sxs-lookup"><span data-stu-id="2c539-122">The temporary environment that exists during migration when some functionality has been migrated to Lync Server 2013 and other functionality still remains on a prior version of Lync Server 2010.</span></span>

<!-- end list -->

  - <span data-ttu-id="2c539-123">*相互*</span><span class="sxs-lookup"><span data-stu-id="2c539-123">*interoperability*</span></span>  
    <span data-ttu-id="2c539-124">在共存阶段部署能够正常运行的能力。</span><span class="sxs-lookup"><span data-stu-id="2c539-124">The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2c539-125">本节内容</span><span class="sxs-lookup"><span data-stu-id="2c539-125">In This Section</span></span>

  - [<span data-ttu-id="2c539-126">开始迁移之前的准备工作</span><span class="sxs-lookup"><span data-stu-id="2c539-126">Before you begin the migration</span></span>](before-you-begin-the-migration.md)

  - [<span data-ttu-id="2c539-127">第1阶段：从 Lync Server 2010 规划迁移</span><span class="sxs-lookup"><span data-stu-id="2c539-127">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [<span data-ttu-id="2c539-128">第 2 阶段：准备迁移</span><span class="sxs-lookup"><span data-stu-id="2c539-128">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

  - [<span data-ttu-id="2c539-129">第3阶段：部署 Lync Server 2013 试点池</span><span class="sxs-lookup"><span data-stu-id="2c539-129">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="2c539-130">第4阶段：将测试用户移动到引导池</span><span class="sxs-lookup"><span data-stu-id="2c539-130">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

  - [<span data-ttu-id="2c539-131">第5阶段：将 Lync Server 2013 边缘服务器添加到引导池</span><span class="sxs-lookup"><span data-stu-id="2c539-131">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [<span data-ttu-id="2c539-132">第 6 阶段：从试点部署移动到生产中</span><span class="sxs-lookup"><span data-stu-id="2c539-132">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

  - [<span data-ttu-id="2c539-133">第 7 阶段：完成迁移后任务</span><span class="sxs-lookup"><span data-stu-id="2c539-133">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

  - [<span data-ttu-id="2c539-134">第 8 阶段：停用旧池</span><span class="sxs-lookup"><span data-stu-id="2c539-134">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

