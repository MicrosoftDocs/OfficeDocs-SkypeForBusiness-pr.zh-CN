---
title: 快速入门指南 - 配置呼叫计划
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: 有关在 Microsoft Teams 中配置通话计划的快速入门指南，以便可以启动并运行一组用户。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c43decd3b3f7d5e23e0e7937a93b4663a80aa583
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799762"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="18e57-103">快速入门指南：在 Microsoft Teams 中配置通话套餐</span><span class="sxs-lookup"><span data-stu-id="18e57-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="18e57-104">本指南将帮助你启动并运行一组用户，以便他们可以浏览 Teams 中的通话计划。</span><span class="sxs-lookup"><span data-stu-id="18e57-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="18e57-105">阅读 2017 年 12 月 12 日 Teams 中的通话计划公告[：Intelligent Communications](https://aka.ms/ipyqus)在 Teams 中执行下一步通话</span><span class="sxs-lookup"><span data-stu-id="18e57-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="18e57-106">我们建议，在此快速入门指南的并行下，阅读电话系统与通话[](calling-plan-landing-page.md)计划和[FastTrack，](https://aka.ms/cloudvoice)以计划和推动成功推出。</span><span class="sxs-lookup"><span data-stu-id="18e57-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="18e57-107">通过添加呼叫计划-由 Skype for Business 支持 Microsoft 365 和 Office 365 功能，你现在可以使用 Teams 通过公用电话交换网 (PSTN) 拨打和接听座机和手机的电话。</span><span class="sxs-lookup"><span data-stu-id="18e57-107">By adding Calling Plans - a Microsoft 365 and Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![显示 Teams 中的"联系人"页面的屏幕截图](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="18e57-109">在 Teams 中启用"呼叫 **"** 选项卡的先决条件</span><span class="sxs-lookup"><span data-stu-id="18e57-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="18e57-110">若要在Teams 中启用"呼叫"选项卡，用户需要在 Teams 中启用 1：1 通话，并且使用支持 1 对 1 Teams 通话的 Teams 客户端。</span><span class="sxs-lookup"><span data-stu-id="18e57-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="18e57-111">若要了解如何在 Teams 中管理 1：1 通话，请阅读[Set-CsTeamsCallingPolicy。](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="18e57-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="18e57-112">若要了解哪些客户端支持呼叫，请阅读 [Microsoft Teams 的限制和规范](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)。</span><span class="sxs-lookup"><span data-stu-id="18e57-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="18e57-113">目前，语音邮件在"呼叫"选项卡中不可用，除非为用户启用了 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="18e57-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="18e57-114">在 Teams 中启用 **拨号盘** 的先决条件</span><span class="sxs-lookup"><span data-stu-id="18e57-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="18e57-115">若要在 Teams **中** 启用"拨号盘"选项卡并允许用户拨打和接听 PSTN 呼叫，你需要为电话系统和呼叫计划预配用户。</span><span class="sxs-lookup"><span data-stu-id="18e57-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="18e57-116">若要了解如何设置呼叫计划，请阅读"[设置呼叫计划"。](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="18e57-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>
<span data-ttu-id="18e57-117">此外，对于仅 Teams 用户，必须确保在 Teams 呼叫策略中启用"允许私人呼叫"。</span><span class="sxs-lookup"><span data-stu-id="18e57-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="18e57-118">有关详细信息 [，请参阅](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) "在过渡到新的 Microsoft Teams 管理中心期间管理 Teams"。</span><span class="sxs-lookup"><span data-stu-id="18e57-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="18e57-119">您还可以使用直接路由来允许用户拨打和接听 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="18e57-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="18e57-120">若要了解如何设置直接路由，请阅读"[配置直接路由"。](https://docs.microsoft.com/microsoftteams/direct-routing-configure)</span><span class="sxs-lookup"><span data-stu-id="18e57-120">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="18e57-121">使用 TeamsUpgradePolicy 控制通话地点</span><span class="sxs-lookup"><span data-stu-id="18e57-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="18e57-122">为了控制传入呼叫 (和聊天) 是否进入 Teams 或 Skype for Business，管理员使用 TeamsUpgradePolicy，使用 [Microsoft Teams](https://aka.ms/teamsadmincenter) 管理中心，或者通过 Skype for [Business](https://docs.microsoft.com/powershell/module/skype) cmdlet 使用远程 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="18e57-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="18e57-123">TeamsUpgradePolicy 的默认配置是"群岛模式"，它旨在确保在 Teams 部署期间不会中断现有业务工作流。</span><span class="sxs-lookup"><span data-stu-id="18e57-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="18e57-124">默认情况下，VoIP、PSTN 和用户的联合呼叫将继续路由到 Skype for Business，直到你更新策略以启用对 Teams 的入站呼叫。</span><span class="sxs-lookup"><span data-stu-id="18e57-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="18e57-125">当收件人位于岛屿模式下时：</span><span class="sxs-lookup"><span data-stu-id="18e57-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="18e57-126">源自 Skype for Business 的传入 VOIP 呼叫始终位于接收者的 Skype for Business 客户端中。</span><span class="sxs-lookup"><span data-stu-id="18e57-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="18e57-127">如果发送方和接收方位于同一租户中，源自 Teams 的传入 VOIP 呼叫将登 *陆 Teams。*</span><span class="sxs-lookup"><span data-stu-id="18e57-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="18e57-128">传入的联合 VOIP (来自哪个客户端) PSTN 呼叫始终位于接收者的 Skype for Business 客户端中。</span><span class="sxs-lookup"><span data-stu-id="18e57-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="18e57-129">为了确保传入的 VOIP 和 PSTN 呼叫始终进入用户的 Teams 客户端，将用户的共存模式更新为 TeamsOnly (这意味着，为其分配 TeamsUpgradePolicy 的"UpgradeToTeams"实例。</span><span class="sxs-lookup"><span data-stu-id="18e57-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="18e57-130">有关共存模式和 TeamsUpgradePolicy 详细信息，请参阅将 Teams 与 Skype for Business 一起使用的组织迁移和 [互操作性指南](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="18e57-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="18e57-131">**备注**</span><span class="sxs-lookup"><span data-stu-id="18e57-131">**NOTES**</span></span>
 - <span data-ttu-id="18e57-132">Skype for Business IP 电话将接收呼叫，即使用户位于 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="18e57-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="18e57-133">已预配电话系统和呼叫计划许可证以用于 Skype for Business Online (例如，已为其分配了 OnlineVoiceRoutingPolicy) 值的用户将在 Teams 中启用"呼叫"选项卡，并且可以从 Teams 拨打出站 PSTN 呼叫，而无需管理员执行任何管理操作。</span><span class="sxs-lookup"><span data-stu-id="18e57-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="18e57-134">如何配置用户以在 Teams 中接收所有传入的 VOIP 和 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="18e57-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="18e57-135">若要确保用户在 Teams 中收到所有传入的 VOIP 和 PSTN 呼叫，在 Microsoft Teams 管理中心将用户的共存模式设置为 TeamsOnly，或使用 Skype for Business 远程 Windows PowerShell 会话更新 TeamsUpgradePolicy，如下所示：</span><span class="sxs-lookup"><span data-stu-id="18e57-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a><span data-ttu-id="18e57-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18e57-136">See also</span></span>
[<span data-ttu-id="18e57-137">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="18e57-137">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="18e57-138">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="18e57-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="18e57-139">具有通话套餐的电话系统</span><span class="sxs-lookup"><span data-stu-id="18e57-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="18e57-140">Skype for Business PowerShell cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="18e57-140">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

