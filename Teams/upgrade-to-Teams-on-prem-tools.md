---
title: 用于从本地Teams升级到 Skype for Business 的工具
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 用于从 Skype for Business 升级到 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 677f642bdb940706079370635a5aa9eec87241fb
ms.sourcegitcommit: e19fdedca6573110d08c7d114e05b84779e36b58
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53437629"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="821fa-103">适用于 IT 管理员的Teams &mdash; 升级工具</span><span class="sxs-lookup"><span data-stu-id="821fa-103">Tools for upgrading to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="821fa-104">本文介绍用于从 Teams 升级到 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="821fa-104">This article describes tools for upgrading to Teams from Skype for Business.</span></span> 

<span data-ttu-id="821fa-105">在开始升级之前，Microsoft 建议以下文章介绍重要的升级概念和共存行为：</span><span class="sxs-lookup"><span data-stu-id="821fa-105">Before beginning your upgrade, Microsoft recommends the following articles that describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="821fa-106">Teams 和 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="821fa-106">Coexistence of Teams and Skype for Business</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="821fa-107">共存模式 - 参考</span><span class="sxs-lookup"><span data-stu-id="821fa-107">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="821fa-108">Teams 客户端体验和共存模式的一致性</span><span class="sxs-lookup"><span data-stu-id="821fa-108">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a><span data-ttu-id="821fa-109">用于管理升级的工具</span><span class="sxs-lookup"><span data-stu-id="821fa-109">Tools for managing the upgrade</span></span>

<span data-ttu-id="821fa-110">无论选择哪种升级方法，对于已经拥有 Skype for Business Online 的用户，可以使用[TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)管理到 TeamsOnly 的转换，TeamsUpgradePolicy 控制用户的共存模式。</span><span class="sxs-lookup"><span data-stu-id="821fa-110">Whichever upgrade method you choose, for users that already have Skype for Business Online, you manage the transition to TeamsOnly using [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), which controls a user’s coexistence mode.</span></span> <span data-ttu-id="821fa-111">对于在本地拥有本地帐户的用户Skype for Business Server，还可使用 `Move-CsUser` 将其[移动到云 。](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)</span><span class="sxs-lookup"><span data-stu-id="821fa-111">For users with an on-premises account in Skype for Business Server, you also use `Move-CsUser` to [move them to the cloud](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud).</span></span>  <span data-ttu-id="821fa-112">有关每个模式详细信息，请参阅 [共存模式](migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="821fa-112">For more information on each of the modes, see [Coexistence modes](migration-interop-guidance-for-teams-with-skype.md).</span></span>

> [!NOTE]
> <span data-ttu-id="821fa-113">如果当前使用 Skype for Business Online 连接器来管理服务，则需要移动到 powerShell Teams并更新现有的 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="821fa-113">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="821fa-114">有关详细信息[，请参阅](teams-powershell-move-from-sfbo.md)从 Skype for Business Online 连接器移动到 Teams PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="821fa-114">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="821fa-115">无论你是使用新模式执行Skype for Business转换，还是只是从默认的 Islands 配置升级到 TeamsOnly 模式，TeamsUpgradePolicy 都是主要工具。与 Teams策略一样，可以直接将 TeamsUpgradePolicy 分配给用户。</span><span class="sxs-lookup"><span data-stu-id="821fa-115">Whether you perform a select capabilities transition using Skype for Business modes or simply upgrade to TeamsOnly mode from the default Islands configuration, TeamsUpgradePolicy is the primary tool.Like any other policy in Teams, you can assign TeamsUpgradePolicy directly to a user.</span></span> <span data-ttu-id="821fa-116">还可以将策略设置为租户范围的默认值。</span><span class="sxs-lookup"><span data-stu-id="821fa-116">You can also set the policy as the tenant-wide default.</span></span> <span data-ttu-id="821fa-117">向用户分配的任何作业优先于租户默认设置。</span><span class="sxs-lookup"><span data-stu-id="821fa-117">Any assignment to a user takes precedence over the tenant default setting.</span></span>  <span data-ttu-id="821fa-118">可以在管理控制台的 Teams PowerShell 中管理策略。</span><span class="sxs-lookup"><span data-stu-id="821fa-118">You can manage the policy in the Teams Admin Console and in PowerShell.</span></span>

<span data-ttu-id="821fa-119">可以将 TeamsUpgradePolicy 的任何模式（TeamsOnly 模式除外）分配给本地Skype for Business用户。</span><span class="sxs-lookup"><span data-stu-id="821fa-119">You can assign any mode of TeamsUpgradePolicy, except for TeamsOnly mode, to users homed in Skype for Business on-premises.</span></span> <span data-ttu-id="821fa-120">相反，只能为托管在云中的用户分配 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="821fa-120">Conversely, users homed in the cloud can only be assigned TeamsOnly mode.</span></span> <span data-ttu-id="821fa-121">**TeamsOnly** 模式只能分配给已托管在云中的用户，因为只有该用户位于 Skype for Business Online 中，才能与 Skype for Business 用户以及 Microsoft 365 电话系统 功能进行互操作和联合。</span><span class="sxs-lookup"><span data-stu-id="821fa-121">**TeamsOnly mode can only be assigned to a user who is already homed in the cloud** because interop and federation with Skype for Business users as well as Microsoft 365 Phone System functionality are only possible if the user is homed in Skype for Business Online.</span></span>  <span data-ttu-id="821fa-122">此外，如果有 Skype for Business 本地部署 (，则不能将 **TeamsOnly** 模式分配为租户范围的默认值，该部署通过存在指向 Office 365 外部位置的 lyncdiscover DNS 记录检测到。</span><span class="sxs-lookup"><span data-stu-id="821fa-122">Further, **you can't assign TeamsOnly mode as the tenant-wide default if you have a Skype for Business on-premises deployment** (which is detected by presence of a lyncdiscover DNS record that points to location other than Office 365.</span></span> <span data-ttu-id="821fa-123">有关详细信息，请参阅[禁用混合配置以完成迁移到"仅Teams"。](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid)</span><span class="sxs-lookup"><span data-stu-id="821fa-123">For details, see [Disable your hybrid configuration to complete migration to Teams Only](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>

<span data-ttu-id="821fa-124">在本地Skype for Business帐户的用户必须使用 Teams 工具集Move-CsUser[](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)本地工具Skype for Business移动到"仅"模式。</span><span class="sxs-lookup"><span data-stu-id="821fa-124">Users with Skype for Business accounts homed on-premises [must be moved online](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) to Teams Only mode using Move-CsUser in the Skype for Business on-premises toolset.</span></span> 

<span data-ttu-id="821fa-125">与其他策略不同，不可在 Microsoft 365 或 Office 365 中创建新的 TeamsUpgradePolicy 实例。</span><span class="sxs-lookup"><span data-stu-id="821fa-125">Unlike other policies, it is not possible to create new instances of TeamsUpgradePolicy in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="821fa-126">所有现有实例都内置于服务中。</span><span class="sxs-lookup"><span data-stu-id="821fa-126">All the existing instances are built into the service.</span></span>  <span data-ttu-id="821fa-127"> (请注意，模式是 TeamsUpgradePolicy 中的一个属性，而不是策略实例的名称。) 在某些（但并非所有）情况下，策略实例的名称与模式相同。</span><span class="sxs-lookup"><span data-stu-id="821fa-127">(Note that mode is a property within TeamsUpgradePolicy, rather than the name of a policy instance.) In some--but not all--cases, the name of the policy instance is the same as mode.</span></span> <span data-ttu-id="821fa-128">具体而言，若要将 TeamsOnly 模式分配给用户，需要向该用户授予 TeamsUpgradePolicy 的"UpgradeToTeams"实例。</span><span class="sxs-lookup"><span data-stu-id="821fa-128">In particular, to assign TeamsOnly mode to a user, you will grant the “UpgradeToTeams” instance of TeamsUpgradePolicy to that user.</span></span> <span data-ttu-id="821fa-129">若要查看所有实例的列表，可以运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="821fa-129">To see a list of all instances, you can run the following command:</span></span>

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

<span data-ttu-id="821fa-130">若要将联机用户升级到 TeamsOnly 模式，请分配"UpgradeToTeams"实例：</span><span class="sxs-lookup"><span data-stu-id="821fa-130">To upgrade an online user to TeamsOnly mode, assign the “UpgradeToTeams” instance:</span></span> 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

<span data-ttu-id="821fa-131">若要将本地用户Skype for Business TeamsOnly 模式，Move-CsUser工具集：</span><span class="sxs-lookup"><span data-stu-id="821fa-131">To upgrade an on-premise Skype for Business user to TeamsOnly mode, use Move-CsUser in the on-premises toolset:</span></span>

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -credential $cred
```

<span data-ttu-id="821fa-132">若要更改租户中所有用户的模式，但具有按用户显式授予权限的用户除外 (优先) ，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="821fa-132">To change the mode for all users in the tenant, except those who have an explicit per-user grant (which takes precedence), run the following command:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
><span data-ttu-id="821fa-133">如果有任何用户在本地Skype for Business帐户，则不能在租户级别分配 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="821fa-133">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="821fa-134">必须使用 Move-CsUser Teams这些用户单独移动到"仅"模式。</span><span class="sxs-lookup"><span data-stu-id="821fa-134">You must move these users individually to Teams Only mode using Move-CsUser.</span></span>


## <a name="using-notifications-in-skype-for-business-clients"></a><span data-ttu-id="821fa-135">在客户端Skype for Business通知</span><span class="sxs-lookup"><span data-stu-id="821fa-135">Using notifications in Skype for Business clients</span></span>

<span data-ttu-id="821fa-136">管理员可以选择在客户端中提供最终用户通知Skype for Business通知用户他们即将升级到 Teams，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="821fa-136">Administrators have the option to provide end user notifications in the Skype for Business client to inform users that they will soon be upgraded to Teams, as shown in the following diagram.</span></span> <span data-ttu-id="821fa-137">例如，在管理员计划将一组用户升级到 TeamsOnly 模式之前一周，管理员可能需要为该组用户启用这些通知。</span><span class="sxs-lookup"><span data-stu-id="821fa-137">For example, a week before the administrator plans to upgrade a group of users to TeamsOnly mode, the administrator might want to turn on these notifications for that group of users.</span></span> <span data-ttu-id="821fa-138">这些通知是使用具有 NotifySfbUsers=true 的 TeamsUpgradePolicy 实例启用的。</span><span class="sxs-lookup"><span data-stu-id="821fa-138">These notifications are enabled using an instance of TeamsUpgradePolicy with NotifySfbUsers=true.</span></span>  <span data-ttu-id="821fa-139">对于 TeamsOnly 外的所有模式，每个模式实际上有两个实例，对应于 NotifySfbUsers 的两个值。</span><span class="sxs-lookup"><span data-stu-id="821fa-139">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span>  <span data-ttu-id="821fa-140">对于 TeamsOnly 外的所有模式，每个模式实际上有两个实例，对应于 NotifySfbUsers 的两个值。</span><span class="sxs-lookup"><span data-stu-id="821fa-140">For all modes other than TeamsOnly, there are actually two instances per mode, corresponding to the two values of NotifySfbUsers.</span></span> 

![显示通知的图表](media/teams-upgrade-sfb-with-notifications.png)

<span data-ttu-id="821fa-142">如果用户在 Skype for Business Online 中，只需分配与用户模式相同的策略实例，但使用 NotifySfbUsers=true。</span><span class="sxs-lookup"><span data-stu-id="821fa-142">If your users are homed in Skype for Business Online, simply assign the policy instance that has the same mode as the user, but with NotifySfbUsers=true.</span></span> 

<span data-ttu-id="821fa-143">如果用户位于 Skype for Business Server 本地，则需要使用本地工具集，并且需要 Skype for Business Server 2015 的 Skype for Business Server 2019 或 CU8。</span><span class="sxs-lookup"><span data-stu-id="821fa-143">If your users are homed in Skype for Business Server on-premises, you’ll need to use the on-premises toolset and you’ll need Skype for Business Server 2019 or CU8 for Skype for Business Server 2015.</span></span> <span data-ttu-id="821fa-144">对于本地 Skype for Business Server中的用户，将遵守 TeamsUpgradePolicy 联机实例中的 mode 属性，但不使用 NotifySfbUsers 属性。</span><span class="sxs-lookup"><span data-stu-id="821fa-144">For users homed in Skype for Business Server on-premises, the mode property from the online instance of TeamsUpgradePolicy is honored, but the NotifySfbUsers property is not.</span></span> <span data-ttu-id="821fa-145">如果需要通知，则必须创建 TeamsUpgradePolicy 本地实例来控制客户端行为。</span><span class="sxs-lookup"><span data-stu-id="821fa-145">If notifications are desired, you must create an on-premises instance of TeamsUpgradePolicy to control the client behavior.</span></span> 

<span data-ttu-id="821fa-146">在本地 PowerShell 窗口中，使用 NotifySfbUsers=true 创建 TeamsUpgradePolicy 的新实例：</span><span class="sxs-lookup"><span data-stu-id="821fa-146">In the on-premises PowerShell window, create a new instance of TeamsUpgradePolicy with NotifySfbUsers=true:</span></span>

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

<span data-ttu-id="821fa-147">然后，使用相同的本地 PowerShell 窗口，将新策略分配给所需的用户：</span><span class="sxs-lookup"><span data-stu-id="821fa-147">Then, using the same on-premises PowerShell window, assign that new policy to the desired users:</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a><span data-ttu-id="821fa-148">会议迁移</span><span class="sxs-lookup"><span data-stu-id="821fa-148">Meeting migration</span></span>

<span data-ttu-id="821fa-149">当用户迁移到 TeamsOnly 模式时，默认情况下，他们Skype for Business的现有会议将转换为Teams。</span><span class="sxs-lookup"><span data-stu-id="821fa-149">When a user is migrated to TeamsOnly mode, by default their existing Skype for Business meetings that they organized will be converted to Teams.</span></span> <span data-ttu-id="821fa-150">可以选择在将 TeamsOnly 模式分配给用户时禁用默认行为。</span><span class="sxs-lookup"><span data-stu-id="821fa-150">You can optionally disable the default behavior when assigning TeamsOnly mode to a user.</span></span> <span data-ttu-id="821fa-151">将用户从本地移动时，必须将会议迁移到云，以便使用联机用户帐户运行，但如果您未指定 -MoveToTeams，会议将迁移为 Skype for Business 会议，而不是转换为 Teams。</span><span class="sxs-lookup"><span data-stu-id="821fa-151">When moving users from on-premises, meetings must be migrated to the cloud to function with the online user account, but if you do not specify -MoveToTeams, the meetings will be migrated as Skype for Business meetings, rather than converted to Teams.</span></span> 

<span data-ttu-id="821fa-152">在租户级别分配 TeamsOnly 模式时，不会为任何用户触发会议迁移。</span><span class="sxs-lookup"><span data-stu-id="821fa-152">When assigning TeamsOnly mode at the tenant level, meeting migration is not triggered for any users.</span></span> <span data-ttu-id="821fa-153">如果要在租户级别分配 TeamsOnly 模式并迁移会议，可以使用 PowerShell 获取租户 (中的用户列表，例如，将 Get-CsOnlineUser 与所需的筛选器一同使用) 然后循环访问每个用户，以使用 Start-CsExMeetingMigration 触发会议迁移。</span><span class="sxs-lookup"><span data-stu-id="821fa-153">If you wish to assign TeamsOnly mode at the tenant level and migrate meetings, you can use PowerShell to get a list of users in the tenant (for example, using Get-CsOnlineUser with whatever filters are needed) and then loop through each of these users to trigger meeting migration using Start-CsExMeetingMigration.</span></span> <span data-ttu-id="821fa-154">有关详细信息，请参阅[使用会议迁移服务 (MMS) 。 ](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="821fa-154">For details, see [Using the Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>



## <a name="related-links"></a><span data-ttu-id="821fa-155">相关链接</span><span class="sxs-lookup"><span data-stu-id="821fa-155">Related links</span></span>

[<span data-ttu-id="821fa-156">共存模式 - 参考</span><span class="sxs-lookup"><span data-stu-id="821fa-156">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="821fa-157">配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="821fa-157">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="821fa-158">在本地和云之间移动用户</span><span class="sxs-lookup"><span data-stu-id="821fa-158">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="821fa-159">设置共存和升级设置</span><span class="sxs-lookup"><span data-stu-id="821fa-159">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="821fa-160">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="821fa-160">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="821fa-161">使用会议迁移服务 (MMS)</span><span class="sxs-lookup"><span data-stu-id="821fa-161">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
