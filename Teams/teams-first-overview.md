---
title: 首先Microsoft Teams
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
localization_priority: Normal
search.appverid: MET150
description: 使用本指南将 Microsoft Teams作为第一个Microsoft 365或Office 365工作负荷。
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 81ecf9a0f963a1be577149c585424c140df2abd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119351"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="29743-103">首先Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="29743-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="29743-104">Microsoft Teams可帮助员工保持联系和协作，尤其是在当前前所未有的时间，远程工作是世界各地员工的真实现实。</span><span class="sxs-lookup"><span data-stu-id="29743-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="29743-105">能够聊天、召开视频会议和协作处理Office文档Teams可帮助公司保持高效。</span><span class="sxs-lookup"><span data-stu-id="29743-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="29743-106">无论是小型企业、非营利组织还是大型组织，都可以先将 Teams 作为 Microsoft 365 或 Office 365 套件中的第一个工作负荷开始使用，然后再部署任何其他 Office 应用 或服务。</span><span class="sxs-lookup"><span data-stu-id="29743-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Microsoft 365 or Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="29743-107">本文详细介绍了使用"第一步"方法Teams注意事项。</span><span class="sxs-lookup"><span data-stu-id="29743-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="29743-108">尽管Teams可能是组织的第一个云部署工作负荷，但部署Teams应是总体云部署策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="29743-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="29743-109">如果已推出其他 Microsoft 365 或 Office 365 服务，Teams 是下一个要推出 (而不是第一个) 的工作负荷，请从如何推出 Teams[开始](./deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="29743-109">If you have already rolled out other Microsoft 365 or Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out Teams](./deploy-overview.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="29743-110">从这里开始</span><span class="sxs-lookup"><span data-stu-id="29743-110">Start here</span></span>

<span data-ttu-id="29743-111">若要开始使用 Teams第一个部署，至少需要满足一些先决条件。</span><span class="sxs-lookup"><span data-stu-id="29743-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="29743-112">以下列表将显示为组织设置的位置，才能启用Teams功能：</span><span class="sxs-lookup"><span data-stu-id="29743-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="29743-113">已Microsoft 365域名Office 365组织或组织</span><span class="sxs-lookup"><span data-stu-id="29743-113">A Microsoft 365 or Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="29743-114">Azure Active Directory AAD (连接) 或类似云标识同步解决方案 - 所有必需属性与租户同步</span><span class="sxs-lookup"><span data-stu-id="29743-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="29743-115">若要了解与 AAD 同步同步的属性，请阅读[Azure AD 连接同步：同步](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)到 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="29743-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="29743-116">为用户分配了相应的用户Teams</span><span class="sxs-lookup"><span data-stu-id="29743-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="29743-117">若要了解Teams，请阅读Microsoft Teams[说明。](/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="29743-117">To understand Teams licensing, read [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="29743-118">组织的网络已准备好用于Teams</span><span class="sxs-lookup"><span data-stu-id="29743-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="29743-119">若要了解网络准备，请阅读[准备组织的网络以Teams。](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="29743-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="29743-120">允许网络访问 Exchange、Sharepoint 和 OneDrive for Business 或 Microsoft 365 Office 365：Office 365 URL 和 IP[地址范围](/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="29743-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Microsoft 365 or Office 365: [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="29743-121">在 2019 年 9 月 1 日之后创建的租户在"仅Teams模式下预配。</span><span class="sxs-lookup"><span data-stu-id="29743-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="29743-122">如果已Skype for Business Server，且租户是在 2019 年 9 月 1 日之后预配的，请联系支持人员以启用 Teams。</span><span class="sxs-lookup"><span data-stu-id="29743-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="29743-123">请确保将"组织范围的升级策略"设置为"岛模式"，然后再Teams<span class="underline"></span>许可证。</span><span class="sxs-lookup"><span data-stu-id="29743-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="29743-124">迁移起点</span><span class="sxs-lookup"><span data-stu-id="29743-124">Migration Starting points</span></span>

<span data-ttu-id="29743-125">您到 Microsoft 365 Office 365 以及 Teams 中可用的功能之旅，具体取决于您的起点以及本地 Skype for Business 或 Lync 服务器的存在。</span><span class="sxs-lookup"><span data-stu-id="29743-125">Your journey to Microsoft 365 or Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="29743-126">除了上述先决条件外，以下部分还将详细介绍基本功能和配置选项。</span><span class="sxs-lookup"><span data-stu-id="29743-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="29743-127">我们已将起点方案细分为以下主题：</span><span class="sxs-lookup"><span data-stu-id="29743-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="29743-128">**租户Teams配置**：租户和用户模式用于控制收件人的行为。</span><span class="sxs-lookup"><span data-stu-id="29743-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="29743-129">可以在租户级别或组织中用户级别分配这些设置。</span><span class="sxs-lookup"><span data-stu-id="29743-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="29743-130">若要了解有关详细信息，请阅读[与 Skype for Business](coexistence-chat-calls-presence.md)共存。</span><span class="sxs-lookup"><span data-stu-id="29743-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="29743-131">**聊天/外部** 通信Teams：聊天服务是指与组织内部或组织外部的对等或群组聊天对话。</span><span class="sxs-lookup"><span data-stu-id="29743-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="29743-132">外部通信也称为联合身份验证Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="29743-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="29743-133">**在 Teams** 创建和查看会议：用户始终可以通过 Outlook Teams 加载项创建联机会议，在用户获得许可后，PSTN 拨入功能在所有方案中均可用。</span><span class="sxs-lookup"><span data-stu-id="29743-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="29743-134">Teams Skype for Business将日历信息存储在用户的邮箱中Exchange信息。</span><span class="sxs-lookup"><span data-stu-id="29743-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="29743-135">本地Exchange服务器必须Exchange Server 2016 CU3 或Teams客户端才能与用户的邮箱交互。</span><span class="sxs-lookup"><span data-stu-id="29743-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="29743-136">如果不Exchange邮箱访问，Teams日历图标将不会显示，并且用户将无法在 Teams 客户端中查看、创建或修改会议。</span><span class="sxs-lookup"><span data-stu-id="29743-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="29743-137">呼叫功能 Teams 中的 **VoIP/PSTN：** 呼叫可以是通过 IP (VoIP) 或 PSTN (电话) 。</span><span class="sxs-lookup"><span data-stu-id="29743-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="29743-138">VoIP 连接在客户端Teams本机发生，而 PSTN 连接发生在用户拨打外部电话号码时。</span><span class="sxs-lookup"><span data-stu-id="29743-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="29743-139">Teams支持两种类型的 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="29743-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="29743-140">Microsoft 呼叫计划：当 Microsoft 提供电话基础结构（包括用户的电话号码）或直接路由配置时，客户通过会话边界控制器 (SBC) 为 Teams 用户提供电话连接。</span><span class="sxs-lookup"><span data-stu-id="29743-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="29743-141">若要了解有关详细信息，请阅读[哪种呼叫计划适合你？电话系统](calling-plan-landing-page.md)[直接路由"](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="29743-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="29743-142">**Teams团队** 协作和频道Teams：在Teams，团队是一组为了工作、项目或共同兴趣而聚在一起的人。</span><span class="sxs-lookup"><span data-stu-id="29743-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="29743-143">Teams由通道决定。</span><span class="sxs-lookup"><span data-stu-id="29743-143">Teams are made up of channels.</span></span> <span data-ttu-id="29743-144">每个频道围绕主题构建，例如"团队事件"、部门名称或只是为了娱乐。</span><span class="sxs-lookup"><span data-stu-id="29743-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="29743-145">频道是一起召开会议、进行对话以及处理文件的地方。</span><span class="sxs-lookup"><span data-stu-id="29743-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="29743-146">协作期间</span><span class="sxs-lookup"><span data-stu-id="29743-146">During collaboration</span></span>

<span data-ttu-id="29743-147">OneDrive for Business (Teams 中的 **) P2P** 文件共享：在 Teams 和频道之外，Teams 用户可以使用 OneDrive for business 或其他 P2P 共享文件程序（如 Citrix 文件、DropBox、Box 和 Google 云端硬盘）对等共享文件。</span><span class="sxs-lookup"><span data-stu-id="29743-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="29743-148">对于OneDrive，用户必须分配有SharePoint Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="29743-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="29743-149">**应用程序** 平台：应用为组织提供开箱即用的工具，以进一步Teams。</span><span class="sxs-lookup"><span data-stu-id="29743-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="29743-150">这些应用结合了由 Microsoft 提供的选项卡、消息传送扩展、连接器和机器人的功能，这些功能由第三方构建，或者由组织中的开发人员提供。</span><span class="sxs-lookup"><span data-stu-id="29743-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="29743-151">安全性和符合性 **功能：Teams** 提供广泛的信息来帮助你处理合规性领域，包括保留策略、数据丢失防护 (DLP) 、电子数据展示和通道、聊天和文件法定保留、审核日志 搜索。</span><span class="sxs-lookup"><span data-stu-id="29743-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="29743-152">若要了解有关详细信息，请阅读[中的安全性和](security-compliance-overview.md)Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="29743-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="29743-153">高级电子数据展示功能需要 E5 许可。</span><span class="sxs-lookup"><span data-stu-id="29743-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="29743-154">[比较许可选项](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。</span><span class="sxs-lookup"><span data-stu-id="29743-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="29743-155">阅读[Exchange Microsoft Teams](exchange-teams-interact.md)交互，了解方案中可用的符合性功能。</span><span class="sxs-lookup"><span data-stu-id="29743-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="29743-156">没有 **<span class="underline">Skype for Business</span>** Lync Server 的组织</span><span class="sxs-lookup"><span data-stu-id="29743-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync Server</span></span>

<span data-ttu-id="29743-157">此起点假定您的组织当前未使用 Skype for Business Lync Server，Teams将成为您的第一个应用程序，Microsoft 365或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="29743-157">This starting point assumes that your organization does not utilize Skype for Business or Lync Server currently and Teams will be your first application in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="29743-158">下表详细介绍了核心服务高级配置和Teams功能。</span><span class="sxs-lookup"><span data-stu-id="29743-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="29743-159">项目</span><span class="sxs-lookup"><span data-stu-id="29743-159">Item</span></span></th>
<th><span data-ttu-id="29743-160">注释</span><span class="sxs-lookup"><span data-stu-id="29743-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="29743-161">租户Teams配置</span><span class="sxs-lookup"><span data-stu-id="29743-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="29743-162">Teams仅模式，所有聊天和通话功能都Teams模式。</span><span class="sxs-lookup"><span data-stu-id="29743-162">Teams Only mode, all chat and calling features are in Teams Only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="29743-163">聊天/外部通信Teams</span><span class="sxs-lookup"><span data-stu-id="29743-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="29743-164">组织 (内部Microsoft 365 Office 365内部) 外部聊天通信可能来自Teams。</span><span class="sxs-lookup"><span data-stu-id="29743-164">Internal (intra Microsoft 365 or Office 365 organization) and external chat communication possible from Teams.</span></span></p>
<p><span data-ttu-id="29743-165"><em>注意：必须为外部访问配置 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="29743-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="29743-166">Skype for Business即使你没有本地或 Skype for Business 或 Microsoft 365 或 Office 365，也需要 DNS 记录，以允许与 Lync 和 Skype for Business 环境联合：</span><span class="sxs-lookup"><span data-stu-id="29743-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises, or in Microsoft 365 or Office 365, to allow federation with Lync and Skype for Business environments:</span></span><br /><span data-ttu-id="29743-167">
<a href="/office365/enterprise/external-domain-name-system-records">外部域名系统记录</a></em></span><span class="sxs-lookup"><span data-stu-id="29743-167">
<a href="/office365/enterprise/external-domain-name-system-records">External Domain Name System records</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="29743-168">在会议视图中创建和Teams</span><span class="sxs-lookup"><span data-stu-id="29743-168">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="29743-169">能够通过加载项创建内部和外部Outlook会议。</span><span class="sxs-lookup"><span data-stu-id="29743-169">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="29743-170">PSTN 拨入和拨出功能随音频会议许可证一起提供。</span><span class="sxs-lookup"><span data-stu-id="29743-170">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="29743-171">Teams日历访问Exchange 2016 CU3+ 本地部署并Exchange混合：使用混合配置向导创建<a href="/exchange/hybrid-deployment/deploy-hybrid">混合部署。</a> </span><span class="sxs-lookup"><span data-stu-id="29743-171">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a> </span></span></p>
<p><span data-ttu-id="29743-172">除了混合Exchange，Exchange OAuth 身份验证：在组织与Exchange Exchange Online <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> OAuth 身份验证"。</span><span class="sxs-lookup"><span data-stu-id="29743-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations".</span></span></p>

</p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="29743-173">通话功能</span><span class="sxs-lookup"><span data-stu-id="29743-173">Calling Features</span></span><br />
<span data-ttu-id="29743-174">VoIP/PSTN Teams</span><span class="sxs-lookup"><span data-stu-id="29743-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="29743-175">可在租户内部和外部使用 VoIP。</span><span class="sxs-lookup"><span data-stu-id="29743-175">VoIP internally and externally to the tenant is available.</span></span></p>
<p><span data-ttu-id="29743-176">PSTN 服务可以通过系统Microsoft 电话配置，还可以添加 Microsoft 呼叫计划或直接路由。</span><span class="sxs-lookup"><span data-stu-id="29743-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="29743-177">Teams和频道协作Teams</span><span class="sxs-lookup"><span data-stu-id="29743-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="29743-178">若要获得完整的体验（包括合规性功能SharePoint，需要向用户分配一个联机许可证。</span><span class="sxs-lookup"><span data-stu-id="29743-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="29743-179">无需迁移现有的本地SharePoint站点。</span><span class="sxs-lookup"><span data-stu-id="29743-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="29743-180">OneDrive for Business (P2P 文件共享) </span><span class="sxs-lookup"><span data-stu-id="29743-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="29743-181">OneDrive for Business要求用户分配SharePoint Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="29743-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="29743-182">如果没有此许可证，将不可能进行对等文件共享。</span><span class="sxs-lookup"><span data-stu-id="29743-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="29743-183">应用程序平台</span><span class="sxs-lookup"><span data-stu-id="29743-183">Application platform</span></span></td>
<td><span data-ttu-id="29743-184">用户将能够使用根据公司策略为用户指定的应用。</span><span class="sxs-lookup"><span data-stu-id="29743-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="29743-185">在此处了解有关详细信息：<a href="/microsoftteams/admin-settings">应用中应用的管理员Teams</a></span><span class="sxs-lookup"><span data-stu-id="29743-185">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="29743-186">安全性和符合性功能</span><span class="sxs-lookup"><span data-stu-id="29743-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="29743-187">保留策略可用。</span><span class="sxs-lookup"><span data-stu-id="29743-187">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="29743-188">支持电子数据展示和法定保留，以确保通道消息的符合性。</span><span class="sxs-lookup"><span data-stu-id="29743-188">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="29743-189">DLP (的) 策略可用。</span><span class="sxs-lookup"><span data-stu-id="29743-189">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="29743-190">完整功能集可用于Exchange Online;Exchange本地部署支持大多数这些功能。</span><span class="sxs-lookup"><span data-stu-id="29743-190">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="29743-191">有关完整列表，请参阅如何<a href="/MicrosoftTeams/exchange-teams-interact">Exchange Teams交互</a>。</span><span class="sxs-lookup"><span data-stu-id="29743-191">For a full list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a>.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="29743-192">为没有 Skype for Business Lync Server 的组织启用步骤</span><span class="sxs-lookup"><span data-stu-id="29743-192">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="29743-193">满足上述"从此处开始"部分中详述的先决条件</span><span class="sxs-lookup"><span data-stu-id="29743-193">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="29743-194">将租户切换到Teams仅 (租户的模式) 设置[：设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="29743-194">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="29743-195">根据公司的业务/公司策略配置租户：管理Microsoft Teams[设置](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="29743-195">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="29743-196">将Teams客户端部署到用户：[获取客户端Teams](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="29743-196">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="29743-197">推动采用计划</span><span class="sxs-lookup"><span data-stu-id="29743-197">Drive your adoption program</span></span>  
    [<span data-ttu-id="29743-198">采用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="29743-198">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="29743-199">Microsoft Teams 采用快速入门清单</span><span class="sxs-lookup"><span data-stu-id="29743-199">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="29743-200">开始计划将其他工作负荷移动到Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="29743-200">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="29743-201">使用 **<span class="underline">Skype for Business</span>** Lync 服务器的组织</span><span class="sxs-lookup"><span data-stu-id="29743-201">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="29743-202">此起点假定您的组织使用 Skype for Business 2019、2015+ 或 Lync 2013+ 本地服务器。</span><span class="sxs-lookup"><span data-stu-id="29743-202">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="29743-203">我们已经为组织从本地服务器迁移到 Teams提供了广泛的指导，这些方案应该遵循这些指南。</span><span class="sxs-lookup"><span data-stu-id="29743-203">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="29743-204">本指南特定于以下方案：Teams是首次在应用或Microsoft 365 Office 365。</span><span class="sxs-lookup"><span data-stu-id="29743-204">This guidance is specific to the scenario that Teams is the first application you utilize in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="29743-205">下表详细介绍了核心服务高级配置和Teams功能。</span><span class="sxs-lookup"><span data-stu-id="29743-205">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="29743-206">项目</span><span class="sxs-lookup"><span data-stu-id="29743-206">Item</span></span></th>
<th><span data-ttu-id="29743-207">注释</span><span class="sxs-lookup"><span data-stu-id="29743-207">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="29743-208">租户Teams配置</span><span class="sxs-lookup"><span data-stu-id="29743-208">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="29743-209">岛屿模式。</span><span class="sxs-lookup"><span data-stu-id="29743-209">Islands mode.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="29743-210">聊天/外部通信Teams</span><span class="sxs-lookup"><span data-stu-id="29743-210">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="29743-211">仅在您自己的租户内部，外部通信 (联合) 通过您的 Skype for Business Lync 服务器部署。</span><span class="sxs-lookup"><span data-stu-id="29743-211">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="29743-212">在会议视图中创建和Teams</span><span class="sxs-lookup"><span data-stu-id="29743-212">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="29743-213">能够通过加载项创建内部和外部Outlook会议。</span><span class="sxs-lookup"><span data-stu-id="29743-213">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="29743-214">PSTN 拨入和拨出功能随音频会议许可证一起提供。</span><span class="sxs-lookup"><span data-stu-id="29743-214">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="29743-215">Teams日历访问Exchange 2016 CU3+ 本地部署，并且Exchange混合：</span><span class="sxs-lookup"><span data-stu-id="29743-215">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="29743-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">使用混合配置向导创建混合部署。</a></span><span class="sxs-lookup"><span data-stu-id="29743-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a></span></span></p>
<p><span data-ttu-id="29743-217">管理员可以 Skype for Business Outlook通过 Teams 会议策略的 PreferredMeetingProviderForIslandsMode 属性<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps">set-csteamsmeetingpolicy</a>控制该加载项。</span><span class="sxs-lookup"><span data-stu-id="29743-217">Administrator can control the Skype for Business Outlook add-in via the Teams meeting policy’s PreferredMeetingProviderForIslandsMode attribute:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span></span></p> 
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="29743-218">通话功能</span><span class="sxs-lookup"><span data-stu-id="29743-218">Calling Features</span></span><br />
<span data-ttu-id="29743-219">VoIP/PSTN Teams</span><span class="sxs-lookup"><span data-stu-id="29743-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="29743-220">可在租户内部使用 VoIP。</span><span class="sxs-lookup"><span data-stu-id="29743-220">VoIP internally to the tenant is available.</span></span></p>
<p><span data-ttu-id="29743-221">PSTN 或呼叫计划服务在用户移动到仅Teams之前不可用。</span><span class="sxs-lookup"><span data-stu-id="29743-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="29743-222">Teams和频道协作Teams</span><span class="sxs-lookup"><span data-stu-id="29743-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="29743-223">若要获得完整的体验（包括合规性功能SharePoint，需要向用户分配一个联机许可证。</span><span class="sxs-lookup"><span data-stu-id="29743-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="29743-224">无需迁移现有的本地SharePoint站点。</span><span class="sxs-lookup"><span data-stu-id="29743-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="29743-225">OneDrive for Business (P2P 文件共享) </span><span class="sxs-lookup"><span data-stu-id="29743-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="29743-226">OneDrive for Business要求用户分配SharePoint Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="29743-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="29743-227">如果没有此许可证，将不可能进行每对等文件共享。</span><span class="sxs-lookup"><span data-stu-id="29743-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="29743-228">应用程序平台</span><span class="sxs-lookup"><span data-stu-id="29743-228">Application platform</span></span></td>
<td><span data-ttu-id="29743-229">用户将能够使用根据公司策略为用户指定的应用。</span><span class="sxs-lookup"><span data-stu-id="29743-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="29743-230">在此处了解有关详细信息：<a href="/microsoftteams/admin-settings">应用中应用的管理员Teams</a></span><span class="sxs-lookup"><span data-stu-id="29743-230">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="29743-231">安全性和符合性功能</span><span class="sxs-lookup"><span data-stu-id="29743-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="29743-232">保留策略可用。</span><span class="sxs-lookup"><span data-stu-id="29743-232">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="29743-233">支持电子数据展示和法定保留，以确保通道消息的符合性。</span><span class="sxs-lookup"><span data-stu-id="29743-233">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="29743-234">DLP (的) 策略可用。</span><span class="sxs-lookup"><span data-stu-id="29743-234">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="29743-235">完整功能集可用于Exchange Online;Exchange本地部署支持大多数这些功能。</span><span class="sxs-lookup"><span data-stu-id="29743-235">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="29743-236">有关完整列表，请参阅如何<a href="/MicrosoftTeams/exchange-teams-interact">Exchange Teams交互。</a></span><span class="sxs-lookup"><span data-stu-id="29743-236">For a complete list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact.</a></span></span></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="29743-237">为具有以下功能的组织启用Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="29743-237">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="29743-238">满足上述"从此处开始"部分中详述的先决条件。</span><span class="sxs-lookup"><span data-stu-id="29743-238">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="29743-239">对于在 2019 年 9 月 1 (预配的租户，请将租户切换为"群岛模式"模式，请联系支持人员) </span><span class="sxs-lookup"><span data-stu-id="29743-239">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="29743-240">设置共存和升级设置</span><span class="sxs-lookup"><span data-stu-id="29743-240">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="29743-241">根据公司的业务/公司策略配置租户</span><span class="sxs-lookup"><span data-stu-id="29743-241">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="29743-242">为你的组织管理 Microsoft Teams 设置</span><span class="sxs-lookup"><span data-stu-id="29743-242">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="29743-243">部署 Teams 客户端</span><span class="sxs-lookup"><span data-stu-id="29743-243">Deploy the Teams client</span></span>  
    [<span data-ttu-id="29743-244">获取 Teams 客户端</span><span class="sxs-lookup"><span data-stu-id="29743-244">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="29743-245">推动采用计划</span><span class="sxs-lookup"><span data-stu-id="29743-245">Drive your adoption program</span></span>  
    [<span data-ttu-id="29743-246">采用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="29743-246">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="29743-247">Microsoft Teams 采用快速入门清单</span><span class="sxs-lookup"><span data-stu-id="29743-247">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="29743-248">开始计划将其他工作负荷移动到Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="29743-248">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

7.  <span data-ttu-id="29743-249">建立Skype for Business混合，并遵循针对 Skype for Business 和 Lync 服务器的建议升级路径</span><span class="sxs-lookup"><span data-stu-id="29743-249">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="29743-250">从Skype for Business本地升级到 Teams</span><span class="sxs-lookup"><span data-stu-id="29743-250">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="29743-251">结束语句</span><span class="sxs-lookup"><span data-stu-id="29743-251">Closing statement</span></span>

<span data-ttu-id="29743-252">Microsoft Teams组织能够将所有员工、信息工作者和一线员工汇集在一个平台上。</span><span class="sxs-lookup"><span data-stu-id="29743-252">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Frontline workers, together on a single platform.</span></span> <span data-ttu-id="29743-253">你可以 [从今天开始](https://products.office.com/microsoft-teams/group-chat-software) 。</span><span class="sxs-lookup"><span data-stu-id="29743-253">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="29743-254">你可以在此处联系我们的所有最新公告和每月产品 [更新](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)。</span><span class="sxs-lookup"><span data-stu-id="29743-254">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="29743-255">此外，随着世界各地的公司正在管理当前的 COVID-19 情况，我们创建了一系列内容来帮助你利用 Teams，以在组织中产生最大影响。</span><span class="sxs-lookup"><span data-stu-id="29743-255">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="29743-256">我们在[COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)期间为客户提供的承诺</span><span class="sxs-lookup"><span data-stu-id="29743-256">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="29743-257">2 周内：我们已了解远程工作</span><span class="sxs-lookup"><span data-stu-id="29743-257">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="29743-258">传送联机会议和事件</span><span class="sxs-lookup"><span data-stu-id="29743-258">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="29743-259">协助中小型企业使用 Teams 远程工作</span><span class="sxs-lookup"><span data-stu-id="29743-259">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="29743-260">实时事件的数字化转换：Bob Bejan 从一线观察结果</span><span class="sxs-lookup"><span data-stu-id="29743-260">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="29743-261">Microsoft IT 便于员工远程工作的 9 大方式</span><span class="sxs-lookup"><span data-stu-id="29743-261">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="29743-262">远程工作，保持安全 - 有关 CISOS 的提示</span><span class="sxs-lookup"><span data-stu-id="29743-262">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="29743-263">帮助教师和学生转换远程学习</span><span class="sxs-lookup"><span data-stu-id="29743-263">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="29743-264">使用远程处理设备时保持Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="29743-264">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="29743-265">支持服务参考</span><span class="sxs-lookup"><span data-stu-id="29743-265">Support Services reference</span></span>

<span data-ttu-id="29743-266">Teams依赖于 Exchange Online、SharePoint Online、OneDrive for Business Microsoft 365 组为用户提供完全集成的 Microsoft 365 或 Office 365 体验。</span><span class="sxs-lookup"><span data-stu-id="29743-266">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Microsoft 365 or Office 365 experience.</span></span> <span data-ttu-id="29743-267">如上所述，Teams完全部署这些服务（功能有限）即可正常工作。</span><span class="sxs-lookup"><span data-stu-id="29743-267">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="29743-268">可以在此处阅读有关Teams及其先决条件的更多信息：[欢迎使用 Teams。](teams-overview.md)</span><span class="sxs-lookup"><span data-stu-id="29743-268">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="29743-269">有关上面列出的每个服务的详细信息，请访问以下链接：</span><span class="sxs-lookup"><span data-stu-id="29743-269">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="29743-270">Exchange Online用于日历功能，以及将对等消息存储在 Teams。</span><span class="sxs-lookup"><span data-stu-id="29743-270">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="29743-271">有关详细信息，请阅读如何[Exchange Teams交互](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="29743-271">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="29743-272">若要Teams本地 Exchange 的互操作，必须配置新的 Exchange OAuth 身份验证协议，如在 Exchange 和 Exchange Online 组织之间配置[OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)身份验证中所述。</span><span class="sxs-lookup"><span data-stu-id="29743-272">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="29743-273">SharePoint用于频道中的文件共享，而 /OneDrive for Business 用于 1：1 或群组聊天中的文件共享。</span><span class="sxs-lookup"><span data-stu-id="29743-273">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="29743-274">若要了解有关详细信息，请阅读[如何SharePoint联机OneDrive for Business如何与 Microsoft Teams](sharepoint-onedrive-interact.md)交互。</span><span class="sxs-lookup"><span data-stu-id="29743-274">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="29743-275">[Microsoft 365组](office-365-groups.md)用于团队和频道创建/管理。</span><span class="sxs-lookup"><span data-stu-id="29743-275">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="29743-276">相关主题</span><span class="sxs-lookup"><span data-stu-id="29743-276">Related topics</span></span>

[<span data-ttu-id="29743-277">Microsoft Teams IT 体系结构和电话解决方案海报</span><span class="sxs-lookup"><span data-stu-id="29743-277">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="29743-278">规划 Skype for Business Server 与 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="29743-278">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="29743-279">使用远程工作程序支持Teams</span><span class="sxs-lookup"><span data-stu-id="29743-279">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="29743-280">远程处理Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="29743-280">Work remotely with Microsoft 365</span></span>](https://aka.ms/remote-work)