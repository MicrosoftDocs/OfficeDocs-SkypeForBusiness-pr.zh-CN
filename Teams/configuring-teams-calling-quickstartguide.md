---
title: "快速入门指南 - 在 Microsoft Teams 中配置通话套餐"
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
description: "有关在 Microsoft Teams 中配置通话套餐的快速入门指南。"
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f9b266a3ce8d5a151ca608453d7f49821069208
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2018
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="cab5e-103">快速入门指南：在 Microsoft Teams 中配置通话套餐</span><span class="sxs-lookup"><span data-stu-id="cab5e-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="cab5e-104">本指南帮助你安排一组用户并使其能够进行操作，以便他们可以在 Teams 中使用通话套餐。</span><span class="sxs-lookup"><span data-stu-id="cab5e-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="cab5e-105">请参阅 2017 年 12 月 12 日 Teams 中的通话套餐公告：[Teams 中通话功能的下一个阶段是智能通信](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="cab5e-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="cab5e-106">我们建议你与此快速入门指南一起使用[实践指导](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)和 [FastTrack](https://aka.ms/cloudvoice) 来规划和推动成功的部署。</span><span class="sxs-lookup"><span data-stu-id="cab5e-106">We recommend that, in parallel with this quick-start guide, you use our [practical guidance](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="cab5e-107">通过添加由 Skype for Business 提供技术支持的 Office 365 功能 - 通话套餐，现在可以使用 Teams 通过公用电话交换网 (PSTN) 向座机和手机拨打电话，也可以接听来自座机和手机的电话。</span><span class="sxs-lookup"><span data-stu-id="cab5e-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Teams 中的通话功能](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="cab5e-109">在 Teams 中启用**“通话”**选项卡的先决条件</span><span class="sxs-lookup"><span data-stu-id="cab5e-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="cab5e-110">要在 Teams 中启用**“通话”**选项卡，并允许你的用户拨打和接听 PSTN 呼叫，你需要为电话系统和通话套餐预配用户。</span><span class="sxs-lookup"><span data-stu-id="cab5e-110">To enable the **Calls** tab in Teams and allow your users to make and receive PSTN calls, you will need provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="cab5e-111">要了解如何对此进行设置，请参阅[设置通话套餐](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)。</span><span class="sxs-lookup"><span data-stu-id="cab5e-111">To learn how to set this up, read [Set up Calling Plans](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cab5e-112">在 Teams 中配置通话套餐之前，请注意以下限制：</span><span class="sxs-lookup"><span data-stu-id="cab5e-112">Before configuring Calling Plans in Teams, please be aware of the following limitations:</span></span>
> * <span data-ttu-id="cab5e-113">**Teams 不支持混合语音** - Teams 当前不支持混合语音。</span><span class="sxs-lookup"><span data-stu-id="cab5e-113">**Hybrid Voice is not supported in Teams** - Hybrid Voice is currently not supported in Teams.</span></span> <span data-ttu-id="cab5e-114">建议混合语音客户不要为了在 Teams 接听电话而更改任一策略，因为这会导致服务中断。</span><span class="sxs-lookup"><span data-stu-id="cab5e-114">Hybrid Voice customers are not advised to change any of the policies to receive calls in Teams, as this will cause service interruptions.</span></span>
> * <span data-ttu-id="cab5e-115">**Teams 不支持联合呼叫** - Teams 当前不支持联合呼叫（在租户/公司之间呼叫）。</span><span class="sxs-lookup"><span data-stu-id="cab5e-115">**Federated calling is not supported in Teams** - Federated calling (calling between tenants/companies) is currently not supported in Teams.</span></span> <span data-ttu-id="cab5e-116">在 Teams 中支持联合呼叫之前，它们会一直路由到 Skype for Business，无论你如何配置呼叫。</span><span class="sxs-lookup"><span data-stu-id="cab5e-116">Federated calls will always be routed to Skype for Business regardless of how you configure calling, until it's supported in Teams.</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="cab5e-117">Teams 互操作性策略配置</span><span class="sxs-lookup"><span data-stu-id="cab5e-117">Teams interop policy configuration</span></span>
<span data-ttu-id="cab5e-118">为了能够在 Teams 中开始接听呼叫，需要结合使用远程 Windows PowerShell 会话与 Skype for Business [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlet 来更新 Teams 互操作性策略，以将呼叫重定向至 Teams。</span><span class="sxs-lookup"><span data-stu-id="cab5e-118">To enable Teams to begin receiving calls, you'll need to update Teams interop policy, using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span> <span data-ttu-id="cab5e-119">有关 Teams 互操作性策略的详细信息，请参阅 [Microsoft Teams 和 Skype for Business 互操作性](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)。</span><span class="sxs-lookup"><span data-stu-id="cab5e-119">For more information about Teams interop policy, see [Microsoft Teams and Skype for Business Interoperability](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability).</span></span>

> [!TIP]
> <span data-ttu-id="cab5e-120">要查找你所需的 PowerShell cmdlet，请在 [Skype for Business PowerShell cmdlet 文档](https://docs.microsoft.com/powershell/module/skype)中的**“筛选”**框中键入 "CsTeamsInteropPolicy"。</span><span class="sxs-lookup"><span data-stu-id="cab5e-120">To find the PowerShell cmdlets you need, type "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-interop-policy"></a><span data-ttu-id="cab5e-121">默认 Teams 互操作性策略</span><span class="sxs-lookup"><span data-stu-id="cab5e-121">Default Teams interop policy</span></span>
<span data-ttu-id="cab5e-122">Teams 具有默认策略配置，旨在确保在部署 Teams 期间，现有业务工作流不会中断。</span><span class="sxs-lookup"><span data-stu-id="cab5e-122">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="cab5e-123">默认情况下，向你的用户拨打的 VoIP、PSTN 和联合呼叫将仍路由至 Skype for Business，直到你更新策略以在 Teams 中启用入站通话。</span><span class="sxs-lookup"><span data-stu-id="cab5e-123">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="cab5e-124">这可确保在你开始试点和部署 Teams 时，语音服务不会出现意外中断。</span><span class="sxs-lookup"><span data-stu-id="cab5e-124">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="cab5e-125">Teams 互操作性策略具有以下默认配置：</span><span class="sxs-lookup"><span data-stu-id="cab5e-125">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="cab5e-126">默认配置的行为如下：</span><span class="sxs-lookup"><span data-stu-id="cab5e-126">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="cab5e-127">**对于现有 Skype for Business 客户**，此策略旨在确保 Skype for Business 呼叫定向至 Skype for Business，Teams 呼叫定向至 Teams。</span><span class="sxs-lookup"><span data-stu-id="cab5e-127">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="cab5e-128">此策略生效后，PSTN 和联合呼叫将定向至 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="cab5e-128">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="cab5e-129">**对于没有 Skype for Business 的客户**，此策略生效后，除了 Teams 用户之间的呼叫外，Teams 中将仅支持出站 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="cab5e-129">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="cab5e-130">要在 Teams 接听 PSTN 呼叫，你需要更改为你的用户分配的 Teams 互操作性策略。</span><span class="sxs-lookup"><span data-stu-id="cab5e-130">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="cab5e-131">对于预配了用于 Skype for Business Online 的电话系统和通话套餐许可证并且配置了默认全局 Teams 互操作性策略的用户，Teams 中将会启用“通话”选项卡，在无需管理员采取任何管理操作的情况下，他们可以从 Teams 进行出站 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="cab5e-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

#### <a name="how-to-configure-teams-to-use-the-default-policy"></a><span data-ttu-id="cab5e-132">如何配置 Teams 以使用默认策略</span><span class="sxs-lookup"><span data-stu-id="cab5e-132">How to configure Teams to use the default policy</span></span>
<span data-ttu-id="cab5e-133">默认情况下，全局 Teams 互操作性策略应用于你的租户中的所有用户，且该策略配置有默认设置，如上文所述。</span><span class="sxs-lookup"><span data-stu-id="cab5e-133">By default, global Teams interop policy is applied to all users in your tenant, and it is configured with the default settings as described above.</span></span> <span data-ttu-id="cab5e-134">如果由于某种原因，你向你的用户授予了不同的策略，但希望恢复默认设置，则需要通过 Skype for Business 远程 Windows PowerShell 会话应用全局 Teams 互操作性策略：</span><span class="sxs-lookup"><span data-stu-id="cab5e-134">If for some reason you have granted different policies to your users and would like to revert to the default setting, you will need to apply the global Teams interop policy via Skype for Business remote Windows PowerShell session:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName Global -Identity user@contoso.com

> [!WARNING]
> <span data-ttu-id="cab5e-135">虽然可以修改全局 Teams 互操作性策略的默认值，但我们强烈建议不要这么做。</span><span class="sxs-lookup"><span data-stu-id="cab5e-135">While it is possible to modify the global Teams interop policy from the default values, we strongly advise against it.</span></span> 

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="cab5e-136">配置 Teams 以接听入站 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="cab5e-136">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="cab5e-137">要在 Teams 中接听入站 PSTN 呼叫，需要应用 `CallingDefaultClient` 参数设置为 Teams 的 Teams 互操作性策略，以将 Teams 配置为默认通话应用程序。</span><span class="sxs-lookup"><span data-stu-id="cab5e-137">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams interop policy with `CallingDefaultClient` parameter set to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cab5e-138">我们建议在进行较广范围或组织级别的更改之前，对一组初始用户应用此配置以利用 Teams 中这些令人兴奋的新通话功能。</span><span class="sxs-lookup"><span data-stu-id="cab5e-138">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="cab5e-139">请考虑使用以下预配置的 Teams 互操作性策略以将入站 PSTN 呼叫路由至 Teams：</span><span class="sxs-lookup"><span data-stu-id="cab5e-139">Consider using the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="cab5e-140">以上策略的行为如下：</span><span class="sxs-lookup"><span data-stu-id="cab5e-140">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="cab5e-141">**对于现有 Skype for Business 客户**，此策略旨在将传入呼叫重定向至 Teams。</span><span class="sxs-lookup"><span data-stu-id="cab5e-141">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="cab5e-142">这包括 VoIP（来自 Teams 和 Skype for Business）和 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="cab5e-142">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> <span data-ttu-id="cab5e-143">联合呼叫仍将在 Skype for Business 中接听。</span><span class="sxs-lookup"><span data-stu-id="cab5e-143">Federated calls will continue to be received in Skype for Business.</span></span> 
* <span data-ttu-id="cab5e-144">**对于没有 Skype for Business 的客户**，此策略生效后，PSTN 呼叫将在 Teams 中接听。</span><span class="sxs-lookup"><span data-stu-id="cab5e-144">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span> <span data-ttu-id="cab5e-145">Teams 当前**不支持**联合呼叫。</span><span class="sxs-lookup"><span data-stu-id="cab5e-145">Federated calling is currently **not supported** in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="cab5e-146">当前，将 `CallingDefaultClient` 更改为 Teams 还将影响向 Skype for Business IP 电话拨打的呼叫。</span><span class="sxs-lookup"><span data-stu-id="cab5e-146">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="cab5e-147">传入呼叫不会在电话上接收，而只会使 Teams 客户端响铃。</span><span class="sxs-lookup"><span data-stu-id="cab5e-147">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="cab5e-148">有关对现有的已认证 SIP 电话的支持的信息，请参阅 [Skype for Business 到 Microsoft Teams 功能路线图](https://aka.ms/skype2teamsroadmap)。</span><span class="sxs-lookup"><span data-stu-id="cab5e-148">Please consult the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-teams-to-receive-pstn-calls"></a><span data-ttu-id="cab5e-149">如何配置 Teams 以接听 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="cab5e-149">How to configure Teams to receive PSTN calls</span></span>
<span data-ttu-id="cab5e-150">通过 Skype for Business 远程 Windows PowerShell 会话应用上文所述的 Teams 互操作性策略以将呼叫重定向至 Teams：</span><span class="sxs-lookup"><span data-stu-id="cab5e-150">Apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="configuring-teams-to-allow-users-to-change-their-preferred-calling-experience"></a><span data-ttu-id="cab5e-151">配置 Teams 以允许用户更改其首选通话体验</span><span class="sxs-lookup"><span data-stu-id="cab5e-151">Configuring Teams to allow users to change their preferred calling experience</span></span>
<span data-ttu-id="cab5e-152">为了让用户自行决定首选通话体验（在 Teams 中还是在 Skype for Business 中接听呼叫），你需要创建启用 `AllowEndUserClientOverride` 参数的自定义 Teams 互操作性策略。</span><span class="sxs-lookup"><span data-stu-id="cab5e-152">To let users to make their own decision over the preferred calling experience, whether to receive calls in Teams or Skype for Business, you need to create a custom Teams interop policy that enables `AllowEndUserClientOverride` parameter.</span></span>

<span data-ttu-id="cab5e-153">下面是用于支持用户选择首选通话体验的 Teams 互操作性策略示例：</span><span class="sxs-lookup"><span data-stu-id="cab5e-153">The following is the example of Teams interop policy to enable user choice of the preferred calling experience:</span></span>

    Identity                   : Tag:CustomPolicy
    AllowEndUserClientOverride : True
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="cab5e-154">向用户应用此自定义策略后，Teams 客户端中将提供用于更改首选通话应用程序的选项，以便用户自行进行更改。</span><span class="sxs-lookup"><span data-stu-id="cab5e-154">Once this custom policy is applied to the users, the option to change the preferred calling application will be available in Teams client for users to make the changes themselves.</span></span>

![首选通话应用程序选项](media/Preferred_calling_application_option.png)

> [!IMPORTANT]
> <span data-ttu-id="cab5e-156">建议在进行较广范围或组织级别的更改之前，对一组初始用户应用此配置。</span><span class="sxs-lookup"><span data-stu-id="cab5e-156">It is recommended that you apply this configuration to an initial set of users prior to making wider or organization level changes.</span></span>

### <a name="how-to-create-and-apply-the-custom-teams-interop-policy"></a><span data-ttu-id="cab5e-157">如何创建和应用自定义 Teams 互操作性策略</span><span class="sxs-lookup"><span data-stu-id="cab5e-157">How to create and apply the custom Teams interop policy</span></span>
<span data-ttu-id="cab5e-158">要通过 Skype for Business 远程 Windows PowerShell 会话创建上文所述的自定义 Teams 互操作性策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cab5e-158">To create the custom Teams interop policy as described above via Skype for Business remote Windows PowerShell session, perform the following:</span></span>

    New-CsTeamsInteropPolicy -Identity tag:CustomPolicy -AllowEndUserClientOverride:$True -CallingDefaultClient:Default -ChatDefaultClient:Default

    Grant-CsTeamsInteropPolicy -PolicyName tag:CustomPolicy -Identity user@contoso.com



## <a name="see-also"></a><span data-ttu-id="cab5e-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cab5e-159">See also</span></span>
[<span data-ttu-id="cab5e-160">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="cab5e-160">Set up Calling Plans</span></span>](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)

[<span data-ttu-id="cab5e-161">Microsoft Teams 和 Skype for Business 互操作性</span><span class="sxs-lookup"><span data-stu-id="cab5e-161">Microsoft Teams and Skype for Business Interoperability</span></span>](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

[<span data-ttu-id="cab5e-162">Microsoft Teams 中具有通话套餐的电话系统实践指导</span><span class="sxs-lookup"><span data-stu-id="cab5e-162">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[<span data-ttu-id="cab5e-163">Skype for Business PowerShell cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="cab5e-163">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="cab5e-164">Teams PowerShell cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="cab5e-164">Teams PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/teams)
