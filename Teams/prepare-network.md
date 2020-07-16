---
title: 为 Teams 准备贵组织的网络
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: 了解如何为 Microsoft 团队准备组织的网络，包括网络要求、网络优化和带宽要求。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: dc05c885b3b2eb5ef4991a6580ebcb0751c87f39
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2020
ms.locfileid: "44874270"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="49a41-103">为 Microsoft Teams 准备组织的网络</span><span class="sxs-lookup"><span data-stu-id="49a41-103">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="49a41-104">网络要求</span><span class="sxs-lookup"><span data-stu-id="49a41-104">Network requirements</span></span>

<span data-ttu-id="49a41-105">如果您已经针对[microsoft 365 或 Office 365 优化了](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity)您的网络，您可能已经准备好参加 microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="49a41-105">If you've already [optimized your network for Microsoft 365 or Office 365](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="49a41-106">在任何情况下，尤其是在开始团队推出之前，如果你作为第一个 Microsoft 365 或 Office 365 工作**remote workers**负荷快速推出，请检查以下事项：</span><span class="sxs-lookup"><span data-stu-id="49a41-106">In any case - and especially if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="49a41-107">您的所有位置是否都有 internet 访问权限（以便他们可以连接到 Microsoft 365 或 Office 365）？</span><span class="sxs-lookup"><span data-stu-id="49a41-107">Do all your locations have internet access (so they can connect to Microsoft 365 or Office 365)?</span></span> <span data-ttu-id="49a41-108">除了普通 web 流量之外，请确保已针对团队中的媒体打开以下内容：</span><span class="sxs-lookup"><span data-stu-id="49a41-108">At a minimum, in addition to normal web traffic, make sure you've opened the following, for all locations, for media in Teams:</span></span>

    |  |  |
    |---------|---------|
    |<span data-ttu-id="49a41-109">端口</span><span class="sxs-lookup"><span data-stu-id="49a41-109">Ports</span></span>     |<span data-ttu-id="49a41-110">UDP 端口<strong>3478</strong>到<strong>3481</strong></span><span class="sxs-lookup"><span data-stu-id="49a41-110">UDP ports <strong>3478</strong> through <strong>3481</strong></span></span>        |
    |[<span data-ttu-id="49a41-111">IP 地址</span><span class="sxs-lookup"><span data-stu-id="49a41-111">IP addresses</span></span>](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<span data-ttu-id="49a41-112"><strong>13.107.64.0/18</strong>、 <strong>52.112.0.0/14</strong>和<strong>52.120.0.0/14</strong></span><span class="sxs-lookup"><span data-stu-id="49a41-112"><strong>13.107.64.0/18</strong>, <strong>52.112.0.0/14</strong>, and <strong>52.120.0.0/14</strong></span></span>         |

> [!IMPORTANT]
> <span data-ttu-id="49a41-113">如果你需要与 Skype for Business （本地或联机）联盟，你将需要配置一些其他 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="49a41-113">If you need to federate with Skype for Business, either on-premises or online, you will need to configure some additional DNS records.</span></span>
>
>|<span data-ttu-id="49a41-114">CNAME 记录/主机名</span><span class="sxs-lookup"><span data-stu-id="49a41-114">CNAME Records / Host name</span></span>  |<span data-ttu-id="49a41-115">TTL</span><span class="sxs-lookup"><span data-stu-id="49a41-115">TTL</span></span>  |<span data-ttu-id="49a41-116">指向 "地址" 或 "值"</span><span class="sxs-lookup"><span data-stu-id="49a41-116">Points to address or value</span></span>  |
>|---------|---------|---------|
>|<span data-ttu-id="49a41-117">sip</span><span class="sxs-lookup"><span data-stu-id="49a41-117">sip</span></span>     |    <span data-ttu-id="49a41-118">3600</span><span class="sxs-lookup"><span data-stu-id="49a41-118">3600</span></span>     |    <span data-ttu-id="49a41-119">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="49a41-119">sipdir.online.lync.com</span></span>     |
>|<span data-ttu-id="49a41-120">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="49a41-120">lyncdiscover</span></span>     |   <span data-ttu-id="49a41-121">3600</span><span class="sxs-lookup"><span data-stu-id="49a41-121">3600</span></span>      |    <span data-ttu-id="49a41-122">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="49a41-122">webdir.online.lync.com</span></span>     |
>


    
2.  <span data-ttu-id="49a41-123">您是否有用于 Microsoft 365 或 Office 365 的经验证的域（例如，contoso.com）？</span><span class="sxs-lookup"><span data-stu-id="49a41-123">Do you have a verified domain for Microsoft 365 or Office 365 (for example, contoso.com)?</span></span>
    
      - <span data-ttu-id="49a41-124">如果你的组织尚未推出 Microsoft 365 或 Office 365，请参阅[入门](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365)。</span><span class="sxs-lookup"><span data-stu-id="49a41-124">If your organization hasn't rolled out Microsoft 365 or Office 365, see [Get started](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365).</span></span>
      - <span data-ttu-id="49a41-125">如果你的组织尚未为 Microsoft 365 或 Office 365 添加或配置验证的域，请参阅[域常见问题解答](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)。</span><span class="sxs-lookup"><span data-stu-id="49a41-125">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="49a41-126">您的组织是否已部署 Exchange Online 和 SharePoint Online？</span><span class="sxs-lookup"><span data-stu-id="49a41-126">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
      - <span data-ttu-id="49a41-127">如果你的组织没有 Exchange Online，请参阅[了解 exchange 和 Microsoft 团队如何交互](exchange-teams-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="49a41-127">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
      - <span data-ttu-id="49a41-128">如果你的组织没有 SharePoint Online，请参阅[了解 Sharepoint online 和 OneDrive For business 如何与 Microsoft 团队进行交互](sharepoint-onedrive-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="49a41-128">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="49a41-129">验证满足这些网络要求后，您可能已准备好[推出团队](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="49a41-129">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="49a41-130">如果你是大型跨国企业版，或者如果你知道你有一些网络限制，请继续阅读，了解如何评估和优化团队的网络。</span><span class="sxs-lookup"><span data-stu-id="49a41-130">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49a41-131">**对于教育机构**：如果您的组织是教育机构，并且您使用学生信息系统（SIS），请在推出团队之前[部署学校数据同步](https://docs.microsoft.com/schooldatasync/)。</span><span class="sxs-lookup"><span data-stu-id="49a41-131">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](https://docs.microsoft.com/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="49a41-132">**运行本地 skype for Business 服务器**：如果你的组织运行的是本地 skype For business 服务器（或 Lync server），则必须[配置 Azure AD Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect)以将本地目录与 Microsoft 365 或 Office 365 同步。</span><span class="sxs-lookup"><span data-stu-id="49a41-132">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Microsoft 365 or Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="49a41-133">最佳做法：使用 CQD 和 call analytics 监控您的网络</span><span class="sxs-lookup"><span data-stu-id="49a41-133">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="49a41-134">使用[通话质量仪表板（CQD）](turning-on-and-using-call-quality-dashboard.md) ，深入了解团队中的通话和会议的质量。</span><span class="sxs-lookup"><span data-stu-id="49a41-134">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="49a41-135">CQD 可通过保持密切关注的质量、可靠性和用户体验来帮助你优化网络。</span><span class="sxs-lookup"><span data-stu-id="49a41-135">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="49a41-136">CQD 查看整个组织的聚合遥测，其中整体模式可能会变得显而易见，这使你可以确定问题并计划补救措施。</span><span class="sxs-lookup"><span data-stu-id="49a41-136">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="49a41-137">此外，CQD 提供了丰富的度量报告，可提供总体质量、可靠性和用户体验的深入见解。</span><span class="sxs-lookup"><span data-stu-id="49a41-137">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="49a41-138">你将使用[调用分析](set-up-call-analytics.md)来调查单个用户的通话和会议问题。</span><span class="sxs-lookup"><span data-stu-id="49a41-138">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="49a41-139">网络优化</span><span class="sxs-lookup"><span data-stu-id="49a41-139">Network optimization</span></span>

<span data-ttu-id="49a41-140">以下任务是可选的，并且不是向团队推出所必需的，尤其是当你是小型企业并且已部署 Microsoft 365 或 Office 365 时。</span><span class="sxs-lookup"><span data-stu-id="49a41-140">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Microsoft 365 or Office 365.</span></span> <span data-ttu-id="49a41-141">使用本指南可优化您的网络和团队性能，或者如果您知道您有一些网络限制。</span><span class="sxs-lookup"><span data-stu-id="49a41-141">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="49a41-142">在以下情况中，可能需要执行其他网络优化：</span><span class="sxs-lookup"><span data-stu-id="49a41-142">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="49a41-143">团队运行缓慢（也许你没有足够的带宽）</span><span class="sxs-lookup"><span data-stu-id="49a41-143">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="49a41-144">呼叫继续丢弃（可能是由于防火墙或代理阻止程序）</span><span class="sxs-lookup"><span data-stu-id="49a41-144">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="49a41-145">呼叫有静电和削减，或者声音类似机器人（可能是抖动或数据包丢失）</span><span class="sxs-lookup"><span data-stu-id="49a41-145">Calls have static and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="49a41-146">有关网络优化的深入讨论，包括用于识别和修复网络障碍的指南，请阅读[Microsoft 365 和 Office 365 网络连接原则](https://aka.ms/pnc)。</span><span class="sxs-lookup"><span data-stu-id="49a41-146">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Microsoft 365 and Office 365 Network Connectivity Principles](https://aka.ms/pnc).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="49a41-147"><strong>网络优化任务</strong></span><span class="sxs-lookup"><span data-stu-id="49a41-147"><strong>Network optimization task</strong></span></span></th>
<th><span data-ttu-id="49a41-148"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="49a41-148"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="49a41-149">网络 planner</span><span class="sxs-lookup"><span data-stu-id="49a41-149">Network planner</span></span></td>
<td><p><span data-ttu-id="49a41-150">有关评估网络的帮助（包括带宽计算和组织的物理位置的网络要求），请查看<a href="https://admin.teams.microsoft.com">团队管理中心</a>内的<a href="https://docs.microsoft.com/microsoftteams/network-planner">网络 Planner</a>工具。</span><span class="sxs-lookup"><span data-stu-id="49a41-150">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="https://docs.microsoft.com/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="49a41-151">当你提供网络详细信息和团队使用情况时，网络 Planner 会计算你的网络要求，以便在组织的物理位置部署团队和云语音。</span><span class="sxs-lookup"><span data-stu-id="49a41-151">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="49a41-152">有关示例方案，请参阅<a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">使用网络 Planner-示例方案</a>。</span><span class="sxs-lookup"><span data-stu-id="49a41-152">For an example scenario, see <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="49a41-153">团队的顾问</span><span class="sxs-lookup"><span data-stu-id="49a41-153">Advisor for Teams</span></span></td>
<td><span data-ttu-id="49a41-154">团队的<a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">顾问</a>是<a href="https://admin.teams.microsoft.com">团队管理中心</a>的一部分。</span><span class="sxs-lookup"><span data-stu-id="49a41-154"><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="49a41-155">它将评估 Microsoft 365 或 Office 365 环境并确定更新或修改所需的最常用配置，帮助你成功推出 Teams。</span><span class="sxs-lookup"><span data-stu-id="49a41-155">It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="49a41-156">外部名称解析</span><span class="sxs-lookup"><span data-stu-id="49a41-156">External Name Resolution</span></span></td>
<td><span data-ttu-id="49a41-157">请确保运行团队客户端的所有计算机可以解析外部 DNS 查询以发现 Microsoft 365 或 Office 365 提供的服务，并且你的防火墙不会阻止访问。</span><span class="sxs-lookup"><span data-stu-id="49a41-157">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Microsoft 365 or Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="49a41-158">有关配置防火墙端口的信息，请转到<a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 和 Office 365 url 和 IP 范围</a>。</span><span class="sxs-lookup"><span data-stu-id="49a41-158">For information about configuring firewall ports, go to <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 and Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="49a41-159">维护会话持久性</span><span class="sxs-lookup"><span data-stu-id="49a41-159">Maintain session persistence</span></span></td>
<td><span data-ttu-id="49a41-160">确保你的防火墙不会更改用于 UDP 的映射网络地址转换（NAT）地址或端口。</span><span class="sxs-lookup"><span data-stu-id="49a41-160">Make sure your firewall doesn't change the mapped Network Address Translation (NAT) addresses or ports for UDP.</span></span></td>
</tr><tr class="odd">
<td><span data-ttu-id="49a41-161">验证 NAT 池大小</span><span class="sxs-lookup"><span data-stu-id="49a41-161">Validate NAT pool size</span></span></td>
<td><span data-ttu-id="49a41-162">验证用户连接所需的网络地址转换（NAT）池大小。</span><span class="sxs-lookup"><span data-stu-id="49a41-162">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="49a41-163">当多个用户和设备使用<a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">网络地址转换（NAT）或端口地址转换（PAT）</a>访问 Microsoft 365 或 Office 365 时，您需要确保隐藏在每个可公共路由的 IP 地址后面的设备不会超过支持的号码。</span><span class="sxs-lookup"><span data-stu-id="49a41-163">When multiple users and devices access Microsoft 365 or Office 365 using <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="49a41-164">确保为 NAT 池分配了足够的公共 IP 地址以防止端口耗尽。</span><span class="sxs-lookup"><span data-stu-id="49a41-164">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="49a41-165">端口耗尽将对内部用户和无法连接到 Microsoft 365 或 Office 365 服务的设备造成影响。</span><span class="sxs-lookup"><span data-stu-id="49a41-165">Port exhaustion will contribute to internal users and devices being unable to connect to the Microsoft 365 or Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="49a41-166">路由到 Microsoft 数据中心</span><span class="sxs-lookup"><span data-stu-id="49a41-166">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="49a41-167"><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">实现最高效的路由到 Microsoft 数据中心</a>。</span><span class="sxs-lookup"><span data-stu-id="49a41-167"><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="49a41-168">确定可使用本地或区域传出点尽可能高效地连接到 Microsoft 网络的位置。</span><span class="sxs-lookup"><span data-stu-id="49a41-168">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="49a41-169">入侵检测和阻止指南</span><span class="sxs-lookup"><span data-stu-id="49a41-169">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="49a41-170">如果你的环境为出站连接的额外安全层部署了<a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">入侵检测</a>或防护系统（IDS/IPS），请确保对所有 Microsoft 365 或 Office 365 url 进行白加白。</span><span class="sxs-lookup"><span data-stu-id="49a41-170">If your environment has an <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to whitelist all Microsoft 365 or Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="49a41-171">配置拆分隧道 VPN</span><span class="sxs-lookup"><span data-stu-id="49a41-171">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="49a41-172">我们建议你为团队流量提供备用路径，该路径绕过虚拟专用网络（VPN），通常称为[拆分隧道 VPN](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing)。</span><span class="sxs-lookup"><span data-stu-id="49a41-172">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as [split-tunnel VPN](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing).</span></span> <span data-ttu-id="49a41-173">拆分隧道意味着 Microsoft 365 或 Office 365 的流量不能通过 VPN，而是直接转到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="49a41-173">Split tunneling means that traffic for Microsoft 365 or Office 365 doesn't go through the VPN but instead goes directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="49a41-174">绕过你的 VPN 将对团队质量产生积极影响，并减少从 VPN 设备和组织网络的负载。</span><span class="sxs-lookup"><span data-stu-id="49a41-174">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="49a41-175">要实现分割隧道 VPN，请与您的 VPN 供应商配合使用。</span><span class="sxs-lookup"><span data-stu-id="49a41-175">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="49a41-176">建议绕过 VPN 的其他原因：</span><span class="sxs-lookup"><span data-stu-id="49a41-176">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="49a41-177">Vpn 一般不是为支持实时媒体而设计或配置的。</span><span class="sxs-lookup"><span data-stu-id="49a41-177">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="49a41-178">某些 Vpn 可能也不支持 UDP （这是团队所必需的）。</span><span class="sxs-lookup"><span data-stu-id="49a41-178">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="49a41-179">Vpn 还会在已加密的媒体流量顶部引入额外的加密层。</span><span class="sxs-lookup"><span data-stu-id="49a41-179">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="49a41-180">由于通过 VPN 设备有头发的流量，到团队的连接可能不会有效。</span><span class="sxs-lookup"><span data-stu-id="49a41-180">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="49a41-181">实施 QoS</span><span class="sxs-lookup"><span data-stu-id="49a41-181">Implement QoS</span></span></td>
<td><span data-ttu-id="49a41-182"><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">使用服务质量（QoS）</a>配置数据包优先级。</span><span class="sxs-lookup"><span data-stu-id="49a41-182"><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="49a41-183">这将改进团队的通话质量，帮助你监控和解决通话质量问题。</span><span class="sxs-lookup"><span data-stu-id="49a41-183">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="49a41-184">应在托管网络的所有段中实现 QoS。</span><span class="sxs-lookup"><span data-stu-id="49a41-184">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="49a41-185">即使已为带宽设置了充足的网络，QoS 在网络事件发生时也会带来风险降低。</span><span class="sxs-lookup"><span data-stu-id="49a41-185">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="49a41-186">通过 QoS，可以确定语音流量的优先顺序，以便这些意外事件不会对质量产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="49a41-186">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="49a41-187">优化 WiFi</span><span class="sxs-lookup"><span data-stu-id="49a41-187">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="49a41-188">与 VPN 类似，WiFi 网络不一定设计或配置为支持实时媒体。</span><span class="sxs-lookup"><span data-stu-id="49a41-188">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="49a41-189">规划或优化 WiFi 网络以支持团队是高质量部署的重要考虑事项。</span><span class="sxs-lookup"><span data-stu-id="49a41-189">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="49a41-190">请考虑以下因素：</span><span class="sxs-lookup"><span data-stu-id="49a41-190">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="49a41-191">实施 QoS 或 WiFi 多媒体（WMM），确保媒体流量在您的 WiFi 网络上得到适当的优先级。</span><span class="sxs-lookup"><span data-stu-id="49a41-191">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="49a41-192">规划和优化 WiFi 频带和接入点放置。</span><span class="sxs-lookup"><span data-stu-id="49a41-192">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="49a41-193">2.4 GHz 范围可能会提供足够的体验，具体取决于接入点的位置，但访问点通常受在该范围内运行的其他消费者设备的影响。</span><span class="sxs-lookup"><span data-stu-id="49a41-193">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="49a41-194">由于其密集范围，5 GHz 范围更适合实时媒体，但需要更多访问点才能获得足够的服务。</span><span class="sxs-lookup"><span data-stu-id="49a41-194">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="49a41-195">此外，终结点还需要相应地支持该范围并配置为利用这些频带。</span><span class="sxs-lookup"><span data-stu-id="49a41-195">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="49a41-196">如果您使用的是双频 WiFi 网络，请考虑实施带通指导委员会。</span><span class="sxs-lookup"><span data-stu-id="49a41-196">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="49a41-197"><em>波段</em>控制是由 WiFi 供应商实施的一项技术，可影响双层客户使用 5 GHz 范围。</span><span class="sxs-lookup"><span data-stu-id="49a41-197"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="49a41-198">当同一频道的接入点太靠近时，它们可能会导致信号重叠并无意间竞争，从而导致用户遇到错误的体验。</span><span class="sxs-lookup"><span data-stu-id="49a41-198">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="49a41-199">确保彼此相邻的接入点位于不重叠的频道上。</span><span class="sxs-lookup"><span data-stu-id="49a41-199">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="49a41-200">每个无线供应商都有自己的无线解决方案部署建议。</span><span class="sxs-lookup"><span data-stu-id="49a41-200">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="49a41-201">有关特定指南，请咨询 WiFi 供应商。</span><span class="sxs-lookup"><span data-stu-id="49a41-201">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="49a41-202">带宽要求</span><span class="sxs-lookup"><span data-stu-id="49a41-202">Bandwidth requirements</span></span>

<span data-ttu-id="49a41-203">团队设计用于提供最佳音频、视频和内容共享体验，无论网络条件如何。</span><span class="sxs-lookup"><span data-stu-id="49a41-203">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="49a41-204">也就是说，当带宽不足时，团队将通过视频质量对音频质量进行优先级排定。</span><span class="sxs-lookup"><span data-stu-id="49a41-204">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="49a41-205">在带宽*不*受限制的情况下，团队会优化媒体质量，包括最高分辨率的视频分辨率、最多30fps 视频和15fps 内容以及高保真音频。</span><span class="sxs-lookup"><span data-stu-id="49a41-205">Where bandwidth *isn't* limited, Teams optimizes media quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span> 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a><span data-ttu-id="49a41-206">相关主题</span><span class="sxs-lookup"><span data-stu-id="49a41-206">Related Topics</span></span>

[<span data-ttu-id="49a41-207">Microsoft 365 和 Office 365 网络连接原理</span><span class="sxs-lookup"><span data-stu-id="49a41-207">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](https://aka.ms/pnc)

[<span data-ttu-id="49a41-208">全球终结点： Skype for Business Online 和团队</span><span class="sxs-lookup"><span data-stu-id="49a41-208">Worldwide endpoints: Skype for Business Online and Teams</span></span>](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="49a41-209">团队的代理服务器</span><span class="sxs-lookup"><span data-stu-id="49a41-209">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="49a41-210">团队中的媒体：为什么会议很简单</span><span class="sxs-lookup"><span data-stu-id="49a41-210">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="49a41-211">团队中的媒体：深入了解媒体流</span><span class="sxs-lookup"><span data-stu-id="49a41-211">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="49a41-212">Teams 中的标识模式和身份验证</span><span class="sxs-lookup"><span data-stu-id="49a41-212">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="49a41-213">如何部署 Teams</span><span class="sxs-lookup"><span data-stu-id="49a41-213">How to roll out Teams</span></span>](How-to-roll-out-teams.md)

