---
title: 使用管理员控制台开始使用团队财务模板
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用。 团队模板，通过使用管理员控制台提供预定义的设置、信道和预安装应用来创建为财务需求设计的团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8273e63213b6a0c3d99d6ef66cb778a2541c0327
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294408"
---
# <a name="use-teams-financial-templates-in-the-admin-console"></a><span data-ttu-id="7547e-104">在管理控制台中使用团队财务模板</span><span class="sxs-lookup"><span data-stu-id="7547e-104">Use Teams financial templates in the admin console</span></span>

<span data-ttu-id="7547e-105">团队模板使你可以通过提供设置、频道和预安装应用的预定义模板来快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="7547e-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="7547e-106">团队模板具有围绕财务需求设计的团队结构的预建定义。</span><span class="sxs-lookup"><span data-stu-id="7547e-106">Teams templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="7547e-107">您还可以扩展团队模板以创建根据您的特定组织需求量身定制的团队。</span><span class="sxs-lookup"><span data-stu-id="7547e-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="7547e-108">在本文中，我们将介绍每个团队模板并建议如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="7547e-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="7547e-109">本文适用于你负责在整个财务组织中规划、部署和管理多个团队的情况。</span><span class="sxs-lookup"><span data-stu-id="7547e-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="7547e-110">你已在你的组织中部署团队服务。</span><span class="sxs-lookup"><span data-stu-id="7547e-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="7547e-111">如果尚未推出团队，请先阅读 [如何展示 Microsoft 团队](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="7547e-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="7547e-112">若要深入了解有关团队模板的详细信息，请参阅 [团队模板入门](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="7547e-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="7547e-113">全球危机或活动</span><span class="sxs-lookup"><span data-stu-id="7547e-113">Global crisis or event</span></span>

<span data-ttu-id="7547e-114">跨业务单元对危机团队协作，并帮助创建业务连续性计划、共享远程工作提示、跟踪客户通信，以及使用公告和新闻让每个人都保持联系。</span><span class="sxs-lookup"><span data-stu-id="7547e-114">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="7547e-115">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="7547e-115">Base template type</span></span>|<span data-ttu-id="7547e-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="7547e-116">baseTemplateId</span></span> | <span data-ttu-id="7547e-117">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="7547e-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="7547e-118">协作处理全球危机或活动</span><span class="sxs-lookup"><span data-stu-id="7547e-118">Collaborate on global crisis or event</span></span>|`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="7547e-119">信道</span><span class="sxs-lookup"><span data-stu-id="7547e-119">Channels:</span></span> <ul><li><span data-ttu-id="7547e-120">常规</span><span class="sxs-lookup"><span data-stu-id="7547e-120">General</span></span><li><span data-ttu-id="7547e-121">宣告</span><span class="sxs-lookup"><span data-stu-id="7547e-121">Announcements</span></span></li><li><span data-ttu-id="7547e-122">世界新闻</span><span class="sxs-lookup"><span data-stu-id="7547e-122">World news</span></span></li><li><span data-ttu-id="7547e-123">业务连续性</span><span class="sxs-lookup"><span data-stu-id="7547e-123">Business continuity</span></span></li><li><span data-ttu-id="7547e-124">远程工作</span><span class="sxs-lookup"><span data-stu-id="7547e-124">Remote working</span></span></li><li><span data-ttu-id="7547e-125">内部 comms</span><span class="sxs-lookup"><span data-stu-id="7547e-125">Internal comms</span></span></li><li><span data-ttu-id="7547e-126">外部 comms</span><span class="sxs-lookup"><span data-stu-id="7547e-126">External comms</span></span></li><li><span data-ttu-id="7547e-127">客户投诉</span><span class="sxs-lookup"><span data-stu-id="7547e-127">Customer complaints</span></span></li><li><span data-ttu-id="7547e-128">Kudos</span><span class="sxs-lookup"><span data-stu-id="7547e-128">Kudos</span></span></li><li><span data-ttu-id="7547e-129">执行更新</span><span class="sxs-lookup"><span data-stu-id="7547e-129">Executive update</span></span></li></ul><span data-ttu-id="7547e-130">识别</span><span class="sxs-lookup"><span data-stu-id="7547e-130">Apps:</span></span> <ul><li><span data-ttu-id="7547e-131">表扬</span><span class="sxs-lookup"><span data-stu-id="7547e-131">Praise</span></span></li><li><span data-ttu-id="7547e-132">源自</span><span class="sxs-lookup"><span data-stu-id="7547e-132">Wiki</span></span></li><li><span data-ttu-id="7547e-133">网站</span><span class="sxs-lookup"><span data-stu-id="7547e-133">Website</span></span></li></ul>|
||||

## <a name="collaborate-within-a-bank-branch"></a><span data-ttu-id="7547e-134">在银行分支内进行协作</span><span class="sxs-lookup"><span data-stu-id="7547e-134">Collaborate within a bank branch</span></span>

<span data-ttu-id="7547e-135">在 Huddles、客户会议、业务流程（如抵押贷款协作）中为您的银行分支员工集中协作，并通过公告和 Kudos 让每个人都参与循环。</span><span class="sxs-lookup"><span data-stu-id="7547e-135">Centralize collaboration for your bank branch employees across Huddles, Customer Meetings, Business Processes such as Mortgage Collaboration, and keep everyone in the loop with Announcements and Kudos.</span></span>

| <span data-ttu-id="7547e-136">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="7547e-136">Base template type</span></span> |<span data-ttu-id="7547e-137">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="7547e-137">baseTemplateId</span></span>| <span data-ttu-id="7547e-138">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="7547e-138">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
|<span data-ttu-id="7547e-139">在银行分支内进行协作</span><span class="sxs-lookup"><span data-stu-id="7547e-139">Collaborate within a bank branch</span></span>|`com.microsoft.teams.template.CollaborateWithinABankBranch` |<span data-ttu-id="7547e-140">信道</span><span class="sxs-lookup"><span data-stu-id="7547e-140">Channels:</span></span> <ul><li><span data-ttu-id="7547e-141">常规</span><span class="sxs-lookup"><span data-stu-id="7547e-141">General</span></span><li><span data-ttu-id="7547e-142">宣告</span><span class="sxs-lookup"><span data-stu-id="7547e-142">Announcements</span></span></li><li><span data-ttu-id="7547e-143">Huddles</span><span class="sxs-lookup"><span data-stu-id="7547e-143">Huddles</span></span></li><li><span data-ttu-id="7547e-144">客户会议</span><span class="sxs-lookup"><span data-stu-id="7547e-144">Customer meetings</span></span></li><li><span data-ttu-id="7547e-145">训练</span><span class="sxs-lookup"><span data-stu-id="7547e-145">Coaching</span></span></li><li><span data-ttu-id="7547e-146">技能发展</span><span class="sxs-lookup"><span data-stu-id="7547e-146">Skills development</span></span></li><li><span data-ttu-id="7547e-147">借贷处理</span><span class="sxs-lookup"><span data-stu-id="7547e-147">Loan processing</span></span></li><li><span data-ttu-id="7547e-148">客户投诉</span><span class="sxs-lookup"><span data-stu-id="7547e-148">Customer complaints</span></span></li><li><span data-ttu-id="7547e-149">Kudos</span><span class="sxs-lookup"><span data-stu-id="7547e-149">Kudos</span></span></li><li><span data-ttu-id="7547e-150">有趣的资料</span><span class="sxs-lookup"><span data-stu-id="7547e-150">Fun stuff</span></span></li><li><span data-ttu-id="7547e-151">合规性</span><span class="sxs-lookup"><span data-stu-id="7547e-151">Compliance</span></span></li></ul>|
||||

