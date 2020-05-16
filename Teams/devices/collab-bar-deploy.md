---
title: 为 Microsoft 团队部署协作栏
ms.author: mitressl
author: flinchbot
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 阅读本文，了解如何为 Microsoft 团队部署协作栏。
ms.openlocfilehash: 4593d6b42e61efbd7d57f27fd0a10ed8f97b82f5
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268016"
---
# <a name="deploy-collaboration-bars-for-microsoft-teams"></a><span data-ttu-id="b81d7-103">为 Microsoft 团队部署协作栏</span><span class="sxs-lookup"><span data-stu-id="b81d7-103">Deploy collaboration bars for Microsoft Teams</span></span>

<span data-ttu-id="b81d7-104">可将 Microsoft 团队的协作栏部署分为以下阶段：</span><span class="sxs-lookup"><span data-stu-id="b81d7-104">Deployment of collaboration bars for Microsoft Teams can be broken down into the following phases:</span></span>

- <span data-ttu-id="b81d7-105">**网站准备情况**确认部署位置（会议室）满足部署要求。</span><span class="sxs-lookup"><span data-stu-id="b81d7-105">**Site readiness** Confirm that your deployment locations (rooms) meet the deployment requirements.</span></span>
- <span data-ttu-id="b81d7-106">**服务准备情况**创建资源帐户并将其分配给设备（[请参阅使用 Microsoft 365 管理中心创建资源帐户](resource-account-ui.md)）。</span><span class="sxs-lookup"><span data-stu-id="b81d7-106">**Service readiness** Create resource accounts and assign them to the devices ([see Create a resource account using the Microsoft 365 admin center](resource-account-ui.md)).</span></span> <span data-ttu-id="b81d7-107">尽管我们建议使用专用的会议室许可证，但经正确授权的最终用户帐户也可以登录协作栏。</span><span class="sxs-lookup"><span data-stu-id="b81d7-107">While we recommend using a dedicated room license, a properly licensed end user account can also sign in to collaboration bars.</span></span>
- <span data-ttu-id="b81d7-108">**配置和部署**在会议室中设置协作栏并连接所需的外围设备（请参阅协作栏的制造商文档）。</span><span class="sxs-lookup"><span data-stu-id="b81d7-108">**Configuration and deployment** Set up collaboration bars in rooms and connect the peripheral devices you need (see the manufacturer's documentation for your collaboration bars).</span></span>

## <a name="site-readiness"></a><span data-ttu-id="b81d7-109">网站准备情况</span><span class="sxs-lookup"><span data-stu-id="b81d7-109">Site readiness</span></span>

<span data-ttu-id="b81d7-110">当已订购的设备正在发送给你的组织时，请与你的网络、设施和音频视觉团队协作，以确保满足部署要求，并且每个网站和聊天室均可在 power、网络和显示器方面随时准备就绪。</span><span class="sxs-lookup"><span data-stu-id="b81d7-110">While the ordered devices are being delivered to your organization, work with your networking, facilities, and audio-visual teams to make sure that deployment requirements are met and each site and room is ready in terms of power, networking, and display.</span></span>

<span data-ttu-id="b81d7-111">我们针对协作栏网站的建议如下：</span><span class="sxs-lookup"><span data-stu-id="b81d7-111">Our recommendations for collaboration bar sites are:</span></span>

- <span data-ttu-id="b81d7-112">大小最多为4人的会议室</span><span class="sxs-lookup"><span data-stu-id="b81d7-112">Rooms up to 4 people in size</span></span>
- <span data-ttu-id="b81d7-113">专用资源帐户</span><span class="sxs-lookup"><span data-stu-id="b81d7-113">Dedicated resource accounts</span></span>
- <span data-ttu-id="b81d7-114">支持触摸的显示器</span><span class="sxs-lookup"><span data-stu-id="b81d7-114">Touch-enabled displays</span></span>
- <span data-ttu-id="b81d7-115">以太网缆线</span><span class="sxs-lookup"><span data-stu-id="b81d7-115">Ethernet cabling</span></span>
- <span data-ttu-id="b81d7-116">在网络上启用的适用于 Microsoft 团队媒体的服务质量（QoS）</span><span class="sxs-lookup"><span data-stu-id="b81d7-116">Quality of Service (QoS) enabled on the network for Microsoft Teams media</span></span>

<span data-ttu-id="b81d7-117">有关物理安装的注意事项，请参阅制造商的文档，如果有，请在安装和装入屏幕并运行缆线之前，充分利用您的音频视觉团队的体验。</span><span class="sxs-lookup"><span data-stu-id="b81d7-117">For physical installation considerations, see the manufacturer's documentation and, if you have one, leverage the experience of your audio-visual team before you install and mount screens and run cabling.</span></span>

> [!TIP]
> <span data-ttu-id="b81d7-118">请务必查看针对团队进行带宽规划和评估网络对实时流量的适用性的[准备好网络](../prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="b81d7-118">Be sure to check out [Prepare your network for Teams](../prepare-network.md) for bandwidth planning and assessing your network’s suitability for real-time traffic.</span></span>
>
> <span data-ttu-id="b81d7-119">我们不建议在团队设备和 Internet 之间放置代理服务器。</span><span class="sxs-lookup"><span data-stu-id="b81d7-119">We don't recommend placing proxy servers between Teams devices and the Internet.</span></span> <span data-ttu-id="b81d7-120">有关代理服务器和团队的详细信息，请查看[团队的代理服务器](../proxy-servers-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="b81d7-120">For more information about proxy servers and Teams, check out [Proxy servers for Teams](../proxy-servers-for-skype-for-business-online.md).</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="b81d7-122">决策点</span><span class="sxs-lookup"><span data-stu-id="b81d7-122">Decision points</span></span>|<ul><li><span data-ttu-id="b81d7-123">确认您的网站满足 Microsoft 团队协作栏的网站准备情况要求。</span><span class="sxs-lookup"><span data-stu-id="b81d7-123">Confirm that your sites meet the site readiness requirements for collaboration bars for Microsoft Teams.</span></span></li><li><span data-ttu-id="b81d7-124">确认您是否为每个网站都提供了足够的带宽。</span><span class="sxs-lookup"><span data-stu-id="b81d7-124">Confirm that you've provided sufficient bandwidth for each site.</span></span></li></ul>|
| ![描述后续步骤的图标](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="b81d7-126">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b81d7-126">Next steps</span></span>|<ul><li><span data-ttu-id="b81d7-127">开始规划协作栏部署和配置。</span><span class="sxs-lookup"><span data-stu-id="b81d7-127">Start to plan your collaboration bar deployment and configuration.</span></span></li></ul>|

## <a name="service-readiness"></a><span data-ttu-id="b81d7-128">服务就绪</span><span class="sxs-lookup"><span data-stu-id="b81d7-128">Service readiness</span></span>

<span data-ttu-id="b81d7-129">在部署协作栏之前，您需要确定他们是使用 Microsoft 365 资源帐户、最终用户帐户还是同时使用这两者。</span><span class="sxs-lookup"><span data-stu-id="b81d7-129">Before you deploy your collaboration bars, you need to decide if they'll use Microsoft 365 resource accounts, end-user accounts, or a mixture of both.</span></span> <span data-ttu-id="b81d7-130">Microsoft 365 资源帐户是指专用于特定资源（如房间、投影仪等）的邮箱和团队帐户。</span><span class="sxs-lookup"><span data-stu-id="b81d7-130">Microsoft 365 resource accounts are mailbox and Teams accounts that are dedicated to specific resources, such as a room, projector, and so on.</span></span> <span data-ttu-id="b81d7-131">这些资源帐户可以使用在创建规则时定义的规则自动答复会议邀请。</span><span class="sxs-lookup"><span data-stu-id="b81d7-131">These resource accounts can automatically respond to meeting invites using rules you define when they're created.</span></span> <span data-ttu-id="b81d7-132">除非协作栏专用于特定个人供其私人使用，否则我们建议为其设置 Microsoft 365 资源帐户。</span><span class="sxs-lookup"><span data-stu-id="b81d7-132">Unless a collaboration bar is dedicated to a specific individual for their private use, we recommend setting up a Microsoft 365 resource account for it.</span></span>

### <a name="using-a-resource-account"></a><span data-ttu-id="b81d7-133">使用资源帐户</span><span class="sxs-lookup"><span data-stu-id="b81d7-133">Using a resource account</span></span>

<span data-ttu-id="b81d7-134">如果您决定设置 Microsoft 365 资源帐户，您需要为其购买会议室许可证。</span><span class="sxs-lookup"><span data-stu-id="b81d7-134">If you decide to set up a Microsoft 365 resource account, you'll need to purchase a Meeting Room license for it.</span></span> <span data-ttu-id="b81d7-135">会议室许可证包括一个资源邮箱，使组织中的人员可以通过 Outlook 或团队预订会议室。</span><span class="sxs-lookup"><span data-stu-id="b81d7-135">The Meeting Room license includes a resource mailbox that enables people in your organization to book the meeting room via Outlook or Teams.</span></span> <span data-ttu-id="b81d7-136">许可证还支持会议参与者之间的视频和音频会议以及屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="b81d7-136">The license also enables video and audio conferencing and screen sharing among meeting participants.</span></span>

<span data-ttu-id="b81d7-137">如果您需要从外部电话号码接收或拨打电话，您还需要 Microsoft 365 手机系统或 Microsoft 365 商业语音许可证。</span><span class="sxs-lookup"><span data-stu-id="b81d7-137">If you need to receive or make calls to or from an external telephone number, you'll also need a Microsoft 365 Phone System or Microsoft 365 Business Voice license.</span></span>

<span data-ttu-id="b81d7-138">创建资源帐户时，可以选择是让帐户自动接受或拒绝会议请求、允许定期会议、指定提前的人员可以预订资源的进度，等等。</span><span class="sxs-lookup"><span data-stu-id="b81d7-138">When you create a resource account, you can choose whether to let the account automatically accept or decline meeting requests, allow recurring meetings, specify how far in advance people can book the resource, and so on.</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

<span data-ttu-id="b81d7-139">有关 Microsoft 365 资源帐户的协作栏的详细信息，请参阅[使用 microsoft 365 管理中心创建资源帐户](resource-account-ui.md)。</span><span class="sxs-lookup"><span data-stu-id="b81d7-139">For more information about collaboration bars for Microsoft 365 resource accounts, see [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md).</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="b81d7-141">决策点</span><span class="sxs-lookup"><span data-stu-id="b81d7-141">Decision points</span></span>|<ul><li><span data-ttu-id="b81d7-142">确定您是否要拨打或接听外部电话，并确定您的资源帐户的授权要求。</span><span class="sxs-lookup"><span data-stu-id="b81d7-142">Decide whether you want to make or receive external phone calls and identify licensing requirements for your resource accounts.</span></span></li></ul>|
| ![描述后续步骤的图标](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="b81d7-144">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b81d7-144">Next steps</span></span>|<ul><li><span data-ttu-id="b81d7-145">准备资源帐户。</span><span class="sxs-lookup"><span data-stu-id="b81d7-145">Prepare resource accounts.</span></span></li></ul>|

## <a name="configuration-and-deployment"></a><span data-ttu-id="b81d7-146">配置和部署</span><span class="sxs-lookup"><span data-stu-id="b81d7-146">Configuration and deployment</span></span>

<span data-ttu-id="b81d7-147">规划配置和部署涵盖以下主要方面：</span><span class="sxs-lookup"><span data-stu-id="b81d7-147">Planning for configuration and deployment covers the following key areas:</span></span>

- <span data-ttu-id="b81d7-148">资源帐户预配</span><span class="sxs-lookup"><span data-stu-id="b81d7-148">Resource account provisioning</span></span>
- <span data-ttu-id="b81d7-149">设备部署</span><span class="sxs-lookup"><span data-stu-id="b81d7-149">Device deployment</span></span>
- <span data-ttu-id="b81d7-150">Microsoft 团队应用程序和外围设备配置的协作栏</span><span class="sxs-lookup"><span data-stu-id="b81d7-150">Collaboration bars for Microsoft Teams application and peripheral device configuration</span></span>
- <span data-ttu-id="b81d7-151"> 测试</span><span class="sxs-lookup"><span data-stu-id="b81d7-151">Testing</span></span>
- <span data-ttu-id="b81d7-152">资产管理</span><span class="sxs-lookup"><span data-stu-id="b81d7-152">Asset management</span></span>

### <a name="account-provisioning"></a><span data-ttu-id="b81d7-153">帐户预配</span><span class="sxs-lookup"><span data-stu-id="b81d7-153">Account provisioning</span></span>

<span data-ttu-id="b81d7-154">如果您计划使用 Microsoft 365 资源帐户让用户预订协作栏，请按照[使用 microsoft 365 管理中心创建资源帐户](resource-account-ui.md)中的说明为需要其中一个的每个协作栏创建 Microsoft 365 资源帐户。</span><span class="sxs-lookup"><span data-stu-id="b81d7-154">If you plan on using Microsoft 365 resource accounts to let users book collaboration bars, follow the instructions in [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md) to create a Microsoft 365 resource account for each collaboration bar that needs one.</span></span> <span data-ttu-id="b81d7-155">这也是你需要向资源帐户添加会议室许可证的地方，并且如果你想要拨打或接听外部电话号码、电话系统或商业语音许可证的来电，也是如此。</span><span class="sxs-lookup"><span data-stu-id="b81d7-155">This is also where you'll need to add a Meeting Room license to the resource account and, if you want to make or receive calls to or from external phone numbers, a Phone System or Business Voice license.</span></span>

<span data-ttu-id="b81d7-156">如果要为单个用户分配协作栏以供其私人使用，则无需设置任何其他帐户。</span><span class="sxs-lookup"><span data-stu-id="b81d7-156">If you want to assign collaboration bars to individual users for their private use, you don't need to set up any additional accounts.</span></span> <span data-ttu-id="b81d7-157">用户可以使用其个人帐户登录到协作栏。</span><span class="sxs-lookup"><span data-stu-id="b81d7-157">Users can sign into collaboration bars using their personal accounts.</span></span>

> [!TIP]
> <span data-ttu-id="b81d7-158">使您的 Microsoft 365 资源帐户的显示名称易于理解。</span><span class="sxs-lookup"><span data-stu-id="b81d7-158">Make the display names for your Microsoft 365 resource accounts descriptive and easy to understand.</span></span> <span data-ttu-id="b81d7-159">这些是用户在搜索并将 Microsoft 团队的协作栏添加到会议时将看到的名称。</span><span class="sxs-lookup"><span data-stu-id="b81d7-159">These are the names that users will see when searching for and adding collaboration bars for Microsoft Teams to meetings.</span></span> <span data-ttu-id="b81d7-160">你可以使用类似于*网站* - *聊天室名称*（*最大会议室容量*）的约定，因此例如 Curie 在伦敦的4人会议室，可能会有显示名称 LON-Curie （4）。</span><span class="sxs-lookup"><span data-stu-id="b81d7-160">You could use a convention like *Site*-*Room Name*(*Max Room Capacity*), so for example Curie, a 4-person meeting room in London, might have the display name LON-CURIE(4).</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="b81d7-162">决策点</span><span class="sxs-lookup"><span data-stu-id="b81d7-162">Decision points</span></span>|<ul><li><span data-ttu-id="b81d7-163">确定专用资源帐户的命名约定。</span><span class="sxs-lookup"><span data-stu-id="b81d7-163">Decide the naming convention for your dedicated resource accounts.</span></span></li><li><span data-ttu-id="b81d7-164">确定是创建单个帐户还是使用批量预配脚本。</span><span class="sxs-lookup"><span data-stu-id="b81d7-164">Decide whether you’ll create individual accounts or use bulk-provisioning scripts.</span></span></li></ul>|
| ![描述后续步骤的图标](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="b81d7-166">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b81d7-166">Next steps</span></span>|<ul><li><span data-ttu-id="b81d7-167">开始规划设备部署。</span><span class="sxs-lookup"><span data-stu-id="b81d7-167">Start to plan your device deployment.</span></span></li></ul>|

### <a name="device-deployment"></a><span data-ttu-id="b81d7-168">设备部署</span><span class="sxs-lookup"><span data-stu-id="b81d7-168">Device deployment</span></span>

<span data-ttu-id="b81d7-169">接下来，你需要创建你的计划，以便将设备和分配的外围设备交付到你的聊天室，然后继续安装和配置。</span><span class="sxs-lookup"><span data-stu-id="b81d7-169">Next, you need to create your plan to deliver the devices and their assigned peripheral devices to your rooms, and then proceed with installation and configuration.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="b81d7-171">决策点</span><span class="sxs-lookup"><span data-stu-id="b81d7-171">Decision points</span></span>|<ul><li><span data-ttu-id="b81d7-172">确定由谁来管理网站的网站部署。</span><span class="sxs-lookup"><span data-stu-id="b81d7-172">Decide who will manage the site-by-site deployment.</span></span></li><li> <span data-ttu-id="b81d7-173">确定将为 Microsoft 团队网站安装协作栏并执行配置和测试的资源。</span><span class="sxs-lookup"><span data-stu-id="b81d7-173">Identify the resources who will install the collaboration bars for Microsoft Teams on site and undertake the configuration and testing.</span></span></li></ul>|
| ![描述后续步骤的图标](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="b81d7-175">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b81d7-175">Next steps</span></span>|<ul><li><span data-ttu-id="b81d7-176">开始设备测试。</span><span class="sxs-lookup"><span data-stu-id="b81d7-176">Start device testing.</span></span></li></ul>|

### <a name="testing"></a><span data-ttu-id="b81d7-177"> 测试</span><span class="sxs-lookup"><span data-stu-id="b81d7-177">Testing</span></span>

<span data-ttu-id="b81d7-178">部署 Microsoft 团队的协作栏后，应进行测试。</span><span class="sxs-lookup"><span data-stu-id="b81d7-178">After the collaboration bars for Microsoft Teams have been deployed, you should test them.</span></span> <span data-ttu-id="b81d7-179">登录设备，检查所需的功能是否在已部署的设备上工作。</span><span class="sxs-lookup"><span data-stu-id="b81d7-179">Sign in to the device and check that the expected capabilities are working on the deployed device.</span></span> <span data-ttu-id="b81d7-180">强烈建议你验证设备是否显示在 Microsoft 团队管理中心的 "**设备**" 选项卡的 "**协作栏**" 部分中。</span><span class="sxs-lookup"><span data-stu-id="b81d7-180">We highly recommend that you verify that the devices are appearing in the **Collaboration bars** section under the **Devices** tab of Microsoft Teams admin center.</span></span> <span data-ttu-id="b81d7-181">还必须进行大量测试通话和会议才能检查质量和性能。</span><span class="sxs-lookup"><span data-stu-id="b81d7-181">It's also important that you make a number of test calls and meetings to check quality and performance.</span></span>

<span data-ttu-id="b81d7-182">我们建议作为常规 Microsoft 团队推出的一部分，为通话质量仪表板（CQD）配置构建文件，监控质量趋势并参与体验审核流程。</span><span class="sxs-lookup"><span data-stu-id="b81d7-182">We recommend that as part of the general Microsoft Teams rollout, you configure building files for Call Quality Dashboard (CQD), monitor quality trends, and engage in the Quality of Experience Review process.</span></span> <span data-ttu-id="b81d7-183">有关详细信息，请参阅[体验质量检查指南](https://aka.ms/qerguide)。</span><span class="sxs-lookup"><span data-stu-id="b81d7-183">For more information, see the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

### <a name="asset-management"></a><span data-ttu-id="b81d7-184">资产管理</span><span class="sxs-lookup"><span data-stu-id="b81d7-184">Asset management</span></span>

<span data-ttu-id="b81d7-185">作为部署的一部分，您将需要用房间名称、登录资源帐户和分配的外围设备更新您的资产注册。</span><span class="sxs-lookup"><span data-stu-id="b81d7-185">As part of the deployment, you'll want to update your asset register with the room name, signed-in resource account, and assigned peripheral devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b81d7-186">相关主题</span><span class="sxs-lookup"><span data-stu-id="b81d7-186">Related topics</span></span>

[<span data-ttu-id="b81d7-187">使用 Microsoft 团队管理中心为 Microsoft 团队配置协作栏的帐户</span><span class="sxs-lookup"><span data-stu-id="b81d7-187">Configure accounts for collaboration bars for Microsoft Teams using Microsoft Teams admin center</span></span>](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
