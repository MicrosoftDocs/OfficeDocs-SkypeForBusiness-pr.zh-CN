---
title: 快速入门指南 - 在 Microsoft Teams 中配置通话套餐
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
search.appverid: MET150
description: 有关在 Microsoft Teams 中配置通话套餐的快速入门指南。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7cd8f5a2d0402418bb2a8c0e5a2c20bc95aeef68
ms.sourcegitcommit: 2dd1369e5112b0c4ed7c6b0be8a17489b71f494a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30469743"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="2a3d3-103">快速入门指南：在 Microsoft Teams 中配置通话套餐</span><span class="sxs-lookup"><span data-stu-id="2a3d3-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="2a3d3-104">本指南帮助你安排一组用户并使其能够进行操作，以便他们可以在 Teams 中使用通话套餐。</span><span class="sxs-lookup"><span data-stu-id="2a3d3-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="2a3d3-105">请参阅 2017 年 12 月 12 日 Teams 中的通话套餐公告：[Teams 中通话功能的下一个阶段是智能通信](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="2a3d3-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="2a3d3-106">我们建议，本快速入门指南的同时，在您阅读[电话系统与调用计划](calling-plan-landing-page.md)和[FastTrack](https://aka.ms/cloudvoice)计划和驱动器成功推出。</span><span class="sxs-lookup"><span data-stu-id="2a3d3-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="2a3d3-107">通过添加由 Skype for Business 提供技术支持的 Office 365 功能 - 通话套餐，现在可以使用 Teams 通过公用电话交换网 (PSTN) 向座机和手机拨打电话，也可以接听来自座机和手机的电话。</span><span class="sxs-lookup"><span data-stu-id="2a3d3-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![在 Teams 中进行通话](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="2a3d3-109">在 Teams 中启用 **“通话”** 选项卡的先决条件</span><span class="sxs-lookup"><span data-stu-id="2a3d3-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="2a3d3-110">若要启用团队中的**呼叫**选项卡用户需要具有 1:1 调用团队中启用并使用团队的客户端支持 1:1 团队呼叫。</span><span class="sxs-lookup"><span data-stu-id="2a3d3-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="2a3d3-111">若要了解如何管理中的团队呼叫 1:1，读取[设置 CsTeamsCallingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="2a3d3-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="2a3d3-112">若要了解哪些客户端支持呼叫，请阅读[限制和规格的 Microsoft 团队](https://docs.microsoft.com/en-us/microsoftteams/limits-specifications-teams)。</span><span class="sxs-lookup"><span data-stu-id="2a3d3-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="2a3d3-113">目前，语音邮件将不可用呼叫选项卡中除非用户启用了 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="2a3d3-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="2a3d3-114">启用团队中的**拨号盘**的先决条件</span><span class="sxs-lookup"><span data-stu-id="2a3d3-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="2a3d3-115">若要启用团队中的**拔号盘**选项卡，并让用户发起和接收 PSTN 呼叫您需要设置用户的电话系统和调用计划。</span><span class="sxs-lookup"><span data-stu-id="2a3d3-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="2a3d3-116">若要了解如何设置调用计划，请阅读[Set up 调用计划](https://docs.microsoft.com/en-us/microsoftteams/set-up-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="2a3d3-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/en-us/microsoftteams/set-up-calling-plans).</span></span>

> [!NOTE]
> <span data-ttu-id="2a3d3-117">您可以使用直接路由允许您强制用户和接收 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="2a3d3-117">You can also use Direct Routing to allow your users to mand and receive PSTN calls.</span></span> <span data-ttu-id="2a3d3-118">若要了解如何设置直接路由，请阅读[配置直接路由](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure)。</span><span class="sxs-lookup"><span data-stu-id="2a3d3-118">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="2a3d3-119">使用控件呼叫位于其中 TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="2a3d3-119">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="2a3d3-120">若要控制传入呼叫 （以及聊天） 位于团队或 Skype for Business 中，管理员可以使用 TeamsUpgradePolicy，使用任一[Microsoft 团队管理中心](https://aka.ms/teamsadmincenter)或远程 Windows PowerShell 会话使用[Skype for Business](https://docs.microsoft.com/powershell/module/skype)cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2a3d3-120">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="2a3d3-121">TeamsUpgradePolicy 的默认配置是群岛模式，旨在确保该工作流不会中断团队部署过程中的现有业务。</span><span class="sxs-lookup"><span data-stu-id="2a3d3-121">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="2a3d3-122">默认情况下，向你的用户拨打的 VoIP、PSTN 和联合呼叫将仍路由至 Skype for Business，直到你更新策略以在 Teams 中启用入站通话。</span><span class="sxs-lookup"><span data-stu-id="2a3d3-122">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="2a3d3-123">当收件人处于群岛模式中：</span><span class="sxs-lookup"><span data-stu-id="2a3d3-123">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="2a3d3-124">传入的 VOIP 呼叫该中起源于的 Skype for Business 始终中收件人的 Skype 业务客户端的园地。</span><span class="sxs-lookup"><span data-stu-id="2a3d3-124">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="2a3d3-125">传入 VOIP 呼叫的团队*的发送者和接收者是否位于同一租户*中的团队园地对源自。</span><span class="sxs-lookup"><span data-stu-id="2a3d3-125">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="2a3d3-126">传入联盟 （无论哪些客户端发起） 的 VOIP 和 PSTN 呼叫始终在收件人的 Skype 园地 for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="2a3d3-126">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="2a3d3-127">若要确保传入 VOIP 和 PSTN 始终调用园地用户的工作组客户端中，更新用户的共存模式为 TeamsOnly （这意味着，将其分配"UpgradeToTeams"TeamsUpgradePolicy 实例。</span><span class="sxs-lookup"><span data-stu-id="2a3d3-127">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="2a3d3-128">在共存模式和 TeamsUpgradePolicy 的详细信息，请参阅[迁移和组织使用团队一起 for Business 的 Skype 的互操作性指南](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="2a3d3-128">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="2a3d3-129">**NOTES**</span><span class="sxs-lookup"><span data-stu-id="2a3d3-129">**NOTES**</span></span>
 - <span data-ttu-id="2a3d3-130">业务 IP 电话的 Skype 将接收呼叫，即使用户处于 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="2a3d3-130">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="2a3d3-131">业务联机 （例如他们已分配的值为 OnlineVoiceRoutingPolicy），会在工作组中启用呼叫选项卡并可将出站 PSTN 呼叫从已经设置与电话系统和调用计划用于 Skype 的许可证的用户没有管理员无需采取任何管理操作的团队。</span><span class="sxs-lookup"><span data-stu-id="2a3d3-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="2a3d3-132">如何配置用户以接收所有传入的 VOIP 和 PSTN 呼叫的团队中</span><span class="sxs-lookup"><span data-stu-id="2a3d3-132">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="2a3d3-133">若要确保用户收到团队中的所有传入的 VOIP 和 PSTN 呼叫，将用户的共存模式设置为 TeamsOnly，在 Microsoft 团队管理中心，或使用业务远程 Windows PowerShell 会话的 Skype 更新 TeamsUpgradePolicy，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2a3d3-133">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a><span data-ttu-id="2a3d3-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a3d3-134">See also</span></span>
[<span data-ttu-id="2a3d3-135">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="2a3d3-135">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="2a3d3-136">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="2a3d3-136">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="2a3d3-137">具有通话套餐的电话系统</span><span class="sxs-lookup"><span data-stu-id="2a3d3-137">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="2a3d3-138">Skype for Business PowerShell cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="2a3d3-138">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

