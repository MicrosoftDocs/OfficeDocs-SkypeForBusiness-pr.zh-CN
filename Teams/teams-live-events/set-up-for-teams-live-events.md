---
title: 设置中的 Microsoft 团队的实时事件
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: 了解 live 事件中的 Microsoft 团队，准备您的网络，包括分配许可证，启用 live 事件计划的用户，并设置 eCDN 提供商的设置的步骤。
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6fa8e2bc277bbece7dcbd94fca397e219cdf278
ms.sourcegitcommit: 6447a3aa060452c8d6879524cd6a56aecf33b152
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "25354361"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a><span data-ttu-id="07ffe-103">设置中的 Microsoft 团队的实时事件</span><span class="sxs-lookup"><span data-stu-id="07ffe-103">Set up for live events in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

<span data-ttu-id="07ffe-104">Live 事件的设置时, 有以下几个您必须采取的步骤：</span><span class="sxs-lookup"><span data-stu-id="07ffe-104">When you are setting up for live events, there are several steps that you must take:</span></span>

## <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a><span data-ttu-id="07ffe-105">步骤 1： 设置您的网络中的 Microsoft 团队的实时事件</span><span class="sxs-lookup"><span data-stu-id="07ffe-105">Step 1: Set up your network for live events in Microsoft Teams</span></span>
<span data-ttu-id="07ffe-106">快速入门 live 事件要求您[准备贵组织的网络中的 Microsoft 团队](https://docs.microsoft.com/microsoftteams/prepare-network)。</span><span class="sxs-lookup"><span data-stu-id="07ffe-106">The quick start live events require you to [prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network).</span></span>  

## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="07ffe-107">第 2 步：获取和分配许可证</span><span class="sxs-lookup"><span data-stu-id="07ffe-107">Step 2: Get and assign licenses</span></span>
<span data-ttu-id="07ffe-108">确保您具有正确的许可证分配[谁可以创建和安排 live 事件？](#who-can-create-and-schedule-live-events)和[谁可以观看 live 事件？](#who-can-watch-live-events)。</span><span class="sxs-lookup"><span data-stu-id="07ffe-108">Ensure you have correct license assignments for [Who can create and schedule live events?](#who-can-create-and-schedule-live-events) and [Who can watch live events?](#who-can-watch-live-events).</span></span>

## <a name="step-3-enable-live-event-scheduling-for-users"></a><span data-ttu-id="07ffe-109">步骤 3： 启用的用户安排 live 事件</span><span class="sxs-lookup"><span data-stu-id="07ffe-109">Step 3: Enable live event scheduling for users</span></span>
<span data-ttu-id="07ffe-110">默认情况下，为团队用户，但如果您希望用户能够安排外部编码器事件，必须执行其他步骤情况下，启用 live 事件计划。</span><span class="sxs-lookup"><span data-stu-id="07ffe-110">Live event scheduling is enabled by default for Teams users but if you are wanting users to schedule external encoder events there are additional steps that you must do.</span></span>

### <a name="for-quick-start-events"></a><span data-ttu-id="07ffe-111">快速入门事件</span><span class="sxs-lookup"><span data-stu-id="07ffe-111">For quick start events</span></span>
<span data-ttu-id="07ffe-112">用户能否团队在创建 live 事件，或不使用*AllowBroadcastScheduling* **TeamsMeetingBroadcastPolicy**团队 powershell 中设置来控制。</span><span class="sxs-lookup"><span data-stu-id="07ffe-112">Use the setting *AllowBroadcastScheduling* in **TeamsMeetingBroadcastPolicy** in Teams PowerShell to control whether the user can create live events in Teams or not.</span></span> <span data-ttu-id="07ffe-113">您可以了解有关管理 TeamsMeetingBroadcastPolicy[此处](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="07ffe-113">You can learn more about managing TeamsMeetingBroadcastPolicy [here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

 <span data-ttu-id="07ffe-114">如果尚未分配自定义策略分配给用户，用户会收到*全局*策略，具有默认情况下启用录制。</span><span class="sxs-lookup"><span data-stu-id="07ffe-114">If you haven't assigned a custom policy assigned to the users, the users will get the *Global* policy, which has recording enabled by default.</span></span>

<span data-ttu-id="07ffe-115">验证*AllowBroadcastScheduling*参数设置为*True*:</span><span class="sxs-lookup"><span data-stu-id="07ffe-115">Verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="07ffe-116">然后将该用户分配到*全局*策略中，运行：</span><span class="sxs-lookup"><span data-stu-id="07ffe-116">Then assign the user to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

#### <a name="user-scenarios"></a><span data-ttu-id="07ffe-117">用户方案</span><span class="sxs-lookup"><span data-stu-id="07ffe-117">User scenarios</span></span>
<span data-ttu-id="07ffe-118">**您希望能够创建 live 事件，公司内的所有用户。**</span><span class="sxs-lookup"><span data-stu-id="07ffe-118">**You want all users in your company to be able to create live events.**</span></span>

<span data-ttu-id="07ffe-119">如果用户分配*Glocal*策略，运行并验证该*AllowBroadcastScheduling* \* 设置为*True*:</span><span class="sxs-lookup"><span data-stu-id="07ffe-119">If users are assigned the *Glocal* policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="07ffe-120">如果用户分配*全局*策略之外的策略，运行以下命令并验证 *-AllowBroadcastScheduling*设置为*True*:</span><span class="sxs-lookup"><span data-stu-id="07ffe-120">If the users are assigned a policy other than the *Global* policy, run the following and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

<span data-ttu-id="07ffe-121">**您希望 live 事件安排在整个组织为 100%已禁用。**</span><span class="sxs-lookup"><span data-stu-id="07ffe-121">**You want live event scheduling to be 100% disabled across your organization.**</span></span>

<span data-ttu-id="07ffe-122">禁用广播计划，请运行：</span><span class="sxs-lookup"><span data-stu-id="07ffe-122">Disable broadcast scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="07ffe-123">组织中的所有用户都分配*全局*策略，运行：</span><span class="sxs-lookup"><span data-stu-id="07ffe-123">Assign all users in your organization to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="07ffe-124">**您希望大量用户能够创建 live 事件，但希望阻止一组用户创建它们。**</span><span class="sxs-lookup"><span data-stu-id="07ffe-124">**You want a large number of users to be able to create live events, but want to prevent a set of users from creating them.**</span></span>

<span data-ttu-id="07ffe-125">将*全局*策略的用户 （即您希望启用） 的一些使用**授予 CsTeamsMeetingBroadcastPolicy**分配但首先运行以下命令并验证*AllowBroadcastScheduling*设置为*True*:</span><span class="sxs-lookup"><span data-stu-id="07ffe-125">Assign the *Global* policy using the **Grant-CsTeamsMeetingBroadcastPolicy** for some of the users (that you want enabled) but first run the following and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="07ffe-126">然后将一个用户分配到*全局*策略中，运行：</span><span class="sxs-lookup"><span data-stu-id="07ffe-126">Then assign a user or users to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="07ffe-127">创建和分配用于禁用计划使用**授予 CsTeamsMeetingBroadcastPolicy** cmdlet 向其他用户 （您希望禁用） 的策略。</span><span class="sxs-lookup"><span data-stu-id="07ffe-127">Create and assign a policy for disabling scheduling using the  **Grant-CsTeamsMeetingBroadcastPolicy** cmdlet to the other users (you want disabled).</span></span> 

<span data-ttu-id="07ffe-128">创建新策略禁用它，运行：</span><span class="sxs-lookup"><span data-stu-id="07ffe-128">Create the new policy with it disabled, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy
```
<span data-ttu-id="07ffe-129">禁用计划，请运行：</span><span class="sxs-lookup"><span data-stu-id="07ffe-129">Disable scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="07ffe-130">然后将用户分配给此策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="07ffe-130">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
<span data-ttu-id="07ffe-131">**您希望 live 事件要禁用的大量的用户，但希望允许一组用户创建这些。**</span><span class="sxs-lookup"><span data-stu-id="07ffe-131">**You want live events to be disabled for a large number of the users, but want to allow a set of users to create them.**</span></span>

<span data-ttu-id="07ffe-132">禁用广播计划，请运行：</span><span class="sxs-lookup"><span data-stu-id="07ffe-132">Disable broadcast scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="07ffe-133">然后将这些用户分配*全局*策略，运行：</span><span class="sxs-lookup"><span data-stu-id="07ffe-133">Then assign those users to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="07ffe-134">创建和分配策略启用计划，请运行：</span><span class="sxs-lookup"><span data-stu-id="07ffe-134">Create and assign a policy for enabling scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="07ffe-135">启用计划排定，运行：</span><span class="sxs-lookup"><span data-stu-id="07ffe-135">Enable scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="07ffe-136">然后将用户分配给此策略，请运行：</span><span class="sxs-lookup"><span data-stu-id="07ffe-136">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

### <a name="for-external-encoder-events"></a><span data-ttu-id="07ffe-137">外部编码器事件</span><span class="sxs-lookup"><span data-stu-id="07ffe-137">For external encoder events</span></span>
<span data-ttu-id="07ffe-138">您必须执行以下操作以启用实时计划为这些用户的事件。</span><span class="sxs-lookup"><span data-stu-id="07ffe-138">You must do the following to enable live event scheduling for those users.</span></span>

#### <a name="step-1-enable-microsoft-stream-for-users-in-your-organization"></a><span data-ttu-id="07ffe-139">步骤 1： 在您的组织 \* \* 中为用户启用 Microsoft 流</span><span class="sxs-lookup"><span data-stu-id="07ffe-139">Step 1: Enable Microsoft Stream for users in your organization\*\*</span></span>
<span data-ttu-id="07ffe-140">Microsoft 流是可用的合格的 Office 365 订阅一部分或作为独立的服务。</span><span class="sxs-lookup"><span data-stu-id="07ffe-140">Microsoft Stream is available as part of eligible Office 365 subscriptions or as a standalone service.</span></span> <span data-ttu-id="07ffe-141">有关详细信息，请参阅[流许可概述](https://docs.microsoft.com/stream/license-overview)。</span><span class="sxs-lookup"><span data-stu-id="07ffe-141">See [Stream licensing overview](https://docs.microsoft.com/stream/license-overview) for more details.</span></span>

> <span data-ttu-id="07ffe-142">![注意]业务 Essentials 或企业高级版计划中不包含 Microsoft 流。</span><span class="sxs-lookup"><span data-stu-id="07ffe-142">![NOTE] Microsoft Stream is not included in Business Essentials or Business Premium plans.</span></span>  

<span data-ttu-id="07ffe-143">了解有关如何可以[分配给 Office 365 中的用户的许可证](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC)，以便用户可以访问 Microsoft 流。</span><span class="sxs-lookup"><span data-stu-id="07ffe-143">Learn more about how you can [assign licenses to users in Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) so that users can access Microsoft Stream.</span></span> <span data-ttu-id="07ffe-144">确保 Microsoft 流的用户不进行阻止，如[本文](https://docs.microsoft.com/stream/disable-user-organization)中所定义。</span><span class="sxs-lookup"><span data-stu-id="07ffe-144">Ensure Microsoft Stream is not blocked for the users as defined in [this article](https://docs.microsoft.com/stream/disable-user-organization).</span></span>

#### <a name="step-2-ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a><span data-ttu-id="07ffe-145">步骤 2： 确保用户具有 live 事件创建权限中 Microsoft 流 \* \*</span><span class="sxs-lookup"><span data-stu-id="07ffe-145">Step 2: Ensure users have live event creation permission in Microsoft Stream\*\*</span></span>
<span data-ttu-id="07ffe-146">默认情况下，管理员可以创建外部编码器 live 事件。</span><span class="sxs-lookup"><span data-stu-id="07ffe-146">By default, administrators can create external encoder live events.</span></span> <span data-ttu-id="07ffe-147">Microsoft 流管理员可以流中[启用 live 事件创建的其他用户](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating)。</span><span class="sxs-lookup"><span data-stu-id="07ffe-147">Microsoft Stream administrator can [enable additional users for live event creation](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) in Stream.</span></span>  

#### <a name="step-3-ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a><span data-ttu-id="07ffe-148">步骤 3： 确保组织者同意设置流管理员 \* \* 的公司策略的实时事件</span><span class="sxs-lookup"><span data-stu-id="07ffe-148">Step 3: Ensure live event organizers have consented to the company policy set by Stream admin\*\*</span></span>
<span data-ttu-id="07ffe-149">如果 Microsoft 流管理员[设置的公司准则策略](https://docs.microsoft.com/stream/company-policy-and-consent)并要求员工保存内容之前接受此策略，然后用户必须这样做团队在创建 （具有外部编码器生产） 的实时事件之前。</span><span class="sxs-lookup"><span data-stu-id="07ffe-149">If a Microsoft Stream administrator has [set up a company guidelines policy](https://docs.microsoft.com/stream/company-policy-and-consent) and requires employees to accept this policy before saving content, then users must do so before creating a live event (with External Encoder production) in Teams.</span></span> <span data-ttu-id="07ffe-150">之前您推出组织中的实时事件功能，请确保将创建这些 live 事件的用户同意策略。</span><span class="sxs-lookup"><span data-stu-id="07ffe-150">Before you rollout the live events feature in the organization, make sure users who will be creating these live events have consented to the policy.</span></span> 

## <a name="step-4-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a><span data-ttu-id="07ffe-151">步骤 4： 设置 eCDN 提供程序中的 Microsoft 团队的实时事件</span><span class="sxs-lookup"><span data-stu-id="07ffe-151">Step 4: Set up eCDN provider for live events in Microsoft Teams</span></span> 
<span data-ttu-id="07ffe-152">Live 事件视频播放使用流式处理 (ABR) 的自适应比特率，但它并单播流，这意味着每个查看器从 internet 获取其自己的视频流。</span><span class="sxs-lookup"><span data-stu-id="07ffe-152">Playback of live event videos uses adaptive bitrate streaming (ABR) but it is a unicast stream, meaning every viewer is getting their own video stream from the internet.</span></span> <span data-ttu-id="07ffe-153">对于 live 事件或发送到您的组织的大部分内容的视频，可能有大量的 internet 带宽使用查看器。</span><span class="sxs-lookup"><span data-stu-id="07ffe-153">For live events or videos sent out to large portions of your organization, there could be a significant amount of internet bandwidth consumed by viewers.</span></span> <span data-ttu-id="07ffe-154">对于希望减少 live 事件此 internet 通信的组织，与 Microsoft 的集成解决方案的实时事件受信任提供软件的视频传送合作伙伴定义网络 (SDNs) 或企业内容交付网络 (eCDNs)。</span><span class="sxs-lookup"><span data-stu-id="07ffe-154">For organizations that want to reduce this internet traffic for live events, live events solutions are integrated with Microsoft's trusted video delivery partners offering software defined networks (SDNs) or enterprise content delivery networks (eCDNs).</span></span> <span data-ttu-id="07ffe-155">这些 SDN / eCDN 平台启用组织牺牲最终用户查看体验的情况下优化网络带宽。</span><span class="sxs-lookup"><span data-stu-id="07ffe-155">These SDN / eCDN platforms enable organizations to optimize network bandwidth without sacrificing end user viewing experiences.</span></span> <span data-ttu-id="07ffe-156">我们的合作伙伴可帮助您在企业网络中启用多可扩展且高效的视频分布。</span><span class="sxs-lookup"><span data-stu-id="07ffe-156">Our partners can help enable a more scalable and efficient video distribution across your enterprise network.</span></span>

<span data-ttu-id="07ffe-157">**购买和安装您的解决方案的 Microsoft 团队之外**获取与通过利用 Microsoft 的受信任的视频传送合作伙伴缩放视频传递专家的帮助。</span><span class="sxs-lookup"><span data-stu-id="07ffe-157">**Purchase & setup your solution outside of Microsoft Teams** Get expert help with scaling video delivery by leveraging Microsoft’s trusted video delivery partners.</span></span> <span data-ttu-id="07ffe-158">启用与团队一起使用的视频传输提供程序之前，您必须购买和安装 SDN/eCDN 解决方案外部和分开团队。</span><span class="sxs-lookup"><span data-stu-id="07ffe-158">Before you can enable a video delivery provider to be used with Teams you must purchase and setup the SDN/eCDN solution outside and separate from Teams.</span></span>

<span data-ttu-id="07ffe-159">以下 SDN/eCDN 解决方案前集成，可以为安装程序将与 Microsoft 流一起使用。</span><span class="sxs-lookup"><span data-stu-id="07ffe-159">The following SDN/eCDN solutions are pre-integrated and can be setup to be used with Microsoft Stream.</span></span>

- <span data-ttu-id="07ffe-160">**配置单元流式处理**提供 live 和点播企业视频分布的简单且强大的解决方案。</span><span class="sxs-lookup"><span data-stu-id="07ffe-160">**Hive Streaming** provides a simple and powerful solution for live and on-demand enterprise video distribution.</span></span> <span data-ttu-id="07ffe-161">配置单元是一种基于软件的解决方案，不需要额外的硬件或带宽，并提供了一种启用数千个并发视频查看器，而不会影响您的网络安全方法。</span><span class="sxs-lookup"><span data-stu-id="07ffe-161">Hive is a software-based solution that requires no additional hardware or bandwidth and provides a secure way to enable thousands of simultaneous video viewers without impact to your network.</span></span> <span data-ttu-id="07ffe-162">对于希望了解影响视频具有其购买 SDN/eCDN 解决方案之前的网络上的客户，配置单元流还提供基于浏览器的分析解决方案的 Microsoft 客户。</span><span class="sxs-lookup"><span data-stu-id="07ffe-162">For customers looking to understand the impact video is having on their network prior to purchasing an SDN/eCDN solution, Hive Streaming also provides a browser-based analytics solution for Microsoft customers.</span></span> <span data-ttu-id="07ffe-163">[了解更多](https://www.hivestreaming.com/partners/integration-partners/microsoft/)。</span><span class="sxs-lookup"><span data-stu-id="07ffe-163">[Learn more](https://www.hivestreaming.com/partners/integration-partners/microsoft/).</span></span>
 
- <span data-ttu-id="07ffe-164">**Kollective**是一个基于云的、 智能对等分发平台，利用您现有的网络基础结构来提供多个窗体中的内容，、 (live 视频流，按需视频、 软件更新、 安全修补程序，等等) 更快、 更多可靠地及较少的带宽。</span><span class="sxs-lookup"><span data-stu-id="07ffe-164">**Kollective** is a cloud-based, smart peering distribution platform that leverages your existing network infrastructure to deliver content, in many forms, (live streaming video, on-demand video, software updates, security patches, etc.) faster, more reliably and with less bandwidth.</span></span> <span data-ttu-id="07ffe-165">我们安全平台是受信任的世界最大金融机构及任何其他硬件、 设置和维护很容易。</span><span class="sxs-lookup"><span data-stu-id="07ffe-165">Our secure platform is trusted by the world’s largest financial institutions and with no additional hardware, setup and maintenance are easy.</span></span> <span data-ttu-id="07ffe-166">[了解更多](http://www.kollective.com)。</span><span class="sxs-lookup"><span data-stu-id="07ffe-166">[Learn more](http://www.kollective.com).</span></span>
 
- <span data-ttu-id="07ffe-167">**提升 OmniCache**提供下一代网络通讯组和跨全局 Wan 确保视频内容的无缝传递，帮助事件生产者优化网络带宽和支持成功 live 事件广播和按需流式处理。</span><span class="sxs-lookup"><span data-stu-id="07ffe-167">**Ramp OmniCache** provides next-generation network distribution and ensures seamless delivery of video content across global WANs, helping event producers optimize network bandwidth and support successful live event broadcasts and on-demand streaming.</span></span> <span data-ttu-id="07ffe-168">快速入门 live 事件提升 OmniCache 支持即将提供。</span><span class="sxs-lookup"><span data-stu-id="07ffe-168">The support for Ramp OmniCache for quick start live events is coming soon.</span></span>  <span data-ttu-id="07ffe-169">[了解更多](http://www.ramp.com)。</span><span class="sxs-lookup"><span data-stu-id="07ffe-169">[Learn more](http://www.ramp.com).</span></span> 
 
> [!NOTE] 
> <span data-ttu-id="07ffe-170">选的 eCDN 解决方案受制于所选**的服务和隐私策略的第三方提供程序的条款**，哪些将控制您使用 eCDN 提供程序的解决方案。</span><span class="sxs-lookup"><span data-stu-id="07ffe-170">Your chosen eCDN solution is subject to the selected **3rd party provider’s terms of service and privacy policy**, which will governs your use of the eCDN provider’s solution.</span></span> <span data-ttu-id="07ffe-171">您使用 eCDN 提供程序的解决方案不会受到的 Microsoft 批量许可条款或联机服务条款。</span><span class="sxs-lookup"><span data-stu-id="07ffe-171">Your use of the eCDN provider’s solution will not be subject to the Microsoft volume licensing terms or Online Services Terms.</span></span> <span data-ttu-id="07ffe-172">如果您不同意**第三方提供程序的术语**，然后不启用团队中的 eCDN 解决方案。</span><span class="sxs-lookup"><span data-stu-id="07ffe-172">If you do not agree to the **3rd party provider’s terms**, then don't enable the eCDN solution in Teams.</span></span> 

<span data-ttu-id="07ffe-173">**设置为"快速启动"eCDN live 事件**使用 PowerShell 团队中，您可以配置 live 事件 eCDN 提供程序。</span><span class="sxs-lookup"><span data-stu-id="07ffe-173">**Set up an eCDN for "Quick start" live events** You can configure eCDN provider for live events in Teams using PowerShell.</span></span> 

> [!NOTE] 
> <span data-ttu-id="07ffe-174">可以为组织配置的单个 eCDN 提供程序。</span><span class="sxs-lookup"><span data-stu-id="07ffe-174">A single eCDN provider can be configured for your organization.</span></span> 

<span data-ttu-id="07ffe-175">***配置单元***您可以使用[集 CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell cmdlet 配置 eCDN 提供程序。</span><span class="sxs-lookup"><span data-stu-id="07ffe-175">***Hive*** You can use [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell cmdlet to configure eCDN provider.</span></span> <span data-ttu-id="07ffe-176">首先获取来自您配置单元联系人，然后运行以下许可证 ID 和 API 模板 URL:</span><span class="sxs-lookup"><span data-stu-id="07ffe-176">First obtain the license ID and API template URL from your Hive contact then run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="07ffe-177">***Kollective***您可以使用[集 CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell cmdlet 配置 eCDN 提供程序。</span><span class="sxs-lookup"><span data-stu-id="07ffe-177">***Kollective*** You can use [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell cmdlet to configure eCDN provider.</span></span> <span data-ttu-id="07ffe-178">首先获取 API 令牌和 API 模板 URL 从 Kollective 联系人，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="07ffe-178">First obtain the API token and the API template URL from your Kollective contact, then run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="07ffe-179">**设置为"外部编码器"live 事件 eCDN**</span><span class="sxs-lookup"><span data-stu-id="07ffe-179">**Set up an eCDN for "External encoder" live events**</span></span> 

<span data-ttu-id="07ffe-180">如果您计划来创建使用外部编码器的实时事件，您将需要以及[配置与 Microsoft 流您 eCDN 提供商](https://docs.microsoft.com/stream/network-caching)。</span><span class="sxs-lookup"><span data-stu-id="07ffe-180">If you plan to create live events that use external encoders, you will need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching) as well.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="07ffe-181">后续步骤</span><span class="sxs-lookup"><span data-stu-id="07ffe-181">Next steps</span></span>
<span data-ttu-id="07ffe-182">转到[配置团队 live 事件](configure-teams-live-events.md)。</span><span class="sxs-lookup"><span data-stu-id="07ffe-182">Go to [Confgure Teams live events](configure-teams-live-events.md).</span></span>
