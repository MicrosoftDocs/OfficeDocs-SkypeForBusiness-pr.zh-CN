---
title: 在 Android 上部署 Microsoft Teams 会议室
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
description: 阅读本文，了解如何在 Android 上部署 Microsoft Teams 会议室。
ms.openlocfilehash: 3da0192ee3676f5ff7294ba719c778ea7b1cc7b2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120794"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a><span data-ttu-id="53caf-103">在 Android 上部署 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="53caf-103">Deploy Microsoft Teams Rooms on Android</span></span>

<span data-ttu-id="53caf-104">在 Android 上部署 Microsoft Teams 会议室可以分为以下阶段：</span><span class="sxs-lookup"><span data-stu-id="53caf-104">Deployment of Microsoft Teams Rooms on Android can be broken down into the following phases:</span></span>

- <span data-ttu-id="53caf-105">**网站就绪性** 确认会议室中的 (位置) 满足部署要求。</span><span class="sxs-lookup"><span data-stu-id="53caf-105">**Site readiness** Confirm that your deployment locations (rooms) meet the deployment requirements.</span></span>
- <span data-ttu-id="53caf-106">**服务就绪性** 创建资源帐户并将其分配给设备 ([请参阅使用 Microsoft 365](resource-account-ui.md) 管理中心创建资源) 。</span><span class="sxs-lookup"><span data-stu-id="53caf-106">**Service readiness** Create resource accounts and assign them to the devices ([see Create a resource account using the Microsoft 365 admin center](resource-account-ui.md)).</span></span> <span data-ttu-id="53caf-107">虽然我们建议使用专用聊天室许可证，但获得适当许可的最终用户帐户也可以登录到 Android 上的 Teams 会议室。</span><span class="sxs-lookup"><span data-stu-id="53caf-107">While we recommend using a dedicated room license, a properly licensed end user account can also sign in to Teams Rooms on Android.</span></span>
- <span data-ttu-id="53caf-108">**配置和部署** 有关详细信息，请参阅制造商的文档 (Teams 会议室并连接) 。</span><span class="sxs-lookup"><span data-stu-id="53caf-108">**Configuration and deployment** Set up Teams Rooms and connect the peripheral devices you need (see the manufacturer's documentation for details).</span></span>

<span data-ttu-id="53caf-109">若要管理 Teams 会议室，你需要是全局管理员、Teams 服务管理员或 Teams 设备管理员。有关管理员角色的信息，请参阅使用[Microsoft Teams 管理员角色管理 Teams。](../using-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="53caf-109">To manage Teams Rooms, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

## <a name="site-readiness"></a><span data-ttu-id="53caf-110">网站就绪</span><span class="sxs-lookup"><span data-stu-id="53caf-110">Site readiness</span></span>

<span data-ttu-id="53caf-111">将订购的设备传送到组织时，请与网络、设施和音频视觉团队协作，确保满足部署要求，并且每个站点和会议室在电源、网络和显示方面已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="53caf-111">While the ordered devices are being delivered to your organization, work with your networking, facilities, and audio-visual teams to make sure that deployment requirements are met and each site and room is ready in terms of power, networking, and display.</span></span>

<span data-ttu-id="53caf-112">我们针对协作栏网站的建议是：</span><span class="sxs-lookup"><span data-stu-id="53caf-112">Our recommendations for collaboration bar sites are:</span></span>

- <span data-ttu-id="53caf-113">大小最多 5 人的房间</span><span class="sxs-lookup"><span data-stu-id="53caf-113">Rooms up to 5 people in size</span></span>
- <span data-ttu-id="53caf-114">专用资源帐户</span><span class="sxs-lookup"><span data-stu-id="53caf-114">Dedicated resource accounts</span></span>
- <span data-ttu-id="53caf-115">支持触摸的显示器</span><span class="sxs-lookup"><span data-stu-id="53caf-115">Touch-enabled displays</span></span>
- <span data-ttu-id="53caf-116">以太网布线</span><span class="sxs-lookup"><span data-stu-id="53caf-116">Ethernet cabling</span></span>
- <span data-ttu-id="53caf-117">网络上为 Microsoft Teams (QoS) 服务质量</span><span class="sxs-lookup"><span data-stu-id="53caf-117">Quality of Service (QoS) enabled on the network for Microsoft Teams media</span></span>

<span data-ttu-id="53caf-118">有关物理安装注意事项，请参阅制造商的文档，如果有，在安装和装载屏幕并运行布线之前，请利用音频视觉团队的经验。</span><span class="sxs-lookup"><span data-stu-id="53caf-118">For physical installation considerations, see the manufacturer's documentation and, if you have one, leverage the experience of your audio-visual team before you install and mount screens and run cabling.</span></span>

> [!TIP]
> <span data-ttu-id="53caf-119">请务必查看为 [Teams 准备](../prepare-network.md) 网络，以规划带宽并评估网络是否适合实时流量。</span><span class="sxs-lookup"><span data-stu-id="53caf-119">Be sure to check out [Prepare your network for Teams](../prepare-network.md) for bandwidth planning and assessing your network’s suitability for real-time traffic.</span></span>
>
> <span data-ttu-id="53caf-120">我们不建议在 Teams 设备和 Internet 之间放置代理服务器。</span><span class="sxs-lookup"><span data-stu-id="53caf-120">We don't recommend placing proxy servers between Teams devices and the Internet.</span></span> <span data-ttu-id="53caf-121">有关代理服务器和 Teams 的信息，请查看 [Teams 的代理服务器](../proxy-servers-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="53caf-121">For more information about proxy servers and Teams, check out [Proxy servers for Teams](../proxy-servers-for-skype-for-business-online.md).</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="53caf-123">决策点</span><span class="sxs-lookup"><span data-stu-id="53caf-123">Decision points</span></span>|<ul><li><span data-ttu-id="53caf-124">确认您的网站满足 Microsoft Teams 协作栏的网站就绪性要求。</span><span class="sxs-lookup"><span data-stu-id="53caf-124">Confirm that your sites meet the site readiness requirements for collaboration bars for Microsoft Teams.</span></span></li><li><span data-ttu-id="53caf-125">请确认为每个网站提供了足够的带宽。</span><span class="sxs-lookup"><span data-stu-id="53caf-125">Confirm that you've provided sufficient bandwidth for each site.</span></span></li></ul>|
| ![描述下一步骤的图标](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="53caf-127">后续步骤</span><span class="sxs-lookup"><span data-stu-id="53caf-127">Next steps</span></span>|<ul><li><span data-ttu-id="53caf-128">开始规划协作栏部署和配置。</span><span class="sxs-lookup"><span data-stu-id="53caf-128">Start to plan your collaboration bar deployment and configuration.</span></span></li></ul>|

## <a name="service-readiness"></a><span data-ttu-id="53caf-129">服务就绪</span><span class="sxs-lookup"><span data-stu-id="53caf-129">Service readiness</span></span>

<span data-ttu-id="53caf-130">在部署 Teams 会议室之前，你需要确定它们使用 Microsoft 365 资源帐户、最终用户帐户还是两者混合使用。</span><span class="sxs-lookup"><span data-stu-id="53caf-130">Before you deploy Teams Rooms, you need to decide if they'll use Microsoft 365 resource accounts, end-user accounts, or a mixture of both.</span></span> <span data-ttu-id="53caf-131">Microsoft 365 资源帐户是专用于特定资源（如会议室、投影仪等）的邮箱和 Teams 帐户。</span><span class="sxs-lookup"><span data-stu-id="53caf-131">Microsoft 365 resource accounts are mailbox and Teams accounts that are dedicated to specific resources, such as a room, projector, and so on.</span></span> <span data-ttu-id="53caf-132">这些资源帐户可以使用创建会议邀请时定义的规则自动响应会议邀请。</span><span class="sxs-lookup"><span data-stu-id="53caf-132">These resource accounts can automatically respond to meeting invites using rules you define when they're created.</span></span> <span data-ttu-id="53caf-133">除非 Teams 会议室专用于个人专用，否则我们建议为它设置 Microsoft 365 资源帐户。</span><span class="sxs-lookup"><span data-stu-id="53caf-133">Unless Teams Rooms is dedicated to a specific individual for their private use, we recommend setting up a Microsoft 365 resource account for it.</span></span>

### <a name="using-a-resource-account"></a><span data-ttu-id="53caf-134">使用资源帐户</span><span class="sxs-lookup"><span data-stu-id="53caf-134">Using a resource account</span></span>

<span data-ttu-id="53caf-135">如果决定设置 Microsoft 365 资源帐户，则需要购买会议室许可证。</span><span class="sxs-lookup"><span data-stu-id="53caf-135">If you decide to set up a Microsoft 365 resource account, you'll need to purchase a Meeting Room license for it.</span></span> <span data-ttu-id="53caf-136">会议室许可证包括一个资源邮箱，使组织中的人员可以通过 Outlook 或 Teams 预订会议室。</span><span class="sxs-lookup"><span data-stu-id="53caf-136">The Meeting Room license includes a resource mailbox that enables people in your organization to book the meeting room via Outlook or Teams.</span></span> <span data-ttu-id="53caf-137">该许可证还支持视频和音频会议以及会议参与者之间的屏幕共享。</span><span class="sxs-lookup"><span data-stu-id="53caf-137">The license also enables video and audio conferencing and screen sharing among meeting participants.</span></span>

<span data-ttu-id="53caf-138">如果需要接收或拨打外部电话号码，可能需要呼叫计划或 Microsoft 365 商业语音 [附加许可证](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business)。</span><span class="sxs-lookup"><span data-stu-id="53caf-138">If you need to receive or make calls to or from an external telephone number, you may need a Calling Plan or Microsoft 365 Business Voice [add-on license](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business).</span></span> <span data-ttu-id="53caf-139">如果在组织中启用了直接路由，则只需要会议室 SKU。</span><span class="sxs-lookup"><span data-stu-id="53caf-139">If you have Direct Routing enabled in your organization, you only need the Meeting Room SKU.</span></span>

<span data-ttu-id="53caf-140">创建资源帐户时，可以选择是否允许帐户自动接受或拒绝会议请求、允许定期会议、指定用户可以提前预订资源多远，等等。</span><span class="sxs-lookup"><span data-stu-id="53caf-140">When you create a resource account, you can choose whether to let the account automatically accept or decline meeting requests, allow recurring meetings, specify how far in advance people can book the resource, and so on.</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

<span data-ttu-id="53caf-141">有关 Microsoft 365 资源帐户的信息，请参阅 [使用 Microsoft 365](resource-account-ui.md)管理中心创建资源帐户。</span><span class="sxs-lookup"><span data-stu-id="53caf-141">For more information about Microsoft 365 resource accounts, see [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md).</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="53caf-143">决策点</span><span class="sxs-lookup"><span data-stu-id="53caf-143">Decision points</span></span>|<ul><li><span data-ttu-id="53caf-144">决定是拨打还是接听外部电话呼叫，并确定资源帐户的许可要求。</span><span class="sxs-lookup"><span data-stu-id="53caf-144">Decide whether you want to make or receive external phone calls and identify licensing requirements for your resource accounts.</span></span></li></ul>|
| ![描述下一步骤的图标](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="53caf-146">后续步骤</span><span class="sxs-lookup"><span data-stu-id="53caf-146">Next steps</span></span>|<ul><li><span data-ttu-id="53caf-147">准备资源帐户。</span><span class="sxs-lookup"><span data-stu-id="53caf-147">Prepare resource accounts.</span></span></li></ul>|

## <a name="configuration-and-deployment"></a><span data-ttu-id="53caf-148">配置和部署</span><span class="sxs-lookup"><span data-stu-id="53caf-148">Configuration and deployment</span></span>

<span data-ttu-id="53caf-149">配置和部署规划包括以下关键领域：</span><span class="sxs-lookup"><span data-stu-id="53caf-149">Planning for configuration and deployment covers the following key areas:</span></span>

- <span data-ttu-id="53caf-150">资源帐户预配</span><span class="sxs-lookup"><span data-stu-id="53caf-150">Resource account provisioning</span></span>
- <span data-ttu-id="53caf-151">设备部署</span><span class="sxs-lookup"><span data-stu-id="53caf-151">Device deployment</span></span>
- <span data-ttu-id="53caf-152">Teams 会议室应用程序和外围设备配置</span><span class="sxs-lookup"><span data-stu-id="53caf-152">Teams Rooms application and peripheral device configuration</span></span>
- <span data-ttu-id="53caf-153">测试</span><span class="sxs-lookup"><span data-stu-id="53caf-153">Testing</span></span>
- <span data-ttu-id="53caf-154">资产管理</span><span class="sxs-lookup"><span data-stu-id="53caf-154">Asset management</span></span>

### <a name="account-provisioning"></a><span data-ttu-id="53caf-155">帐户设置</span><span class="sxs-lookup"><span data-stu-id="53caf-155">Account provisioning</span></span>

<span data-ttu-id="53caf-156">如果计划使用 Microsoft 365 资源帐户让用户预订协作栏，请按照使用 Microsoft [365](resource-account-ui.md) 管理中心创建资源帐户中的说明为每个需要协作栏的协作栏创建 Microsoft 365 资源帐户。</span><span class="sxs-lookup"><span data-stu-id="53caf-156">If you plan on using Microsoft 365 resource accounts to let users book collaboration bars, follow the instructions in [Create a resource account using the Microsoft 365 admin center](resource-account-ui.md) to create a Microsoft 365 resource account for each collaboration bar that needs one.</span></span> <span data-ttu-id="53caf-157">这也是您需要向资源帐户添加会议室许可证的地方，如果要拨打或接听来自外部电话号码的呼叫，请添加呼叫计划或商务语音许可证（如果您的组织没有使用直接路由）。</span><span class="sxs-lookup"><span data-stu-id="53caf-157">This is also where you'll need to add a Meeting Room license to the resource account and, if you want to make or receive calls to or from external phone numbers, a Calling Plan or Business Voice license if your organization is not using Direct Routing.</span></span>

<span data-ttu-id="53caf-158">如果要将 Teams 会议室分配给单个用户供其专用，则不需要设置任何其他帐户。</span><span class="sxs-lookup"><span data-stu-id="53caf-158">If you want to assign Teams Rooms to individual users for their private use, you don't need to set up any additional accounts.</span></span> <span data-ttu-id="53caf-159">用户可以使用个人帐户登录到协作栏。</span><span class="sxs-lookup"><span data-stu-id="53caf-159">Users can sign into collaboration bars using their personal accounts.</span></span>

> [!TIP]
> <span data-ttu-id="53caf-160">使 Microsoft 365 资源帐户的显示名称具有描述性且易于理解。</span><span class="sxs-lookup"><span data-stu-id="53caf-160">Make the display names for your Microsoft 365 resource accounts descriptive and easy to understand.</span></span> <span data-ttu-id="53caf-161">这些是用户在搜索 Teams 会议室以及将 Teams 会议室添加到会议时会看到的名称。</span><span class="sxs-lookup"><span data-stu-id="53caf-161">These are the names that users will see when searching for and adding Teams Rooms to meetings.</span></span> <span data-ttu-id="53caf-162">您可以使用网站会议室名称 (最大会议室容量) 等约定，例如，伦敦 4 人会议室 Curie 可能拥有 - 显示名称 LON-CURIE (4) 。 </span><span class="sxs-lookup"><span data-stu-id="53caf-162">You could use a convention like *Site*-*Room Name*(*Max Room Capacity*), so for example Curie, a 4-person meeting room in London, might have the display name LON-CURIE(4).</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="53caf-164">决策点</span><span class="sxs-lookup"><span data-stu-id="53caf-164">Decision points</span></span>|<ul><li><span data-ttu-id="53caf-165">确定专用资源帐户的命名约定。</span><span class="sxs-lookup"><span data-stu-id="53caf-165">Decide the naming convention for your dedicated resource accounts.</span></span></li><li><span data-ttu-id="53caf-166">决定是创建单个帐户还是使用批量预配脚本。</span><span class="sxs-lookup"><span data-stu-id="53caf-166">Decide whether you’ll create individual accounts or use bulk-provisioning scripts.</span></span></li></ul>|
| ![描述下一步骤的图标](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="53caf-168">后续步骤</span><span class="sxs-lookup"><span data-stu-id="53caf-168">Next steps</span></span>|<ul><li><span data-ttu-id="53caf-169">开始计划设备部署。</span><span class="sxs-lookup"><span data-stu-id="53caf-169">Start to plan your device deployment.</span></span></li></ul>|

### <a name="device-deployment"></a><span data-ttu-id="53caf-170">设备部署</span><span class="sxs-lookup"><span data-stu-id="53caf-170">Device deployment</span></span>

<span data-ttu-id="53caf-171">接下来，需要创建计划，将设备及其分配的外围设备交付到会议室，然后继续进行安装和配置。</span><span class="sxs-lookup"><span data-stu-id="53caf-171">Next, you need to create your plan to deliver the devices and their assigned peripheral devices to your rooms, and then proceed with installation and configuration.</span></span>

|    |     |
|-----------|------------|
| ![描述决策点的图标](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="53caf-173">决策点</span><span class="sxs-lookup"><span data-stu-id="53caf-173">Decision points</span></span>|<ul><li><span data-ttu-id="53caf-174">决定管理站点到站点部署的人员。</span><span class="sxs-lookup"><span data-stu-id="53caf-174">Decide who will manage the site-by-site deployment.</span></span></li><li> <span data-ttu-id="53caf-175">确定将现场安装 Teams 会议室的资源，并执行配置和测试。</span><span class="sxs-lookup"><span data-stu-id="53caf-175">Identify the resources who will install Teams Rooms on site and undertake the configuration and testing.</span></span></li></ul>|
| ![描述下一步骤的图标](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="53caf-177">后续步骤</span><span class="sxs-lookup"><span data-stu-id="53caf-177">Next steps</span></span>|<ul><li><span data-ttu-id="53caf-178">开始设备测试.</span><span class="sxs-lookup"><span data-stu-id="53caf-178">Start device testing.</span></span></li></ul>|

### <a name="testing"></a><span data-ttu-id="53caf-179">测试</span><span class="sxs-lookup"><span data-stu-id="53caf-179">Testing</span></span>

<span data-ttu-id="53caf-180">部署 Teams 会议室后，应测试它们。</span><span class="sxs-lookup"><span data-stu-id="53caf-180">After you have deployed Teams Rooms, you should test them.</span></span> <span data-ttu-id="53caf-181">登录到 Teams 会议室，检查预期功能是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="53caf-181">Sign in to Teams Rooms and check that the expected capabilities are working.</span></span> <span data-ttu-id="53caf-182">强烈建议验证它们是否显示在 Microsoft Teams 管理中心的"设备"选项卡下的"协作栏"部分。</span><span class="sxs-lookup"><span data-stu-id="53caf-182">We highly recommend that you verify that they are appearing in the **Collaboration bars** section under the **Devices** tab of Microsoft Teams admin center.</span></span> <span data-ttu-id="53caf-183">还必须进行大量测试呼叫和会议，以检查质量和性能。</span><span class="sxs-lookup"><span data-stu-id="53caf-183">It's also important that you make a number of test calls and meetings to check quality and performance.</span></span>

<span data-ttu-id="53caf-184">建议在 Microsoft Teams 常规推广过程中，为呼叫质量仪表板 (CQD) 配置生成文件，监视质量趋势，并参与体验质量评审过程。</span><span class="sxs-lookup"><span data-stu-id="53caf-184">We recommend that as part of the general Microsoft Teams rollout, you configure building files for Call Quality Dashboard (CQD), monitor quality trends, and engage in the Quality of Experience Review process.</span></span> <span data-ttu-id="53caf-185">有关详细信息，请参阅 [体验质量评审指南](../quality-of-experience-review-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="53caf-185">For more information, see the [Quality of Experience Review Guide](../quality-of-experience-review-guide.md).</span></span>

### <a name="asset-management"></a><span data-ttu-id="53caf-186">资产管理</span><span class="sxs-lookup"><span data-stu-id="53caf-186">Asset management</span></span>

<span data-ttu-id="53caf-187">在部署中，需要使用聊天室名称、登录的资源帐户和分配的外围设备更新资产注册。</span><span class="sxs-lookup"><span data-stu-id="53caf-187">As part of the deployment, you'll want to update your asset register with the room name, signed-in resource account, and assigned peripheral devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="53caf-188">相关主题</span><span class="sxs-lookup"><span data-stu-id="53caf-188">Related topics</span></span>

[<span data-ttu-id="53caf-189">使用 Microsoft Teams 管理中心配置 Microsoft Teams 会议室的帐户</span><span class="sxs-lookup"><span data-stu-id="53caf-189">Configure accounts for Microsoft Teams Rooms using Microsoft Teams admin center</span></span>](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->