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
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 阅读本主题，了解 Microsoft Phone 系统直接路由如何让你将支持的客户提供的会话边界控制器（SBC）连接到 Microsoft Phone 系统。
ms.openlocfilehash: be0d901095afa322935944a9b4898e540946bf8a
ms.sourcegitcommit: 46b15a11755a89526be2a0b20befad61c628cdb4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955721"
---
# <a name="plan-direct-routing"></a><span data-ttu-id="3d866-103">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="3d866-103">Plan Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="3d866-104">观看以下会话，了解直接路由的好处、如何为其规划以及如何部署它： [Microsoft 团队中的直接路由](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="3d866-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="3d866-105">Microsoft 手机系统直接路由允许你将支持的客户提供的会话边界控制器（SBC）连接到 Microsoft Phone 系统。</span><span class="sxs-lookup"><span data-stu-id="3d866-105">Microsoft Phone System Direct Routing lets you connect a supported, customer-provided Session Border Controller (SBC) to Microsoft Phone System.</span></span>  <span data-ttu-id="3d866-106">例如，利用此功能，你可以配置与 Microsoft 团队客户端的本地公共交换电话网络（PSTN）连接，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="3d866-106">With this capability, for example, you can configure on-premises Public Switched Telephone Network (PSTN) connectivity with Microsoft Teams client, as shown in the following diagram:</span></span> 

<span data-ttu-id="3d866-107">![显示本地 PSTN 连接配置的图表](media/PlanDirectRouting1-PSTNwithTeams.png "与 Microsoft 团队客户端的本地 PSTN 连接配置")</span><span class="sxs-lookup"><span data-stu-id="3d866-107">![Diagram showing configuration of on-premises PSTN connectivity](media/PlanDirectRouting1-PSTNwithTeams.png "Configuration of on-premises PSTN connectivity with Microsoft Teams client")</span></span>

  > [!NOTE]
  > <span data-ttu-id="3d866-108">Skype for Business Online 还允许你与客户提供的 SBC 配对，但这需要一个本地 Skype for business 服务器部署或特殊版本的 Skype for business （称为云连接器），它位于 SBC 和 Microsoft 云之间。</span><span class="sxs-lookup"><span data-stu-id="3d866-108">Skype for Business Online also lets you pair a customer-provided SBC, but this requires an on-premises Skype for Business Server deployment or a special edition of Skype for Business, called Cloud Connector, in between the SBC and the Microsoft Cloud.</span></span> <span data-ttu-id="3d866-109">此方案称为混合语音。</span><span class="sxs-lookup"><span data-stu-id="3d866-109">This scenario is known as hybrid voice.</span></span> <span data-ttu-id="3d866-110">相比之下，直接路由允许受支持的 SBC 和 Microsoft 云之间的直接连接。</span><span class="sxs-lookup"><span data-stu-id="3d866-110">In contrast, Direct Routing allows a direct connection between the supported SBC and the Microsoft Cloud.</span></span> 

<span data-ttu-id="3d866-111">通过直接路由，你可以将 SBC 连接到几乎任何电话中继或与第三方 PSTN 设备互连。</span><span class="sxs-lookup"><span data-stu-id="3d866-111">With Direct Routing, you can connect your SBC to almost any telephony trunk or interconnect with third-party PSTN equipment.</span></span> <span data-ttu-id="3d866-112">直接路由使您能够：</span><span class="sxs-lookup"><span data-stu-id="3d866-112">Direct Routing enables you to:</span></span> 

- <span data-ttu-id="3d866-113">将几乎任何 PSTN 中继与 Microsoft Phone 系统配合使用。</span><span class="sxs-lookup"><span data-stu-id="3d866-113">Use virtually any PSTN trunk with Microsoft Phone System.</span></span> 
- <span data-ttu-id="3d866-114">配置客户拥有的电话设备（如第三方专用分支机构（PBX）、模拟设备和 Microsoft Phone 系统）之间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="3d866-114">Configure interoperability between customer-owned telephony equipment, such as a third-party private branch exchange (PBX), analog devices, and Microsoft Phone System.</span></span>

<span data-ttu-id="3d866-115">Microsoft 还提供了所有云语音解决方案，例如呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="3d866-115">Microsoft also offers all-in-the-cloud voice solutions, such as Calling Plan.</span></span> <span data-ttu-id="3d866-116">但是，混合语音解决方案可能最适合你的组织，前提是：</span><span class="sxs-lookup"><span data-stu-id="3d866-116">However, a hybrid voice solution might be best for your organization if:</span></span> 

- <span data-ttu-id="3d866-117">Microsoft 通话计划在您所在的国家/地区不可用。</span><span class="sxs-lookup"><span data-stu-id="3d866-117">Microsoft Calling Plan is not available in your country.</span></span> 
- <span data-ttu-id="3d866-118">您的组织需要连接到第三方模拟设备、呼叫中心等。</span><span class="sxs-lookup"><span data-stu-id="3d866-118">Your organization requires connection to third-party analog devices, call centers, and so on.</span></span> 
- <span data-ttu-id="3d866-119">您的组织已有一个具有 PSTN 运营商的现有合同。</span><span class="sxs-lookup"><span data-stu-id="3d866-119">Your organization has an existing contract with a PSTN carrier.</span></span>

<span data-ttu-id="3d866-120">直接路由还支持拥有 Microsoft 通话计划附加许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="3d866-120">Direct Routing also supports users who have the additional license for the Microsoft Calling Plan.</span></span> <span data-ttu-id="3d866-121">有关详细信息，请参阅[电话系统和通话计划](calling-plan-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="3d866-121">For more information, see [Phone System and Calling Plans](calling-plan-landing-page.md).</span></span> 

<span data-ttu-id="3d866-122">通过直接路由，当用户参与计划的会议时，拨入号码由 Microsoft 音频会议服务提供，这需要正确的许可。</span><span class="sxs-lookup"><span data-stu-id="3d866-122">With Direct Routing, when users participate in a scheduled conference, the dial-in number is provided by Microsoft Audio Conferencing service, which requires proper licensing.</span></span>  <span data-ttu-id="3d866-123">当拨号时，Microsoft 音频会议服务使用在线呼叫功能来呼叫呼叫，这需要正确的许可。</span><span class="sxs-lookup"><span data-stu-id="3d866-123">When dialing out, the Microsoft Audio Conferencing service places the call using online calling capabilities, which requires proper licensing.</span></span> <span data-ttu-id="3d866-124">（请注意，拨号不通过直接路由路由。）有关详细信息，请参阅[与团队联机会议](https://products.office.com/microsoft-teams/online-meeting-solutions)。</span><span class="sxs-lookup"><span data-stu-id="3d866-124">(Note that dialing out does not route through Direct Routing.) For more information, see [Online Meetings with Teams](https://products.office.com/microsoft-teams/online-meeting-solutions).</span></span> 
 
<span data-ttu-id="3d866-125">规划直接路由的部署是成功实施的关键。</span><span class="sxs-lookup"><span data-stu-id="3d866-125">Planning your deployment of Direct Routing is key to a successful implementation.</span></span> <span data-ttu-id="3d866-126">本文介绍基础结构和授权要求，并提供有关 SBC 连接的信息：</span><span class="sxs-lookup"><span data-stu-id="3d866-126">This article describes infrastructure and licensing requirements and provides information about SBC connectivity:</span></span> 

- [<span data-ttu-id="3d866-127">基础结构要求</span><span class="sxs-lookup"><span data-stu-id="3d866-127">Infrastructure requirements</span></span>](#infrastructure-requirements)
- [<span data-ttu-id="3d866-128">许可和其他要求</span><span class="sxs-lookup"><span data-stu-id="3d866-128">Licensing and other requirements</span></span>](#licensing-and-other-requirements)
- [<span data-ttu-id="3d866-129">SBC 域名称</span><span class="sxs-lookup"><span data-stu-id="3d866-129">SBC domain names</span></span>](#sbc-domain-names)
- [<span data-ttu-id="3d866-130">适用于 SBC 的公共受信任证书</span><span class="sxs-lookup"><span data-stu-id="3d866-130">Public trusted certificate for the SBC</span></span>](#public-trusted-certificate-for-the-sbc)
- [<span data-ttu-id="3d866-131">SIP 信号： Fqdn</span><span class="sxs-lookup"><span data-stu-id="3d866-131">SIP Signaling: FQDNs</span></span>](#sip-signaling-fqdns)
- [<span data-ttu-id="3d866-132">SIP 信号：端口</span><span class="sxs-lookup"><span data-stu-id="3d866-132">SIP Signaling: Ports</span></span>](#sip-signaling-ports)
- [<span data-ttu-id="3d866-133">媒体流量：端口范围</span><span class="sxs-lookup"><span data-stu-id="3d866-133">Media traffic: Port ranges</span></span>](#media-traffic-port-ranges)
- [<span data-ttu-id="3d866-134">支持的会话边框控制器（SBCs）</span><span class="sxs-lookup"><span data-stu-id="3d866-134">Supported Session Border Controllers (SBCs)</span></span>](#supported-session-border-controllers-sbcs)

<span data-ttu-id="3d866-135">有关配置直接路由的详细信息，请参阅[配置直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="3d866-135">For detailed information about configuring Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="infrastructure-requirements"></a><span data-ttu-id="3d866-136">基础结构要求</span><span class="sxs-lookup"><span data-stu-id="3d866-136">Infrastructure requirements</span></span>
<span data-ttu-id="3d866-137">下表列出了用于部署直接路由的支持的 SBCs、域和其他网络连接要求的基础结构要求：</span><span class="sxs-lookup"><span data-stu-id="3d866-137">The infrastructure requirements for the supported SBCs, domains, and other network connectivity requirements to deploy Direct Routing are listed in the following table:</span></span>  

|<span data-ttu-id="3d866-138">**基础结构要求**</span><span class="sxs-lookup"><span data-stu-id="3d866-138">**Infrastructure requirement**</span></span>|<span data-ttu-id="3d866-139">**您需要以下**</span><span class="sxs-lookup"><span data-stu-id="3d866-139">**You need the following**</span></span>|
|:--- |:--- |
|<span data-ttu-id="3d866-140">会话边框控制器（SBC）</span><span class="sxs-lookup"><span data-stu-id="3d866-140">Session Border Controller (SBC)</span></span>|<span data-ttu-id="3d866-141">受支持的 SBC。</span><span class="sxs-lookup"><span data-stu-id="3d866-141">A supported SBC.</span></span> <span data-ttu-id="3d866-142">有关详细信息，请参阅[支持的 SBCs](#supported-session-border-controllers-sbcs)。</span><span class="sxs-lookup"><span data-stu-id="3d866-142">For more information, see [Supported SBCs](#supported-session-border-controllers-sbcs).</span></span>|
|<span data-ttu-id="3d866-143">连接到 SBC 的电话中继</span><span class="sxs-lookup"><span data-stu-id="3d866-143">Telephony trunks connected to the SBC</span></span>|<span data-ttu-id="3d866-144">一个或多个电话中继连接到 SBC。</span><span class="sxs-lookup"><span data-stu-id="3d866-144">One or more telephony trunks connected to the SBC.</span></span> <span data-ttu-id="3d866-145">一端，SBC 通过直接路由连接到 Microsoft 手机系统。</span><span class="sxs-lookup"><span data-stu-id="3d866-145">On one end, the SBC connects to the Microsoft Phone System via Direct Routing.</span></span> <span data-ttu-id="3d866-146">SBC 还可以连接到第三方电话实体，如 Pbx、模拟电话适配器等。</span><span class="sxs-lookup"><span data-stu-id="3d866-146">The SBC can also connect to third-party telephony entities, such as PBXs, Analog Telephony Adapters, and so on.</span></span> <span data-ttu-id="3d866-147">任何连接到 SBC 的 PSTN 连接选项都将正常工作。</span><span class="sxs-lookup"><span data-stu-id="3d866-147">Any PSTN connectivity option connected to the SBC will work.</span></span> <span data-ttu-id="3d866-148">（有关将 PSTN 中继到 SBC 的配置，请参阅 SBC 供应商或主干提供商。）</span><span class="sxs-lookup"><span data-stu-id="3d866-148">(For configuration of the PSTN trunks to the SBC, please refer to the SBC vendors or trunk providers.)</span></span>|
|<span data-ttu-id="3d866-149">Office 365 租户</span><span class="sxs-lookup"><span data-stu-id="3d866-149">Office 365 tenant</span></span>|<span data-ttu-id="3d866-150">用于家庭 Microsoft 团队用户的 Office 365 租户，以及与 SBC 的配置和连接。</span><span class="sxs-lookup"><span data-stu-id="3d866-150">An Office 365 tenant that you use to home your Microsoft Teams users, and the configuration and connection to the SBC.</span></span>|
|<span data-ttu-id="3d866-151">用户注册机构</span><span class="sxs-lookup"><span data-stu-id="3d866-151">User registrar</span></span>|<span data-ttu-id="3d866-152">用户必须托管在 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="3d866-152">User must be homed in Office 365.</span></span><br/><span data-ttu-id="3d866-153">如果你的公司有一个本地 Skype for Business 或 Lync 环境以及与 Office 365 的混合连接，则无法为驻留在本地的用户启用团队中的语音。</span><span class="sxs-lookup"><span data-stu-id="3d866-153">If your company has an on-premises Skype for Business or Lync environment with hybrid connectivity to Office 365, you cannot enable voice in Teams for a user homed on-premises.</span></span><br/><br/><span data-ttu-id="3d866-154">若要检查用户的注册机构，请使用以下 Skype for Business Online PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3d866-154">To check the registrar of a user, use the following Skype for Business Online PowerShell cmdlet:</span></span><br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/><span data-ttu-id="3d866-155">该 cmdlet 的输出应显示：</span><span class="sxs-lookup"><span data-stu-id="3d866-155">The output of the cmdlet should show:</span></span><br/><code>HostingProvider : sipfed.online.lync.com</code>|
|<span data-ttu-id="3d866-156">域</span><span class="sxs-lookup"><span data-stu-id="3d866-156">Domains</span></span>|<span data-ttu-id="3d866-157">添加到您的 Office 365 租户的一个或多个域。</span><span class="sxs-lookup"><span data-stu-id="3d866-157">One or more domains added to your Office 365 tenants.</span></span><br/><br/><span data-ttu-id="3d866-158">请注意，你无法使用为你的\*租户自动创建的默认域 onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="3d866-158">Note that you cannot use the default domain, \*.onmicrosoft.com, that is automatically created for your tenant.</span></span><br/><br/><span data-ttu-id="3d866-159">若要查看域，您可以使用以下 Skype for Business Online PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3d866-159">To view the domains, you can use the following Skype for Business Online PowerShell cmdlet:</span></span><br/><code>Get-CsTenant \| fl Domains</code><br/><br/><span data-ttu-id="3d866-160">有关域和 Office 365 租户的详细信息，请参阅[域常见问题解答](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。</span><span class="sxs-lookup"><span data-stu-id="3d866-160">For more information about domains and Office 365 tenants, see [Domains FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).</span></span>|
|<span data-ttu-id="3d866-161">SBC 的公共 IP 地址</span><span class="sxs-lookup"><span data-stu-id="3d866-161">Public IP address for the SBC</span></span>|<span data-ttu-id="3d866-162">可用于连接到 SBC 的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3d866-162">A public IP address that can be used to connect to the SBC.</span></span> <span data-ttu-id="3d866-163">SBC 可以使用 NAT，具体取决于 SBC 的类型。</span><span class="sxs-lookup"><span data-stu-id="3d866-163">Based on the type of SBC, the SBC can use NAT.</span></span>|
|<span data-ttu-id="3d866-164">适用于 SBC 的完全限定的域名（FQDN）</span><span class="sxs-lookup"><span data-stu-id="3d866-164">Fully Qualified Domain Name (FQDN) for the SBC</span></span>|<span data-ttu-id="3d866-165">SBC 的 FQDN，其中 FQDN 的域部分是 Office 365 租户中注册的域之一。</span><span class="sxs-lookup"><span data-stu-id="3d866-165">A FQDN for the SBC, where the domain portion of the FQDN is one of the registered domains in your Office 365 tenant.</span></span> <span data-ttu-id="3d866-166">有关详细信息，请参阅[SBC 域名](#sbc-domain-names)。</span><span class="sxs-lookup"><span data-stu-id="3d866-166">For more information, see [SBC domain names](#sbc-domain-names).</span></span>|
|<span data-ttu-id="3d866-167">SBC 的公共 DNS 条目</span><span class="sxs-lookup"><span data-stu-id="3d866-167">Public DNS entry for the SBC</span></span> |<span data-ttu-id="3d866-168">将 SBC FQDN 映射到公共 IP 地址的公共 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="3d866-168">A public DNS entry mapping the SBC FQDN to the public IP Address.</span></span> |
|<span data-ttu-id="3d866-169">适用于 SBC 的公共受信任证书</span><span class="sxs-lookup"><span data-stu-id="3d866-169">Public trusted certificate for the SBC</span></span> |<span data-ttu-id="3d866-170">用于 SBC 的证书，用于与直接路由的所有通信。</span><span class="sxs-lookup"><span data-stu-id="3d866-170">A certificate for the SBC to be used for all communication with Direct Routing.</span></span> <span data-ttu-id="3d866-171">有关详细信息，请参阅[SBC 的公共受信任证书](#public-trusted-certificate-for-the-sbc)。</span><span class="sxs-lookup"><span data-stu-id="3d866-171">For more information, see [Public trusted certificate for the SBC](#public-trusted-certificate-for-the-sbc).</span></span>|
|<span data-ttu-id="3d866-172">直接路由的连接点</span><span class="sxs-lookup"><span data-stu-id="3d866-172">Connection points for Direct Routing</span></span> |<span data-ttu-id="3d866-173">直接路由的连接点是以下三个 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="3d866-173">The connection points for Direct Routing are the following three FQDNs:</span></span><br/><br/><span data-ttu-id="3d866-174">`sip.pstnhub.microsoft.com`-必须首先尝试全局 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3d866-174">`sip.pstnhub.microsoft.com` – Global FQDN, must be tried first.</span></span><br/><span data-ttu-id="3d866-175">`sip2.pstnhub.microsoft.com`-辅助 FQDN，地理位置映射到第二个优先级区域。</span><span class="sxs-lookup"><span data-stu-id="3d866-175">`sip2.pstnhub.microsoft.com` – Secondary FQDN, geographically maps to the second priority region.</span></span><br/><span data-ttu-id="3d866-176">`sip3.pstnhub.microsoft.com`-第三方 FQDN-地理位置映射到第三个优先级区域。</span><span class="sxs-lookup"><span data-stu-id="3d866-176">`sip3.pstnhub.microsoft.com` – Tertiary FQDN, geographically maps to the third priority region.</span></span><br/><br/><span data-ttu-id="3d866-177">有关配置要求的信息，请参阅[SIP 信号： fqdn](#sip-signaling-fqdns)。</span><span class="sxs-lookup"><span data-stu-id="3d866-177">For information on configuration requirements, see [SIP Signaling: FQDNs](#sip-signaling-fqdns).</span></span>|
|<span data-ttu-id="3d866-178">用于直接路由媒体的防火墙 IP 地址和端口</span><span class="sxs-lookup"><span data-stu-id="3d866-178">Firewall IP addresses and ports for Direct Routing media</span></span> |<span data-ttu-id="3d866-179">SBC 与云中的以下服务进行通信：</span><span class="sxs-lookup"><span data-stu-id="3d866-179">The SBC communicates to the following services in the cloud:</span></span><br/><br/><span data-ttu-id="3d866-180">负责处理信号的 SIP 代理</span><span class="sxs-lookup"><span data-stu-id="3d866-180">SIP Proxy, which handles the signaling</span></span><br/><span data-ttu-id="3d866-181">处理媒体的媒体处理器-当媒体绕过时除外</span><span class="sxs-lookup"><span data-stu-id="3d866-181">Media Processor, which handles media -except when Media Bypass is on</span></span><br/><br/><span data-ttu-id="3d866-182">这两个服务在 Microsoft 云中具有单独的 IP 地址，如本文档后面部分所述。</span><span class="sxs-lookup"><span data-stu-id="3d866-182">These two services have separate IP addresses in Microsoft Cloud, described later in this document.</span></span><br/><br/><span data-ttu-id="3d866-183">有关详细信息，请参阅[Office 365 url 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)中的 " [Microsoft 团队" 部分](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="3d866-183">For more information, see the [Microsoft Teams section](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) in [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> |
|<span data-ttu-id="3d866-184">媒体传输配置文件</span><span class="sxs-lookup"><span data-stu-id="3d866-184">Media Transport Profile</span></span>|<span data-ttu-id="3d866-185">TCP/RTP/SAVP</span><span class="sxs-lookup"><span data-stu-id="3d866-185">TCP/RTP/SAVP</span></span> <br/><span data-ttu-id="3d866-186">UDP/RTP/SAVP</span><span class="sxs-lookup"><span data-stu-id="3d866-186">UDP/RTP/SAVP</span></span>|
<span data-ttu-id="3d866-187">适用于 Microsoft 团队媒体的防火墙 IP 地址和端口</span><span class="sxs-lookup"><span data-stu-id="3d866-187">Firewall IP addresses and ports for Microsoft Teams media</span></span> |<span data-ttu-id="3d866-188">有关详细信息，请参阅[Office 365 url 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="3d866-188">For more information, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> |
|||

## <a name="licensing-and-other-requirements"></a><span data-ttu-id="3d866-189">许可和其他要求</span><span class="sxs-lookup"><span data-stu-id="3d866-189">Licensing and other requirements</span></span> 

<span data-ttu-id="3d866-190">直接路由用户必须在 Office 365 中分配以下许可证：</span><span class="sxs-lookup"><span data-stu-id="3d866-190">Users of Direct Routing must have the following licenses assigned in Office 365:</span></span> 

- <span data-ttu-id="3d866-191">Microsoft Phone 系统。</span><span class="sxs-lookup"><span data-stu-id="3d866-191">Microsoft Phone System.</span></span> 
- <span data-ttu-id="3d866-192">Microsoft 团队 + Skype for Business 计划2（如果包含在 "授权" 中）。</span><span class="sxs-lookup"><span data-stu-id="3d866-192">Microsoft Teams + Skype for Business Plan 2, if included in licensing.</span></span>
- <span data-ttu-id="3d866-193">Microsoft 音频会议（有关何时需要许可证的具体示例，请阅读备注和以下段落）。</span><span class="sxs-lookup"><span data-stu-id="3d866-193">Microsoft Audio Conferencing (please read the notes and the paragraph below for specific examples about when the license is required).</span></span>

> [!NOTE]
> <span data-ttu-id="3d866-194">不应将 Skype for business 计划从包括它的任何许可协议中删除。</span><span class="sxs-lookup"><span data-stu-id="3d866-194">Skype for Business Plan should not be removed from any licensing agreement where it is included.</span></span> 


> [!IMPORTANT]
>  <span data-ttu-id="3d866-195">如果你想要将外部参与者添加到计划会议，请通过拨出或提供拨入号码来向其添加外部参与者，需要音频会议许可证。</span><span class="sxs-lookup"><span data-stu-id="3d866-195">In the case that you would like to add external participants to scheduled meetings, either by dialing out to them or by providing the dial-in number, the audio conferencing license is required.</span></span>


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a><span data-ttu-id="3d866-196">临时呼叫升级和音频会议许可证</span><span class="sxs-lookup"><span data-stu-id="3d866-196">Ad hoc call escalation and Audio Conferencing license</span></span>

<span data-ttu-id="3d866-197">团队用户可以启动一对一团队到 PSTN 或团队成员通话，并向其添加 PSTN 参与者。</span><span class="sxs-lookup"><span data-stu-id="3d866-197">A Teams user can start a one-on-one Teams to PSTN or Teams to Teams call and add a PSTN participant to it.</span></span> <span data-ttu-id="3d866-198">此方案称为点对点会议。</span><span class="sxs-lookup"><span data-stu-id="3d866-198">This scenario is called an ad hoc conference.</span></span> <span data-ttu-id="3d866-199">该调用所采用的路径取决于进行此呼叫的用户是否已分配 Microsoft 音频会议许可证：</span><span class="sxs-lookup"><span data-stu-id="3d866-199">The path that the call takes depends whether the user who escalates the call has a Microsoft Audio Conferencing license assigned or not:</span></span>

- <span data-ttu-id="3d866-200">如果提出通话的团队用户分配了 Microsoft 音频会议许可证，则会通过 Microsoft 音频会议服务进行升级。</span><span class="sxs-lookup"><span data-stu-id="3d866-200">If the Teams user who escalates the call has a Microsoft Audio Conferencing license assigned, the escalation happens through the Microsoft Audio Conferencing service.</span></span> <span data-ttu-id="3d866-201">被邀请加入现有呼叫的远程 PSTN 参与者接收有关传入呼叫的通知，并查看分配给启动升级的团队用户的 Microsoft bridge 的号码。</span><span class="sxs-lookup"><span data-stu-id="3d866-201">The remote PSTN participant who is invited to the existing call receives a notification about the incoming call and sees the number of the Microsoft bridge assigned to the Teams user who initiated the escalation.</span></span>
- <span data-ttu-id="3d866-202">如果提出通话的团队用户没有分配 Microsoft 音频会议许可证，则会通过连接到直接路由界面的会话边界控制器进行升级。</span><span class="sxs-lookup"><span data-stu-id="3d866-202">If the Teams user who escalates the call does not have the Microsoft Audio Conferencing license assigned, the escalation happens through a Session Border Controller connected to the Direct Routing interface.</span></span> <span data-ttu-id="3d866-203">被邀请呼叫的远程 PSTN 参与者接收有关传入呼叫的通知，并查看发起升级的团队用户数。</span><span class="sxs-lookup"><span data-stu-id="3d866-203">The remote PSTN participant who is invited to the call receives a notification about the incoming call and sees the number of the Teams user who initiated the escalation.</span></span> <span data-ttu-id="3d866-204">用于升级的特定 SBC 由用户的路由策略定义。</span><span class="sxs-lookup"><span data-stu-id="3d866-204">The specific SBC used for the escalation is defined by Routing Policy of the user.</span></span> 


<span data-ttu-id="3d866-205">此外，必须确保以下内容：</span><span class="sxs-lookup"><span data-stu-id="3d866-205">In addition, you must ensure the following:</span></span>
 
- <span data-ttu-id="3d866-206">CsOnlineVoiceRoutingPolicy 已分配给用户。</span><span class="sxs-lookup"><span data-stu-id="3d866-206">CsOnlineVoiceRoutingPolicy is assigned to the user.</span></span> 
- <span data-ttu-id="3d866-207">允许在 Microsoft 团队的租户级别启用私人通话。</span><span class="sxs-lookup"><span data-stu-id="3d866-207">Allow Private Calling is enabled at the tenant level for Microsoft Teams.</span></span> 

<span data-ttu-id="3d866-208">直接路由还支持为 Microsoft 通话计划授权的用户。</span><span class="sxs-lookup"><span data-stu-id="3d866-208">Direct Routing also supports users who are licensed for Microsoft Calling Plan.</span></span> <span data-ttu-id="3d866-209">带有呼叫计划的 Microsoft Phone 系统可以使用直接路由界面路由某些呼叫。</span><span class="sxs-lookup"><span data-stu-id="3d866-209">Microsoft Phone System with Calling Plan can route some calls using the Direct Routing interface.</span></span> <span data-ttu-id="3d866-210">但是，用户的电话号码必须是联机购买的或移植到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="3d866-210">However, the users' phone numbers must be either acquired online or ported to Microsoft.</span></span>  

<span data-ttu-id="3d866-211">为同一用户混合呼叫计划和直接路由连接是可选的，但可能很有用（例如，当用户分配了 Microsoft 通话计划，但想要使用 SBC 路由某些调用）。</span><span class="sxs-lookup"><span data-stu-id="3d866-211">Mixing Calling Plan and Direct Routing connectivity for the same user is optional, but could be useful (for example, when the user is assigned a Microsoft Calling Plan but wants to route some calls using the SBC).</span></span> <span data-ttu-id="3d866-212">最常见的方案之一是调用第三方的 Pbx。</span><span class="sxs-lookup"><span data-stu-id="3d866-212">One of the most common scenarios are calls to third-party PBXs.</span></span>  <span data-ttu-id="3d866-213">使用第三方 Pbx，除与连接到该 Pbx 的手机通话外，所有通话均使用 Microsoft 通话计划进行路由，但连接到第三方 Pbx 的电话的电话将转到 SBC，因此在企业网络中，而不是 PSTN。</span><span class="sxs-lookup"><span data-stu-id="3d866-213">With third-party PBXs, all calls, except calls to the phones connected to that PBXs, are routed using Microsoft Calling Plan, but calls to the phones connected to third-party PBXs go to the SBC, and therefore stay within the enterprise network and not the PSTN.</span></span> 

<span data-ttu-id="3d866-214">有关电话系统许可的详细信息，请参阅[使用 office 365](https://products.office.com/compare-all-microsoft-office-products?tab=2)和[Office 365 计划选项](https://technet.microsoft.com/library/office-365-plan-options.aspx)充分利用 office。</span><span class="sxs-lookup"><span data-stu-id="3d866-214">For more information about Phone System licensing, see [Get the most from Office with Office 365](https://products.office.com/compare-all-microsoft-office-products?tab=2) and [Office 365 Plan Options](https://technet.microsoft.com/library/office-365-plan-options.aspx).</span></span> 

<span data-ttu-id="3d866-215">有关电话系统许可的详细信息，请参阅[Microsoft 团队附加许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="3d866-215">For more information about Phone System licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span> 

## <a name="supported-end-points"></a><span data-ttu-id="3d866-216">支持的终结点</span><span class="sxs-lookup"><span data-stu-id="3d866-216">Supported end points</span></span> 

<span data-ttu-id="3d866-217">您可以用作终点：</span><span class="sxs-lookup"><span data-stu-id="3d866-217">You can use as an end point:</span></span>

- <span data-ttu-id="3d866-218">任何团队客户端。</span><span class="sxs-lookup"><span data-stu-id="3d866-218">Any Teams client.</span></span> 
- <span data-ttu-id="3d866-219">常见的区域电话。</span><span class="sxs-lookup"><span data-stu-id="3d866-219">Common Area Phones.</span></span> <span data-ttu-id="3d866-220">请参阅[设置 Microsoft 团队的通用区域电话许可证](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones)。</span><span class="sxs-lookup"><span data-stu-id="3d866-220">See [Set up the Common Area Phone license for Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones).</span></span> <span data-ttu-id="3d866-221">注意使用直接路由设置普通的区域电话时，不需要呼叫计划许可证。</span><span class="sxs-lookup"><span data-stu-id="3d866-221">Note you do not need a Calling Plan license when setting up a Common Area Phone with Direct Routing.</span></span>
- <span data-ttu-id="3d866-222">Skype for Business 3PIP 手机。</span><span class="sxs-lookup"><span data-stu-id="3d866-222">Skype for Business 3PIP phones.</span></span> <span data-ttu-id="3d866-223">请参阅[Microsoft 团队的 Skype for business 电话（3PIP）支持](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)</span><span class="sxs-lookup"><span data-stu-id="3d866-223">See [Skype for Business phones (3PIP) support with Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)</span></span>


## <a name="sbc-domain-names"></a><span data-ttu-id="3d866-224">SBC 域名称</span><span class="sxs-lookup"><span data-stu-id="3d866-224">SBC domain names</span></span>

<span data-ttu-id="3d866-225">SBC 域名必须来自租户域中注册的一个名称。</span><span class="sxs-lookup"><span data-stu-id="3d866-225">The SBC domain name must be from one of the names registered in Domains of the tenant.</span></span> <span data-ttu-id="3d866-226">不能将\*onmicrosoft.com 租户用于 SBC 的 FQDN 名称。</span><span class="sxs-lookup"><span data-stu-id="3d866-226">You cannot use the \*.onmicrosoft.com tenant for the FQDN name of the SBC.</span></span>

<span data-ttu-id="3d866-227">下表显示为租户注册的 DNS 名称的示例、该名称是否可以用作 SBC 的 FQDN 以及有效 FQDN 名称的示例：</span><span class="sxs-lookup"><span data-stu-id="3d866-227">The following table shows examples of DNS names registered for the tenant, whether the name can be used as a FQDN for the SBC, and examples of valid FQDN names:</span></span>

|<span data-ttu-id="3d866-228">**DNS 名称**</span><span class="sxs-lookup"><span data-stu-id="3d866-228">**DNS name**</span></span>|<span data-ttu-id="3d866-229">**可用于 SBC FQDN**</span><span class="sxs-lookup"><span data-stu-id="3d866-229">**Can be used for SBC FQDN**</span></span>|<span data-ttu-id="3d866-230">**FQDN 名称的示例**</span><span class="sxs-lookup"><span data-stu-id="3d866-230">**Examples of FQDN names**</span></span>|
|:--- |:--- |:--- |
<span data-ttu-id="3d866-231">contoso.com</span><span class="sxs-lookup"><span data-stu-id="3d866-231">contoso.com</span></span>|<span data-ttu-id="3d866-232">是</span><span class="sxs-lookup"><span data-stu-id="3d866-232">Yes</span></span>|<span data-ttu-id="3d866-233">**有效的名称：**</span><span class="sxs-lookup"><span data-stu-id="3d866-233">**Valid names:**</span></span><br/><span data-ttu-id="3d866-234">sbc1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3d866-234">sbc1.contoso.com</span></span><br/><span data-ttu-id="3d866-235">ssbcs15.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3d866-235">ssbcs15.contoso.com</span></span><br/><span data-ttu-id="3d866-236">europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3d866-236">europe.contoso.com</span></span>|
|<span data-ttu-id="3d866-237">contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="3d866-237">contoso.onmicrosoft.com</span></span>|<span data-ttu-id="3d866-238">否</span><span class="sxs-lookup"><span data-stu-id="3d866-238">No</span></span>|<span data-ttu-id="3d866-239">SBC 名称不支持使用 \* onmicrosoft.com 域</span><span class="sxs-lookup"><span data-stu-id="3d866-239">Using \*.onmicrosoft.com domains is not supported for SBC names</span></span>

<span data-ttu-id="3d866-240">假设您要使用新域名。</span><span class="sxs-lookup"><span data-stu-id="3d866-240">Assume you want to use a new domain name.</span></span> <span data-ttu-id="3d866-241">例如，你的租户已将 contoso.com 用作你的租户中注册的域名，并且你希望使用 sbc1.sip.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="3d866-241">For example, your tenant has contoso.com as a domain name registered in your tenant, and you want to use sbc1.sip.contoso.com.</span></span> <span data-ttu-id="3d866-242">在你可以将 SBC 与 name sbc1.sip.contoso.com 配对之前，必须在租户中的域中注册域名 sip.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="3d866-242">Before you can pair an SBC with the name sbc1.sip.contoso.com, you must register the domain name sip.contoso.com in Domains in your tenant.</span></span> <span data-ttu-id="3d866-243">如果你在注册域名之前尝试将 SBC 与 sbc1.sip.contoso.com 配对，你将收到以下错误： "无法使用" sbc1.sip.contoso.com "域，因为它不是为此租户配置的。"</span><span class="sxs-lookup"><span data-stu-id="3d866-243">If you try pairing an SBC with sbc1.sip.contoso.com before registering the domain name, you will get the following error: "Cannot use the "sbc1.sip.contoso.com" domain as it was not configured for this tenant."</span></span>
<span data-ttu-id="3d866-244">添加域名后，你还需要使用 UPN user@sip.contoso.com 创建用户并分配团队许可证。</span><span class="sxs-lookup"><span data-stu-id="3d866-244">After you add the domain name, you also need to create a user with UPN user@sip.contoso.com and assign a Teams license.</span></span> <span data-ttu-id="3d866-245">在将域名添加到租户域之后，可能需要长达24小时才能完全预配域名，并创建一个具有新名称的用户，并为该用户分配一个许可证。</span><span class="sxs-lookup"><span data-stu-id="3d866-245">It might take up to 24 hours to fully provision the domain name after it is added to Domains of your tenant, a user with a new name is created, and a license is assigned to the user.</span></span> 

<span data-ttu-id="3d866-246">公司可能在一个租户中有多个 SIP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="3d866-246">It is possible that a company might have several SIP address spaces in one tenant.</span></span> <span data-ttu-id="3d866-247">例如，公司可能已将 contoso.com 用作 SIP 地址空间，而 fabrikam.com 作为第二个 SIP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="3d866-247">For example, a company might have contoso.com as a SIP address space and fabrikam.com as the second SIP address space.</span></span> <span data-ttu-id="3d866-248">某些用户具有地址 user@contoso.com，而某些用户具有地址 user@fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="3d866-248">Some users have address user@contoso.com and some users have address user@fabrikam.com.</span></span> 

<span data-ttu-id="3d866-249">SBC 仅需要一个 FQDN，并且可以通过配对的租户中的任何地址空间为用户服务。</span><span class="sxs-lookup"><span data-stu-id="3d866-249">The SBC only needs one FQDN and can service users from any address space in the paired tenant.</span></span> <span data-ttu-id="3d866-250">例如，具有名称 sbc1.contoso.com 的 SBC 可以接收和发送具有地址 user@contoso.com 和 user@fabrikam.com 的用户的 PSTN 流量，只要这些 SIP 地址空间在同一租户中注册。</span><span class="sxs-lookup"><span data-stu-id="3d866-250">For example,  an SBC with the name sbc1.contoso.com can receive and send the PSTN traffic for users with addresses user@contoso.com and user@fabrikam.com as long as these SIP address spaces are registered in the same tenant.</span></span>  

## <a name="public-trusted-certificate-for-the-sbc"></a><span data-ttu-id="3d866-251">适用于 SBC 的公共受信任证书</span><span class="sxs-lookup"><span data-stu-id="3d866-251">Public trusted certificate for the SBC</span></span>

<span data-ttu-id="3d866-252">Microsoft 建议你通过生成证书签名请求（CSR）来请求 SBC 的证书。</span><span class="sxs-lookup"><span data-stu-id="3d866-252">Microsoft recommends that you request the certificate for the SBC by generating a certification signing request (CSR).</span></span> <span data-ttu-id="3d866-253">有关为 SBC 生成 CSR 的特定说明，请参阅由 SBC 供应商提供的互连说明或文档。</span><span class="sxs-lookup"><span data-stu-id="3d866-253">For specific instructions on generating a CSR for an SBC, refer to the interconnection instructions or documentation provided by your SBC vendors.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="3d866-254">大多数证书颁发机构（Ca）要求私钥大小至少为2048。</span><span class="sxs-lookup"><span data-stu-id="3d866-254">Most Certificate Authorities (CAs) require the private key size to be at least 2048.</span></span> <span data-ttu-id="3d866-255">在生成 CSR 时请记住这一点。</span><span class="sxs-lookup"><span data-stu-id="3d866-255">Keep this in mind when generating the CSR.</span></span>

<span data-ttu-id="3d866-256">证书需要在 "主题"、"公用名" 或 "使用者备用名称" 字段中具有 SBC FQDN。</span><span class="sxs-lookup"><span data-stu-id="3d866-256">The certificate needs to have the SBC FQDN in the subject, common name, or subject alternate name fields.</span></span>

<span data-ttu-id="3d866-257">或者，直接路由支持 SAN 中的通配符，并且通配符需要符合 TLS 上的标准[RFC HTTP](https://tools.ietf.org/html/rfc2818#section-3.1)。</span><span class="sxs-lookup"><span data-stu-id="3d866-257">Alternatively, Direct Routing  supports a wildcard in SAN, and the wildcard needs to conform to standard [RFC HTTP Over TLS](https://tools.ietf.org/html/rfc2818#section-3.1).</span></span> <span data-ttu-id="3d866-258">SAN 中将使用\*contoso.com，这将与 SBC FQDN sbc.contoso.com 相匹配，但与 sbc.test.contoso.com 不匹配。</span><span class="sxs-lookup"><span data-stu-id="3d866-258">An example would be using \*.contoso.com in the SAN, which would match the SBC FQDN sbc.contoso.com, but wouldn’t match with sbc.test.contoso.com.</span></span>

<span data-ttu-id="3d866-259">证书需要由以下根证书颁发机构之一生成：</span><span class="sxs-lookup"><span data-stu-id="3d866-259">The certificate needs to be generated by one of the following root certificate authorities:</span></span>

- <span data-ttu-id="3d866-260">AffirmTrust</span><span class="sxs-lookup"><span data-stu-id="3d866-260">AffirmTrust</span></span>
- <span data-ttu-id="3d866-261">AddTrust 外部 CA 根</span><span class="sxs-lookup"><span data-stu-id="3d866-261">AddTrust External CA Root</span></span>
- <span data-ttu-id="3d866-262">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="3d866-262">Baltimore CyberTrust Root</span></span>
- <span data-ttu-id="3d866-263">Buypass</span><span class="sxs-lookup"><span data-stu-id="3d866-263">Buypass</span></span>
- <span data-ttu-id="3d866-264">Cybertrust</span><span class="sxs-lookup"><span data-stu-id="3d866-264">Cybertrust</span></span>
- <span data-ttu-id="3d866-265">第3类公共主证书颁发机构</span><span class="sxs-lookup"><span data-stu-id="3d866-265">Class 3 Public Primary Certification Authority</span></span>
- <span data-ttu-id="3d866-266">Comodo 安全根 CA</span><span class="sxs-lookup"><span data-stu-id="3d866-266">Comodo Secure Root CA</span></span>
- <span data-ttu-id="3d866-267">德国 Telekom</span><span class="sxs-lookup"><span data-stu-id="3d866-267">Deutsche Telekom</span></span> 
- <span data-ttu-id="3d866-268">DigiCert 全局根 CA</span><span class="sxs-lookup"><span data-stu-id="3d866-268">DigiCert Global Root CA</span></span>
- <span data-ttu-id="3d866-269">DigiCert 高确定性 EV 根 CA</span><span class="sxs-lookup"><span data-stu-id="3d866-269">DigiCert High Assurance EV Root CA</span></span>
- <span data-ttu-id="3d866-270">Entrust</span><span class="sxs-lookup"><span data-stu-id="3d866-270">Entrust</span></span>
- <span data-ttu-id="3d866-271">GlobalSign</span><span class="sxs-lookup"><span data-stu-id="3d866-271">GlobalSign</span></span>
- <span data-ttu-id="3d866-272">转到 Daddy</span><span class="sxs-lookup"><span data-stu-id="3d866-272">Go Daddy</span></span>
- <span data-ttu-id="3d866-273">GeoTrust</span><span class="sxs-lookup"><span data-stu-id="3d866-273">GeoTrust</span></span>
- <span data-ttu-id="3d866-274">Verisign，Inc。</span><span class="sxs-lookup"><span data-stu-id="3d866-274">Verisign, Inc.</span></span> 
- <span data-ttu-id="3d866-275">SSL.com</span><span class="sxs-lookup"><span data-stu-id="3d866-275">SSL.com</span></span>
- <span data-ttu-id="3d866-276">Starfield</span><span class="sxs-lookup"><span data-stu-id="3d866-276">Starfield</span></span>
- <span data-ttu-id="3d866-277">适用于 Microsoft 的 Symantec 企业版移动根</span><span class="sxs-lookup"><span data-stu-id="3d866-277">Symantec Enterprise Mobile Root for Microsoft</span></span> 
- <span data-ttu-id="3d866-278">SwissSign</span><span class="sxs-lookup"><span data-stu-id="3d866-278">SwissSign</span></span>
- <span data-ttu-id="3d866-279">Thawte 时间戳 CA</span><span class="sxs-lookup"><span data-stu-id="3d866-279">Thawte Timestamping CA</span></span>
- <span data-ttu-id="3d866-280">Trustwave</span><span class="sxs-lookup"><span data-stu-id="3d866-280">Trustwave</span></span>
- <span data-ttu-id="3d866-281">TeliaSonera</span><span class="sxs-lookup"><span data-stu-id="3d866-281">TeliaSonera</span></span> 
- <span data-ttu-id="3d866-282">T 位系统国际 GmbH （德国 Telekom）</span><span class="sxs-lookup"><span data-stu-id="3d866-282">T-Systems International GmbH (Deutsche Telekom)</span></span>
- <span data-ttu-id="3d866-283">QuoVadis</span><span class="sxs-lookup"><span data-stu-id="3d866-283">QuoVadis</span></span>

<span data-ttu-id="3d866-284">Microsoft 正在努力根据客户请求添加其他认证机构。</span><span class="sxs-lookup"><span data-stu-id="3d866-284">Microsoft is working on adding additional certification authorities based on customer requests.</span></span> 

## <a name="sip-signaling-fqdns"></a><span data-ttu-id="3d866-285">SIP 信号： Fqdn</span><span class="sxs-lookup"><span data-stu-id="3d866-285">SIP Signaling: FQDNs</span></span> 

<span data-ttu-id="3d866-286">直接路由在以下 Office 365 环境中提供：</span><span class="sxs-lookup"><span data-stu-id="3d866-286">Direct Routing is offered in the following Office 365 environments:</span></span>
- <span data-ttu-id="3d866-287">Office 365</span><span class="sxs-lookup"><span data-stu-id="3d866-287">Office 365</span></span>
- <span data-ttu-id="3d866-288">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="3d866-288">Office 365 GCC</span></span>
- <span data-ttu-id="3d866-289">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="3d866-289">Office 365 GCC High</span></span>
- <span data-ttu-id="3d866-290">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="3d866-290">Office 365 DoD</span></span>

<span data-ttu-id="3d866-291">了解有关[Office 365 和美国政府环境](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)（如 GCC、gcc 高级版和 DoD）的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3d866-291">Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="3d866-292">Office 365 和 Office 365 GCC 环境</span><span class="sxs-lookup"><span data-stu-id="3d866-292">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="3d866-293">直接路由的连接点是以下三个 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="3d866-293">The connection point for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="3d866-294">**sip.pstnhub.microsoft.com** -必须首先尝试全局 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3d866-294">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="3d866-295">当 SBC 发送一个请求来解析此名称时，Microsoft Azure DNS 服务器将返回指向分配给 SBC 的主 Azure 数据中心的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3d866-295">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="3d866-296">该作业基于数据中心的性能指标和与 SBC 的地理位置的接近度。</span><span class="sxs-lookup"><span data-stu-id="3d866-296">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="3d866-297">返回的 IP 地址对应于主 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3d866-297">The IP address returned corresponds to the primary FQDN.</span></span>
- <span data-ttu-id="3d866-298">**sip2.pstnhub.microsoft.com** -辅助 FQDN-地理位置映射到第二个优先级区域。</span><span class="sxs-lookup"><span data-stu-id="3d866-298">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>
- <span data-ttu-id="3d866-299">**sip3.pstnhub.microsoft.com** -第三方 FQDN-地理位置映射到第三个优先级区域。</span><span class="sxs-lookup"><span data-stu-id="3d866-299">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="3d866-300">按顺序放置这三个 Fqdn 需要：</span><span class="sxs-lookup"><span data-stu-id="3d866-300">Placing these three FQDNs in order is required to:</span></span>

- <span data-ttu-id="3d866-301">提供最佳体验（加载时间最少且最接近通过查询第一个 FQDN 分配的 SBC 数据中心）。</span><span class="sxs-lookup"><span data-stu-id="3d866-301">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>
- <span data-ttu-id="3d866-302">当从 SBC 建立连接到遇到暂时性问题的数据中心时，请提供故障转移。</span><span class="sxs-lookup"><span data-stu-id="3d866-302">Provide failover when connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="3d866-303">有关详细信息，请参阅下面的[故障转移机制](#failover-mechanism-for-sip-signaling)。</span><span class="sxs-lookup"><span data-stu-id="3d866-303">For more information, see [Failover mechanism](#failover-mechanism-for-sip-signaling) below.</span></span>  

<span data-ttu-id="3d866-304">Fqdn （sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com 和 sip3.pstnhub.microsoft.com）将解析为以下 IP 地址之一：</span><span class="sxs-lookup"><span data-stu-id="3d866-304">The FQDNs – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com and sip3.pstnhub.microsoft.com – will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="3d866-305">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="3d866-305">52.114.148.0</span></span>
- <span data-ttu-id="3d866-306">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="3d866-306">52.114.132.46</span></span> 
- <span data-ttu-id="3d866-307">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="3d866-307">52.114.75.24</span></span> 
- <span data-ttu-id="3d866-308">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="3d866-308">52.114.76.76</span></span> 
- <span data-ttu-id="3d866-309">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="3d866-309">52.114.7.24</span></span> 
- <span data-ttu-id="3d866-310">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="3d866-310">52.114.14.70</span></span>

<span data-ttu-id="3d866-311">您需要在防火墙中打开所有这些 IP 地址的端口，以允许传入和传出通信发送和接收来自地址的发送信号。</span><span class="sxs-lookup"><span data-stu-id="3d866-311">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="3d866-312">如果你的防火墙支持 DNS 名称，FQDN sip-all.pstnhub.microsoft.com 将解析为所有这些 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3d866-312">If your firewall supports DNS names, the FQDN sip-all.pstnhub.microsoft.com resolves to all these IP addresses.</span></span> 


### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="3d866-313">Office 365 GCC DoD 环境</span><span class="sxs-lookup"><span data-stu-id="3d866-313">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="3d866-314">直接路由的连接点是以下 FQDN：</span><span class="sxs-lookup"><span data-stu-id="3d866-314">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="3d866-315">**sip.pstnhub.dod.teams.microsoft.us** -全局 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3d866-315">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="3d866-316">由于 Office 365 DoD 环境仅存在于美国数据中心，因此没有第二个和第三个 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="3d866-316">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="3d866-317">FQDN sip.pstnhub.dod.teams.microsoft.us 将解析为下列 IP 地址之一：</span><span class="sxs-lookup"><span data-stu-id="3d866-317">The FQDN sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="3d866-318">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="3d866-318">52.127.64.33</span></span>
- <span data-ttu-id="3d866-319">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="3d866-319">52.127.68.34</span></span>

<span data-ttu-id="3d866-320">您需要在防火墙中打开所有这些 IP 地址的端口，以允许传入和传出通信发送和接收来自地址的发送信号。</span><span class="sxs-lookup"><span data-stu-id="3d866-320">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="3d866-321">如果你的防火墙支持 DNS 名称，FQDN sip.pstnhub.dod.teams.microsoft.us 将解析为所有这些 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3d866-321">If your firewall supports DNS names, the FQDN sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="3d866-322">Office 365 GCC 高环境</span><span class="sxs-lookup"><span data-stu-id="3d866-322">Office 365 GCC High environment</span></span>

<span data-ttu-id="3d866-323">直接路由的连接点是以下 FQDN：</span><span class="sxs-lookup"><span data-stu-id="3d866-323">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="3d866-324">**sip.pstnhub.gov.teams.microsoft.us** -全局 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3d866-324">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="3d866-325">由于 GCC 的高环境仅存在于美国数据中心，因此没有第二个和第三个 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="3d866-325">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="3d866-326">FQDN sip.pstnhub.gov.teams.microsoft.us 将解析为下列 IP 地址之一：</span><span class="sxs-lookup"><span data-stu-id="3d866-326">The FQDN sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="3d866-327">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="3d866-327">52.127.88.59</span></span>
- <span data-ttu-id="3d866-328">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="3d866-328">52.127.92.64</span></span>

<span data-ttu-id="3d866-329">您需要在防火墙中打开所有这些 IP 地址的端口，以允许传入和传出通信发送和接收来自地址的发送信号。</span><span class="sxs-lookup"><span data-stu-id="3d866-329">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="3d866-330">如果你的防火墙支持 DNS 名称，FQDN sip.pstnhub.gov.teams.microsoft.us 将解析为所有这些 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3d866-330">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="3d866-331">SIP 信号：端口</span><span class="sxs-lookup"><span data-stu-id="3d866-331">SIP Signaling: Ports</span></span>

<span data-ttu-id="3d866-332">对于 Office 365 环境，您必须使用以下端口，即提供直接路由：</span><span class="sxs-lookup"><span data-stu-id="3d866-332">You must use the following ports for Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="3d866-333">Office 365</span><span class="sxs-lookup"><span data-stu-id="3d866-333">Office 365</span></span>
- <span data-ttu-id="3d866-334">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="3d866-334">Office 365 GCC</span></span>
- <span data-ttu-id="3d866-335">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="3d866-335">Office 365 GCC High</span></span>
- <span data-ttu-id="3d866-336">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="3d866-336">Office 365 DoD</span></span>

|<span data-ttu-id="3d866-337">**流量**</span><span class="sxs-lookup"><span data-stu-id="3d866-337">**Traffic**</span></span>|<span data-ttu-id="3d866-338">**从**</span><span class="sxs-lookup"><span data-stu-id="3d866-338">**From**</span></span>|<span data-ttu-id="3d866-339">**到**</span><span class="sxs-lookup"><span data-stu-id="3d866-339">**To**</span></span>|<span data-ttu-id="3d866-340">**源端口**</span><span class="sxs-lookup"><span data-stu-id="3d866-340">**Source port**</span></span>|<span data-ttu-id="3d866-341">**目标端口**</span><span class="sxs-lookup"><span data-stu-id="3d866-341">**Destination port**</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="3d866-342">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="3d866-342">SIP/TLS</span></span>|<span data-ttu-id="3d866-343">SIP 代理</span><span class="sxs-lookup"><span data-stu-id="3d866-343">SIP Proxy</span></span>|<span data-ttu-id="3d866-344">SBC</span><span class="sxs-lookup"><span data-stu-id="3d866-344">SBC</span></span>|<span data-ttu-id="3d866-345">1024-65535</span><span class="sxs-lookup"><span data-stu-id="3d866-345">1024 – 65535</span></span>|<span data-ttu-id="3d866-346">在 SBC 上定义（对于 Office 365，必须使用仅适用于 Office 的 GCC/DoD 专用端口5061）</span><span class="sxs-lookup"><span data-stu-id="3d866-346">Defined on the SBC (For Office 365 GCC High/DoD only port 5061 must be used)</span></span>|
<span data-ttu-id="3d866-347">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="3d866-347">SIP/TLS</span></span>|<span data-ttu-id="3d866-348">SBC</span><span class="sxs-lookup"><span data-stu-id="3d866-348">SBC</span></span>|<span data-ttu-id="3d866-349">SIP 代理</span><span class="sxs-lookup"><span data-stu-id="3d866-349">SIP Proxy</span></span>|<span data-ttu-id="3d866-350">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="3d866-350">Defined on the SBC</span></span>|<span data-ttu-id="3d866-351">5061</span><span class="sxs-lookup"><span data-stu-id="3d866-351">5061</span></span>|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a><span data-ttu-id="3d866-352">SIP 信号的故障转移机制</span><span class="sxs-lookup"><span data-stu-id="3d866-352">Failover mechanism for SIP Signaling</span></span>

<span data-ttu-id="3d866-353">SBC 进行 DNS 查询来解析 sip.pstnhub.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="3d866-353">The SBC makes a DNS query to resolve sip.pstnhub.microsoft.com.</span></span> <span data-ttu-id="3d866-354">根据 SBC 位置和数据中心性能指标，选择主数据中心。</span><span class="sxs-lookup"><span data-stu-id="3d866-354">Based on the SBC location and the datacenter performance metrics, the primary datacenter is selected.</span></span> <span data-ttu-id="3d866-355">如果主数据中心遇到问题，则 SBC 将尝试可解析为第二个分配的数据中心的 sip2.pstnhub.microsoft.com，并且在这种情况下，在两个区域中的数据中心不可用时，SBC 将重试最后一个 FQDN （sip3.pstnhub.microsoft.com），它提供第三数据中心 IP。</span><span class="sxs-lookup"><span data-stu-id="3d866-355">If the primary datacenter experiences an issue, the SBC will try the sip2.pstnhub.microsoft.com, which resolves to the second assigned datacenter, and, in the rare case that datacenters in two regions are not available, the SBC retries the last FQDN (sip3.pstnhub.microsoft.com), which provides the tertiary datacenter IP.</span></span>

<span data-ttu-id="3d866-356">下表总结了主数据中心、辅助数据中心和第三数据中心之间的关系：</span><span class="sxs-lookup"><span data-stu-id="3d866-356">The table below summarizes the relationships between primary, secondary, and tertiary datacenters:</span></span>

|<span data-ttu-id="3d866-357">**如果主数据中心是**</span><span class="sxs-lookup"><span data-stu-id="3d866-357">**If the primary datacenter is**</span></span>|<span data-ttu-id="3d866-358">**EMEA**</span><span class="sxs-lookup"><span data-stu-id="3d866-358">**EMEA**</span></span>|<span data-ttu-id="3d866-359">**NOAM**</span><span class="sxs-lookup"><span data-stu-id="3d866-359">**NOAM**</span></span>|<span data-ttu-id="3d866-360">**地区**</span><span class="sxs-lookup"><span data-stu-id="3d866-360">**ASIA**</span></span>|
|:--- |:--- |:--- |:--- |
|<span data-ttu-id="3d866-361">辅助数据中心（sip2.pstnhub.microsoft.com）</span><span class="sxs-lookup"><span data-stu-id="3d866-361">The secondary datacenter (sip2.pstnhub.microsoft.com)</span></span>|<span data-ttu-id="3d866-362">我们</span><span class="sxs-lookup"><span data-stu-id="3d866-362">US</span></span>|<span data-ttu-id="3d866-363">各</span><span class="sxs-lookup"><span data-stu-id="3d866-363">EU</span></span>|<span data-ttu-id="3d866-364">我们</span><span class="sxs-lookup"><span data-stu-id="3d866-364">US</span></span>|
|<span data-ttu-id="3d866-365">第三数据中心（sip3.pstnhub.microsoft.com）</span><span class="sxs-lookup"><span data-stu-id="3d866-365">The tertiary datacenter (sip3.pstnhub.microsoft.com)</span></span>|<span data-ttu-id="3d866-366">地区</span><span class="sxs-lookup"><span data-stu-id="3d866-366">ASIA</span></span>|<span data-ttu-id="3d866-367">地区</span><span class="sxs-lookup"><span data-stu-id="3d866-367">ASIA</span></span>|<span data-ttu-id="3d866-368">各</span><span class="sxs-lookup"><span data-stu-id="3d866-368">EU</span></span>|
|||||

## <a name="media-traffic-port-ranges"></a><span data-ttu-id="3d866-369">媒体流量：端口范围</span><span class="sxs-lookup"><span data-stu-id="3d866-369">Media traffic: Port ranges</span></span>
<span data-ttu-id="3d866-370">请注意，如果你想要在不使用媒体绕过的情况下部署直接路由，请应用以下要求。</span><span class="sxs-lookup"><span data-stu-id="3d866-370">Note that the requirements below apply if you want to deploy Direct Routing without Media Bypass.</span></span> <span data-ttu-id="3d866-371">有关媒体绕过的防火墙要求，请参阅[使用直接路由规划媒体旁路](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass)。</span><span class="sxs-lookup"><span data-stu-id="3d866-371">For firewall requirements for Media Bypass, please refer to [Plan for media bypass with Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass).</span></span>



<span data-ttu-id="3d866-372">媒体流量从 Microsoft 云中单独的服务流出。</span><span class="sxs-lookup"><span data-stu-id="3d866-372">The media traffic flows to and from a separate service in the Microsoft Cloud.</span></span> <span data-ttu-id="3d866-373">媒体流量的 IP 范围如下所示。</span><span class="sxs-lookup"><span data-stu-id="3d866-373">The IP range for Media traffic are as follows.</span></span>

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="3d866-374">Office 365 和 Office 365 GCC 环境</span><span class="sxs-lookup"><span data-stu-id="3d866-374">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="3d866-375">52.112.0.0/14 （从52.112.0.1 到52.115.255.254 的 IP 地址）。</span><span class="sxs-lookup"><span data-stu-id="3d866-375">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="3d866-376">Office 365 GCC DoD 环境</span><span class="sxs-lookup"><span data-stu-id="3d866-376">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="3d866-377">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="3d866-377">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="3d866-378">Office 365 GCC 高环境</span><span class="sxs-lookup"><span data-stu-id="3d866-378">Office 365 GCC High environment</span></span>

- <span data-ttu-id="3d866-379">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="3d866-379">52.127.88.0/21</span></span>

### <a name="port-range-applicable-to-all-environments"></a><span data-ttu-id="3d866-380">端口范围（适用于所有环境）</span><span class="sxs-lookup"><span data-stu-id="3d866-380">Port range (applicable to all environments)</span></span>
<span data-ttu-id="3d866-381">下表显示了媒体处理器的端口范围：</span><span class="sxs-lookup"><span data-stu-id="3d866-381">The port range of the Media Processors is shown in the following table:</span></span> 

|<span data-ttu-id="3d866-382">**流量**</span><span class="sxs-lookup"><span data-stu-id="3d866-382">**Traffic**</span></span>|<span data-ttu-id="3d866-383">**从**</span><span class="sxs-lookup"><span data-stu-id="3d866-383">**From**</span></span>|<span data-ttu-id="3d866-384">**到**</span><span class="sxs-lookup"><span data-stu-id="3d866-384">**To**</span></span>|<span data-ttu-id="3d866-385">**源端口**</span><span class="sxs-lookup"><span data-stu-id="3d866-385">**Source port**</span></span>|<span data-ttu-id="3d866-386">**目标端口**</span><span class="sxs-lookup"><span data-stu-id="3d866-386">**Destination port**</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="3d866-387">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="3d866-387">UDP/SRTP</span></span>|<span data-ttu-id="3d866-388">媒体处理器</span><span class="sxs-lookup"><span data-stu-id="3d866-388">Media Processor</span></span>|<span data-ttu-id="3d866-389">SBC</span><span class="sxs-lookup"><span data-stu-id="3d866-389">SBC</span></span>|<span data-ttu-id="3d866-390">49152-53247</span><span class="sxs-lookup"><span data-stu-id="3d866-390">49152 – 53247</span></span>|<span data-ttu-id="3d866-391">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="3d866-391">Defined on the SBC</span></span>|
|<span data-ttu-id="3d866-392">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="3d866-392">UDP/SRTP</span></span>|<span data-ttu-id="3d866-393">SBC</span><span class="sxs-lookup"><span data-stu-id="3d866-393">SBC</span></span>|<span data-ttu-id="3d866-394">媒体处理器</span><span class="sxs-lookup"><span data-stu-id="3d866-394">Media Processor</span></span>|<span data-ttu-id="3d866-395">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="3d866-395">Defined on the SBC</span></span>|<span data-ttu-id="3d866-396">49152-53247</span><span class="sxs-lookup"><span data-stu-id="3d866-396">49152 – 53247</span></span>|

  > [!NOTE]
  > <span data-ttu-id="3d866-397">Microsoft 建议在 SBC 上对每个并发调用至少有两个端口。</span><span class="sxs-lookup"><span data-stu-id="3d866-397">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span>


## <a name="media-traffic-media-processors-geography"></a><span data-ttu-id="3d866-398">媒体流量：媒体处理者地理位置</span><span class="sxs-lookup"><span data-stu-id="3d866-398">Media traffic: Media processors geography</span></span>

<span data-ttu-id="3d866-399">媒体流量通过名为媒体处理器的组件流出。</span><span class="sxs-lookup"><span data-stu-id="3d866-399">The media traffic flows via components called media processors.</span></span> <span data-ttu-id="3d866-400">媒体处理器与 SIP 代理放在同一数据中心。</span><span class="sxs-lookup"><span data-stu-id="3d866-400">Media processors are placed in the same datacenters as SIP proxies.</span></span> <span data-ttu-id="3d866-401">此外，还有其他媒体处理器来优化媒体流。</span><span class="sxs-lookup"><span data-stu-id="3d866-401">Also, there are additional media processors to optimize media flow.</span></span> <span data-ttu-id="3d866-402">例如，我们目前在澳大利亚（通过新加坡或香港特别行政区）提供 SIP 代理组件，但我们在澳大利亚本地有媒体处理器。</span><span class="sxs-lookup"><span data-stu-id="3d866-402">For example, we do not have a SIP proxy component now in Australia (SIP flows via Singapore or Hong Kong) but we do have the media processor locally in Australia.</span></span> <span data-ttu-id="3d866-403">对媒体处理者的需求取决于我们通过发送远距离（例如从澳大利亚到新加坡或香港特别行政区）进行的延迟。</span><span class="sxs-lookup"><span data-stu-id="3d866-403">The need for the media processors locally is dictated by the latency which we experience by sending traffic long-distance, for example from Australia to Singapore or Hong Kong.</span></span> <span data-ttu-id="3d866-404">虽然从澳大利亚到香港或新加坡的流量示例中的延迟是为 SIP 流量保持良好的通话质量，但对于实时媒体流量而言，它是不可接受的。</span><span class="sxs-lookup"><span data-stu-id="3d866-404">While latency in the example of traffic flowing from Australia to Hong Kong or Singapore is acceptable to preserve good call quality for SIP traffic, for real-time media traffic it is not.</span></span>

<span data-ttu-id="3d866-405">媒体处理器的位置：</span><span class="sxs-lookup"><span data-stu-id="3d866-405">Location of the media processors:</span></span>

<span data-ttu-id="3d866-406">SIP 代理和媒体处理器组件部署的位置：</span><span class="sxs-lookup"><span data-stu-id="3d866-406">Locations where both SIP proxy and media processor components deployed:</span></span>
- <span data-ttu-id="3d866-407">我们（美国西部和华南东数据中心的两个）</span><span class="sxs-lookup"><span data-stu-id="3d866-407">US (two in US West and US East datacenters)</span></span>
- <span data-ttu-id="3d866-408">欧洲（阿姆斯特丹和都柏林数据中心）</span><span class="sxs-lookup"><span data-stu-id="3d866-408">Europe (Amsterdam and Dublin datacenters)</span></span>
- <span data-ttu-id="3d866-409">亚洲（新加坡和香港特别行政区）</span><span class="sxs-lookup"><span data-stu-id="3d866-409">Asia (Singapore and Hong Kong datacenters)</span></span>

<span data-ttu-id="3d866-410">仅部署媒体处理器的位置（SIP 通过上面列出的最接近的数据中心流）：</span><span class="sxs-lookup"><span data-stu-id="3d866-410">Locations where only media processors are deployed (SIP flows via the closest datacenter listed above):</span></span>
- <span data-ttu-id="3d866-411">日本（JP 和西部数据中心）</span><span class="sxs-lookup"><span data-stu-id="3d866-411">Japan (JP East and West datacenters)</span></span>
- <span data-ttu-id="3d866-412">澳大利亚（AU 东和西数据中心）</span><span class="sxs-lookup"><span data-stu-id="3d866-412">Australia (AU East and West datacenters)</span></span>




## <a name="media-traffic-codecs"></a><span data-ttu-id="3d866-413">媒体流量：编解码器</span><span class="sxs-lookup"><span data-stu-id="3d866-413">Media traffic: Codecs</span></span>

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a><span data-ttu-id="3d866-414">SBC 和云媒体处理器或 Microsoft 团队客户端之间的腿。</span><span class="sxs-lookup"><span data-stu-id="3d866-414">Leg between SBC and Cloud Media Processor or Microsoft Teams client.</span></span>
<span data-ttu-id="3d866-415">适用于媒体旁路情况和非绕过情况。</span><span class="sxs-lookup"><span data-stu-id="3d866-415">Applies to both media bypass case and non-bypass cases.</span></span>

<span data-ttu-id="3d866-416">会话边界控制器和云媒体处理器（没有媒体旁路）或团队客户端与 SBC 之间（如果启用了媒体旁路）之间的直接路由接口，可以使用以下编解码器：</span><span class="sxs-lookup"><span data-stu-id="3d866-416">The Direct Routing interface on the leg between the Session Border Controller and Cloud Media Processor (without media bypass) or between the Teams client and the SBC (if Media Bypass enabled) can use the following codecs:</span></span>

- <span data-ttu-id="3d866-417">非媒体旁路（SBC 到云媒体处理器）：绞丝、711、722、G 729</span><span class="sxs-lookup"><span data-stu-id="3d866-417">Non-Media bypass (SBC to Cloud Media Processor): SILK, G.711, G.722, G.729</span></span>
- <span data-ttu-id="3d866-418">媒体绕过（SBC 到团队客户端）：绞丝、711、722、729</span><span class="sxs-lookup"><span data-stu-id="3d866-418">Media Bypass (SBC to Teams client):  SILK, G.711, G.722, G.729</span></span>

<span data-ttu-id="3d866-419">你可以通过从优惠中排除不需要的编解码器来强制使用会话边界控制器上的特定编解码器。</span><span class="sxs-lookup"><span data-stu-id="3d866-419">You can force use of the specific codec on the Session Border Controller by excluding undesirable codecs from the offer.</span></span>

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a><span data-ttu-id="3d866-420">Microsoft 团队客户端与云媒体处理器之间的腿</span><span class="sxs-lookup"><span data-stu-id="3d866-420">Leg between Microsoft Teams Client and Cloud Media Processor</span></span>
<span data-ttu-id="3d866-421">仅适用于非媒体旁路大小写。</span><span class="sxs-lookup"><span data-stu-id="3d866-421">Applies to non-media bypass case only.</span></span> <span data-ttu-id="3d866-422">通过媒体绕过，媒体将直接在团队客户端和 SBC 之间流动。</span><span class="sxs-lookup"><span data-stu-id="3d866-422">With Media Bypass, the media flows directly between the Teams client and the SBC.</span></span>

<span data-ttu-id="3d866-423">在云媒体处理器和 Microsoft 团队客户端之间的腿处使用的是722或。</span><span class="sxs-lookup"><span data-stu-id="3d866-423">On the leg between the Cloud Media Processor and Microsoft Teams client either SILK or G.722 is used.</span></span> <span data-ttu-id="3d866-424">此段腿的编解码器选项基于 Microsoft 算法，这些算法考虑多个参数。</span><span class="sxs-lookup"><span data-stu-id="3d866-424">The codec choice on this leg is based on Microsoft algorithms, which take into consideration multiple parameters.</span></span> 


## <a name="supported-session-border-controllers-sbcs"></a><span data-ttu-id="3d866-425">支持的会话边框控制器（SBCs）</span><span class="sxs-lookup"><span data-stu-id="3d866-425">Supported Session Border Controllers (SBCs)</span></span>

<span data-ttu-id="3d866-426">Microsoft 仅支持经认证的 SBCs 与直接路由配对。</span><span class="sxs-lookup"><span data-stu-id="3d866-426">Microsoft only supports certified SBCs to pair with Direct Routing.</span></span> <span data-ttu-id="3d866-427">由于企业语音对企业至关重要，Microsoft 使用所选 SBCs 运行大量测试，并与 SBC 供应商一起使用，确保两个系统兼容。</span><span class="sxs-lookup"><span data-stu-id="3d866-427">Because Enterprise Voice is critical for businesses, Microsoft runs intensive tests with the selected SBCs, and works with the SBC vendors to ensure the two systems are compatible.</span></span> 

<span data-ttu-id="3d866-428">已验证的设备列为团队直接路由的认证。</span><span class="sxs-lookup"><span data-stu-id="3d866-428">Devices that have been validated are listed as Certified for Teams Direct Routing.</span></span> <span data-ttu-id="3d866-429">认证的设备保证能够在所有情况下正常工作。</span><span class="sxs-lookup"><span data-stu-id="3d866-429">The certified devices are guaranteed to work in all scenarios.</span></span> 

<span data-ttu-id="3d866-430">有关支持的 SBCs 的详细信息，请参阅[为直接路由认证的会话边框控制器列表](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="3d866-430">For more information about supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

 
## <a name="see-also"></a><span data-ttu-id="3d866-431">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d866-431">See also</span></span>

[<span data-ttu-id="3d866-432">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="3d866-432">Configure Direct Routing</span></span>](direct-routing-configure.md)
