---
title: 为 Teams 准备组织网络
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: 了解如何为 Microsoft Teams 准备组织网络，包括网络要求、网络优化和带宽要求。
localization_priority: Priority
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
ms.openlocfilehash: db911db3631caebb0e767401f80c36bdac6c9c1b
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420827"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="cf61c-103">为 Microsoft Teams 准备组织网络</span><span class="sxs-lookup"><span data-stu-id="cf61c-103">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="cf61c-104">网络要求</span><span class="sxs-lookup"><span data-stu-id="cf61c-104">Network requirements</span></span>

<span data-ttu-id="cf61c-105">如果您已[针对 Microsoft 365 或Office 365 应用优化了网络](/Office365/Enterprise/assessing-network-connectivity)，您可能已准备好使用 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="cf61c-105">If you've already [optimized your network for Microsoft 365 or Office 365](/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="cf61c-106">无论是哪种情况——尤其是将Teams作为首个 Microsoft 365 或 Office 365 工作负载迅速推出以支持 **远程工作者** 时——请在推出 Teams 之前检查以下内容：</span><span class="sxs-lookup"><span data-stu-id="cf61c-106">In any case - and especially if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="cf61c-107">是否所有场所都可以访问 Internet （以便连接到 Microsoft 365 或 Office 365）？</span><span class="sxs-lookup"><span data-stu-id="cf61c-107">Do all your locations have internet access (so they can connect to Microsoft 365 or Office 365)?</span></span> <span data-ttu-id="cf61c-108">除了正常的 Web 流量，请确保已打开在 [Office 365 URL 和 IP 地址范围中为 Teams 列出的 TCP 端口和 IP 地址](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="cf61c-108">In addition to normal web traffic, make sure you've opened the TCP ports and IP addresses listed for Teams in [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="cf61c-109">如果需要与本地或联机 Skype for Business 联合，则需要配置一些额外的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="cf61c-109">If you need to federate with Skype for Business, either on-premises or online, you will need to configure an additional DNS record.</span></span>
    >
    >|<span data-ttu-id="cf61c-110">DNS 记录</span><span class="sxs-lookup"><span data-stu-id="cf61c-110">DNS record</span></span>  |<span data-ttu-id="cf61c-111">服务</span><span class="sxs-lookup"><span data-stu-id="cf61c-111">Service</span></span>  |<span data-ttu-id="cf61c-112">协议</span><span class="sxs-lookup"><span data-stu-id="cf61c-112">Protocol</span></span>  |<span data-ttu-id="cf61c-113">优先级</span><span class="sxs-lookup"><span data-stu-id="cf61c-113">Priority</span></span>  |<span data-ttu-id="cf61c-114">权重</span><span class="sxs-lookup"><span data-stu-id="cf61c-114">Weight</span></span>  |<span data-ttu-id="cf61c-115">端口</span><span class="sxs-lookup"><span data-stu-id="cf61c-115">Port</span></span>  |<span data-ttu-id="cf61c-116">目标</span><span class="sxs-lookup"><span data-stu-id="cf61c-116">Target</span></span>  |
    >|---------|---------|---------|---------|---------|---------|---------|
    >|<span data-ttu-id="cf61c-117">SRV</span><span class="sxs-lookup"><span data-stu-id="cf61c-117">SRV</span></span>     |<span data-ttu-id="cf61c-118">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="cf61c-118">sipfederationtls</span></span>     |<span data-ttu-id="cf61c-119">TCP</span><span class="sxs-lookup"><span data-stu-id="cf61c-119">TCP</span></span>     |<span data-ttu-id="cf61c-120">100</span><span class="sxs-lookup"><span data-stu-id="cf61c-120">100</span></span>     |<span data-ttu-id="cf61c-121">{1}</span><span class="sxs-lookup"><span data-stu-id="cf61c-121">1</span></span>     |<span data-ttu-id="cf61c-122">5061</span><span class="sxs-lookup"><span data-stu-id="cf61c-122">5061</span></span>     |<span data-ttu-id="cf61c-123">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cf61c-123">sipfed.online.lync.com</span></span>     |
    
2.  <span data-ttu-id="cf61c-124">您是否拥有 Microsoft 365 或 Office 365 的验证域（例如，contoso.com）？</span><span class="sxs-lookup"><span data-stu-id="cf61c-124">Do you have a verified domain for Microsoft 365 or Office 365 (for example, contoso.com)?</span></span>
    
    - <span data-ttu-id="cf61c-125">如果您的组织尚未推出 Microsoft 365 或 Office 365，请参阅 [入门](/microsoft-365/admin/admin-overview/get-started-with-office-365)。</span><span class="sxs-lookup"><span data-stu-id="cf61c-125">If your organization hasn't rolled out Microsoft 365 or Office 365, see [Get started](/microsoft-365/admin/admin-overview/get-started-with-office-365).</span></span>
    - <span data-ttu-id="cf61c-126">如果您的组织尚未添加或配置 Microsoft 365 或 Office 365 的验证域，请参阅 [域常见问题解答](/microsoft-365/admin/setup/domains-faq)。</span><span class="sxs-lookup"><span data-stu-id="cf61c-126">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see the [Domains FAQ](/microsoft-365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="cf61c-127">您的组织是否部署了 Exchange Online 和 SharePoint Online？</span><span class="sxs-lookup"><span data-stu-id="cf61c-127">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
    - <span data-ttu-id="cf61c-128">如果您的组织没有 Exchange Online，请参阅[了解 Exchange 与 Microsoft Teams 如何交互](exchange-teams-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="cf61c-128">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
    - <span data-ttu-id="cf61c-129">如果您的组织没有 SharePoint Online，请参阅[了解 SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](sharepoint-onedrive-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="cf61c-129">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="cf61c-130">确认满足这些网络要求后，即可推出 [Teams](./deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="cf61c-130">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](./deploy-overview.md).</span></span> <span data-ttu-id="cf61c-131">如果您是大型跨国企业，或者清楚自身存在一些网络限制，请继续阅读，了解如何针对 Teams 对您的网络进行评估和优化。</span><span class="sxs-lookup"><span data-stu-id="cf61c-131">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf61c-132">**对于教育机构**：如果您的组织是教育机构，并且使用学生信息系统 （SIS）， 请 [部署学校数据同步](/schooldatasync/) 之后再推出 Teams。</span><span class="sxs-lookup"><span data-stu-id="cf61c-132">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="cf61c-133">**运行本地 Skype for Business Server**：如果您的组织正在运行本地 Skype for Business Server（或 Lync Server），则必须 [配置 Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) 以将您的本地目录与 Microsoft 365 或 Office 365 同步。</span><span class="sxs-lookup"><span data-stu-id="cf61c-133">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Microsoft 365 or Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="cf61c-134">最佳做法：使用 CQD 和呼叫分析监视网络</span><span class="sxs-lookup"><span data-stu-id="cf61c-134">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="cf61c-135">利用 [通话质量仪表板 （CQD）](turning-on-and-using-call-quality-dashboard.md) 了解 Teams 中通话和会议的质量。</span><span class="sxs-lookup"><span data-stu-id="cf61c-135">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="cf61c-136">CQD 通过密切关注质量、可靠性和用户体验来帮助您优化网络。</span><span class="sxs-lookup"><span data-stu-id="cf61c-136">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="cf61c-137">CQD 对整个组织的聚合遥测可以凸显出其整体模式，以便于识别问题并规划改进措施。</span><span class="sxs-lookup"><span data-stu-id="cf61c-137">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="cf61c-138">此外，CQD 所提供的丰富的指标报告内包含对整体质量、可靠性和用户体验的洞见。</span><span class="sxs-lookup"><span data-stu-id="cf61c-138">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="cf61c-139">你将使用 [呼叫分析](set-up-call-analytics.md) 来调查单个用户的通话和会议问题。</span><span class="sxs-lookup"><span data-stu-id="cf61c-139">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="cf61c-140">网络优化</span><span class="sxs-lookup"><span data-stu-id="cf61c-140">Network optimization</span></span>

<span data-ttu-id="cf61c-141">以下任务不是推出 Teams 所必需的，尤其是对于已推出 Microsoft 365 或 Office 365 的小型企业。</span><span class="sxs-lookup"><span data-stu-id="cf61c-141">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Microsoft 365 or Office 365.</span></span> <span data-ttu-id="cf61c-142">如果需要优化网络和 Teams 性能，或者存在已知网络限制时，请使用本指南。</span><span class="sxs-lookup"><span data-stu-id="cf61c-142">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="cf61c-143">如果存在以下情况，建议进行额外的网络优化：</span><span class="sxs-lookup"><span data-stu-id="cf61c-143">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="cf61c-144">Teams 运行速度较慢（可能带宽不足）</span><span class="sxs-lookup"><span data-stu-id="cf61c-144">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="cf61c-145">通话频繁掉线（可能由于防火墙或代理阻止程序）</span><span class="sxs-lookup"><span data-stu-id="cf61c-145">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="cf61c-146">通话有杂音并且时断时续，或者语音生硬（可能因为信号波动或数据包丢失）</span><span class="sxs-lookup"><span data-stu-id="cf61c-146">Calls have static and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="cf61c-147">如需深入了解网络优化相关内容，包括如何识别和修复网络故障，请参阅 [Microsoft 365 和 Office 365 网络连接原则](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)。</span><span class="sxs-lookup"><span data-stu-id="cf61c-147">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Microsoft 365 and Office 365 Network Connectivity Principles](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="cf61c-148">网络优化任务</span><span class="sxs-lookup"><span data-stu-id="cf61c-148">Network optimization task</span></span></th>
<th><span data-ttu-id="cf61c-149">详细信息</span><span class="sxs-lookup"><span data-stu-id="cf61c-149">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="cf61c-150">网络规划器</span><span class="sxs-lookup"><span data-stu-id="cf61c-150">Network planner</span></span></td>
<td><p><span data-ttu-id="cf61c-151">如需评估您组织所有地点的网络，包括带宽计算和网络要求，请参阅 <a href="https://admin.teams.microsoft.com">Teams 管理中心</a> 内的 <a href="/microsoftteams/network-planner">网络规划</a> 工具。</span><span class="sxs-lookup"><span data-stu-id="cf61c-151">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="cf61c-152">只要您提供网络的详细信息和 Teams 的使用场景，网络规划器便会计算出在您组织的所有地点部署 Teams 和云语音的网络要求。</span><span class="sxs-lookup"><span data-stu-id="cf61c-152">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="cf61c-153">如需了解示例方案，请参阅 <a href="/microsoftteams/tutorial-network-planner-example">使用网络规划器 - 示例方案</a>。</span><span class="sxs-lookup"><span data-stu-id="cf61c-153">For an example scenario, see <a href="/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cf61c-154">Teams 顾问</span><span class="sxs-lookup"><span data-stu-id="cf61c-154">Advisor for Teams</span></span></td>
<td><span data-ttu-id="cf61c-155"><a href="/microsoftteams/use-advisor-teams-roll-out">Teams 顾问</a> 是 <a href="https://admin.teams.microsoft.com">Teams 管理中心</a> 的一部分。</span><span class="sxs-lookup"><span data-stu-id="cf61c-155"><a href="/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="cf61c-156">它将评估 Microsoft 365 或 Office 365 环境并确定更新或修改所需的最常用配置，帮助你成功推出 Teams。</span><span class="sxs-lookup"><span data-stu-id="cf61c-156">It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cf61c-157">外部名称解析</span><span class="sxs-lookup"><span data-stu-id="cf61c-157">External Name Resolution</span></span></td>
<td><span data-ttu-id="cf61c-158">确保所有运行 Teams 客户端的计算机都可以解析外部 DNS 查询，以发现您的防火墙没有阻止访问的 Microsoft 365 或 Office 365 服务。</span><span class="sxs-lookup"><span data-stu-id="cf61c-158">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Microsoft 365 or Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="cf61c-159">关于配置防火墙端口的内容，请参阅 <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 和 Office 365 URL 和 IP 范围</a>。</span><span class="sxs-lookup"><span data-stu-id="cf61c-159">For information about configuring firewall ports, go to <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 and Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cf61c-160">维持会话持续性</span><span class="sxs-lookup"><span data-stu-id="cf61c-160">Maintain session persistence</span></span></td>
<td><span data-ttu-id="cf61c-161">请确保防火墙不会更改 UDP 的映射网络地址转换 （NAT） 地址或端口。</span><span class="sxs-lookup"><span data-stu-id="cf61c-161">Make sure your firewall doesn't change the mapped Network Address Translation (NAT) addresses or ports for UDP.</span></span></td>
</tr><tr class="odd">
<td><span data-ttu-id="cf61c-162">验证 NAT 池大小</span><span class="sxs-lookup"><span data-stu-id="cf61c-162">Validate NAT pool size</span></span></td>
<td><span data-ttu-id="cf61c-163">验证用户连接所需的网络地址转换 （NAT） 池大小。</span><span class="sxs-lookup"><span data-stu-id="cf61c-163">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="cf61c-164">当多个用户和设备使用 <a href="/office365/enterprise/nat-support-with-office-365">网络地址转换 （NAT） 或端口地址转换 （PAT）</a>访问 Microsoft 365 或 Office 365 时，需要确保每个可公开路由 IP 地址后隐藏的设备不超过支持的数量。</span><span class="sxs-lookup"><span data-stu-id="cf61c-164">When multiple users and devices access Microsoft 365 or Office 365 using <a href="/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="cf61c-165">确保向 NAT 池分配了充足的公共 IP 地址，以防止端口耗尽。</span><span class="sxs-lookup"><span data-stu-id="cf61c-165">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="cf61c-166">端口耗尽将造成内部用户和设备无法连接到 Microsoft 365 或 Office 365 服务。</span><span class="sxs-lookup"><span data-stu-id="cf61c-166">Port exhaustion will contribute to internal users and devices being unable to connect to the Microsoft 365 or Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cf61c-167">路由至 Microsoft 数据中心</span><span class="sxs-lookup"><span data-stu-id="cf61c-167">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="cf61c-168"><a href="/office365/enterprise/client-connectivity">实现到 Microsoft 数据中心的最有效的路由</a>。</span><span class="sxs-lookup"><span data-stu-id="cf61c-168"><a href="/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="cf61c-169">尽可能有效地识别可使用本地或区域出口点连接到 Microsoft 网络的位置。</span><span class="sxs-lookup"><span data-stu-id="cf61c-169">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cf61c-170">入侵检测和防护指南</span><span class="sxs-lookup"><span data-stu-id="cf61c-170">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="cf61c-171">如果您的环境为了额外提高出站连接安全性而部署了 <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">入侵检测</a> 或防护系统 （IDS/IPS），请确保允许所有 Microsoft 365 或 Office 365 URL。</span><span class="sxs-lookup"><span data-stu-id="cf61c-171">If your environment has an <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to allow all Microsoft 365 or Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cf61c-172">配置拆分通道 VPN</span><span class="sxs-lookup"><span data-stu-id="cf61c-172">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="cf61c-173">建议为 Teams 流量提供一个绕过虚拟专用网络（VPN）的备用路径 <a href="/windows/security/identity-protection/vpn/vpn-routing">（通常被称为“拆分通道 VPN”）</a>。</span><span class="sxs-lookup"><span data-stu-id="cf61c-173">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as <a href="/windows/security/identity-protection/vpn/vpn-routing">split-tunnel VPN</a>.</span></span> <span data-ttu-id="cf61c-174">拆分通道意味着 Microsoft 365 或 Office 365 的流量不会通过 VPN，而是直接转到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="cf61c-174">Split tunneling means that traffic for Microsoft 365 or Office 365 doesn't go through the VPN but instead goes directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="cf61c-175">绕过 VPN 可以改善 Teams 使用质量，并减少来自 VPN 设备和组织网络的负载。</span><span class="sxs-lookup"><span data-stu-id="cf61c-175">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="cf61c-176">要实施拆分通道 VPN，请咨询 VPN 供应商。</span><span class="sxs-lookup"><span data-stu-id="cf61c-176">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="cf61c-177">建议绕过 VPN 的其他原因：</span><span class="sxs-lookup"><span data-stu-id="cf61c-177">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="cf61c-178">VPN 通常没有设计或配置为支持实时媒体。</span><span class="sxs-lookup"><span data-stu-id="cf61c-178">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="cf61c-179">某些 VPN 可能也不支持 UDP（Teams 需要 UDP）。</span><span class="sxs-lookup"><span data-stu-id="cf61c-179">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="cf61c-180">VPN 还会在已加密的媒体流量之上额外引入一层加密。</span><span class="sxs-lookup"><span data-stu-id="cf61c-180">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="cf61c-181">由于流量经过 VPN 设备的回流，与 Teams 的连接效率可能不高。</span><span class="sxs-lookup"><span data-stu-id="cf61c-181">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="cf61c-182">实施 QoS</span><span class="sxs-lookup"><span data-stu-id="cf61c-182">Implement QoS</span></span></td>
<td><span data-ttu-id="cf61c-183"><a href="/microsoftteams/qos-in-teams">使用服务质量 （QoS）</a> 来配置数据包优先顺序。</span><span class="sxs-lookup"><span data-stu-id="cf61c-183"><a href="/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="cf61c-184">这将提高 Teams 的通话质量，并帮助监视和解决通话质量问题。</span><span class="sxs-lookup"><span data-stu-id="cf61c-184">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="cf61c-185">QoS 应在托管网络的所有段上实施。</span><span class="sxs-lookup"><span data-stu-id="cf61c-185">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="cf61c-186">即使网络带宽已预配充分，QoS 也可在发生意外网络事件时缓解风险。</span><span class="sxs-lookup"><span data-stu-id="cf61c-186">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="cf61c-187">QoS 会优先传输语音流量，以避免意外事件影响通话质量。</span><span class="sxs-lookup"><span data-stu-id="cf61c-187">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="cf61c-188">优化 WiFi</span><span class="sxs-lookup"><span data-stu-id="cf61c-188">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="cf61c-189">与 VPN 类似，WiFi 网络不一定设计或配置为支持实时媒体。</span><span class="sxs-lookup"><span data-stu-id="cf61c-189">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="cf61c-190">为支持 Teams 而规划或优化 Wi-Fi 网络是实现高质量部署的一个重要考虑事项。</span><span class="sxs-lookup"><span data-stu-id="cf61c-190">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="cf61c-191">请考虑以下因素：</span><span class="sxs-lookup"><span data-stu-id="cf61c-191">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="cf61c-192">实施 QoS 或 Wi-Fi 多媒体 (WMM)，以确保您的 Wi-Fi 网络优先处理媒体流量。</span><span class="sxs-lookup"><span data-stu-id="cf61c-192">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="cf61c-193">规划和优化 Wi-Fi 频带和接入点位置。</span><span class="sxs-lookup"><span data-stu-id="cf61c-193">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="cf61c-194">如果接入点位置合理， 2.4 GHz 频段也有可能提供合格的体验，但接入点通常会受到该频段内运行的其他用户设备的影响。</span><span class="sxs-lookup"><span data-stu-id="cf61c-194">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="cf61c-195">5 GHz 频段因其密集性更适合实时媒体，但需要更多接入点以获取充足的覆盖率。</span><span class="sxs-lookup"><span data-stu-id="cf61c-195">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="cf61c-196">另外，终结点还需要支持此频段，并进行相应配置才能利用这些频带。</span><span class="sxs-lookup"><span data-stu-id="cf61c-196">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="cf61c-197">如果部署的是双频 Wi-Fi 网络，不妨实施频带切换。</span><span class="sxs-lookup"><span data-stu-id="cf61c-197">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="cf61c-198"><em>频带转向</em>是一种由 Wi-Fi 供应商实现的技术，用于引导双频客户端使用 5GHz 频段。</span><span class="sxs-lookup"><span data-stu-id="cf61c-198"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="cf61c-199">如果同一信道的接入点距离太近，可能会造成信号重叠，在无意中产生竞争，进而导致用户体验不佳。</span><span class="sxs-lookup"><span data-stu-id="cf61c-199">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="cf61c-200">请确保相邻接入点的信道不会重叠。</span><span class="sxs-lookup"><span data-stu-id="cf61c-200">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="cf61c-201">每个无线供应商都有自己的无线解决方案部署建议。</span><span class="sxs-lookup"><span data-stu-id="cf61c-201">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="cf61c-202">请咨询您的 WiFi 供应商以寻求具体指导。</span><span class="sxs-lookup"><span data-stu-id="cf61c-202">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="cf61c-203">带宽要求</span><span class="sxs-lookup"><span data-stu-id="cf61c-203">Bandwidth requirements</span></span>

<span data-ttu-id="cf61c-204">Teams 旨在不受网络条件限制，提供最佳音频、视频和内容共享体验。</span><span class="sxs-lookup"><span data-stu-id="cf61c-204">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="cf61c-205">话虽如此，当带宽不足时，Teams 将优先确保音频质量，其次才是视频质量。</span><span class="sxs-lookup"><span data-stu-id="cf61c-205">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="cf61c-206">如果带宽不受限制，Teams 会优化媒体质量，包括高保真音频、高达 1080p 的视频分辨率，以及高达 30fps（帧/秒）的视频和内容。</span><span class="sxs-lookup"><span data-stu-id="cf61c-206">Where bandwidth isn't limited, Teams optimizes media quality, including high-fidelity audio, up to 1080p video resolution, and up to 30fps (frames per second) for video and content.</span></span>

<span data-ttu-id="cf61c-207">下表介绍 Teams 如何使用带宽。</span><span class="sxs-lookup"><span data-stu-id="cf61c-207">This table describes how Teams uses bandwidth.</span></span> <span data-ttu-id="cf61c-208">Teams 在带宽利用率方面始终保守，可在 1.5Mbps 以下提供高清视频质量。</span><span class="sxs-lookup"><span data-stu-id="cf61c-208">Teams is always conservative on bandwidth utilization and can deliver HD video quality in under 1.5Mbps.</span></span> <span data-ttu-id="cf61c-209">每个音频/视频通话或会议中的实际带宽消耗量将取决于多种因素，如视频布局、视频分辨率和每秒视频帧。</span><span class="sxs-lookup"><span data-stu-id="cf61c-209">The actual bandwidth consumption in each audio/video call or meeting will vary based on several factors, such as video layout, video resolution, and video frames per second.</span></span> <span data-ttu-id="cf61c-210">如果有更多带宽可用，质量和使用率将会增加，以提供最佳体验。</span><span class="sxs-lookup"><span data-stu-id="cf61c-210">When more bandwidth is available, quality and usage will increase to deliver the best experience.</span></span>

:::row:::
   :::column span="":::
      <span data-ttu-id="cf61c-211">**形态**</span><span class="sxs-lookup"><span data-stu-id="cf61c-211">**Modality**</span></span>
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="cf61c-212">**带宽要求（比特率 KB/s 向上/向下）**</span><span class="sxs-lookup"><span data-stu-id="cf61c-212">**Bandwidth requirements (bitrate KB/s up/down)**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="cf61c-213">**最小值**</span><span class="sxs-lookup"><span data-stu-id="cf61c-213">**Minimum**</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="cf61c-214">**建议**</span><span class="sxs-lookup"><span data-stu-id="cf61c-214">**Recommended**</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="cf61c-215">**最佳性能**</span><span class="sxs-lookup"><span data-stu-id="cf61c-215">**Best performance**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="cf61c-216">**音频**</span><span class="sxs-lookup"><span data-stu-id="cf61c-216">**Audio**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="cf61c-217">一对一</span><span class="sxs-lookup"><span data-stu-id="cf61c-217">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-218">10/10</span><span class="sxs-lookup"><span data-stu-id="cf61c-218">10/10</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-219">58/58</span><span class="sxs-lookup"><span data-stu-id="cf61c-219">58/58</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-220">76/76</span><span class="sxs-lookup"><span data-stu-id="cf61c-220">76/76</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="cf61c-221">会议</span><span class="sxs-lookup"><span data-stu-id="cf61c-221">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-222">10/10</span><span class="sxs-lookup"><span data-stu-id="cf61c-222">10/10</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-223">58/58</span><span class="sxs-lookup"><span data-stu-id="cf61c-223">58/58</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-224">76/76</span><span class="sxs-lookup"><span data-stu-id="cf61c-224">76/76</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="cf61c-225">**Video**</span><span class="sxs-lookup"><span data-stu-id="cf61c-225">**Video**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="cf61c-226">一对一</span><span class="sxs-lookup"><span data-stu-id="cf61c-226">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-227">150/150</span><span class="sxs-lookup"><span data-stu-id="cf61c-227">150/150</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-228">1,500/1,500</span><span class="sxs-lookup"><span data-stu-id="cf61c-228">1,500/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-229">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="cf61c-229">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="cf61c-230">会议</span><span class="sxs-lookup"><span data-stu-id="cf61c-230">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-231">150/200</span><span class="sxs-lookup"><span data-stu-id="cf61c-231">150/200</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-232">2,500/4,000</span><span class="sxs-lookup"><span data-stu-id="cf61c-232">2,500/4,000</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-233">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="cf61c-233">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="cf61c-234">**屏幕共享**</span><span class="sxs-lookup"><span data-stu-id="cf61c-234">**Screen sharing**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="cf61c-235">一对一</span><span class="sxs-lookup"><span data-stu-id="cf61c-235">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-236">200/200</span><span class="sxs-lookup"><span data-stu-id="cf61c-236">200/200</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-237">1,500/1,500</span><span class="sxs-lookup"><span data-stu-id="cf61c-237">1,500/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-238">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="cf61c-238">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="cf61c-239">会议</span><span class="sxs-lookup"><span data-stu-id="cf61c-239">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-240">250/250</span><span class="sxs-lookup"><span data-stu-id="cf61c-240">250/250</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-241">2,500/2,500</span><span class="sxs-lookup"><span data-stu-id="cf61c-241">2,500/2,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-242">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="cf61c-242">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="cf61c-243">**同框场景模式**</span><span class="sxs-lookup"><span data-stu-id="cf61c-243">**Together Mode**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="cf61c-244">一对一</span><span class="sxs-lookup"><span data-stu-id="cf61c-244">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-245">不适用</span><span class="sxs-lookup"><span data-stu-id="cf61c-245">N/A</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-246">不适用</span><span class="sxs-lookup"><span data-stu-id="cf61c-246">N/A</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-247">不适用</span><span class="sxs-lookup"><span data-stu-id="cf61c-247">N/A</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="cf61c-248">会议</span><span class="sxs-lookup"><span data-stu-id="cf61c-248">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-249">1,000/1,500</span><span class="sxs-lookup"><span data-stu-id="cf61c-249">1,000/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-250">1,500/2,500</span><span class="sxs-lookup"><span data-stu-id="cf61c-250">1,500/2,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="cf61c-251">2,500/4,000</span><span class="sxs-lookup"><span data-stu-id="cf61c-251">2,500/4,000</span></span>
   :::column-end:::
:::row-end:::

<span data-ttu-id="cf61c-252">**最小**、 **推荐** 和 **最佳性能** 带宽要求基于每个终结点的使用情况。</span><span class="sxs-lookup"><span data-stu-id="cf61c-252">**Minimum**, **Recommended**, and **Best performance** bandwidth requirements are based on per-endpoint usage.</span></span> <span data-ttu-id="cf61c-253">通常，每个用户都有一个终结点，例如计算机或移动设备。</span><span class="sxs-lookup"><span data-stu-id="cf61c-253">Typically, there's one endpoint per user, such as a computer or mobile device.</span></span> <span data-ttu-id="cf61c-254">但是，如果用户在 *同时* 计算机 *和移动设备* 加入 Teams 会议，则两个终结点将与该用户关联。</span><span class="sxs-lookup"><span data-stu-id="cf61c-254">However, if a user joins a Teams meeting on *both* a computer *and* a mobile device, two endpoints are associated with that user.</span></span>

- <span data-ttu-id="cf61c-255">**视频通话的最小** 带宽要求最高为 240p 分辨率，屏幕共享内容帧速率自适应为 1.875 到 7.5fps，而"协同模式/大型库"视频分辨率高达 540p。</span><span class="sxs-lookup"><span data-stu-id="cf61c-255">**Minimum** Bandwidth requirements for video calls are up to 240p resolution, screen sharing content frame rates adaptive 1.875 to 7.5fps, and Together Mode/Large Gallery video up to 540p resolution.</span></span>  

- <span data-ttu-id="cf61c-256">**建议** 视频通话带宽要求高达 1080p 分辨率<sup>\*</sup>、屏幕共享内容帧速率自适应 7.5 到 30fps，以及高达 1080p 分辨率的汇总模式/大型库视频<sup>\*</sup>。</span><span class="sxs-lookup"><span data-stu-id="cf61c-256">**Recommended** Bandwidth requirements for video calls are up to 1080p resolution<sup>\*</sup>, screen sharing content frame rates adaptive 7.5 to 30fps, and Together Mode/Large Gallery video up to 1080p resolution<sup>\*</sup>.</span></span>  

- <span data-ttu-id="cf61c-257">**最佳性能** 指南允许使用屏幕共享内容帧速率自适应 15 到 30fps，为较大的与会者会议、高损失环境和更高的运动内容提供更高的保真视频。</span><span class="sxs-lookup"><span data-stu-id="cf61c-257">**Best Performance** Guidance allows higher fidelity video for larger attendee meetings, high loss environments, and higher motion content with screen sharing content frame rates adaptive 15 to 30fps.</span></span>

<span data-ttu-id="cf61c-258"><sup>\*</sup>预期质量最高为 1080p，但根据网络条件，视频分辨率和质量将相应地进行优化。</span><span class="sxs-lookup"><span data-stu-id="cf61c-258"><sup>\*</sup>Expect up to 1080p quality but depending on your network conditions, video resolution and quality will be optimized accordingly.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="cf61c-259">相关主题</span><span class="sxs-lookup"><span data-stu-id="cf61c-259">Related Topics</span></span>

[<span data-ttu-id="cf61c-260">Microsoft 365 和 Office 365 网络连接原则</span><span class="sxs-lookup"><span data-stu-id="cf61c-260">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="cf61c-261">全球范围终结点：Skype for Business Online 和 Teams</span><span class="sxs-lookup"><span data-stu-id="cf61c-261">Worldwide endpoints: Skype for Business Online and Teams</span></span>](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="cf61c-262">Teams 的代理服务器</span><span class="sxs-lookup"><span data-stu-id="cf61c-262">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="cf61c-263">Teams 中的媒体：会议简单的原因</span><span class="sxs-lookup"><span data-stu-id="cf61c-263">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="cf61c-264">Teams 中的媒体：深入了解媒体流</span><span class="sxs-lookup"><span data-stu-id="cf61c-264">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="cf61c-265">Teams 中的标识模式和身份验证</span><span class="sxs-lookup"><span data-stu-id="cf61c-265">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="cf61c-266">如何部署 Teams</span><span class="sxs-lookup"><span data-stu-id="cf61c-266">How to roll out Teams</span></span>](./deploy-overview.md)

[<span data-ttu-id="cf61c-267">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="cf61c-267">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
