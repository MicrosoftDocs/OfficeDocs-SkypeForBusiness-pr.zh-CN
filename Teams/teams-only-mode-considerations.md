---
title: 仅 Teams 模式注意事项
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: 管理员可以了解如何在管理中心中Microsoft Teams升级到仅Microsoft Teams模式。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b2232d4774a31f3b081b2410371a5903debe9123
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239009"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="58b62-103">仅 Teams 模式注意事项</span><span class="sxs-lookup"><span data-stu-id="58b62-103">Teams Only mode considerations</span></span>

<span data-ttu-id="58b62-104">组织或Microsoft 365 Office 365管理员可以将单个用户或整个租户升级到Teams模式。</span><span class="sxs-lookup"><span data-stu-id="58b62-104">Administrators of Microsoft 365 or Office 365 organizations can upgrade either individual users or the entire tenant to Teams Only mode.</span></span>  

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="58b62-105">升级到仅Teams模式通过单个客户端体验为用户提供 Microsoft Teams（Microsoft 365 或 Office 365 团队协作的中心）的全部优势。</span><span class="sxs-lookup"><span data-stu-id="58b62-105">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Microsoft 365 or Office 365, via a single client experience.</span></span> <span data-ttu-id="58b62-106">仅Teams模式的用户将在 Teams 中接收所有呼叫和聊天，无论发送方使用的是 Skype for Business 还是 Teams，并且受益于互操作和联合身份验证支持。</span><span class="sxs-lookup"><span data-stu-id="58b62-106">Users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="58b62-107">尽管成千上万的客户已成功升级到 Microsoft Teams，但有些注意事项可能会影响组织的升级时间线和用户体验。</span><span class="sxs-lookup"><span data-stu-id="58b62-107">Although thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization's upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="58b62-108">为了实现最佳用户体验，请先确认 Teams 满足你的协作和通信要求，确保你的网络可以支持 Teams，以及实施你的用户就绪计划，然后再将用户升级到 Teams。</span><span class="sxs-lookup"><span data-stu-id="58b62-108">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="58b62-109">如果只是开始进行升级规划，请务必查看我们的升级Microsoft Teams[入门](upgrade-start-here.md)。</span><span class="sxs-lookup"><span data-stu-id="58b62-109">If you are just starting your upgrade planning, be sure to review our [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md) guide.</span></span> 

<span data-ttu-id="58b62-110">**共存注意事项**：已使用 Skype for Business Online 和/或 Skype for Business Server 的组织Teams其环境中以满足其需求的速度引入资源。</span><span class="sxs-lookup"><span data-stu-id="58b62-110">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="58b62-111">组织可根据需要以Teams方式向一组所需用户推出服务，使用 Teams 的用户可以与使用 Skype for Business 的用户进行通信。反之亦然。</span><span class="sxs-lookup"><span data-stu-id="58b62-111">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="58b62-112">为了管理此体验，管理员使用共存模式来定义最终用户客户端体验、传入聊天和呼叫的路由行为，以及新会议是安排在 Teams 还是 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="58b62-112">To manage this experience, administrators use coexistence modes, which define the end-user client experience, the routing behavior of incoming chats and calls, and whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="58b62-113">如果用户已升级到"仅"，则用户可以与其他Teams **联合**;但是，当两个用户都使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="58b62-113">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="58b62-114">升级到"仅Teams的用户仍可加入Skype for Business会议。</span><span class="sxs-lookup"><span data-stu-id="58b62-114">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="58b62-115">有关共存的更多详细信息，请参阅了解Microsoft Teams Skype for Business[和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="58b62-115">For more detailed information about coexistence, please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> <span data-ttu-id="58b62-116">有关使用使用者Teams Skype (服务) ，请参阅Teams[和Skype互操作性](teams-skype-interop.md)。</span><span class="sxs-lookup"><span data-stu-id="58b62-116">For more information about Teams and Skype (Consumer), see [Teams and Skype interoperability](teams-skype-interop.md).</span></span>


<span data-ttu-id="58b62-117">**特定于用户的注意事项**：某些用户方案仍在不断发展，管理员可能会决定在升级组织中其他用户时暂时推迟某些用户的升级。</span><span class="sxs-lookup"><span data-stu-id="58b62-117">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="58b62-118">具体而言，我们仍在努力解决主要设备基于 VDI 的用户的方案。</span><span class="sxs-lookup"><span data-stu-id="58b62-118">In particular, we are still working on addressing scenarios for users whose primary device is VDI-based.</span></span> <span data-ttu-id="58b62-119">有关站点公告，请监视Microsoft 365[路线图](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="58b62-119">For site announcements, monitor the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

> [!NOTE]
> <span data-ttu-id="58b62-120">在移动到"仅Teams模式之前，需要替换或更新不支持此Teams。</span><span class="sxs-lookup"><span data-stu-id="58b62-120">Before you move to Teams Only mode you need to replace or update devices that don't support Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="58b62-121">**请记住**：迁移到 Teams不仅仅是技术迁移。</span><span class="sxs-lookup"><span data-stu-id="58b62-121">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="58b62-122">成功升级会评估技术准备情况以及最终用户准备情况。</span><span class="sxs-lookup"><span data-stu-id="58b62-122">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="58b62-123">请查看我们的Skype for Business Teams指南，详细了解如何[](upgrade-framework.md)规划升级到 Teams。</span><span class="sxs-lookup"><span data-stu-id="58b62-123">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  
