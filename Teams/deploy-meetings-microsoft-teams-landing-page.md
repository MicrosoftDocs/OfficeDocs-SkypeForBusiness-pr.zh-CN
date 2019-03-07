---
title: Microsoft Teams 中的会议
description: 使用这些部署资源帮助你在 Microsoft Teams 中部署会议。
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/28/2019
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d6554a641fe9abc02461fac891a3bb4fc5a9440
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461089"
---
# <a name="meetings--conferencing-in-microsoft-teams"></a><span data-ttu-id="989cb-103">Microsoft Teams 中的会议</span><span class="sxs-lookup"><span data-stu-id="989cb-103">Meetings & conferencing in Microsoft Teams</span></span>

<span data-ttu-id="989cb-104">你已完成了[入门](get-started-with-teams-quick-start.md)。</span><span class="sxs-lookup"><span data-stu-id="989cb-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="989cb-105">你已在整个组织中部署了具有[聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)的 Teams。</span><span class="sxs-lookup"><span data-stu-id="989cb-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="989cb-106">现在你准备添加会议工作负载，其中包括[音频会议](deploy-audio-conferencing-teams-landing-page.md)、视频和分享。</span><span class="sxs-lookup"><span data-stu-id="989cb-106">Now you're ready to add the meetings workload, including [audio conferencing](deploy-audio-conferencing-teams-landing-page.md), video, and sharing.</span></span> <span data-ttu-id="989cb-107">方法如下。</span><span class="sxs-lookup"><span data-stu-id="989cb-107">Here's how.</span></span> 


## <a name="meetings--conferencing-deployment-decisions"></a><span data-ttu-id="989cb-108">会议部署决策</span><span class="sxs-lookup"><span data-stu-id="989cb-108">Meetings & conferencing deployment decisions</span></span>

<span data-ttu-id="989cb-109">Teams 为组织提供了现成的出色体验，并且大多数组织发现默认设置即适合它们。</span><span class="sxs-lookup"><span data-stu-id="989cb-109">Teams provides a great out-of-the-box experience for your organization, and most organizations find that the default settings work for them.</span></span> <span data-ttu-id="989cb-110">本文可帮助你决定是否要根据组织的情况和业务需求更改任何默认设置，然后引导你完成每项更改。</span><span class="sxs-lookup"><span data-stu-id="989cb-110">This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="989cb-111">我们将这些设置分为两组：首先是[你更有可能更改的一组核心设置](#core-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="989cb-111">We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="989cb-112">第二组包括你可能希望根据组织的需求配置的[其他设置](#additional-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="989cb-112">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

> [!Tip]
> <span data-ttu-id="989cb-113">观看下面的课程来详细了解会议：[Microsoft Teams 中的会议：面向 IT 专业人员的简介](https://aka.ms/teams-meetings-intro)</span><span class="sxs-lookup"><span data-stu-id="989cb-113">Watch the following session to learn more about Meetings: [Introduction to Meetings in Microsoft Teams for IT Pros](https://aka.ms/teams-meetings-intro)</span></span>


## <a name="meetings--conferencing-prerequisites"></a><span data-ttu-id="989cb-114">会议先决条件</span><span class="sxs-lookup"><span data-stu-id="989cb-114">Meetings & conferencing prerequisites</span></span> 

<span data-ttu-id="989cb-115">在整个组织中大规模部署会议之前，请花时间检查并确认你的环境已准备好为用户提供最佳体验。</span><span class="sxs-lookup"><span data-stu-id="989cb-115">Before scaling your meetings deployment across your organization, take time to review and confirm that your environment is ready to provide users with the best possible experience.</span></span> <span data-ttu-id="989cb-116">查看以下信息，并根据需要对你的环境进行任何必需的更改。</span><span class="sxs-lookup"><span data-stu-id="989cb-116">Review the following information and make any required changes to your environment as needed.</span></span>

<span data-ttu-id="989cb-117">若要获得最佳 Teams 体验，你的组织必须部署了 Exchange Online 和 SharePoint Online，并且你必须有适用于 O365 的已验证域（例如，*contoso.com*）。</span><span class="sxs-lookup"><span data-stu-id="989cb-117">To get the best experience on Teams, your organization must have deployed Exchange Online and SharePoint Online, and you must have a verified domain for O365 such as *contoso.com*.</span></span>

<span data-ttu-id="989cb-118">为了在整个组织中大规模部署会议，你应确保所有用户地点都有权访问 Internet，以便连接到 Office 365 服务。</span><span class="sxs-lookup"><span data-stu-id="989cb-118">To scale meetings across your organization you should ensure that all user locations have internet access to connect to the Office 365 Services.</span></span> <span data-ttu-id="989cb-119">你至少应确保以下常用端口在用户地点已向 Internet 开放：</span><span class="sxs-lookup"><span data-stu-id="989cb-119">At a minimum you should make sure that the following common ports are open to the internet from your user’s locations:-</span></span>

- <span data-ttu-id="989cb-120">将使用 Teams 的客户端上用于传出连接的 TCP 端口 80 和 443。</span><span class="sxs-lookup"><span data-stu-id="989cb-120">TCP ports 80 and 443 outgoing from clients that will use Teams</span></span>
- <span data-ttu-id="989cb-121">将使用 Teams 的客户端上用于传出连接的 UDP 端口 3478 到 3481。</span><span class="sxs-lookup"><span data-stu-id="989cb-121">UDP ports 3478 through 3481 outgoing from clients that will use Teams</span></span>

<span data-ttu-id="989cb-122">可以使用[网络测试配套工具](https://www.powershellgallery.com/packages/NetworkTestingCompanion/1.5.2)，确认网络位置已做好准备应对支持你的会议体验的语音和视频流量。</span><span class="sxs-lookup"><span data-stu-id="989cb-122">You can use the [Network Testing Companion](https://www.powershellgallery.com/packages/NetworkTestingCompanion/1.5.2) to confirm that your network locations are ready for the voice and video traffic that will support your meetings experience.</span></span>

| <span data-ttu-id="989cb-123">询问你自己</span><span class="sxs-lookup"><span data-stu-id="989cb-123">Ask yourself</span></span> | <span data-ttu-id="989cb-124">操作</span><span class="sxs-lookup"><span data-stu-id="989cb-124">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="989cb-125">我的网络是否已准备好进行 Teams 会议部署？</span><span class="sxs-lookup"><span data-stu-id="989cb-125">Is my network ready for Teams meetings deployment?</span></span> | <span data-ttu-id="989cb-126">若要验证网络是否准备就绪，请参阅：</span><span class="sxs-lookup"><span data-stu-id="989cb-126">To verify that your network is ready, see:</span></span><ul><li>[<span data-ttu-id="989cb-127">为 Microsoft Teams 准备组织的网络</span><span class="sxs-lookup"><span data-stu-id="989cb-127">Prepare your organization's network for Microsoft Teams</span></span>](https://docs.microsoft.com/en-us/MicrosoftTeams/prepare-network)</li><li>[<span data-ttu-id="989cb-128">Office 365 URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="989cb-128">Office 365 URLs and IP address ranges</span></span>](https://docs.microsoft.com/en-us/MicrosoftTeams/office-365-urls-ip-address-ranges)</li></ul> |
|||

## <a name="core-deployment-decisions"></a><span data-ttu-id="989cb-129">核心部署决策</span><span class="sxs-lookup"><span data-stu-id="989cb-129">Core deployment decisions</span></span>

<span data-ttu-id="989cb-130">以下是大多数组织在默认设置不适合的情况下想要更改的设置。</span><span class="sxs-lookup"><span data-stu-id="989cb-130">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

### <a name="teams-administrators"></a><span data-ttu-id="989cb-131">Teams 管理员</span><span class="sxs-lookup"><span data-stu-id="989cb-131">Teams administrators</span></span>

<span data-ttu-id="989cb-132">Teams 提供了一组可用于为组织管理 Teams 的自定义管理员角色。</span><span class="sxs-lookup"><span data-stu-id="989cb-132">Teams provides a set of custom administrator roles that can be used to manage Teams for your organization.</span></span> <span data-ttu-id="989cb-133">这些角色为管理员提供各种能力。</span><span class="sxs-lookup"><span data-stu-id="989cb-133">The roles provide various capabilities to administrators.</span></span> 

| <span data-ttu-id="989cb-134">询问你自己</span><span class="sxs-lookup"><span data-stu-id="989cb-134">Ask yourself</span></span> | <span data-ttu-id="989cb-135">操作</span><span class="sxs-lookup"><span data-stu-id="989cb-135">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="989cb-136">将为谁分配 Teams 通信管理员角色？</span><span class="sxs-lookup"><span data-stu-id="989cb-136">Who will be assigned the Teams Communications Administrator role?</span></span>|<span data-ttu-id="989cb-137">若要详细了解 Teams 管理员角色，请参阅[使用 Microsoft Teams 管理员角色来管理 Teams](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="989cb-137">To learn more about Teams administrator roles see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>|
|<span data-ttu-id="989cb-138">将为谁分配 Teams 通信支持工程师角色？</span><span class="sxs-lookup"><span data-stu-id="989cb-138">Who will be assigned the Teams Communications Support Engineer role?</span></span>|<span data-ttu-id="989cb-139">若要分配管理员角色，请参阅[使用 Active Directory 为用户分配管理员和非管理员角色](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="989cb-139">To assign admin roles, see [Assign administrator and non-administrator roles to users with Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>|
|<span data-ttu-id="989cb-140">将为谁分配 Teams 通信支持专家角色？</span><span class="sxs-lookup"><span data-stu-id="989cb-140">Who will be assigned the Teams Communications Support Specialist role?</span></span>||
|||

### <a name="meetings-settings"></a><span data-ttu-id="989cb-141">会议设置</span><span class="sxs-lookup"><span data-stu-id="989cb-141">Meetings settings</span></span> 

<span data-ttu-id="989cb-142">会议设置用于控制匿名用户是否可加入 Teams 会议、设置会议邀请，并在想要启用服务质量 (QoS) 的情况下设置实时流量端口。</span><span class="sxs-lookup"><span data-stu-id="989cb-142">Meetings settings are used to control whether anonymous users can join Teams meetings, set up meeting invitations, and if you want to turn on Quality of Service (QoS), set the ports for real-time traffic.</span></span> <span data-ttu-id="989cb-143">这些设置将用于用户在组织中安排的所有 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="989cb-143">These settings will be used for all of the Teams meetings that users schedule in your organization.</span></span> 

| <span data-ttu-id="989cb-144">询问你自己</span><span class="sxs-lookup"><span data-stu-id="989cb-144">Ask yourself</span></span> | <span data-ttu-id="989cb-145">操作</span><span class="sxs-lookup"><span data-stu-id="989cb-145">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="989cb-146">是否要自定义初始会议设置？</span><span class="sxs-lookup"><span data-stu-id="989cb-146">Will I customize the initial meeting settings?</span></span> |<span data-ttu-id="989cb-147">请参阅 [Teams 中的会议教程](tutorial-meetings-in-teams.yml)，详细了解会议设置。</span><span class="sxs-lookup"><span data-stu-id="989cb-147">See the [Meetings in Teams tutorial](tutorial-meetings-in-teams.yml) to learn more about meetings settings.</span></span>|
|<span data-ttu-id="989cb-148">是否要实施 QoS？</span><span class="sxs-lookup"><span data-stu-id="989cb-148">Will I implement QoS?</span></span>|<span data-ttu-id="989cb-149">有关 QoS 概念的详细信息，请参阅 [Microsoft Teams 中的服务质量](qos-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="989cb-149">See [Quality of Service in Microsoft Teams](qos-in-teams.md) for information about QoS concepts.</span></span> <span data-ttu-id="989cb-150">方案和实施。</span><span class="sxs-lookup"><span data-stu-id="989cb-150">scenarios, and implementation.</span></span>|
|||

### <a name="meeting-policies"></a><span data-ttu-id="989cb-151">会议策略</span><span class="sxs-lookup"><span data-stu-id="989cb-151">Meeting policies</span></span>

<span data-ttu-id="989cb-152">会议策略用于控制在用户加入 Teams 会议时可以使用哪些功能。</span><span class="sxs-lookup"><span data-stu-id="989cb-152">Meeting policies are used to control what features are available to users when they join Teams meetings.</span></span> <span data-ttu-id="989cb-153">你可以使用默认策略，或者为组织中主持会议的人员创建一个或多个自定义会议策略。</span><span class="sxs-lookup"><span data-stu-id="989cb-153">You can use the default policy or create one or more custom meeting policies for people that host meetings in your organization.</span></span> <span data-ttu-id="989cb-154">若要了解详细信息，请参阅 [Microsoft Team 中的会议教程](tutorial-meetings-in-teams.yml)。</span><span class="sxs-lookup"><span data-stu-id="989cb-154">To learn more, see the [Meetings in Microsoft Team tutorial](tutorial-meetings-in-teams.yml).</span></span>

| <span data-ttu-id="989cb-155">询问你自己</span><span class="sxs-lookup"><span data-stu-id="989cb-155">Ask yourself</span></span> | <span data-ttu-id="989cb-156">操作</span><span class="sxs-lookup"><span data-stu-id="989cb-156">Action</span></span> |
|--------------|--------|
|<ul><li><span data-ttu-id="989cb-157">是否要自定义初始会议策略？</span><span class="sxs-lookup"><span data-stu-id="989cb-157">Will I customize the initial meeting policies?</span></span></li><li><span data-ttu-id="989cb-158">是否需要多个会议策略？</span><span class="sxs-lookup"><span data-stu-id="989cb-158">Do I require multiple meeting policies?</span></span></li><li><span data-ttu-id="989cb-159">如何确定向哪些用户组应用哪些会议策略？</span><span class="sxs-lookup"><span data-stu-id="989cb-159">How will I determine which groups of users get which meetings policy applied?</span></span></li></ul>|<br><span data-ttu-id="989cb-160">请阅读 [Teams 中的会议策略](meeting-policies-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="989cb-160">Read [Manage meeting policies in Teams](meeting-policies-in-teams.md).</span></span>|
|||

### <a name="audio-conferencing"></a><span data-ttu-id="989cb-161">音频会议</span><span class="sxs-lookup"><span data-stu-id="989cb-161">Audio Conferencing</span></span>

<span data-ttu-id="989cb-162">音频会议允许会议参与者使用传统陆上线路、专用分组交换机 (PBX) 或移动电话通过公共交换电话网 (PSTN) 拨入来加入会议，从而为组织提供了另一个进入任何会议的入口点。</span><span class="sxs-lookup"><span data-stu-id="989cb-162">Audio Conferencing provides organizations with additional entry points to any meeting (ad hoc or scheduled) by allowing meeting participants to join via public switched telephone network (PSTN) by dialing in using a traditional land line, private branch exchange (PBX), or mobile phone.</span></span> 

<span data-ttu-id="989cb-163">准备好部署音频会议时，请参阅深入的[音频会议部署](deploy-audio-conferencing-teams-landing-page.md)指引。</span><span class="sxs-lookup"><span data-stu-id="989cb-163">When you're ready to roll out Audio Conferencing, see the in-depth [Audio Conferencing rollout](deploy-audio-conferencing-teams-landing-page.md) guidance.</span></span>

### <a name="meeting-room-and-personal-devices"></a><span data-ttu-id="989cb-164">会议室和个人设备</span><span class="sxs-lookup"><span data-stu-id="989cb-164">Meeting room and personal devices</span></span>

<span data-ttu-id="989cb-165">为了在 Teams 实现最佳会议体验，请考虑使用 Teams 设备，例如会议室系统、手机、耳机和相机。</span><span class="sxs-lookup"><span data-stu-id="989cb-165">For an optimal meeting experience in Teams, consider using Teams devices such as room systems, phones, headsets, and cameras.</span></span> <span data-ttu-id="989cb-166">若要了解详细信息，请参阅[用于智能通信的 Teams 设备](https://products.office.com/microsoft-teams/across-devices)。</span><span class="sxs-lookup"><span data-stu-id="989cb-166">To learn more, see [Teams devices for intelligent communications](https://products.office.com/microsoft-teams/across-devices).</span></span>

| <span data-ttu-id="989cb-167">询问你自己</span><span class="sxs-lookup"><span data-stu-id="989cb-167">Ask yourself</span></span> | <span data-ttu-id="989cb-168">操作</span><span class="sxs-lookup"><span data-stu-id="989cb-168">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="989cb-169">是否要为我的用户购买个人设备？</span><span class="sxs-lookup"><span data-stu-id="989cb-169">Will I purchase personal devices for my users?</span></span> |<span data-ttu-id="989cb-170">请阅读[在 Microsoft Teams 中管理设备](device-management.md)。</span><span class="sxs-lookup"><span data-stu-id="989cb-170">Read [Manage your devices in Teams](device-management.md).</span></span> |
|<span data-ttu-id="989cb-171">是否要为我的会议室购买和部署会议室系统设备？</span><span class="sxs-lookup"><span data-stu-id="989cb-171">Will I purchase and deploy room system devices for my conference rooms?</span></span>|<span data-ttu-id="989cb-172">请阅读[会议室设备和解决方案](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="989cb-172">Read [Meeting room devices and solutions](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span>|
|||

### <a name="reporting"></a><span data-ttu-id="989cb-173">报告</span><span class="sxs-lookup"><span data-stu-id="989cb-173">Reporting</span></span>

<span data-ttu-id="989cb-174">使用活动报告来查看组织中的用户使用 Teams 的情况。</span><span class="sxs-lookup"><span data-stu-id="989cb-174">Use activity reports to see how users in your organization are using Teams.</span></span> <span data-ttu-id="989cb-175">例如，如果某些用户尚未使用 Teams，他们可能不知道如何开始使用或了解如何使用 Teams 提高效率和改善协作。</span><span class="sxs-lookup"><span data-stu-id="989cb-175">For example, if some don’t use Teams yet, they might not know how to get started or understand how they can use Teams to be more productive and collaborative.</span></span> <span data-ttu-id="989cb-176">组织可以使用活动报告来决定在何处优先安排培训和沟通工作。</span><span class="sxs-lookup"><span data-stu-id="989cb-176">Your organization can use the activity reports to decide where to prioritize training and communication efforts.</span></span> 


| <span data-ttu-id="989cb-177">询问你自己</span><span class="sxs-lookup"><span data-stu-id="989cb-177">Ask yourself</span></span> | <span data-ttu-id="989cb-178">操作</span><span class="sxs-lookup"><span data-stu-id="989cb-178">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="989cb-179">谁将负责报告？</span><span class="sxs-lookup"><span data-stu-id="989cb-179">Who will be responsible for reporting?</span></span>|<span data-ttu-id="989cb-180">请阅读[使用 Teams 活动报告](teams-activity-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="989cb-180">Read [Use activity reports for Teams](teams-activity-reports.md).</span></span>  |
|<span data-ttu-id="989cb-181">谁将负责监视使用情况？</span><span class="sxs-lookup"><span data-stu-id="989cb-181">Who will be responsible for monitoring usage?</span></span>|<span data-ttu-id="989cb-182">请阅读[在 Teams 中监视使用情况和反馈](get-started-with-teams-monitor-usage-and-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="989cb-182">Read [Monitor usage and feedback in Teams](get-started-with-teams-monitor-usage-and-feedback.md).</span></span>|
|||

## <a name="additional-deployment-decisions"></a><span data-ttu-id="989cb-183">其他部署决策</span><span class="sxs-lookup"><span data-stu-id="989cb-183">Additional deployment decisions</span></span>

<span data-ttu-id="989cb-184">你可能需要根据组织的需求和配置更改这些设置。</span><span class="sxs-lookup"><span data-stu-id="989cb-184">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="bandwidth-planning"></a><span data-ttu-id="989cb-185">带宽规划</span><span class="sxs-lookup"><span data-stu-id="989cb-185">Bandwidth planning</span></span> 

<span data-ttu-id="989cb-186">带宽规划允许组织对跨广域网和 Internet 链路举行会议所需的带宽进行预估，这样他们就可以确认网络得到正确配置，可以支持横向扩展的会议服务。</span><span class="sxs-lookup"><span data-stu-id="989cb-186">Bandwidth planning lets organizations estimate the bandwidth that will be required to support meetings across their wide area networks and internet links so they can confirm that the network is correctly provisioned to support a scaled out meeting service.</span></span> 

| <span data-ttu-id="989cb-187">询问你自己</span><span class="sxs-lookup"><span data-stu-id="989cb-187">Ask yourself</span></span> | <span data-ttu-id="989cb-188">操作</span><span class="sxs-lookup"><span data-stu-id="989cb-188">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="989cb-189">是否需要在会议部署之前和部署期间进行带宽规划？</span><span class="sxs-lookup"><span data-stu-id="989cb-189">Do I need to do bandwidth planning prior to and during my Meetings rollout?</span></span> |<span data-ttu-id="989cb-190">请参阅[网络准备情况](3-envision-evaluate-my-environment.md#network-readiness)了解详细信息，并获取用于简化规划过程的工具链接。</span><span class="sxs-lookup"><span data-stu-id="989cb-190">See [Network Readiness](3-envision-evaluate-my-environment.md#network-readiness) for more information and links to tools to simplify your planning process.</span></span>|
|||

### <a name="meeting-recording-and-archiving"></a><span data-ttu-id="989cb-191">会议录制和存档</span><span class="sxs-lookup"><span data-stu-id="989cb-191">Meeting recording and archiving</span></span>

<span data-ttu-id="989cb-192">用户可以录制其会议和组内呼叫，以便捕获音频、视频和屏幕共享活动。</span><span class="sxs-lookup"><span data-stu-id="989cb-192">Users can record their meetings and group calls to capture audio, video, and screen sharing activity.</span></span> <span data-ttu-id="989cb-193">还有一个用于为录像添加自动转录功能的选项，这样用户就能够回放包含隐藏式字幕的会议录像，并在转录文本中搜索重要的讨论事项。</span><span class="sxs-lookup"><span data-stu-id="989cb-193">There is also an option for recordings to have automatic transcription, so that users can play back meeting recordings with closed captions and search for important discussion items in the transcript.</span></span> <span data-ttu-id="989cb-194">录制在云中进行，并保存在 Microsoft Stream 中，因此用户可以安全地在组织中共享录像。</span><span class="sxs-lookup"><span data-stu-id="989cb-194">The recording happens in the cloud and is saved in Microsoft Stream, so users can share it securely across their organization.</span></span> <span data-ttu-id="989cb-195">若要查找会议录像，请转到会议对话。</span><span class="sxs-lookup"><span data-stu-id="989cb-195">To find the recording for a meeting, go to the meeting conversation.</span></span>

<span data-ttu-id="989cb-196">若要了解详细信息，请参阅 [Teams 云会议录制](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="989cb-196">To learn more, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

| <span data-ttu-id="989cb-197">询问你自己</span><span class="sxs-lookup"><span data-stu-id="989cb-197">Ask yourself</span></span> | <span data-ttu-id="989cb-198">操作</span><span class="sxs-lookup"><span data-stu-id="989cb-198">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="989cb-199">是否要开启会议转录服务？</span><span class="sxs-lookup"><span data-stu-id="989cb-199">Will I turn on the meeting transcription service?</span></span>|<span data-ttu-id="989cb-200">请参阅[开启或关闭录制转录](cloud-recording.md#turn-on-or-turn-off-recording-transcription)</span><span class="sxs-lookup"><span data-stu-id="989cb-200">See [Turn on or turn off recording transcription](cloud-recording.md#turn-on-or-turn-off-recording-transcription)</span></span>|
|||


### <a name="live-events-policies"></a><span data-ttu-id="989cb-201">实时事件策略</span><span class="sxs-lookup"><span data-stu-id="989cb-201">Live events policies</span></span>

<span data-ttu-id="989cb-202">Teams 实时事件策略用于管理用户组的事件设置。</span><span class="sxs-lookup"><span data-stu-id="989cb-202">Teams live events policies are used to manage event settings for groups of users.</span></span> <span data-ttu-id="989cb-203">可以使用默认策略，或创建可分配给在组织内主持实时事件的用户的其他策略。</span><span class="sxs-lookup"><span data-stu-id="989cb-203">You can use the default policy or create additional policies that can be assigned to users who hold live events within your organization.</span></span> 

| <span data-ttu-id="989cb-204">询问你自己</span><span class="sxs-lookup"><span data-stu-id="989cb-204">Ask yourself</span></span> | <span data-ttu-id="989cb-205">操作</span><span class="sxs-lookup"><span data-stu-id="989cb-205">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="989cb-206">我的组织是否将使用 Teams 实时事件？</span><span class="sxs-lookup"><span data-stu-id="989cb-206">Will my organization use Teams live events?</span></span>| <span data-ttu-id="989cb-207">有关规划、设置和配置 Teams 实时事件的详细信息，请参阅[实时事件文章](teams-live-events/what-are-teams-live-events.md)。</span><span class="sxs-lookup"><span data-stu-id="989cb-207">See the [live events articles](teams-live-events/what-are-teams-live-events.md) for more information about planning for, setting up, and configuring Teams live events.</span></span>|
|||

### <a name="conference-room-systems-rollout"></a><span data-ttu-id="989cb-208">会议室系统部署</span><span class="sxs-lookup"><span data-stu-id="989cb-208">Conference room systems rollout</span></span>

<span data-ttu-id="989cb-209">拥有许多会议室的组织可能需要考虑采用一种结构化方法来清点其会议室、识别相应的设备，然后进行部署。</span><span class="sxs-lookup"><span data-stu-id="989cb-209">Organizations with many conference rooms may want to consider a structured approach to inventorying their rooms, identifying the appropriate devices, and then rolling them out.</span></span> 



| <span data-ttu-id="989cb-210">询问你自己</span><span class="sxs-lookup"><span data-stu-id="989cb-210">Ask yourself</span></span> | <span data-ttu-id="989cb-211">操作</span><span class="sxs-lookup"><span data-stu-id="989cb-211">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="989cb-212">我需要进行操作什么来部署会议室系统？</span><span class="sxs-lookup"><span data-stu-id="989cb-212">What do I need to do to roll out conference room systems?</span></span>|<span data-ttu-id="989cb-213">请参阅[规划 Skype Room Systems v2](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) 文章。</span><span class="sxs-lookup"><span data-stu-id="989cb-213">Check out the [Plan Skype Room Systems v2](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) articles.</span></span>|
|||

### <a name="cloud-video-interop"></a><span data-ttu-id="989cb-214">云视频互操作性</span><span class="sxs-lookup"><span data-stu-id="989cb-214">Cloud video interop</span></span>

<span data-ttu-id="989cb-215">云视频互操作性使第三方会议室设备能够加入 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="989cb-215">Cloud video interop makes it possible for third-party meeting room devices to join Teams meetings.</span></span> 

<span data-ttu-id="989cb-216">包含内容协作的视频电话会议可让你发挥会议的最大作用。</span><span class="sxs-lookup"><span data-stu-id="989cb-216">Video teleconferencing with content collaboration helps you make the most out of meetings.</span></span> <span data-ttu-id="989cb-217">但是，会议室系统和设备的升级费用非常昂贵。</span><span class="sxs-lookup"><span data-stu-id="989cb-217">However, meeting room systems and devices are expensive to upgrade.</span></span> <span data-ttu-id="989cb-218">Teams 的云视频互操作性可与第三方系统配合工作，并能为所有参与者提供本机会议体验 - 无论是在会议室中还是在 Teams 客户端内。</span><span class="sxs-lookup"><span data-stu-id="989cb-218">Cloud video interop for Teams works with third-party systems and delivers a native meeting experience for all participants – in meeting rooms or inside Teams clients.</span></span> 

| <span data-ttu-id="989cb-219">询问你自己</span><span class="sxs-lookup"><span data-stu-id="989cb-219">Ask yourself</span></span> | <span data-ttu-id="989cb-220">操作</span><span class="sxs-lookup"><span data-stu-id="989cb-220">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="989cb-221">是否要在我的会议室系统部署过程中使用云视频互操作性解决方案？</span><span class="sxs-lookup"><span data-stu-id="989cb-221">Will I use a cloud video interop solution as part of my room systems deployment?</span></span> | <span data-ttu-id="989cb-222">请阅读 [Teams 的云视频互操作性](cloud-video-interop.md)。</span><span class="sxs-lookup"><span data-stu-id="989cb-222">Read [Cloud Video Interop for Teams](cloud-video-interop.md).</span></span>|
|||


### <a name="personal-device-rollout"></a><span data-ttu-id="989cb-223">个人设备部署</span><span class="sxs-lookup"><span data-stu-id="989cb-223">Personal device rollout</span></span>

<span data-ttu-id="989cb-224">在为支持会议和语音部署规划更大规模的个人设备部署时，请考虑使用可重复的逐站点部署流程，这种流程可提供稳定可靠的质量。</span><span class="sxs-lookup"><span data-stu-id="989cb-224">When planning a larger rollout of personal devices to support meetings or voice deployments, consider using a repeatable site-by-site rollout process that delivers repeatable quality.</span></span>

| <span data-ttu-id="989cb-225">询问你自己</span><span class="sxs-lookup"><span data-stu-id="989cb-225">Ask yourself</span></span> | <span data-ttu-id="989cb-226">操作</span><span class="sxs-lookup"><span data-stu-id="989cb-226">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="989cb-227">是否要使用逐站点方法来部署会议？</span><span class="sxs-lookup"><span data-stu-id="989cb-227">Will I use a site-by-site approach to roll out Meetings?</span></span> |  <span data-ttu-id="989cb-228">[Teams 站点实现设置方案](3-onboard-deploy-my-service.md#site-enablement-playbook-for-microsoft-teams-voice-workloads)提供了良好的基础，你可将其用于自己的部署。</span><span class="sxs-lookup"><span data-stu-id="989cb-228">The [Site enablement playbook for Teams](3-onboard-deploy-my-service.md#site-enablement-playbook-for-microsoft-teams-voice-workloads) provides a good foundation that you can use for your own deployments.</span></span> <span data-ttu-id="989cb-229">该指南侧重于语音，但有关设备交付、帐户准备、采用和培训的一般原则适用于大型会议部署。</span><span class="sxs-lookup"><span data-stu-id="989cb-229">The guide is focused on voice, but the general principles of device delivery, account readiness, adoption, and training apply to a large meeting deployment.</span></span> |
|||

### <a name="troubleshoot-meeting-and-call-quality"></a><span data-ttu-id="989cb-230">会议和通话质量疑难解答</span><span class="sxs-lookup"><span data-stu-id="989cb-230">Troubleshoot meeting and call quality</span></span> 

<span data-ttu-id="989cb-231">Teams 提供两种用于监视和排除通话质量问题的方法：[通话分析和通话质量仪表板](difference-between-call-analytics-and-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="989cb-231">Teams gives you two ways to monitor and troubleshoot call quality problems: [Call Analytics and Call Quality Dashboard](difference-between-call-analytics-and-call-quality-dashboard.md).</span></span> <span data-ttu-id="989cb-232">通话分析显示有关与每个用户的特定通话和会议相关的设备、网络和连接的详细信息。</span><span class="sxs-lookup"><span data-stu-id="989cb-232">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user.</span></span> <span data-ttu-id="989cb-233">通话分析旨在帮助管理员和技术支持人员解决特定通话的通话质量问题，而通话质量仪表板旨在帮助管理员和网络工程师优化网络。</span><span class="sxs-lookup"><span data-stu-id="989cb-233">Call Analytics is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, whereas the Call Quality Dashboard is designed to help admins and network engineers optimize a network.</span></span> <span data-ttu-id="989cb-234">通话质量仪表板关注的不是特定用户，而是整个 Teams 组织的聚合信息。</span><span class="sxs-lookup"><span data-stu-id="989cb-234">Call Quality Dashboard shifts focus from specific users and instead looks at aggregate information for an entire Teams organization.</span></span> 

|<span data-ttu-id="989cb-235">询问你自己</span><span class="sxs-lookup"><span data-stu-id="989cb-235">Ask yourself</span></span>|<span data-ttu-id="989cb-236">操作</span><span class="sxs-lookup"><span data-stu-id="989cb-236">Action</span></span> |
|------------|-------|
| <span data-ttu-id="989cb-237">谁将负责监视和排查通话质量问题？</span><span class="sxs-lookup"><span data-stu-id="989cb-237">Who will be responsible for monitoring and troubleshooting call quality issues?</span></span> | <span data-ttu-id="989cb-238">请阅读[使用通话分析来排查通话质量不良问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)，了解排查通话质量问题所需的权限级别。</span><span class="sxs-lookup"><span data-stu-id="989cb-238">Read [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md) for information about permission levels required to troubleshoot call quality issues.</span></span>|
|||

### <a name="operate-your-meetings-service"></a><span data-ttu-id="989cb-239">操作会议服务</span><span class="sxs-lookup"><span data-stu-id="989cb-239">Operate your meetings service</span></span>

<span data-ttu-id="989cb-240">请务必了解 Teams 服务的整体运行状况，以便能够在发生影响服务的任何事件时主动提醒组织中的其他人。</span><span class="sxs-lookup"><span data-stu-id="989cb-240">It’s important that you understand the overall health of the Teams service so that you can proactively alert others in your organization of any event that affects the service.</span></span> <span data-ttu-id="989cb-241">[操作我的服务](1-drive-value-operate-my-service.md)文章提供了有关服务操作的深入指引。</span><span class="sxs-lookup"><span data-stu-id="989cb-241">The [Operate my service](1-drive-value-operate-my-service.md) articles provide in-depth guidance for service operations.</span></span>

|<span data-ttu-id="989cb-242">询问你自己</span><span class="sxs-lookup"><span data-stu-id="989cb-242">Ask yourself</span></span>|<span data-ttu-id="989cb-243">操作</span><span class="sxs-lookup"><span data-stu-id="989cb-243">Action</span></span> |
|------------|-------|
|<span data-ttu-id="989cb-244">谁将在我的组织中负责管理会议服务？</span><span class="sxs-lookup"><span data-stu-id="989cb-244">Who in my organization will be responsible for managing the meetings service?</span></span> | <span data-ttu-id="989cb-245">请确保此人员具有管理会议服务所需的 Teams 管理员权限。</span><span class="sxs-lookup"><span data-stu-id="989cb-245">Make sure this person has the Teams admin permissions they need in order to manage your meetings service.</span></span> <span data-ttu-id="989cb-246">若要详细了解 Teams 管理员角色，请参阅[使用 Microsoft Teams 管理员角色来管理 Teams](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="989cb-246">To learn more about Teams administrator roles see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>|
|||


## <a name="next-steps"></a><span data-ttu-id="989cb-247">后续步骤</span><span class="sxs-lookup"><span data-stu-id="989cb-247">Next steps</span></span>
- <span data-ttu-id="989cb-248">在整个组织中[推动采用](adopt-microsoft-teams-landing-page.md)会议。</span><span class="sxs-lookup"><span data-stu-id="989cb-248">[Drive adoption](adopt-microsoft-teams-landing-page.md) of meetings & conferencing throughout your organization.</span></span>
- [<span data-ttu-id="989cb-249">添加音频会议</span><span class="sxs-lookup"><span data-stu-id="989cb-249">Add audio conferencing</span></span>](deploy-audio-conferencing-teams-landing-page.md)
- [<span data-ttu-id="989cb-250">部署云语音</span><span class="sxs-lookup"><span data-stu-id="989cb-250">Roll out cloud voice</span></span>](cloud-voice-landing-page.md)
- <span data-ttu-id="989cb-251">在 Teams 的初步部署中加入特别推荐的应用 - 例如 Planner。</span><span class="sxs-lookup"><span data-stu-id="989cb-251">Include featured apps - such as Planner - in your initial Teams rollout.</span></span> <span data-ttu-id="989cb-252">在推动 Teams 采用的过程中添加其他[应用、聊天机器人和连接器](deploy-apps-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="989cb-252">Add other [apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md) as you drive Teams adoption.</span></span>
