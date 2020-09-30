---
title: 管理控制台中的团队制造模板入门
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
description: 了解如何使用。 团队模板，可通过使用管理员控制台提供预定义的设置、信道和预安装应用来创建为制造需求设计的团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb7769a193e95f31db8ffb02b6120babfa05c661
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308395"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-console"></a><span data-ttu-id="dd5ec-104">在管理控制台中使用团队制造模板</span><span class="sxs-lookup"><span data-stu-id="dd5ec-104">Use Teams manufacturing templates in the admin console</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="dd5ec-105">团队模板使你可以通过提供设置、频道和预安装应用的预定义模板来快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="dd5ec-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="dd5ec-106">团队模板具有围绕制造需求设计的团队结构的预建定义。</span><span class="sxs-lookup"><span data-stu-id="dd5ec-106">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="dd5ec-107">您还可以扩展团队模板以创建根据您的特定组织需求量身定制的团队。</span><span class="sxs-lookup"><span data-stu-id="dd5ec-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="dd5ec-108">在本文中，我们将介绍每个团队模板并建议如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="dd5ec-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="dd5ec-109">本文适用于你负责在你的制造组织中规划、部署和管理多个团队的情况。</span><span class="sxs-lookup"><span data-stu-id="dd5ec-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="dd5ec-110">你已在你的组织中部署团队服务。</span><span class="sxs-lookup"><span data-stu-id="dd5ec-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="dd5ec-111">如果尚未推出团队，请先阅读 [如何展示 Microsoft 团队](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="dd5ec-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="dd5ec-112">若要深入了解有关团队模板的详细信息，请参阅 [团队模板入门](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="dd5ec-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="dd5ec-113">质量和安全性</span><span class="sxs-lookup"><span data-stu-id="dd5ec-113">Quality and safety</span></span>

<span data-ttu-id="dd5ec-114">使用制造工厂团队集中沟通、访问资源和车间运营。</span><span class="sxs-lookup"><span data-stu-id="dd5ec-114">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="dd5ec-115">包括政策和流程文档、培训视频、安全通知、倒班移交流程。</span><span class="sxs-lookup"><span data-stu-id="dd5ec-115">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="dd5ec-116">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="dd5ec-116">Base template type</span></span>|<span data-ttu-id="dd5ec-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="dd5ec-117">baseTemplateId</span></span> | <span data-ttu-id="dd5ec-118">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="dd5ec-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="dd5ec-119">质量和安全性</span><span class="sxs-lookup"><span data-stu-id="dd5ec-119">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="dd5ec-120">信道</span><span class="sxs-lookup"><span data-stu-id="dd5ec-120">Channels:</span></span> <ul><li><span data-ttu-id="dd5ec-121">常规</span><span class="sxs-lookup"><span data-stu-id="dd5ec-121">General</span></span><li><span data-ttu-id="dd5ec-122">宣告</span><span class="sxs-lookup"><span data-stu-id="dd5ec-122">Announcements</span></span></li><li><span data-ttu-id="dd5ec-123">第1行</span><span class="sxs-lookup"><span data-stu-id="dd5ec-123">Line 1</span></span></li><li><span data-ttu-id="dd5ec-124">第2行</span><span class="sxs-lookup"><span data-stu-id="dd5ec-124">Line 2</span></span></li><li><span data-ttu-id="dd5ec-125">第3行</span><span class="sxs-lookup"><span data-stu-id="dd5ec-125">Line 3</span></span></li><li><span data-ttu-id="dd5ec-126">引起</span><span class="sxs-lookup"><span data-stu-id="dd5ec-126">Safety</span></span></li><li><span data-ttu-id="dd5ec-127">培训</span><span class="sxs-lookup"><span data-stu-id="dd5ec-127">Training</span></span></li><li><span data-ttu-id="dd5ec-128">维护</span><span class="sxs-lookup"><span data-stu-id="dd5ec-128">Maintenance</span></span></li><li><span data-ttu-id="dd5ec-129">有趣的资料</span><span class="sxs-lookup"><span data-stu-id="dd5ec-129">Fun stuff</span></span></li></ul> <span data-ttu-id="dd5ec-130">识别</span><span class="sxs-lookup"><span data-stu-id="dd5ec-130">Apps:</span></span> <ul><li><span data-ttu-id="dd5ec-131">源自</span><span class="sxs-lookup"><span data-stu-id="dd5ec-131">Wiki</span></span></li></ul>|
||||
