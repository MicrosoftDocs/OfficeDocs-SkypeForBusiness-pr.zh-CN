---
title: 从 Skype for Business 内部部署升级到团队-Microsoft 团队
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 从 Skype for Business 升级到 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bf51019aad5b2deb6239c698623475263241b3f
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940625"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="f53e1-103">面向 IT 管理员的团队升级工具 &mdash;</span><span class="sxs-lookup"><span data-stu-id="f53e1-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="f53e1-104">本文介绍了用于升级到团队的工具。</span><span class="sxs-lookup"><span data-stu-id="f53e1-104">This article describes tools for upgrading to Teams.</span></span> <span data-ttu-id="f53e1-105">本文是针对 IT 管理员介绍升级概念和实现的第三个。</span><span class="sxs-lookup"><span data-stu-id="f53e1-105">This article is the third of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="f53e1-106">概述</span><span class="sxs-lookup"><span data-stu-id="f53e1-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="f53e1-107">升级方法</span><span class="sxs-lookup"><span data-stu-id="f53e1-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- <span data-ttu-id="f53e1-108"> (本文中**用于管理升级的工具**) </span><span class="sxs-lookup"><span data-stu-id="f53e1-108">**Tools for managing your upgrade**   (This article)</span></span>
- [<span data-ttu-id="f53e1-109">具有 Skype for business 内部部署的组织的其他注意事项</span><span class="sxs-lookup"><span data-stu-id="f53e1-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="f53e1-110">实现升级</span><span class="sxs-lookup"><span data-stu-id="f53e1-110">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="f53e1-111"> (PSTN) 注意事项的公共交换电话网络</span><span class="sxs-lookup"><span data-stu-id="f53e1-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="f53e1-112">此外，以下文章介绍了重要的升级概念和共存行为：</span><span class="sxs-lookup"><span data-stu-id="f53e1-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="f53e1-113">团队和 Skype for business 的共存</span><span class="sxs-lookup"><span data-stu-id="f53e1-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="f53e1-114">共存模式-参考</span><span class="sxs-lookup"><span data-stu-id="f53e1-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="f53e1-115">Teams 客户端体验和共存模式的一致性</span><span class="sxs-lookup"><span data-stu-id="f53e1-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="f53e1-116">用于管理升级的工具</span><span class="sxs-lookup"><span data-stu-id="f53e1-116">Tools for managing the upgrade</span></span>

<span data-ttu-id="f53e1-117">无论选择哪种升级方法，都可以使用 [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)（用于控制用户的共存模式）管理到 TeamsOnly 的切换。</span><span class="sxs-lookup"><span data-stu-id="f53e1-117">Whichever upgrade method you choose, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="f53e1-118">有关每种模式的详细信息，请参阅 [共存模式](migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="f53e1-118">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

<span data-ttu-id="f53e1-119">无论是使用 Skype for Business 模式执行选择功能过渡，还是只从默认孤岛配置升级到 TeamsOnly 模式，TeamsUpgradePolicy 是主要工具。</span><span class="sxs-lookup"><span data-stu-id="f53e1-119">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool.</span></span> <span data-ttu-id="f53e1-120">与团队中的任何其他策略一样，你可以将 TeamsUpgradePolicy 直接分配给用户。</span><span class="sxs-lookup"><span data-stu-id="f53e1-120">Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="f53e1-121">您也可以将策略设置为租户范围内的默认设置。</span><span class="sxs-lookup"><span data-stu-id="f53e1-121">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="f53e1-122">对用户的任何分配都优先于租户默认设置。</span><span class="sxs-lookup"><span data-stu-id="f53e1-122">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="f53e1-123">你可以在团队管理控制台和 PowerShell 中管理该策略。</span><span class="sxs-lookup"><span data-stu-id="f53e1-123">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="f53e1-124">你可以将用户的任何模式分配给用户，无论用户是托管在 Skype for Business Online 还是在本地， **除了只能将 TeamsOnly 模式分配给已驻留在 skype for Business online 中的用户**。</span><span class="sxs-lookup"><span data-stu-id="f53e1-124">You can assign any mode of TeamsUpgradePolicy to users whether the user is homed in Skype for Business Online or on-premises, **except that TeamsOnly mode can only be assigned to a user who is already homed in Skype for Business Online**.</span></span> <span data-ttu-id="f53e1-125">这是因为使用 Skype for Business 用户和联盟以及 Microsoft 365 Phone 系统功能的互操作仅在用户托管在 Skype for business Online 中时才可以使用。</span><span class="sxs-lookup"><span data-stu-id="f53e1-125">This is because interop with Skype for Business users and federation as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span>

<span data-ttu-id="f53e1-126">具有 Skype for business 帐户的 Skype for business 帐户的用户 [必须在线 (移动](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 到 skype For business online 或直接与团队) 使用 Skype for business 内部部署工具单中的 "移动 move-csuser"。</span><span class="sxs-lookup"><span data-stu-id="f53e1-126">Users with Skype for Business accounts homed on-premises [must be moved online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (either to Skype for Business Online or direct to Teams) using Move-CsUser in the Skype for Business on-premises toolset.</span></span> <span data-ttu-id="f53e1-127">这些用户可以通过1个或2个步骤移到 TeamsOnly：</span><span class="sxs-lookup"><span data-stu-id="f53e1-127">These users can be moved to TeamsOnly in either 1 or 2 steps:</span></span>

-   <span data-ttu-id="f53e1-128">1步：在 Move-csuser 中指定-MoveToTeams 开关。</span><span class="sxs-lookup"><span data-stu-id="f53e1-128">1 step:  Specify the -MoveToTeams switch in Move-CsUser.</span></span> <span data-ttu-id="f53e1-129">这需要具有 CU8 或更高版本的 Skype for business Server 2019 或 Skype for business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="f53e1-129">This requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span>

-   <span data-ttu-id="f53e1-130">2个步骤：运行移动 Move-csuser 后，使用 TeamsUpgradePolicy 向用户授予 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="f53e1-130">2 steps: After running Move-CsUser, grant TeamsOnly mode to the user using TeamsUpgradePolicy.</span></span>

<span data-ttu-id="f53e1-131">与其他策略不同，不能在 Microsoft 365 或 Office 365 中创建新的 TeamsUpgradePolicy 实例。</span><span class="sxs-lookup"><span data-stu-id="f53e1-131">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="f53e1-132">所有现有实例都内置在该服务中。</span><span class="sxs-lookup"><span data-stu-id="f53e1-132">All the existing instances are built into the service.</span></span>  <span data-ttu-id="f53e1-133"> (注意，mode 是 TeamsUpgradePolicy 内的一个属性，而不是策略实例的名称。 ) 在某些-但不是所有情况下，策略实例的名称与模式相同。</span><span class="sxs-lookup"><span data-stu-id="f53e1-133">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="f53e1-134">特别是，若要为用户分配 TeamsOnly 模式，请将 TeamsUpgradePolicy 的 "UpgradeToTeams" 实例授予该用户。</span><span class="sxs-lookup"><span data-stu-id="f53e1-134">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="f53e1-135">若要查看所有实例的列表，可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f53e1-135">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="f53e1-136">若要将联机用户升级到 TeamsOnly 模式，请分配 "UpgradeToTeams" 实例：</span><span class="sxs-lookup"><span data-stu-id="f53e1-136">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="f53e1-137">若要将内部部署的 Skype for business 用户升级到 TeamsOnly 模式，请在本地工具集中使用移动 Move-csuser：</span><span class="sxs-lookup"><span data-stu-id="f53e1-137">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

<span data-ttu-id="f53e1-138">若要为租户中的所有用户更改模式，但具有明确的每用户授权 (的模式优先) ，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f53e1-138">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="f53e1-139">如果你拥有本地 Skype for Business 帐户的任何用户，则不能在租户级别分配 TeamsOnly 模式，除非你将其他模式显式分配给具有本地 Skype for Business 帐户的所有用户。</span><span class="sxs-lookup"><span data-stu-id="f53e1-139">If you have any users with Skype for Business accounts on-premises, you must not assign TeamsOnly mode at the tenant level, unless you explicitly assign some other mode to all users with on-premises Skype for Business accounts.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="f53e1-140">在 Skype for Business 客户端中使用通知</span><span class="sxs-lookup"><span data-stu-id="f53e1-140">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="f53e1-141">管理员可以选择在 Skype for Business 客户端中提供最终用户通知，以通知用户即将升级到团队，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="f53e1-141">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="f53e1-142">例如，管理员计划将一组用户升级到 TeamsOnly 模式之前的一周，管理员可能希望为该组用户启用这些通知。</span><span class="sxs-lookup"><span data-stu-id="f53e1-142">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="f53e1-143">使用 NotifySfbUsers = true 的 TeamsUpgradePolicy 实例启用这些通知。</span><span class="sxs-lookup"><span data-stu-id="f53e1-143">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="f53e1-144">对于除 TeamsOnly 之外的所有模式，实际上每个模式有两个实例，它们对应于 NotifySfbUsers 的两个值。</span><span class="sxs-lookup"><span data-stu-id="f53e1-144">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="f53e1-145">对于除 TeamsOnly 之外的所有模式，实际上每个模式有两个实例，它们对应于 NotifySfbUsers 的两个值。</span><span class="sxs-lookup"><span data-stu-id="f53e1-145">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![显示通知的图表](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="f53e1-147">如果你的用户托管在 Skype for Business Online 中，只需分配与用户具有相同模式的策略实例，但 NotifySfbUsers = true。</span><span class="sxs-lookup"><span data-stu-id="f53e1-147">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="f53e1-148">如果你的用户托管在本地 Skype for business 服务器中，你需要使用本地工具集，你需要使用 skype for business server 2019 或 CU8 for Skype for business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="f53e1-148">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="f53e1-149">对于驻留在本地 Skype for business 服务器中的用户，将接受 TeamsUpgradePolicy 的 online 实例的 mode 属性，但 NotifySfbUsers 属性不是。</span><span class="sxs-lookup"><span data-stu-id="f53e1-149">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="f53e1-150">如果需要通知，必须创建 TeamsUpgradePolicy 的本地实例以控制客户端行为。</span><span class="sxs-lookup"><span data-stu-id="f53e1-150">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="f53e1-151">在本地 PowerShell 窗口中，使用 NotifySfbUsers = true 创建 TeamsUpgradePolicy 的新实例：</span><span class="sxs-lookup"><span data-stu-id="f53e1-151">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="f53e1-152">然后，使用相同的本地 PowerShell 窗口，将该新策略分配给所需的用户：</span><span class="sxs-lookup"><span data-stu-id="f53e1-152">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="f53e1-153">会议迁移</span><span class="sxs-lookup"><span data-stu-id="f53e1-153">Meeting migration</span></span>

<span data-ttu-id="f53e1-154">当用户迁移到 TeamsOnly 模式时，默认情况下，他们组织的现有 Skype for Business 会议将被转换为团队。</span><span class="sxs-lookup"><span data-stu-id="f53e1-154">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="f53e1-155">你可以选择禁用向用户分配 TeamsOnly 模式时的默认行为。</span><span class="sxs-lookup"><span data-stu-id="f53e1-155">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="f53e1-156">从本地移动用户时，必须将会议迁移到云才能使用联机用户帐户运行，但如果未指定-MoveToTeams，则会议将作为 Skype for Business 会议进行迁移，而不是转换为团队。</span><span class="sxs-lookup"><span data-stu-id="f53e1-156">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="f53e1-157">在租户级别分配 TeamsOnly 模式时，不会为任何用户触发会议迁移。</span><span class="sxs-lookup"><span data-stu-id="f53e1-157">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="f53e1-158">如果你想要在租户级别分配 TeamsOnly 模式和迁移会议，则可以使用 PowerShell 获取租户中的用户列表 (例如，将 CsOnlineUser 与) 需要的任何筛选器一起使用，然后遍历这些用户中的每个用户以使用启动-CsExMeetingMigration 触发会议迁移。</span><span class="sxs-lookup"><span data-stu-id="f53e1-158">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="f53e1-159">有关详细信息，请参阅 [使用会议迁移服务 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。</span><span class="sxs-lookup"><span data-stu-id="f53e1-159">For details, see [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="f53e1-160">相关链接</span><span class="sxs-lookup"><span data-stu-id="f53e1-160">Related links</span></span>

[<span data-ttu-id="f53e1-161">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="f53e1-161">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="f53e1-162">配置 Skype for Business 服务器与 Microsoft 365 或 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="f53e1-162">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="f53e1-163">在本地和云之间移动用户</span><span class="sxs-lookup"><span data-stu-id="f53e1-163">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="f53e1-164">设置共存和升级设置</span><span class="sxs-lookup"><span data-stu-id="f53e1-164">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="f53e1-165">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="f53e1-165">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="f53e1-166">使用会议迁移服务 (MMS) </span><span class="sxs-lookup"><span data-stu-id="f53e1-166">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

