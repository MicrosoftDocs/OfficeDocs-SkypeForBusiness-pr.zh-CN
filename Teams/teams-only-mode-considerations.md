---
title: 仅 Teams 模式注意事项
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dearbeen
description: 准备升级到 "仅 Microsoft 团队" 模式
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 806a96db63ca0bbb44eb92ed6e84f8451069e725
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035456"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="f4a83-103">仅 Teams 模式注意事项</span><span class="sxs-lookup"><span data-stu-id="f4a83-103">Teams Only mode considerations</span></span>

<span data-ttu-id="f4a83-104">如果你是 Office 365 租户上的管理员，则你现在将在 Microsoft 团队管理中心中看到 "升级到仅团队" 模式的选项。</span><span class="sxs-lookup"><span data-stu-id="f4a83-104">If you are an administrator on your Office 365 tenant, you will now see the option to upgrade to Teams Only mode in the Microsoft Teams admin center.</span></span> <span data-ttu-id="f4a83-105">利用此功能，你可以升级单个用户，或者升级整个租户。</span><span class="sxs-lookup"><span data-stu-id="f4a83-105">With this functionality you can upgrade either individual users, or alternatively, the entire tenant.</span></span>  

<span data-ttu-id="f4a83-106">升级到 "仅团队" 模式可为用户提供 Microsoft 团队的全部好处，即 Office 365 中团队协作的全部好处，通过单个客户端体验。</span><span class="sxs-lookup"><span data-stu-id="f4a83-106">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Office 365, via a single client experience.</span></span> <span data-ttu-id="f4a83-107">此外，"仅工作组" 模式中的用户将收到团队中的所有通话和聊天，无论发件人是使用 Skype for Business 还是团队，都可以通过互操作和联合支持获得好处。</span><span class="sxs-lookup"><span data-stu-id="f4a83-107">Additionally, users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="f4a83-108">虽然数以千计的客户成功升级到 Microsoft 团队，但仍有可能会影响组织的升级时间线和用户体验。</span><span class="sxs-lookup"><span data-stu-id="f4a83-108">While thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization’s upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="f4a83-109">特别是，选择升级选项并不一定意味着你的组织已准备好进行此更改。</span><span class="sxs-lookup"><span data-stu-id="f4a83-109">In particular, having the option to upgrade doesn’t necessarily mean your organization is ready for this change.</span></span> <span data-ttu-id="f4a83-110">为了实现最佳用户体验，请先确认 Teams 满足你的协作和通信要求，确保你的网络可以支持 Teams，以及实施你的用户就绪计划，然后再将用户升级到 Teams。</span><span class="sxs-lookup"><span data-stu-id="f4a83-110">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="f4a83-111">如果您刚刚开始升级规划，请务必查看我们的完整升级指南和规划资源。</span><span class="sxs-lookup"><span data-stu-id="f4a83-111">If you are just starting your upgrade planning, be sure to review our full upgrade guidance and planning resources.</span></span> <span data-ttu-id="f4a83-112">[从这里开始](upgrade-start-here.md)。</span><span class="sxs-lookup"><span data-stu-id="f4a83-112">[Start here](upgrade-start-here.md).</span></span> 

<span data-ttu-id="f4a83-113">**共存注意事项**：已使用 Skype For business Online 和/或 Skype For business 服务器的组织可以按满足其需求的节奏将团队引入到其环境中。</span><span class="sxs-lookup"><span data-stu-id="f4a83-113">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="f4a83-114">组织可以根据需要以增量方式向所需的一组用户推出团队，并且使用团队的用户可以与使用 Skype for Business 的用户进行通信，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="f4a83-114">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="f4a83-115">为管理此体验，管理员使用共存模式，这些模式定义了最终用户客户体验、传入聊天和通话的传送行为，以及团队或 Skype for business 中是否安排新会议。</span><span class="sxs-lookup"><span data-stu-id="f4a83-115">To manage this experience, administrators use coexistence modes, which define the end user client experience, the routing behavior of incoming chats and calls, as well as whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="f4a83-116">如果用户仅升级到**团队**，则用户可以与其他组织中的用户联盟;但是，当两个用户都使用团队时，将提供最佳体验。</span><span class="sxs-lookup"><span data-stu-id="f4a83-116">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="f4a83-117">已升级到团队的用户仍可加入 Skype for Business 会议。</span><span class="sxs-lookup"><span data-stu-id="f4a83-117">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!NOTE]
> <span data-ttu-id="f4a83-118">升级到团队的用户仅无法与使用 Skype for 消费者的用户通信。</span><span class="sxs-lookup"><span data-stu-id="f4a83-118">Users who are upgraded to Teams Only cannot communicate with users who are using Skype for Consumer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4a83-119">有关共存的更多详细信息，请参阅[了解 Microsoft 团队和 Skype for business 共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="f4a83-119">For more detailed information about coexistence please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> 

<span data-ttu-id="f4a83-120">**租户范围内的注意事项**：我们正在致力于在以下环境中启用团队;但是，现在，如果其 Skype for Business 租户托管在以下环境之一中，则管理员不应升级其组织中的任何用户：</span><span class="sxs-lookup"><span data-stu-id="f4a83-120">**Tenant-wide considerations**: We are working on enabling Teams in the following environments; however, for now, administrators shouldn't upgrade any users in their organization if their Skype for Business tenant is hosted in one of the following environments:</span></span>

 - <span data-ttu-id="f4a83-121">政府社区云高</span><span class="sxs-lookup"><span data-stu-id="f4a83-121">Government Community Cloud High</span></span>
 - <span data-ttu-id="f4a83-122">政府社区云 DoD</span><span class="sxs-lookup"><span data-stu-id="f4a83-122">Government Community Cloud DoD</span></span>
 - <span data-ttu-id="f4a83-123">由世纪互联运营的 Office 365</span><span class="sxs-lookup"><span data-stu-id="f4a83-123">Office 365 operated by 21Vianet</span></span>
 - <span data-ttu-id="f4a83-124">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="f4a83-124">Office 365 Germany</span></span>
 - <span data-ttu-id="f4a83-125">Skype for business 租户托管于韩国 **，** 组织要求团队数据存储在韩国。</span><span class="sxs-lookup"><span data-stu-id="f4a83-125">Skype for Business tenant is hosted in South Korea **and** the organization requires Teams data to be stored in South Korea.</span></span> <span data-ttu-id="f4a83-126">目前，存储在韩国的 Skype for business 数据的组织将其团队数据存储在亚洲数据中心区域，而不是在韩国数据中心区域中。</span><span class="sxs-lookup"><span data-stu-id="f4a83-126">Currently, organizations with Skype for Business data stored in South Korea that upgrade to Teams will have their Teams data stored in the Asia datacenter region, not in the South Korea datacenter region.</span></span>

<span data-ttu-id="f4a83-127">**特定于用户的注意事项**：某些用户方案仍在发展，管理员可能决定在升级组织中的其他用户时临时推迟某些用户的升级。</span><span class="sxs-lookup"><span data-stu-id="f4a83-127">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="f4a83-128">特别是，我们仍在针对其主要设备基于 VDI 的用户处理方案。</span><span class="sxs-lookup"><span data-stu-id="f4a83-128">In particular, we are still working on addressing scenarios for users whose primary device is VDI-based.</span></span> <span data-ttu-id="f4a83-129">请监控[Office 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)网站，了解公告。</span><span class="sxs-lookup"><span data-stu-id="f4a83-129">Please monitor the [Office 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) site for announcements.</span></span>

> [!NOTE]
> <span data-ttu-id="f4a83-130">在移动到 "仅团队" 模式之前，你需要替换或更新不支持团队的设备。</span><span class="sxs-lookup"><span data-stu-id="f4a83-130">Before you move to Teams Only mode you need to replace or update devices that don’t support Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="f4a83-131">**请记住**：迁移到团队不仅仅是技术迁移。</span><span class="sxs-lookup"><span data-stu-id="f4a83-131">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="f4a83-132">成功的升级会评估技术准备和最终用户准备情况。</span><span class="sxs-lookup"><span data-stu-id="f4a83-132">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="f4a83-133">查看我们的 Skype for Business 到团队[升级指南](upgrade-framework.md)，了解有关规划实施团队升级的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f4a83-133">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  
