---
title: 使用管理中心Teams财务模板入门
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
description: 了解如何使用。 Teams模板，通过使用管理中心提供预定义的设置、通道和预安装的应用，创建专为财务需求设计的团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fd7c6fa61f7c929e198440b574b6bb10db7370d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092470"
---
# <a name="use-teams-financial-templates-in-the-admin-center"></a><span data-ttu-id="1619c-104">使用Teams管理中心中的财务模板</span><span class="sxs-lookup"><span data-stu-id="1619c-104">Use Teams financial templates in the admin center</span></span>

<span data-ttu-id="1619c-105">Teams 模板提供预定义的设置、频道和预安装的应用模板，让你能够快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="1619c-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="1619c-106">Teams模板具有围绕财务需求设计的团队结构的预生成定义。</span><span class="sxs-lookup"><span data-stu-id="1619c-106">Teams templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="1619c-107">你还可以扩展 Teams 模板，以创建根据特定组织需求量身定制的团队。</span><span class="sxs-lookup"><span data-stu-id="1619c-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="1619c-108">在本文中，我们将介绍各个 Teams 模板，并推荐其使用方法。</span><span class="sxs-lookup"><span data-stu-id="1619c-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="1619c-109">如果你负责规划、部署和管理整个财务组织的多个团队，则本文适合你。</span><span class="sxs-lookup"><span data-stu-id="1619c-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="1619c-110">你已在贵组织内部署 Teams 服务。</span><span class="sxs-lookup"><span data-stu-id="1619c-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="1619c-111">如果尚未部署 Teams，首先请阅读[如何部署 Microsoft Teams](./deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="1619c-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="1619c-112">若要了解有关常规团队模板的详细信息，请参阅[开始使用 Teams 模板](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="1619c-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="1619c-113">全球问题或事件</span><span class="sxs-lookup"><span data-stu-id="1619c-113">Global crisis or event</span></span>

<span data-ttu-id="1619c-114">跨业务部门集中协作，帮助创建业务连续性计划、共享远程工作技巧、跟踪客户通信，以及让每个人都随时了解公告和新闻。</span><span class="sxs-lookup"><span data-stu-id="1619c-114">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="1619c-115">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="1619c-115">Base template type</span></span>|<span data-ttu-id="1619c-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="1619c-116">baseTemplateId</span></span> | <span data-ttu-id="1619c-117">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="1619c-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="1619c-118">协作解决全球问题或事件</span><span class="sxs-lookup"><span data-stu-id="1619c-118">Collaborate on global crisis or event</span></span>|`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="1619c-119">频道：</span><span class="sxs-lookup"><span data-stu-id="1619c-119">Channels:</span></span> <ul><li><span data-ttu-id="1619c-120">常规</span><span class="sxs-lookup"><span data-stu-id="1619c-120">General</span></span><li><span data-ttu-id="1619c-121">公告</span><span class="sxs-lookup"><span data-stu-id="1619c-121">Announcements</span></span></li><li><span data-ttu-id="1619c-122">世界新闻</span><span class="sxs-lookup"><span data-stu-id="1619c-122">World news</span></span></li><li><span data-ttu-id="1619c-123">业务连续性</span><span class="sxs-lookup"><span data-stu-id="1619c-123">Business continuity</span></span></li><li><span data-ttu-id="1619c-124">远程工作</span><span class="sxs-lookup"><span data-stu-id="1619c-124">Remote working</span></span></li><li><span data-ttu-id="1619c-125">内部通信</span><span class="sxs-lookup"><span data-stu-id="1619c-125">Internal comms</span></span></li><li><span data-ttu-id="1619c-126">外部通信</span><span class="sxs-lookup"><span data-stu-id="1619c-126">External comms</span></span></li><li><span data-ttu-id="1619c-127">审批请求</span><span class="sxs-lookup"><span data-stu-id="1619c-127">Approvals request</span></span></li><li><span data-ttu-id="1619c-128">客户投诉</span><span class="sxs-lookup"><span data-stu-id="1619c-128">Customer complaints</span></span></li><li><span data-ttu-id="1619c-129">Kudos</span><span class="sxs-lookup"><span data-stu-id="1619c-129">Kudos</span></span></li><li><span data-ttu-id="1619c-130">高管更新</span><span class="sxs-lookup"><span data-stu-id="1619c-130">Executive update</span></span></li></ul><span data-ttu-id="1619c-131">应用：</span><span class="sxs-lookup"><span data-stu-id="1619c-131">Apps:</span></span> <ul><li><span data-ttu-id="1619c-132">表扬</span><span class="sxs-lookup"><span data-stu-id="1619c-132">Praise</span></span></li><li><span data-ttu-id="1619c-133">Wiki</span><span class="sxs-lookup"><span data-stu-id="1619c-133">Wiki</span></span></li><li><span data-ttu-id="1619c-134">网站</span><span class="sxs-lookup"><span data-stu-id="1619c-134">Website</span></span></li><li><span data-ttu-id="1619c-135">Planner</span><span class="sxs-lookup"><span data-stu-id="1619c-135">Planner</span></span></li></ul>|
||||

## <a name="collaborate-within-a-bank-branch"></a><span data-ttu-id="1619c-136">在银行分支机构内协作</span><span class="sxs-lookup"><span data-stu-id="1619c-136">Collaborate within a bank branch</span></span>

<span data-ttu-id="1619c-137">跨 Huddles、客户会议、业务流程（如按揭协作）集中银行分支机构员工的协作，让每个人都了解公告和 Kudos。</span><span class="sxs-lookup"><span data-stu-id="1619c-137">Centralize collaboration for your bank branch employees across Huddles, Customer Meetings, Business Processes such as Mortgage Collaboration, and keep everyone in the loop with Announcements and Kudos.</span></span>

| <span data-ttu-id="1619c-138">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="1619c-138">Base template type</span></span> |<span data-ttu-id="1619c-139">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="1619c-139">baseTemplateId</span></span>| <span data-ttu-id="1619c-140">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="1619c-140">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
|<span data-ttu-id="1619c-141">在银行分支机构内协作</span><span class="sxs-lookup"><span data-stu-id="1619c-141">Collaborate within a bank branch</span></span>|`com.microsoft.teams.template.CollaborateWithinABankBranch` |<span data-ttu-id="1619c-142">频道：</span><span class="sxs-lookup"><span data-stu-id="1619c-142">Channels:</span></span> <ul><li><span data-ttu-id="1619c-143">常规</span><span class="sxs-lookup"><span data-stu-id="1619c-143">General</span></span><li><span data-ttu-id="1619c-144">公告</span><span class="sxs-lookup"><span data-stu-id="1619c-144">Announcements</span></span></li><li><span data-ttu-id="1619c-145">小型会议室</span><span class="sxs-lookup"><span data-stu-id="1619c-145">Huddles</span></span></li><li><span data-ttu-id="1619c-146">客户会议</span><span class="sxs-lookup"><span data-stu-id="1619c-146">Customer meetings</span></span></li><li><span data-ttu-id="1619c-147">审批请求</span><span class="sxs-lookup"><span data-stu-id="1619c-147">Approvals Request</span></span></li><li><span data-ttu-id="1619c-148">指导</span><span class="sxs-lookup"><span data-stu-id="1619c-148">Coaching</span></span></li><li><span data-ttu-id="1619c-149">技能开发</span><span class="sxs-lookup"><span data-stu-id="1619c-149">Skills development</span></span></li><li><span data-ttu-id="1619c-150">贷款处理</span><span class="sxs-lookup"><span data-stu-id="1619c-150">Loan processing</span></span></li><li><span data-ttu-id="1619c-151">客户投诉</span><span class="sxs-lookup"><span data-stu-id="1619c-151">Customer complaints</span></span></li><li><span data-ttu-id="1619c-152">Kudos</span><span class="sxs-lookup"><span data-stu-id="1619c-152">Kudos</span></span></li><li><span data-ttu-id="1619c-153">有趣的内容</span><span class="sxs-lookup"><span data-stu-id="1619c-153">Fun stuff</span></span></li><li><span data-ttu-id="1619c-154">合规性</span><span class="sxs-lookup"><span data-stu-id="1619c-154">Compliance</span></span></li></ul><span data-ttu-id="1619c-155">应用：</span><span class="sxs-lookup"><span data-stu-id="1619c-155">Apps:</span></span><ul><li><span data-ttu-id="1619c-156">表扬</span><span class="sxs-lookup"><span data-stu-id="1619c-156">Praise</span></span></li></ul>|
||||