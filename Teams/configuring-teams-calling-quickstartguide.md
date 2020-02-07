---
title: 快速入门指南 - 在 Microsoft Teams 中配置通话套餐
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: 有关在 Microsoft 团队中配置呼叫计划的快速入门指南。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b7f1ded5d843689e828b00c0a466e012b8750582
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825360"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="2f05a-103">快速入门指南：在 Microsoft Teams 中配置通话套餐</span><span class="sxs-lookup"><span data-stu-id="2f05a-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="2f05a-104">本指南将帮助您获取并运行一组用户，以便他们可以浏览团队中的呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="2f05a-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="2f05a-105">阅读2017年12月12日，发布团队中的通话计划：[智能通信在团队中进行下一步通话](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="2f05a-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="2f05a-106">我们建议，与本快速入门指南并行，[使用通话计划](calling-plan-landing-page.md)和[FastTrack](https://aka.ms/cloudvoice)阅读电话系统以规划和推动成功的推出。</span><span class="sxs-lookup"><span data-stu-id="2f05a-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="2f05a-107">通过添加呼叫计划-Skype for Business 支持的 Office 365 功能-您现在可以使用团队通过公共交换电话网络（PSTN）拨打和接收来自土地线路和移动电话的电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="2f05a-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![显示团队中的联系人页面的屏幕截图](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="2f05a-109">启用团队中的 "**调用**" 选项卡的先决条件</span><span class="sxs-lookup"><span data-stu-id="2f05a-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="2f05a-110">若要启用团队中的 "**通话**" 选项卡，用户需要在团队中启用1:1 通话并使用支持1:1 团队通话的团队客户端。</span><span class="sxs-lookup"><span data-stu-id="2f05a-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="2f05a-111">若要了解如何在团队中管理1:1 通话，请参阅[CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="2f05a-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="2f05a-112">若要了解哪些客户端支持呼叫，请阅读[Microsoft 团队的限制和规范](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)。</span><span class="sxs-lookup"><span data-stu-id="2f05a-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="2f05a-113">目前，语音邮件将在 "通话" 选项卡中不可用，除非用户已启用 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="2f05a-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="2f05a-114">启用团队中的**拨号键盘**的先决条件</span><span class="sxs-lookup"><span data-stu-id="2f05a-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="2f05a-115">若要启用团队中的 "**拨号盘**" 选项卡并允许用户拨打和接收 PSTN 呼叫，您需要为用户预配电话系统和通话计划。</span><span class="sxs-lookup"><span data-stu-id="2f05a-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="2f05a-116">若要了解如何设置通话计划，请参阅[设置通话计划](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="2f05a-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>
<span data-ttu-id="2f05a-117">此外，对于仅限团队的用户，您必须确保在团队呼叫策略中启用 "允许私人通话"。</span><span class="sxs-lookup"><span data-stu-id="2f05a-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="2f05a-118">有关详细信息，请参阅[切换到新的 Microsoft 团队管理中心期间管理团队](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="2f05a-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="2f05a-119">您还可以使用直接路由允许用户拨打和接收 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="2f05a-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="2f05a-120">若要了解如何设置直接路由，请参阅[配置直接路由](https://docs.microsoft.com/microsoftteams/direct-routing-configure)。</span><span class="sxs-lookup"><span data-stu-id="2f05a-120">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="2f05a-121">使用 TeamsUpgradePolicy 控制呼叫所在的位置</span><span class="sxs-lookup"><span data-stu-id="2f05a-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="2f05a-122">若要控制团队或 Skype for business 中的传入呼叫（和聊天）土地，管理员是否使用[Microsoft 团队管理中心](https://aka.ms/teamsadmincenter)或使用与[Skype for](https://docs.microsoft.com/powershell/module/skype) Business Cmdlet 的远程 Windows PowerShell 会话使用 TeamsUpgradePolicy。</span><span class="sxs-lookup"><span data-stu-id="2f05a-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="2f05a-123">TeamsUpgradePolicy 的默认配置为 "孤岛" 模式，它旨在确保现有业务工作流在团队部署期间不会中断。</span><span class="sxs-lookup"><span data-stu-id="2f05a-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="2f05a-124">默认情况下，对你的用户的 VoIP、PSTN 和联合呼叫将继续路由到 Skype for business，直到你更新策略以启用到团队的入站呼叫。</span><span class="sxs-lookup"><span data-stu-id="2f05a-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="2f05a-125">当收件人处于 "孤岛" 模式时：</span><span class="sxs-lookup"><span data-stu-id="2f05a-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="2f05a-126">在 Skype for Business 中发起的 VOIP 呼叫始终位于接收方的 Skype for business 客户端中。</span><span class="sxs-lookup"><span data-stu-id="2f05a-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="2f05a-127">*如果发件人和接收方位于同一个租户*中，则为团队中的团队土地发起的 VOIP 呼叫。</span><span class="sxs-lookup"><span data-stu-id="2f05a-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="2f05a-128">传入的联合 VOIP （无论发起哪种客户端）和 PSTN 呼叫始终位于接收方的 Skype for business 客户端中。</span><span class="sxs-lookup"><span data-stu-id="2f05a-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="2f05a-129">若要确保传入 VOIP 和 PSTN 呼叫始终位于用户的团队客户端，请将用户的共存模式更新为 TeamsOnly （这意味着，为他们分配 TeamsUpgradePolicy 的 "UpgradeToTeams" 实例。</span><span class="sxs-lookup"><span data-stu-id="2f05a-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="2f05a-130">有关共存模式和 TeamsUpgradePolicy 的详细信息，请参阅[使用团队与 Skype For business 一起使用的组织的迁移和互操作指南](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="2f05a-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="2f05a-131">**笔记**</span><span class="sxs-lookup"><span data-stu-id="2f05a-131">**NOTES**</span></span>
 - <span data-ttu-id="2f05a-132">Skype for Business IP 手机将接收呼叫，即使用户处于 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="2f05a-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="2f05a-133">已使用手机系统和通话计划许可证（如已为 Skype for Business Online）使用的用户（如已分配了 OnlineVoiceRoutingPolicy 的值）将在团队中启用 "呼叫" 选项卡，并且可以将出站 PSTN 呼叫从无需管理员执行任何管理操作的团队。</span><span class="sxs-lookup"><span data-stu-id="2f05a-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="2f05a-134">如何配置用户以接收团队中的所有传入 VOIP 和 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="2f05a-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="2f05a-135">为确保用户收到团队中所有传入的 VOIP 和 PSTN 呼叫，请将用户的共存模式设置为 Microsoft 团队管理中心中的 TeamsOnly，或使用 Skype for Business 远程 Windows PowerShell 会话更新 TeamsUpgradePolicy，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2f05a-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a><span data-ttu-id="2f05a-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f05a-136">See also</span></span>
[<span data-ttu-id="2f05a-137">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="2f05a-137">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="2f05a-138">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="2f05a-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="2f05a-139">具有通话套餐的电话系统</span><span class="sxs-lookup"><span data-stu-id="2f05a-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="2f05a-140">Skype for Business PowerShell cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="2f05a-140">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

