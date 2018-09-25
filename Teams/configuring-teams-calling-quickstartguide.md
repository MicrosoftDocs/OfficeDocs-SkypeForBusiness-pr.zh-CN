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
ms.openlocfilehash: 6a1fb82f57035f238ce222bf7f21b72983d21075
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015930"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="26923-103">快速入门指南：在 Microsoft Teams 中配置通话套餐</span><span class="sxs-lookup"><span data-stu-id="26923-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="26923-104">本指南帮助你安排一组用户并使其能够进行操作，以便他们可以在 Teams 中使用通话套餐。</span><span class="sxs-lookup"><span data-stu-id="26923-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="26923-105">请参阅 2017 年 12 月 12 日 Teams 中的通话套餐公告：[Teams 中通话功能的下一个阶段是智能通信](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="26923-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="26923-106">我们建议你与此快速入门指南一起使用[实践指导](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)和 [FastTrack](https://aka.ms/cloudvoice) 来规划和推动成功的部署。</span><span class="sxs-lookup"><span data-stu-id="26923-106">We recommend that, in parallel with this quick-start guide, you use our [practical guidance](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="26923-107">通过添加由 Skype for Business 提供技术支持的 Office 365 功能 - 通话套餐，现在可以使用 Teams 通过公用电话交换网 (PSTN) 向座机和手机拨打电话，也可以接听来自座机和手机的电话。</span><span class="sxs-lookup"><span data-stu-id="26923-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![在 Teams 中进行通话](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="26923-109">在 Teams 中启用 **“通话”** 选项卡的先决条件</span><span class="sxs-lookup"><span data-stu-id="26923-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="26923-110">要在 Teams 中启用 **“通话”** 选项卡，并允许你的用户拨打和接听 PSTN 呼叫，你需要为电话系统和通话套餐预配用户。</span><span class="sxs-lookup"><span data-stu-id="26923-110">To enable the **Calls** tab in Teams and allow your users to make and receive PSTN calls, you will need provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="26923-111">要了解如何对此进行设置，请参阅[设置通话套餐](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)。</span><span class="sxs-lookup"><span data-stu-id="26923-111">To learn how to set this up, read [Set up Calling Plans](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans).</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="26923-112">Teams 互操作性策略配置</span><span class="sxs-lookup"><span data-stu-id="26923-112">Teams interop policy configuration</span></span>
<span data-ttu-id="26923-113">要启用 Teams 以开始接听呼叫，需要使用 [Microsoft Teams 和 Skype for Business 管理中心](https://aka.ms/teamsadmincenter)或结合使用远程 Windows PowerShell 会话与 Skype for Business [`*-CsTeamsUpgradePolicy` 和 `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlet 来更新 Teams 升级策略和 Teams 互操作性策略以将呼叫重定向至 Teams。</span><span class="sxs-lookup"><span data-stu-id="26923-113">To enable Teams to begin receiving calls, you'll need to update Teams upgrade policy and Teams interop policy, using [Microsoft Teams & Skype for Business Admin Center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsUpgradePolicy` and `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span>

<span data-ttu-id="26923-114">有关 Teams 升级策略和 Teams 互操作性策略的详细信息，请参阅[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)。</span><span class="sxs-lookup"><span data-stu-id="26923-114">For more information about Teams upgrade policy and Teams interop policy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span></span>

> [!TIP]
> <span data-ttu-id="26923-115">要查找你所需的 PowerShell cmdlet，请在 [Skype for Business PowerShell cmdlet 文档](https://docs.microsoft.com/powershell/module/skype)中的 **“筛选”** 框中键入“CsTeamsUpgradePolicy”或“CsTeamsInteropPolicy”。</span><span class="sxs-lookup"><span data-stu-id="26923-115">To find the PowerShell cmdlets you need, type "CsTeamsUpgradePolicy" or "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-upgrade-and-interop-policies"></a><span data-ttu-id="26923-116">默认的 Teams 升级和互操作性策略</span><span class="sxs-lookup"><span data-stu-id="26923-116">Default Teams upgrade and interop policies</span></span>
<span data-ttu-id="26923-117">Teams 具有默认策略配置，旨在确保在部署 Teams 期间，现有业务工作流不会中断。</span><span class="sxs-lookup"><span data-stu-id="26923-117">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="26923-118">默认情况下，向你的用户拨打的 VoIP、PSTN 和联合呼叫将仍路由至 Skype for Business，直到你更新策略以在 Teams 中启用入站通话。</span><span class="sxs-lookup"><span data-stu-id="26923-118">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="26923-119">这可确保在你开始试点和部署 Teams 时，语音服务不会出现意外中断。</span><span class="sxs-lookup"><span data-stu-id="26923-119">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="26923-120">默认情况下，Teams 升级策略处于旧模式，以支持 Teams 互操作性策略确定聊天和通话的路由位置 - Teams 或 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="26923-120">Teams upgrade policy by default is kept at legacy mode that will honor Teams interop policy to determine where chats and calls are to be routed--Teams or Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="26923-121">按照[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)中所述，Teams 升级策略和 Teams 互操作性策略的行为不久将会更改。</span><span class="sxs-lookup"><span data-stu-id="26923-121">The behaviors of Teams upgrade policy and Teams interop policy will soon change as described in [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="26923-122">Teams 互操作性策略具有以下默认配置：</span><span class="sxs-lookup"><span data-stu-id="26923-122">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="26923-123">默认配置的行为如下：</span><span class="sxs-lookup"><span data-stu-id="26923-123">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="26923-124">**对于现有 Skype for Business 客户**，此策略旨在确保 Skype for Business 呼叫定向至 Skype for Business，Teams 呼叫定向至 Teams。</span><span class="sxs-lookup"><span data-stu-id="26923-124">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="26923-125">此策略生效后，PSTN 和联合呼叫将定向至 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="26923-125">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="26923-126">**对于没有 Skype for Business 的客户**，此策略生效后，除了 Teams 用户之间的呼叫外，Teams 中将仅支持出站 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="26923-126">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="26923-127">要在 Teams 接听 PSTN 呼叫，你需要更改为你的用户分配的 Teams 互操作性策略。</span><span class="sxs-lookup"><span data-stu-id="26923-127">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="26923-128">对于预配了用于 Skype for Business Online 的电话系统和通话套餐许可证并且配置了默认全局 Teams 互操作性策略的用户，Teams 中将会启用“通话”选项卡，在无需管理员采取任何管理操作的情况下，他们可以从 Teams 进行出站 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="26923-128">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="26923-129">配置 Teams 以接听入站 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="26923-129">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="26923-130">要在 Teams 中接听入站 PSTN 呼叫，需要应用 Teams 升级策略以及 `CallingDefaultClient` 参数设置为 Teams 的相应 Teams 互操作性策略，以将 Teams 配置为默认通话应用。</span><span class="sxs-lookup"><span data-stu-id="26923-130">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams upgrade policy with the corresponding Teams interop policy that sets `CallingDefaultClient` parameter to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26923-131">我们建议在进行较广范围或组织级别的更改之前，对一组初始用户应用此配置以利用 Teams 中这些令人兴奋的新通话功能。</span><span class="sxs-lookup"><span data-stu-id="26923-131">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="26923-132">如果你选择继续使用旧的 Teams 升级策略，请使用以下预配置的 Teams 互操作性策略以将入站 PSTN 呼叫路由到 Teams：</span><span class="sxs-lookup"><span data-stu-id="26923-132">If you choose to continue to use the legacy Teams upgrade policy, use the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="26923-133">如果你选择使用更新的 Teams 升级策略，则需要为用户分配 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="26923-133">If you choose to use the updated Teams upgrade policy, you need to assign TeamsOnly mode to your users.</span></span>

<span data-ttu-id="26923-134">以上策略的行为如下：</span><span class="sxs-lookup"><span data-stu-id="26923-134">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="26923-135">**对于现有 Skype for Business 客户**，此策略旨在将传入呼叫重定向至 Teams。</span><span class="sxs-lookup"><span data-stu-id="26923-135">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="26923-136">这包括 VoIP（来自 Teams 和 Skype for Business）和 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="26923-136">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> 
* <span data-ttu-id="26923-137">**对于没有 Skype for Business 的客户**，此策略生效后，将在 Teams 中接听 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="26923-137">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="26923-138">当前，将 `CallingDefaultClient` 更改为 Teams 还将影响向 Skype for Business IP 电话拨打的呼叫。</span><span class="sxs-lookup"><span data-stu-id="26923-138">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="26923-139">传入呼叫不会在电话上接收，而只会使 Teams 客户端响铃。</span><span class="sxs-lookup"><span data-stu-id="26923-139">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="26923-140">有关对现有的已认证 SIP 电话的支持的信息，请参阅 [Skype for Business 到 Microsoft Teams 功能路线图](https://aka.ms/skype2teamsroadmap)。</span><span class="sxs-lookup"><span data-stu-id="26923-140">Please consult the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a><span data-ttu-id="26923-141">如何配置用户以在 Teams 中接听 PSTN 通话</span><span class="sxs-lookup"><span data-stu-id="26923-141">How to configure users to receive PSTN calls in Teams</span></span>
<span data-ttu-id="26923-142">使用旧的 Teams 升级策略时，通过 Skype for Business 远程 Windows PowerShell 会话应用上文所述的 Teams 互操作性策略以将呼叫重定向至 Teams：</span><span class="sxs-lookup"><span data-stu-id="26923-142">When using the legacy Teams upgrade policy, apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

<span data-ttu-id="26923-143">如果你选择使用 TeamsOnly 模式，可以通过 Microsoft Teams 和 Skype for Business 管理中心或通过 Skype for Business 远程 Windows PowerShell 会话将用户的共存模式更改为 TeamsOnly 以将呼叫重定向至 Teams：</span><span class="sxs-lookup"><span data-stu-id="26923-143">If you choose to use TeamsOnly mode, you can change the user's coexistence mode to TeamsOnly via Microsoft Teams & Skype for Business Admin Center, or via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a><span data-ttu-id="26923-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26923-144">See also</span></span>
[<span data-ttu-id="26923-145">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="26923-145">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="26923-146">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="26923-146">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="26923-147">Microsoft Teams 中具有通话套餐的电话系统实践指导</span><span class="sxs-lookup"><span data-stu-id="26923-147">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[<span data-ttu-id="26923-148">Skype for Business PowerShell cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="26923-148">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="26923-149">Teams PowerShell cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="26923-149">Teams PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/teams)
