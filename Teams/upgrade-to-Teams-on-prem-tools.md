---
title: 用于从 Skype for Business 本地部署升级到 Teams 的工具
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 从 Skype for Business 升级到 Teams 的工具
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61dc34d56ebb10dc7319d855bbd0d98184f1e54a
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347843"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="511c8-103">用于升级为 IT 管理员的 Teams &mdash; 的工具</span><span class="sxs-lookup"><span data-stu-id="511c8-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="511c8-104">本文介绍用于升级到 Teams 的工具。</span><span class="sxs-lookup"><span data-stu-id="511c8-104">This article describes tools for upgrading to Teams.</span></span> <span data-ttu-id="511c8-105">本文是介绍 IT 管理员升级概念和实现的几个文章的第三篇。</span><span class="sxs-lookup"><span data-stu-id="511c8-105">This article is the third of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="511c8-106">概述</span><span class="sxs-lookup"><span data-stu-id="511c8-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="511c8-107">升级方法</span><span class="sxs-lookup"><span data-stu-id="511c8-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- <span data-ttu-id="511c8-108">**本文介绍用于管理升级 (**   工具) </span><span class="sxs-lookup"><span data-stu-id="511c8-108">**Tools for managing your upgrade**   (This article)</span></span>
- [<span data-ttu-id="511c8-109">使用本地 Skype for Business 的组织的其他注意事项</span><span class="sxs-lookup"><span data-stu-id="511c8-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="511c8-110">实现升级</span><span class="sxs-lookup"><span data-stu-id="511c8-110">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="511c8-111">公共电话交换网 (PSTN) 注意事项</span><span class="sxs-lookup"><span data-stu-id="511c8-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="511c8-112">此外，以下文章介绍重要的升级概念和共存行为：</span><span class="sxs-lookup"><span data-stu-id="511c8-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="511c8-113">Teams 和 Skype for Business 共存</span><span class="sxs-lookup"><span data-stu-id="511c8-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="511c8-114">共存模式 - 参考</span><span class="sxs-lookup"><span data-stu-id="511c8-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="511c8-115">Teams 客户端体验和共存模式的一致性</span><span class="sxs-lookup"><span data-stu-id="511c8-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="511c8-116">用于管理升级的工具</span><span class="sxs-lookup"><span data-stu-id="511c8-116">Tools for managing the upgrade</span></span>

<span data-ttu-id="511c8-117">无论选择哪种升级方法，对于已拥有 Skype for Business Online 的用户，你使用 [TeamsUpgradePolicy（](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)控制用户的共存模式）管理到 TeamsOnly 的转换。</span><span class="sxs-lookup"><span data-stu-id="511c8-117">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="511c8-118">对于在 Skype for Business Server 中拥有本地帐户的用户，还可将其 `Move-CsUser` [移动到云中](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)。</span><span class="sxs-lookup"><span data-stu-id="511c8-118">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="511c8-119">有关每个模式详细信息，请参阅 [共存模式](migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="511c8-119">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

> [!NOTE]
> <span data-ttu-id="511c8-120">如果你当前正在使用 Skype for Business Online 连接器管理服务，则需要移动到 Teams PowerShell 模块并更新现有的 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="511c8-120">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="511c8-121">有关详细信息 [，请参阅](teams-powershell-move-from-sfbo.md) "从 Skype for Business Online 连接器移动到 Teams PowerShell 模块"。</span><span class="sxs-lookup"><span data-stu-id="511c8-121">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="511c8-122">无论你是使用 Skype for Business 模式执行选择功能转换，还是只是从默认群岛配置升级到 TeamsOnly 模式，TeamsUpgradePolicy 都是已拥有 Skype for Business Online 的用户的主要工具。</span><span class="sxs-lookup"><span data-stu-id="511c8-122">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool for users who already have Skype for Business Online.</span></span> <span data-ttu-id="511c8-123">与 Teams 中的其他任何策略一样，可以直接将 TeamsUpgradePolicy 分配给用户。</span><span class="sxs-lookup"><span data-stu-id="511c8-123">Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="511c8-124">还可以将策略设置为租户范围默认值。</span><span class="sxs-lookup"><span data-stu-id="511c8-124">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="511c8-125">向用户分配的任何作业优先于租户默认设置。</span><span class="sxs-lookup"><span data-stu-id="511c8-125">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="511c8-126">可以在 Teams 管理控制台和 PowerShell 中管理策略。</span><span class="sxs-lookup"><span data-stu-id="511c8-126">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="511c8-127">还可以将 TeamsUpgradePolicy 的任何模式（TeamsOnly 模式除外）分配给本地 Skype for Business 中的用户。</span><span class="sxs-lookup"><span data-stu-id="511c8-127">You can also assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="511c8-128">**TeamsOnly 模式只能分配给** 已位于 Skype for Business Online 中的用户。</span><span class="sxs-lookup"><span data-stu-id="511c8-128">**TeamsOnly mode can only be assigned to a user who is already homed in Skype for Business Online**.</span></span> <span data-ttu-id="511c8-129">这是因为只有在用户位于 Skype for Business Online 中时，才能与 Skype for Business 用户和联合身份验证以及 Microsoft 365 电话系统功能进行互操作。</span><span class="sxs-lookup"><span data-stu-id="511c8-129">This is because interop with Skype for Business users and federation as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span> <span data-ttu-id="511c8-130">此外，如果你有本地 Skype for Business 部署 (则不能将 **TeamsOnly** 模式分配为租户范围默认值 (该部署通过指向 Office 365 之外位置的 lyncdiscover DNS 记录检测到。</span><span class="sxs-lookup"><span data-stu-id="511c8-130">In addition, **you cannot assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span>

<span data-ttu-id="511c8-131">具有本地版 Skype for Business 帐户[](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)的用户必须联机 (移动到 Skype for Business Online 或直接移动到 Teams) ，使用 Skype for Business 本地工具集中的 Move-CsUser。</span><span class="sxs-lookup"><span data-stu-id="511c8-131">Users with Skype for Business accounts homed on-premises [must be moved online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (either to Skype for Business Online or direct to Teams) using Move-CsUser in the Skype for Business on-premises toolset.</span></span> <span data-ttu-id="511c8-132">这些用户可以通过 1 或 2 个步骤移动到 TeamsOnly：</span><span class="sxs-lookup"><span data-stu-id="511c8-132">These users can be moved to TeamsOnly in either 1 or 2 steps:</span></span>

-   <span data-ttu-id="511c8-133">1 步：在 Move-CsUser 中指定 -MoveToTeams 开关。</span><span class="sxs-lookup"><span data-stu-id="511c8-133">1 step:  Specify the -MoveToTeams switch in Move-CsUser.</span></span> <span data-ttu-id="511c8-134">这需要具有 CU8 或更高版本的 Skype for Business Server 2019 或 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="511c8-134">This requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span>

-   <span data-ttu-id="511c8-135">2 个步骤：运行 Move-CsUser 后，使用 TeamsUpgradePolicy 向用户授予 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="511c8-135">2 steps: After running Move-CsUser, grant TeamsOnly mode to the user using TeamsUpgradePolicy.</span></span>

<span data-ttu-id="511c8-136">与其他策略不同，在 Microsoft 365 或 Office 365 中无法创建新的 TeamsUpgradePolicy 实例。</span><span class="sxs-lookup"><span data-stu-id="511c8-136">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="511c8-137">所有现有实例都内置于服务中。</span><span class="sxs-lookup"><span data-stu-id="511c8-137">All the existing instances are built into the service.</span></span>  <span data-ttu-id="511c8-138"> (请注意，模式是 TeamsUpgradePolicy 中的一个属性，而不是策略实例的名称。) 在某些（但并非所有）情况下，策略实例的名称与模式相同。</span><span class="sxs-lookup"><span data-stu-id="511c8-138">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="511c8-139">具体而言，若要将 TeamsOnly 模式分配给用户，需要向该用户授予 TeamsUpgradePolicy 的"UpgradeToTeams"实例。</span><span class="sxs-lookup"><span data-stu-id="511c8-139">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="511c8-140">若要查看所有实例的列表，可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="511c8-140">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="511c8-141">若要将联机用户升级到 TeamsOnly 模式，请分配"UpgradeToTeams"实例：</span><span class="sxs-lookup"><span data-stu-id="511c8-141">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="511c8-142">若要将本地 Skype for Business 用户升级到 TeamsOnly 模式，Move-CsUser工具集：</span><span class="sxs-lookup"><span data-stu-id="511c8-142">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

<span data-ttu-id="511c8-143">若要更改租户中所有用户的模式（具有按用户显式授予权限的用户除外 (优先) ，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="511c8-143">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="511c8-144">如果有任何用户在本地拥有 Skype for Business 帐户，则不能在租户级别分配 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="511c8-144">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="511c8-145">必须使用 Move-CsUser 将这些用户分别移动到云中。</span><span class="sxs-lookup"><span data-stu-id="511c8-145">You must move these users individually to the cloud using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="511c8-146">在 Skype for Business 客户端中使用通知</span><span class="sxs-lookup"><span data-stu-id="511c8-146">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="511c8-147">管理员可以选择在 Skype for Business 客户端中提供最终用户通知，以通知用户他们即将升级到 Teams，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="511c8-147">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="511c8-148">例如，在管理员计划将一组用户升级到 TeamsOnly 模式之前一周，管理员可能需要为该组用户启用这些通知。</span><span class="sxs-lookup"><span data-stu-id="511c8-148">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="511c8-149">这些通知是使用具有 NotifySfbUsers=true 的 TeamsUpgradePolicy 实例启用的。</span><span class="sxs-lookup"><span data-stu-id="511c8-149">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="511c8-150">对于 TeamsOnly 外的所有模式，每个模式实际上都有两个实例，对应于 NotifySfbUsers 的两个值。</span><span class="sxs-lookup"><span data-stu-id="511c8-150">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="511c8-151">对于 TeamsOnly 外的所有模式，每个模式实际上都有两个实例，对应于 NotifySfbUsers 的两个值。</span><span class="sxs-lookup"><span data-stu-id="511c8-151">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![显示通知的图表](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="511c8-153">如果你的用户在 Skype for Business Online 中，只需分配与用户模式相同的策略实例，但使用 NotifySfbUsers=true。</span><span class="sxs-lookup"><span data-stu-id="511c8-153">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="511c8-154">如果你的用户在本地的 Skype for Business Server 中，你需要使用本地工具集，并且你需要 Skype for Business Server 2019 或 CU8 for Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="511c8-154">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="511c8-155">对于本地 Skype for Business Server 中的用户，将遵守 TeamsUpgradePolicy 联机实例中的 mode 属性，但不使用 NotifySfbUsers 属性。</span><span class="sxs-lookup"><span data-stu-id="511c8-155">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="511c8-156">如果需要通知，则必须创建 TeamsUpgradePolicy 本地实例来控制客户端行为。</span><span class="sxs-lookup"><span data-stu-id="511c8-156">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="511c8-157">在本地 PowerShell 窗口中，使用 NotifySfbUsers=true 创建 TeamsUpgradePolicy 的新实例：</span><span class="sxs-lookup"><span data-stu-id="511c8-157">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="511c8-158">然后，使用相同的本地 PowerShell 窗口，将新策略分配给所需的用户：</span><span class="sxs-lookup"><span data-stu-id="511c8-158">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="511c8-159">会议迁移</span><span class="sxs-lookup"><span data-stu-id="511c8-159">Meeting migration</span></span>

<span data-ttu-id="511c8-160">当用户迁移到 TeamsOnly 模式时，默认情况下，他们组织的现有 Skype for Business 会议将转换为 Teams。</span><span class="sxs-lookup"><span data-stu-id="511c8-160">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="511c8-161">可以选择在将 TeamsOnly 模式分配给用户时禁用默认行为。</span><span class="sxs-lookup"><span data-stu-id="511c8-161">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="511c8-162">将用户从本地移动时，会议必须迁移到云中，以便使用联机用户帐户运行，但如果不指定 -MoveToTeams，会议将迁移为 Skype for Business 会议，而不是转换为 Teams。</span><span class="sxs-lookup"><span data-stu-id="511c8-162">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="511c8-163">在租户级别分配 TeamsOnly 模式时，不会为任何用户触发会议迁移。</span><span class="sxs-lookup"><span data-stu-id="511c8-163">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="511c8-164">如果要在租户级别分配 TeamsOnly 模式并迁移会议，可以使用 PowerShell 获取租户 (中的用户列表，例如，将 Get-CsOnlineUser 与所需的筛选器一起使用) 然后循环访问其中每个用户，以使用 Start-CsExMeetingMigration 触发会议迁移。</span><span class="sxs-lookup"><span data-stu-id="511c8-164">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="511c8-165">有关详细信息，请参阅["使用会议迁移服务 (MMS) 。 ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="511c8-165">For details, see [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="511c8-166">相关链接</span><span class="sxs-lookup"><span data-stu-id="511c8-166">Related links</span></span>

[<span data-ttu-id="511c8-167">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="511c8-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="511c8-168">在 Skype for Business Server 与 Microsoft 365 或 Office 365 之间配置混合连接</span><span class="sxs-lookup"><span data-stu-id="511c8-168">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="511c8-169">在本地和云之间移动用户</span><span class="sxs-lookup"><span data-stu-id="511c8-169">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="511c8-170">设置共存和升级设置</span><span class="sxs-lookup"><span data-stu-id="511c8-170">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="511c8-171">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="511c8-171">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="511c8-172">使用会议迁移服务 (MMS) </span><span class="sxs-lookup"><span data-stu-id="511c8-172">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

