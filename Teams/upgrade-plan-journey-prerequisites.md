---
title: Microsoft 团队先决条件 |依赖关系采用升级
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 使用本指南了解在组织中部署团队的先决条件和环境相关性
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dbdb59bc5239b8982e330972188ec15527312d22
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548538"
---
<span data-ttu-id="7db15-103">![升级旅行图, 强调技术准备阶段](media/upgrade-banner-tech-readiness.png "升级旅程的阶段, 重点介绍技术准备阶段")</span><span class="sxs-lookup"><span data-stu-id="7db15-103">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="7db15-104">本文是您的升级过程的技术准备阶段的一部分, 与用户准备阶段并行完成的活动。</span><span class="sxs-lookup"><span data-stu-id="7db15-104">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="7db15-105">在继续之前, 请确认您已完成以前阶段中的这些活动:</span><span class="sxs-lookup"><span data-stu-id="7db15-105">Before proceeding, confirm that you’ve completed these activities from previous stages:</span></span>

- [<span data-ttu-id="7db15-106">已登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="7db15-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="7db15-107">已定义项目范围</span><span class="sxs-lookup"><span data-stu-id="7db15-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="7db15-108">了解 Skype for Business 和团队的共存和互操作性</span><span class="sxs-lookup"><span data-stu-id="7db15-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="7db15-109">已选择升级旅程</span><span class="sxs-lookup"><span data-stu-id="7db15-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="7db15-110">团队的先决条件和环境依赖关系</span><span class="sxs-lookup"><span data-stu-id="7db15-110">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="7db15-111">团队合并多个 Office 365 服务, 因此依赖于这些服务的正确实现和操作。</span><span class="sxs-lookup"><span data-stu-id="7db15-111">Teams combines multiple Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="7db15-112">这些服务包括 (但不限于) SharePoint Online、Exchange Online 和 OneDrive for business。</span><span class="sxs-lookup"><span data-stu-id="7db15-112">These services include—but aren’t limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="7db15-113">尽管并非所有服务都是必需的, 但我们强烈建议你实现所有服务。</span><span class="sxs-lookup"><span data-stu-id="7db15-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="7db15-114">如果您选择不实施某些服务, 它将影响团队可为您的组织提供的功能。</span><span class="sxs-lookup"><span data-stu-id="7db15-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="7db15-115">例如, 虽然您不必实现 SharePoint Online, 但团队确实依赖于 SharePoint Online 执行某些功能 (如组对话中的文件共享), 因此不实现此服务将减少通过客户端.</span><span class="sxs-lookup"><span data-stu-id="7db15-115">For example, though you don’t have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="7db15-116">请参阅以下文章, 了解有关先决条件以及团队如何与其他技术交互的方法:</span><span class="sxs-lookup"><span data-stu-id="7db15-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="7db15-117">如果你的组织尚未部署任何 Office 365 工作负荷, 请参阅[office 365 for business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)入门。</span><span class="sxs-lookup"><span data-stu-id="7db15-117">If your organization hasn’t deployed any Office 365 workloads, see [Getting Started with Office 365 for business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="7db15-118">如果你的组织尚未为 Office 365 添加或配置验证的域, 请参阅[验证你的 office 365 域](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)。</span><span class="sxs-lookup"><span data-stu-id="7db15-118">If your organization hasn’t added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="7db15-119">如果你的组织尚未将身份与 Azure Active Directory 同步, 请参阅[Microsoft 团队中的身份模型和身份验证](identify-models-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="7db15-119">If your organization hasn’t synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="7db15-120">如果您的组织不是¹ t 拥有 Exchange Online, 请参阅[了解 exchange 和 Microsoft 团队如何交互](Exchange-Teams-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="7db15-120">If your organization doesn¹t have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="7db15-121">如果你的组织没有 SharePoint Online, 请参阅[了解 Sharepoint online 和 OneDrive For business 如何与 Microsoft 团队进行交互](SharePoint-OneDrive-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="7db15-121">If your organization doesn’t have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="7db15-122">了解[Office 365 组和 Microsoft 团队如何交互](Office-365-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="7db15-122">Learn how [Office 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="7db15-123">如果您的组织是教育机构, 并且您使用学生信息系统, 请在部署 Microsoft 团队之前[部署学校数据同步](https://docs.microsoft.com/schooldatasync)。</span><span class="sxs-lookup"><span data-stu-id="7db15-123">If your organization is an educational institution and you use a Student Information System, [deploy School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

<span data-ttu-id="7db15-124">验证你的环境满足所有适用的先决条件后, 请[评估团队的当前环境](upgrade-plan-journey-evaluate-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="7db15-124">After you’ve verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
