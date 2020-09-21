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
description: 了解如何使用团队模板，通过使用管理控制台提供预定义的设置、信道和预安装应用来创建为制造需求设计的团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 896435daaf7b1036a54649e8670b0a19d88b2474
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2020
ms.locfileid: "48135997"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-console"></a><span data-ttu-id="9f083-103">在管理控制台中使用团队制造模板</span><span class="sxs-lookup"><span data-stu-id="9f083-103">Use Teams manufacturing templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="9f083-104">团队模板使你可以通过提供设置、频道和预安装应用的预定义模板来快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="9f083-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="9f083-105">团队模板具有围绕制造需求设计的团队结构的预建定义。</span><span class="sxs-lookup"><span data-stu-id="9f083-105">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="9f083-106">您还可以扩展团队模板以创建根据您的特定组织需求量身定制的团队。</span><span class="sxs-lookup"><span data-stu-id="9f083-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="9f083-107">在本文中，我们将介绍每个团队模板以及我们建议如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="9f083-107">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="9f083-108">本文适用于你负责在你的制造组织中规划、部署和管理多个团队的情况。</span><span class="sxs-lookup"><span data-stu-id="9f083-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="9f083-109">我们假定你的组织中已部署团队服务。</span><span class="sxs-lookup"><span data-stu-id="9f083-109">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="9f083-110">如果尚未推出团队，请先阅读 [如何展示 Microsoft 团队](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="9f083-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="9f083-111">若要深入了解有关团队模板的详细信息，请参阅 [团队模板入门](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="9f083-111">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="9f083-112">质量和安全性</span><span class="sxs-lookup"><span data-stu-id="9f083-112">Quality and safety</span></span>

<span data-ttu-id="9f083-113">使用制造工厂团队集中沟通、访问资源和车间运营。</span><span class="sxs-lookup"><span data-stu-id="9f083-113">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="9f083-114">包括政策和流程文档、培训视频、安全通知、倒班移交流程。</span><span class="sxs-lookup"><span data-stu-id="9f083-114">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="9f083-115">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="9f083-115">Base template type</span></span>|<span data-ttu-id="9f083-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="9f083-116">baseTemplateId</span></span> | <span data-ttu-id="9f083-117">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="9f083-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="9f083-118">质量和安全性</span><span class="sxs-lookup"><span data-stu-id="9f083-118">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="9f083-119">信道</span><span class="sxs-lookup"><span data-stu-id="9f083-119">Channels:</span></span> <ul><li><span data-ttu-id="9f083-120">常规</span><span class="sxs-lookup"><span data-stu-id="9f083-120">General</span></span><li><span data-ttu-id="9f083-121">宣告</span><span class="sxs-lookup"><span data-stu-id="9f083-121">Announcements</span></span></li><li><span data-ttu-id="9f083-122">第1行</span><span class="sxs-lookup"><span data-stu-id="9f083-122">Line 1</span></span></li><li><span data-ttu-id="9f083-123">第2行</span><span class="sxs-lookup"><span data-stu-id="9f083-123">Line 2</span></span></li><li><span data-ttu-id="9f083-124">第3行</span><span class="sxs-lookup"><span data-stu-id="9f083-124">Line 3</span></span></li><li><span data-ttu-id="9f083-125">引起</span><span class="sxs-lookup"><span data-stu-id="9f083-125">Safety</span></span></li><li><span data-ttu-id="9f083-126">培训</span><span class="sxs-lookup"><span data-stu-id="9f083-126">Training</span></span></li><li><span data-ttu-id="9f083-127">维护</span><span class="sxs-lookup"><span data-stu-id="9f083-127">Maintenance</span></span></li><li><span data-ttu-id="9f083-128">有趣的资料</span><span class="sxs-lookup"><span data-stu-id="9f083-128">Fun stuff</span></span></li></ul> <span data-ttu-id="9f083-129">识别</span><span class="sxs-lookup"><span data-stu-id="9f083-129">Apps:</span></span> <ul><li><span data-ttu-id="9f083-130">源自</span><span class="sxs-lookup"><span data-stu-id="9f083-130">Wiki</span></span></li></ul>|
||||