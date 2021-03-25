---
title: 实现移动到 Microsoft Teams
author: Benny-54
ms.author: v-bshilpa
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 本文介绍如何部署和实施 Microsoft Teams。
f1.keywords: ''
localization_priority: Normal
search.appverid: ''
ms.collection: ''
ms.custom: ''
ms.openlocfilehash: 678cad1b71c9f3e8d1e79a50f5ae46aba4456b5a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120663"
---
# <a name="implement-your-move-to-microsoft-teams"></a><span data-ttu-id="4c74b-103">实现移动到 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4c74b-103">Implement your move to Microsoft Teams</span></span>

<span data-ttu-id="4c74b-104">本文提供有关以下方案的 Microsoft Teams 部署和实施的指导：</span><span class="sxs-lookup"><span data-stu-id="4c74b-104">This article provides your guidance on deployment and implementation of Microsoft Teams for the following scenarios:</span></span>

1. <span data-ttu-id="4c74b-105">对于已 **使用 Microsoft Teams 的组织**</span><span class="sxs-lookup"><span data-stu-id="4c74b-105">For organizations **already using Microsoft Teams**</span></span>
2. <span data-ttu-id="4c74b-106">对于 **尚未使用 Microsoft Teams 的组织**</span><span class="sxs-lookup"><span data-stu-id="4c74b-106">For organizations **not yet using Microsoft Teams**</span></span>

## <a name="deploying-and-implementing-microsoft-teams-for-organizations-already-using-microsoft-teams"></a><span data-ttu-id="4c74b-107">为已使用 Microsoft Teams 的组织部署和实施 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4c74b-107">Deploying and implementing Microsoft Teams for organizations already using Microsoft Teams</span></span>
 
<span data-ttu-id="4c74b-108">在继续之前，请确认已经完成了以下活动:</span><span class="sxs-lookup"><span data-stu-id="4c74b-108">Before proceeding, confirm that you've completed the following activities:</span></span> 

- <span data-ttu-id="4c74b-109">为组织设想的团队协作</span><span class="sxs-lookup"><span data-stu-id="4c74b-109">Envisioned teamwork for your organization</span></span>  
- <span data-ttu-id="4c74b-110">确定的支持方和关键利益干系人</span><span class="sxs-lookup"><span data-stu-id="4c74b-110">Identified champions and critical stakeholders</span></span> 
- <span data-ttu-id="4c74b-111">请确定项目范围</span><span class="sxs-lookup"><span data-stu-id="4c74b-111">Defined your project scope</span></span>  
- <span data-ttu-id="4c74b-112">试点 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4c74b-112">Piloted Microsoft Teams</span></span> 
- <span data-ttu-id="4c74b-113">准备组织</span><span class="sxs-lookup"><span data-stu-id="4c74b-113">Prepared your organization</span></span> 

<span data-ttu-id="4c74b-114">如果已推出 **Microsoft Teams，** 并且想要将许可用户从 Kaizala 移到 Microsoft Teams，请遵循本文中的指导。</span><span class="sxs-lookup"><span data-stu-id="4c74b-114">Follow the guidance in this article, if you **already have Microsoft Teams rolled out** and want to move your licensed users from Kaizala to Microsoft Teams.</span></span> 
   
<span data-ttu-id="4c74b-115">我们建议采用以下过渡框架：</span><span class="sxs-lookup"><span data-stu-id="4c74b-115">We recommend the following framework for transition:</span></span>  
   
<span data-ttu-id="4c74b-116">**规划过渡**</span><span class="sxs-lookup"><span data-stu-id="4c74b-116">**Plan for your transition**</span></span> 
   
1. <span data-ttu-id="4c74b-117">首先，将聊天组移动到 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="4c74b-117">First, move your chat groups to Microsoft Teams.</span></span>
1. <span data-ttu-id="4c74b-118">接下来，使用 Teams 中的应用替换 Kaizala 操作卡。</span><span class="sxs-lookup"><span data-stu-id="4c74b-118">Next, use apps in Teams to replace Kaizala action cards.</span></span>
1. <span data-ttu-id="4c74b-119">若要确保一线员工已配备，请升级到 Teams 一线辅助角色功能。</span><span class="sxs-lookup"><span data-stu-id="4c74b-119">To ensure that frontline workers are equipped, upgrade to Teams Frontline Worker functionality.</span></span> <span data-ttu-id="4c74b-120">有关 Teams 前端辅助角色的快速入门指南，请参阅 [一线员工快速入门指南](./flw-quickstart.yml)。</span><span class="sxs-lookup"><span data-stu-id="4c74b-120">For a quick start guide on Teams Frontline Worker, see [Frontline Worker Quick Start Guide](./flw-quickstart.yml).</span></span>
1. <span data-ttu-id="4c74b-121">考虑加入供应商和合作伙伴，邀请他们作为来宾加入 Teams。</span><span class="sxs-lookup"><span data-stu-id="4c74b-121">Consider Onboarding suppliers and partners to invite as guests in Teams.</span></span>  
  
<span data-ttu-id="4c74b-122">**管理更改**</span><span class="sxs-lookup"><span data-stu-id="4c74b-122">**Manage change**</span></span>  
   
1. <span data-ttu-id="4c74b-123">创建一个沟通活动，以提高对过渡项目的认知。</span><span class="sxs-lookup"><span data-stu-id="4c74b-123">Create a communication campaign to raise awareness on the transition project.</span></span> 
1. <span data-ttu-id="4c74b-124">将更改通知组织，并确定推动 Microsoft Teams 采用率的冠军。</span><span class="sxs-lookup"><span data-stu-id="4c74b-124">Notify your organization of the change and identify champions to drive adoption of Microsoft Teams.</span></span> 
1. <span data-ttu-id="4c74b-125">允许用户通过免费培训了解有关 Microsoft Teams 的更多内容。</span><span class="sxs-lookup"><span data-stu-id="4c74b-125">Empower your users to learn more about Microsoft Teams through free training.</span></span> 
   
<span data-ttu-id="4c74b-126">若要了解有关详细信息，请参阅 [Microsoft Teams 视频培训](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7?ui=en-us&rs=en-us&ad=us)。</span><span class="sxs-lookup"><span data-stu-id="4c74b-126">To learn more, see [Microsoft Teams video training](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7?ui=en-us&rs=en-us&ad=us).</span></span>   
 
## <a name="deploying-and-implementing-microsoft-teams-for-organizations-not-yet-using-microsoft-teams"></a><span data-ttu-id="4c74b-127">为尚未使用 Microsoft Teams 的组织部署和实施 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4c74b-127">Deploying and implementing Microsoft Teams for organizations not yet using Microsoft Teams</span></span>
 
<span data-ttu-id="4c74b-128">如果使用的是 Kaizala，并且想要将用户从 Kaizala 移动到 Microsoft Teams，请遵循本部分中的指导。</span><span class="sxs-lookup"><span data-stu-id="4c74b-128">Follow the guidance in this section, if you're using Kaizala and want to move your users from Kaizala to Microsoft Teams.</span></span>
   
<span data-ttu-id="4c74b-129">**在继续之前，请确认已完成以下活动**：</span><span class="sxs-lookup"><span data-stu-id="4c74b-129">**Before proceeding, confirm that you've completed the following activities**:</span></span> 
   
- <span data-ttu-id="4c74b-130">为组织设想的团队协作</span><span class="sxs-lookup"><span data-stu-id="4c74b-130">Envisioned teamwork for your organization</span></span> 
- <span data-ttu-id="4c74b-131">确定的支持方和关键利益干系人</span><span class="sxs-lookup"><span data-stu-id="4c74b-131">Identified champions and critical stakeholders</span></span> 
- <span data-ttu-id="4c74b-132">请确定项目范围</span><span class="sxs-lookup"><span data-stu-id="4c74b-132">Defined your project scope</span></span>  
- <span data-ttu-id="4c74b-133">试点 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4c74b-133">Piloted Microsoft Teams</span></span>
- <span data-ttu-id="4c74b-134">准备组织</span><span class="sxs-lookup"><span data-stu-id="4c74b-134">Prepared your organization</span></span>  
   
<span data-ttu-id="4c74b-135">我们建议采用以下过渡框架：</span><span class="sxs-lookup"><span data-stu-id="4c74b-135">We recommend the following framework for transition:</span></span> 
   
- <span data-ttu-id="4c74b-136">**为组织构想团队合作**</span><span class="sxs-lookup"><span data-stu-id="4c74b-136">**Envision teamwork for your organization**</span></span> 
   
   <span data-ttu-id="4c74b-137">列出使用 Kaizala 的当前方案。</span><span class="sxs-lookup"><span data-stu-id="4c74b-137">List the current scenarios in which Kaizala is used.</span></span> <span data-ttu-id="4c74b-138">接下来，设想 Microsoft Teams 的上述方案。</span><span class="sxs-lookup"><span data-stu-id="4c74b-138">Next, envision scenarios above and beyond with Microsoft Teams.</span></span>  

- <span data-ttu-id="4c74b-139">**试点团队**</span><span class="sxs-lookup"><span data-stu-id="4c74b-139">**Pilot Teams**</span></span>

   <span data-ttu-id="4c74b-140">向具有优先方案集的试点用户组推出 Teams。</span><span class="sxs-lookup"><span data-stu-id="4c74b-140">Roll out Teams to a Pilot group of users with a prioritized scenario set.</span></span> 

- <span data-ttu-id="4c74b-141">**部署 Teams**</span><span class="sxs-lookup"><span data-stu-id="4c74b-141">**Deploy Teams**</span></span> 

   <span data-ttu-id="4c74b-142">从试点组学习。</span><span class="sxs-lookup"><span data-stu-id="4c74b-142">Learn from the pilot group.</span></span> <span data-ttu-id="4c74b-143">准备向整个组织推出。</span><span class="sxs-lookup"><span data-stu-id="4c74b-143">Prepare to roll out to the complete organization.</span></span>  

- <span data-ttu-id="4c74b-144">**使用 Kaizala 和 Teams**</span><span class="sxs-lookup"><span data-stu-id="4c74b-144">**Use Kaizala and Teams**</span></span>  

   <span data-ttu-id="4c74b-145">若要查找适合你的企业正确的 Microsoft Teams，请参阅[比较 Microsoft Teams Online 选项|Microsoft Teams。](https://www.microsoft.com/microsoft-teams/compare-microsoft-teams-options)</span><span class="sxs-lookup"><span data-stu-id="4c74b-145">To find the right Microsoft Teams for your business, see [Compare Microsoft Teams Online Options | Microsoft Teams](https://www.microsoft.com/microsoft-teams/compare-microsoft-teams-options).</span></span> 

- <span data-ttu-id="4c74b-146">**管理更改**</span><span class="sxs-lookup"><span data-stu-id="4c74b-146">**Manage change**</span></span> 

   <span data-ttu-id="4c74b-147">通过最终用户培训让组织准备好进行变更，推动采用。</span><span class="sxs-lookup"><span data-stu-id="4c74b-147">Prepare your organization for change through end-user training to drive adoption.</span></span> <span data-ttu-id="4c74b-148">IT 管理员和冠军可以推动工作，以在移动时影响积极的更改管理。</span><span class="sxs-lookup"><span data-stu-id="4c74b-148">IT Admins and Champions can drive efforts to influence positive change management on the move.</span></span>  

- <span data-ttu-id="4c74b-149">**规划 Teams 的采用**</span><span class="sxs-lookup"><span data-stu-id="4c74b-149">**Plan for your adoption of Teams**</span></span>

    <span data-ttu-id="4c74b-150">准备将自定义解决方案从 Kaizala 移动到 Teams，例如自定义操作卡片。</span><span class="sxs-lookup"><span data-stu-id="4c74b-150">Prepare to move custom solutions from Kaizala to Teams, for example, Custom Action cards.</span></span> 
     
- <span data-ttu-id="4c74b-151">**将组织移动到 Teams**</span><span class="sxs-lookup"><span data-stu-id="4c74b-151">**Move your organization to Teams**</span></span> 

    <span data-ttu-id="4c74b-152">为组织提供简化的工具，以从 CEO 到一线通信！</span><span class="sxs-lookup"><span data-stu-id="4c74b-152">Empower your organization with a streamlined tool for communication from CEO to the frontline!</span></span>