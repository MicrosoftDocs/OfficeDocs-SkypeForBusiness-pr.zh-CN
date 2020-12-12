---
title: 在管理中心使用 Teams 零售模板
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
description: 了解如何通过使用管理中心提供预定义的设置、频道和预安装的应用，使用 Teams 模板创建专为零售商需求设计的团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b40da8fd1cc8182d0e5ad80c30f5a459f17d26f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662637"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a><span data-ttu-id="668e8-103">在管理中心使用 Teams 零售模板</span><span class="sxs-lookup"><span data-stu-id="668e8-103">Use Teams retail templates in the admin center</span></span>

<span data-ttu-id="668e8-104">Teams 模板提供预定义的设置、频道和预安装应用模板，让你快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="668e8-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="668e8-105">Teams 模板具有围绕零售商需求设计的团队结构的预构建定义。</span><span class="sxs-lookup"><span data-stu-id="668e8-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="668e8-106">可以使用 Teams 模板快速创建适用于零售商的团队类型，并在整个组织中部署它们。</span><span class="sxs-lookup"><span data-stu-id="668e8-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="668e8-107">还可以扩展 Teams 模板，创建根据特定组织需求定制的团队。</span><span class="sxs-lookup"><span data-stu-id="668e8-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="668e8-108">本文将介绍每个 Teams 模板，以及我们建议如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="668e8-108">In this article, we'll introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="668e8-109">如果你负责规划、部署和管理整个零售组织的多个团队，本文适合你。</span><span class="sxs-lookup"><span data-stu-id="668e8-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="668e8-110">我们假设你已在组织中部署了 Teams 服务。</span><span class="sxs-lookup"><span data-stu-id="668e8-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="668e8-111">如果尚未推出 Teams，请首先阅读"如何推出[Microsoft Teams"。](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="668e8-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="668e8-112">若要了解有关团队模板的一般信息，请参阅 [Teams 模板入门](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="668e8-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="668e8-113">组织商店</span><span class="sxs-lookup"><span data-stu-id="668e8-113">Organize a store</span></span>

<span data-ttu-id="668e8-114">将零售员工汇集在一个中心体验中，以管理任务、共享文档和解决客户问题。</span><span class="sxs-lookup"><span data-stu-id="668e8-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="668e8-115">集成其他应用程序，以简化&流程。</span><span class="sxs-lookup"><span data-stu-id="668e8-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="668e8-116">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="668e8-116">Base template type</span></span> |<span data-ttu-id="668e8-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="668e8-117">baseTemplateId</span></span> | <span data-ttu-id="668e8-118">此基本模板提供的属性</span><span class="sxs-lookup"><span data-stu-id="668e8-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="668e8-119">组织商店</span><span class="sxs-lookup"><span data-stu-id="668e8-119">Organize a store</span></span>|`retailStore`|<span data-ttu-id="668e8-120">频道：</span><span class="sxs-lookup"><span data-stu-id="668e8-120">Channels:</span></span> <ul><li><span data-ttu-id="668e8-121">常规</span><span class="sxs-lookup"><span data-stu-id="668e8-121">General</span></span><li><span data-ttu-id="668e8-122">Shift 切换</span><span class="sxs-lookup"><span data-stu-id="668e8-122">Shift handoff</span></span></li><li><span data-ttu-id="668e8-123">学习</span><span class="sxs-lookup"><span data-stu-id="668e8-123">Learning</span></span></li></ul> <span data-ttu-id="668e8-124">应用：</span><span class="sxs-lookup"><span data-stu-id="668e8-124">Apps:</span></span> <ul><li><span data-ttu-id="668e8-125">Wiki</span><span class="sxs-lookup"><span data-stu-id="668e8-125">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="668e8-126">管理器协作</span><span class="sxs-lookup"><span data-stu-id="668e8-126">Manager Collaboration</span></span>

<span data-ttu-id="668e8-127">管理器协作模板非常适合为一组经理创建团队，以跨商店/区域等进行协作。例如，如果您的组织有区域，您可以为加利福尼亚州创建经理协作团队，并包括该区域的所有商店经理，以及该区域的区域经理。</span><span class="sxs-lookup"><span data-stu-id="668e8-127">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="668e8-128">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="668e8-128">Base template type</span></span>| <span data-ttu-id="668e8-129">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="668e8-129">baseTemplateId</span></span> | <span data-ttu-id="668e8-130">此基本模板提供的属性</span><span class="sxs-lookup"><span data-stu-id="668e8-130">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="668e8-131">零售 - 管理器协作</span><span class="sxs-lookup"><span data-stu-id="668e8-131">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="668e8-132">频道：</span><span class="sxs-lookup"><span data-stu-id="668e8-132">Channels:</span></span> <ul><li><span data-ttu-id="668e8-133">常规</span><span class="sxs-lookup"><span data-stu-id="668e8-133">General</span></span><li><span data-ttu-id="668e8-134">运营</span><span class="sxs-lookup"><span data-stu-id="668e8-134">Operations</span></span></li><li><span data-ttu-id="668e8-135">学习</span><span class="sxs-lookup"><span data-stu-id="668e8-135">Learning</span></span></li></ul> <span data-ttu-id="668e8-136">应用：</span><span class="sxs-lookup"><span data-stu-id="668e8-136">Apps:</span></span> <ul><li><span data-ttu-id="668e8-137">Wiki</span><span class="sxs-lookup"><span data-stu-id="668e8-137">Wiki</span></span></li></ul>|
||||
