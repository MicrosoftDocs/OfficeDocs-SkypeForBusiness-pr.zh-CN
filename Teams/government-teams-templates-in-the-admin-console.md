---
title: 在管理中心使用 Teams 政府版模板
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
description: 了解如何使用。 使用管理中心提供预定义的设置、频道和预安装的应用，创建旨在满足政府需求的团队结构的团队模板。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: db0d8fa4a2744f0f3c3591918230e3f569727ae7
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662197"
---
# <a name="use-teams-government-templates-in-the-admin-center"></a><span data-ttu-id="64039-104">在管理中心使用 Teams 政府版模板</span><span class="sxs-lookup"><span data-stu-id="64039-104">Use Teams government templates in the admin center</span></span>

<span data-ttu-id="64039-105">Teams 模板提供预定义的设置、频道和预安装应用模板，让你可以快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="64039-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="64039-106">Teams 模板具有围绕政府需求设计的团队结构的预构建定义。</span><span class="sxs-lookup"><span data-stu-id="64039-106">Teams templates have pre-built definitions of team structures designed around governmental needs.</span></span> <span data-ttu-id="64039-107">还可以扩展 Teams 模板，创建根据特定组织需求定制的团队。</span><span class="sxs-lookup"><span data-stu-id="64039-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="64039-108">本文介绍每个 Teams 模板，并推荐其使用方法。</span><span class="sxs-lookup"><span data-stu-id="64039-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="64039-109">如果你负责规划、部署和管理整个政府组织的多个团队，本文适合你。</span><span class="sxs-lookup"><span data-stu-id="64039-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your governmental organization.</span></span> <span data-ttu-id="64039-110">你已在组织中部署了 Teams 服务。</span><span class="sxs-lookup"><span data-stu-id="64039-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="64039-111">如果尚未推出 Teams，请首先阅读"如何推出[Microsoft Teams"。](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="64039-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="64039-112">若要了解有关团队模板的一般信息，请参阅 [Teams 模板入门](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="64039-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="coordinate-incident-response"></a><span data-ttu-id="64039-113">协调事件响应</span><span class="sxs-lookup"><span data-stu-id="64039-113">Coordinate incident response</span></span>

<span data-ttu-id="64039-114">集中应对管理或事件响应团队的通信和关键资源。</span><span class="sxs-lookup"><span data-stu-id="64039-114">Centralize communication and critical resources for your crisis management or incident response team.</span></span> <span data-ttu-id="64039-115">在此团队中，您可以包括许多不同类型的文件，以帮助创建所有文档的一个中央位置。</span><span class="sxs-lookup"><span data-stu-id="64039-115">Within this team, you can include many different types of files to help create a central place for all your documents.</span></span> <span data-ttu-id="64039-116">使用联机会议改进信息流和态势感知。</span><span class="sxs-lookup"><span data-stu-id="64039-116">Use online meetings to improve information flow and situational awareness.</span></span>

| <span data-ttu-id="64039-117">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="64039-117">Base template type</span></span> |<span data-ttu-id="64039-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="64039-118">baseTemplateId</span></span> | <span data-ttu-id="64039-119">此基本模板提供的属性</span><span class="sxs-lookup"><span data-stu-id="64039-119">Properties that come with this base template</span></span> |
|-------------------|-------|---------------------------------------------------------------------------|
|<span data-ttu-id="64039-120">协调事件响应</span><span class="sxs-lookup"><span data-stu-id="64039-120">Coordinate incident response</span></span>|`com.microsoft.teams.template.CoordinateIncidentResponse`|<span data-ttu-id="64039-121">频道：</span><span class="sxs-lookup"><span data-stu-id="64039-121">Channels:</span></span> <ul><li><span data-ttu-id="64039-122">常规</span><span class="sxs-lookup"><span data-stu-id="64039-122">General</span></span><li><span data-ttu-id="64039-123">公告</span><span class="sxs-lookup"><span data-stu-id="64039-123">Announcements</span></span></li><li><span data-ttu-id="64039-124">后勤工作</span><span class="sxs-lookup"><span data-stu-id="64039-124">Logistics</span></span></li><li><span data-ttu-id="64039-125">规划</span><span class="sxs-lookup"><span data-stu-id="64039-125">Planning</span></span></li><li><span data-ttu-id="64039-126">恢复</span><span class="sxs-lookup"><span data-stu-id="64039-126">Recovery</span></span></li><li><span data-ttu-id="64039-127">紧急</span><span class="sxs-lookup"><span data-stu-id="64039-127">Urgent</span></span></li></ul> <span data-ttu-id="64039-128">应用：</span><span class="sxs-lookup"><span data-stu-id="64039-128">Apps:</span></span> <ul><li><span data-ttu-id="64039-129">Wiki</span><span class="sxs-lookup"><span data-stu-id="64039-129">Wiki</span></span></li><li><span data-ttu-id="64039-130">Excel</span><span class="sxs-lookup"><span data-stu-id="64039-130">Excel</span></span></li><li><span data-ttu-id="64039-131">OneNote</span><span class="sxs-lookup"><span data-stu-id="64039-131">OneNote</span></span></li><li><span data-ttu-id="64039-132">SharePoint</span><span class="sxs-lookup"><span data-stu-id="64039-132">SharePoint</span></span></li><li><span data-ttu-id="64039-133">Planner</span><span class="sxs-lookup"><span data-stu-id="64039-133">Planner</span></span></li></ul>|
||||