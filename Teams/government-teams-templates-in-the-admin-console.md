---
title: 在管理中心中使用团队政府模板
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
description: 了解如何使用。 团队模板：通过使用管理中心提供预定义的设置、信道和预安装应用来创建专为政府需求设计的团队结构。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 993cabc7139edeb971f60f1cdf44428fb4083db9
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655509"
---
# <a name="use-teams-government-templates-in-the-admin-center"></a><span data-ttu-id="33b4f-104">在管理中心中使用团队政府模板</span><span class="sxs-lookup"><span data-stu-id="33b4f-104">Use Teams government templates in the admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="33b4f-105">团队模板使你可以通过提供设置、频道和预安装应用的预定义模板来快速轻松地创建团队。</span><span class="sxs-lookup"><span data-stu-id="33b4f-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="33b4f-106">团队模板具有围绕政府需求设计的团队结构的预建定义。</span><span class="sxs-lookup"><span data-stu-id="33b4f-106">Teams templates have pre-built definitions of team structures designed around governmental needs.</span></span> <span data-ttu-id="33b4f-107">您还可以扩展团队模板以创建根据您的特定组织需求量身定制的团队。</span><span class="sxs-lookup"><span data-stu-id="33b4f-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="33b4f-108">在本文中，我们将介绍每个团队模板并建议如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="33b4f-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="33b4f-109">本文适用于你负责在政府组织中规划、部署和管理多个团队的情况。</span><span class="sxs-lookup"><span data-stu-id="33b4f-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your governmental organization.</span></span> <span data-ttu-id="33b4f-110">你已在你的组织中部署团队服务。</span><span class="sxs-lookup"><span data-stu-id="33b4f-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="33b4f-111">如果尚未推出团队，请先阅读 [如何展示 Microsoft 团队](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="33b4f-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="33b4f-112">若要深入了解有关团队模板的详细信息，请参阅 [团队模板入门](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="33b4f-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="coordinate-incident-response"></a><span data-ttu-id="33b4f-113">协调事件响应</span><span class="sxs-lookup"><span data-stu-id="33b4f-113">Coordinate incident response</span></span>

<span data-ttu-id="33b4f-114">集中管理危机管理或事件响应团队的沟通和关键资源。</span><span class="sxs-lookup"><span data-stu-id="33b4f-114">Centralize communication and critical resources for your crisis management or incident response team.</span></span> <span data-ttu-id="33b4f-115">在此团队中，你可以包含许多不同类型的文件，以便为你的所有文档创建一个中心位置。</span><span class="sxs-lookup"><span data-stu-id="33b4f-115">Within this team, you can include many different types of files to help create a central place for all your documents.</span></span> <span data-ttu-id="33b4f-116">使用联机会议改善信息流和形势意识。</span><span class="sxs-lookup"><span data-stu-id="33b4f-116">Use online meetings to improve information flow and situational awareness.</span></span>

| <span data-ttu-id="33b4f-117">基本模板类型</span><span class="sxs-lookup"><span data-stu-id="33b4f-117">Base template type</span></span> |<span data-ttu-id="33b4f-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="33b4f-118">baseTemplateId</span></span> | <span data-ttu-id="33b4f-119">此基本模板附带的属性</span><span class="sxs-lookup"><span data-stu-id="33b4f-119">Properties that come with this base template</span></span> |
|-------------------|-------|---------------------------------------------------------------------------|
|<span data-ttu-id="33b4f-120">协调事件响应</span><span class="sxs-lookup"><span data-stu-id="33b4f-120">Coordinate incident response</span></span>|`com.microsoft.teams.template.CoordinateIncidentResponse` |<span data-ttu-id="33b4f-121">信道</span><span class="sxs-lookup"><span data-stu-id="33b4f-121">Channels:</span></span> <ul><li><span data-ttu-id="33b4f-122">常规</span><span class="sxs-lookup"><span data-stu-id="33b4f-122">General</span></span><li><span data-ttu-id="33b4f-123">宣告</span><span class="sxs-lookup"><span data-stu-id="33b4f-123">Announcements</span></span></li><li><span data-ttu-id="33b4f-124">后勤工作</span><span class="sxs-lookup"><span data-stu-id="33b4f-124">Logistics</span></span></li><li><span data-ttu-id="33b4f-125">规划</span><span class="sxs-lookup"><span data-stu-id="33b4f-125">Planning</span></span></li><li><span data-ttu-id="33b4f-126">恢复</span><span class="sxs-lookup"><span data-stu-id="33b4f-126">Recovery</span></span></li><li><span data-ttu-id="33b4f-127">急需</span><span class="sxs-lookup"><span data-stu-id="33b4f-127">Urgent</span></span></li></ul> <span data-ttu-id="33b4f-128">识别</span><span class="sxs-lookup"><span data-stu-id="33b4f-128">Apps:</span></span> <ul><li><span data-ttu-id="33b4f-129">源自</span><span class="sxs-lookup"><span data-stu-id="33b4f-129">Wiki</span></span></li><li><span data-ttu-id="33b4f-130">Excel</span><span class="sxs-lookup"><span data-stu-id="33b4f-130">Excel</span></span></li><li><span data-ttu-id="33b4f-131">OneNote</span><span class="sxs-lookup"><span data-stu-id="33b4f-131">OneNote</span></span></li><li><span data-ttu-id="33b4f-132">SharePoint</span><span class="sxs-lookup"><span data-stu-id="33b4f-132">SharePoint</span></span></li><li><span data-ttu-id="33b4f-133">Planner</span><span class="sxs-lookup"><span data-stu-id="33b4f-133">Planner</span></span></li></ul>|
||||