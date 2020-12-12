---
title: 管理中心中的 Teams 制造模板入门
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
description: 了解如何使用。 使用管理中心提供预定义的设置、频道和预安装的应用，创建专为制造需求设计的团队结构的团队模板。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 51a28e997e5c7c0b36fb49cd0bb46768b7808a29
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662217"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-center"></a><span data-ttu-id="45848-104">在管理中心使用 Teams 制造模板</span><span class="sxs-lookup"><span data-stu-id="45848-104">Use Teams manufacturing templates in the admin center</span></span>

<span data-ttu-id="45848-105">Teams 模板提供预定义的设置、频道和预安装应用模板，让你可以快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="45848-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="45848-106">Teams 模板具有围绕制造需求设计的团队结构的预构建定义。</span><span class="sxs-lookup"><span data-stu-id="45848-106">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="45848-107">还可以扩展 Teams 模板，创建根据特定组织需求定制的团队。</span><span class="sxs-lookup"><span data-stu-id="45848-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="45848-108">本文介绍每个 Teams 模板，并推荐其使用方法。</span><span class="sxs-lookup"><span data-stu-id="45848-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="45848-109">本文适用于负责规划、部署和管理整个制造组织的多个团队。</span><span class="sxs-lookup"><span data-stu-id="45848-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="45848-110">你已在组织中部署了 Teams 服务。</span><span class="sxs-lookup"><span data-stu-id="45848-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="45848-111">如果尚未推出 Teams，请首先阅读"如何推出[Microsoft Teams"。](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="45848-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="45848-112">若要了解有关团队模板的一般信息，请参阅 [Teams 模板入门](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="45848-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="45848-113">质量和安全</span><span class="sxs-lookup"><span data-stu-id="45848-113">Quality and safety</span></span>

<span data-ttu-id="45848-114">与制造工厂团队集中通信、访问资源和工厂运营。</span><span class="sxs-lookup"><span data-stu-id="45848-114">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="45848-115">包括策略和过程文档、培训视频、安全通知、轮班流程。</span><span class="sxs-lookup"><span data-stu-id="45848-115">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="45848-116">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="45848-116">Base template type</span></span>|<span data-ttu-id="45848-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="45848-117">baseTemplateId</span></span>| <span data-ttu-id="45848-118">此基本模板提供的属性</span><span class="sxs-lookup"><span data-stu-id="45848-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="45848-119">质量和安全</span><span class="sxs-lookup"><span data-stu-id="45848-119">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="45848-120">频道：</span><span class="sxs-lookup"><span data-stu-id="45848-120">Channels:</span></span> <ul><li><span data-ttu-id="45848-121">常规</span><span class="sxs-lookup"><span data-stu-id="45848-121">General</span></span><li><span data-ttu-id="45848-122">公告</span><span class="sxs-lookup"><span data-stu-id="45848-122">Announcements</span></span></li><li><span data-ttu-id="45848-123">第 1 行</span><span class="sxs-lookup"><span data-stu-id="45848-123">Line 1</span></span></li><li><span data-ttu-id="45848-124">第 2 行</span><span class="sxs-lookup"><span data-stu-id="45848-124">Line 2</span></span></li><li><span data-ttu-id="45848-125">第 3 行</span><span class="sxs-lookup"><span data-stu-id="45848-125">Line 3</span></span></li><li><span data-ttu-id="45848-126">安全</span><span class="sxs-lookup"><span data-stu-id="45848-126">Safety</span></span></li><li><span data-ttu-id="45848-127">培训</span><span class="sxs-lookup"><span data-stu-id="45848-127">Training</span></span></li><li><span data-ttu-id="45848-128">维护</span><span class="sxs-lookup"><span data-stu-id="45848-128">Maintenance</span></span></li><li><span data-ttu-id="45848-129">有趣的内容</span><span class="sxs-lookup"><span data-stu-id="45848-129">Fun stuff</span></span></li></ul> <span data-ttu-id="45848-130">应用：</span><span class="sxs-lookup"><span data-stu-id="45848-130">Apps:</span></span> <ul><li><span data-ttu-id="45848-131">Wiki</span><span class="sxs-lookup"><span data-stu-id="45848-131">Wiki</span></span></li><li><span data-ttu-id="45848-132">Planner</span><span class="sxs-lookup"><span data-stu-id="45848-132">Planner</span></span></li></ul>|
||||
