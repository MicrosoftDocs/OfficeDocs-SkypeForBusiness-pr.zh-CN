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
description: 管理员可以了解如何在 Microsoft Teams 管理中心准备升级到 Microsoft Teams 仅模式。
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
ms.openlocfilehash: 4a38967ffb80f59fab88006b5aad2e6ecb76395c
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460992"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="638c1-103">仅 Teams 模式注意事项</span><span class="sxs-lookup"><span data-stu-id="638c1-103">Teams Only mode considerations</span></span>

<span data-ttu-id="638c1-104">Microsoft 365 或 Office 365 组织的管理员可以将单个用户或整个租户升级到 Teams Only 模式。</span><span class="sxs-lookup"><span data-stu-id="638c1-104">Administrators of Microsoft 365 or Office 365 organizations can upgrade either individual users or the entire tenant to Teams Only mode.</span></span>  

<span data-ttu-id="638c1-105">升级到 Teams Only 模式可为用户提供 Microsoft Teams（Microsoft 365 或 Office 365 中团队合作的中心）的全部优势，只需一个客户端体验。</span><span class="sxs-lookup"><span data-stu-id="638c1-105">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Microsoft 365 or Office 365, via a single client experience.</span></span> <span data-ttu-id="638c1-106">无论发送方使用的是 Skype for Business 还是 Teams，Teams 模式的用户都将在 Teams 中接收所有呼叫和聊天，并且受益于互操作和联合支持。</span><span class="sxs-lookup"><span data-stu-id="638c1-106">Users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="638c1-107">尽管成千上万的客户已成功升级到 Microsoft Teams，但有些注意事项可能会影响组织的升级时间线和用户体验。</span><span class="sxs-lookup"><span data-stu-id="638c1-107">Although thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization's upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="638c1-108">为了实现最佳用户体验，请先确认 Teams 满足你的协作和通信要求，确保你的网络可以支持 Teams，以及实施你的用户就绪计划，然后再将用户升级到 Teams。</span><span class="sxs-lookup"><span data-stu-id="638c1-108">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="638c1-109">如果刚开始进行升级规划，请务必查看 [Microsoft Teams](upgrade-start-here.md) 升级指南入门。</span><span class="sxs-lookup"><span data-stu-id="638c1-109">If you are just starting your upgrade planning, be sure to review our [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md) guide.</span></span> 

<span data-ttu-id="638c1-110">**共存注意事项**：已使用 Skype for Business Online 和/或 Skype for Business Server 的组织可以加速将 Teams 引入其环境以满足其需求。</span><span class="sxs-lookup"><span data-stu-id="638c1-110">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="638c1-111">组织可根据需要以增量方式向一组所需用户推出 Teams，使用 Teams 的用户可以与使用 Skype for Business 的用户进行通信，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="638c1-111">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="638c1-112">为了管理此体验，管理员使用共存模式，这些模式定义最终用户客户端体验、传入聊天和呼叫的路由行为，以及是否在 Teams 或 Skype for Business 中安排新会议。</span><span class="sxs-lookup"><span data-stu-id="638c1-112">To manage this experience, administrators use coexistence modes, which define the end-user client experience, the routing behavior of incoming chats and calls, and whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="638c1-113">如果用户升级到"仅 Teams"，则用户可以与其他组织的用户 **联合**;但是，当两个用户都使用 Teams 时，提供最佳体验。</span><span class="sxs-lookup"><span data-stu-id="638c1-113">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="638c1-114">升级到 Teams Only 的用户仍可加入 Skype for Business 会议。</span><span class="sxs-lookup"><span data-stu-id="638c1-114">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="638c1-115">有关共存的更多详细信息，请参阅了解 Microsoft Teams 和 [Skype for Business 共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="638c1-115">For more detailed information about coexistence, please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> <span data-ttu-id="638c1-116">有关 Teams 和 Skype (Consumer) ，请参阅 [Teams 和 Skype 互操作性](teams-skype-interop.md)。</span><span class="sxs-lookup"><span data-stu-id="638c1-116">For more information about Teams and Skype (Consumer), see [Teams and Skype interoperability](teams-skype-interop.md).</span></span>


<span data-ttu-id="638c1-117">**特定于用户的注意事项**：某些用户方案仍在不断发展，管理员可能会决定在升级组织中其他用户时暂时推迟某些用户的升级。</span><span class="sxs-lookup"><span data-stu-id="638c1-117">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="638c1-118">具体而言，我们仍在努力解决主要设备基于 VDI 的用户的方案。</span><span class="sxs-lookup"><span data-stu-id="638c1-118">In particular, we are still working on addressing scenarios for users whose primary device is VDI-based.</span></span> <span data-ttu-id="638c1-119">有关站点公告，请监视 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="638c1-119">For site announcements, monitor the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

> [!NOTE]
> <span data-ttu-id="638c1-120">在移动到"仅 Teams"模式之前，需要替换或更新不支持 Teams 的设备。</span><span class="sxs-lookup"><span data-stu-id="638c1-120">Before you move to Teams Only mode you need to replace or update devices that don't support Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="638c1-121">**请记住**：迁移到 Teams 不仅仅是技术迁移。</span><span class="sxs-lookup"><span data-stu-id="638c1-121">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="638c1-122">成功的升级会评估技术就绪状态和最终用户就绪性。</span><span class="sxs-lookup"><span data-stu-id="638c1-122">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="638c1-123">查看我们的 Skype for Business 到 Teams 升级 [指南](upgrade-framework.md) ，详细了解如何规划升级到 Teams 的规划。</span><span class="sxs-lookup"><span data-stu-id="638c1-123">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  
