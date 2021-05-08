---
title: 升级到新环境的先决条件和环境Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 使用本指南了解在组织中部署Teams先决条件和环境依赖项
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e9924c24f19da3cf17f8e8a124a03acc294c24b4
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282159"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="78877-103">先决条件和环境依赖项Teams</span><span class="sxs-lookup"><span data-stu-id="78877-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="78877-104">![升级过程图，强调技术准备阶段](media/upgrade-banner-tech-readiness.png "升级过程阶段，着重强调技术准备阶段")</span><span class="sxs-lookup"><span data-stu-id="78877-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="78877-105">本文是升级过程的技术准备阶段（与用户准备阶段并行完成的活动）的一部分。</span><span class="sxs-lookup"><span data-stu-id="78877-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="78877-106">在继续之前，请确认已完成之前阶段中的这些活动：</span><span class="sxs-lookup"><span data-stu-id="78877-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="78877-107">登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="78877-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="78877-108">请确定项目范围</span><span class="sxs-lookup"><span data-stu-id="78877-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="78877-109">了解两者共存Skype for Business互操作性Teams</span><span class="sxs-lookup"><span data-stu-id="78877-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="78877-110">选择了升级旅程</span><span class="sxs-lookup"><span data-stu-id="78877-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="78877-111">Teams服务Microsoft 365 Office 365服务，因此依赖于这些服务的正确实现和操作。</span><span class="sxs-lookup"><span data-stu-id="78877-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="78877-112">这些服务包括但不限于联机、SharePoint和Exchange Online OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="78877-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="78877-113">虽然并非所有服务都是必需的，但我们强烈建议实现所有这些服务。</span><span class="sxs-lookup"><span data-stu-id="78877-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="78877-114">如果选择不实现某些服务，它将影响组织Teams的功能。</span><span class="sxs-lookup"><span data-stu-id="78877-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="78877-115">例如，虽然无需实现 SharePoint Online，Teams 确实依赖于 SharePoint Online 实现某些功能，例如组对话中的文件共享，因此不实现此服务会减少通过客户端提供的功能。</span><span class="sxs-lookup"><span data-stu-id="78877-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="78877-116">请参阅以下文章，了解先决条件以及如何Teams技术交互：</span><span class="sxs-lookup"><span data-stu-id="78877-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="78877-117">如果组织尚未部署任何Microsoft 365或Office 365，请参阅[入门](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)。</span><span class="sxs-lookup"><span data-stu-id="78877-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="78877-118">如果你的组织尚未添加或配置已验证的域Microsoft 365或Office 365，请参阅域[常见问题](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)解答。</span><span class="sxs-lookup"><span data-stu-id="78877-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="78877-119">如果组织尚未将标识同步到Azure Active Directory，请参阅标识[模型和身份验证Microsoft Teams。](identify-models-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="78877-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="78877-120">如果您的组织没有 Exchange Online，请参阅[了解 Exchange 与 Microsoft Teams 如何交互](Exchange-Teams-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="78877-120">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="78877-121">如果您的组织没有 SharePoint Online，请参阅[了解 SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](SharePoint-OneDrive-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="78877-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="78877-122">若要了解如何[Microsoft 365组Microsoft Teams交互](Office-365-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="78877-122">To learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="78877-123">如果你的组织是教育机构，并且你使用学生信息系统，请参阅在部署学校数据同步之前欢迎使用[Microsoft](/schooldatasync) Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="78877-123">If your organization is an educational institution and you use a Student Information System, see [Welcome to Microsoft School Data Sync](/schooldatasync) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="78877-124">如果你的组织考虑使用公用电话交换网 (PSTN) 呼叫选项，请参阅语音 - 电话系统 和[PSTN](cloud-voice-landing-page.md)连接、哪个呼叫[](calling-plan-landing-page.md)计划适合你和 电话系统[直接路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="78877-124">If your organization is considering Public Switched Telephone Network (PSTN) calling options, see [Voice - Phone System and PSTN connectivity](cloud-voice-landing-page.md), [Which Calling Plan is right for you](calling-plan-landing-page.md), and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

- <span data-ttu-id="78877-125">若要确保在推出前满足所有网络要求Teams，请参阅[准备](prepare-network.md)组织的网络以Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="78877-125">To ensure all network requirements have been met before rolling out Teams, see [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

- <span data-ttu-id="78877-126">如果当前使用 Skype for Business Online 连接器来管理服务，则需要移动到 powerShell Teams并更新现有的 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="78877-126">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="78877-127">有关详细信息[，请参阅](teams-powershell-move-from-sfbo.md)从 Skype for Business Online 连接器移动到 Teams PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="78877-127">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="78877-128">验证环境满足所有适用的先决条件后，请评估当前[环境](upgrade-plan-journey-evaluate-environment.md)Teams。</span><span class="sxs-lookup"><span data-stu-id="78877-128">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>