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
ms.openlocfilehash: 41eb3335eef78f1da2c64b1df65443ba93d40159
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962903"
---
# <a name="deploy-collaboration-bars-for-microsoft-teams"></a><span data-ttu-id="2b74b-103">为 Microsoft 团队部署协作栏</span><span class="sxs-lookup"><span data-stu-id="2b74b-103">Deploy collaboration bars for Microsoft Teams</span></span>

<span data-ttu-id="2b74b-104">可将 Microsoft 团队的协作栏部署分为以下阶段：</span><span class="sxs-lookup"><span data-stu-id="2b74b-104">Deployment of collaboration bars for Microsoft Teams can be broken down into the following phases:</span></span>

- <span data-ttu-id="2b74b-105">**网站准备情况** 确认部署位置 (会议室) 满足部署要求。</span><span class="sxs-lookup"><span data-stu-id="2b74b-105">**Site readiness** Confirm that your deployment locations (rooms) meet the deployment requirements.</span></span>
- <span data-ttu-id="2b74b-106">**服务准备情况** 创建资源帐户并将其分配到 "设备" ([请参阅使用 Microsoft 365 管理中心) 创建资源帐户](resource-account-ui.md) 。</span><span class="sxs-lookup"><span data-stu-id="2b74b-106">**Service readiness** Create resource accounts and assign them to the devices ([see Create a resource account using the Microsoft 365 admin center](resource-account-ui.md)).</span></span> <span data-ttu-id="2b74b-107">尽管我们建议使用专用的会议室许可证，但经正确授权的最终用户帐户也可以登录协作栏。</span><span class="sxs-lookup"><span data-stu-id="2b74b-107">While we recommend using a dedicated room license, a properly licensed end user account can also sign in to collaboration bars.</span></span>
- <span data-ttu-id="2b74b-108">**配置和部署** 在会议室中设置协作栏并连接所需的外围设备 (请参阅协作栏) 的制造商文档。</span><span class="sxs-lookup"><span data-stu-id="2b74b-108">**Configuration and deployment** Set up collaboration bars in rooms and connect the peripheral devices you need (see the manufacturer's documentation for your collaboration bars).</span></span>

<span data-ttu-id="2b74b-109">若要管理协作栏，您必须是全局管理员、团队服务管理员或团队设备管理员。有关管理员角色的详细信息，请参阅 [使用 Microsoft 团队管理员角色管理团队](../using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="2b74b-109">To manage collaboration bars, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

## <a name="site-readiness"></a><span data-ttu-id="2b74b-110">网站准备情况</span><span class="sxs-lookup"><span data-stu-id="2b74b-110">Site readiness</span></span>

<span data-ttu-id="2b74b-111">当已订购的设备正在发送给你的组织时，请与你的网络、设施和音频视觉团队协作，以确保满足部署要求，并且每个网站和聊天室均可在 power、网络和显示器方面随时准备就绪。</span><span class="sxs-lookup"><span data-stu-id="2b74b-111">While the ordered devices are being delivered to your organization, work with your networking, facilities, and audio-visual teams to make sure that deployment requirements are met and each site and room is ready in terms of power, networking, and display.</span></span>

<span data-ttu-id="2b74b-112">我们针对协作栏网站的建议如下：</span><span class="sxs-lookup"><span data-stu-id="2b74b-112">Our recommendations for collaboration bar sites are:</span></span>

- <span data-ttu-id="2b74b-113">大小最多为4人的会议室</span><span class="sxs-lookup"><span data-stu-id="2b74b-113">Rooms up to 4 people in size</span></span>
- <span data-ttu-id="2b74b-114">专用资源帐户</span><span class="sxs-lookup"><span data-stu-id="2b74b-114">Dedicated resource accounts</span></span>
- <span data-ttu-id="2b74b-115">支持触摸的显示器</span><span class="sxs-lookup"><span data-stu-id="2b74b-115">Touch-enabled displays</span></span>
- <span data-ttu-id="2b74b-116">以太网缆线</span><span class="sxs-lookup"><span data-stu-id="2b74b-116">Ethernet cabling</span></span>
- <span data-ttu-id="2b74b-117">Microsoft 团队媒体网络上启用的服务质量 (QoS) </span><span class="sxs-lookup"><span data-stu-id="2b74b-117">Quality of Service (QoS) enabled on the network for Microsoft Teams media</span></span>

<span data-ttu-id="2b74b-118">有关物理安装的注意事项，请参阅制造商的文档，如果有，请在安装和装入屏幕并运行缆线之前，充分利用您的音频视觉团队的体验。</span><span class="sxs-lookup"><span data-stu-id="2b74b-118">For physical installation considerations, see the manufacturer's documentation and, if you have one, leverage the experience of your audio-visual team before you install and mount screens and run cabling.</span></span>

> [!TIP]
> <span data-ttu-id="2b74b-119">请务必查看针对团队进行带宽规划和评估网络对实时流量的适用性的 [准备好网络](../prepare-network.md) 。</span><span class="sxs-lookup"><span data-stu-id="2b74b-119">Be sure to check out [Prepare your network for Teams](../prepare-network.md) for bandwidth planning and assessing your network’s suitability for real-time traffic.</span></span>
>
> <span data-ttu-id="2b74b-120">我们不建议在团队设备和 Internet 之间放置代理服务器。</span><span class="sxs-lookup"><span data-stu-id="2b74b-120">We don't recommend placing proxy servers between Teams devices and the Internet.</span></span> <span data-ttu-id="2b74b-121">有关代理服务器和团队的详细信息，请查看 [团队的代理服务器](../proxy-servers-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="2b74b-121">For more information about proxy servers and Teams, check out [Proxy servers for Teams](../proxy-servers-for-skype-for-business-online.md).</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="2b74b-123">决策点</span><span class="sxs-lookup"><span data-stu-id="2b74b-123">Decision points</span></span>|<ul><li><span data-ttu-id="2b74b-124">确认您的网站满足 Microsoft 团队协作栏的网站准备情况要求。</span><span class="sxs-lookup"><span data-stu-id="2b74b-124">Confirm that your sites meet the site readiness requirements for collaboration bars for Microsoft Teams.</span></span></li><li><span data-ttu-id="2b74b-125">确认您是否为每个网站都提供了足够的带宽。</span><span class="sxs-lookup"><span data-stu-id="2b74b-125">Confirm that you've provided sufficient bandwidth for each site.</span></span></li></ul>|
| ![描述后续步骤的图标](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="2b74b-127">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2b74b-127">Next steps</span></span>|<ul><li><span data-ttu-id="2b74b-128">开始规划协作栏部署和配置。</span><span class="sxs-lookup"><span data-stu-id="2b74b-128">Start to plan your collaboration bar deployment and configuration.</span></span></li></ul>|

## <a name="service-readiness"></a><span data-ttu-id="2b74b-129">服务就绪</span><span class="sxs-lookup"><span data-stu-id="2b74b-129">Service readiness</span></span>

<span data-ttu-id="2b74b-130">在部署协作栏之前，您需要确定他们是使用 Microsoft 365 资源帐户、最终用户帐户还是同时使用这两者。</span><span class="sxs-lookup"><span data-stu-id="2b74b-130">Before you deploy your collaboration bars, you need to decide if they'll use Microsoft 365 resource accounts, end-user accounts, or a mixture of both.</span></span> <span data-ttu-id="2b74b-131">Microsoft 365 资源帐户是指专用于特定资源（如房间、投影仪等）的邮箱和团队帐户。</span><span class="sxs-lookup"><span data-stu-id="2b74b-131">Microsoft 365 resource accounts are mailbox and Teams accounts that are dedicated to specific resources, such as a room, projector, and so on.</span></span> <span data-ttu-id="2b74b-132">这些资源帐户可以使用在创建规则时定义的规则自动答复会议邀请。</span><span class="sxs-lookup"><span data-stu-id="2b74b-132">These resource accounts can automatically respond to meeting invites using rules you define when they're created.</span></span> <span data-ttu-id="2b74b-133">除非协作栏专用于特定个人供其私人使用，否则我们建议为其设置 Microsoft 365 资源帐户。</span><span class="sxs-lookup"><span data-stu-id="2b74b-133">Unless a collaboration bar is dedicated to a specific individual for their private use, we recommend setting up a Microsoft 365 resource account for it.</span></span>

### <a name="using-a-resource-account"></a><span data-ttu-id="2b74b-134">使用资源帐户</span><span class="sxs-lookup"><span data-stu-id="2b74b-134">Using a resource account</span></span>

<span data-ttu-id="2b74b-135">如果您决定设置 Microsoft 365 资源帐户，您需要为其购买会议室许可证。</span><span class="sxs-lookup"><span data-stu-id="2b74b-135">If you decide to set up a Microsoft 365 resource account, you'll need to purchase a Meeting Room license for it.</span></span> <span data-ttu-id="2b74b-136">会议室许可证包括一个资源邮箱，使组织中的人员可以通过 Outlook 或团队预订会议室。</span><span class="sxs-lookup"><span data-stu-id="2b74b-136">The Meeting Room license includes a resource mailbox that enables people in your organization to book the meeting room via Outlook or Teams.</span></span> <span data-ttu-id="2b74b-137">许可证还支持会议参与者之间的视频和音频会议以及屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="2b74b-137">The license also enables video and audio conferencing and screen sharing among meeting participants.</span></span>

<span data-ttu-id="2b74b-138">如果您需要接收或拨出外部电话号码，您可能需要一个呼叫计划或 Microsoft 365 Business Voice [附加设备许可证](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business)。</span><span class="sxs-lookup"><span data-stu-id="2b74b-138">If you need to receive or make calls to or from an external telephone number, you may need a Calling Plan or Microsoft 365 Business Voice [add-on license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business).</span></span> <span data-ttu-id="2b74b-139">如果您的组织中已启用直接路由，则只需要会议室 SKU。</span><span class="sxs-lookup"><span data-stu-id="2b74b-139">If you have Direct Routing enabled in your organization, you only need the Meeting Room SKU.</span></span>

<span data-ttu-id="2b74b-140">创建资源帐户时，可以选择是让帐户自动接受或拒绝会议请求、允许定期会议、指定提前的人员可以预订资源的进度，等等。</span><span class="sxs-lookup"><span data-stu-id="2b74b-140">When you create a resource account, you can choose whether to let the account automatically accept or decline meeting requests, allow recurring meetings, specify how far in advance people can book the resource, and so on.</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

<span data-ttu-id="2b74b-141">有关 Microsoft 365 资源帐户的协作栏的详细信息，请参阅 [使用 microsoft 365 管理中心创建资源帐户](resource-account-ui.md)。</span><span class="sxs-lookup"><span data-stu-id="2b74b-141">For more information about collaboration bars for Microsoft 365 resource accounts, see [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md).</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="2b74b-143">决策点</span><span class="sxs-lookup"><span data-stu-id="2b74b-143">Decision points</span></span>|<ul><li><span data-ttu-id="2b74b-144">确定您是否要拨打或接听外部电话，并确定您的资源帐户的授权要求。</span><span class="sxs-lookup"><span data-stu-id="2b74b-144">Decide whether you want to make or receive external phone calls and identify licensing requirements for your resource accounts.</span></span></li></ul>|
| ![描述后续步骤的图标](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="2b74b-146">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2b74b-146">Next steps</span></span>|<ul><li><span data-ttu-id="2b74b-147">准备资源帐户。</span><span class="sxs-lookup"><span data-stu-id="2b74b-147">Prepare resource accounts.</span></span></li></ul>|

## <a name="configuration-and-deployment"></a><span data-ttu-id="2b74b-148">配置和部署</span><span class="sxs-lookup"><span data-stu-id="2b74b-148">Configuration and deployment</span></span>

<span data-ttu-id="2b74b-149">规划配置和部署涵盖以下主要方面：</span><span class="sxs-lookup"><span data-stu-id="2b74b-149">Planning for configuration and deployment covers the following key areas:</span></span>

- <span data-ttu-id="2b74b-150">资源帐户预配</span><span class="sxs-lookup"><span data-stu-id="2b74b-150">Resource account provisioning</span></span>
- <span data-ttu-id="2b74b-151">设备部署</span><span class="sxs-lookup"><span data-stu-id="2b74b-151">Device deployment</span></span>
- <span data-ttu-id="2b74b-152">Microsoft 团队应用程序和外围设备配置的协作栏</span><span class="sxs-lookup"><span data-stu-id="2b74b-152">Collaboration bars for Microsoft Teams application and peripheral device configuration</span></span>
- <span data-ttu-id="2b74b-153"> 测试</span><span class="sxs-lookup"><span data-stu-id="2b74b-153">Testing</span></span>
- <span data-ttu-id="2b74b-154">资产管理</span><span class="sxs-lookup"><span data-stu-id="2b74b-154">Asset management</span></span>

### <a name="account-provisioning"></a><span data-ttu-id="2b74b-155">帐户预配</span><span class="sxs-lookup"><span data-stu-id="2b74b-155">Account provisioning</span></span>

<span data-ttu-id="2b74b-156">如果您计划使用 Microsoft 365 资源帐户让用户预订协作栏，请按照 [使用 microsoft 365 管理中心创建资源帐户](resource-account-ui.md) 中的说明为需要其中一个的每个协作栏创建 Microsoft 365 资源帐户。</span><span class="sxs-lookup"><span data-stu-id="2b74b-156">If you plan on using Microsoft 365 resource accounts to let users book collaboration bars, follow the instructions in [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md) to create a Microsoft 365 resource account for each collaboration bar that needs one.</span></span> <span data-ttu-id="2b74b-157">这也是你需要向资源帐户添加会议室许可证的地方，如果你想要在你的组织未使用直接路由的情况下拨打或接听外部电话号码、呼叫计划或商业语音许可证，请使用呼叫计划或商业语音许可证。</span><span class="sxs-lookup"><span data-stu-id="2b74b-157">This is also where you'll need to add a Meeting Room license to the resource account and, if you want to make or receive calls to or from external phone numbers, a Calling Plan or Business Voice license if your organization is not using Direct Routing.</span></span>

<span data-ttu-id="2b74b-158">如果要为单个用户分配协作栏以供其私人使用，则无需设置任何其他帐户。</span><span class="sxs-lookup"><span data-stu-id="2b74b-158">If you want to assign collaboration bars to individual users for their private use, you don't need to set up any additional accounts.</span></span> <span data-ttu-id="2b74b-159">用户可以使用其个人帐户登录到协作栏。</span><span class="sxs-lookup"><span data-stu-id="2b74b-159">Users can sign into collaboration bars using their personal accounts.</span></span>

> [!TIP]
> <span data-ttu-id="2b74b-160">使您的 Microsoft 365 资源帐户的显示名称易于理解。</span><span class="sxs-lookup"><span data-stu-id="2b74b-160">Make the display names for your Microsoft 365 resource accounts descriptive and easy to understand.</span></span> <span data-ttu-id="2b74b-161">这些是用户在搜索并将 Microsoft 团队的协作栏添加到会议时将看到的名称。</span><span class="sxs-lookup"><span data-stu-id="2b74b-161">These are the names that users will see when searching for and adding collaboration bars for Microsoft Teams to meetings.</span></span> <span data-ttu-id="2b74b-162">你可以使用类似于*网站* - *聊天室名称*的约定 (*最大会议室的容量*) ，因此，例如，在伦敦的4人会议室中，可能会有显示名称 LON-Curie (4) 。</span><span class="sxs-lookup"><span data-stu-id="2b74b-162">You could use a convention like *Site*-*Room Name*(*Max Room Capacity*), so for example Curie, a 4-person meeting room in London, might have the display name LON-CURIE(4).</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="2b74b-164">决策点</span><span class="sxs-lookup"><span data-stu-id="2b74b-164">Decision points</span></span>|<ul><li><span data-ttu-id="2b74b-165">确定专用资源帐户的命名约定。</span><span class="sxs-lookup"><span data-stu-id="2b74b-165">Decide the naming convention for your dedicated resource accounts.</span></span></li><li><span data-ttu-id="2b74b-166">确定是创建单个帐户还是使用批量预配脚本。</span><span class="sxs-lookup"><span data-stu-id="2b74b-166">Decide whether you’ll create individual accounts or use bulk-provisioning scripts.</span></span></li></ul>|
| ![描述后续步骤的图标](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="2b74b-168">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2b74b-168">Next steps</span></span>|<ul><li><span data-ttu-id="2b74b-169">开始规划设备部署。</span><span class="sxs-lookup"><span data-stu-id="2b74b-169">Start to plan your device deployment.</span></span></li></ul>|

### <a name="device-deployment"></a><span data-ttu-id="2b74b-170">设备部署</span><span class="sxs-lookup"><span data-stu-id="2b74b-170">Device deployment</span></span>

<span data-ttu-id="2b74b-171">接下来，你需要创建你的计划，以便将设备和分配的外围设备交付到你的聊天室，然后继续安装和配置。</span><span class="sxs-lookup"><span data-stu-id="2b74b-171">Next, you need to create your plan to deliver the devices and their assigned peripheral devices to your rooms, and then proceed with installation and configuration.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="2b74b-173">决策点</span><span class="sxs-lookup"><span data-stu-id="2b74b-173">Decision points</span></span>|<ul><li><span data-ttu-id="2b74b-174">确定由谁来管理网站的网站部署。</span><span class="sxs-lookup"><span data-stu-id="2b74b-174">Decide who will manage the site-by-site deployment.</span></span></li><li> <span data-ttu-id="2b74b-175">确定将为 Microsoft 团队网站安装协作栏并执行配置和测试的资源。</span><span class="sxs-lookup"><span data-stu-id="2b74b-175">Identify the resources who will install the collaboration bars for Microsoft Teams on site and undertake the configuration and testing.</span></span></li></ul>|
| ![描述后续步骤的图标](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="2b74b-177">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2b74b-177">Next steps</span></span>|<ul><li><span data-ttu-id="2b74b-178">开始设备测试。</span><span class="sxs-lookup"><span data-stu-id="2b74b-178">Start device testing.</span></span></li></ul>|

### <a name="testing"></a><span data-ttu-id="2b74b-179"> 测试</span><span class="sxs-lookup"><span data-stu-id="2b74b-179">Testing</span></span>

<span data-ttu-id="2b74b-180">部署 Microsoft 团队的协作栏后，应进行测试。</span><span class="sxs-lookup"><span data-stu-id="2b74b-180">After the collaboration bars for Microsoft Teams have been deployed, you should test them.</span></span> <span data-ttu-id="2b74b-181">登录设备，检查所需的功能是否在已部署的设备上工作。</span><span class="sxs-lookup"><span data-stu-id="2b74b-181">Sign in to the device and check that the expected capabilities are working on the deployed device.</span></span> <span data-ttu-id="2b74b-182">强烈建议你验证设备是否显示在 Microsoft 团队管理中心的 "**设备**" 选项卡的 "**协作栏**" 部分中。</span><span class="sxs-lookup"><span data-stu-id="2b74b-182">We highly recommend that you verify that the devices are appearing in the **Collaboration bars** section under the **Devices** tab of Microsoft Teams admin center.</span></span> <span data-ttu-id="2b74b-183">还必须进行大量测试通话和会议才能检查质量和性能。</span><span class="sxs-lookup"><span data-stu-id="2b74b-183">It's also important that you make a number of test calls and meetings to check quality and performance.</span></span>

<span data-ttu-id="2b74b-184">我们建议作为常规 Microsoft 团队推出的一部分，为通话质量仪表板配置构建文件 (CQD) 、监控质量趋势以及参与体验审核流程。</span><span class="sxs-lookup"><span data-stu-id="2b74b-184">We recommend that as part of the general Microsoft Teams rollout, you configure building files for Call Quality Dashboard (CQD), monitor quality trends, and engage in the Quality of Experience Review process.</span></span> <span data-ttu-id="2b74b-185">有关详细信息，请参阅 [体验质量检查指南](https://aka.ms/qerguide)。</span><span class="sxs-lookup"><span data-stu-id="2b74b-185">For more information, see the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

### <a name="asset-management"></a><span data-ttu-id="2b74b-186">资产管理</span><span class="sxs-lookup"><span data-stu-id="2b74b-186">Asset management</span></span>

<span data-ttu-id="2b74b-187">作为部署的一部分，您将需要用房间名称、登录资源帐户和分配的外围设备更新您的资产注册。</span><span class="sxs-lookup"><span data-stu-id="2b74b-187">As part of the deployment, you'll want to update your asset register with the room name, signed-in resource account, and assigned peripheral devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2b74b-188">相关主题</span><span class="sxs-lookup"><span data-stu-id="2b74b-188">Related topics</span></span>

[<span data-ttu-id="2b74b-189">使用 Microsoft 团队管理中心为 Microsoft 团队配置协作栏的帐户</span><span class="sxs-lookup"><span data-stu-id="2b74b-189">Configure accounts for collaboration bars for Microsoft Teams using Microsoft Teams admin center</span></span>](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
