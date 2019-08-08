---
title: 迁移到 Skype for Business 服务器2019
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本部分中的主题将指导你完成迁移到 Skype for Business Server 2019 的过程。
ms.openlocfilehash: 8e58eaa3870e8149e874a1ec196a728976f429f3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237770"
---
# <a name="migration-to-skype-for-business-server-2019"></a><span data-ttu-id="1e01f-103">迁移到 Skype for Business 服务器2019</span><span class="sxs-lookup"><span data-stu-id="1e01f-103">Migration to Skype for Business Server 2019</span></span>

<span data-ttu-id="1e01f-104">本部分中的主题将指导你完成迁移到 Skype for Business Server 2019 的过程。</span><span class="sxs-lookup"><span data-stu-id="1e01f-104">The topics in this section guide you through the process of migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="1e01f-105">本文介绍将 Lync Server 2013 或 Skype for business Server 2015 迁移到 Skype for business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="1e01f-105">This article covers migrating Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1e01f-106">在整个内容中, 我们使用术语 "*旧版*" 指的是要迁移到 Skype For business server 2019 的旧版 Lync server 2013 或 skype For business server 2015。</span><span class="sxs-lookup"><span data-stu-id="1e01f-106">Throughout the content, we use the term *legacy* to refer to the legacy Lync Server 2013 or Skype for Business Server 2015 that you are migrating to Skype for Business Server 2019.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1e01f-107">本指南介绍了完成迁移的每个阶段通常需要执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="1e01f-107">This guide describes the steps generally required to accomplish each phase of migration.</span></span> <span data-ttu-id="1e01f-108">它不能解决每个可能的旧部署拓扑或每种可能的迁移方案。</span><span class="sxs-lookup"><span data-stu-id="1e01f-108">It does not address every possible legacy deployment topology or every possible migration scenario.</span></span> <span data-ttu-id="1e01f-109">因此, 你可能不需要执行所述的每个步骤, 或者你可能需要执行其他步骤, 具体取决于你的部署。</span><span class="sxs-lookup"><span data-stu-id="1e01f-109">Therefore, you may not need to perform every step described, or you may need to perform additional steps, depending on your deployment.</span></span> <span data-ttu-id="1e01f-110">本指南还提供了验证步骤的示例。</span><span class="sxs-lookup"><span data-stu-id="1e01f-110">This guide also provides examples of verification steps.</span></span> <span data-ttu-id="1e01f-111">提供这些验证步骤旨在帮助你了解需要查找的内容, 以确保每个阶段在你的迁移过程中成功完成。</span><span class="sxs-lookup"><span data-stu-id="1e01f-111">These verification steps are provided to help you understand what you need to look for to ensure that each phase completes successfully as you progress through your migration.</span></span> <span data-ttu-id="1e01f-112">将这些验证步骤定制到特定迁移过程。</span><span class="sxs-lookup"><span data-stu-id="1e01f-112">Tailor these verification steps to your specific migration process.</span></span> 
  
<span data-ttu-id="1e01f-113">本指南提供有关升级现有部署的特定信息。</span><span class="sxs-lookup"><span data-stu-id="1e01f-113">This guide provides information specific to upgrading your existing deployment.</span></span> <span data-ttu-id="1e01f-114">它不介绍如何更改现有拓扑。</span><span class="sxs-lookup"><span data-stu-id="1e01f-114">It does not explain how to change your existing topology.</span></span> <span data-ttu-id="1e01f-115">本指南不介绍新功能的实现。</span><span class="sxs-lookup"><span data-stu-id="1e01f-115">This guide does not cover the implementation of new features.</span></span> <span data-ttu-id="1e01f-116">当详细过程记录在其他位置时, 本指南将指导你查看文章或文章部分。</span><span class="sxs-lookup"><span data-stu-id="1e01f-116">When a detailed procedure is documented elsewhere, this guide directs you to the article or article section.</span></span> 
  
<span data-ttu-id="1e01f-117">本文将根据下表中的指定来定义术语。</span><span class="sxs-lookup"><span data-stu-id="1e01f-117">This article defines terms as specified in the following list.</span></span>
  
<span data-ttu-id="1e01f-118">**迁移:** 将生产部署从 Lync Server 2013 或 Skype for business Server 2015 移动到 Skype for business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="1e01f-118">**migration:** Moving your production deployment from Lync Server 2013 or Skype for Business Server 2015 to Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="1e01f-119">**共存:** 在迁移过程中, 当某些功能迁移到 Skype for business Server 2019 且其他功能仍在以前的版本上时, 在迁移期间存在的临时环境。</span><span class="sxs-lookup"><span data-stu-id="1e01f-119">**coexistence:** The temporary environment that exists during migration when some functionality has been migrated to Skype for Business Server 2019 and other functionality still remains on a prior version.</span></span>
    
<span data-ttu-id="1e01f-120">**互操作性:** 部署在共存期间成功运行的能力。</span><span class="sxs-lookup"><span data-stu-id="1e01f-120">**interoperability:** The ability of your deployment to operate successfully during the period of coexistence.</span></span>

<span data-ttu-id="1e01f-121">**旧版:** 您要从中迁移的系统, 即 Lync Server 2013 或 Skype for business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="1e01f-121">**legacy:** The system you are migrating away from, which is either Lync Server 2013 or Skype for Business Server 2015.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="1e01f-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="1e01f-122">In this section</span></span>

- [<span data-ttu-id="1e01f-123">开始迁移之前的准备工作</span><span class="sxs-lookup"><span data-stu-id="1e01f-123">Before you begin the migration</span></span>](before-you-begin-the-migration.md)
    
- [<span data-ttu-id="1e01f-124">第 1 阶段：规划迁移</span><span class="sxs-lookup"><span data-stu-id="1e01f-124">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
- [<span data-ttu-id="1e01f-125">第 2 阶段：准备迁移</span><span class="sxs-lookup"><span data-stu-id="1e01f-125">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
- [<span data-ttu-id="1e01f-126">第 3 阶段：部署试点池</span><span class="sxs-lookup"><span data-stu-id="1e01f-126">Phase 3: Deploy pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
- [<span data-ttu-id="1e01f-127">第4阶段: 将测试用户移动到试验池</span><span class="sxs-lookup"><span data-stu-id="1e01f-127">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [<span data-ttu-id="1e01f-128">第 5 阶段：在试点池中添加 Edge Server</span><span class="sxs-lookup"><span data-stu-id="1e01f-128">Phase 5: Add Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
- [<span data-ttu-id="1e01f-129">第 6 阶段：从试点部署移动到生产中</span><span class="sxs-lookup"><span data-stu-id="1e01f-129">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
- [<span data-ttu-id="1e01f-130">第 7 阶段：完成迁移后任务</span><span class="sxs-lookup"><span data-stu-id="1e01f-130">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
- [<span data-ttu-id="1e01f-131">第 8 阶段：停用旧池</span><span class="sxs-lookup"><span data-stu-id="1e01f-131">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

