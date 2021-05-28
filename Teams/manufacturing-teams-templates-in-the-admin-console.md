---
title: 管理中心中的制造团队模板入门
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
description: 了解如何通过使用管理中心提供预定义的设置、频道和预安装的应用，使用团队模板创建专为制造需求设计的团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ec27cba4336d86f51a32582440d5d7902ffca2b9
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684479"
---
# <a name="use-manufacturing-team-templates-in-the-admin-center"></a><span data-ttu-id="6efec-103">在管理中心使用制造团队模板</span><span class="sxs-lookup"><span data-stu-id="6efec-103">Use manufacturing team templates in the admin center</span></span>

<span data-ttu-id="6efec-104">使用团队模板，你可以通过提供设置、频道和预安装应用的预定义模板快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="6efec-104">Team templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="6efec-105">团队模板具有围绕制造需求设计的团队结构的预生成定义。</span><span class="sxs-lookup"><span data-stu-id="6efec-105">Team templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="6efec-106">还可以扩展团队模板，创建根据特定组织需求定制的团队。</span><span class="sxs-lookup"><span data-stu-id="6efec-106">You can also extend the team templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="6efec-107">本文介绍每个团队模板，并推荐其使用方法。</span><span class="sxs-lookup"><span data-stu-id="6efec-107">In this article, we introduce each of the team templates and recommend how to use them.</span></span>

<span data-ttu-id="6efec-108">如果你负责规划、部署和管理整个制造组织的多个团队，则本文适合你。</span><span class="sxs-lookup"><span data-stu-id="6efec-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="6efec-109">你已在贵组织内部署 Teams 服务。</span><span class="sxs-lookup"><span data-stu-id="6efec-109">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="6efec-110">如果尚未部署 Teams，首先请阅读[如何部署 Microsoft Teams](./deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="6efec-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="6efec-111">若要了解有关团队模板的一般信息，请参阅 [团队模板入门](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="6efec-111">To learn more about team templates in general, refer to [Get started with team templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="6efec-112">质量和安全</span><span class="sxs-lookup"><span data-stu-id="6efec-112">Quality and safety</span></span>

<span data-ttu-id="6efec-113">与制造工厂团队集中通信、访问资源和工厂运营。</span><span class="sxs-lookup"><span data-stu-id="6efec-113">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="6efec-114">包括策略和过程文档、培训视频、安全通知、轮班转移流程。</span><span class="sxs-lookup"><span data-stu-id="6efec-114">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="6efec-115">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="6efec-115">Base template type</span></span>|<span data-ttu-id="6efec-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="6efec-116">baseTemplateId</span></span>| <span data-ttu-id="6efec-117">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="6efec-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="6efec-118">质量和安全</span><span class="sxs-lookup"><span data-stu-id="6efec-118">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="6efec-119">频道：</span><span class="sxs-lookup"><span data-stu-id="6efec-119">Channels:</span></span> <ul><li><span data-ttu-id="6efec-120">常规</span><span class="sxs-lookup"><span data-stu-id="6efec-120">General</span></span><li><span data-ttu-id="6efec-121">公告</span><span class="sxs-lookup"><span data-stu-id="6efec-121">Announcements</span></span></li><li><span data-ttu-id="6efec-122">第 1 行</span><span class="sxs-lookup"><span data-stu-id="6efec-122">Line 1</span></span></li><li><span data-ttu-id="6efec-123">第 2 行</span><span class="sxs-lookup"><span data-stu-id="6efec-123">Line 2</span></span></li><li><span data-ttu-id="6efec-124">第 3 行</span><span class="sxs-lookup"><span data-stu-id="6efec-124">Line 3</span></span></li><li><span data-ttu-id="6efec-125">安全</span><span class="sxs-lookup"><span data-stu-id="6efec-125">Safety</span></span></li><li><span data-ttu-id="6efec-126">培训</span><span class="sxs-lookup"><span data-stu-id="6efec-126">Training</span></span></li><li><span data-ttu-id="6efec-127">维护</span><span class="sxs-lookup"><span data-stu-id="6efec-127">Maintenance</span></span></li><li><span data-ttu-id="6efec-128">有趣的内容</span><span class="sxs-lookup"><span data-stu-id="6efec-128">Fun stuff</span></span></li></ul> <span data-ttu-id="6efec-129">应用：</span><span class="sxs-lookup"><span data-stu-id="6efec-129">Apps:</span></span> <ul><li><span data-ttu-id="6efec-130">Wiki</span><span class="sxs-lookup"><span data-stu-id="6efec-130">Wiki</span></span></li><li><span data-ttu-id="6efec-131">Planner</span><span class="sxs-lookup"><span data-stu-id="6efec-131">Planner</span></span></li></ul>|
||||