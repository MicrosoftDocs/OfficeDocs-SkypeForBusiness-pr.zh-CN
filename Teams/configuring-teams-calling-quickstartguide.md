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
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4f3145455553c8126d66b3e56b69ec646f5f19ad
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530693"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="87d4b-103">快速入门指南：在 Microsoft Teams 中配置通话套餐</span><span class="sxs-lookup"><span data-stu-id="87d4b-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="87d4b-104">本指南帮助你安排一组用户并使其能够进行操作，以便他们可以在 Teams 中使用通话套餐。</span><span class="sxs-lookup"><span data-stu-id="87d4b-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="87d4b-105">请参阅 2017 年 12 月 12 日 Teams 中的通话套餐公告：[Teams 中通话功能的下一个阶段是智能通信](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="87d4b-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="87d4b-106">我们建议你与此快速入门指南一起使用[实践指导](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)和 [FastTrack](https://aka.ms/cloudvoice) 来规划和推动成功的部署。</span><span class="sxs-lookup"><span data-stu-id="87d4b-106">We recommend that, in parallel with this quick-start guide, you use our [practical guidance](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="87d4b-107">通过添加由 Skype for Business 提供技术支持的 Office 365 功能 - 通话套餐，现在可以使用 Teams 通过公用电话交换网 (PSTN) 向座机和手机拨打电话，也可以接听来自座机和手机的电话。</span><span class="sxs-lookup"><span data-stu-id="87d4b-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![在 Teams 中进行通话](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="87d4b-109">在 Teams 中启用 **“通话”** 选项卡的先决条件</span><span class="sxs-lookup"><span data-stu-id="87d4b-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="87d4b-110">若要启用团队中的**呼叫**选项卡用户需要具有 1:1 调用团队中启用并使用团队的客户端支持 1:1 团队呼叫。</span><span class="sxs-lookup"><span data-stu-id="87d4b-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="87d4b-111">若要了解如何管理中的团队呼叫 1:1，读取[设置 CsTeamsCallingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="87d4b-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="87d4b-112">若要了解哪些客户端支持呼叫，请阅读[限制和规格的 Microsoft 团队](https://docs.microsoft.com/en-us/microsoftteams/limits-specifications-teams)。</span><span class="sxs-lookup"><span data-stu-id="87d4b-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="87d4b-113">目前，语音邮件将不可用呼叫选项卡中除非用户启用了 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="87d4b-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="87d4b-114">启用团队中的**拨号盘**的先决条件</span><span class="sxs-lookup"><span data-stu-id="87d4b-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="87d4b-115">若要启用团队中的**拔号盘**选项卡，并让用户发起和接收 PSTN 呼叫您需要设置用户的电话系统和调用计划。</span><span class="sxs-lookup"><span data-stu-id="87d4b-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="87d4b-116">若要了解如何设置调用计划，请阅读[Set up 调用计划](https://docs.microsoft.com/en-us/microsoftteams/set-up-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="87d4b-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/en-us/microsoftteams/set-up-calling-plans).</span></span>

> [!NOTE]
> <span data-ttu-id="87d4b-117">您可以使用直接路由允许您强制用户和接收 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="87d4b-117">You can also use Direct Routing to allow your users to mand and receive PSTN calls.</span></span> <span data-ttu-id="87d4b-118">若要了解如何设置直接路由，请阅读[配置直接路由](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure)。</span><span class="sxs-lookup"><span data-stu-id="87d4b-118">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure).</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="87d4b-119">Teams 互操作性策略配置</span><span class="sxs-lookup"><span data-stu-id="87d4b-119">Teams interop policy configuration</span></span>
<span data-ttu-id="87d4b-120">若要启用团队以开始接收呼叫，您将需要更新团队升级策略和团队互操作性策略，使用[的 Microsoft 团队业务管理中心的 Skype](https://aka.ms/teamsadmincenter)或使用远程 Windows PowerShell 会话 Skype for Business [ `*-CsTeamsUpgradePolicy`和`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype)cmdlet，以将重定向到团队呼叫。</span><span class="sxs-lookup"><span data-stu-id="87d4b-120">To enable Teams to begin receiving calls, you'll need to update Teams upgrade policy and Teams interop policy, using [Microsoft Teams & Skype for Business Admin Center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsUpgradePolicy` and `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span>

<span data-ttu-id="87d4b-121">有关升级团队的策略和团队互操作性策略的详细信息，请参阅[迁移和组织使用团队一起 for Business 的 Skype 的互操作性指南](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)。</span><span class="sxs-lookup"><span data-stu-id="87d4b-121">For more information about Teams upgrade policy and Teams interop policy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span></span>

> [!TIP]
> <span data-ttu-id="87d4b-122">若要查找所需的 PowerShell cmdlet，键入"CsTeamsUpgradePolicy"或"CsTeamsInteropPolicy"的**筛选器**框中[的业务 PowerShell cmdlet 文档 Skype](https://docs.microsoft.com/powershell/module/skype)。</span><span class="sxs-lookup"><span data-stu-id="87d4b-122">To find the PowerShell cmdlets you need, type "CsTeamsUpgradePolicy" or "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-upgrade-and-interop-policies"></a><span data-ttu-id="87d4b-123">默认团队需要升级和互操作性策略</span><span class="sxs-lookup"><span data-stu-id="87d4b-123">Default Teams upgrade and interop policies</span></span>
<span data-ttu-id="87d4b-124">Teams 具有默认策略配置，旨在确保在部署 Teams 期间，现有业务工作流不会中断。</span><span class="sxs-lookup"><span data-stu-id="87d4b-124">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="87d4b-125">默认情况下，向你的用户拨打的 VoIP、PSTN 和联合呼叫将仍路由至 Skype for Business，直到你更新策略以在 Teams 中启用入站通话。</span><span class="sxs-lookup"><span data-stu-id="87d4b-125">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="87d4b-126">这可确保在你开始试点和部署 Teams 时，语音服务不会出现意外中断。</span><span class="sxs-lookup"><span data-stu-id="87d4b-126">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="87d4b-127">默认情况下升级策略保留在将服从团队互操作性策略，以确定要在其中聊天和呼叫的路由-的旧版模式的团队团队或 for Business 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="87d4b-127">Teams upgrade policy by default is kept at legacy mode that will honor Teams interop policy to determine where chats and calls are to be routed--Teams or Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="87d4b-128">团队的行为升级策略和[迁移和组织使用团队一起 for Business 的 Skype 的互操作性指南](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)中所述，将发生更改团队互操作性策略</span><span class="sxs-lookup"><span data-stu-id="87d4b-128">The behaviors of Teams upgrade policy and Teams interop policy will soon change as described in [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="87d4b-129">Teams 互操作性策略具有以下默认配置：</span><span class="sxs-lookup"><span data-stu-id="87d4b-129">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="87d4b-130">默认配置的行为如下：</span><span class="sxs-lookup"><span data-stu-id="87d4b-130">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="87d4b-131">**对于现有 Skype for Business 客户**，此策略旨在确保 Skype for Business 呼叫定向至 Skype for Business，Teams 呼叫定向至 Teams。</span><span class="sxs-lookup"><span data-stu-id="87d4b-131">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="87d4b-132">此策略生效后，PSTN 和联合呼叫将定向至 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="87d4b-132">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="87d4b-133">**对于没有 Skype for Business 的客户**，此策略生效后，除了 Teams 用户之间的呼叫外，Teams 中将仅支持出站 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="87d4b-133">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="87d4b-134">要在 Teams 接听 PSTN 呼叫，你需要更改为你的用户分配的 Teams 互操作性策略。</span><span class="sxs-lookup"><span data-stu-id="87d4b-134">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="87d4b-135">对于预配了用于 Skype for Business Online 的电话系统和通话套餐许可证并且配置了默认全局 Teams 互操作性策略的用户，Teams 中将会启用“通话”选项卡，在无需管理员采取任何管理操作的情况下，他们可以从 Teams 进行出站 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="87d4b-135">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="87d4b-136">配置 Teams 以接听入站 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="87d4b-136">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="87d4b-137">若要接收团队中的入站的 PSTN 呼叫，您需要通过应用与相应团队互操作性策略设置的团队升级策略调用应用程序的默认配置团队`CallingDefaultClient`团队参数。</span><span class="sxs-lookup"><span data-stu-id="87d4b-137">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams upgrade policy with the corresponding Teams interop policy that sets `CallingDefaultClient` parameter to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87d4b-138">我们建议在进行较广范围或组织级别的更改之前，对一组初始用户应用此配置以利用 Teams 中这些令人兴奋的新通话功能。</span><span class="sxs-lookup"><span data-stu-id="87d4b-138">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="87d4b-139">如果您选择要继续使用旧的团队升级策略，则使用下面的预配置的团队互操作性策略路由到团队的入站的 PSTN 呼叫：</span><span class="sxs-lookup"><span data-stu-id="87d4b-139">If you choose to continue to use the legacy Teams upgrade policy, use the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="87d4b-140">如果您选择使用更新的团队升级策略，您需要向用户分配 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="87d4b-140">If you choose to use the updated Teams upgrade policy, you need to assign TeamsOnly mode to your users.</span></span>

<span data-ttu-id="87d4b-141">以上策略的行为如下：</span><span class="sxs-lookup"><span data-stu-id="87d4b-141">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="87d4b-142">**对于现有 Skype for Business 客户**，此策略旨在将传入呼叫重定向至 Teams。</span><span class="sxs-lookup"><span data-stu-id="87d4b-142">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="87d4b-143">这包括 VoIP（来自 Teams 和 Skype for Business）和 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="87d4b-143">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> 
* <span data-ttu-id="87d4b-144">**对于没有 Skype for Business 的客户**，此策略生效后，PSTN 呼叫将在 Teams 中接听。</span><span class="sxs-lookup"><span data-stu-id="87d4b-144">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="87d4b-145">当前，将 `CallingDefaultClient` 更改为 Teams 还将影响向 Skype for Business IP 电话拨打的呼叫。</span><span class="sxs-lookup"><span data-stu-id="87d4b-145">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="87d4b-146">传入呼叫不会在电话上接收，而只会使 Teams 客户端响铃。</span><span class="sxs-lookup"><span data-stu-id="87d4b-146">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="87d4b-147">有关对现有的已认证 SIP 电话的支持的信息，请参阅 [Skype for Business 到 Microsoft Teams 功能路线图](https://aka.ms/skype2teamsroadmap)。</span><span class="sxs-lookup"><span data-stu-id="87d4b-147">Please consult the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a><span data-ttu-id="87d4b-148">如何配置用户以接收 PSTN 呼叫的团队中</span><span class="sxs-lookup"><span data-stu-id="87d4b-148">How to configure users to receive PSTN calls in Teams</span></span>
<span data-ttu-id="87d4b-149">使用旧的团队升级策略时应用团队互操作性策略，如上述通过业务远程 Windows PowerShell 会话的 Skype 重定向到团队呼叫：</span><span class="sxs-lookup"><span data-stu-id="87d4b-149">When using the legacy Teams upgrade policy, apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

<span data-ttu-id="87d4b-150">如果您选择使用 TeamsOnly 模式，您可以更改为 TeamsOnly 通过 Microsoft 团队和 Skype 的业务管理中心中，或通过业务远程 Windows PowerShell 会话的 Skype 重定向到团队呼叫的用户的共存模式：</span><span class="sxs-lookup"><span data-stu-id="87d4b-150">If you choose to use TeamsOnly mode, you can change the user's coexistence mode to TeamsOnly via Microsoft Teams & Skype for Business Admin Center, or via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a><span data-ttu-id="87d4b-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87d4b-151">See also</span></span>
[<span data-ttu-id="87d4b-152">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="87d4b-152">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="87d4b-153">使用团队一起 Skype for Business 的组织的迁移和互操作性指南</span><span class="sxs-lookup"><span data-stu-id="87d4b-153">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="87d4b-154">Microsoft Teams 中具有通话套餐的电话系统实践指导</span><span class="sxs-lookup"><span data-stu-id="87d4b-154">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[<span data-ttu-id="87d4b-155">Skype for Business PowerShell cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="87d4b-155">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="87d4b-156">Teams PowerShell cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="87d4b-156">Teams PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/teams)
