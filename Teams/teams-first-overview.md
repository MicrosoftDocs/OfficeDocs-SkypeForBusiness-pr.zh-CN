---
title: 推出 Microsoft Teams First
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
description: 使用本指南将 Microsoft Teams 作为第一个 Microsoft 365 或 Office 365 工作负荷推出。
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: a30d5bed9443df3077ab7384cd8266d2f049148d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909476"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="84d0d-103">推出 Microsoft Teams First</span><span class="sxs-lookup"><span data-stu-id="84d0d-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="84d0d-104">Microsoft Teams 可帮助你的员工保持联系并相互协作，尤其是在当前前所未有的时间，远程工作是世界各地的员工现实。</span><span class="sxs-lookup"><span data-stu-id="84d0d-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="84d0d-105">能够在 Teams 中聊天、召开视频会议和协作处理 Office 文档可帮助公司保持高效。</span><span class="sxs-lookup"><span data-stu-id="84d0d-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="84d0d-106">无论是小型企业、非营利组织还是大型组织，都可以在部署任何其他 Office 应用或服务之前，先将 Teams 用作 Microsoft 365 或 Office 365 套件中的第一个工作负荷。</span><span class="sxs-lookup"><span data-stu-id="84d0d-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Microsoft 365 or Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="84d0d-107">本文详细介绍了使用"Teams First"方法必须考虑的注意事项。</span><span class="sxs-lookup"><span data-stu-id="84d0d-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84d0d-108">虽然 Teams 可以是组织的第一个云部署工作负荷，但部署 Teams 应该是总体云部署策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="84d0d-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="84d0d-109">如果已推出其他 Microsoft 365 或 Office 365 服务，而 Teams 是下一个要推出 (而不是第一个) 的工作负荷，请从"如何推出 [Teams"](How-to-roll-out-teams.md)开始。</span><span class="sxs-lookup"><span data-stu-id="84d0d-109">If you have already rolled out other Microsoft 365 or Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out Teams](How-to-roll-out-teams.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="84d0d-110">从这里开始</span><span class="sxs-lookup"><span data-stu-id="84d0d-110">Start here</span></span>

<span data-ttu-id="84d0d-111">若要开始使用 Teams First 部署，至少需要满足一些先决条件。</span><span class="sxs-lookup"><span data-stu-id="84d0d-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="84d0d-112">以下列表将显示在启用 Teams 之前，组织必须拥有哪些功能：</span><span class="sxs-lookup"><span data-stu-id="84d0d-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="84d0d-113">使用域名配置的 Microsoft 365 或 Office 365 组织</span><span class="sxs-lookup"><span data-stu-id="84d0d-113">A Microsoft 365 or Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="84d0d-114">Azure Active Directory 连接 (AAD) 或类似云标识同步解决方案 - 所有必需属性与租户同步</span><span class="sxs-lookup"><span data-stu-id="84d0d-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="84d0d-115">若要了解与 AAD 同步同步的属性，请阅读 [Azure AD Connect 同步：同步到 Azure Active Directory 的属性](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span><span class="sxs-lookup"><span data-stu-id="84d0d-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="84d0d-116">为 Teams 分配相应的用户许可证</span><span class="sxs-lookup"><span data-stu-id="84d0d-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="84d0d-117">若要了解 Teams 许可，请阅读 [Microsoft Teams 服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="84d0d-117">To understand Teams licensing, read [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="84d0d-118">为 Teams 准备的组织网络</span><span class="sxs-lookup"><span data-stu-id="84d0d-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="84d0d-119">若要了解网络准备，请阅读["为 Teams 准备组织的网络"。](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="84d0d-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="84d0d-120">允许网络访问 Microsoft 365 或 Office 365 中的 Exchange、Sharepoint 和 OneDrive for [Business：Office 365 URL](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)和 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="84d0d-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Microsoft 365 or Office 365: [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="84d0d-121">在 2019 年 9 月 1 日之后创建的租户在"仅 Teams"模式下预配。</span><span class="sxs-lookup"><span data-stu-id="84d0d-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="84d0d-122">如果你部署了 Skype for Business Server，并且你的租户是在 2019 年 9 月 1 日之后预配的，请联系支持人员为 Teams 启用共存功能。</span><span class="sxs-lookup"><span data-stu-id="84d0d-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="84d0d-123">在将任何 Teams 许可证分配给用户之前，请确保将"组织范围的<span class="underline"></span>升级策略"设置为"岛模式"。</span><span class="sxs-lookup"><span data-stu-id="84d0d-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="84d0d-124">迁移起点</span><span class="sxs-lookup"><span data-stu-id="84d0d-124">Migration Starting points</span></span>

<span data-ttu-id="84d0d-125">你到 Microsoft 365 或 Office 365 之旅以及 Teams 中可用的功能，具体取决于起点以及本地 Skype for Business 或 Lync 服务器的存在。</span><span class="sxs-lookup"><span data-stu-id="84d0d-125">Your journey to Microsoft 365 or Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="84d0d-126">除了上述先决条件外，以下部分还将详细介绍基本功能和配置选项。</span><span class="sxs-lookup"><span data-stu-id="84d0d-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="84d0d-127">我们已将起点方案细分为以下主题：</span><span class="sxs-lookup"><span data-stu-id="84d0d-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="84d0d-128">**租户团队配置**：租户和用户模式用于控制收件人的行为。</span><span class="sxs-lookup"><span data-stu-id="84d0d-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="84d0d-129">这些设置可以在组织的租户级别或用户级别分配。</span><span class="sxs-lookup"><span data-stu-id="84d0d-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="84d0d-130">若要了解有关详细信息，请阅读[与 Skype for Business 共存。](coexistence-chat-calls-presence.md)</span><span class="sxs-lookup"><span data-stu-id="84d0d-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="84d0d-131">**Teams 中的聊天/** 外部通信：聊天服务是指组织内部或组织外部的对等或群组聊天对话。</span><span class="sxs-lookup"><span data-stu-id="84d0d-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="84d0d-132">外部通信在 Skype for Business 中也称为联合。</span><span class="sxs-lookup"><span data-stu-id="84d0d-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="84d0d-133">**在 Teams 中** 创建和查看会议：用户始终可以通过 Outlook Teams 加载项创建联机会议，在用户获得许可后，PSTN 拨入功能在所有方案中均可用。</span><span class="sxs-lookup"><span data-stu-id="84d0d-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="84d0d-134">Teams 和 Skype for Business 将日历信息存储在用户的 Exchange 邮箱中。</span><span class="sxs-lookup"><span data-stu-id="84d0d-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="84d0d-135">本地 Exchange 服务器必须Exchange Server 2016 CU3 或更高层，Teams 客户端才能与用户的邮箱进行交互。</span><span class="sxs-lookup"><span data-stu-id="84d0d-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="84d0d-136">如果没有 Exchange 邮箱访问权限，Teams 中的日历图标将不会显示，并且用户将无法在 Teams 客户端中查看、创建或修改会议。</span><span class="sxs-lookup"><span data-stu-id="84d0d-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="84d0d-137">**Teams 中的呼叫功能 VoIP/PSTN：** 呼叫可以是通过 IP (VoIP) 语音呼叫或 PSTN (公用电话) 。</span><span class="sxs-lookup"><span data-stu-id="84d0d-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="84d0d-138">VoIP 连接在 Teams 客户端之间本机发生，而 PSTN 连接发生在用户拨打外部电话号码时。</span><span class="sxs-lookup"><span data-stu-id="84d0d-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="84d0d-139">Teams 支持两种类型的 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="84d0d-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="84d0d-140">Microsoft 呼叫计划，当 Microsoft 提供电话基础结构（包括用户的电话号码）或直接路由配置时，客户通过会话边界控制器 (SBC) 为 Teams 用户提供电话连接。</span><span class="sxs-lookup"><span data-stu-id="84d0d-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="84d0d-141">若要了解有关详细信息，请阅读 [哪种呼叫计划适合你？](calling-plan-landing-page.md) 以及 [电话系统直接路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="84d0d-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="84d0d-142">**Teams 中的团队和** 频道协作：在 Teams 中，团队是一组为了工作、项目或共同兴趣而聚在一起的人。</span><span class="sxs-lookup"><span data-stu-id="84d0d-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="84d0d-143">团队由频道决定。</span><span class="sxs-lookup"><span data-stu-id="84d0d-143">Teams are made up of channels.</span></span> <span data-ttu-id="84d0d-144">每个频道围绕主题构建，例如"团队活动"、部门名称或只是为了娱乐。</span><span class="sxs-lookup"><span data-stu-id="84d0d-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="84d0d-145">频道是召开会议、进行对话以及一起处理文件的地方。</span><span class="sxs-lookup"><span data-stu-id="84d0d-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="84d0d-146">协作期间</span><span class="sxs-lookup"><span data-stu-id="84d0d-146">During collaboration</span></span>

<span data-ttu-id="84d0d-147">Teams 中的 **OneDrive for Business (P2P** 文件共享) ：在 Teams 和频道之外，Teams 用户可以使用 OneDrive for Business 或其他 P2P 共享文件程序（如 Citrix 文件、DropBox、Box 和 Google Drive）进行文件对等共享。</span><span class="sxs-lookup"><span data-stu-id="84d0d-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="84d0d-148">对于 OneDrive for Business，用户必须分配有 SharePoint Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="84d0d-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="84d0d-149">**应用程序** 平台：应用为组织提供可进一步利用 Teams 的开箱即用工具。</span><span class="sxs-lookup"><span data-stu-id="84d0d-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="84d0d-150">这些应用结合了由 Microsoft 提供、由第三方或组织中的开发人员提供的选项卡、消息传递扩展、连接器和机器人的功能。</span><span class="sxs-lookup"><span data-stu-id="84d0d-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="84d0d-151">**安全性和符合性功能：** Teams 提供大量信息来帮助你实现合规性，包括保留策略、数据丢失保护 (DLP) 、电子数据展示和通道、聊天和文件法定保留、审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="84d0d-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="84d0d-152">若要了解有关详细信息，请阅读 [Microsoft Teams 中的安全性和符合性](security-compliance-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="84d0d-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="84d0d-153">高级电子数据展示功能需要 E5 许可。</span><span class="sxs-lookup"><span data-stu-id="84d0d-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="84d0d-154">[比较许可选项](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。</span><span class="sxs-lookup"><span data-stu-id="84d0d-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="84d0d-155">阅读 [Exchange 和 Microsoft Teams 如何交互](exchange-teams-interact.md) ，了解在你的方案中可用的合规性功能。</span><span class="sxs-lookup"><span data-stu-id="84d0d-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="84d0d-156">没有 **<span class="underline"></span>** Skype for Business 或 Lync Server 的组织</span><span class="sxs-lookup"><span data-stu-id="84d0d-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync Server</span></span>

<span data-ttu-id="84d0d-157">此起点假定你的组织当前未使用 Skype for Business 或 Lync Server，而 Teams 将是 Microsoft 365 或 Office 365 中的第一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="84d0d-157">This starting point assumes that your organization does not utilize Skype for Business or Lync Server currently and Teams will be your first application in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="84d0d-158">下表详细介绍了 Teams 的核心服务的高级别配置和最终用户功能。</span><span class="sxs-lookup"><span data-stu-id="84d0d-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="84d0d-159">项目</span><span class="sxs-lookup"><span data-stu-id="84d0d-159">Item</span></span></th>
<th><span data-ttu-id="84d0d-160">注释</span><span class="sxs-lookup"><span data-stu-id="84d0d-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="84d0d-161">租户团队配置</span><span class="sxs-lookup"><span data-stu-id="84d0d-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="84d0d-162">仅 Teams 模式，所有聊天和通话功能均在 Teams 中提供。</span><span class="sxs-lookup"><span data-stu-id="84d0d-162">Teams Only mode, all chat and calling features are in Teams Only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84d0d-163">Teams 中的聊天/外部通信</span><span class="sxs-lookup"><span data-stu-id="84d0d-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="84d0d-164">Microsoft (365 或 Office 365 组织内部的) 和来自 Teams 的外部聊天通信。</span><span class="sxs-lookup"><span data-stu-id="84d0d-164">Internal (intra Microsoft 365 or Office 365 organization) and external chat communication possible from Teams.</span></span></p>
<p><span data-ttu-id="84d0d-165"><em>注意：必须为外部访问配置 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="84d0d-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="84d0d-166">即使你在本地或 Microsoft 365 或 Office 365 中没有 Skype for Business，也需要 Skype for Business DNS 记录，以允许与 Lync 和 Skype for Business 环境联合：</span><span class="sxs-lookup"><span data-stu-id="84d0d-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises, or in Microsoft 365 or Office 365, to allow federation with Lync and Skype for Business environments:</span></span><br /><span data-ttu-id="84d0d-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">外部域名系统记录</a></em></span><span class="sxs-lookup"><span data-stu-id="84d0d-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">External Domain Name System records</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="84d0d-168">在 Teams 创建和查看会议</span><span class="sxs-lookup"><span data-stu-id="84d0d-168">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="84d0d-169">能够通过 Outlook 加载项创建内部和外部会议。</span><span class="sxs-lookup"><span data-stu-id="84d0d-169">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="84d0d-170">PSTN 拨入和拨出功能可用于音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="84d0d-170">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="84d0d-171">Teams 日历访问需要使用已建立 Exchange 混合部署的 Exchange 2016 CU3+ 本地：使用混合配置向导创建 <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">混合部署。</a> </span><span class="sxs-lookup"><span data-stu-id="84d0d-171">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a> </span></span></p>
<p><span data-ttu-id="84d0d-172">除了 Exchange 混合配置，还建立 Exchange OAuth 身份验证：在 Exchange 和 Exchange Online 组织之间 <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> 配置 OAuth 身份验证"。</span><span class="sxs-lookup"><span data-stu-id="84d0d-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations".</span></span></p>

</p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84d0d-173">呼叫功能</span><span class="sxs-lookup"><span data-stu-id="84d0d-173">Calling Features</span></span><br />
<span data-ttu-id="84d0d-174">Teams 中的 VoIP/PSTN</span><span class="sxs-lookup"><span data-stu-id="84d0d-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="84d0d-175">可在租户内部和外部使用 VoIP。</span><span class="sxs-lookup"><span data-stu-id="84d0d-175">VoIP internally and externally to the tenant is available.</span></span></p>
<p><span data-ttu-id="84d0d-176">PSTN 服务可以通过 Microsoft Phone 系统进行配置，还可以添加 Microsoft 呼叫计划或直接路由。</span><span class="sxs-lookup"><span data-stu-id="84d0d-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="84d0d-177">Teams 中的团队和频道协作</span><span class="sxs-lookup"><span data-stu-id="84d0d-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="84d0d-178">若要获得完整体验，包括合规性功能，需要将 SharePoint Online 许可证分配给用户。</span><span class="sxs-lookup"><span data-stu-id="84d0d-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="84d0d-179">不需要迁移现有的本地 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="84d0d-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84d0d-180">OneDrive for Business (P2P 文件共享) </span><span class="sxs-lookup"><span data-stu-id="84d0d-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="84d0d-181">OneDrive for Business 要求用户分配有 SharePoint Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="84d0d-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="84d0d-182">如果没有此许可证，将不可能进行对等文件共享。</span><span class="sxs-lookup"><span data-stu-id="84d0d-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="84d0d-183">应用程序平台</span><span class="sxs-lookup"><span data-stu-id="84d0d-183">Application platform</span></span></td>
<td><span data-ttu-id="84d0d-184">用户将能够使用根据公司策略为用户指定的应用。</span><span class="sxs-lookup"><span data-stu-id="84d0d-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="84d0d-185">在此处了解更多信息 <a href="https://docs.microsoft.com/microsoftteams/admin-settings">：Teams 中应用的管理员设置</a></span><span class="sxs-lookup"><span data-stu-id="84d0d-185">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84d0d-186">安全性和符合性功能</span><span class="sxs-lookup"><span data-stu-id="84d0d-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="84d0d-187">保留策略可用。</span><span class="sxs-lookup"><span data-stu-id="84d0d-187">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="84d0d-188">支持电子数据展示和法定保留，以确保通道消息的符合性。</span><span class="sxs-lookup"><span data-stu-id="84d0d-188">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="84d0d-189">DLP (数据丢失防护) 可用。</span><span class="sxs-lookup"><span data-stu-id="84d0d-189">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="84d0d-190">Exchange Online 提供的完整功能集;本地 Exchange 支持大多数这些功能。</span><span class="sxs-lookup"><span data-stu-id="84d0d-190">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="84d0d-191">有关完整列表，请参阅 <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Exchange 和 Teams 如何交互</a>。</span><span class="sxs-lookup"><span data-stu-id="84d0d-191">For a full list, see <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a>.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="84d0d-192">为没有 Skype for Business 或 Lync Server 的组织启用步骤</span><span class="sxs-lookup"><span data-stu-id="84d0d-192">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="84d0d-193">满足上述"此处开始"部分中详述的先决条件</span><span class="sxs-lookup"><span data-stu-id="84d0d-193">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="84d0d-194">将租户切换到仅针对现有租户 (Teams 模式) ： [设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="84d0d-194">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="84d0d-195">根据公司的业务/公司策略配置租户：管理组织的 Microsoft Teams [设置](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="84d0d-195">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="84d0d-196">将 Teams 客户端部署到用户： [获取 Teams 的客户端](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="84d0d-196">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="84d0d-197">推动采用计划</span><span class="sxs-lookup"><span data-stu-id="84d0d-197">Drive your adoption program</span></span>  
    [<span data-ttu-id="84d0d-198">采用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84d0d-198">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="84d0d-199">Microsoft Teams 采用快速入门清单</span><span class="sxs-lookup"><span data-stu-id="84d0d-199">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="84d0d-200">开始计划将其他工作负荷移动到 Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="84d0d-200">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="84d0d-201">使用 **<span class="underline"></span>** Skype for Business 或 Lync 服务器的组织</span><span class="sxs-lookup"><span data-stu-id="84d0d-201">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="84d0d-202">此起点假定你的组织使用本地 Skype for Business 2019、2015+ 或 Lync 2013+ 服务器。</span><span class="sxs-lookup"><span data-stu-id="84d0d-202">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="84d0d-203">我们已针对组织从本地服务器迁移到 Teams 提供了广泛的指导，这些方案应该遵循这些指南。</span><span class="sxs-lookup"><span data-stu-id="84d0d-203">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="84d0d-204">本指南特定于 Teams 是 Microsoft 365 或 Office 365 中利用的第一个应用程序的方案。</span><span class="sxs-lookup"><span data-stu-id="84d0d-204">This guidance is specific to the scenario that Teams is the first application you utilize in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="84d0d-205">下表详细介绍了 Teams 的核心服务的高级别配置和最终用户功能。</span><span class="sxs-lookup"><span data-stu-id="84d0d-205">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="84d0d-206">项目</span><span class="sxs-lookup"><span data-stu-id="84d0d-206">Item</span></span></th>
<th><span data-ttu-id="84d0d-207">注释</span><span class="sxs-lookup"><span data-stu-id="84d0d-207">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="84d0d-208">租户团队配置</span><span class="sxs-lookup"><span data-stu-id="84d0d-208">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="84d0d-209">岛屿模式。</span><span class="sxs-lookup"><span data-stu-id="84d0d-209">Islands mode.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84d0d-210">Teams 中的聊天/外部通信</span><span class="sxs-lookup"><span data-stu-id="84d0d-210">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="84d0d-211">仅在你自己的租户内部，外部通信 (联合) 通过 Skype for Business 或 Lync 服务器部署进行。</span><span class="sxs-lookup"><span data-stu-id="84d0d-211">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="84d0d-212">在 Teams 创建和查看会议</span><span class="sxs-lookup"><span data-stu-id="84d0d-212">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="84d0d-213">能够通过 Outlook 加载项创建内部和外部会议。</span><span class="sxs-lookup"><span data-stu-id="84d0d-213">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="84d0d-214">PSTN 拨入和拨出功能可用于音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="84d0d-214">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="84d0d-215">Teams 日历访问要求使用 Exchange 混合部署 Exchange 2016 CU3+ 本地：</span><span class="sxs-lookup"><span data-stu-id="84d0d-215">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="84d0d-216">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">使用混合配置向导创建混合部署。</a></span><span class="sxs-lookup"><span data-stu-id="84d0d-216">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a></span></span></p>
<p><span data-ttu-id="84d0d-217">管理员可以通过 Teams 会议策略的 PreferredMeetingProviderForIslandsMode 属性<a href="https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>控制 Skype for Business Outlook 加载项。</span><span class="sxs-lookup"><span data-stu-id="84d0d-217">Administrator can control the Skype for Business Outlook add-in via the Teams meeting policy’s PreferredMeetingProviderForIslandsMode attribute:<a href="https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span></span></p> 
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="84d0d-218">呼叫功能</span><span class="sxs-lookup"><span data-stu-id="84d0d-218">Calling Features</span></span><br />
<span data-ttu-id="84d0d-219">Teams 中的 VoIP/PSTN</span><span class="sxs-lookup"><span data-stu-id="84d0d-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="84d0d-220">可在租户内部使用 VoIP。</span><span class="sxs-lookup"><span data-stu-id="84d0d-220">VoIP internally to the tenant is available.</span></span></p>
<p><span data-ttu-id="84d0d-221">PSTN 或呼叫计划服务在用户移动到"仅 Teams"体验之前不可用。</span><span class="sxs-lookup"><span data-stu-id="84d0d-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="84d0d-222">Teams 中的团队和频道协作</span><span class="sxs-lookup"><span data-stu-id="84d0d-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="84d0d-223">若要获得完整体验，包括合规性功能，需要将 SharePoint Online 许可证分配给用户。</span><span class="sxs-lookup"><span data-stu-id="84d0d-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="84d0d-224">不需要迁移现有的本地 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="84d0d-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84d0d-225">OneDrive for Business (P2P 文件共享) </span><span class="sxs-lookup"><span data-stu-id="84d0d-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="84d0d-226">OneDrive for Business 要求用户分配有 SharePoint Online 许可证。</span><span class="sxs-lookup"><span data-stu-id="84d0d-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="84d0d-227">如果没有此许可证，将不可能进行按对等文件共享。</span><span class="sxs-lookup"><span data-stu-id="84d0d-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="84d0d-228">应用程序平台</span><span class="sxs-lookup"><span data-stu-id="84d0d-228">Application platform</span></span></td>
<td><span data-ttu-id="84d0d-229">用户将能够使用根据公司策略为用户指定的应用。</span><span class="sxs-lookup"><span data-stu-id="84d0d-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="84d0d-230">在此处了解更多信息 <a href="https://docs.microsoft.com/microsoftteams/admin-settings">：Teams 中应用的管理员设置</a></span><span class="sxs-lookup"><span data-stu-id="84d0d-230">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="84d0d-231">安全性和符合性功能</span><span class="sxs-lookup"><span data-stu-id="84d0d-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="84d0d-232">保留策略可用。</span><span class="sxs-lookup"><span data-stu-id="84d0d-232">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="84d0d-233">支持电子数据展示和法定保留，以确保通道消息的符合性。</span><span class="sxs-lookup"><span data-stu-id="84d0d-233">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="84d0d-234">DLP (数据丢失防护) 可用。</span><span class="sxs-lookup"><span data-stu-id="84d0d-234">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="84d0d-235">Exchange Online 提供的完整功能集;本地 Exchange 支持大多数这些功能。</span><span class="sxs-lookup"><span data-stu-id="84d0d-235">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="84d0d-236">有关完整列表，请参阅 <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Exchange 和 Teams 如何交互。</a></span><span class="sxs-lookup"><span data-stu-id="84d0d-236">For a complete list, see <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact.</a></span></span></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="84d0d-237">为使用 Skype for Business Server 的组织启用步骤</span><span class="sxs-lookup"><span data-stu-id="84d0d-237">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="84d0d-238">满足上述"此处开始"部分中详述的先决条件。</span><span class="sxs-lookup"><span data-stu-id="84d0d-238">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="84d0d-239">对于 2019 年 9 月 1 日 (预配的租户，请将租户切换到群岛模式模式，请联系支持部门，) </span><span class="sxs-lookup"><span data-stu-id="84d0d-239">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="84d0d-240">设置共存和升级设置</span><span class="sxs-lookup"><span data-stu-id="84d0d-240">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="84d0d-241">根据公司的业务/公司策略配置租户</span><span class="sxs-lookup"><span data-stu-id="84d0d-241">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="84d0d-242">为你的组织管理 Microsoft Teams 设置</span><span class="sxs-lookup"><span data-stu-id="84d0d-242">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="84d0d-243">部署 Teams 客户端</span><span class="sxs-lookup"><span data-stu-id="84d0d-243">Deploy the Teams client</span></span>  
    [<span data-ttu-id="84d0d-244">获取 Teams 客户端</span><span class="sxs-lookup"><span data-stu-id="84d0d-244">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="84d0d-245">推动采用计划</span><span class="sxs-lookup"><span data-stu-id="84d0d-245">Drive your adoption program</span></span>  
    [<span data-ttu-id="84d0d-246">采用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84d0d-246">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="84d0d-247">Microsoft Teams 采用快速入门清单</span><span class="sxs-lookup"><span data-stu-id="84d0d-247">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="84d0d-248">开始计划将其他工作负荷移动到 Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="84d0d-248">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

7.  <span data-ttu-id="84d0d-249">建立 Skype for Business 混合并遵循 Skype for Business 和 Lync 服务器的建议升级路径</span><span class="sxs-lookup"><span data-stu-id="84d0d-249">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="84d0d-250">从本地 Skype for Business 升级到 Teams</span><span class="sxs-lookup"><span data-stu-id="84d0d-250">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="84d0d-251">结束语句</span><span class="sxs-lookup"><span data-stu-id="84d0d-251">Closing statement</span></span>

<span data-ttu-id="84d0d-252">Microsoft Teams 可以是组织在单个平台上将所有员工、信息工作者和一线工作者汇集在一起的一个促成工具。</span><span class="sxs-lookup"><span data-stu-id="84d0d-252">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Frontline workers, together on a single platform.</span></span> <span data-ttu-id="84d0d-253">你可以 [从今天开始](https://products.office.com/microsoft-teams/group-chat-software) 。</span><span class="sxs-lookup"><span data-stu-id="84d0d-253">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="84d0d-254">你可以在此处随时了解我们的最新公告和每月产品 [更新](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)。</span><span class="sxs-lookup"><span data-stu-id="84d0d-254">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="84d0d-255">此外，由于世界各地的公司正在管理当前的 COVID-19 情况，我们创建了一系列内容，可帮助你利用 Teams 在组织中实现最大影响。</span><span class="sxs-lookup"><span data-stu-id="84d0d-255">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="84d0d-256">我们在[COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)期间为客户提供的承诺</span><span class="sxs-lookup"><span data-stu-id="84d0d-256">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="84d0d-257">2 周后：我们已了解远程工作</span><span class="sxs-lookup"><span data-stu-id="84d0d-257">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="84d0d-258">传送联机会议和事件</span><span class="sxs-lookup"><span data-stu-id="84d0d-258">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="84d0d-259">协助中小型企业使用 Teams 远程工作</span><span class="sxs-lookup"><span data-stu-id="84d0d-259">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="84d0d-260">实时事件的数字化转换：Bob Be在一线观察结果</span><span class="sxs-lookup"><span data-stu-id="84d0d-260">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="84d0d-261">Microsoft IT 便于员工远程工作的 9 大方式</span><span class="sxs-lookup"><span data-stu-id="84d0d-261">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="84d0d-262">远程工作，保持安全 — CISOS 提示</span><span class="sxs-lookup"><span data-stu-id="84d0d-262">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="84d0d-263">帮助教师和学生转换到远程学习</span><span class="sxs-lookup"><span data-stu-id="84d0d-263">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="84d0d-264">在远程使用 Microsoft Teams 时保持高效</span><span class="sxs-lookup"><span data-stu-id="84d0d-264">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="84d0d-265">支持服务参考</span><span class="sxs-lookup"><span data-stu-id="84d0d-265">Support Services reference</span></span>

<span data-ttu-id="84d0d-266">Teams 依赖 Exchange Online、SharePoint Online、OneDrive for Business 和 Microsoft 365 组为用户提供完全集成的 Microsoft 365 或 Office 365 体验。</span><span class="sxs-lookup"><span data-stu-id="84d0d-266">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Microsoft 365 or Office 365 experience.</span></span> <span data-ttu-id="84d0d-267">如上所述，Teams 在未完全部署这些服务的情况下工作 - 功能有限。</span><span class="sxs-lookup"><span data-stu-id="84d0d-267">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="84d0d-268">可在此处阅读有关 Teams 及其先决条件的更多信息：[欢迎使用 Teams。](teams-overview.md)</span><span class="sxs-lookup"><span data-stu-id="84d0d-268">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="84d0d-269">有关上面列出的每个服务的详细信息，请访问以下链接：</span><span class="sxs-lookup"><span data-stu-id="84d0d-269">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="84d0d-270">Exchange Online 用于在 Teams 中存储日历功能和存储对等消息。</span><span class="sxs-lookup"><span data-stu-id="84d0d-270">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="84d0d-271">若要了解更多信息，请阅读 [Exchange 和 Teams 如何交互](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="84d0d-271">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84d0d-272">对于 Teams 与 Exchange 本地的互操作，必须配置新的 Exchange OAuth 身份验证协议，如在 Exchange 和 Exchange Online 组织之间配置 [OAuth 身份验证中所述](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)。</span><span class="sxs-lookup"><span data-stu-id="84d0d-272">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="84d0d-273">SharePoint 用于频道中的文件共享，而 /OneDrive for Business 用于在 1：1 或群组聊天中共享文件。</span><span class="sxs-lookup"><span data-stu-id="84d0d-273">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="84d0d-274">若要了解有关详细信息，请阅读 [SharePoint Online 和 OneDrive for Business 如何与 Microsoft Teams 交互](sharepoint-onedrive-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="84d0d-274">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="84d0d-275">[Microsoft 365 组](office-365-groups.md) 用于团队和频道创建/管理。</span><span class="sxs-lookup"><span data-stu-id="84d0d-275">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="84d0d-276">相关主题</span><span class="sxs-lookup"><span data-stu-id="84d0d-276">Related topics</span></span>

[<span data-ttu-id="84d0d-277">Microsoft Teams IT 体系结构和电话解决方案海报</span><span class="sxs-lookup"><span data-stu-id="84d0d-277">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="84d0d-278">规划 Skype for Business Server 与 Office 365 之间的混合连接</span><span class="sxs-lookup"><span data-stu-id="84d0d-278">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="84d0d-279">使用 Teams 支持远程工作者</span><span class="sxs-lookup"><span data-stu-id="84d0d-279">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="84d0d-280">使用 Microsoft 365 远程工作</span><span class="sxs-lookup"><span data-stu-id="84d0d-280">Work remotely with Microsoft 365</span></span>](https://aka.ms/remote-work)
