---
title: 规划直接路由
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: 阅读本主题, 了解 Microsoft Phone 系统直接路由如何让你将支持的客户提供的会话边界控制器 (SBC) 连接到 Microsoft Phone 系统。
ms.openlocfilehash: b675fae995d228d440c5173ec444dce16745717f
ms.sourcegitcommit: 6cbdcb8606044ad7ab49a4e3c828c2dc3d50fcc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2019
ms.locfileid: "36271420"
---
# <a name="plan-direct-routing"></a><span data-ttu-id="c5635-103">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="c5635-103">Plan Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="c5635-104">观看以下会话, 了解直接路由的好处、如何为其规划以及如何部署它: [Microsoft 团队中的直接路由](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="c5635-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="c5635-105">Microsoft 手机系统直接路由允许你将支持的客户提供的会话边界控制器 (SBC) 连接到 Microsoft Phone 系统。</span><span class="sxs-lookup"><span data-stu-id="c5635-105">Microsoft Phone System Direct Routing lets you connect a supported, customer-provided Session Border Controller (SBC) to Microsoft Phone System.</span></span>  <span data-ttu-id="c5635-106">例如, 利用此功能, 你可以配置与 Microsoft 团队客户端的本地 PSTN 连接, 如下图所示:</span><span class="sxs-lookup"><span data-stu-id="c5635-106">With this capability, for example, you can configure on-premises PSTN connectivity with Microsoft Teams client, as shown in the following diagram:</span></span> 

<span data-ttu-id="c5635-107">![显示本地 PSTN 连接配置的图表](media/PlanDirectRouting1-PSTNwithTeams.png "与 Microsoft 团队客户端的本地 PSTN 连接配置")</span><span class="sxs-lookup"><span data-stu-id="c5635-107">![Diagram showing configuration of on-premises PSTN connectivity](media/PlanDirectRouting1-PSTNwithTeams.png "Configuration of on-premises PSTN connectivity with Microsoft Teams client")</span></span>

  > [!NOTE]
  > <span data-ttu-id="c5635-108">Skype for Business Online 还允许你与客户提供的 SBC 配对, 但这需要一个本地 Skype for business 服务器部署或特殊版本的 Skype for business (称为云连接器), 它位于 SBC 和 Microsoft 云之间。</span><span class="sxs-lookup"><span data-stu-id="c5635-108">Skype for Business Online also lets you pair a customer-provided SBC, but this requires an on-premises Skype for Business Server deployment or a special edition of Skype for Business, called Cloud Connector, in between the SBC and the Microsoft Cloud.</span></span> <span data-ttu-id="c5635-109">此方案称为混合语音。</span><span class="sxs-lookup"><span data-stu-id="c5635-109">This scenario is known as hybrid voice.</span></span> <span data-ttu-id="c5635-110">相比之下, 直接路由允许受支持的 SBC 和 Microsoft 云之间的直接连接。</span><span class="sxs-lookup"><span data-stu-id="c5635-110">In contrast, Direct Routing allows a direct connection between the supported SBC and the Microsoft Cloud.</span></span> 

<span data-ttu-id="c5635-111">通过直接路由, 你可以将 SBC 连接到几乎任何电话中继或与第三方公共交换电话网络 (PSTN) 设备互连。</span><span class="sxs-lookup"><span data-stu-id="c5635-111">With Direct Routing, you can connect your SBC to almost any telephony trunk or interconnect with third-party Public Switched Telephone Network (PSTN) equipment.</span></span> <span data-ttu-id="c5635-112">直接路由使您能够:</span><span class="sxs-lookup"><span data-stu-id="c5635-112">Direct Routing enables you to:</span></span> 

- <span data-ttu-id="c5635-113">将几乎任何 PSTN 中继与 Microsoft Phone 系统配合使用。</span><span class="sxs-lookup"><span data-stu-id="c5635-113">Use virtually any PSTN trunk with Microsoft Phone System.</span></span> 
- <span data-ttu-id="c5635-114">配置客户拥有的电话设备 (如第三方专用分支机构 (PBX)、模拟设备和 Microsoft Phone 系统) 之间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="c5635-114">Configure interoperability between customer-owned telephony equipment, such as a third-party private branch exchange (PBX), analog devices, and Microsoft Phone System.</span></span>

<span data-ttu-id="c5635-115">Microsoft 还提供了所有云语音解决方案, 例如呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="c5635-115">Microsoft also offers all-in-the-cloud voice solutions, such as Calling Plan.</span></span>  <span data-ttu-id="c5635-116">但是, 混合语音解决方案可能最适合你的组织, 前提是:</span><span class="sxs-lookup"><span data-stu-id="c5635-116">However, a hybrid voice solution might be best for your organization if:</span></span> 

- <span data-ttu-id="c5635-117">Microsoft 通话计划在您所在的国家/地区不可用。</span><span class="sxs-lookup"><span data-stu-id="c5635-117">Microsoft Calling Plan is not available in your country.</span></span> 
- <span data-ttu-id="c5635-118">您的组织需要连接到第三方模拟设备、呼叫中心等。</span><span class="sxs-lookup"><span data-stu-id="c5635-118">Your organization requires connection to third-party analog devices, call centers, and so on.</span></span> 
- <span data-ttu-id="c5635-119">您的组织已有一个具有 PSTN 运营商的现有合同。</span><span class="sxs-lookup"><span data-stu-id="c5635-119">Your organization has an existing contract with a PSTN carrier.</span></span>

<span data-ttu-id="c5635-120">直接路由还支持拥有 Microsoft 通话计划附加许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="c5635-120">Direct Routing also supports users who have the additional license for the Microsoft Calling Plan.</span></span> <span data-ttu-id="c5635-121">有关详细信息, 请参阅[电话系统和通话计划](calling-plan-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="c5635-121">For more information, see [Phone System and Calling Plans](calling-plan-landing-page.md).</span></span> 

<span data-ttu-id="c5635-122">通过直接路由, 当用户参与计划的会议时, 拨入号码由 Microsoft 音频会议服务提供, 这需要正确的许可。</span><span class="sxs-lookup"><span data-stu-id="c5635-122">With Direct Routing, when users participate in a scheduled conference, the dial-in number is provided by Microsoft Audio Conferencing service, which requires proper licensing.</span></span>  <span data-ttu-id="c5635-123">当拨号时, Microsoft 音频会议服务使用在线呼叫功能来呼叫呼叫, 这需要正确的许可。</span><span class="sxs-lookup"><span data-stu-id="c5635-123">When dialing out, the Microsoft Audio Conferencing service places the call using online calling capabilities, which requires proper licensing.</span></span> <span data-ttu-id="c5635-124">(请注意, 拨号不通过直接路由路由。)有关详细信息, 请参阅[与团队联机会议](https://products.office.com/microsoft-teams/online-meeting-solutions)。</span><span class="sxs-lookup"><span data-stu-id="c5635-124">(Note that dialing out does not route through Direct Routing.) For more information, see [Online Meetings with Teams](https://products.office.com/microsoft-teams/online-meeting-solutions).</span></span> 
 
<span data-ttu-id="c5635-125">规划直接路由的部署是成功实施的关键。</span><span class="sxs-lookup"><span data-stu-id="c5635-125">Planning your deployment of Direct Routing is key to a successful implementation.</span></span> <span data-ttu-id="c5635-126">本文介绍基础结构和授权要求, 并提供有关 SBC 连接的信息:</span><span class="sxs-lookup"><span data-stu-id="c5635-126">This article describes infrastructure and licensing requirements and provides information about SBC connectivity:</span></span> 

- [<span data-ttu-id="c5635-127">基础结构要求</span><span class="sxs-lookup"><span data-stu-id="c5635-127">Infrastructure requirements</span></span>](#infrastructure-requirements)
- [<span data-ttu-id="c5635-128">许可和其他要求</span><span class="sxs-lookup"><span data-stu-id="c5635-128">Licensing and other requirements</span></span>](#licensing-and-other-requirements)
- [<span data-ttu-id="c5635-129">SBC 域名称</span><span class="sxs-lookup"><span data-stu-id="c5635-129">SBC domain names</span></span>](#sbc-domain-names)
- [<span data-ttu-id="c5635-130">适用于 SBC 的公共受信任证书</span><span class="sxs-lookup"><span data-stu-id="c5635-130">Public trusted certificate for the SBC</span></span>](#public-trusted-certificate-for-the-sbc)
- [<span data-ttu-id="c5635-131">SIP 信号: Fqdn</span><span class="sxs-lookup"><span data-stu-id="c5635-131">SIP Signaling: FQDNs</span></span>](#sip-signaling-fqdns)
- [<span data-ttu-id="c5635-132">SIP 信号: 端口</span><span class="sxs-lookup"><span data-stu-id="c5635-132">SIP Signaling: Ports</span></span>](#sip-signaling-ports)
- [<span data-ttu-id="c5635-133">媒体流量: 端口范围</span><span class="sxs-lookup"><span data-stu-id="c5635-133">Media traffic: Port ranges</span></span>](#media-traffic-port-ranges)
- [<span data-ttu-id="c5635-134">支持的会话边框控制器 (SBCs)</span><span class="sxs-lookup"><span data-stu-id="c5635-134">Supported Session Border Controllers (SBCs)</span></span>](#supported-session-border-controllers-sbcs)

<span data-ttu-id="c5635-135">有关配置直接路由的详细信息, 请参阅[配置直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="c5635-135">For detailed information about configuring Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="infrastructure-requirements"></a><span data-ttu-id="c5635-136">基础结构要求</span><span class="sxs-lookup"><span data-stu-id="c5635-136">Infrastructure requirements</span></span>
<span data-ttu-id="c5635-137">下表列出了用于部署直接路由的支持的 SBCs、域和其他网络连接要求的基础结构要求:</span><span class="sxs-lookup"><span data-stu-id="c5635-137">The infrastructure requirements for the supported SBCs, domains, and other network connectivity requirements to deploy Direct Routing are listed in the following table:</span></span>  

|<span data-ttu-id="c5635-138">**基础结构要求**</span><span class="sxs-lookup"><span data-stu-id="c5635-138">**Infrastructure requirement**</span></span>|<span data-ttu-id="c5635-139">**您需要以下**</span><span class="sxs-lookup"><span data-stu-id="c5635-139">**You need the following**</span></span>|
|:--- |:--- |
|<span data-ttu-id="c5635-140">会话边框控制器 (SBC)</span><span class="sxs-lookup"><span data-stu-id="c5635-140">Session Border Controller (SBC)</span></span>|<span data-ttu-id="c5635-141">受支持的 SBC。</span><span class="sxs-lookup"><span data-stu-id="c5635-141">A supported SBC.</span></span> <span data-ttu-id="c5635-142">有关详细信息, 请参阅[支持的 SBCs](#supported-session-border-controllers-sbcs)。</span><span class="sxs-lookup"><span data-stu-id="c5635-142">For more information, see [Supported SBCs](#supported-session-border-controllers-sbcs).</span></span>|
|<span data-ttu-id="c5635-143">连接到 SBC 的电话中继</span><span class="sxs-lookup"><span data-stu-id="c5635-143">Telephony trunks connected to the SBC</span></span>|<span data-ttu-id="c5635-144">一个或多个电话中继连接到 SBC。</span><span class="sxs-lookup"><span data-stu-id="c5635-144">One or more telephony trunks connected to the SBC.</span></span> <span data-ttu-id="c5635-145">一端, SBC 通过直接路由连接到 Microsoft 手机系统。</span><span class="sxs-lookup"><span data-stu-id="c5635-145">On one end, the SBC connects to the Microsoft Phone System via Direct Routing.</span></span> <span data-ttu-id="c5635-146">SBC 还可以连接到第三方电话实体, 如 Pbx、模拟电话适配器等。</span><span class="sxs-lookup"><span data-stu-id="c5635-146">The SBC can also connect to third-party telephony entities, such as PBXs, Analog Telephony Adapters, and so on.</span></span> <span data-ttu-id="c5635-147">任何连接到 SBC 的 PSTN 连接选项都将正常工作。</span><span class="sxs-lookup"><span data-stu-id="c5635-147">Any PSTN connectivity option connected to the SBC will work.</span></span> <span data-ttu-id="c5635-148">(注意: 有关将 PSTN 中继到 SBC 的配置, 请参阅 SBC 供应商或中继提供商。)</span><span class="sxs-lookup"><span data-stu-id="c5635-148">(Note: For configuration of the PSTN trunks to SBC, please refer to the SBC vendors or trunk providers.)</span></span>|
|<span data-ttu-id="c5635-149">Office 365 租户</span><span class="sxs-lookup"><span data-stu-id="c5635-149">Office 365 tenant</span></span>|<span data-ttu-id="c5635-150">用于家庭 Microsoft 团队用户的 Office 365 租户, 以及与 SBC 的配置和连接。</span><span class="sxs-lookup"><span data-stu-id="c5635-150">An Office 365 tenant that you use to home your Microsoft Teams users, and the configuration and connection to the SBC.</span></span>|
|<span data-ttu-id="c5635-151">用户注册机构</span><span class="sxs-lookup"><span data-stu-id="c5635-151">User registrar</span></span>|<span data-ttu-id="c5635-152">用户必须托管在 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="c5635-152">User must be homed in Office 365.</span></span><br/><span data-ttu-id="c5635-153">如果你的公司有一个本地 Skype for Business 或 Lync 环境以及与 Office 365 的混合连接, 则无法为驻留在本地的用户启用团队中的语音。</span><span class="sxs-lookup"><span data-stu-id="c5635-153">If your company has an on-premises Skype for Business or Lync environment with hybrid connectivity to Office 365, you cannot enable voice in Teams for a user homed on-premises.</span></span><br/><br/><span data-ttu-id="c5635-154">若要检查用户的注册机构, 请使用以下 Skype for Business Online PowerShell cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c5635-154">To check the registrar of a user, use the following Skype for Business Online PowerShell cmdlet:</span></span><br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/><span data-ttu-id="c5635-155">该 cmdlet 的输出应显示:</span><span class="sxs-lookup"><span data-stu-id="c5635-155">The output of the cmdlet should show:</span></span><br/><code>HostingProvider : sipfed.online.lync.com</code>|
|<span data-ttu-id="c5635-156">域</span><span class="sxs-lookup"><span data-stu-id="c5635-156">Domains</span></span>|<span data-ttu-id="c5635-157">添加到您的 Office 365 租户的一个或多个域。</span><span class="sxs-lookup"><span data-stu-id="c5635-157">One or more domains added to your Office 365 tenants.</span></span><br/><br/><span data-ttu-id="c5635-158">**注意:** 您不能使用为你的租户自动创建的默认域, \* onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="c5635-158">**Note:** You cannot use the default domain, \*.onmicrosoft.com, that is automatically created for your tenant.</span></span><br/><br/><span data-ttu-id="c5635-159">若要查看域, 您可以使用以下 Skype for Business Online PowerShell cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c5635-159">To view the domains, you can use the following Skype for Business Online PowerShell cmdlet:</span></span><br/><code>Get-CsTenant \| fl Domains</code><br/><br/><span data-ttu-id="c5635-160">有关域和 Office 365 租户的详细信息, 请参阅[域常见问题解答](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。</span><span class="sxs-lookup"><span data-stu-id="c5635-160">For more information about domains and Office 365 tenants, see [Domains FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).</span></span>|
|<span data-ttu-id="c5635-161">SBC 的公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="c5635-161">Public IP address for the SBC</span></span>|<span data-ttu-id="c5635-162">可用于连接到 SBC 的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c5635-162">A public IP address that can be used to connect to the SBC.</span></span> <span data-ttu-id="c5635-163">SBC 可以使用 NAT, 具体取决于 SBC 的类型。</span><span class="sxs-lookup"><span data-stu-id="c5635-163">Based on the type of SBC, the SBC can use NAT.</span></span>|
|<span data-ttu-id="c5635-164">适用于 SBC 的完全限定的域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="c5635-164">Fully Qualified Domain Name (FQDN) for the SBC</span></span>|<span data-ttu-id="c5635-165">SBC 的 FQDN, 其中 FQDN 的域部分是 Office 365 租户中注册的域之一。</span><span class="sxs-lookup"><span data-stu-id="c5635-165">A FQDN for the SBC, where the domain portion of the FQDN is one of the registered domains in your Office 365 tenant.</span></span> <span data-ttu-id="c5635-166">有关详细信息, 请参阅[SBC 域名](#sbc-domain-names)。</span><span class="sxs-lookup"><span data-stu-id="c5635-166">For more information, see [SBC domain names](#sbc-domain-names).</span></span>|
|<span data-ttu-id="c5635-167">SBC 的公共 DNS 条目</span><span class="sxs-lookup"><span data-stu-id="c5635-167">Public DNS entry for the SBC</span></span> |<span data-ttu-id="c5635-168">将 SBC FQDN 映射到公共 IP 地址的公共 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="c5635-168">A public DNS entry mapping the SBC FQDN to the public IP Address.</span></span> |
|<span data-ttu-id="c5635-169">适用于 SBC 的公共受信任证书</span><span class="sxs-lookup"><span data-stu-id="c5635-169">Public trusted certificate for the SBC</span></span> |<span data-ttu-id="c5635-170">用于 SBC 的证书, 用于与直接路由的所有通信。</span><span class="sxs-lookup"><span data-stu-id="c5635-170">A certificate for the SBC to be used for all communication with Direct Routing.</span></span> <span data-ttu-id="c5635-171">有关详细信息, 请参阅[SBC 的公共受信任证书](#public-trusted-certificate-for-the-sbc)。</span><span class="sxs-lookup"><span data-stu-id="c5635-171">For more information, see [Public trusted certificate for the SBC](#public-trusted-certificate-for-the-sbc).</span></span>|
|<span data-ttu-id="c5635-172">直接路由的连接点</span><span class="sxs-lookup"><span data-stu-id="c5635-172">Connection points for Direct Routing</span></span> |<span data-ttu-id="c5635-173">直接路由的连接点是以下三个 Fqdn:</span><span class="sxs-lookup"><span data-stu-id="c5635-173">The connection points for Direct Routing are the following three FQDNs:</span></span><br/><br/><span data-ttu-id="c5635-174">`sip.pstnhub.microsoft.com`-必须首先尝试全局 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c5635-174">`sip.pstnhub.microsoft.com` – Global FQDN, must be tried first.</span></span><br/><span data-ttu-id="c5635-175">`sip2.pstnhub.microsoft.com`-辅助 FQDN, 地理位置映射到第二个优先级区域。</span><span class="sxs-lookup"><span data-stu-id="c5635-175">`sip2.pstnhub.microsoft.com` – Secondary FQDN, geographically maps to the second priority region.</span></span><br/><span data-ttu-id="c5635-176">`sip3.pstnhub.microsoft.com`-第三方 FQDN-地理位置映射到第三个优先级区域。</span><span class="sxs-lookup"><span data-stu-id="c5635-176">`sip3.pstnhub.microsoft.com` – Tertiary FQDN, geographically maps to the third priority region.</span></span><br/><br/><span data-ttu-id="c5635-177">有关配置要求的信息, 请参阅[SIP 信号: fqdn](#sip-signaling-fqdns)。</span><span class="sxs-lookup"><span data-stu-id="c5635-177">For information on configuration requirements, see [SIP Signaling: FQDNs](#sip-signaling-fqdns).</span></span>|
|<span data-ttu-id="c5635-178">用于直接路由媒体的防火墙 IP 地址和端口</span><span class="sxs-lookup"><span data-stu-id="c5635-178">Firewall IP addresses and ports for Direct Routing media</span></span> |<span data-ttu-id="c5635-179">SBC 与云中的以下服务进行通信:</span><span class="sxs-lookup"><span data-stu-id="c5635-179">The SBC communicates to the following services in the cloud:</span></span><br/><br/><span data-ttu-id="c5635-180">负责处理信号的 SIP 代理</span><span class="sxs-lookup"><span data-stu-id="c5635-180">SIP Proxy, which handles the signaling</span></span><br/><span data-ttu-id="c5635-181">处理媒体的媒体处理器-当媒体绕过时除外</span><span class="sxs-lookup"><span data-stu-id="c5635-181">Media Processor, which handles media -except when Media Bypass is on</span></span><br/><br/><span data-ttu-id="c5635-182">这两个服务在 Microsoft 云中具有单独的 IP 地址, 如本文档后面部分所述。</span><span class="sxs-lookup"><span data-stu-id="c5635-182">These two services have separate IP addresses in Microsoft Cloud, described later in this document.</span></span><br/><br/><span data-ttu-id="c5635-183">有关详细信息, 请参阅[Office 365 url 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)中的 " [Microsoft 团队" 部分](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="c5635-183">For more information, see the [Microsoft Teams section](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) in [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> |
|<span data-ttu-id="c5635-184">媒体传输配置文件</span><span class="sxs-lookup"><span data-stu-id="c5635-184">Media Transport Profile</span></span>|<span data-ttu-id="c5635-185">TCP/RTP/SAVP</span><span class="sxs-lookup"><span data-stu-id="c5635-185">TCP/RTP/SAVP</span></span> <br/><span data-ttu-id="c5635-186">UDP/RTP/SAVP</span><span class="sxs-lookup"><span data-stu-id="c5635-186">UDP/RTP/SAVP</span></span>|
<span data-ttu-id="c5635-187">适用于 Microsoft 团队媒体的防火墙 IP 地址和端口</span><span class="sxs-lookup"><span data-stu-id="c5635-187">Firewall IP addresses and ports for Microsoft Teams media</span></span> |<span data-ttu-id="c5635-188">有关详细信息, 请参阅[Office 365 url 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="c5635-188">For more information, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> |
|||

## <a name="licensing-and-other-requirements"></a><span data-ttu-id="c5635-189">许可和其他要求</span><span class="sxs-lookup"><span data-stu-id="c5635-189">Licensing and other requirements</span></span> 

<span data-ttu-id="c5635-190">直接路由用户必须在 Office 365 中分配以下许可证:</span><span class="sxs-lookup"><span data-stu-id="c5635-190">Users of Direct Routing must have the following licenses assigned in Office 365:</span></span> 

- <span data-ttu-id="c5635-191">Microsoft Phone 系统</span><span class="sxs-lookup"><span data-stu-id="c5635-191">Microsoft Phone System</span></span> 
- <span data-ttu-id="c5635-192">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c5635-192">Microsoft Teams</span></span> 
- <span data-ttu-id="c5635-193">Microsoft 音频会议</span><span class="sxs-lookup"><span data-stu-id="c5635-193">Microsoft Audio Conferencing</span></span> 


> [!IMPORTANT]
>  <span data-ttu-id="c5635-194">如果你想要将外部参与者添加到计划会议, 请通过拨出或提供拨入号码来向其添加外部参与者,*需要*音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="c5635-194">In the case that you would like to add external participants to scheduled meetings, either by dialing out to them or by providing the dial-in number, the audio conferencing license is *required*.</span></span>

> [!NOTE]
> <span data-ttu-id="c5635-195">*需要*音频会议许可证才能执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="c5635-195">The audio conferencing license is *required* to:</span></span>
> - <span data-ttu-id="c5635-196">从1:1 调用升级到组呼叫。</span><span class="sxs-lookup"><span data-stu-id="c5635-196">Escalate from 1:1 call to a group call.</span></span>
> - <span data-ttu-id="c5635-197">将外部参与者添加到计划会议, 方法是拨出或提供拨入号码。</span><span class="sxs-lookup"><span data-stu-id="c5635-197">Add external participants to scheduled meetings, by either dialing out or providing the dial-in number.</span></span> 


<span data-ttu-id="c5635-198">此外, 必须确保以下内容:</span><span class="sxs-lookup"><span data-stu-id="c5635-198">In addition, you must ensure the following:</span></span>
 
- <span data-ttu-id="c5635-199">CsOnlineVoiceRoutingPolicy 已分配给用户。</span><span class="sxs-lookup"><span data-stu-id="c5635-199">CsOnlineVoiceRoutingPolicy is assigned to the user.</span></span> 
- <span data-ttu-id="c5635-200">允许在 Microsoft 团队的租户级别启用私人通话。</span><span class="sxs-lookup"><span data-stu-id="c5635-200">Allow Private Calling is enabled at the tenant level for Microsoft Teams.</span></span> 

<span data-ttu-id="c5635-201">直接路由还支持为 Microsoft 通话计划授权的用户。</span><span class="sxs-lookup"><span data-stu-id="c5635-201">Direct Routing also supports users who are licensed for Microsoft Calling Plan.</span></span> <span data-ttu-id="c5635-202">带有呼叫计划的 Microsoft Phone 系统可以使用直接路由界面路由某些呼叫。</span><span class="sxs-lookup"><span data-stu-id="c5635-202">Microsoft Phone System with Calling Plan can route some calls using the Direct Routing interface.</span></span> <span data-ttu-id="c5635-203">但是, 用户的电话号码必须是联机购买的或移植到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="c5635-203">However, the users' phone numbers must be either acquired online or ported to Microsoft.</span></span>  

<span data-ttu-id="c5635-204">为同一用户混合呼叫计划和直接路由连接是可选的, 但可能很有用, 例如, 当用户分配了 Microsoft 通话计划, 但想要通过 SBC 路由某些调用时。</span><span class="sxs-lookup"><span data-stu-id="c5635-204">Mixing Calling Plan and Direct Routing connectivity for the same user is optional, but could be useful, for example, when the user is assigned a Microsoft Calling Plan but wants to route some calls via SBC.</span></span> <span data-ttu-id="c5635-205">最常见的方案之一是调用第三方的 Pbx。</span><span class="sxs-lookup"><span data-stu-id="c5635-205">One of the most common scenarios are calls to third-party PBXs.</span></span>  <span data-ttu-id="c5635-206">使用第三方 Pbx, 除与连接到该 Pbx 的手机的通话外, 所有呼叫均通过 Microsoft 呼叫计划进行路由;但是, 拨打连接到第三方 Pbx 的电话将转到 SBC, 因此保持在企业网络内, 而不是在 PSTN 中。</span><span class="sxs-lookup"><span data-stu-id="c5635-206">With third-party PBXs, all calls, except calls to the phones connected to that PBXs, are routed via Microsoft Calling Plan; but calls to the phones connected to third-party PBXs go to the SBC, therefore stay within the enterprise network and not to the PSTN.</span></span> 

<span data-ttu-id="c5635-207">有关电话系统许可的详细信息, 请参阅[使用 office 365](https://products.office.com/compare-all-microsoft-office-products?tab=2)和[Office 365 计划选项](https://technet.microsoft.com/library/office-365-plan-options.aspx)充分利用 office。</span><span class="sxs-lookup"><span data-stu-id="c5635-207">For more information about Phone System licensing, see [Get the most from Office with Office 365](https://products.office.com/compare-all-microsoft-office-products?tab=2) and [Office 365 Plan Options](https://technet.microsoft.com/library/office-365-plan-options.aspx).</span></span> 

<span data-ttu-id="c5635-208">有关电话系统许可的详细信息, 请参阅[Microsoft 团队附加许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="c5635-208">For more information about Phone System licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span> 

## <a name="sbc-domain-names"></a><span data-ttu-id="c5635-209">SBC 域名称</span><span class="sxs-lookup"><span data-stu-id="c5635-209">SBC domain names</span></span>

<span data-ttu-id="c5635-210">SBC 域名必须来自租户的 "域" 中注册的一个名称。</span><span class="sxs-lookup"><span data-stu-id="c5635-210">The SBC domain name must be from one of the names registered in “Domains” of the tenant.</span></span> <span data-ttu-id="c5635-211">不能对 SBC 的 FQDN 名称使用 \* onmicrosoft.com 租户。</span><span class="sxs-lookup"><span data-stu-id="c5635-211">You cannot use the \*.onmicrosoft.com tenant for the FQDN name of the SBC.</span></span>

<span data-ttu-id="c5635-212">下表显示为租户注册的 DNS 名称的示例、该名称是否可以用作 SBC 的 FQDN 以及有效 FQDN 名称的示例:</span><span class="sxs-lookup"><span data-stu-id="c5635-212">The following table shows examples of DNS names registered for the tenant, whether the name can be used as a FQDN for the SBC, and examples of valid FQDN names:</span></span>

|<span data-ttu-id="c5635-213">**DNS 名称**</span><span class="sxs-lookup"><span data-stu-id="c5635-213">**DNS name**</span></span>|<span data-ttu-id="c5635-214">**可用于 SBC FQDN**</span><span class="sxs-lookup"><span data-stu-id="c5635-214">**Can be used for SBC FQDN**</span></span>|<span data-ttu-id="c5635-215">**FQDN 名称的示例**</span><span class="sxs-lookup"><span data-stu-id="c5635-215">**Examples of FQDN names**</span></span>|
|:--- |:--- |:--- |
<span data-ttu-id="c5635-216">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5635-216">contoso.com</span></span>|<span data-ttu-id="c5635-217">是</span><span class="sxs-lookup"><span data-stu-id="c5635-217">Yes</span></span>|<span data-ttu-id="c5635-218">**有效的名称:**</span><span class="sxs-lookup"><span data-stu-id="c5635-218">**Valid names:**</span></span><br/><span data-ttu-id="c5635-219">sbc1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5635-219">sbc1.contoso.com</span></span><br/><span data-ttu-id="c5635-220">ssbcs15.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5635-220">ssbcs15.contoso.com</span></span><br/><span data-ttu-id="c5635-221">europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5635-221">europe.contoso.com</span></span>|
|<span data-ttu-id="c5635-222">contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="c5635-222">contoso.onmicrosoft.com</span></span>|<span data-ttu-id="c5635-223">否</span><span class="sxs-lookup"><span data-stu-id="c5635-223">No</span></span>|<br/><span data-ttu-id="c5635-224">SBC 名称不支持使用 \* onmicrosoft.com 域</span><span class="sxs-lookup"><span data-stu-id="c5635-224">Using \*.onmicrosoft.com domains is not supported for SBC names</span></span>

<span data-ttu-id="c5635-225">假设您要使用新域名。</span><span class="sxs-lookup"><span data-stu-id="c5635-225">Assume you want to use a new domain name.</span></span> <span data-ttu-id="c5635-226">例如, 你的租户已将 contoso.com 用作你的租户中注册的域名, 并且你希望使用 sbc1.sip.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c5635-226">For example, your tenant has contoso.com as a domain name registered in your tenant, and you want to use sbc1.sip.contoso.com.</span></span> <span data-ttu-id="c5635-227">在你可以将 SBC 与 name sbc1.sip.contoso.com 配对之前, 必须在租户中的 "域" 中注册域名 sip.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c5635-227">Before you can pair an SBC with the name sbc1.sip.contoso.com, you must register the domain name sip.contoso.com in "Domains" in your tenant.</span></span> <span data-ttu-id="c5635-228">如果你在注册域名之前尝试将 SBC 与 sbc1.sip.contoso.com 配对, 你将收到以下错误: "无法使用" sbc1.sip.contoso.com "域, 因为它不是为此租户配置的。"</span><span class="sxs-lookup"><span data-stu-id="c5635-228">If you try pairing an SBC with sbc1.sip.contoso.com before registering the domain name, you will get the following error: "Cannot use the "sbc1.sip.contoso.com" domain as it was not configured for this tenant."</span></span>
<span data-ttu-id="c5635-229">添加域名后, 你还需要使用 UPN user@sip.contoso.com 创建用户并分配 "团队" 许可证。</span><span class="sxs-lookup"><span data-stu-id="c5635-229">After you add the domain name, you also need to create a user with UPN user@sip.contoso.com and assign a "Teams" license.</span></span> <span data-ttu-id="c5635-230">在将域名添加到租户的 "域" 之后, 可能需要长达24小时才能完全预配域名, 并将创建一个具有新名称的用户, 并为该用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="c5635-230">It might take up to 24 hours to fully provision the domain name after it is added to "Domains" of your tenant, a user with a new name is created, and a license is assigned to the user.</span></span> 

<span data-ttu-id="c5635-231">公司可能在一个租户中有多个 SIP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="c5635-231">It is possible that a company might have several SIP address spaces in one tenant.</span></span> <span data-ttu-id="c5635-232">例如, 公司可能已将 contoso.com 用作 SIP 地址空间, 而 fabrikam.com 作为第二个 SIP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="c5635-232">For example, a company might have contoso.com as a SIP address space and fabrikam.com as the second SIP address space.</span></span> <span data-ttu-id="c5635-233">某些用户具有地址 user@contoso.com, 而某些用户具有地址 user@fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="c5635-233">Some users have address user@contoso.com and some users have address user@fabrikam.com.</span></span> 

<span data-ttu-id="c5635-234">SBC 仅需要一个 FQDN, 并且可以通过配对的租户中的任何地址空间为用户服务。</span><span class="sxs-lookup"><span data-stu-id="c5635-234">The SBC only needs one FQDN and can service users from any address space in the paired tenant.</span></span> <span data-ttu-id="c5635-235">例如, 具有名称 sbc1.contoso.com 的 SBC 可以接收和发送具有地址 user@contoso.com 和 user@fabrikam.com 的用户的 PSTN 流量, 只要这些 SIP 地址空间在同一租户中注册。</span><span class="sxs-lookup"><span data-stu-id="c5635-235">For example,  an SBC with the name sbc1.contoso.com can receive and send the PSTN traffic for users with addresses user@contoso.com and user@fabrikam.com as long as these SIP address spaces are registered in the same tenant.</span></span>  

## <a name="public-trusted-certificate-for-the-sbc"></a><span data-ttu-id="c5635-236">适用于 SBC 的公共受信任证书</span><span class="sxs-lookup"><span data-stu-id="c5635-236">Public trusted certificate for the SBC</span></span>

<span data-ttu-id="c5635-237">Microsoft 强烈建议你通过生成证书签名请求 (CSR) 来请求 SBC 的证书。</span><span class="sxs-lookup"><span data-stu-id="c5635-237">Microsoft strongly recommends that you request the certificate for the SBC by generating a certification signing request (CSR).</span></span> <span data-ttu-id="c5635-238">有关为 SBC 生成 CSR 的特定说明, 请参阅由 SBC 供应商提供的互连说明或文档。</span><span class="sxs-lookup"><span data-stu-id="c5635-238">For specific instructions on generating a CSR for an SBC, refer to the interconnection instructions or documentation provided by your SBC vendors.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="c5635-239">大多数证书颁发机构 (Ca) 要求私钥大小至少为2048。</span><span class="sxs-lookup"><span data-stu-id="c5635-239">Most Certificate Authorities (CAs) require the private key size to be at least 2048.</span></span> <span data-ttu-id="c5635-240">在生成 CSR 时请记住这一点。</span><span class="sxs-lookup"><span data-stu-id="c5635-240">Keep this in mind when generating the CSR.</span></span>

<span data-ttu-id="c5635-241">证书需要在 "主题"、"公用名" 或 "使用者备用名称" 字段中具有 SBC FQDN。</span><span class="sxs-lookup"><span data-stu-id="c5635-241">The certificate needs to have the SBC FQDN in the subject, common name, or subject alternate name fields.</span></span>

<span data-ttu-id="c5635-242">或者, 直接路由支持 SAN 中的通配符, 并且通配符需要符合 TLS 上的标准[RFC HTTP](https://tools.ietf.org/html/rfc2818#section-3.1)。</span><span class="sxs-lookup"><span data-stu-id="c5635-242">Alternatively, Direct Routing  supports a wildcard in SAN, and the wildcard needs to conform to standard [RFC HTTP Over TLS](https://tools.ietf.org/html/rfc2818#section-3.1).</span></span> <span data-ttu-id="c5635-243">SAN 中将使用 \* contoso.com, 这将与 SBC FQDN sbc.contoso.com 相匹配, 但与 sbc.test.contoso.com 不匹配。</span><span class="sxs-lookup"><span data-stu-id="c5635-243">An example would be using \*.contoso.com in the SAN, which would match the SBC FQDN sbc.contoso.com, but wouldn’t match with sbc.test.contoso.com.</span></span>

<span data-ttu-id="c5635-244">证书需要由以下根证书颁发机构之一生成:</span><span class="sxs-lookup"><span data-stu-id="c5635-244">The certificate needs to be generated by one of the following root certificate authorities:</span></span>

- <span data-ttu-id="c5635-245">AffirmTrust</span><span class="sxs-lookup"><span data-stu-id="c5635-245">AffirmTrust</span></span>
- <span data-ttu-id="c5635-246">AddTrust 外部 CA 根</span><span class="sxs-lookup"><span data-stu-id="c5635-246">AddTrust External CA Root</span></span>
- <span data-ttu-id="c5635-247">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="c5635-247">Baltimore CyberTrust Root</span></span>
- <span data-ttu-id="c5635-248">Buypass</span><span class="sxs-lookup"><span data-stu-id="c5635-248">Buypass</span></span>
- <span data-ttu-id="c5635-249">Cybertrust</span><span class="sxs-lookup"><span data-stu-id="c5635-249">Cybertrust</span></span>
- <span data-ttu-id="c5635-250">第3类公共主证书颁发机构</span><span class="sxs-lookup"><span data-stu-id="c5635-250">Class 3 Public Primary Certification Authority</span></span>
- <span data-ttu-id="c5635-251">Comodo 安全根 CA</span><span class="sxs-lookup"><span data-stu-id="c5635-251">Comodo Secure Root CA</span></span>
- <span data-ttu-id="c5635-252">德国 Telekom</span><span class="sxs-lookup"><span data-stu-id="c5635-252">Deutsche Telekom</span></span> 
- <span data-ttu-id="c5635-253">DigiCert 全局根 CA</span><span class="sxs-lookup"><span data-stu-id="c5635-253">DigiCert Global Root CA</span></span>
- <span data-ttu-id="c5635-254">DigiCert 高确定性 EV 根 CA</span><span class="sxs-lookup"><span data-stu-id="c5635-254">DigiCert High Assurance EV Root CA</span></span>
- <span data-ttu-id="c5635-255">Entrust</span><span class="sxs-lookup"><span data-stu-id="c5635-255">Entrust</span></span>
- <span data-ttu-id="c5635-256">GlobalSign</span><span class="sxs-lookup"><span data-stu-id="c5635-256">GlobalSign</span></span>
- <span data-ttu-id="c5635-257">转到 Daddy</span><span class="sxs-lookup"><span data-stu-id="c5635-257">Go Daddy</span></span>
- <span data-ttu-id="c5635-258">GeoTrust</span><span class="sxs-lookup"><span data-stu-id="c5635-258">GeoTrust</span></span>
- <span data-ttu-id="c5635-259">Verisign, Inc。</span><span class="sxs-lookup"><span data-stu-id="c5635-259">Verisign, Inc.</span></span> 
- <span data-ttu-id="c5635-260">Starfield</span><span class="sxs-lookup"><span data-stu-id="c5635-260">Starfield</span></span> 
- <span data-ttu-id="c5635-261">适用于 Microsoft 的 Symantec 企业版移动根</span><span class="sxs-lookup"><span data-stu-id="c5635-261">Symantec Enterprise Mobile Root for Microsoft</span></span> 
- <span data-ttu-id="c5635-262">SwissSign</span><span class="sxs-lookup"><span data-stu-id="c5635-262">SwissSign</span></span>
- <span data-ttu-id="c5635-263">Thawte 时间戳 CA</span><span class="sxs-lookup"><span data-stu-id="c5635-263">Thawte Timestamping CA</span></span>
- <span data-ttu-id="c5635-264">Trustwave</span><span class="sxs-lookup"><span data-stu-id="c5635-264">Trustwave</span></span>
- <span data-ttu-id="c5635-265">TeliaSonera</span><span class="sxs-lookup"><span data-stu-id="c5635-265">TeliaSonera</span></span> 
- <span data-ttu-id="c5635-266">T 位系统国际 GmbH (德国 Telekom)</span><span class="sxs-lookup"><span data-stu-id="c5635-266">T-Systems International GmbH (Deutsche Telekom)</span></span>
- <span data-ttu-id="c5635-267">QuoVadis</span><span class="sxs-lookup"><span data-stu-id="c5635-267">QuoVadis</span></span>

<span data-ttu-id="c5635-268">Microsoft 正在努力根据客户请求添加其他认证机构。</span><span class="sxs-lookup"><span data-stu-id="c5635-268">Microsoft is working on adding additional certification authorities based on customer requests.</span></span> 

## <a name="sip-signaling-fqdns"></a><span data-ttu-id="c5635-269">SIP 信号: Fqdn</span><span class="sxs-lookup"><span data-stu-id="c5635-269">SIP Signaling: FQDNs</span></span> 

<span data-ttu-id="c5635-270">直接路由在以下 Office 365 环境中提供:</span><span class="sxs-lookup"><span data-stu-id="c5635-270">Direct Routing is offered in the following Office 365 environments:</span></span>
- <span data-ttu-id="c5635-271">Office 365</span><span class="sxs-lookup"><span data-stu-id="c5635-271">Office 365</span></span>
- <span data-ttu-id="c5635-272">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="c5635-272">Office 365 GCC</span></span>
- <span data-ttu-id="c5635-273">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="c5635-273">Office 365 GCC High</span></span>
- <span data-ttu-id="c5635-274">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="c5635-274">Office 365 DoD</span></span>

<span data-ttu-id="c5635-275">了解有关[Office 365 和美国政府环境](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)(如 GCC、gcc 高级版和 DoD) 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c5635-275">Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="c5635-276">Office 365 和 Office 365 GCC 环境</span><span class="sxs-lookup"><span data-stu-id="c5635-276">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="c5635-277">直接路由的连接点是以下三个 Fqdn:</span><span class="sxs-lookup"><span data-stu-id="c5635-277">The connection point for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="c5635-278">**sip.pstnhub.microsoft.com** -必须首先尝试全局 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c5635-278">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="c5635-279">当 SBC 发送一个请求来解析此名称时, Microsoft Azure DNS 服务器将返回指向分配给 SBC 的主 Azure 数据中心的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c5635-279">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="c5635-280">该作业基于数据中心的性能指标和与 SBC 的地理位置的接近度。</span><span class="sxs-lookup"><span data-stu-id="c5635-280">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="c5635-281">返回的 IP 地址对应于主 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c5635-281">The IP address returned corresponds to the primary FQDN.</span></span>
- <span data-ttu-id="c5635-282">**sip2.pstnhub.microsoft.com** -辅助 FQDN-地理位置映射到第二个优先级区域。</span><span class="sxs-lookup"><span data-stu-id="c5635-282">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>
- <span data-ttu-id="c5635-283">**sip3.pstnhub.microsoft.com** -第三方 FQDN-地理位置映射到第三个优先级区域。</span><span class="sxs-lookup"><span data-stu-id="c5635-283">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="c5635-284">按顺序放置这三个 Fqdn 需要:</span><span class="sxs-lookup"><span data-stu-id="c5635-284">Placing these three FQDNs in order is required to:</span></span>

- <span data-ttu-id="c5635-285">提供最佳体验 (加载时间最少且最接近通过查询第一个 FQDN 分配的 SBC 数据中心)。</span><span class="sxs-lookup"><span data-stu-id="c5635-285">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>
- <span data-ttu-id="c5635-286">当从 SBC 建立连接到遇到暂时性问题的数据中心时, 请提供故障转移。</span><span class="sxs-lookup"><span data-stu-id="c5635-286">Provide failover when connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="c5635-287">有关详细信息, 请参阅下面的[故障转移机制](#failover-mechanism-for-sip-signaling)。</span><span class="sxs-lookup"><span data-stu-id="c5635-287">For more information, see [Failover mechanism](#failover-mechanism-for-sip-signaling) below.</span></span>  

<span data-ttu-id="c5635-288">Fqdn (sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com 和 sip3.pstnhub.microsoft.com) 将解析为以下 IP 地址之一:</span><span class="sxs-lookup"><span data-stu-id="c5635-288">The FQDNs – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com and sip3.pstnhub.microsoft.com – will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="c5635-289">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="c5635-289">52.114.148.0</span></span>
- <span data-ttu-id="c5635-290">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="c5635-290">52.114.132.46</span></span> 
- <span data-ttu-id="c5635-291">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="c5635-291">52.114.75.24</span></span> 
- <span data-ttu-id="c5635-292">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="c5635-292">52.114.76.76</span></span> 
- <span data-ttu-id="c5635-293">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="c5635-293">52.114.7.24</span></span> 
- <span data-ttu-id="c5635-294">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="c5635-294">52.114.14.70</span></span>

<span data-ttu-id="c5635-295">您需要在防火墙中打开所有这些 IP 地址的端口, 以允许传入和传出通信发送和接收来自地址的发送信号。</span><span class="sxs-lookup"><span data-stu-id="c5635-295">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="c5635-296">如果你的防火墙支持 DNS 名称, FQDN sip-all.pstnhub.microsoft.com 将解析为所有这些 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c5635-296">If your firewall supports DNS names, the FQDN sip-all.pstnhub.microsoft.com resolves to all these IP addresses.</span></span> 


### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="c5635-297">Office 365 GCC DoD 环境</span><span class="sxs-lookup"><span data-stu-id="c5635-297">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="c5635-298">直接路由的连接点是以下 FQDN:</span><span class="sxs-lookup"><span data-stu-id="c5635-298">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="c5635-299">**sip.pstnhub.dod.teams.microsoft.us** -全局 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c5635-299">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="c5635-300">由于 Office 365 DoD 环境仅存在于美国数据中心, 因此没有第二个和第三个 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="c5635-300">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="c5635-301">Fqdn-sip.pstnhub.dod.teams.microsoft.us 将解析为以下 IP 地址之一:</span><span class="sxs-lookup"><span data-stu-id="c5635-301">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="c5635-302">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="c5635-302">52.127.64.33</span></span>
- <span data-ttu-id="c5635-303">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="c5635-303">52.127.68.34</span></span>

<span data-ttu-id="c5635-304">您需要在防火墙中打开所有这些 IP 地址的端口, 以允许传入和传出通信发送和接收来自地址的发送信号。</span><span class="sxs-lookup"><span data-stu-id="c5635-304">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="c5635-305">如果你的防火墙支持 DNS 名称, FQDN sip.pstnhub.dod.teams.microsoft.us 将解析为所有这些 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c5635-305">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="c5635-306">Office 365 GCC 高环境</span><span class="sxs-lookup"><span data-stu-id="c5635-306">Office 365 GCC High environment</span></span>

<span data-ttu-id="c5635-307">直接路由的连接点是以下 FQDN:</span><span class="sxs-lookup"><span data-stu-id="c5635-307">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="c5635-308">**sip.pstnhub.gov.teams.microsoft.us** -全局 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c5635-308">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="c5635-309">由于 GCC 的高环境仅存在于美国数据中心, 因此没有第二个和第三个 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="c5635-309">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="c5635-310">Fqdn-sip.pstnhub.gov.teams.microsoft.us 将解析为以下 IP 地址之一:</span><span class="sxs-lookup"><span data-stu-id="c5635-310">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="c5635-311">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="c5635-311">52.127.88.59</span></span>
- <span data-ttu-id="c5635-312">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="c5635-312">52.127.92.64</span></span>

<span data-ttu-id="c5635-313">您需要在防火墙中打开所有这些 IP 地址的端口, 以允许传入和传出通信发送和接收来自地址的发送信号。</span><span class="sxs-lookup"><span data-stu-id="c5635-313">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="c5635-314">如果你的防火墙支持 DNS 名称, FQDN sip.pstnhub.gov.teams.microsoft.us 将解析为所有这些 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c5635-314">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="c5635-315">SIP 信号: 端口</span><span class="sxs-lookup"><span data-stu-id="c5635-315">SIP Signaling: Ports</span></span>

<span data-ttu-id="c5635-316">对于提供直接路由的所有 Office 365 环境, 端口要求是相同的:</span><span class="sxs-lookup"><span data-stu-id="c5635-316">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="c5635-317">Office 365</span><span class="sxs-lookup"><span data-stu-id="c5635-317">Office 365</span></span>
- <span data-ttu-id="c5635-318">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="c5635-318">Office 365 GCC</span></span>
- <span data-ttu-id="c5635-319">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="c5635-319">Office 365 GCC High</span></span>
- <span data-ttu-id="c5635-320">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="c5635-320">Office 365 DoD</span></span>

<span data-ttu-id="c5635-321">您必须使用以下端口:</span><span class="sxs-lookup"><span data-stu-id="c5635-321">You must use the following ports:</span></span>

|<span data-ttu-id="c5635-322">**流量**</span><span class="sxs-lookup"><span data-stu-id="c5635-322">**Traffic**</span></span>|<span data-ttu-id="c5635-323">**从**</span><span class="sxs-lookup"><span data-stu-id="c5635-323">**From**</span></span>|<span data-ttu-id="c5635-324">**到**</span><span class="sxs-lookup"><span data-stu-id="c5635-324">**To**</span></span>|<span data-ttu-id="c5635-325">**源端口**</span><span class="sxs-lookup"><span data-stu-id="c5635-325">**Source port**</span></span>|<span data-ttu-id="c5635-326">**目标端口**</span><span class="sxs-lookup"><span data-stu-id="c5635-326">**Destination port**</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="c5635-327">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="c5635-327">SIP/TLS</span></span>|<span data-ttu-id="c5635-328">SIP 代理</span><span class="sxs-lookup"><span data-stu-id="c5635-328">SIP Proxy</span></span>|<span data-ttu-id="c5635-329">SBC</span><span class="sxs-lookup"><span data-stu-id="c5635-329">SBC</span></span>|<span data-ttu-id="c5635-330">1024-65535</span><span class="sxs-lookup"><span data-stu-id="c5635-330">1024 – 65535</span></span>|<span data-ttu-id="c5635-331">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="c5635-331">Defined on the SBC</span></span>|
<span data-ttu-id="c5635-332">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="c5635-332">SIP/TLS</span></span>|<span data-ttu-id="c5635-333">SBC</span><span class="sxs-lookup"><span data-stu-id="c5635-333">SBC</span></span>|<span data-ttu-id="c5635-334">SIP 代理</span><span class="sxs-lookup"><span data-stu-id="c5635-334">SIP Proxy</span></span>|<span data-ttu-id="c5635-335">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="c5635-335">Defined on the SBC</span></span>|<span data-ttu-id="c5635-336">5061</span><span class="sxs-lookup"><span data-stu-id="c5635-336">5061</span></span>|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a><span data-ttu-id="c5635-337">SIP 信号的故障转移机制</span><span class="sxs-lookup"><span data-stu-id="c5635-337">Failover mechanism for SIP Signaling</span></span>

<span data-ttu-id="c5635-338">SBC 进行 DNS 查询来解析 sip.pstnhub.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="c5635-338">The SBC makes a DNS query to resolve sip.pstnhub.microsoft.com.</span></span> <span data-ttu-id="c5635-339">根据 SBC 位置和数据中心性能指标, 选择主数据中心。</span><span class="sxs-lookup"><span data-stu-id="c5635-339">Based on the SBC location and the datacenter performance metrics, the primary datacenter is selected.</span></span> <span data-ttu-id="c5635-340">如果主数据中心遇到问题, 则 SBC 将尝试可解析为第二个分配的数据中心的 sip2.pstnhub.microsoft.com, 并且在这种情况下, 在两个区域中的数据中心不可用时, SBC 将重试最后一个 FQDN (sip3.pstnhub.microsoft.com), 它提供第三数据中心 IP。</span><span class="sxs-lookup"><span data-stu-id="c5635-340">If the primary datacenter experiences an issue, the SBC will try the sip2.pstnhub.microsoft.com, which resolves to the second assigned datacenter, and, in the rare case that datacenters in two regions are not available, the SBC retries the last FQDN (sip3.pstnhub.microsoft.com), which provides the tertiary datacenter IP.</span></span>

<span data-ttu-id="c5635-341">下表总结了主数据中心、辅助数据中心和第三数据中心之间的关系:</span><span class="sxs-lookup"><span data-stu-id="c5635-341">The table below summarizes the relationships between primary, secondary, and tertiary datacenters:</span></span>

|<span data-ttu-id="c5635-342">**如果主数据中心是**</span><span class="sxs-lookup"><span data-stu-id="c5635-342">**If the primary datacenter is**</span></span>|<span data-ttu-id="c5635-343">**EMEA**</span><span class="sxs-lookup"><span data-stu-id="c5635-343">**EMEA**</span></span>|<span data-ttu-id="c5635-344">**NOAM**</span><span class="sxs-lookup"><span data-stu-id="c5635-344">**NOAM**</span></span>|<span data-ttu-id="c5635-345">**地区**</span><span class="sxs-lookup"><span data-stu-id="c5635-345">**ASIA**</span></span>|
|:--- |:--- |:--- |:--- |
|<span data-ttu-id="c5635-346">辅助数据中心 (sip2.pstnhub.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="c5635-346">The secondary datacenter (sip2.pstnhub.microsoft.com)</span></span>|<span data-ttu-id="c5635-347">我们</span><span class="sxs-lookup"><span data-stu-id="c5635-347">US</span></span>|<span data-ttu-id="c5635-348">各</span><span class="sxs-lookup"><span data-stu-id="c5635-348">EU</span></span>|<span data-ttu-id="c5635-349">我们</span><span class="sxs-lookup"><span data-stu-id="c5635-349">US</span></span>|
|<span data-ttu-id="c5635-350">第三数据中心 (sip3.pstnhub.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="c5635-350">The tertiary datacenter (sip3.pstnhub.microsoft.com)</span></span>|<span data-ttu-id="c5635-351">地区</span><span class="sxs-lookup"><span data-stu-id="c5635-351">ASIA</span></span>|<span data-ttu-id="c5635-352">地区</span><span class="sxs-lookup"><span data-stu-id="c5635-352">ASIA</span></span>|<span data-ttu-id="c5635-353">各</span><span class="sxs-lookup"><span data-stu-id="c5635-353">EU</span></span>|
|||||

## <a name="media-traffic-port-ranges"></a><span data-ttu-id="c5635-354">媒体流量: 端口范围</span><span class="sxs-lookup"><span data-stu-id="c5635-354">Media traffic: Port ranges</span></span>
<span data-ttu-id="c5635-355">请注意, 如果你想要在不使用媒体绕过的情况下部署直接路由, 请应用以下要求。</span><span class="sxs-lookup"><span data-stu-id="c5635-355">Note that the requirements below apply if you want to deploy Direct Routing without Media Bypass.</span></span> <span data-ttu-id="c5635-356">有关媒体绕过的防火墙要求, 请参阅[使用直接路由规划媒体旁路](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-plan-media-bypass)。</span><span class="sxs-lookup"><span data-stu-id="c5635-356">For firewall requirements for Media Bypass, please refer to [Plan for media bypass with Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-plan-media-bypass).</span></span>



<span data-ttu-id="c5635-357">媒体流量从 Microsoft 云中单独的服务流出。</span><span class="sxs-lookup"><span data-stu-id="c5635-357">The media traffic flows to and from a separate service in the Microsoft Cloud.</span></span> <span data-ttu-id="c5635-358">媒体流量的 IP 范围:</span><span class="sxs-lookup"><span data-stu-id="c5635-358">The IP range for Media traffic:</span></span>

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="c5635-359">Office 365 和 Office 365 GCC 环境</span><span class="sxs-lookup"><span data-stu-id="c5635-359">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="c5635-360">52.112.0.0/14 (从52.112.0.1 到52.115.255.254 的 IP 地址)。</span><span class="sxs-lookup"><span data-stu-id="c5635-360">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="c5635-361">Office 365 GCC DoD 环境</span><span class="sxs-lookup"><span data-stu-id="c5635-361">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="c5635-362">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="c5635-362">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="c5635-363">Office 365 GCC 高环境</span><span class="sxs-lookup"><span data-stu-id="c5635-363">Office 365 GCC High environment</span></span>

- <span data-ttu-id="c5635-364">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="c5635-364">52.127.88.0/21</span></span>

### <a name="port-range-applicable-to-all-environments"></a><span data-ttu-id="c5635-365">端口范围 (适用于所有环境)</span><span class="sxs-lookup"><span data-stu-id="c5635-365">Port range (applicable to all environments)</span></span>
<span data-ttu-id="c5635-366">下表显示了媒体处理器的端口范围:</span><span class="sxs-lookup"><span data-stu-id="c5635-366">The port range of the Media Processors is shown in the following table:</span></span> 

|<span data-ttu-id="c5635-367">**流量**</span><span class="sxs-lookup"><span data-stu-id="c5635-367">**Traffic**</span></span>|<span data-ttu-id="c5635-368">**从**</span><span class="sxs-lookup"><span data-stu-id="c5635-368">**From**</span></span>|<span data-ttu-id="c5635-369">**到**</span><span class="sxs-lookup"><span data-stu-id="c5635-369">**To**</span></span>|<span data-ttu-id="c5635-370">**源端口**</span><span class="sxs-lookup"><span data-stu-id="c5635-370">**Source port**</span></span>|<span data-ttu-id="c5635-371">**目标端口**</span><span class="sxs-lookup"><span data-stu-id="c5635-371">**Destination port**</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="c5635-372">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="c5635-372">UDP/SRTP</span></span>|<span data-ttu-id="c5635-373">媒体处理器</span><span class="sxs-lookup"><span data-stu-id="c5635-373">Media Processor</span></span>|<span data-ttu-id="c5635-374">SBC</span><span class="sxs-lookup"><span data-stu-id="c5635-374">SBC</span></span>|<span data-ttu-id="c5635-375">49 152-53 247</span><span class="sxs-lookup"><span data-stu-id="c5635-375">49 152 – 53 247</span></span>|<span data-ttu-id="c5635-376">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="c5635-376">Defined on the SBC</span></span>|
|<span data-ttu-id="c5635-377">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="c5635-377">UDP/SRTP</span></span>|<span data-ttu-id="c5635-378">SBC</span><span class="sxs-lookup"><span data-stu-id="c5635-378">SBC</span></span>|<span data-ttu-id="c5635-379">媒体处理器</span><span class="sxs-lookup"><span data-stu-id="c5635-379">Media Processor</span></span>|<span data-ttu-id="c5635-380">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="c5635-380">Defined on the SBC</span></span>|<span data-ttu-id="c5635-381">49 152-53 247</span><span class="sxs-lookup"><span data-stu-id="c5635-381">49 152 – 53 247</span></span>|
|

  > [!NOTE]
  > <span data-ttu-id="c5635-382">Microsoft 建议在 SBC 上对每个并发调用至少有两个端口。</span><span class="sxs-lookup"><span data-stu-id="c5635-382">Microsoft  recommends at least two ports per concurrent call on the SBC.</span></span>

## <a name="media-traffic-codecs"></a><span data-ttu-id="c5635-383">媒体流量: 编解码器</span><span class="sxs-lookup"><span data-stu-id="c5635-383">Media traffic: Codecs</span></span>

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a><span data-ttu-id="c5635-384">SBC 和云媒体处理器或 Microsoft 团队客户端之间的腿。</span><span class="sxs-lookup"><span data-stu-id="c5635-384">Leg between SBC and Cloud Media Processor or Microsoft Teams client.</span></span>
<span data-ttu-id="c5635-385">适用于媒体旁路情况和非绕过情况</span><span class="sxs-lookup"><span data-stu-id="c5635-385">Applies to both media bypass case and non-bypass cases</span></span>

<span data-ttu-id="c5635-386">会话边界控制器和云媒体处理器 (没有媒体旁路) 或团队客户端与 SBC 之间 (如果启用了媒体旁路) 之间的直接路由接口, 可以使用以下编解码器:</span><span class="sxs-lookup"><span data-stu-id="c5635-386">The Direct Routing interface on the leg between the Session Border Controller and Cloud Media Processor (without media bypass) or between the Teams client and the SBC (if Media Bypass enabled) can use the following codecs:</span></span>
- <span data-ttu-id="c5635-387">非媒体旁路 (SBC 到云媒体处理器): 绞丝、711、722、G 729</span><span class="sxs-lookup"><span data-stu-id="c5635-387">Non-Media bypass (SBC to Cloud Media Processor): SILK, G.711, G.722, G.729</span></span>
- <span data-ttu-id="c5635-388">媒体绕过 (SBC 到团队客户端): 绞丝、711、722、729、OPUS</span><span class="sxs-lookup"><span data-stu-id="c5635-388">Media Bypass (SBC to Teams client):  SILK, G.711, G.722, G.729, OPUS</span></span>

<span data-ttu-id="c5635-389">你可以通过从优惠中排除不需要的编解码器来强制使用会话边界控制器上的特定编解码器。</span><span class="sxs-lookup"><span data-stu-id="c5635-389">You can force use of the specific codec on the Session Border Controller by excluding undesirable codecs from the offer.</span></span>

### <a name="leg-between-microsoft-teams-client--and-cloud-media-processor"></a><span data-ttu-id="c5635-390">Microsoft 团队客户端与云媒体处理器之间的腿</span><span class="sxs-lookup"><span data-stu-id="c5635-390">Leg between Microsoft Teams Client  and Cloud Media Processor</span></span>
<span data-ttu-id="c5635-391">仅适用于非媒体旁路大小写。</span><span class="sxs-lookup"><span data-stu-id="c5635-391">Applies to non-media bypass case only.</span></span> <span data-ttu-id="c5635-392">在团队客户端和 SBC 之间直接使用媒体绕过媒体流</span><span class="sxs-lookup"><span data-stu-id="c5635-392">With Media Bypass media flows directly between Teams client and SBC</span></span>

<span data-ttu-id="c5635-393">在云媒体处理器和 Microsoft 团队客户端之间的腿处使用的是绞丝或722。</span><span class="sxs-lookup"><span data-stu-id="c5635-393">On the leg between the Cloud Media Processor and Microsoft Teams client either SILK or G.722 used.</span></span> <span data-ttu-id="c5635-394">此腿上基于 Microsoft 算法的编解码器选择, 这考虑了多个参数。</span><span class="sxs-lookup"><span data-stu-id="c5635-394">The codec choice on this leg  based on Microsoft algorithms, which take into consideration multiple parameters.</span></span> 


## <a name="supported-session-border-controllers-sbcs"></a><span data-ttu-id="c5635-395">支持的会话边框控制器 (SBCs)</span><span class="sxs-lookup"><span data-stu-id="c5635-395">Supported Session Border Controllers (SBCs)</span></span>

<span data-ttu-id="c5635-396">Microsoft 仅支持经认证的 SBCs 与直接路由配对。</span><span class="sxs-lookup"><span data-stu-id="c5635-396">Microsoft only supports certified SBCs to pair with Direct Routing.</span></span> <span data-ttu-id="c5635-397">由于企业语音对企业至关重要, Microsoft 使用所选 SBCs 运行大量测试, 并与 SBC 供应商一起使用, 确保两个系统兼容。</span><span class="sxs-lookup"><span data-stu-id="c5635-397">Because Enterprise Voice is critical for businesses, Microsoft runs intensive tests with the selected SBCs, and works with the SBC vendors to ensure the two systems are compatible.</span></span> 

<span data-ttu-id="c5635-398">已验证的设备列为团队直接路由的认证。</span><span class="sxs-lookup"><span data-stu-id="c5635-398">Devices that have been validated are listed as Certified for Teams Direct Routing.</span></span> <span data-ttu-id="c5635-399">认证的设备保证能够在所有情况下正常工作。</span><span class="sxs-lookup"><span data-stu-id="c5635-399">The certified devices are guaranteed to work in all scenarios.</span></span> 

<span data-ttu-id="c5635-400">有关支持的 SBCs 的详细信息, 请参阅[为直接路由认证的会话边框控制器列表](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="c5635-400">For more information about supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

 
## <a name="see-also"></a><span data-ttu-id="c5635-401">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5635-401">See also</span></span>

[<span data-ttu-id="c5635-402">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="c5635-402">Configure Direct Routing</span></span>](direct-routing-configure.md)



