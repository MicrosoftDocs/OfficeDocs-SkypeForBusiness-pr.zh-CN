---
title: 仅 Teams 模式注意事项
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: 准备升级到 Microsoft 团队模式
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords: ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dd0bf20219b8d213c354f5fc239ae3924a0d21c0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226636"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="3cf8d-103">仅 Teams 模式注意事项</span><span class="sxs-lookup"><span data-stu-id="3cf8d-103">Teams Only mode considerations</span></span>

<span data-ttu-id="3cf8d-104">如果您是管理员在 Office 365 租户，现在您会看到升级为仅团队模式的 Microsoft 团队管理中心中的选项。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-104">If you are an administrator on your Office 365 tenant, you will now see the option to upgrade to Teams Only mode in the Microsoft Teams admin center.</span></span> <span data-ttu-id="3cf8d-105">利用此功能可以升级各个用户，或者此外，整个租户。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-105">With this functionality you can upgrade either individual users, or alternatively, the entire tenant.</span></span>  

<span data-ttu-id="3cf8d-106">升级到团队仅模式为用户提供用于在 Office 365 中，通过单个客户端体验的团队协作的中心的 Microsoft 团队的全部好处。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-106">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Office 365, via a single client experience.</span></span> <span data-ttu-id="3cf8d-107">此外，仅在工作组模式中的用户将接收所有呼叫和聊天团队，无论发件人是否适用于商务或团队使用 Skype 然后中受益于互操作和联合身份验证支持。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-107">Additionally, users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="3cf8d-108">虽然成千上万客户已成功升级到 Microsoft 团队，有可能影响一路将您的组织升级时间线和用户体验的注意事项。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-108">While thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization’s upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="3cf8d-109">具体而言，具有升级选项并不一定意味着您的组织已准备好进行此更改。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-109">In particular, having the option to upgrade doesn’t necessarily mean your organization is ready for this change.</span></span> <span data-ttu-id="3cf8d-110">为了实现最佳用户体验，请先确认 Teams 满足你的协作和通信要求，确保你的网络可以支持 Teams，以及实施你的用户就绪计划，然后再将用户升级到 Teams。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-110">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="3cf8d-111">如果您刚开始升级规划，请务必查看我们完全升级指南和规划资源。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-111">If you are just starting your upgrade planning, be sure to review our full upgrade guidance and planning resources.</span></span> <span data-ttu-id="3cf8d-112">[从这里开始](upgrade-introduction.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-112">[Start here](upgrade-introduction.md).</span></span> 

<span data-ttu-id="3cf8d-113">**共存注意事项**： 已使用 Skype 业务 online 和/或 Skype 的业务服务器可以将团队引入满足他们的需求的步调其环境的组织。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-113">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="3cf8d-114">组织可以增量推出团队到一组所需的用户根据需要，使用团队的用户通信与用户使用 Skype for Business，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-114">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="3cf8d-115">若要管理此体验，管理员使用共存模式，定义的最终用户客户端体验，传入的路由行为聊天和呼叫，以及是否将新会议安排在团队或 for Business 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-115">To manage this experience, administrators use coexistence modes, which define the end user client experience, the routing behavior of incoming chats and calls, as well as whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="3cf8d-116">如果用户升级到**团队仅**;，用户可以与其他组织中用户联盟但是，当两个用户使用团队提供最佳体验。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-116">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="3cf8d-117">升级到仅团队的用户仍可以加入 Skype 业务会议。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-117">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!NOTE]
> <span data-ttu-id="3cf8d-118">升级到仅团队的用户无法与使用 Skype 使用者的用户通信。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-118">Users who are upgraded to Teams Only cannot communicate with users who are using Skype for Consumer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3cf8d-119">有关共存的详细信息请参阅[了解 Microsoft 团队和 Skype 的业务共存及互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-119">For more detailed information about coexistence please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> 

<span data-ttu-id="3cf8d-120">**租户范围注意事项**： 我们正在在以下环境; 启用团队但是，现在，管理员不应升级其组织中的任何用户如果业务租户其 Skype 承载于以下环境之一：</span><span class="sxs-lookup"><span data-stu-id="3cf8d-120">**Tenant-wide considerations**: We are working on enabling Teams in the following environments; however, for now, administrators shouldn't upgrade any users in their organization if their Skype for Business tenant is hosted in one of the following environments:</span></span>

 - <span data-ttu-id="3cf8d-121">政府社区云高</span><span class="sxs-lookup"><span data-stu-id="3cf8d-121">Government Community Cloud High</span></span>
 - <span data-ttu-id="3cf8d-122">政府社区云 DoD</span><span class="sxs-lookup"><span data-stu-id="3cf8d-122">Government Community Cloud DoD</span></span>
 - <span data-ttu-id="3cf8d-123">Office 365 由 21Vianet</span><span class="sxs-lookup"><span data-stu-id="3cf8d-123">Office 365 operated by 21Vianet</span></span>
 - <span data-ttu-id="3cf8d-124">Office 365 德国</span><span class="sxs-lookup"><span data-stu-id="3cf8d-124">Office 365 Germany</span></span>
 - <span data-ttu-id="3cf8d-125">Skype 业务租户位于韩国**和**组织需要团队数据存储中韩国。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-125">Skype for Business tenant is hosted in South Korea **and** the organization requires Teams data to be stored in South Korea.</span></span> <span data-ttu-id="3cf8d-126">当前，与 Skype 的业务数据存储在韩国升级到团队的组织将具有的亚洲数据中心区域，不在韩国数据中心区域中存储其团队数据。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-126">Currently, organizations with Skype for Business data stored in South Korea that upgrade to Teams will have their Teams data stored in the Asia datacenter region, not in the South Korea datacenter region.</span></span>

<span data-ttu-id="3cf8d-127">**特定于用户的注意事项**： 一些用户方案仍在发展，以及管理员可以决定暂时将组织中的其他用户升级时推迟升级的特定用户。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-127">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="3cf8d-128">我们正在努力解决这些方案;请监视通知的[Office 365 路线图](https://www.microsoft.com/en-us/microsoft-365/roadmap)网站。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-128">We are working on addressing these scenarios; please monitor the [Office 365 Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap) site for announcements.</span></span>

| <span data-ttu-id="3cf8d-129">应用场景</span><span class="sxs-lookup"><span data-stu-id="3cf8d-129">Scenario</span></span> | <span data-ttu-id="3cf8d-130">注释</span><span class="sxs-lookup"><span data-stu-id="3cf8d-130">Notes</span></span> |
|----------|-------|
|<span data-ttu-id="3cf8d-131">用户的主工作设备已 Mac，并且用户需要请参阅在 Outlook 中的同事 availability。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-131">User’s primary work device is a Mac, and user needs to see colleagues' availability in Outlook.</span></span> | <span data-ttu-id="3cf8d-132">团队中的 outlook 状态尚不完全支持的 Mac 设备。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-132">Outlook presence in Teams is not yet fully supported for Mac devices.</span></span> |
| <span data-ttu-id="3cf8d-133">用户定期举行会议与客户或不同的国际区域中的外部合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-133">User is regularly conducting meetings with customers or external partners in different international regions.</span></span> | <span data-ttu-id="3cf8d-134">其租户位于不同的地理位置的外部与会者看不到 IM 聊天**联合**会议中。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-134">External attendees whose tenant resides in a different geo-location don’t see IM chat while in a **federated** meeting.</span></span> <span data-ttu-id="3cf8d-135">参与者仍可以加入会议作为匿名用户。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-135">Participants can still join the meeting as anonymous users.</span></span> |
| <span data-ttu-id="3cf8d-136">用户执行 Skype 业务广播的会议。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-136">User is conducting Skype for Business Broadcast meetings.</span></span> |  <span data-ttu-id="3cf8d-137">时团队 live 事件 （替换 Skype 广播） 已在公共预览，此用户可能需要总体可用性团队 live 事件之前一直保持 for Business 的 Skype 上。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-137">While Teams live events (replacing Skype Broadcast) is already in public preview, this user may need to stay on Skype for Business until general availability of Teams live events.</span></span>
| <span data-ttu-id="3cf8d-138">用户的主设备是基于 VDI。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-138">User’s primary device is VDI-based.</span></span> | |
|||

> [!IMPORTANT]
> <span data-ttu-id="3cf8d-139">**记住**： 移动到团队大于技术迁移。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-139">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="3cf8d-140">成功升级评估技术的准备情况和最终用户准备情况。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-140">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="3cf8d-141">查看业务我们 Skype 到团队[升级指南](upgrade-framework.md)规划实现升级到团队的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3cf8d-141">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  
