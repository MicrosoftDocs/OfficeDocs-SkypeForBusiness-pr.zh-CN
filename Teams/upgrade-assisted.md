---
title: 辅助升级|Skype Business Online 到 Teams 升级
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: 从 Skype for Business Online 到 Teams 的辅助升级概述
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
ms.openlocfilehash: 03ea21de9f8cb64b1221044babeeae335a52d8ea
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995191"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="95d71-103">从 Skype for Business Online 到 Microsoft Teams 的辅助升级</span><span class="sxs-lookup"><span data-stu-id="95d71-103">Assisted upgrades from Skype for Business Online to Microsoft Teams</span></span>

<span data-ttu-id="95d71-104">Microsoft 为 Teams 提供辅助升级，以帮助组织在 2021 年 7 月 31 日服务停用时从 Skype for Business Online 成功过渡。</span><span class="sxs-lookup"><span data-stu-id="95d71-104">Microsoft offers assisted upgrades to Teams to help organizations make a successful transition from Skype for Business Online as the service retires July 31, 2021.</span></span> <span data-ttu-id="95d71-105">辅助升级可以减少需要执行的技术任务数，并可以更专注于组织准备、用户意识和 Teams 培训。</span><span class="sxs-lookup"><span data-stu-id="95d71-105">Assisted upgrades reduce the number of technical tasks you need to do and allow for greater focus on organizational preparedness, user awareness, and Teams training.</span></span>

<span data-ttu-id="95d71-106">建议在升级之前 [查看升级](https://aka.ms/SkypeToTeams) 指南。</span><span class="sxs-lookup"><span data-stu-id="95d71-106">We recommend that you review our [upgrade guidance](https://aka.ms/SkypeToTeams) before your upgrade.</span></span> <span data-ttu-id="95d71-107">我们的升级指南包括建议的活动和有用的资源，用于完成从 Skype for Business Online 升级到 Teams。</span><span class="sxs-lookup"><span data-stu-id="95d71-107">Our upgrade guidance includes recommended activities and helpful resources for completing an upgrade from Skype for Business Online to Teams.</span></span> <span data-ttu-id="95d71-108">本指南适用于计划升级到 Teams 的任何组织，无论是管理升级的所有方面，还是使用辅助过程。</span><span class="sxs-lookup"><span data-stu-id="95d71-108">This guidance applies to any organization planning an upgrade to Teams, whether they manage all aspects of the upgrade or use the assisted process.</span></span>

> [!NOTE]
> <span data-ttu-id="95d71-109">如果计划进行 Teams 辅助升级，可以在计划的升级日期之前从 Skype for Business Online 执行自己的升级。</span><span class="sxs-lookup"><span data-stu-id="95d71-109">If you're scheduled for an assisted upgrade to Teams, you can perform your own upgrade from Skype for Business Online before your scheduled upgrade date.</span></span> <span data-ttu-id="95d71-110">有关如何手动升级到 Teams 的信息，请参阅我们的升级 [指南](https://aka.ms/SkypeToTeams)。</span><span class="sxs-lookup"><span data-stu-id="95d71-110">For more information about how to manually upgrade to Teams, see our [upgrade guidance](https://aka.ms/SkypeToTeams).</span></span>
>
> <span data-ttu-id="95d71-111">辅助升级不适用于 Skype for Business Server 本地部署。</span><span class="sxs-lookup"><span data-stu-id="95d71-111">Assisted upgrade is not available for on-premises deployments of Skype for Business Server.</span></span>

## <a name="notifications-for-scheduled-customers"></a><span data-ttu-id="95d71-112">计划客户的通知</span><span class="sxs-lookup"><span data-stu-id="95d71-112">Notifications for scheduled customers</span></span>

<span data-ttu-id="95d71-113">计划向 Teams 进行辅助升级的 Skype for Business Online 客户将收到一系列升级通知。</span><span class="sxs-lookup"><span data-stu-id="95d71-113">Skype for Business Online customers that are scheduled for assisted upgrades to Teams will receive a series of upgrade notifications.</span></span> <span data-ttu-id="95d71-114">这些通知将在计划的升级日期前 90 天开始。</span><span class="sxs-lookup"><span data-stu-id="95d71-114">These notifications will begin 90 days before the scheduled upgrade date.</span></span> <span data-ttu-id="95d71-115">这些通知将作为 Microsoft  365 消息中心中的"更改计划"帖子、Teams 管理中心中的升级仪表板通知以及向最终用户提供的应用内标志传递。</span><span class="sxs-lookup"><span data-stu-id="95d71-115">These notifications will be delivered as *Plan for Change* posts in the Microsoft 365 Message Center, upgrade dashboard notifications in Teams admin center, and in-app flags to end users.</span></span>

<span data-ttu-id="95d71-116">升级通知将包括辅助升级的计划日期，并链接到升级资源和培训，以帮助推动 Teams 的采用和使用。</span><span class="sxs-lookup"><span data-stu-id="95d71-116">Upgrade notifications will include the scheduled date of the assisted upgrade, and will link to upgrade resources and training to help drive adoption and usage of Teams.</span></span>

## <a name="the-assisted-upgrade-experience"></a><span data-ttu-id="95d71-117">辅助升级体验</span><span class="sxs-lookup"><span data-stu-id="95d71-117">The assisted upgrade experience</span></span>

<span data-ttu-id="95d71-118">辅助升级将从 2021 年 8 月开始，在上述计划通知中共享特定于租户的日期。</span><span class="sxs-lookup"><span data-stu-id="95d71-118">Assisted upgrades will begin in August 2021 with tenant-specific dates shared in the scheduling notifications mentioned above.</span></span>

<span data-ttu-id="95d71-119">升级持续时间因用户数量和部署特征而异。</span><span class="sxs-lookup"><span data-stu-id="95d71-119">The duration of the upgrade will vary by volume of users and the characteristics of the deployment.</span></span> <span data-ttu-id="95d71-120">但是，在大多数情况下，租户中的用户将在升级开始后的 24 小时内升级。</span><span class="sxs-lookup"><span data-stu-id="95d71-120">However, in most cases, users within a tenant will be upgraded within 24 hours of the start of the upgrade.</span></span> <span data-ttu-id="95d71-121">在此期间，最终用户仍可访问 Skype for Business Online 功能。</span><span class="sxs-lookup"><span data-stu-id="95d71-121">During this time, end users will still have access to Skype for Business Online functionality.</span></span> <span data-ttu-id="95d71-122">完成升级并且用户注销 Skype for Business Online 后，他们将开始使用 Teams 进行消息传递、会议和通话。</span><span class="sxs-lookup"><span data-stu-id="95d71-122">Once the upgrade has completed and users sign out of Skype for Business Online, they'll start using Teams for messaging, meetings, and calling.</span></span>

## <a name="the-post-upgrade-experience"></a><span data-ttu-id="95d71-123">升级后体验</span><span class="sxs-lookup"><span data-stu-id="95d71-123">The post-upgrade experience</span></span>

<span data-ttu-id="95d71-124">辅助升级完成后，已升级用户的共存模式将设置为"仅 Teams"，并且 Microsoft 只能更改为其他共存模式。</span><span class="sxs-lookup"><span data-stu-id="95d71-124">When the assisted upgrade completes, the **Coexistence Mode** for upgraded users is set to Teams Only and can only be changed to a different coexistence mode by Microsoft.</span></span> <span data-ttu-id="95d71-125">建议在升级之前查看 ["仅 Teams](teams-only-mode-considerations.md) 模式注意事项"。</span><span class="sxs-lookup"><span data-stu-id="95d71-125">We recommend that you review [Teams Only mode considerations](teams-only-mode-considerations.md) before your upgrade.</span></span> <span data-ttu-id="95d71-126">下表提供了仅 Teams 用户体验的概要概述。</span><span class="sxs-lookup"><span data-stu-id="95d71-126">The table below provides a high-level overview of the Teams Only user experience.</span></span>

:::row:::
    :::column span="1":::
        <span data-ttu-id="95d71-127">**聊天和通话**</span><span class="sxs-lookup"><span data-stu-id="95d71-127">**Chat and Calling**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="95d71-128">所有通话和聊天在 Teams 中启动和接收</span><span class="sxs-lookup"><span data-stu-id="95d71-128">All calls and chats are started and received in Teams</span></span>
        - <span data-ttu-id="95d71-129">用户可以与 (Skype for Business 用户) 聊天/通话</span><span class="sxs-lookup"><span data-stu-id="95d71-129">Users can communicate (chat/call) with any Skype for Business user</span></span>
        - <span data-ttu-id="95d71-130">组织可以通过管理外部访问权限，使 Teams 用户能够与 Skype 消费者服务 [的用户通信](manage-external-access.md)</span><span class="sxs-lookup"><span data-stu-id="95d71-130">Organizations can enable Teams users to communicate with users of the Skype consumer service by managing [external access permissions](manage-external-access.md)</span></span>
        - <span data-ttu-id="95d71-131">尝试登录 Skype for Business Online 的 Teams 用户将被重定向到 Teams</span><span class="sxs-lookup"><span data-stu-id="95d71-131">Teams users who attempt to sign in to Skype for Business Online will be redirected to Teams</span></span>
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        <span data-ttu-id="95d71-132">**会议**</span><span class="sxs-lookup"><span data-stu-id="95d71-132">**Meetings**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="95d71-133">用户在 Teams 中安排所有新会议， (插件) </span><span class="sxs-lookup"><span data-stu-id="95d71-133">Users schedule all new meetings in Teams (plugin replaced)</span></span>
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        <span data-ttu-id="95d71-134">**迁移的数据**</span><span class="sxs-lookup"><span data-stu-id="95d71-134">**Migrated Data**</span></span>
    :::column-end:::
    :::column span="3":::
        - <span data-ttu-id="95d71-135">Skype for Business Online 中的现有联系人，包括 (但无通讯组列表</span><span class="sxs-lookup"><span data-stu-id="95d71-135">Existing contacts from Skype for Business Online including federated (but no distribution lists</span></span>
        - <span data-ttu-id="95d71-136">现有 Skype for Business Online 会议将转换为 Teams 会议</span><span class="sxs-lookup"><span data-stu-id="95d71-136">Existing Skype for Business Online meetings are converted to Teams meetings</span></span>
    :::column-end:::
:::row-end:::

## <a name="related-content"></a><span data-ttu-id="95d71-137">相关内容</span><span class="sxs-lookup"><span data-stu-id="95d71-137">Related content</span></span>

- [<span data-ttu-id="95d71-138">开始 Microsoft Teams 升级</span><span class="sxs-lookup"><span data-stu-id="95d71-138">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="95d71-139">Skype for Business Online 停用</span><span class="sxs-lookup"><span data-stu-id="95d71-139">Skype for Business Online retirement</span></span>](skype-for-business-online-retirement.md)
- [<span data-ttu-id="95d71-140">Get-CsTeamsUpgradeStatus</span><span class="sxs-lookup"><span data-stu-id="95d71-140">Get-CsTeamsUpgradeStatus</span></span>](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [<span data-ttu-id="95d71-141">仅 Teams 模式注意事项</span><span class="sxs-lookup"><span data-stu-id="95d71-141">Teams Only mode considerations</span></span>](teams-only-mode-considerations.md)
