---
title: 为 Teams 准备贵组织的网络
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: 了解如何为 Microsoft Teams 准备组织的网络，包括网络要求、网络优化和带宽要求。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 9212c096323eb57754e0a8a47b61649bec42de87
ms.sourcegitcommit: 5c33ca450a3215b9bf3c5da8bb3c9ef1a715a1a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099567"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="5869f-103">为 Microsoft Teams 准备组织的网络</span><span class="sxs-lookup"><span data-stu-id="5869f-103">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="5869f-104">网络要求</span><span class="sxs-lookup"><span data-stu-id="5869f-104">Network requirements</span></span>

<span data-ttu-id="5869f-105">如果你已针对 [Microsoft 365 或 Office 365](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity)优化网络，则你可能已准备好使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="5869f-105">If you've already [optimized your network for Microsoft 365 or Office 365](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="5869f-106">在任何情况下，尤其是在将 Teams 作为第一个 Microsoft 365 或 Office 365 工作负荷快速推出以支持远程工作者 **的情况下，在开始** 推出 Teams 之前，请检查以下内容：</span><span class="sxs-lookup"><span data-stu-id="5869f-106">In any case - and especially if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="5869f-107">是否所有位置都提供 Internet (以便它们可以连接到 Microsoft 365 或 Office 365) ？</span><span class="sxs-lookup"><span data-stu-id="5869f-107">Do all your locations have internet access (so they can connect to Microsoft 365 or Office 365)?</span></span> <span data-ttu-id="5869f-108">除了正常的 Web 流量外，至少请确保已针对 Teams 中的媒体在所有位置打开以下内容：</span><span class="sxs-lookup"><span data-stu-id="5869f-108">At a minimum, in addition to normal web traffic, make sure you've opened the following, for all locations, for media in Teams:</span></span>

    |  |  |
    |---------|---------|
    |<span data-ttu-id="5869f-109">端口</span><span class="sxs-lookup"><span data-stu-id="5869f-109">Ports</span></span>     |<span data-ttu-id="5869f-110">UDP 端口 <strong>3478</strong> 到 <strong>3481</strong></span><span class="sxs-lookup"><span data-stu-id="5869f-110">UDP ports <strong>3478</strong> through <strong>3481</strong></span></span>        |
    |[<span data-ttu-id="5869f-111">IP 地址</span><span class="sxs-lookup"><span data-stu-id="5869f-111">IP addresses</span></span>](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<span data-ttu-id="5869f-112"><strong>13.107.64.0/18、52.112.0.0/14</strong>和<strong>52.120.0.0/14</strong> <strong></strong></span><span class="sxs-lookup"><span data-stu-id="5869f-112"><strong>13.107.64.0/18</strong>, <strong>52.112.0.0/14</strong>, and <strong>52.120.0.0/14</strong></span></span>         |

    > [!IMPORTANT]
    > <span data-ttu-id="5869f-113">如果需要在本地或在线与 Skype for Business 联合，则需要配置一些额外的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="5869f-113">If you need to federate with Skype for Business, either on-premises or online, you will need to configure some additional DNS records.</span></span>
    >
    >|<span data-ttu-id="5869f-114">CNAME 记录/主机名</span><span class="sxs-lookup"><span data-stu-id="5869f-114">CNAME Records / Host name</span></span>  |<span data-ttu-id="5869f-115">TTL</span><span class="sxs-lookup"><span data-stu-id="5869f-115">TTL</span></span>  |<span data-ttu-id="5869f-116">指向地址或值</span><span class="sxs-lookup"><span data-stu-id="5869f-116">Points to address or value</span></span>  |
    >|---------|---------|---------|
    >|<span data-ttu-id="5869f-117">sip</span><span class="sxs-lookup"><span data-stu-id="5869f-117">sip</span></span>     |    <span data-ttu-id="5869f-118">3600</span><span class="sxs-lookup"><span data-stu-id="5869f-118">3600</span></span>     |    <span data-ttu-id="5869f-119">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5869f-119">sipdir.online.lync.com</span></span>     |
    >|<span data-ttu-id="5869f-120">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5869f-120">lyncdiscover</span></span>     |   <span data-ttu-id="5869f-121">3600</span><span class="sxs-lookup"><span data-stu-id="5869f-121">3600</span></span>      |    <span data-ttu-id="5869f-122">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5869f-122">webdir.online.lync.com</span></span>     |
    
2.  <span data-ttu-id="5869f-123">你是否拥有 Microsoft 365 或 Office 365 (验证域，例如contoso.com) ？</span><span class="sxs-lookup"><span data-stu-id="5869f-123">Do you have a verified domain for Microsoft 365 or Office 365 (for example, contoso.com)?</span></span>
    
    - <span data-ttu-id="5869f-124">如果你的组织尚未推出 Microsoft 365 或 Office 365，请参阅["开始使用"。](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365)</span><span class="sxs-lookup"><span data-stu-id="5869f-124">If your organization hasn't rolled out Microsoft 365 or Office 365, see [Get started](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365).</span></span>
    - <span data-ttu-id="5869f-125">如果你的组织尚未为 Microsoft 365 或 Office 365 添加或配置已验证的域，请参阅 [域常见问题解答](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)。</span><span class="sxs-lookup"><span data-stu-id="5869f-125">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="5869f-126">您的组织是否部署了 Exchange Online 和 SharePoint Online？</span><span class="sxs-lookup"><span data-stu-id="5869f-126">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
    - <span data-ttu-id="5869f-127">如果你的组织没有 Exchange Online，请参阅"了解 Exchange 和[Microsoft Teams 如何交互"。](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="5869f-127">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
    - <span data-ttu-id="5869f-128">如果你的组织没有 SharePoint Online，请参阅"了解 SharePoint Online 和[OneDrive for Business 如何与 Microsoft Teams 交互"。](sharepoint-onedrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="5869f-128">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="5869f-129">确认满足这些网络要求后，可以开始推出[Teams。](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="5869f-129">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="5869f-130">如果你是一家大型的跨国企业，或者你知道自己存在一些网络限制，请继续阅读，了解如何评估和优化 Teams 的网络。</span><span class="sxs-lookup"><span data-stu-id="5869f-130">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5869f-131">**对于教育机构**：如果你的组织是教育机构，并且你使用学生信息系统 (SIS) ，请部署学校数据同步，然后再推出 [](https://docs.microsoft.com/schooldatasync/)Teams。</span><span class="sxs-lookup"><span data-stu-id="5869f-131">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](https://docs.microsoft.com/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="5869f-132">**运行本地 Skype for Business Server：** 如果你的组织运行本地 Skype for Business Server (或 Lync Server) ，则必须配置 Azure [AD Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) 以将本地目录与 Microsoft 365 或 Office 365 同步。</span><span class="sxs-lookup"><span data-stu-id="5869f-132">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Microsoft 365 or Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="5869f-133">最佳做法：使用 CQD 监视网络并调用分析</span><span class="sxs-lookup"><span data-stu-id="5869f-133">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="5869f-134">使用 [CQD (](turning-on-and-using-call-quality-dashboard.md) 呼叫质量) ，深入了解 Teams 中的通话和会议质量。</span><span class="sxs-lookup"><span data-stu-id="5869f-134">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="5869f-135">CQD 可通过密切关注质量、可靠性和用户体验来帮助优化网络。</span><span class="sxs-lookup"><span data-stu-id="5869f-135">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="5869f-136">CQD 查看整个组织的聚合遥测数据，其中总体模式可能变得明显，从而可以识别问题和计划修正。</span><span class="sxs-lookup"><span data-stu-id="5869f-136">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="5869f-137">此外，CQD 还提供丰富的指标报告，用于深入了解整体质量、可靠性和用户体验。</span><span class="sxs-lookup"><span data-stu-id="5869f-137">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="5869f-138">你将使用 [呼叫分析调查](set-up-call-analytics.md) 单个用户的呼叫和会议问题。</span><span class="sxs-lookup"><span data-stu-id="5869f-138">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="5869f-139">网络优化</span><span class="sxs-lookup"><span data-stu-id="5869f-139">Network optimization</span></span>

<span data-ttu-id="5869f-140">以下任务是可选的，在推出 Teams 时不需要，尤其是如果你是小型企业并且已推出 Microsoft 365 或 Office 365 时。</span><span class="sxs-lookup"><span data-stu-id="5869f-140">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Microsoft 365 or Office 365.</span></span> <span data-ttu-id="5869f-141">使用本指南优化网络和 Teams 性能，或者如果知道存在一些网络限制。</span><span class="sxs-lookup"><span data-stu-id="5869f-141">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="5869f-142">如果：可能需要执行其他网络优化：</span><span class="sxs-lookup"><span data-stu-id="5869f-142">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="5869f-143">团队运行速度缓慢 (，可能是因为带宽不足) </span><span class="sxs-lookup"><span data-stu-id="5869f-143">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="5869f-144">调用不断 (可能是防火墙或代理阻止程序) </span><span class="sxs-lookup"><span data-stu-id="5869f-144">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="5869f-145">呼叫具有静态和中断，或者声音像机器人 (可能是抖动或数据包丢失) </span><span class="sxs-lookup"><span data-stu-id="5869f-145">Calls have static and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="5869f-146">有关网络优化的深入讨论，包括识别和修复网络障碍的指南，请阅读 [Microsoft 365 和 Office 365 网络连接原则](https://aka.ms/pnc)。</span><span class="sxs-lookup"><span data-stu-id="5869f-146">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Microsoft 365 and Office 365 Network Connectivity Principles](https://aka.ms/pnc).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="5869f-147"><strong>网络优化任务</strong></span><span class="sxs-lookup"><span data-stu-id="5869f-147"><strong>Network optimization task</strong></span></span></th>
<th><span data-ttu-id="5869f-148"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="5869f-148"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5869f-149">网络规划器</span><span class="sxs-lookup"><span data-stu-id="5869f-149">Network planner</span></span></td>
<td><p><span data-ttu-id="5869f-150">有关评估网络的帮助，包括组织物理位置的带宽计算和网络要求，请查看 Teams 管理中心中的<a href="https://docs.microsoft.com/microsoftteams/network-planner">网络规划</a><a href="https://admin.teams.microsoft.com">器工具</a>。</span><span class="sxs-lookup"><span data-stu-id="5869f-150">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="https://docs.microsoft.com/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="5869f-151">提供网络详细信息和 Teams 使用情况时，网络规划器会计算跨组织的物理位置部署 Teams 和云语音的网络要求。</span><span class="sxs-lookup"><span data-stu-id="5869f-151">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="5869f-152">有关示例方案，请参阅<a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">"使用网络规划器 - 示例方案"。</a></span><span class="sxs-lookup"><span data-stu-id="5869f-152">For an example scenario, see <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5869f-153">Teams 顾问</span><span class="sxs-lookup"><span data-stu-id="5869f-153">Advisor for Teams</span></span></td>
<td><span data-ttu-id="5869f-154"><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">Teams 顾问</a> 是 Teams 管理 <a href="https://admin.teams.microsoft.com">中心的一部分</a>。</span><span class="sxs-lookup"><span data-stu-id="5869f-154"><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="5869f-155">它将评估 Microsoft 365 或 Office 365 环境并确定更新或修改所需的最常用配置，帮助你成功推出 Teams。</span><span class="sxs-lookup"><span data-stu-id="5869f-155">It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5869f-156">外部名称解析</span><span class="sxs-lookup"><span data-stu-id="5869f-156">External Name Resolution</span></span></td>
<td><span data-ttu-id="5869f-157">请确保运行 Teams 客户端的所有计算机都可以解析外部 DNS 查询，以发现 Microsoft 365 或 Office 365 提供的服务，并且防火墙不会阻止访问。</span><span class="sxs-lookup"><span data-stu-id="5869f-157">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Microsoft 365 or Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="5869f-158">有关配置防火墙端口的信息，请转到 Microsoft <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">365 和 Office 365 URL 和 IP 范围</a>。</span><span class="sxs-lookup"><span data-stu-id="5869f-158">For information about configuring firewall ports, go to <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 and Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5869f-159">维护会话持久性</span><span class="sxs-lookup"><span data-stu-id="5869f-159">Maintain session persistence</span></span></td>
<td><span data-ttu-id="5869f-160">请确保防火墙不会更改映射的网络地址转换 (NAT) UDP 的地址或端口。</span><span class="sxs-lookup"><span data-stu-id="5869f-160">Make sure your firewall doesn't change the mapped Network Address Translation (NAT) addresses or ports for UDP.</span></span></td>
</tr><tr class="odd">
<td><span data-ttu-id="5869f-161">验证 NAT 池大小</span><span class="sxs-lookup"><span data-stu-id="5869f-161">Validate NAT pool size</span></span></td>
<td><span data-ttu-id="5869f-162">根据用户连接所需的 (NAT) 网络地址转换。</span><span class="sxs-lookup"><span data-stu-id="5869f-162">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="5869f-163">当多个用户和设备使用网络地址转换 (NAT) 或端口地址转换 <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365"> (PAT) </a>访问 Microsoft 365 或 Office 365 时，需要确保隐藏在每个可公开路由 IP 地址后面的设备不超过支持的数量。</span><span class="sxs-lookup"><span data-stu-id="5869f-163">When multiple users and devices access Microsoft 365 or Office 365 using <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="5869f-164">确保向 NAT 池分配足够的公共 IP 地址，以防止端口耗尽。</span><span class="sxs-lookup"><span data-stu-id="5869f-164">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="5869f-165">端口耗尽会导致内部用户和设备无法连接到 Microsoft 365 或 Office 365 服务。</span><span class="sxs-lookup"><span data-stu-id="5869f-165">Port exhaustion will contribute to internal users and devices being unable to connect to the Microsoft 365 or Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5869f-166">路由到 Microsoft 数据中心</span><span class="sxs-lookup"><span data-stu-id="5869f-166">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="5869f-167"><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">实现到 Microsoft 数据中心的最有效的路由</a>。</span><span class="sxs-lookup"><span data-stu-id="5869f-167"><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="5869f-168">确定可以使用本地或区域出口点尽可能高效地连接到 Microsoft 网络的位置。</span><span class="sxs-lookup"><span data-stu-id="5869f-168">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5869f-169">入侵检测和预防指南</span><span class="sxs-lookup"><span data-stu-id="5869f-169">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="5869f-170">如果为出站连接<a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools"></a>部署了入侵检测或防护系统 (IDS/IPS) ，请确保允许所有 Microsoft 365 或 Office 365 URL。</span><span class="sxs-lookup"><span data-stu-id="5869f-170">If your environment has an <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to allow all Microsoft 365 or Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5869f-171">配置拆分隧道 VPN</span><span class="sxs-lookup"><span data-stu-id="5869f-171">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="5869f-172">我们建议为 Teams 流量提供备用路径，以绕过虚拟专用网络 (VPN) 通常称为拆分隧道<a href="https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing">VPN。</a></span><span class="sxs-lookup"><span data-stu-id="5869f-172">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as <a href="https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing">split-tunnel VPN</a>.</span></span> <span data-ttu-id="5869f-173">拆分隧道意味着 Microsoft 365 或 Office 365 的流量不会通过 VPN，而是直接转到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="5869f-173">Split tunneling means that traffic for Microsoft 365 or Office 365 doesn't go through the VPN but instead goes directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="5869f-174">绕过 VPN 将对 Teams 质量产生积极的影响，并且会减少来自 VPN 设备和组织的网络的负载。</span><span class="sxs-lookup"><span data-stu-id="5869f-174">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="5869f-175">若要实现拆分隧道 VPN，请与 VPN 供应商合作。</span><span class="sxs-lookup"><span data-stu-id="5869f-175">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="5869f-176">建议绕过 VPN 的其他原因：</span><span class="sxs-lookup"><span data-stu-id="5869f-176">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="5869f-177">VPN 通常未设计为或配置为支持实时媒体。</span><span class="sxs-lookup"><span data-stu-id="5869f-177">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="5869f-178">某些 VPN 可能也不支持 Teams (所需的 UDP) 。</span><span class="sxs-lookup"><span data-stu-id="5869f-178">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="5869f-179">VPN 还会基于已加密的媒体流量引入额外的加密层。</span><span class="sxs-lookup"><span data-stu-id="5869f-179">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="5869f-180">由于通过 VPN 设备将流量固定在一起，与 Teams 的连接可能效率不够。</span><span class="sxs-lookup"><span data-stu-id="5869f-180">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5869f-181">实施 QoS</span><span class="sxs-lookup"><span data-stu-id="5869f-181">Implement QoS</span></span></td>
<td><span data-ttu-id="5869f-182"><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">使用服务质量和 QoS (</a> 配置) 优先级。</span><span class="sxs-lookup"><span data-stu-id="5869f-182"><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="5869f-183">这将提高 Teams 中的呼叫质量，并帮助你监视和排查呼叫质量问题。</span><span class="sxs-lookup"><span data-stu-id="5869f-183">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="5869f-184">QoS 应在托管网络的所有分段上实现。</span><span class="sxs-lookup"><span data-stu-id="5869f-184">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="5869f-185">即使网络已充分预配带宽，QoS 也能够针对意外的网络事件提供风险缓解。</span><span class="sxs-lookup"><span data-stu-id="5869f-185">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="5869f-186">使用 QoS 时，语音流量具有优先级，以便这些意外事件不会对质量造成负面影响。</span><span class="sxs-lookup"><span data-stu-id="5869f-186">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5869f-187">优化 WiFi</span><span class="sxs-lookup"><span data-stu-id="5869f-187">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="5869f-188">与 VPN 类似，WiFi 网络不一定设计为或配置为支持实时媒体。</span><span class="sxs-lookup"><span data-stu-id="5869f-188">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="5869f-189">规划或优化 WiFi 网络以支持 Teams 是高质量部署的一个重要考虑因素。</span><span class="sxs-lookup"><span data-stu-id="5869f-189">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="5869f-190">请考虑以下因素：</span><span class="sxs-lookup"><span data-stu-id="5869f-190">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="5869f-191">使用 WMM (QoS 或 WiFi 多媒体) 以确保媒体流量在 WiFi 网络上获得适当的优先级。</span><span class="sxs-lookup"><span data-stu-id="5869f-191">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="5869f-192">计划和优化 WiFi 带和接入点位置。</span><span class="sxs-lookup"><span data-stu-id="5869f-192">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="5869f-193">2.4 GHz 范围可能提供足够的体验，具体取决于接入点的位置，但访问点通常受该范围内运行的其他使用者设备的影响。</span><span class="sxs-lookup"><span data-stu-id="5869f-193">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="5869f-194">由于 5 GHz 范围密集，因此更适合实时媒体，但需要更多的接入点才能获得足够的覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="5869f-194">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="5869f-195">此外，终结点还需要相应地支持该范围并配置为利用这些频带。</span><span class="sxs-lookup"><span data-stu-id="5869f-195">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="5869f-196">如果你使用的是双带 WiFi 网络，请考虑实施带引导。</span><span class="sxs-lookup"><span data-stu-id="5869f-196">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="5869f-197"><em>带式操纵</em> 是 WiFi 供应商实现的技术，用于影响双带客户端使用 5 GHz 范围。</span><span class="sxs-lookup"><span data-stu-id="5869f-197"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="5869f-198">当同一通道的接入点过于靠近时，它们可能会导致信号重叠和意外竞争，从而导致用户体验不佳。</span><span class="sxs-lookup"><span data-stu-id="5869f-198">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="5869f-199">确保彼此旁边的接入点位于不重叠的通道上。</span><span class="sxs-lookup"><span data-stu-id="5869f-199">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="5869f-200">每个无线供应商都有自己的无线解决方案部署建议。</span><span class="sxs-lookup"><span data-stu-id="5869f-200">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="5869f-201">有关具体指南，请咨询 WiFi 供应商。</span><span class="sxs-lookup"><span data-stu-id="5869f-201">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="5869f-202">带宽要求</span><span class="sxs-lookup"><span data-stu-id="5869f-202">Bandwidth requirements</span></span>

<span data-ttu-id="5869f-203">Teams 旨在提供最佳的音频、视频和内容共享体验，而不管网络状况如何。</span><span class="sxs-lookup"><span data-stu-id="5869f-203">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="5869f-204">也就是说，当带宽不足时，Teams 将音频质量比视频质量优先。</span><span class="sxs-lookup"><span data-stu-id="5869f-204">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="5869f-205">在带宽没有限制的地方，Teams 会优化媒体质量，包括高达 1080p 视频分辨率、高达 30fps 的视频和 15fps 的内容以及高保真音频。</span><span class="sxs-lookup"><span data-stu-id="5869f-205">Where bandwidth *isn't* limited, Teams optimizes media quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span> 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a><span data-ttu-id="5869f-206">相关主题</span><span class="sxs-lookup"><span data-stu-id="5869f-206">Related Topics</span></span>

[<span data-ttu-id="5869f-207">Microsoft 365 和 Office 365 网络连接原则</span><span class="sxs-lookup"><span data-stu-id="5869f-207">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](https://aka.ms/pnc)

[<span data-ttu-id="5869f-208">全球终结点：Skype for Business Online 和 Teams</span><span class="sxs-lookup"><span data-stu-id="5869f-208">Worldwide endpoints: Skype for Business Online and Teams</span></span>](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="5869f-209">Teams 的代理服务器</span><span class="sxs-lookup"><span data-stu-id="5869f-209">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="5869f-210">Teams 中的媒体：为什么会议简单</span><span class="sxs-lookup"><span data-stu-id="5869f-210">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="5869f-211">Teams 中的媒体：深入探讨媒体流</span><span class="sxs-lookup"><span data-stu-id="5869f-211">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="5869f-212">Teams 中的标识模式和身份验证</span><span class="sxs-lookup"><span data-stu-id="5869f-212">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="5869f-213">如何部署 Teams</span><span class="sxs-lookup"><span data-stu-id="5869f-213">How to roll out Teams</span></span>](How-to-roll-out-teams.md)

[<span data-ttu-id="5869f-214">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="5869f-214">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
