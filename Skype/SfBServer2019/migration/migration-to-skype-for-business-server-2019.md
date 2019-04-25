---
title: 迁移到 Skype 业务服务器 2019
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本节中的主题将指导您完成的迁移到 Skype for Business Server 2019 过程。
ms.openlocfilehash: 32babd6fedd5defc756f73bbf001716c7c0b8a72
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231607"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="3297d-103">迁移到 Skype 业务服务器 2019</span><span class="sxs-lookup"><span data-stu-id="3297d-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="3297d-104">本节中的主题将指导您完成的迁移到 Skype for Business Server 2019 过程。</span><span class="sxs-lookup"><span data-stu-id="3297d-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="3297d-105">本文介绍了迁移的 Lync Server 2013 或 Skype 的业务服务器 2015 到 Skype 的业务服务器 2019年。</span><span class="sxs-lookup"><span data-stu-id="3297d-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3297d-106">整个内容，我们使用术语*旧*引用旧式 Lync Server 2013 或 Skype 的要在业务服务器 2019年到 Skype 迁移的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="3297d-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3297d-107">本指南介绍通常所需完成迁移的每个阶段的步骤。</span><span class="sxs-lookup"><span data-stu-id="3297d-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="3297d-108">它不讨论每个可能的旧部署拓扑或每个可能的迁移方案。</span><span class="sxs-lookup"><span data-stu-id="3297d-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="3297d-109">因此，您可能不需要执行每个步骤所述，或需要执行附加步骤，具体取决于您的部署。</span><span class="sxs-lookup"><span data-stu-id="3297d-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="3297d-110">本指南还提供了示例验证步骤。</span><span class="sxs-lookup"><span data-stu-id="3297d-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="3297d-111">以下验证步骤提供可帮助您了解您需要查找以确保的每个阶段完成成功进行的迁移。</span><span class="sxs-lookup"><span data-stu-id="3297d-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="3297d-112">定制到特定的迁移过程以下验证步骤。</span><span class="sxs-lookup"><span data-stu-id="3297d-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="3297d-113">本指南提供特定于升级现有部署的信息。</span><span class="sxs-lookup"><span data-stu-id="3297d-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="3297d-114">它并不介绍如何更改现有的拓扑。</span><span class="sxs-lookup"><span data-stu-id="3297d-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="3297d-115">本指南不涉及新功能的实现。</span><span class="sxs-lookup"><span data-stu-id="3297d-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="3297d-116">时使用的详细的过程已在其他文档，本指南可引导您对文章或文章部分。</span><span class="sxs-lookup"><span data-stu-id="3297d-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="3297d-117">本文术语的定义如以下列表中指定。</span><span class="sxs-lookup"><span data-stu-id="3297d-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="3297d-118">**迁移：** 进入生产部署从 Lync Server 2013 或 Skype 的业务服务器 2015 Skype 的业务服务器 2019年。</span><span class="sxs-lookup"><span data-stu-id="3297d-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="3297d-119">**共存：** 某些功能已迁移至 Skype 业务服务器 2019年和其他功能迁移期间存在的临时环境仍保留在早期版本上。</span><span class="sxs-lookup"><span data-stu-id="3297d-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="3297d-120">**互操作性：** 成功运行共存阶段部署的功能。</span><span class="sxs-lookup"><span data-stu-id="3297d-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="3297d-121">**旧：** 系统进行迁移时远离，这 Lync Server 2013 或业务服务器 2015年的 Skype。</span><span class="sxs-lookup"><span data-stu-id="3297d-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="3297d-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="3297d-122">In this section</span></span>

- [<span data-ttu-id="3297d-123">开始迁移之前的准备工作</span><span class="sxs-lookup"><span data-stu-id="3297d-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="3297d-124">第 1 阶段：规划迁移</span><span class="sxs-lookup"><span data-stu-id="3297d-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="3297d-125">第 2 阶段：准备迁移</span><span class="sxs-lookup"><span data-stu-id="3297d-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="3297d-126">第 3 阶段：部署试点池</span><span class="sxs-lookup"><span data-stu-id="3297d-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="3297d-127">第 4 阶段： 将测试用户移至试点池</span><span class="sxs-lookup"><span data-stu-id="3297d-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="3297d-128">第 5 阶段：在试点池中添加 Edge Server</span><span class="sxs-lookup"><span data-stu-id="3297d-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="3297d-129">第 6 阶段：从试点部署移动到生产中</span><span class="sxs-lookup"><span data-stu-id="3297d-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="3297d-130">第 7 阶段：完成迁移后任务</span><span class="sxs-lookup"><span data-stu-id="3297d-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="3297d-131">第 8 阶段：停用旧池</span><span class="sxs-lookup"><span data-stu-id="3297d-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

