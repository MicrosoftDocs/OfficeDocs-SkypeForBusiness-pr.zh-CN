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
description: 了解如何使用 Teams 模板通过管理中心提供预定义的设置、频道和预安装的应用，从而创建针对零售商需求设计的团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b40da8fd1cc8182d0e5ad80c30f5a459f17d26f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662637"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a><span data-ttu-id="8fe9a-103">在管理中心使用 Teams 零售模板</span><span class="sxs-lookup"><span data-stu-id="8fe9a-103">Use Teams retail templates in the admin center</span></span>

<span data-ttu-id="8fe9a-104">Teams 模板提供预定义的设置、频道和预安装的应用模板，让你能够快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="8fe9a-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="8fe9a-105">Teams 模板具有预先构建的围绕零售商需求设计的团队结构定义。</span><span class="sxs-lookup"><span data-stu-id="8fe9a-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="8fe9a-106">可使用 Teams 模板快速创建适用于零售商的团队类型，并在整个组织中部署它们。</span><span class="sxs-lookup"><span data-stu-id="8fe9a-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="8fe9a-107">你还可以扩展 Teams 模板，以创建根据特定组织需求量身定制的团队。</span><span class="sxs-lookup"><span data-stu-id="8fe9a-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="8fe9a-108">在本文中，我们将介绍各个 Teams 模板并建议如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="8fe9a-108">In this article, we'll introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="8fe9a-109">如果你负责在整个零售组织中规划、部署和管理多个团队，则本文非常适合你。</span><span class="sxs-lookup"><span data-stu-id="8fe9a-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="8fe9a-110">假设你已在贵组织内部署 Teams 服务。</span><span class="sxs-lookup"><span data-stu-id="8fe9a-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="8fe9a-111">如果尚未部署 Teams，首先请阅读[如何部署 Microsoft Teams](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="8fe9a-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="8fe9a-112">若要了解有关常规团队模板的详细信息，请参阅[开始使用 Teams 模板](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="8fe9a-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="8fe9a-113">组织商店</span><span class="sxs-lookup"><span data-stu-id="8fe9a-113">Organize a store</span></span>

<span data-ttu-id="8fe9a-114">将你的零售员工汇集到一个中心体验中，以管理任务、共享文档和解决客户问题。</span><span class="sxs-lookup"><span data-stu-id="8fe9a-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="8fe9a-115">整合其他应用程序，以简化轮班开始和结束流程。</span><span class="sxs-lookup"><span data-stu-id="8fe9a-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="8fe9a-116">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="8fe9a-116">Base template type</span></span> |<span data-ttu-id="8fe9a-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="8fe9a-117">baseTemplateId</span></span> | <span data-ttu-id="8fe9a-118">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="8fe9a-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="8fe9a-119">组织商店</span><span class="sxs-lookup"><span data-stu-id="8fe9a-119">Organize a store</span></span>|`retailStore`|<span data-ttu-id="8fe9a-120">频道：</span><span class="sxs-lookup"><span data-stu-id="8fe9a-120">Channels:</span></span> <ul><li><span data-ttu-id="8fe9a-121">常规</span><span class="sxs-lookup"><span data-stu-id="8fe9a-121">General</span></span><li><span data-ttu-id="8fe9a-122">换班</span><span class="sxs-lookup"><span data-stu-id="8fe9a-122">Shift handoff</span></span></li><li><span data-ttu-id="8fe9a-123">学习</span><span class="sxs-lookup"><span data-stu-id="8fe9a-123">Learning</span></span></li></ul> <span data-ttu-id="8fe9a-124">应用：</span><span class="sxs-lookup"><span data-stu-id="8fe9a-124">Apps:</span></span> <ul><li><span data-ttu-id="8fe9a-125">Wiki</span><span class="sxs-lookup"><span data-stu-id="8fe9a-125">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="8fe9a-126">经理协作</span><span class="sxs-lookup"><span data-stu-id="8fe9a-126">Manager Collaboration</span></span>

<span data-ttu-id="8fe9a-127">经理协作模板非常适合用于创建一个团队，供一组经理跨商店/地区进行协作等。例如，如果你的组织跨越多个地区，则可以为加利福尼亚地区创建一个经理协作团队，并包括该地区的所有商店经理以及该地区的区域经理。</span><span class="sxs-lookup"><span data-stu-id="8fe9a-127">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="8fe9a-128">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="8fe9a-128">Base template type</span></span>| <span data-ttu-id="8fe9a-129">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="8fe9a-129">baseTemplateId</span></span> | <span data-ttu-id="8fe9a-130">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="8fe9a-130">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="8fe9a-131">零售 - 经理协作</span><span class="sxs-lookup"><span data-stu-id="8fe9a-131">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="8fe9a-132">频道：</span><span class="sxs-lookup"><span data-stu-id="8fe9a-132">Channels:</span></span> <ul><li><span data-ttu-id="8fe9a-133">常规</span><span class="sxs-lookup"><span data-stu-id="8fe9a-133">General</span></span><li><span data-ttu-id="8fe9a-134">运营</span><span class="sxs-lookup"><span data-stu-id="8fe9a-134">Operations</span></span></li><li><span data-ttu-id="8fe9a-135">学习</span><span class="sxs-lookup"><span data-stu-id="8fe9a-135">Learning</span></span></li></ul> <span data-ttu-id="8fe9a-136">应用：</span><span class="sxs-lookup"><span data-stu-id="8fe9a-136">Apps:</span></span> <ul><li><span data-ttu-id="8fe9a-137">Wiki</span><span class="sxs-lookup"><span data-stu-id="8fe9a-137">Wiki</span></span></li></ul>|
||||
