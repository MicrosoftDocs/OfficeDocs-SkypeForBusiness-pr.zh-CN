---
title: 在管理中心Teams制造模板入门
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
description: 了解如何使用。 Teams模板，通过使用管理中心提供预定义的设置、通道和预安装的应用，创建专为制造需求设计的团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f5439cd8fdd053ab8444a1016eac94064638605
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120553"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-center"></a><span data-ttu-id="7262b-104">在Teams中心使用生产模板</span><span class="sxs-lookup"><span data-stu-id="7262b-104">Use Teams manufacturing templates in the admin center</span></span>

<span data-ttu-id="7262b-105">Teams 模板提供预定义的设置、频道和预安装的应用模板，让你能够快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="7262b-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="7262b-106">Teams模板具有围绕制造需求设计的团队结构的预生成定义。</span><span class="sxs-lookup"><span data-stu-id="7262b-106">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="7262b-107">你还可以扩展 Teams 模板，以创建根据特定组织需求量身定制的团队。</span><span class="sxs-lookup"><span data-stu-id="7262b-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="7262b-108">本文介绍每个Teams模板，并推荐其使用方法。</span><span class="sxs-lookup"><span data-stu-id="7262b-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="7262b-109">如果你负责规划、部署和管理整个制造组织的多个团队，则本文适合你。</span><span class="sxs-lookup"><span data-stu-id="7262b-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="7262b-110">你已在贵组织内部署 Teams 服务。</span><span class="sxs-lookup"><span data-stu-id="7262b-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="7262b-111">如果尚未部署 Teams，首先请阅读[如何部署 Microsoft Teams](./deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="7262b-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="7262b-112">若要了解有关常规团队模板的详细信息，请参阅[开始使用 Teams 模板](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="7262b-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="7262b-113">质量和安全</span><span class="sxs-lookup"><span data-stu-id="7262b-113">Quality and safety</span></span>

<span data-ttu-id="7262b-114">与制造工厂团队集中通信、访问资源和工厂运营。</span><span class="sxs-lookup"><span data-stu-id="7262b-114">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="7262b-115">包括策略和过程文档、培训视频、安全通知、轮班转移流程。</span><span class="sxs-lookup"><span data-stu-id="7262b-115">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="7262b-116">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="7262b-116">Base template type</span></span>|<span data-ttu-id="7262b-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="7262b-117">baseTemplateId</span></span>| <span data-ttu-id="7262b-118">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="7262b-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="7262b-119">质量和安全</span><span class="sxs-lookup"><span data-stu-id="7262b-119">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="7262b-120">频道：</span><span class="sxs-lookup"><span data-stu-id="7262b-120">Channels:</span></span> <ul><li><span data-ttu-id="7262b-121">常规</span><span class="sxs-lookup"><span data-stu-id="7262b-121">General</span></span><li><span data-ttu-id="7262b-122">公告</span><span class="sxs-lookup"><span data-stu-id="7262b-122">Announcements</span></span></li><li><span data-ttu-id="7262b-123">第 1 行</span><span class="sxs-lookup"><span data-stu-id="7262b-123">Line 1</span></span></li><li><span data-ttu-id="7262b-124">第 2 行</span><span class="sxs-lookup"><span data-stu-id="7262b-124">Line 2</span></span></li><li><span data-ttu-id="7262b-125">第 3 行</span><span class="sxs-lookup"><span data-stu-id="7262b-125">Line 3</span></span></li><li><span data-ttu-id="7262b-126">安全</span><span class="sxs-lookup"><span data-stu-id="7262b-126">Safety</span></span></li><li><span data-ttu-id="7262b-127">培训</span><span class="sxs-lookup"><span data-stu-id="7262b-127">Training</span></span></li><li><span data-ttu-id="7262b-128">维护</span><span class="sxs-lookup"><span data-stu-id="7262b-128">Maintenance</span></span></li><li><span data-ttu-id="7262b-129">有趣的内容</span><span class="sxs-lookup"><span data-stu-id="7262b-129">Fun stuff</span></span></li></ul> <span data-ttu-id="7262b-130">应用：</span><span class="sxs-lookup"><span data-stu-id="7262b-130">Apps:</span></span> <ul><li><span data-ttu-id="7262b-131">Wiki</span><span class="sxs-lookup"><span data-stu-id="7262b-131">Wiki</span></span></li><li><span data-ttu-id="7262b-132">Planner</span><span class="sxs-lookup"><span data-stu-id="7262b-132">Planner</span></span></li></ul>|
||||