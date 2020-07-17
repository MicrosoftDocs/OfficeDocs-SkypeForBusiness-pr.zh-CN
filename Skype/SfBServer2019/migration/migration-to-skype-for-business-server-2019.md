---
title: 迁移到 Skype for Business Server 2019
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本节中的主题将指导您完成迁移到 Skype for business Server 2019 的过程。
ms.openlocfilehash: 860fce550de33ed726bbbe723c8c7677ff09fc1c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752614"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="b03f7-103">迁移到 Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="b03f7-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="b03f7-104">本节中的主题将指导您完成迁移到 Skype for business Server 2019 的过程。</span><span class="sxs-lookup"><span data-stu-id="b03f7-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="b03f7-105">本文介绍了如何将 Lync Server 2013 或 Skype for business Server 2015 迁移到 Skype for Business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="b03f7-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b03f7-106">在整个内容中，我们使用*旧式的旧版*Lync server 2013 或 skype For business server 2015 迁移到 Skype For business server 2019。</span><span class="sxs-lookup"><span data-stu-id="b03f7-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b03f7-107">本指南介绍了完成每个迁移阶段通常需要执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="b03f7-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="b03f7-108">它并非适用于每种可能的旧部署拓扑或每种可能的迁移方案。</span><span class="sxs-lookup"><span data-stu-id="b03f7-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="b03f7-109">因此，您可能不需要执行所述的每个步骤，也可能需要执行额外步骤，具体取决于您的部署。</span><span class="sxs-lookup"><span data-stu-id="b03f7-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="b03f7-110">本指南还提供了验证步骤的示例。</span><span class="sxs-lookup"><span data-stu-id="b03f7-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="b03f7-111">提供这些验证步骤是为了帮助您了解需要查看哪些内容，以确保执行迁移时每个阶段都成功完成。</span><span class="sxs-lookup"><span data-stu-id="b03f7-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="b03f7-112">请根据您的特定迁移过程定制这些验证步骤。</span><span class="sxs-lookup"><span data-stu-id="b03f7-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="b03f7-113">本指南提供专用于升级现有部署的信息。</span><span class="sxs-lookup"><span data-stu-id="b03f7-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="b03f7-114">它未解释如何更改现有拓扑。</span><span class="sxs-lookup"><span data-stu-id="b03f7-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="b03f7-115">本指南不涉及新功能的实现。</span><span class="sxs-lookup"><span data-stu-id="b03f7-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="b03f7-116">在其他地方记录详细过程时，本指南将指导您使用文章或文章部分。</span><span class="sxs-lookup"><span data-stu-id="b03f7-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="b03f7-117">本文定义了以下列表中指定的术语。</span><span class="sxs-lookup"><span data-stu-id="b03f7-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="b03f7-118">**迁移：** 将你的生产部署从 Lync Server 2013 或 Skype for business Server 2015 迁移到 Skype for business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="b03f7-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="b03f7-119">**共存：** 在迁移过程中，如果将某些功能迁移到 Skype for business Server 2019，并且其他功能仍保留在以前的版本中，则在迁移过程中存在的临时环境。</span><span class="sxs-lookup"><span data-stu-id="b03f7-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="b03f7-120">**互操作性：** 您的部署在共存期间成功运行的能力。</span><span class="sxs-lookup"><span data-stu-id="b03f7-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="b03f7-121">**旧版：** 您要从中迁移的系统，即 Lync Server 2013 或 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="b03f7-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="b03f7-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="b03f7-122">In this section</span></span>

- [<span data-ttu-id="b03f7-123">开始迁移之前的准备工作</span><span class="sxs-lookup"><span data-stu-id="b03f7-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="b03f7-124">第 1 阶段：规划迁移</span><span class="sxs-lookup"><span data-stu-id="b03f7-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="b03f7-125">第 2 阶段：准备迁移</span><span class="sxs-lookup"><span data-stu-id="b03f7-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="b03f7-126">第 3 阶段：部署试点池</span><span class="sxs-lookup"><span data-stu-id="b03f7-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="b03f7-127">第4阶段：将测试用户移动到引导池</span><span class="sxs-lookup"><span data-stu-id="b03f7-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="b03f7-128">第 5 阶段：在试点池中添加 Edge Server</span><span class="sxs-lookup"><span data-stu-id="b03f7-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="b03f7-129">第 6 阶段：从试点部署移动到生产中</span><span class="sxs-lookup"><span data-stu-id="b03f7-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="b03f7-130">第 7 阶段：完成迁移后任务</span><span class="sxs-lookup"><span data-stu-id="b03f7-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="b03f7-131">第 8 阶段：停用旧池</span><span class="sxs-lookup"><span data-stu-id="b03f7-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

