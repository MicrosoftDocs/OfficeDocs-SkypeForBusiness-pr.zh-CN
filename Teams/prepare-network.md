---
title: 为 Microsoft Teams 准备贵组织的网络
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: arachman
description: 了解如何准备和管理你的 Microsoft Teams 网络。 信息包括网络要求、带宽要求和其他考虑事项。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2af8872253e2962322712a013cb3043a7da2d81b
ms.sourcegitcommit: c0679cbaf7df38769f722afd65c4232311d25515
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2019
ms.locfileid: "29562626"
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="cb213-104">为 Microsoft Teams 准备贵组织的网络</span><span class="sxs-lookup"><span data-stu-id="cb213-104">Prepare your organization's network for Microsoft Teams</span></span>
=================================================

> [!Tip]
> <span data-ttu-id="cb213-105">观看下面的会话，若要了解如何团队利用您的网络和如何最好地规划最佳的网络连接：[团队网络规划](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="cb213-105">Watch the following session to learn how to Teams leverages your network and how to best plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking)</span></span>


<span data-ttu-id="cb213-106">Teams 组合了三种形式的流量：</span><span class="sxs-lookup"><span data-stu-id="cb213-106">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="cb213-107">Office 365 联机环境与 Teams 客户端之间的数据流量（信号发送、联机状态、聊天、文件上载和下载、OneNote 同步）。</span><span class="sxs-lookup"><span data-stu-id="cb213-107">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="cb213-108">点对点实时通信流量（音频、视频、桌面共享）。</span><span class="sxs-lookup"><span data-stu-id="cb213-108">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="cb213-109">会议实时通信流量（音频、视频、桌面共享）。</span><span class="sxs-lookup"><span data-stu-id="cb213-109">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="cb213-110">这在两个级别上影响网络：对于点对点应用场景，流量在 Microsoft Teams 客户端之间直接传输；对于会议应用场景，流量在 Office 365 环境与 Microsoft Teams 客户端之间传输。</span><span class="sxs-lookup"><span data-stu-id="cb213-110">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios.</span></span> <span data-ttu-id="cb213-111">为了确保获得最佳通信流，必须允许在内部网络段（例如，WAN 上的站点）之间以及网络站点与 Office 365 之间传输流量。</span><span class="sxs-lookup"><span data-stu-id="cb213-111">To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365.</span></span> <span data-ttu-id="cb213-112">如果未打开正确的端口或主动阻止特定端口，将会导致降低体验。</span><span class="sxs-lookup"><span data-stu-id="cb213-112">Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="cb213-113">IOS 和 Android 移动设备上支持会议。</span><span class="sxs-lookup"><span data-stu-id="cb213-113">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="cb213-114">为了在 Microsoft Teams 中获得实时媒体方面的最佳体验，需要满足 Office 365 的网络连接要求。</span><span class="sxs-lookup"><span data-stu-id="cb213-114">To get an optimal experience with real time media within Microsoft Teams, it is required to meet the networking requirements for Office 365.</span></span> <span data-ttu-id="cb213-115">有关详细信息，请参阅 [Skype for Business Online 中的媒体质量和网络连接性能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)。</span><span class="sxs-lookup"><span data-stu-id="cb213-115">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="cb213-116">两个定义网络段 （客户端到 Microsoft 边缘） 和客户边缘到 Microsoft 边缘，请考虑以下建议。</span><span class="sxs-lookup"><span data-stu-id="cb213-116">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="cb213-117">值</span><span class="sxs-lookup"><span data-stu-id="cb213-117">Value</span></span>  |<span data-ttu-id="cb213-118">客户端到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="cb213-118">Client to Microsoft Edge</span></span>  |<span data-ttu-id="cb213-119">客户边缘到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="cb213-119">Customer Edge to Microsoft Edge</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="cb213-120">**延迟（单向）**</span><span class="sxs-lookup"><span data-stu-id="cb213-120">**Latency (one way)**</span></span>     |<span data-ttu-id="cb213-121">< 50 ms</span><span class="sxs-lookup"><span data-stu-id="cb213-121">< 50ms</span></span>          |<span data-ttu-id="cb213-122">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="cb213-122">< 30ms</span></span>          |
|<span data-ttu-id="cb213-123">**延迟（RTT 或往返时间）**</span><span class="sxs-lookup"><span data-stu-id="cb213-123">**Latency (RTT or Round-trip Time)**</span></span> |<span data-ttu-id="cb213-124">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="cb213-124">< 100ms</span></span>         |<span data-ttu-id="cb213-125">< 60 ms</span><span class="sxs-lookup"><span data-stu-id="cb213-125">< 60ms</span></span>         |
|<span data-ttu-id="cb213-126">**突发数据包丢失**</span><span class="sxs-lookup"><span data-stu-id="cb213-126">**Burst packet loss**</span></span>    |<span data-ttu-id="cb213-127">< 10%，在任何 200 ms 时间间隔内</span><span class="sxs-lookup"><span data-stu-id="cb213-127"><10% during any 200ms interval</span></span>         |<span data-ttu-id="cb213-128">< 1%，在任何 200 ms 时间间隔内</span><span class="sxs-lookup"><span data-stu-id="cb213-128"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="cb213-129">**数据包丢失**</span><span class="sxs-lookup"><span data-stu-id="cb213-129">**Packet loss**</span></span>     |<span data-ttu-id="cb213-130">< 1%，在任何 15 s 时间间隔内</span><span class="sxs-lookup"><span data-stu-id="cb213-130"><1% during any 15s interval</span></span>          |<span data-ttu-id="cb213-131">< 0.1%，在任何 15 s 时间间隔内</span><span class="sxs-lookup"><span data-stu-id="cb213-131"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="cb213-132">**数据包中间间隔抖动**</span><span class="sxs-lookup"><span data-stu-id="cb213-132">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="cb213-133">< 30 ms，在任何 15 s 时间间隔内</span><span class="sxs-lookup"><span data-stu-id="cb213-133"><30ms during any 15s interval</span></span>         |<span data-ttu-id="cb213-134">< 15 ms，在任何 15 s 时间间隔内</span><span class="sxs-lookup"><span data-stu-id="cb213-134"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="cb213-135">**数据包重新排序**</span><span class="sxs-lookup"><span data-stu-id="cb213-135">**Packet reorder**</span></span>    |<span data-ttu-id="cb213-136">< 0.05% 无序数据包</span><span class="sxs-lookup"><span data-stu-id="cb213-136"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="cb213-137">< 0.01% 无序数据包</span><span class="sxs-lookup"><span data-stu-id="cb213-137"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="cb213-138">要测试两个网段，你可以使用[网络评估工具](https://go.microsoft.com/fwlink/?linkid=855799)。</span><span class="sxs-lookup"><span data-stu-id="cb213-138">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="cb213-139">此工具可以直接部署在客户端 PC 上，也可以部署在连接到客户网络边缘的 PC 上。</span><span class="sxs-lookup"><span data-stu-id="cb213-139">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="cb213-140">此工具附带内容有限的文档，有关此工具用法的深度文档，请参阅此处：[网络就绪评估](https://go.microsoft.com/fwlink/?linkid=855800)。</span><span class="sxs-lookup"><span data-stu-id="cb213-140">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="cb213-141">通过进行此网络就绪评估，你可以验证你的网络是否为运行实时媒体应用（例如 Microsoft Teams）做好准备。</span><span class="sxs-lookup"><span data-stu-id="cb213-141">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="cb213-142">对于希望成功部署 Skype for Business 的客户，同样建议进行此网络就绪评估。</span><span class="sxs-lookup"><span data-stu-id="cb213-142">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>

<a name="bandwidth-requirements"></a><span data-ttu-id="cb213-143">带宽要求</span><span class="sxs-lookup"><span data-stu-id="cb213-143">Bandwidth requirements</span></span>
----------

<span data-ttu-id="cb213-144">Microsoft Teams 的带宽计算很复杂，因此为了帮助进行此计算，创建了一个计算器。</span><span class="sxs-lookup"><span data-stu-id="cb213-144">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created.</span></span> <span data-ttu-id="cb213-145">要访问计算器，请转到 [MyAdvisor 中的网络规划器](https://aka.ms/bwcalc/)。</span><span class="sxs-lookup"><span data-stu-id="cb213-145">To access the calculator, go to [Network Planner in MyAdvisor](https://aka.ms/bwcalc/).</span></span>

> [!NOTE]
> <span data-ttu-id="cb213-146">团队带宽处理改进了业务 online Skype： 对于呼叫或会议 （与音频、 视频和共享） 的体验，高质量，团队需要仅 1.2 Mbps。</span><span class="sxs-lookup"><span data-stu-id="cb213-146">Teams bandwidth handling improves on Skype for Business Online: for a high quality calling or meeting experience (with audio, video, and sharing), Teams requires only 1.2 Mbps.</span></span> <span data-ttu-id="cb213-147">它还可以扩展最多进一步的超级高质量，如果没有足够的可用带宽。</span><span class="sxs-lookup"><span data-stu-id="cb213-147">It can also scale up further for super high quality if there is enough available bandwidth.</span></span> <span data-ttu-id="cb213-148">当团队请求遇到低带宽条件时，团队可以快速重新调整带宽使用情况，以适应可用带宽。</span><span class="sxs-lookup"><span data-stu-id="cb213-148">When a Teams request encounters a low bandwidth condition, Teams can quickly readjust bandwidth usage to adapt to available bandwidth.</span></span>

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

<a name="additional-network-considerations"></a><span data-ttu-id="cb213-149">其他网络考虑事项</span><span class="sxs-lookup"><span data-stu-id="cb213-149">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="cb213-150">**外部名称解析**</span><span class="sxs-lookup"><span data-stu-id="cb213-150">**External Name Resolution**</span></span>

<span data-ttu-id="cb213-151">确保运行 Teams 客户端的所有客户端计算机都可以解析外部 DNS 查询以发现 Office 365 提供的服务。</span><span class="sxs-lookup"><span data-stu-id="cb213-151">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365.</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="cb213-152">**NAT 池大小**</span><span class="sxs-lookup"><span data-stu-id="cb213-152">**NAT Pool Size**</span></span>

<span data-ttu-id="cb213-153">多个用户/设备使用网络地址转换 (NAT) 或端口地址转换 (PAT) 访问 Office 365 时，你需要确保每个公开可路由 IP 地址后面隐藏的设备不超过支持的数量。</span><span class="sxs-lookup"><span data-stu-id="cb213-153">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="cb213-154">为了缓解此风险，请确保为 NAT 池分配足够的公用 IP 地址以防止端口耗尽。</span><span class="sxs-lookup"><span data-stu-id="cb213-154">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="cb213-155">端口耗尽会导致内部最终用户和设备在连接到 Office 365 服务时遇到问题。</span><span class="sxs-lookup"><span data-stu-id="cb213-155">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="cb213-156">有关详细信息，请参阅 [Office 365 的 NAT 支持](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)。</span><span class="sxs-lookup"><span data-stu-id="cb213-156">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="cb213-157">**入侵检测和防护指导**</span><span class="sxs-lookup"><span data-stu-id="cb213-157">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="cb213-158">如果你的环境部署了入侵检测和/或防护系统 (IDS/IPS)，从而为出站连接附加了一层安全性，请确保目标为 Office 365 URL 的任何流量都列入白名单。</span><span class="sxs-lookup"><span data-stu-id="cb213-158">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="cb213-159">网络运行状况确定</span><span class="sxs-lookup"><span data-stu-id="cb213-159">Network health determination</span></span>
-----------------

<span data-ttu-id="cb213-160">规划在你的网络中实施 Microsoft Teams 时，你必须确保有所需的带宽、有权访问所有所需的 IP 地址、打开了正确的端口且满足实时媒体的性能要求。</span><span class="sxs-lookup"><span data-stu-id="cb213-160">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="cb213-161">你应清楚，如果你无法满足这些条件，那么你的最终用户在使用 Teams 时由于在通话和会议过程中质量较差而无法获得最优体验。</span><span class="sxs-lookup"><span data-stu-id="cb213-161">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="cb213-162">如果你未满足这些条件，现在应考虑暂停项目，以确保先满足条件，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="cb213-162">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![决策点图标。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="cb213-164">决策点</span><span class="sxs-lookup"><span data-stu-id="cb213-164">Decision Point</span></span>         |<span data-ttu-id="cb213-165">你是否评估了用于支持实时媒体的网络功能？</span><span class="sxs-lookup"><span data-stu-id="cb213-165">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="cb213-166">如果未正确评估你的网络，或者你知道它将无法支持实时媒体，你是否将禁用视频和屏幕共享功能以降低网络影响和糟糕的 Teams 体验？</span><span class="sxs-lookup"><span data-stu-id="cb213-166">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![后续步骤图标。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="cb213-168">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cb213-168">Next Steps</span></span>         |<span data-ttu-id="cb213-169">网络质量未知：按照[网络就绪评估](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)指导来确定你的网络是否可以支持实时媒体。</span><span class="sxs-lookup"><span data-stu-id="cb213-169">Network Quality Unknown: Follow the [Network Readiness Assessment](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) guidance to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="cb213-170">网络质量较差：执行网络补救步骤以提供合适的环境来支持高质量的实时媒体。</span><span class="sxs-lookup"><span data-stu-id="cb213-170">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="cb213-171">网络满意：确保可以正确访问所有 IP 地址和端口。</span><span class="sxs-lookup"><span data-stu-id="cb213-171">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

