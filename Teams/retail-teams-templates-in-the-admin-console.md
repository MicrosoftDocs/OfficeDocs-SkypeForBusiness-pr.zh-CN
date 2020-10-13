---
title: 在管理中心中使用团队零售模板
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
description: 了解如何使用团队模板，通过使用管理中心提供预定义的设置、信道和预安装应用来创建专为零售需求设计的团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 40e21687aa3d14b0cb9d51d4ba5f856eada3c538
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424562"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a><span data-ttu-id="62acf-103">在管理中心中使用团队零售模板</span><span class="sxs-lookup"><span data-stu-id="62acf-103">Use Teams retail templates in the admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="62acf-104">团队模板使你可以通过提供设置、频道和预安装应用的预定义模板来快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="62acf-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="62acf-105">团队模板具有围绕零售商需求设计的团队结构的预建定义。</span><span class="sxs-lookup"><span data-stu-id="62acf-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="62acf-106">你可以使用团队模板快速创建适用于零售商的团队类型，并在组织中部署这些团队。</span><span class="sxs-lookup"><span data-stu-id="62acf-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="62acf-107">您还可以扩展团队模板以创建根据您的特定组织需求量身定制的团队。</span><span class="sxs-lookup"><span data-stu-id="62acf-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="62acf-108">在本文中，我们将介绍每个团队模板以及我们建议如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="62acf-108">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="62acf-109">本文适用于您负责在您的零售组织中规划、部署和管理多个团队的情况。</span><span class="sxs-lookup"><span data-stu-id="62acf-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="62acf-110">我们假定你的组织中已部署团队服务。</span><span class="sxs-lookup"><span data-stu-id="62acf-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="62acf-111">如果尚未推出团队，请先阅读 [如何展示 Microsoft 团队](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="62acf-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="62acf-112">若要深入了解有关团队模板的详细信息，请参阅 [团队模板入门](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="62acf-112">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="62acf-113">组织商店</span><span class="sxs-lookup"><span data-stu-id="62acf-113">Organize a store</span></span>

<span data-ttu-id="62acf-114">将零售员工集中在一个中心体验中，以管理任务、共享文档和解决客户问题。</span><span class="sxs-lookup"><span data-stu-id="62acf-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="62acf-115">集成其他应用程序以简化班次开始 & 结束过程。</span><span class="sxs-lookup"><span data-stu-id="62acf-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="62acf-116">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="62acf-116">Base template type</span></span> |<span data-ttu-id="62acf-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="62acf-117">baseTemplateId</span></span> | <span data-ttu-id="62acf-118">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="62acf-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="62acf-119">组织商店</span><span class="sxs-lookup"><span data-stu-id="62acf-119">Organize a store</span></span>| `retailStore`|<span data-ttu-id="62acf-120">信道</span><span class="sxs-lookup"><span data-stu-id="62acf-120">Channels:</span></span> <ul><li><span data-ttu-id="62acf-121">常规</span><span class="sxs-lookup"><span data-stu-id="62acf-121">General</span></span><li><span data-ttu-id="62acf-122">切换切换</span><span class="sxs-lookup"><span data-stu-id="62acf-122">Shift handoff</span></span></li><li><span data-ttu-id="62acf-123">培训</span><span class="sxs-lookup"><span data-stu-id="62acf-123">Learning</span></span></li></ul> <span data-ttu-id="62acf-124">识别</span><span class="sxs-lookup"><span data-stu-id="62acf-124">Apps:</span></span> <ul><li><span data-ttu-id="62acf-125">源自</span><span class="sxs-lookup"><span data-stu-id="62acf-125">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="62acf-126">经理协作</span><span class="sxs-lookup"><span data-stu-id="62acf-126">Manager Collaboration</span></span>

<span data-ttu-id="62acf-127">经理协作模板非常适合为一组经理创建团队，以便在商店/地区等协作。例如，如果您的组织拥有区域，则可以为加利福尼亚地区创建经理协作团队，并包括该地区的所有商店经理以及该地区的地区经理。</span><span class="sxs-lookup"><span data-stu-id="62acf-127">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="62acf-128">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="62acf-128">Base template type</span></span>| <span data-ttu-id="62acf-129">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="62acf-129">baseTemplateId</span></span> | <span data-ttu-id="62acf-130">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="62acf-130">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="62acf-131">零售经理协作</span><span class="sxs-lookup"><span data-stu-id="62acf-131">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="62acf-132">信道</span><span class="sxs-lookup"><span data-stu-id="62acf-132">Channels:</span></span> <ul><li><span data-ttu-id="62acf-133">常规</span><span class="sxs-lookup"><span data-stu-id="62acf-133">General</span></span><li><span data-ttu-id="62acf-134">运营</span><span class="sxs-lookup"><span data-stu-id="62acf-134">Operations</span></span></li><li><span data-ttu-id="62acf-135">培训</span><span class="sxs-lookup"><span data-stu-id="62acf-135">Learning</span></span></li></ul> <span data-ttu-id="62acf-136">识别</span><span class="sxs-lookup"><span data-stu-id="62acf-136">Apps:</span></span> <ul><li><span data-ttu-id="62acf-137">源自</span><span class="sxs-lookup"><span data-stu-id="62acf-137">Wiki</span></span></li></ul>|
||||
