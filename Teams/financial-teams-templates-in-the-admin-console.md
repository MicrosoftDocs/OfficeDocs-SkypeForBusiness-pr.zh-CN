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
description: 了解如何使用团队模板通过使用管理员控制台提供预定义的设置、信道和预安装应用来创建为财务需求设计的团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 270e03d58a89cf35132f254d2dd1af55d894e8d0
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2020
ms.locfileid: "48135993"
---
# <a name="use-teams-financial-templates-in-the-admin-console"></a><span data-ttu-id="3dc03-103">在管理控制台中使用团队财务模板</span><span class="sxs-lookup"><span data-stu-id="3dc03-103">Use Teams financial templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="3dc03-104">团队模板使你可以通过提供设置、频道和预安装应用的预定义模板来快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="3dc03-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="3dc03-105">团队模板具有围绕财务需求设计的团队结构的预建定义。</span><span class="sxs-lookup"><span data-stu-id="3dc03-105">Teams templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="3dc03-106">您还可以扩展团队模板以创建根据您的特定组织需求量身定制的团队。</span><span class="sxs-lookup"><span data-stu-id="3dc03-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="3dc03-107">在本文中，我们将介绍每个团队模板以及我们建议如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="3dc03-107">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="3dc03-108">本文适用于你负责在整个财务组织中规划、部署和管理多个团队的情况。</span><span class="sxs-lookup"><span data-stu-id="3dc03-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="3dc03-109">我们假定你的组织中已部署团队服务。</span><span class="sxs-lookup"><span data-stu-id="3dc03-109">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="3dc03-110">如果尚未推出团队，请先阅读 [如何展示 Microsoft 团队](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="3dc03-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="3dc03-111">若要深入了解有关团队模板的详细信息，请参阅 [团队模板入门](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="3dc03-111">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="3dc03-112">全球危机或活动</span><span class="sxs-lookup"><span data-stu-id="3dc03-112">Global crisis or event</span></span>

<span data-ttu-id="3dc03-113">跨业务单元对危机团队协作，并帮助创建业务连续性计划、共享远程工作提示、跟踪客户通信，以及使用公告和新闻让每个人都保持联系。</span><span class="sxs-lookup"><span data-stu-id="3dc03-113">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="3dc03-114">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="3dc03-114">Base template type</span></span>|<span data-ttu-id="3dc03-115">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3dc03-115">baseTemplateId</span></span> | <span data-ttu-id="3dc03-116">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="3dc03-116">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="3dc03-117">协作处理全球危机或活动</span><span class="sxs-lookup"><span data-stu-id="3dc03-117">Collaborate on global crisis or event</span></span>|`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="3dc03-118">信道</span><span class="sxs-lookup"><span data-stu-id="3dc03-118">Channels:</span></span> <ul><li><span data-ttu-id="3dc03-119">常规</span><span class="sxs-lookup"><span data-stu-id="3dc03-119">General</span></span><li><span data-ttu-id="3dc03-120">宣告</span><span class="sxs-lookup"><span data-stu-id="3dc03-120">Announcements</span></span></li><li><span data-ttu-id="3dc03-121">世界新闻</span><span class="sxs-lookup"><span data-stu-id="3dc03-121">World news</span></span></li><li><span data-ttu-id="3dc03-122">业务连续性</span><span class="sxs-lookup"><span data-stu-id="3dc03-122">Business continuity</span></span></li><li><span data-ttu-id="3dc03-123">远程工作</span><span class="sxs-lookup"><span data-stu-id="3dc03-123">Remote working</span></span></li><li><span data-ttu-id="3dc03-124">内部 comms</span><span class="sxs-lookup"><span data-stu-id="3dc03-124">Internal comms</span></span></li><li><span data-ttu-id="3dc03-125">外部 comms</span><span class="sxs-lookup"><span data-stu-id="3dc03-125">External comms</span></span></li><li><span data-ttu-id="3dc03-126">客户投诉</span><span class="sxs-lookup"><span data-stu-id="3dc03-126">Customer complaints</span></span></li><li><span data-ttu-id="3dc03-127">Kudos</span><span class="sxs-lookup"><span data-stu-id="3dc03-127">Kudos</span></span></li><li><span data-ttu-id="3dc03-128">执行更新</span><span class="sxs-lookup"><span data-stu-id="3dc03-128">Executive update</span></span></li></ul><span data-ttu-id="3dc03-129">识别</span><span class="sxs-lookup"><span data-stu-id="3dc03-129">Apps:</span></span> <ul><li><span data-ttu-id="3dc03-130">表扬</span><span class="sxs-lookup"><span data-stu-id="3dc03-130">Praise</span></span></li><li><span data-ttu-id="3dc03-131">源自</span><span class="sxs-lookup"><span data-stu-id="3dc03-131">Wiki</span></span></li><li><span data-ttu-id="3dc03-132">网站</span><span class="sxs-lookup"><span data-stu-id="3dc03-132">Website</span></span></li></ul>|
||||

## <a name="collaborate-within-a-bank-branch"></a><span data-ttu-id="3dc03-133">在银行分支内进行协作</span><span class="sxs-lookup"><span data-stu-id="3dc03-133">Collaborate within a bank branch</span></span>

<span data-ttu-id="3dc03-134">在 Huddles、客户会议、业务流程（如抵押贷款协作）中为您的银行分支员工集中协作，并通过公告和 Kudos 让每个人都参与循环。</span><span class="sxs-lookup"><span data-stu-id="3dc03-134">Centralize collaboration for your bank branch employees across Huddles, Customer Meetings, Business Processes such as Mortgage Collaboration, and keep everyone in the loop with Announcements and Kudos.</span></span>

| <span data-ttu-id="3dc03-135">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="3dc03-135">Base template type</span></span> |<span data-ttu-id="3dc03-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3dc03-136">baseTemplateId</span></span>| <span data-ttu-id="3dc03-137">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="3dc03-137">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
|<span data-ttu-id="3dc03-138">在银行分支内进行协作</span><span class="sxs-lookup"><span data-stu-id="3dc03-138">Collaborate within a bank branch</span></span>|`com.microsoft.teams.template.CollaborateWithinABankBranch` |<span data-ttu-id="3dc03-139">信道</span><span class="sxs-lookup"><span data-stu-id="3dc03-139">Channels:</span></span> <ul><li><span data-ttu-id="3dc03-140">常规</span><span class="sxs-lookup"><span data-stu-id="3dc03-140">General</span></span><li><span data-ttu-id="3dc03-141">宣告</span><span class="sxs-lookup"><span data-stu-id="3dc03-141">Announcements</span></span></li><li><span data-ttu-id="3dc03-142">Huddles</span><span class="sxs-lookup"><span data-stu-id="3dc03-142">Huddles</span></span></li><li><span data-ttu-id="3dc03-143">客户会议</span><span class="sxs-lookup"><span data-stu-id="3dc03-143">Customer meetings</span></span></li><li><span data-ttu-id="3dc03-144">训练</span><span class="sxs-lookup"><span data-stu-id="3dc03-144">Coaching</span></span></li><li><span data-ttu-id="3dc03-145">技能发展</span><span class="sxs-lookup"><span data-stu-id="3dc03-145">Skills development</span></span></li><li><span data-ttu-id="3dc03-146">借贷处理</span><span class="sxs-lookup"><span data-stu-id="3dc03-146">Loan processing</span></span></li><li><span data-ttu-id="3dc03-147">客户投诉</span><span class="sxs-lookup"><span data-stu-id="3dc03-147">Customer complaints</span></span></li><li><span data-ttu-id="3dc03-148">Kudos</span><span class="sxs-lookup"><span data-stu-id="3dc03-148">Kudos</span></span></li><li><span data-ttu-id="3dc03-149">有趣的资料</span><span class="sxs-lookup"><span data-stu-id="3dc03-149">Fun stuff</span></span></li><li><span data-ttu-id="3dc03-150">合规性</span><span class="sxs-lookup"><span data-stu-id="3dc03-150">Compliance</span></span></li></ul>|
||||

