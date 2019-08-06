---
title: 为 Microsoft Teams 准备贵组织的网络
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/25/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
description: 了解如何准备和管理你的 Microsoft Teams 网络。 信息包括网络要求、带宽要求和其他考虑事项。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 041c391f202ac42b782ffc200db9ad495961fa52
ms.sourcegitcommit: a49caec01ff724475d6670b303d851ddd8266c2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2019
ms.locfileid: "36206954"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="a5c18-104">为 Microsoft Teams 准备贵组织的网络</span><span class="sxs-lookup"><span data-stu-id="a5c18-104">Prepare your organization's network for Microsoft Teams</span></span>


<span data-ttu-id="a5c18-105">Teams 组合了三种形式的流量：</span><span class="sxs-lookup"><span data-stu-id="a5c18-105">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="a5c18-106">Office 365 联机环境与 Teams 客户端之间的数据流量（信号发送、联机状态、聊天、文件上载和下载、OneNote 同步）。</span><span class="sxs-lookup"><span data-stu-id="a5c18-106">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="a5c18-107">点对点实时通信流量（音频、视频、桌面共享）。</span><span class="sxs-lookup"><span data-stu-id="a5c18-107">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="a5c18-108">会议实时通信流量（音频、视频、桌面共享）。</span><span class="sxs-lookup"><span data-stu-id="a5c18-108">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="a5c18-109">这在两个级别上影响网络：对于点对点应用场景，流量在 Microsoft Teams 客户端之间直接传输；对于会议应用场景，流量在 Office 365 环境与 Microsoft Teams 客户端之间传输。</span><span class="sxs-lookup"><span data-stu-id="a5c18-109">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios.</span></span> <span data-ttu-id="a5c18-110">为了确保获得最佳通信流，必须允许在内部网络段（例如，WAN 上的站点）之间以及网络站点与 Office 365 之间传输流量。</span><span class="sxs-lookup"><span data-stu-id="a5c18-110">To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365.</span></span> <span data-ttu-id="a5c18-111">如果未打开正确的端口或主动阻止特定端口，将会导致降低体验。</span><span class="sxs-lookup"><span data-stu-id="a5c18-111">Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="a5c18-112">在 iOS 和 Android 移动设备上支持会议。</span><span class="sxs-lookup"><span data-stu-id="a5c18-112">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="a5c18-113">要在 Microsoft 团队内获得实时媒体的最佳体验, 你的网络必须满足 Office 365 的网络要求。</span><span class="sxs-lookup"><span data-stu-id="a5c18-113">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="a5c18-114">有关详细信息，请参阅 [Skype for Business Online 的媒体质量和网络连接性能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)。</span><span class="sxs-lookup"><span data-stu-id="a5c18-114">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="a5c18-115">对于两个定义网络段（客户端到 Microsoft Edge 和客户边缘到 Microsoft Edge），请考虑以下建议：</span><span class="sxs-lookup"><span data-stu-id="a5c18-115">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="a5c18-116">值</span><span class="sxs-lookup"><span data-stu-id="a5c18-116">Value</span></span>  |<span data-ttu-id="a5c18-117">客户端到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a5c18-117">Client to Microsoft Edge</span></span>  |<span data-ttu-id="a5c18-118">客户边缘到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a5c18-118">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="a5c18-119">**延迟 (一种方法)**\*</span><span class="sxs-lookup"><span data-stu-id="a5c18-119">**Latency (one way)** \*</span></span>  |<span data-ttu-id="a5c18-120">< 50 ms</span><span class="sxs-lookup"><span data-stu-id="a5c18-120">< 50ms</span></span>          |<span data-ttu-id="a5c18-121">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="a5c18-121">< 30ms</span></span>         |
|<span data-ttu-id="a5c18-122">**延迟 (RTT 或往返时间)**\*</span><span class="sxs-lookup"><span data-stu-id="a5c18-122">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="a5c18-123">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="a5c18-123">< 100ms</span></span>   |<span data-ttu-id="a5c18-124">< 60 ms</span><span class="sxs-lookup"><span data-stu-id="a5c18-124">< 60ms</span></span> |
|<span data-ttu-id="a5c18-125">**突发数据包丢失**</span><span class="sxs-lookup"><span data-stu-id="a5c18-125">**Burst packet loss**</span></span>    |<span data-ttu-id="a5c18-126">< 10%，在任何 200 ms 时间间隔内</span><span class="sxs-lookup"><span data-stu-id="a5c18-126"><10% during any 200ms interval</span></span>         |<span data-ttu-id="a5c18-127">< 1%，在任何 200 ms 时间间隔内</span><span class="sxs-lookup"><span data-stu-id="a5c18-127"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="a5c18-128">**数据包丢失**</span><span class="sxs-lookup"><span data-stu-id="a5c18-128">**Packet loss**</span></span>     |<span data-ttu-id="a5c18-129">< 1%，在任何 15 s 时间间隔内</span><span class="sxs-lookup"><span data-stu-id="a5c18-129"><1% during any 15s interval</span></span>          |<span data-ttu-id="a5c18-130">< 0.1%，在任何 15 s 时间间隔内</span><span class="sxs-lookup"><span data-stu-id="a5c18-130"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="a5c18-131">**数据包中间间隔抖动**</span><span class="sxs-lookup"><span data-stu-id="a5c18-131">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="a5c18-132">< 30 ms，在任何 15 s 时间间隔内</span><span class="sxs-lookup"><span data-stu-id="a5c18-132"><30ms during any 15s interval</span></span>         |<span data-ttu-id="a5c18-133">< 15 ms，在任何 15 s 时间间隔内</span><span class="sxs-lookup"><span data-stu-id="a5c18-133"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="a5c18-134">**数据包重新排序**</span><span class="sxs-lookup"><span data-stu-id="a5c18-134">**Packet reorder**</span></span>    |<span data-ttu-id="a5c18-135">< 0.05% 无序数据包</span><span class="sxs-lookup"><span data-stu-id="a5c18-135"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="a5c18-136">< 0.01% 无序数据包</span><span class="sxs-lookup"><span data-stu-id="a5c18-136"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="a5c18-137">\*延迟指标目标假设您的公司网站或网站, Microsoft 边缘位于同一大陆。</span><span class="sxs-lookup"><span data-stu-id="a5c18-137">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="a5c18-138">您的公司网站与 Microsoft 网络 edge 的连接包括第一跃点网络访问权限, 可以是 WiFi 或其他无线技术。</span><span class="sxs-lookup"><span data-stu-id="a5c18-138">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="a5c18-139">网络性能目标采用正确的带宽和/或[QoS 规划](QoS-in-Teams.md)。</span><span class="sxs-lookup"><span data-stu-id="a5c18-139">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="a5c18-140">换句话说, 当网络连接处于峰值负载时, 要求直接适用于团队实时媒体流量。</span><span class="sxs-lookup"><span data-stu-id="a5c18-140">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="a5c18-141">有关为团队准备网络的更多帮助, 请查看[网络 Planner](https://docs.microsoft.com/microsoftteams/network-planner)。</span><span class="sxs-lookup"><span data-stu-id="a5c18-141">For more help with preparing your network for Teams, check out [Network Planner](https://docs.microsoft.com/microsoftteams/network-planner).</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="a5c18-142">带宽要求</span><span class="sxs-lookup"><span data-stu-id="a5c18-142">Bandwidth requirements</span></span>
<span data-ttu-id="a5c18-143">无论您的网络状况如何, Microsoft 团队可为您提供最佳的音频、视频和内容共享体验。</span><span class="sxs-lookup"><span data-stu-id="a5c18-143">Microsoft Teams gives you the best audio, video and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="a5c18-144">通过可变编解码器, 可以在有限的带宽环境中协商媒体, 影响最小。</span><span class="sxs-lookup"><span data-stu-id="a5c18-144">With variable codecs, media can be negotiated in limited bandwidth environments with minimal impact.</span></span> <span data-ttu-id="a5c18-145">但是, 带宽不是个问题, 可以针对质量优化体验, 包括最高分辨率的视频分辨率、最多30fps 视频和15fps 内容以及高保真音频。</span><span class="sxs-lookup"><span data-stu-id="a5c18-145">But where bandwidth is not a concern, experiences can be optimized for quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span>

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]


<!--
The content you will find below can be used as supplemental background information; however, it is recommended that customers use [Network Planner](https://aka.ms/bwcalc) to track their needs.

> [!IMPORTANT]
>If the required bandwidth is not available, the media stack inside Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.


|Activity  |Download Bandwidth  |Upload Bandwidth  |Traffic Flow |
|---------|---------|---------|---------|
|**Peer to peer Audio Call**     |0.1 Mb         |0.1Mb         |Client <> Client         |
|**Peer to peer Video Call (full screen)**     |4 Mb         |4Mb         |Client <> Client          |
|**Peer to peer Desktop Sharing (1920*1080 resolution)**     |4 Mb         |4 Mb         |Client <> Client          |
|**2 Participant Meeting**     |4 Mb         |4 Mb         |Client <> Office 365         |
|**3 participant meeting**     |8 Mb         |6.5 Mb         |Client <> Office 365           |
|**4 participant meeting**     |5.5 Mb         |4 Mb         |Client <> Office 365           |
|**5 participant+ meeting**     |6 Mb         |1.5 Mb         |Client <> Office 365           |
-->

<a name="additional-network-considerations"></a><span data-ttu-id="a5c18-146">其他网络注意事项</span><span class="sxs-lookup"><span data-stu-id="a5c18-146">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="a5c18-147">外部名称解析</span><span class="sxs-lookup"><span data-stu-id="a5c18-147">External Name Resolution</span></span>

<span data-ttu-id="a5c18-148">确保运行团队客户端的所有客户端计算机可以解析外部 DNS 查询以发现 Office 365 提供的服务, 并且你的防火墙不会阻止访问。</span><span class="sxs-lookup"><span data-stu-id="a5c18-148">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="a5c18-149">有关配置防火墙端口的信息, 请转到[Office 365 url 和 IP 范围](office-365-urls-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="a5c18-149">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="a5c18-150">NAT 池大小</span><span class="sxs-lookup"><span data-stu-id="a5c18-150">NAT Pool Size</span></span>

<span data-ttu-id="a5c18-151">当多个用户/设备使用网络地址转换 (NAT) 或端口地址转换 (PAT) 访问 Office 365 时, 您需要确保隐藏在每个可访问的 IP 地址后面的设备不会超过支持的号码。</span><span class="sxs-lookup"><span data-stu-id="a5c18-151">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="a5c18-152">若要降低此风险, 请确保为 NAT 池分配足够的公共 IP 地址以防止端口耗尽。</span><span class="sxs-lookup"><span data-stu-id="a5c18-152">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="a5c18-153">当连接到 Office 365 服务时, 端口耗尽将导致内部最终用户和设备面临问题。</span><span class="sxs-lookup"><span data-stu-id="a5c18-153">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="a5c18-154">有关详细信息, 请参阅[Office 365 的 NAT 支持](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)。</span><span class="sxs-lookup"><span data-stu-id="a5c18-154">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="a5c18-155">**入侵检测和阻止指南**</span><span class="sxs-lookup"><span data-stu-id="a5c18-155">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="a5c18-156">如果你的环境具有针对出站连接的额外安全层而部署的入侵检测和/或防护系统 (IDS/IPS), 请确保将包含目标到 Office 365 Url 的任何流量列入白名单。</span><span class="sxs-lookup"><span data-stu-id="a5c18-156">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="a5c18-157">网络运行状况确定</span><span class="sxs-lookup"><span data-stu-id="a5c18-157">Network health determination</span></span>
-----------------

<span data-ttu-id="a5c18-158">当规划网络中 Microsoft 团队的实现时, 必须确保你拥有所需的带宽, 你可以访问所有所需的 IP 地址、正确的端口, 并且你可以满足实时媒体的性能要求.</span><span class="sxs-lookup"><span data-stu-id="a5c18-158">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="a5c18-159">如果您不能满足这些条件, 最终用户将不会因在通话和会议期间出现不良质量而从团队获得最佳体验。</span><span class="sxs-lookup"><span data-stu-id="a5c18-159">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="a5c18-160">如果您不满足这些条件, 则需要考虑暂停项目以确保满足条件, 然后再继续。</span><span class="sxs-lookup"><span data-stu-id="a5c18-160">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![表示决策点的图标](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="a5c18-162">决策点</span><span class="sxs-lookup"><span data-stu-id="a5c18-162">Decision Point</span></span>         |<span data-ttu-id="a5c18-163">您是否对支持实时媒体的网络功能进行了评估？</span><span class="sxs-lookup"><span data-stu-id="a5c18-163">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="a5c18-164">如果您的网络未正确评估, 或者您知道它不支持实时媒体, 您是否将禁用视频和屏幕共享功能来减少网络影响和不良团队体验？</span><span class="sxs-lookup"><span data-stu-id="a5c18-164">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![表示后续步骤的图标](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="a5c18-166">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a5c18-166">Next Steps</span></span>         |<span data-ttu-id="a5c18-167">网络质量未知: 执行网络准备情况评估以确定网络是否已准备好使用实时媒体。</span><span class="sxs-lookup"><span data-stu-id="a5c18-167">Network Quality Unknown: Perform a Network Readiness Assessment to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="a5c18-168">网络质量差: 执行网络修复步骤, 为高质量实时媒体提供合适的环境。</span><span class="sxs-lookup"><span data-stu-id="a5c18-168">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="a5c18-169">网络满意: 确保所有 IP 地址和端口均可正确访问。</span><span class="sxs-lookup"><span data-stu-id="a5c18-169">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="a5c18-170">相关主题</span><span class="sxs-lookup"><span data-stu-id="a5c18-170">Related Topics</span></span>

[<span data-ttu-id="a5c18-171">视频: 网络规划</span><span class="sxs-lookup"><span data-stu-id="a5c18-171">Video: Network Planning</span></span>](https://aka.ms/teams-networking)
