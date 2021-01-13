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
description: 管理员可以了解如何准备在 Microsoft Teams 管理中心升级到 Microsoft Teams 仅模式。
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
ms.openlocfilehash: 86c27d8619a436c6a77ab435cfcb2cc4133befe0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802372"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="471bd-103">仅 Teams 模式注意事项</span><span class="sxs-lookup"><span data-stu-id="471bd-103">Teams Only mode considerations</span></span>

<span data-ttu-id="471bd-104">如果你是 Microsoft 365 或 Office 365 组织的管理员，现在你将在 Microsoft Teams 管理中心看到升级到"仅 Teams"模式的选项。</span><span class="sxs-lookup"><span data-stu-id="471bd-104">If you are an administrator in your Microsoft 365 or Office 365 organization, you will now see the option to upgrade to Teams Only mode in the Microsoft Teams admin center.</span></span> <span data-ttu-id="471bd-105">使用此功能，可以升级单个用户，也可以升级整个租户。</span><span class="sxs-lookup"><span data-stu-id="471bd-105">With this functionality you can upgrade either individual users, or alternatively, the entire tenant.</span></span>  

<span data-ttu-id="471bd-106">升级到"仅 Teams"模式可为用户提供 Microsoft Teams（Microsoft 365 或 Office 365 中团队合作的中心）的全部优势，只需一个客户端体验。</span><span class="sxs-lookup"><span data-stu-id="471bd-106">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Microsoft 365 or Office 365, via a single client experience.</span></span> <span data-ttu-id="471bd-107">此外，采用"仅 Teams"模式的用户将在 Teams 中接收所有呼叫和聊天，无论发送方使用的是 Skype for Business 还是 Teams，并且受益于互操作和联合支持。</span><span class="sxs-lookup"><span data-stu-id="471bd-107">Additionally, users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="471bd-108">尽管成千上万的客户已成功升级到 Microsoft Teams，但一些注意事项可能会影响组织的升级时间线和用户体验。</span><span class="sxs-lookup"><span data-stu-id="471bd-108">While thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization's upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="471bd-109">具体而言，选择升级不一定意味着组织已准备好进行此更改。</span><span class="sxs-lookup"><span data-stu-id="471bd-109">In particular, having the option to upgrade doesn't necessarily mean your organization is ready for this change.</span></span> <span data-ttu-id="471bd-110">为了实现最佳用户体验，请先确认 Teams 满足你的协作和通信要求，确保你的网络可以支持 Teams，以及实施你的用户就绪计划，然后再将用户升级到 Teams。</span><span class="sxs-lookup"><span data-stu-id="471bd-110">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="471bd-111">如果刚开始进行升级规划，请务必查看 Microsoft Teams 升级 [指南入门](upgrade-start-here.md) 。</span><span class="sxs-lookup"><span data-stu-id="471bd-111">If you are just starting your upgrade planning, be sure to review our [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md) guide.</span></span> 

<span data-ttu-id="471bd-112">**共存注意事项**：已使用 Skype for Business Online 和/或 Skype for Business Server 的组织可以加速将 Teams 引入其环境以满足其需求。</span><span class="sxs-lookup"><span data-stu-id="471bd-112">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="471bd-113">组织可根据需要以增量方式向一组所需用户推出 Teams，使用 Teams 的用户可以与使用 Skype for Business 的用户进行通信，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="471bd-113">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="471bd-114">为了管理此体验，管理员使用共存模式来定义最终用户客户端体验、传入聊天和通话的路由行为，以及是否在 Teams 或 Skype for Business 中安排新会议。</span><span class="sxs-lookup"><span data-stu-id="471bd-114">To manage this experience, administrators use coexistence modes, which define the end user client experience, the routing behavior of incoming chats and calls, as well as whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="471bd-115">如果用户升级到"仅 Teams"，则用户可以与其他组织 **的用户联合**;但是，当两个用户都使用 Teams 时，提供最佳体验。</span><span class="sxs-lookup"><span data-stu-id="471bd-115">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="471bd-116">升级到 Teams 的用户可以加入 Skype for Business 会议。</span><span class="sxs-lookup"><span data-stu-id="471bd-116">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="471bd-117">有关共存的更多详细信息，请参阅了解 Microsoft Teams 和 [Skype for Business 共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="471bd-117">For more detailed information about coexistence, please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> <span data-ttu-id="471bd-118">有关 Teams 和 Skype (Consumer) ，请参阅 [Teams 和 Skype 互操作性](teams-skype-interop.md)。</span><span class="sxs-lookup"><span data-stu-id="471bd-118">For more information about Teams and Skype (Consumer), see [Teams and Skype interoperability](teams-skype-interop.md).</span></span>

<span data-ttu-id="471bd-119">**租户范围的注意事项**：我们正在努力在下列环境中启用 Teams;但是，目前，如果用户的 Skype for Business 租户托管在下列环境之一中，则管理员不应升级其组织的任何用户：</span><span class="sxs-lookup"><span data-stu-id="471bd-119">**Tenant-wide considerations**: We are working on enabling Teams in the following environments; however, for now, administrators shouldn't upgrade any users in their organization if their Skype for Business tenant is hosted in one of the following environments:</span></span>

 - <span data-ttu-id="471bd-120">由世纪网运营的 Office 365</span><span class="sxs-lookup"><span data-stu-id="471bd-120">Office 365 operated by 21Vianet</span></span>
 - <span data-ttu-id="471bd-121">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="471bd-121">Office 365 Germany</span></span>
 - <span data-ttu-id="471bd-122">Skype for Business 租户托管 **在韩国，** 组织要求 Teams 数据存储在韩国。</span><span class="sxs-lookup"><span data-stu-id="471bd-122">Skype for Business tenant is hosted in South Korea **and** the organization requires Teams data to be stored in South Korea.</span></span> <span data-ttu-id="471bd-123">目前，将 Skype for Business 数据存储在韩国、升级到 Teams 的组织将 Teams 数据存储在亚洲数据中心区域，而不是韩国数据中心区域。</span><span class="sxs-lookup"><span data-stu-id="471bd-123">Currently, organizations with Skype for Business data stored in South Korea that upgrade to Teams will have their Teams data stored in the Asia datacenter region, not in the South Korea datacenter region.</span></span>

<span data-ttu-id="471bd-124">**特定于用户的注意事项**：某些用户方案仍在不断发展，管理员可能会决定在升级组织中其他用户时暂时推迟某些用户的升级。</span><span class="sxs-lookup"><span data-stu-id="471bd-124">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="471bd-125">具体而言，我们仍在努力解决主要设备基于 VDI 的用户的方案。</span><span class="sxs-lookup"><span data-stu-id="471bd-125">In particular, we are still working on addressing scenarios for users whose primary device is VDI-based.</span></span> <span data-ttu-id="471bd-126">有关公告，请监视 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap) 网站。</span><span class="sxs-lookup"><span data-stu-id="471bd-126">Please monitor the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) site for announcements.</span></span>

> [!NOTE]
> <span data-ttu-id="471bd-127">在移动到"仅 Teams"模式之前，需要替换或更新不支持 Teams 的设备。</span><span class="sxs-lookup"><span data-stu-id="471bd-127">Before you move to Teams Only mode you need to replace or update devices that don't support Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="471bd-128">**请记住**：迁移到 Teams 不仅仅是技术迁移。</span><span class="sxs-lookup"><span data-stu-id="471bd-128">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="471bd-129">成功的升级会评估技术就绪性与最终用户就绪性。</span><span class="sxs-lookup"><span data-stu-id="471bd-129">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="471bd-130">请查看我们的 Skype for Business 到 Teams 升级 [指南](upgrade-framework.md) ，详细了解如何规划到 Teams 的升级。</span><span class="sxs-lookup"><span data-stu-id="471bd-130">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  
