---
title: 为 Microsoft Teams 准备贵组织的网络
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
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
ms.openlocfilehash: 57f8ffc7d5cedeb6117deffb99ad48ccbe17b48f
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640727"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="39b59-104">为 Microsoft Teams 准备贵组织的网络</span><span class="sxs-lookup"><span data-stu-id="39b59-104">Prepare your organization's network for Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="39b59-105">观看下面的会话，若要了解如何团队利用您的网络和如何最好地规划最佳的网络连接：[团队网络规划](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="39b59-105">Watch the following session to learn how to Teams leverages your network and how to best plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking)</span></span>


<span data-ttu-id="39b59-106">团队结合使用三种形式的流量：</span><span class="sxs-lookup"><span data-stu-id="39b59-106">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="39b59-107">Office 365 联机环境和团队客户端 （信号、 状态、 聊天、 文件上载和下载、 OneNote 同步） 之间的数据通信。</span><span class="sxs-lookup"><span data-stu-id="39b59-107">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="39b59-108">对等实时通信 （音频、 视频、 桌面共享） 流量。</span><span class="sxs-lookup"><span data-stu-id="39b59-108">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="39b59-109">会议实时通信流量 （音频、 视频、 桌面共享）。</span><span class="sxs-lookup"><span data-stu-id="39b59-109">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="39b59-110">这会影响网络在两个级别： 通信将直接的对等方案中，在 Microsoft 团队客户端之间流动和通信将会议方案的流动的 Microsoft 团队客户端和 Office 365 环境之间。</span><span class="sxs-lookup"><span data-stu-id="39b59-110">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios.</span></span> <span data-ttu-id="39b59-111">若要确保最佳通信流，必须允许通讯以及为之间流动二者之间的内部网络段 （例如，通过 WAN 网站） 之间的网络站点和 Office 365。</span><span class="sxs-lookup"><span data-stu-id="39b59-111">To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365.</span></span> <span data-ttu-id="39b59-112">不打开了正确的端口或主动阻止特定端口将导致降级体验。</span><span class="sxs-lookup"><span data-stu-id="39b59-112">Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="39b59-113">IOS 和 Android 移动设备上支持会议。</span><span class="sxs-lookup"><span data-stu-id="39b59-113">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="39b59-114">若要获取的 Microsoft 团队中的实时媒体与获得最佳体验，您的网络必须满足 Office 365 的网络要求。</span><span class="sxs-lookup"><span data-stu-id="39b59-114">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="39b59-115">有关详细信息，请参阅[媒体质量和业务 online Skype 的网络连接性能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)。</span><span class="sxs-lookup"><span data-stu-id="39b59-115">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="39b59-116">两个定义网络段 （客户端到 Microsoft 边缘） 和客户边缘到 Microsoft 边缘，请考虑以下建议。</span><span class="sxs-lookup"><span data-stu-id="39b59-116">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="39b59-117">值</span><span class="sxs-lookup"><span data-stu-id="39b59-117">Value</span></span>  |<span data-ttu-id="39b59-118">客户端到 Microsoft 边缘</span><span class="sxs-lookup"><span data-stu-id="39b59-118">Client to Microsoft Edge</span></span>  |<span data-ttu-id="39b59-119">客户边缘到 Microsoft 边缘</span><span class="sxs-lookup"><span data-stu-id="39b59-119">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="39b59-120">**延迟 （一种方法）**\*</span><span class="sxs-lookup"><span data-stu-id="39b59-120">**Latency (one way)** \*</span></span>  |<span data-ttu-id="39b59-121">< 50 毫秒</span><span class="sxs-lookup"><span data-stu-id="39b59-121">< 50ms</span></span>          |<span data-ttu-id="39b59-122">< 30ms</span><span class="sxs-lookup"><span data-stu-id="39b59-122">< 30ms</span></span>         |
|<span data-ttu-id="39b59-123">**延迟 （RTT 或往返时间）**\*</span><span class="sxs-lookup"><span data-stu-id="39b59-123">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="39b59-124">< 为 100 毫秒</span><span class="sxs-lookup"><span data-stu-id="39b59-124">< 100ms</span></span>   |<span data-ttu-id="39b59-125">< 为 60 毫秒</span><span class="sxs-lookup"><span data-stu-id="39b59-125">< 60ms</span></span> |
|<span data-ttu-id="39b59-126">**突发数据包丢失**</span><span class="sxs-lookup"><span data-stu-id="39b59-126">**Burst packet loss**</span></span>    |<span data-ttu-id="39b59-127">任何为 200 毫秒间隔期间 <10%</span><span class="sxs-lookup"><span data-stu-id="39b59-127"><10% during any 200ms interval</span></span>         |<span data-ttu-id="39b59-128">任何为 200 毫秒间隔期间 <1%</span><span class="sxs-lookup"><span data-stu-id="39b59-128"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="39b59-129">**数据包丢失**</span><span class="sxs-lookup"><span data-stu-id="39b59-129">**Packet loss**</span></span>     |<span data-ttu-id="39b59-130"><1%期间任何 15 秒间隔</span><span class="sxs-lookup"><span data-stu-id="39b59-130"><1% during any 15s interval</span></span>          |<span data-ttu-id="39b59-131"><0.1%期间任何 15 秒间隔</span><span class="sxs-lookup"><span data-stu-id="39b59-131"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="39b59-132">**数据包间到达抖动**</span><span class="sxs-lookup"><span data-stu-id="39b59-132">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="39b59-133"><30ms 期间任何 15 秒间隔</span><span class="sxs-lookup"><span data-stu-id="39b59-133"><30ms during any 15s interval</span></span>         |<span data-ttu-id="39b59-134"><15ms 期间任何 15 秒间隔</span><span class="sxs-lookup"><span data-stu-id="39b59-134"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="39b59-135">**数据包重新排序**</span><span class="sxs-lookup"><span data-stu-id="39b59-135">**Packet reorder**</span></span>    |<span data-ttu-id="39b59-136"><0.05%序的数据包</span><span class="sxs-lookup"><span data-stu-id="39b59-136"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="39b59-137"><0.01%序的数据包</span><span class="sxs-lookup"><span data-stu-id="39b59-137"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="39b59-138">\*延迟指标目标假定您的公司网站和 Microsoft 边缘位于同一洲。</span><span class="sxs-lookup"><span data-stu-id="39b59-138">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="39b59-139">公司网站连接到 Microsoft 网络边缘包含第一个跃点网络访问，可以是 WiFi 或其他无线技术。</span><span class="sxs-lookup"><span data-stu-id="39b59-139">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="39b59-140">网络性能目标假定适当的带宽和/或[QoS 规划](QoS-in-Teams.md)。</span><span class="sxs-lookup"><span data-stu-id="39b59-140">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="39b59-141">换句话说的要求适用于团队实时的媒体流量直接峰值负载下的网络连接时。</span><span class="sxs-lookup"><span data-stu-id="39b59-141">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="39b59-142">若要测试两个网络段，您可以使用[网络评估工具](https://go.microsoft.com/fwlink/?linkid=855799)。</span><span class="sxs-lookup"><span data-stu-id="39b59-142">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="39b59-143">此工具可以部署这两个客户端上 PC 直接并连接到客户网络边缘 PC 上。</span><span class="sxs-lookup"><span data-stu-id="39b59-143">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="39b59-144">该工具包含有限的文档，但围绕使用率的工具更深入地介绍文档可在此处找到：[网络准备情况评估](https://go.microsoft.com/fwlink/?linkid=855800)。</span><span class="sxs-lookup"><span data-stu-id="39b59-144">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="39b59-145">通过运行此网络准备情况评估，您可以验证您的网络准备运行实时的媒体的应用程序，如 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="39b59-145">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="39b59-146">这是建议的客户希望成功部署 for Business 的 Skype 运行相同的网络准备情况评估。</span><span class="sxs-lookup"><span data-stu-id="39b59-146">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="39b59-147">带宽要求</span><span class="sxs-lookup"><span data-stu-id="39b59-147">Bandwidth requirements</span></span>

<span data-ttu-id="39b59-148">Microsoft 团队的带宽计算很复杂，为了与此，具有创建一个计算器。</span><span class="sxs-lookup"><span data-stu-id="39b59-148">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created.</span></span> <span data-ttu-id="39b59-149">若要访问计算器，转到[网络规划人员](https://aka.ms/bwcalc/)MyAdvisor 中。</span><span class="sxs-lookup"><span data-stu-id="39b59-149">To access the calculator, go to [Network Planner](https://aka.ms/bwcalc/)  in MyAdvisor.</span></span>

> [!NOTE]
> <span data-ttu-id="39b59-150">团队带宽处理改进了业务 online Skype： 对于呼叫或会议 （与音频、 视频和共享） 的体验，高质量，团队需要仅 1.2 Mbps。</span><span class="sxs-lookup"><span data-stu-id="39b59-150">Teams bandwidth handling improves on Skype for Business Online: for a high quality calling or meeting experience (with audio, video, and sharing), Teams requires only 1.2 Mbps.</span></span> <span data-ttu-id="39b59-151">它还可以扩展最多进一步的超级高质量，如果没有足够的可用带宽。</span><span class="sxs-lookup"><span data-stu-id="39b59-151">It can also scale up further for super high quality if there is enough available bandwidth.</span></span> <span data-ttu-id="39b59-152">当团队请求遇到低带宽条件时，团队可以快速重新调整带宽使用情况，以适应可用带宽。</span><span class="sxs-lookup"><span data-stu-id="39b59-152">When a Teams request encounters a low bandwidth condition, Teams can quickly readjust bandwidth usage to adapt to available bandwidth.</span></span>

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

<a name="additional-network-considerations"></a><span data-ttu-id="39b59-153">其他网络注意事项</span><span class="sxs-lookup"><span data-stu-id="39b59-153">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="39b59-154">外部名称解析</span><span class="sxs-lookup"><span data-stu-id="39b59-154">External Name Resolution</span></span>

<span data-ttu-id="39b59-155">确保运行团队客户端的所有客户端计算机可以解析发现 Office 365 提供的服务的外部 DNS 查询，并且，您的防火墙不会阻止访问。</span><span class="sxs-lookup"><span data-stu-id="39b59-155">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="39b59-156">有关配置防火墙端口的信息，请转到[Office 365 Url 和 IP 范围](office-365-urls-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="39b59-156">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="39b59-157">NAT 池大小</span><span class="sxs-lookup"><span data-stu-id="39b59-157">NAT Pool Size</span></span>

<span data-ttu-id="39b59-158">当多个用户/设备访问 Office 365 使用网络地址转换 (NAT) 或端口地址转换 (PAT) 时，您需要确保隐藏在每个公共可路由的 IP 地址的设备不能超过支持的数目。</span><span class="sxs-lookup"><span data-stu-id="39b59-158">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="39b59-159">若要减轻此风险，请确保足够公共 IP 地址将分配给 NAT 池以防止端口耗尽。</span><span class="sxs-lookup"><span data-stu-id="39b59-159">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="39b59-160">端口耗尽会导致内部最终用户和设备连接到 Office 365 服务时面临的问题。</span><span class="sxs-lookup"><span data-stu-id="39b59-160">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="39b59-161">有关详细信息，请参阅[Office 365 的 NAT 支持](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)。</span><span class="sxs-lookup"><span data-stu-id="39b59-161">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="39b59-162">**入侵检测和防护指南**</span><span class="sxs-lookup"><span data-stu-id="39b59-162">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="39b59-163">如果您的环境的入侵检测和/或防护系统 (ID/IP) 部署额外的安全的出站连接，请确保目标为 Office 365 Url 与任何通信白名单。</span><span class="sxs-lookup"><span data-stu-id="39b59-163">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="39b59-164">网络运行状况确定</span><span class="sxs-lookup"><span data-stu-id="39b59-164">Network health determination</span></span>
-----------------

<span data-ttu-id="39b59-165">在您的网络内的 Microsoft 团队实现规划时，您必须确保您具有所需的带宽、 您有权访问所有必需 IP 地址，打开了正确的端口和您会议实时的媒体的性能要求.</span><span class="sxs-lookup"><span data-stu-id="39b59-165">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="39b59-166">如果您知道您将不符合这些条件，您的最终用户将不获得最佳体验团队由于错误质量呼叫和会议过程中。</span><span class="sxs-lookup"><span data-stu-id="39b59-166">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="39b59-167">您应不满足这些条件，这是要考虑暂停项目来确保在继续之前满足条件的时间。</span><span class="sxs-lookup"><span data-stu-id="39b59-167">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![决策点图标。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="39b59-169">决策点</span><span class="sxs-lookup"><span data-stu-id="39b59-169">Decision Point</span></span>         |<span data-ttu-id="39b59-170">您已经评估支持实时媒体您网络功能？</span><span class="sxs-lookup"><span data-stu-id="39b59-170">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="39b59-171">如果您的网络未正确评估，或您知道它将不支持实时媒体，您将禁用视频和屏幕共享功能，以减少网络影响和差团队体验？</span><span class="sxs-lookup"><span data-stu-id="39b59-171">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![后续步骤图标。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="39b59-173">后续步骤</span><span class="sxs-lookup"><span data-stu-id="39b59-173">Next Steps</span></span>         |<span data-ttu-id="39b59-174">网络质量未知： 按照[网络准备情况评估](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)指导来确定您的网络是否准备好让实时媒体。</span><span class="sxs-lookup"><span data-stu-id="39b59-174">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="39b59-175">网络质量差： 执行网络补救步骤，以提供高质量实时媒体的适当环境。</span><span class="sxs-lookup"><span data-stu-id="39b59-175">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="39b59-176">网络满意： 确保所有 IP 地址和端口都都正确可访问。</span><span class="sxs-lookup"><span data-stu-id="39b59-176">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="39b59-177">相关主题</span><span class="sxs-lookup"><span data-stu-id="39b59-177">Related Topics</span></span>

[<span data-ttu-id="39b59-178">视频： 网络规划</span><span class="sxs-lookup"><span data-stu-id="39b59-178">Video: Network Planning</span></span>](https://aka.ms/teams-networking)