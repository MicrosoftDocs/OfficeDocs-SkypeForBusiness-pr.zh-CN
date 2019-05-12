---
title: Microsoft 团队系统必备组件 |依赖项应用升级
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 使用本指南可了解有关先决条件和环境依赖项以在组织中部署团队
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 784c2ac08ca6dbfece5cdc8c99fee2b308325576
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895930"
---
<span data-ttu-id="8fd41-103">![升级旅程，重点强调的技术的准备阶段的阶段](media/upgrade-banner-tech-readiness.png "升级旅程，重点强调的技术的准备阶段的阶段")</span><span class="sxs-lookup"><span data-stu-id="8fd41-103">![Stages of the upgrade journey, with emphasis on the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="8fd41-104">本文是您升级旅程，与用户准备阶段并行完成的活动的技术的准备阶段的一部分。</span><span class="sxs-lookup"><span data-stu-id="8fd41-104">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="8fd41-105">在继续之前，确认您已完成从以前的阶段的这些活动：</span><span class="sxs-lookup"><span data-stu-id="8fd41-105">Before proceeding, confirm that you’ve completed these activities from previous stages:</span></span>

- [<span data-ttu-id="8fd41-106">登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="8fd41-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="8fd41-107">定义您的项目范围</span><span class="sxs-lookup"><span data-stu-id="8fd41-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="8fd41-108">商业和团队理解共存和 Skype 的互操作性</span><span class="sxs-lookup"><span data-stu-id="8fd41-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="8fd41-109">选择您升级旅程</span><span class="sxs-lookup"><span data-stu-id="8fd41-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="8fd41-110">先决条件和团队环境依赖项</span><span class="sxs-lookup"><span data-stu-id="8fd41-110">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="8fd41-111">团队结合使用多个 Office 365 服务，因此依赖的正确实现和操作这些服务。</span><span class="sxs-lookup"><span data-stu-id="8fd41-111">Teams combines multiple Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="8fd41-112">这些服务包括 — 但不限于 — SharePoint Online 和 Exchange Online 的 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="8fd41-112">These services include—but aren’t limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="8fd41-113">尽管并非所有服务都都需要，但强烈建议您实现所有这些。</span><span class="sxs-lookup"><span data-stu-id="8fd41-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="8fd41-114">如果您选择不实现某些服务，它会影响团队可以提供您的组织的功能。</span><span class="sxs-lookup"><span data-stu-id="8fd41-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="8fd41-115">例如，您无需实现 SharePoint Online，但团队依赖 SharePoint Online 的某些功能如文件共享中组对话，因此不实现此服务将降低通过提供的功能客户端。</span><span class="sxs-lookup"><span data-stu-id="8fd41-115">For example, though you don’t have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="8fd41-116">请参阅以下文章以了解有关先决条件和团队与其他技术的交互方式：</span><span class="sxs-lookup"><span data-stu-id="8fd41-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="8fd41-117">如果您的组织未部署任何 Office 365 工作负载，请参阅[Getting Started with Office 365 的业务](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)。</span><span class="sxs-lookup"><span data-stu-id="8fd41-117">If your organization hasn’t deployed any Office 365 workloads, see [Getting Started with Office 365 for business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="8fd41-118">如果贵组织尚未添加或 Office 365 配置已验证的域，请参阅[Verify Office 365 域](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)。</span><span class="sxs-lookup"><span data-stu-id="8fd41-118">If your organization hasn’t added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="8fd41-119">如果贵组织尚未同步到 Azure Active Directory 标识，请参阅[标识模型和 Microsoft 团队中的身份验证](identify-models-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="8fd41-119">If your organization hasn’t synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="8fd41-120">如果您的组织 doesn¹t Exchange Online，请参阅[的了解 Exchange 和 Microsoft 团队的交互方式](Exchange-Teams-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="8fd41-120">If your organization doesn¹t have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="8fd41-121">如果您的组织没有 SharePoint Online，请参阅[的了解 SharePoint Online 和 OneDrive for Business 如何与 Microsoft 团队交互](SharePoint-OneDrive-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="8fd41-121">If your organization doesn’t have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="8fd41-122">了解如何[Office 365 组和 Microsoft 团队进行交互](Office-365-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="8fd41-122">Learn how [Office 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="8fd41-123">如果您的组织是教育机构并使用学生信息系统，然后再部署 Microsoft 团队[部署学校数据同步](https://docs.microsoft.com/schooldatasync)。</span><span class="sxs-lookup"><span data-stu-id="8fd41-123">If your organization is an educational institution and you use a Student Information System, [deploy School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

<span data-ttu-id="8fd41-124">后验证了您的环境符合[评估当前环境团队](upgrade-plan-journey-evaluate-environment.md)的所有适用的先决条件。</span><span class="sxs-lookup"><span data-stu-id="8fd41-124">After you’ve verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
