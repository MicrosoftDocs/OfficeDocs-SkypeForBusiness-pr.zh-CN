---
title: 使用Teams管理中心中的政府模板
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
description: 了解如何使用。 Teams模板，通过使用管理中心提供预定义的设置、通道和预安装的应用，创建专为政府需求设计的团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: db22de142b9e7f2bead93e607dd01c9dd362ddba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092210"
---
# <a name="use-teams-government-templates-in-the-admin-center"></a><span data-ttu-id="6a248-104">使用Teams管理中心中的政府模板</span><span class="sxs-lookup"><span data-stu-id="6a248-104">Use Teams government templates in the admin center</span></span>

<span data-ttu-id="6a248-105">Teams 模板提供预定义的设置、频道和预安装的应用模板，让你能够快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="6a248-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="6a248-106">Teams模板具有围绕政府需求设计的团队结构的预生成定义。</span><span class="sxs-lookup"><span data-stu-id="6a248-106">Teams templates have pre-built definitions of team structures designed around governmental needs.</span></span> <span data-ttu-id="6a248-107">你还可以扩展 Teams 模板，以创建根据特定组织需求量身定制的团队。</span><span class="sxs-lookup"><span data-stu-id="6a248-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="6a248-108">本文介绍每个Teams模板，并推荐其使用方法。</span><span class="sxs-lookup"><span data-stu-id="6a248-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="6a248-109">如果你负责规划、部署和管理整个政府组织的多个团队，则本文适合你。</span><span class="sxs-lookup"><span data-stu-id="6a248-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your governmental organization.</span></span> <span data-ttu-id="6a248-110">你已在贵组织内部署 Teams 服务。</span><span class="sxs-lookup"><span data-stu-id="6a248-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="6a248-111">如果尚未部署 Teams，首先请阅读[如何部署 Microsoft Teams](./deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="6a248-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="6a248-112">若要了解有关常规团队模板的详细信息，请参阅[开始使用 Teams 模板](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="6a248-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="coordinate-incident-response"></a><span data-ttu-id="6a248-113">协调事件响应</span><span class="sxs-lookup"><span data-stu-id="6a248-113">Coordinate incident response</span></span>

<span data-ttu-id="6a248-114">集中沟通和关键资源，以用于您的紧急管理或事件响应团队。</span><span class="sxs-lookup"><span data-stu-id="6a248-114">Centralize communication and critical resources for your crisis management or incident response team.</span></span> <span data-ttu-id="6a248-115">在此团队中，您可以包括许多不同类型的文件，以帮助创建所有文档的一个中央位置。</span><span class="sxs-lookup"><span data-stu-id="6a248-115">Within this team, you can include many different types of files to help create a central place for all your documents.</span></span> <span data-ttu-id="6a248-116">使用联机会议改进信息流和态势感知。</span><span class="sxs-lookup"><span data-stu-id="6a248-116">Use online meetings to improve information flow and situational awareness.</span></span>

| <span data-ttu-id="6a248-117">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="6a248-117">Base template type</span></span> |<span data-ttu-id="6a248-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="6a248-118">baseTemplateId</span></span> | <span data-ttu-id="6a248-119">此基本模板包含的属性</span><span class="sxs-lookup"><span data-stu-id="6a248-119">Properties that come with this base template</span></span> |
|-------------------|-------|---------------------------------------------------------------------------|
|<span data-ttu-id="6a248-120">协调事件响应</span><span class="sxs-lookup"><span data-stu-id="6a248-120">Coordinate incident response</span></span>|`com.microsoft.teams.template.CoordinateIncidentResponse`|<span data-ttu-id="6a248-121">频道：</span><span class="sxs-lookup"><span data-stu-id="6a248-121">Channels:</span></span> <ul><li><span data-ttu-id="6a248-122">常规</span><span class="sxs-lookup"><span data-stu-id="6a248-122">General</span></span><li><span data-ttu-id="6a248-123">公告</span><span class="sxs-lookup"><span data-stu-id="6a248-123">Announcements</span></span></li><li><span data-ttu-id="6a248-124">后勤工作</span><span class="sxs-lookup"><span data-stu-id="6a248-124">Logistics</span></span></li><li><span data-ttu-id="6a248-125">规划</span><span class="sxs-lookup"><span data-stu-id="6a248-125">Planning</span></span></li><li><span data-ttu-id="6a248-126">恢复</span><span class="sxs-lookup"><span data-stu-id="6a248-126">Recovery</span></span></li><li><span data-ttu-id="6a248-127">紧急</span><span class="sxs-lookup"><span data-stu-id="6a248-127">Urgent</span></span></li></ul> <span data-ttu-id="6a248-128">应用：</span><span class="sxs-lookup"><span data-stu-id="6a248-128">Apps:</span></span> <ul><li><span data-ttu-id="6a248-129">Wiki</span><span class="sxs-lookup"><span data-stu-id="6a248-129">Wiki</span></span></li><li><span data-ttu-id="6a248-130">Excel</span><span class="sxs-lookup"><span data-stu-id="6a248-130">Excel</span></span></li><li><span data-ttu-id="6a248-131">OneNote</span><span class="sxs-lookup"><span data-stu-id="6a248-131">OneNote</span></span></li><li><span data-ttu-id="6a248-132">SharePoint</span><span class="sxs-lookup"><span data-stu-id="6a248-132">SharePoint</span></span></li><li><span data-ttu-id="6a248-133">Planner</span><span class="sxs-lookup"><span data-stu-id="6a248-133">Planner</span></span></li></ul>|
||||