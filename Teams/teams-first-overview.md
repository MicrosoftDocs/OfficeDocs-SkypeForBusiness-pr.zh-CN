---
title: 首先部署 Microsoft 团队
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
description: 使用本指南可以将 Microsoft 团队作为您的第一个 Office 365 工作负荷。
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2cd8fc92d3f46df8bcfaa07a96b69b84790750aa
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44041709"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="84894-103">首先部署 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="84894-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="84894-104">Microsoft 团队可以帮助你的员工彼此保持联系并协作，尤其是在当前空前的时间，远程工作是世界各地员工的现实。</span><span class="sxs-lookup"><span data-stu-id="84894-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="84894-105">能够聊天、进行视频会议和协作处理团队中的 Office 文档可帮助公司保持高效。</span><span class="sxs-lookup"><span data-stu-id="84894-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="84894-106">无论您是小型企业、非盈利性组织还是大型组织，您都可以在部署任何其他 Office 应用或服务之前，开始将团队作为 Office 365 套件中的第一工作负荷。</span><span class="sxs-lookup"><span data-stu-id="84894-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="84894-107">本文详细介绍了 "团队优先" 方法中必须执行的注意事项。</span><span class="sxs-lookup"><span data-stu-id="84894-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84894-108">尽管团队可以是你的组织的第一个云部署工作负载，但部署团队应该是整体云部署策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="84894-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="84894-109">如果你已推出其他 Office 365 服务，并且团队是你要推出的下一个工作负荷（而不是第一个），请首先向[团队推出](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="84894-109">If you have already rolled out other Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out  Teams](How-to-roll-out-teams.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="84894-110">从这里开始</span><span class="sxs-lookup"><span data-stu-id="84894-110">Start here</span></span>

<span data-ttu-id="84894-111">若要开始使用你的团队首次部署，你需要至少满足某些预备先决条件。</span><span class="sxs-lookup"><span data-stu-id="84894-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="84894-112">以下列表将显示在启用团队之前你必须为你的组织设置的内容：</span><span class="sxs-lookup"><span data-stu-id="84894-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="84894-113">使用您的域名配置的 Office 365 组织</span><span class="sxs-lookup"><span data-stu-id="84894-113">An Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="84894-114">Azure Active Directory 连接（AAD connect）或类似的云标识同步解决方案-与你的租户同步的所有必需属性</span><span class="sxs-lookup"><span data-stu-id="84894-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="84894-115">若要了解与 AAD 同步同步的属性，请参阅[AZURE AD Connect 同步：属性同步到 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span><span class="sxs-lookup"><span data-stu-id="84894-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="84894-116">为团队分配的相应用户许可证</span><span class="sxs-lookup"><span data-stu-id="84894-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="84894-117">若要了解团队许可，请阅读[Microsoft 团队服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="84894-117">To understand Teams licensing, read [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="84894-118">为团队准备的组织网络</span><span class="sxs-lookup"><span data-stu-id="84894-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="84894-119">若要了解网络准备，请阅读为[团队准备组织的网络](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="84894-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="84894-120">允许 Office 365 中的 Exchange、Sharepoint 和 OneDrive for business 的网络访问： [office 365 url 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="84894-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Office 365: [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="84894-121">在2019年9月1日之后创建的租户将在 "仅团队" 模式下预配。</span><span class="sxs-lookup"><span data-stu-id="84894-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="84894-122">如果你已部署 Skype for Business 服务器，并且你的租户是在2019年9月1日之后预配的，请联系支持人员以启用团队的共存功能。</span><span class="sxs-lookup"><span data-stu-id="84894-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="84894-123">在向用户分配任何团队许可证<span class="underline">之前</span>，请确保 "组织范围升级策略" 已设置为 "安全岛模式"。</span><span class="sxs-lookup"><span data-stu-id="84894-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="84894-124">迁移起始点</span><span class="sxs-lookup"><span data-stu-id="84894-124">Migration Starting points</span></span>

<span data-ttu-id="84894-125">根据您的起点和在本地 Skype for business 或 Lync server 的存在，您可以在团队中使用 Office 365 和功能。</span><span class="sxs-lookup"><span data-stu-id="84894-125">Your journey to Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="84894-126">除了上述先决条件之外，以下部分还将详细介绍基本功能和配置选项。</span><span class="sxs-lookup"><span data-stu-id="84894-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="84894-127">我们已将起始点方案分解为以下主题：</span><span class="sxs-lookup"><span data-stu-id="84894-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="84894-128">**租户团队配置**：租户和用户模式用于控制收件人的行为。</span><span class="sxs-lookup"><span data-stu-id="84894-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="84894-129">可以在组织中的租户级别或用户级别分配这些设置。</span><span class="sxs-lookup"><span data-stu-id="84894-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="84894-130">若要了解详细信息，请阅读[Skype For Business 共存](coexistence-chat-calls-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="84894-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="84894-131">**团队中的聊天/外部通信**：聊天服务指的是与组织内或外部组织内的对等或群组聊天对话。</span><span class="sxs-lookup"><span data-stu-id="84894-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="84894-132">外部通信也称为 "Skype for Business" 中的联盟。</span><span class="sxs-lookup"><span data-stu-id="84894-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="84894-133">**在团队中创建和查看会议**：用户随时可以通过 Outlook 团队外接程序和 PSTN 拨入功能创建联机会议。一旦用户获得许可，即可在所有方案中使用。</span><span class="sxs-lookup"><span data-stu-id="84894-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="84894-134">用户的 Exchange 邮箱中的团队和 Skype for business 存储日历信息。</span><span class="sxs-lookup"><span data-stu-id="84894-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="84894-135">本地 Exchange server 必须是 Exchange Server 2016 CU3 或更高版本才能使团队客户能够与用户的邮箱交互。</span><span class="sxs-lookup"><span data-stu-id="84894-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="84894-136">没有 Exchange 邮箱访问时，不会显示团队中的日历图标，用户将无法在团队客户端中查看、创建或修改会议。</span><span class="sxs-lookup"><span data-stu-id="84894-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="84894-137">**呼叫功能团队中的 VoIP/PSTN**：通话可通过 IP 语音（VoIP）或公共交换电话网络（PSTN）进行。</span><span class="sxs-lookup"><span data-stu-id="84894-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="84894-138">VoIP 连接在团队客户端之间进行，而 PSTN 连接在用户拨打外部电话号码时才会发生。</span><span class="sxs-lookup"><span data-stu-id="84894-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="84894-139">团队支持两种类型的 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="84894-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="84894-140">Microsoft 通话计划-当 Microsoft 为团队用户提供电话服务基础结构（包括用户的电话号码）或直接路由配置时，客户通过会话边界控制器（SBC）为团队用户提供电话连接。</span><span class="sxs-lookup"><span data-stu-id="84894-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="84894-141">若要了解详细信息，请阅读适合[你的呼叫计划？](calling-plan-landing-page.md)和[手机系统直接路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="84894-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="84894-142">团队**中的团队和渠道协作**：在团队中，团队是为工作、项目或常见兴趣共同工作的人员组。</span><span class="sxs-lookup"><span data-stu-id="84894-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="84894-143">团队由频道组成。</span><span class="sxs-lookup"><span data-stu-id="84894-143">Teams are made up of channels.</span></span> <span data-ttu-id="84894-144">每个频道都围绕一个主题构建，如 "团队活动"、"部门名称" 或 "只是有趣"。</span><span class="sxs-lookup"><span data-stu-id="84894-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="84894-145">频道是您在其中举行会议、进行对话和协同处理文件的地方。</span><span class="sxs-lookup"><span data-stu-id="84894-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="84894-146">协作期间</span><span class="sxs-lookup"><span data-stu-id="84894-146">During collaboration</span></span>

<span data-ttu-id="84894-147">**工作组中的 OneDrive For business （P2P 文件共享）**：团队和频道外，团队用户可以使用 OneDrive for business 或其他 P2P 共享文件程序（如 Citrix 文件、DropBox、Box 和 Google 驱动器）共享文件对等。</span><span class="sxs-lookup"><span data-stu-id="84894-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="84894-148">对于 OneDrive for business，用户必须分配有 SharePoint Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="84894-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="84894-149">**应用程序平台**：应用为你的组织提供现成的工具，以充分利用团队。</span><span class="sxs-lookup"><span data-stu-id="84894-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="84894-150">这些应用结合由 Microsoft （由第三方构建）或您的组织中的开发人员提供的选项卡、消息扩展、连接器和 bot 的功能。</span><span class="sxs-lookup"><span data-stu-id="84894-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="84894-151">**安全性和合规性功能：** 团队有大量信息可帮助您处理合规性领域，包括保留策略、数据丢失保护（DLP）、电子数据展示和用于频道、聊天和文件的法律封存、审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="84894-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="84894-152">若要了解详细信息，请阅读[Microsoft 团队中的安全和合规性](security-compliance-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="84894-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="84894-153">提前的电子数据展示功能需要 E5 许可。</span><span class="sxs-lookup"><span data-stu-id="84894-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="84894-154">[比较授权选项](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。</span><span class="sxs-lookup"><span data-stu-id="84894-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="84894-155">了解[Exchange 和 Microsoft 团队如何交互](exchange-teams-interact.md)，以了解你的方案中提供了哪些合规性功能。</span><span class="sxs-lookup"><span data-stu-id="84894-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="84894-156">**<span class="underline">没有</span>** Skype for Business 或 Lync 服务器的组织</span><span class="sxs-lookup"><span data-stu-id="84894-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="84894-157">此起始点假定你的组织不利用 Skype for Business 或 Lync server，当前和团队将是 Office 365 中的第一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="84894-157">This starting point assumes that your organization does not utilize Skype for Business or Lync server currently and Teams will be your first application in Office 365.</span></span> <span data-ttu-id="84894-158">下表详细介绍了适用于核心服务的团队的高级配置和最终用户功能。</span><span class="sxs-lookup"><span data-stu-id="84894-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="84894-159">项目</span><span class="sxs-lookup"><span data-stu-id="84894-159">Item</span></span></th>
<th><span data-ttu-id="84894-160">注释</span><span class="sxs-lookup"><span data-stu-id="84894-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="84894-161">租户团队配置</span><span class="sxs-lookup"><span data-stu-id="84894-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="84894-162">仅限工作组模式，所有聊天和通话功能仅在团队中</span><span class="sxs-lookup"><span data-stu-id="84894-162">Teams Only mode, all chat and calling features are in Teams Only</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84894-163">团队中的聊天/外部通信</span><span class="sxs-lookup"><span data-stu-id="84894-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="84894-164">内部（Office 365 内部组织）和团队外部聊天通信</span><span class="sxs-lookup"><span data-stu-id="84894-164">Internal (intra Office 365 organization) and external chat communication possible from Teams</span></span></p>
<p><span data-ttu-id="84894-165"><em>注意：必须为外部访问配置 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="84894-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="84894-166">即使您在本地或 Office 365 中没有 Skype for business，也可以使用 skype for business DNS 记录来允许与 Lync 和 Skype for business 环境进行联盟。</span><span class="sxs-lookup"><span data-stu-id="84894-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises or in Office 365 to allow federation with Lync and Skype for Business environments.</span></span><br /><span data-ttu-id="84894-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Office 365 的外部域名系统记录</a></em></span><span class="sxs-lookup"><span data-stu-id="84894-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">External Domain Name System records for Office 365</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="84894-168"><em>在团队中创建和查看会议</em></span><span class="sxs-lookup"><span data-stu-id="84894-168"><em>Create and view Meetings in Teams</em></span></span></td>
<td><p><span data-ttu-id="84894-169"><em>能够通过 Outlook 加载项创建会议</em></span><span class="sxs-lookup"><span data-stu-id="84894-169"><em>Able to create meetings via Outlook add-in</em></span></span></p>
<p><span data-ttu-id="84894-170"><em>可通过音频会议许可证使用 PSTN 拨入和拨出功能。</span><span class="sxs-lookup"><span data-stu-id="84894-170"><em>PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span><br />
<span data-ttu-id="84894-171">注意：团队日历访问需要部署了 exchange 2016 CU3 + 本地部署和已建立的 Exchange 混合版：<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">使用混合配置向导创建混合部署</a></span><span class="sxs-lookup"><span data-stu-id="84894-171">Note: Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard</a></span></span><br />
<span data-ttu-id="84894-172">除了 Exchange 混合配置之外，建立 Exchange OAuth 身份验证：在<a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Exchange 和 Exchange Online 组织之间配置 OAuth 身份验证</a></em></span><span class="sxs-lookup"><span data-stu-id="84894-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations</a></em></span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84894-173">通话功能</span><span class="sxs-lookup"><span data-stu-id="84894-173">Calling Features</span></span><br />
<span data-ttu-id="84894-174">团队中的 VoIP/PSTN</span><span class="sxs-lookup"><span data-stu-id="84894-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="84894-175">可在租户内部和外部使用 VoIP</span><span class="sxs-lookup"><span data-stu-id="84894-175">VoIP internally and externally to the tenant is available</span></span></p>
<p><span data-ttu-id="84894-176">PSTN 服务可以通过 Microsoft Phone 系统进行配置，还可以添加 Microsoft 通话计划或直接路由。</span><span class="sxs-lookup"><span data-stu-id="84894-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="84894-177">团队中的团队和渠道协作</span><span class="sxs-lookup"><span data-stu-id="84894-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="84894-178">若要获得完整体验，包括合规性功能，需要向用户分配 SharePoint Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="84894-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="84894-179">不需要迁移现有的本地 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="84894-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84894-180">OneDrive for Business （P2P 文件共享）</span><span class="sxs-lookup"><span data-stu-id="84894-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="84894-181">OneDrive for business 要求用户分配有 SharePoint Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="84894-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="84894-182">不能进行此类许可证对等文件共享。</span><span class="sxs-lookup"><span data-stu-id="84894-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="84894-183">应用程序平台</span><span class="sxs-lookup"><span data-stu-id="84894-183">Application platform</span></span></td>
<td><span data-ttu-id="84894-184">用户将能够根据你的公司策略使用指定的适用应用。</span><span class="sxs-lookup"><span data-stu-id="84894-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="84894-185">在此了解详细信息：<a href="https://docs.microsoft.com/microsoftteams/admin-settings">团队中的应用的管理员设置</a></span><span class="sxs-lookup"><span data-stu-id="84894-185">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84894-186">安全性和合规性功能</span><span class="sxs-lookup"><span data-stu-id="84894-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="84894-187">保留策略可用</span><span class="sxs-lookup"><span data-stu-id="84894-187">Retention policies are available</span></span></p></li>
<li><p><span data-ttu-id="84894-188">支持针对频道消息的电子数据展示和法律封存</span><span class="sxs-lookup"><span data-stu-id="84894-188">eDiscovery and Legal Hold for compliance on channel messages is supported</span></span></p></li>
<li><p><span data-ttu-id="84894-189">数据丢失防护策略（DLP）可用</span><span class="sxs-lookup"><span data-stu-id="84894-189">Data Loss Prevention policies (DLP) are available</span></span></p></li>
</ul>
<p><span data-ttu-id="84894-190">完整功能集通过 Exchange Online 提供，本地 Exchange 支持这些功能中的大部分，请参阅</span><span class="sxs-lookup"><span data-stu-id="84894-190">Full feature set available with Exchange Online, Exchange on-premises supports most of these features, see</span></span></p>
<p><span data-ttu-id="84894-191"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Exchange 与 Teams 如何交互</a></span><span class="sxs-lookup"><span data-stu-id="84894-191"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a></span></span></p>
<p><span data-ttu-id="84894-192">对于完整列表</span><span class="sxs-lookup"><span data-stu-id="84894-192">for full list</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="84894-193">没有 Skype for Business 或 Lync Server 的组织的启用步骤</span><span class="sxs-lookup"><span data-stu-id="84894-193">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="84894-194">在上面的 "开始" 部分中，了解有关先决条件的详细信息</span><span class="sxs-lookup"><span data-stu-id="84894-194">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="84894-195">将租户切换到 "仅限团队" 模式（仅适用于现有租户）：[设置你的共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="84894-195">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="84894-196">根据公司的业务/公司策略配置你的租户：[管理你的组织的 Microsoft 团队设置](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="84894-196">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="84894-197">将团队客户端部署到你的用户：[获取团队客户端](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="84894-197">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="84894-198">推动你的采纳计划</span><span class="sxs-lookup"><span data-stu-id="84894-198">Drive your adoption program</span></span>  
    [<span data-ttu-id="84894-199">采用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84894-199">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="84894-200">Microsoft Teams 采用快速入门清单</span><span class="sxs-lookup"><span data-stu-id="84894-200">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="84894-201">开始规划将其他工作负荷移动到 Office 365</span><span class="sxs-lookup"><span data-stu-id="84894-201">Begin planning moving other workloads to Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="84894-202">具有 Skype for Business 或 Lync 服务器**<span class="underline">的</span>** 组织</span><span class="sxs-lookup"><span data-stu-id="84894-202">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="84894-203">此起始点假定你的组织使用 Skype for Business 2019 或 2015 + 或 Lync 2013 + server 内部部署。</span><span class="sxs-lookup"><span data-stu-id="84894-203">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="84894-204">对于从本地服务器迁移到团队的组织，我们已经有了详细指南，应遵循这些方案。</span><span class="sxs-lookup"><span data-stu-id="84894-204">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="84894-205">本指南特定于团队是你在 Office 365 中使用的第一个应用程序的方案。</span><span class="sxs-lookup"><span data-stu-id="84894-205">This guidance is specific to the scenario that Teams is the first application you utilize in Office 365.</span></span> <span data-ttu-id="84894-206">下表详细介绍了适用于核心服务的团队的高级配置和最终用户功能。</span><span class="sxs-lookup"><span data-stu-id="84894-206">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="84894-207">项目</span><span class="sxs-lookup"><span data-stu-id="84894-207">Item</span></span></th>
<th><span data-ttu-id="84894-208">注释</span><span class="sxs-lookup"><span data-stu-id="84894-208">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="84894-209">租户团队配置</span><span class="sxs-lookup"><span data-stu-id="84894-209">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="84894-210">孤岛模式</span><span class="sxs-lookup"><span data-stu-id="84894-210">Islands mode</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84894-211">团队中的聊天/外部通信</span><span class="sxs-lookup"><span data-stu-id="84894-211">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="84894-212">仅限内部租户，外部通信（联合）通过 Skype for Business 或 Lync server 部署</span><span class="sxs-lookup"><span data-stu-id="84894-212">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="84894-213">在团队中创建和查看会议</span><span class="sxs-lookup"><span data-stu-id="84894-213">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="84894-214">能够通过 Outlook 加载项创建会议</span><span class="sxs-lookup"><span data-stu-id="84894-214">Able to create meetings via Outlook add-in</span></span></p>
<p><span data-ttu-id="84894-215">可通过音频会议许可证使用 PSTN 拨入和拨出功能。</span><span class="sxs-lookup"><span data-stu-id="84894-215">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span><br />
<span data-ttu-id="84894-216">团队日历访问需要 Exchange 2016 CU3 + 本地部署，并已建立 Exchange 混合版：</span><span class="sxs-lookup"><span data-stu-id="84894-216">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="84894-217">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">使用混合配置向导创建混合部署</a></span><span class="sxs-lookup"><span data-stu-id="84894-217">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard</a></span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84894-218">通话功能</span><span class="sxs-lookup"><span data-stu-id="84894-218">Calling Features</span></span><br />
<span data-ttu-id="84894-219">团队中的 VoIP/PSTN</span><span class="sxs-lookup"><span data-stu-id="84894-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="84894-220">租户内部的 VoIP 可用</span><span class="sxs-lookup"><span data-stu-id="84894-220">VoIP internally to the tenant is available</span></span></p>
<p><span data-ttu-id="84894-221">PSTN 或通话计划服务不可用，直到用户移动到团队仅体验</span><span class="sxs-lookup"><span data-stu-id="84894-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="84894-222">团队中的团队和渠道协作</span><span class="sxs-lookup"><span data-stu-id="84894-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="84894-223">若要获得完整体验，包括合规性功能，需要向用户分配 SharePoint Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="84894-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="84894-224">不需要迁移现有的本地 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="84894-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84894-225">OneDrive for Business （P2P 文件共享）</span><span class="sxs-lookup"><span data-stu-id="84894-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="84894-226">OneDrive for business 要求用户分配有 SharePoint Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="84894-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="84894-227">不能进行这种许可证的每对等文件共享。</span><span class="sxs-lookup"><span data-stu-id="84894-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="84894-228">应用程序平台</span><span class="sxs-lookup"><span data-stu-id="84894-228">Application platform</span></span></td>
<td><span data-ttu-id="84894-229">用户将能够根据你的公司策略使用指定的适用应用。</span><span class="sxs-lookup"><span data-stu-id="84894-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="84894-230">在此了解详细信息：<a href="https://docs.microsoft.com/microsoftteams/admin-settings">团队中的应用的管理员设置</a></span><span class="sxs-lookup"><span data-stu-id="84894-230">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84894-231">安全性和合规性功能</span><span class="sxs-lookup"><span data-stu-id="84894-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="84894-232">保留策略可用</span><span class="sxs-lookup"><span data-stu-id="84894-232">Retention policies are available</span></span></p></li>
<li><p><span data-ttu-id="84894-233">支持针对频道消息的电子数据展示和法律封存</span><span class="sxs-lookup"><span data-stu-id="84894-233">eDiscovery and Legal Hold for compliance on channel messages is supported</span></span></p></li>
<li><p><span data-ttu-id="84894-234">数据丢失防护策略（DLP）可用</span><span class="sxs-lookup"><span data-stu-id="84894-234">Data Loss Prevention policies (DLP) are available</span></span></p></li>
</ul>
<p><span data-ttu-id="84894-235">完整功能集通过 Exchange Online 提供，本地 Exchange 支持这些功能中的大部分，请参阅</span><span class="sxs-lookup"><span data-stu-id="84894-235">Full feature set available with Exchange Online, Exchange on-premises supports most of these features, see</span></span></p>
<p><span data-ttu-id="84894-236"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Exchange 与 Teams 如何交互</a></span><span class="sxs-lookup"><span data-stu-id="84894-236"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a></span></span></p>
<ul>
<li><p><span data-ttu-id="84894-237">对于完整列表</span><span class="sxs-lookup"><span data-stu-id="84894-237">for full list</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="84894-238">具有 Skype for business 服务器的组织的启用步骤</span><span class="sxs-lookup"><span data-stu-id="84894-238">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="84894-239">在上面的 "开始" 部分中，满足上述先决条件。</span><span class="sxs-lookup"><span data-stu-id="84894-239">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="84894-240">将租户切换到 "孤岛" 模式（在9/1/2019 之后预配租户），请联系支持人员进行此更改）</span><span class="sxs-lookup"><span data-stu-id="84894-240">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="84894-241">设置共存和升级设置</span><span class="sxs-lookup"><span data-stu-id="84894-241">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="84894-242">根据公司的企业/公司策略配置租户</span><span class="sxs-lookup"><span data-stu-id="84894-242">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="84894-243">为你的组织管理 Microsoft Teams 设置</span><span class="sxs-lookup"><span data-stu-id="84894-243">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="84894-244">部署团队客户端</span><span class="sxs-lookup"><span data-stu-id="84894-244">Deploy the Teams client</span></span>  
    [<span data-ttu-id="84894-245">获取 Teams 客户端</span><span class="sxs-lookup"><span data-stu-id="84894-245">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="84894-246">推动你的采纳计划</span><span class="sxs-lookup"><span data-stu-id="84894-246">Drive your adoption program</span></span>  
    [<span data-ttu-id="84894-247">采用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84894-247">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="84894-248">Microsoft Teams 采用快速入门清单</span><span class="sxs-lookup"><span data-stu-id="84894-248">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="84894-249">开始规划将其他工作负荷移动到 Office 365</span><span class="sxs-lookup"><span data-stu-id="84894-249">Begin planning moving other workloads to Office 365</span></span>

7.  <span data-ttu-id="84894-250">建立 Skype for business 混合，并按照推荐的升级路径进行 Skype for Business 和 Lync 服务器</span><span class="sxs-lookup"><span data-stu-id="84894-250">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="84894-251">从本地 Skype for Business 升级到团队</span><span class="sxs-lookup"><span data-stu-id="84894-251">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="84894-252">结算语句</span><span class="sxs-lookup"><span data-stu-id="84894-252">Closing statement</span></span>

<span data-ttu-id="84894-253">Microsoft 团队可以是你的组织的一个启用码，以将所有员工、信息工作者和一线工作者汇集到一个平台上。</span><span class="sxs-lookup"><span data-stu-id="84894-253">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Firstline workers, together on a single platform.</span></span> <span data-ttu-id="84894-254">您可以立即[开始](https://products.office.com/microsoft-teams/group-chat-software)使用。</span><span class="sxs-lookup"><span data-stu-id="84894-254">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="84894-255">您可以在[此处](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)与我们的所有最新通知和每月产品更新保持联系。</span><span class="sxs-lookup"><span data-stu-id="84894-255">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="84894-256">此外，随着全球各地的公司正在管理当前的 COVID-19，我们已创建一系列内容，帮助您利用团队最大程度地影响您的组织。</span><span class="sxs-lookup"><span data-stu-id="84894-256">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="84894-257">我们[在 COVID 期间对客户的承诺-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="84894-257">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="84894-258">2周内：我们学到的有关远程工作的内容</span><span class="sxs-lookup"><span data-stu-id="84894-258">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="84894-259">提供联机会议和事件</span><span class="sxs-lookup"><span data-stu-id="84894-259">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="84894-260">协助中小型企业使用 Teams 远程工作</span><span class="sxs-lookup"><span data-stu-id="84894-260">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="84894-261">实时事件的数字转换： Bob Bejan 在 frontline 中的观测值</span><span class="sxs-lookup"><span data-stu-id="84894-261">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="84894-262">Microsoft IT 便于员工远程工作的 9 大方式</span><span class="sxs-lookup"><span data-stu-id="84894-262">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="84894-263">远程工作，保持安全-CISOs 提示</span><span class="sxs-lookup"><span data-stu-id="84894-263">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="84894-264">帮助教师和学生将交换机转换为远程学习</span><span class="sxs-lookup"><span data-stu-id="84894-264">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="84894-265">在与 Microsoft 团队远程协作的同时保持工作效率</span><span class="sxs-lookup"><span data-stu-id="84894-265">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="84894-266">支持服务参考</span><span class="sxs-lookup"><span data-stu-id="84894-266">Support Services reference</span></span>

<span data-ttu-id="84894-267">团队依赖于 Exchange Online、SharePoint Online、OneDrive for Business 和 Microsoft 365 组，以便为你的用户提供完全集成的 Office 365 体验。</span><span class="sxs-lookup"><span data-stu-id="84894-267">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Office 365 experience.</span></span> <span data-ttu-id="84894-268">如上所述，团队将在不完全部署这些服务的情况下正常工作-但功能有限。</span><span class="sxs-lookup"><span data-stu-id="84894-268">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="84894-269">你可以在此处阅读有关团队及其先决条件的详细信息：[欢迎使用团队](teams-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="84894-269">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="84894-270">有关以上列出的每项服务的详细信息，请访问以下链接：</span><span class="sxs-lookup"><span data-stu-id="84894-270">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="84894-271">Exchange Online 用于日历功能并将对等消息存储到团队中的对等消息中。</span><span class="sxs-lookup"><span data-stu-id="84894-271">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="84894-272">若要了解详细信息，请阅读[Exchange 和团队如何进行交互](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="84894-272">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84894-273">对于具有本地 Exchange 的团队互操作，必须按照在 [Exchange 和 Exchange Online 组织之间配置 OAuth 身份验证](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)中所述配置新的 Exchange OAuth 身份验证协议。</span><span class="sxs-lookup"><span data-stu-id="84894-273">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="84894-274">SharePoint 用于频道中的文件共享，而/OneDrive 用于在1:1 或群组聊天中进行文件共享。</span><span class="sxs-lookup"><span data-stu-id="84894-274">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="84894-275">若要了解详细信息，请参阅[SharePoint Online 和 OneDrive For Business 如何与 Microsoft 团队进行交互](sharepoint-onedrive-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="84894-275">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="84894-276">[Microsoft 365 组](office-365-groups.md)用于团队和频道创建/管理。</span><span class="sxs-lookup"><span data-stu-id="84894-276">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="84894-277">相关主题</span><span class="sxs-lookup"><span data-stu-id="84894-277">Related topics</span></span>

[<span data-ttu-id="84894-278">Microsoft Teams IT 体系结构和电话解决方案海报</span><span class="sxs-lookup"><span data-stu-id="84894-278">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="84894-279">规划 Skype for Business Server 与 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="84894-279">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="84894-280">支持使用团队的远程工作人员</span><span class="sxs-lookup"><span data-stu-id="84894-280">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="84894-281">使用 Office 365 远程工作</span><span class="sxs-lookup"><span data-stu-id="84894-281">Work remotely with Office 365</span></span>](https://aka.ms/remote-work)
