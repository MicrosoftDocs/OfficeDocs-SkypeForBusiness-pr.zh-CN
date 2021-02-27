---
title: 升级到 Teams 的先决条件和环境依赖项
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 使用本指南了解在组织中部署 Teams 的先决条件和环境依赖项
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
ms.openlocfilehash: b0ad5716dbbe1925a93f4fbfadca7084e39a9599
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347803"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="55a22-103">Teams 的先决条件和环境依赖项</span><span class="sxs-lookup"><span data-stu-id="55a22-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="55a22-104">![升级过程图，强调技术准备阶段](media/upgrade-banner-tech-readiness.png "升级旅程的阶段，侧重于技术准备阶段")</span><span class="sxs-lookup"><span data-stu-id="55a22-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="55a22-105">本文是升级过程的技术准备阶段（与用户就绪性阶段并行完成的活动）的一部分。</span><span class="sxs-lookup"><span data-stu-id="55a22-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="55a22-106">在继续之前，请确认已完成上述阶段中的这些活动：</span><span class="sxs-lookup"><span data-stu-id="55a22-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="55a22-107">已登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="55a22-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="55a22-108">定义项目范围</span><span class="sxs-lookup"><span data-stu-id="55a22-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="55a22-109">了解 Skype for Business 和 Teams 的共存和互操作性</span><span class="sxs-lookup"><span data-stu-id="55a22-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="55a22-110">选择了升级旅程</span><span class="sxs-lookup"><span data-stu-id="55a22-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="55a22-111">Teams 结合了多个 Microsoft 365 和 Office 365 服务，因此依赖于这些服务的正确实现和操作。</span><span class="sxs-lookup"><span data-stu-id="55a22-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="55a22-112">这些服务包括但不限于 SharePoint Online、Exchange Online 和 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="55a22-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="55a22-113">尽管并非所有服务都是必需的，但我们强烈建议实现所有这些服务。</span><span class="sxs-lookup"><span data-stu-id="55a22-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="55a22-114">如果选择不实施某些服务，则会影响 Teams 为组织提供的功能。</span><span class="sxs-lookup"><span data-stu-id="55a22-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="55a22-115">例如，虽然无需实现 SharePoint Online，但 Teams 确实依赖 SharePoint Online 实现某些功能，例如组对话中的文件共享，因此不实现此服务会降低通过客户端提供的功能。</span><span class="sxs-lookup"><span data-stu-id="55a22-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="55a22-116">请参阅以下文章，了解先决条件以及 Teams 如何与其他技术交互：</span><span class="sxs-lookup"><span data-stu-id="55a22-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="55a22-117">如果组织尚未部署任何 Microsoft 365 或 Office 365 工作负荷，请参阅["入门"。](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)</span><span class="sxs-lookup"><span data-stu-id="55a22-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="55a22-118">如果你的组织尚未为 Microsoft 365 或 Office 365 添加或配置已验证的域，请参阅 [域常见问题解答](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)。</span><span class="sxs-lookup"><span data-stu-id="55a22-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="55a22-119">如果组织尚未将标识同步到 Azure Active Directory，请参阅 Microsoft Teams 中的标识 [模型和身份验证](identify-models-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="55a22-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="55a22-120">如果你的组织没有 Exchange Online，请参阅"了解 Exchange 和 Microsoft Teams 如何[交互"。](Exchange-Teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="55a22-120">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="55a22-121">如果你的组织没有 SharePoint Online，请参阅"了解 SharePoint Online 和[OneDrive for Business 如何与 Microsoft Teams 交互"。](SharePoint-OneDrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="55a22-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="55a22-122">了解 [Microsoft 365 组和 Microsoft Teams 如何交互](Office-365-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="55a22-122">To learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="55a22-123">如果你的组织是教育机构，并且你使用学生信息系统，则部署 Microsoft Teams 之前，请参阅"欢迎使用 [Microsoft 学校数据](https://docs.microsoft.com/schooldatasync) 同步"。</span><span class="sxs-lookup"><span data-stu-id="55a22-123">If your organization is an educational institution and you use a Student Information System, see [Welcome to Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="55a22-124">如果你的组织正在考虑公用电话交换网 (PSTN) 呼叫选项，请参阅"语音 - 电话系统和[PSTN](cloud-voice-landing-page.md)连接"（哪个[](calling-plan-landing-page.md)呼叫计划适合你）和电话[系统直接路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="55a22-124">If your organization is considering Public Switched Telephone Network (PSTN) calling options, see [Voice - Phone System and PSTN connectivity](cloud-voice-landing-page.md), [Which Calling Plan is right for you](calling-plan-landing-page.md), and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

- <span data-ttu-id="55a22-125">若要确保在推出 Teams 之前满足所有网络要求，请参阅"为 Microsoft Teams 准备组织的[网络"。](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="55a22-125">To ensure all network requirements have been met before rolling out Teams, see [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

- <span data-ttu-id="55a22-126">如果你当前正在使用 Skype for Business Online 连接器管理服务，则需要移动到 Teams PowerShell 模块并更新现有的 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="55a22-126">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="55a22-127">有关详细信息 [，请参阅](teams-powershell-move-from-sfbo.md) "从 Skype for Business Online 连接器移动到 Teams PowerShell 模块"。</span><span class="sxs-lookup"><span data-stu-id="55a22-127">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="55a22-128">验证环境满足所有适用的先决条件后，请 [评估 Teams 的当前环境](upgrade-plan-journey-evaluate-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="55a22-128">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
