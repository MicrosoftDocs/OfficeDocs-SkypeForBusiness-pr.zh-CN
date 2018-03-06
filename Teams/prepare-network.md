---
title: "为 Microsoft Teams 准备贵组织的网络"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: arachman
description: "了解如何准备和管理你的 Microsoft Teams 网络。 信息包括网络要求、带宽要求和其他考虑事项。"
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0528d958f7e7f8f06f4dbfb1e38b297577436c56
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="c68cb-104">为 Microsoft Teams 准备贵组织的网络</span><span class="sxs-lookup"><span data-stu-id="c68cb-104">Prepare your organization's network for Microsoft Teams</span></span>
=================================================

<span data-ttu-id="c68cb-105">Teams 组合了三种形式的流量：</span><span class="sxs-lookup"><span data-stu-id="c68cb-105">Microsoft Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="c68cb-106">Office 365 联机环境与 Teams 客户端之间的数据流量（信号发送、联机状态、聊天、文件上载和下载、OneNote 同步）。</span><span class="sxs-lookup"><span data-stu-id="c68cb-106">Data traffic between the Office 365 online environment and the Microsoft Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="c68cb-107">点对点实时通信流量（音频、视频、桌面共享）。</span><span class="sxs-lookup"><span data-stu-id="c68cb-107">Conferencing real time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="c68cb-108">会议实时通信流量（音频、视频、桌面共享）。</span><span class="sxs-lookup"><span data-stu-id="c68cb-108">Conferencing real time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="c68cb-109">这在两个级别上影响网络：对于点对点应用场景，流量在 Teams 客户端之间直接传输；对于会议应用场景，流量在 Office 365 环境与 Teams 客户端之间传输。</span><span class="sxs-lookup"><span data-stu-id="c68cb-109">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer to peer and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios.</span></span> <span data-ttu-id="c68cb-110">为了确保获得最佳通信流，必须允许在内部网络段（例如，WAN 上的站点）之间以及网络站点与 Office 365 之间传输流量。</span><span class="sxs-lookup"><span data-stu-id="c68cb-110">To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example between sites over the WAN) as well as between the network sites and Office 365.</span></span> <span data-ttu-id="c68cb-111">如果未打开正确的端口或主动阻止特定端口，将会导致降低体验。</span><span class="sxs-lookup"><span data-stu-id="c68cb-111">Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="c68cb-112">当前，在 iOS 和 Android 移动设备上支持会议，但在 Windows Phone 上不支持。</span><span class="sxs-lookup"><span data-stu-id="c68cb-112">Currently, meetings are supported on iOS and Android mobile devices, but not on Windows Phone (support for Windows Phone is coming soon).</span></span>

<span data-ttu-id="c68cb-113">为了在 Teams 中获得实时媒体方面的最佳体验，需要满足 Office 365 的网络连接要求（有关更多详细信息，请参阅以下原始资料：[Skype for Business Online 的媒体质量和网络连接性能](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)）</span><span class="sxs-lookup"><span data-stu-id="c68cb-113">To get an optimal experience with real time media within Microsoft Teams, it is required to meet the Networking Requirements for Office 365 (please see the following source for more details: [Media Quality and Network Connectivity Performance for Skype for Business Online](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917) )</span></span> 

<span data-ttu-id="c68cb-114">两个定义网络段（客户端到 Microsoft Edge 和客户边缘到 Microsoft Edge）必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="c68cb-114">The two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge) must met the following requirements:</span></span>


|<span data-ttu-id="c68cb-115">值</span><span class="sxs-lookup"><span data-stu-id="c68cb-115">Value</span></span>  |<span data-ttu-id="c68cb-116">客户端到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c68cb-116">Client to Microsoft Edge</span></span>  |<span data-ttu-id="c68cb-117">客户边缘到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c68cb-117">Customer Edge to Microsoft Edge</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="c68cb-118">**延迟（单向）**</span><span class="sxs-lookup"><span data-stu-id="c68cb-118">**Latency (one way)**</span></span>     |<span data-ttu-id="c68cb-119">< 50 ms</span><span class="sxs-lookup"><span data-stu-id="c68cb-119">< 50ms</span></span>          |<span data-ttu-id="c68cb-120">< 30 ms</span><span class="sxs-lookup"><span data-stu-id="c68cb-120">< 30ms</span></span>          |
|<span data-ttu-id="c68cb-121">**延迟（RTT 或往返时间）**</span><span class="sxs-lookup"><span data-stu-id="c68cb-121">**Latency (RTT or Round-trip Time)**</span></span> |<span data-ttu-id="c68cb-122">< 100 ms</span><span class="sxs-lookup"><span data-stu-id="c68cb-122">< 100ms</span></span>         |<span data-ttu-id="c68cb-123">< 60 ms</span><span class="sxs-lookup"><span data-stu-id="c68cb-123">< 60ms</span></span>         |
|<span data-ttu-id="c68cb-124">**突发数据包丢失**</span><span class="sxs-lookup"><span data-stu-id="c68cb-124">**Burst packet loss**</span></span>    |<span data-ttu-id="c68cb-125">< 10%，在任何 200 ms 时间间隔内</span><span class="sxs-lookup"><span data-stu-id="c68cb-125"><10% during any 200ms interval</span></span>         |<span data-ttu-id="c68cb-126">< 1%，在任何 200 ms 时间间隔内</span><span class="sxs-lookup"><span data-stu-id="c68cb-126"><1% during any 200 ms interval</span></span>         |
|<span data-ttu-id="c68cb-127">**数据包丢失**</span><span class="sxs-lookup"><span data-stu-id="c68cb-127">**Packet loss**</span></span>     |<span data-ttu-id="c68cb-128">< 1%，在任何 15 s 时间间隔内</span><span class="sxs-lookup"><span data-stu-id="c68cb-128"><1% during any 15s interval</span></span>          |<span data-ttu-id="c68cb-129">< 0.1%，在任何 15 s 时间间隔内</span><span class="sxs-lookup"><span data-stu-id="c68cb-129"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="c68cb-130">**数据包中间间隔抖动**</span><span class="sxs-lookup"><span data-stu-id="c68cb-130">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="c68cb-131">< 30 ms，在任何 15 s 时间间隔内</span><span class="sxs-lookup"><span data-stu-id="c68cb-131"><30ms during any 15s interval</span></span>         |<span data-ttu-id="c68cb-132">< 15 ms，在任何 15 s 时间间隔内</span><span class="sxs-lookup"><span data-stu-id="c68cb-132"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="c68cb-133">**数据包重新排序**</span><span class="sxs-lookup"><span data-stu-id="c68cb-133">**Packet reorder**</span></span>    |<span data-ttu-id="c68cb-134">< 0.05% 无序数据包</span><span class="sxs-lookup"><span data-stu-id="c68cb-134"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="c68cb-135">< 0.01% 无序数据包</span><span class="sxs-lookup"><span data-stu-id="c68cb-135"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="c68cb-136">要测试两个网段，你可以下载[网络评估工具](https://go.microsoft.com/fwlink/?linkid=855799)。</span><span class="sxs-lookup"><span data-stu-id="c68cb-136">To test both network segments, you can download the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="c68cb-137">此工具可以直接部署在客户端 PC 上，也可以部署在连接到客户网络边缘的 PC 上。</span><span class="sxs-lookup"><span data-stu-id="c68cb-137">This tool can be deployed on both the client PC directly, as well as a PC/laptop connected to the Customer Network Edge.</span></span> <span data-ttu-id="c68cb-138">此工具包含的文档有限，因此请不要错过下载随附的扩展文档。</span><span class="sxs-lookup"><span data-stu-id="c68cb-138">The tool includes limited documentation, so don't miss the extensive documentation included with the download.</span></span> <span data-ttu-id="c68cb-139">通过进行此网络就绪评估，你可以验证你的网络是否已为运行实时媒体应用程序（例如 Teams）做好准备。</span><span class="sxs-lookup"><span data-stu-id="c68cb-139">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>



> [!NOTE]
> <span data-ttu-id="c68cb-140">对于希望成功部署 Skype for Business 的客户，同样建议进行此网络就绪评估。</span><span class="sxs-lookup"><span data-stu-id="c68cb-140">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>

<a name="bandwidth-requirements"></a><span data-ttu-id="c68cb-141">带宽要求</span><span class="sxs-lookup"><span data-stu-id="c68cb-141">Bandwidth requirements</span></span>
----------

<span data-ttu-id="c68cb-142">Teams 的带宽计算很复杂，因此为了帮助进行此计算，创建了一个计算器。</span><span class="sxs-lookup"><span data-stu-id="c68cb-142">Bandwidth calculations for Microsoft Teams are complex and to help with this, a calculator has been created.</span></span> <span data-ttu-id="c68cb-143">要访问该计算器，请访问：<http://aka.ms/bwcalc>。</span><span class="sxs-lookup"><span data-stu-id="c68cb-143">To access the calculator, go here: <http://aka.ms/bwcalc/>.</span></span>

<span data-ttu-id="c68cb-144">下文内容可以用作补充背景信息，但建议客户使用[带宽计算器](https://aka.ms/bwcalc)来跟踪其需求。</span><span class="sxs-lookup"><span data-stu-id="c68cb-144">The content you will find below can be used as supplemental background information, however it is recommended that customers use the [Bandwidth Calculator](https://aka.ms/bwcalc) to track their needs.</span></span>



> [!IMPORTANT]
><span data-ttu-id="c68cb-145">如果未提供所需的带宽，Teams 中的媒体堆栈将降低音频/视频会话的质量以适应较低的可用带宽，因而会影响通话/会议的质量。</span><span class="sxs-lookup"><span data-stu-id="c68cb-145">If the required bandwidth is not available, the media stack inside Microsoft Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting.</span></span> <span data-ttu-id="c68cb-146">Teams 客户端在处理音频质量和视频质量时将尝试优先考虑音频质量。</span><span class="sxs-lookup"><span data-stu-id="c68cb-146">The Microsoft Teams client will attempt to prioritize the quality of audio over the quality of video.</span></span> <span data-ttu-id="c68cb-147">因此，提供所需带宽非常重要。</span><span class="sxs-lookup"><span data-stu-id="c68cb-147">It is therefore extremely important to have the expected bandwidth available.</span></span>


|<span data-ttu-id="c68cb-148">活动</span><span class="sxs-lookup"><span data-stu-id="c68cb-148">Activity</span></span>  |<span data-ttu-id="c68cb-149">下载带宽</span><span class="sxs-lookup"><span data-stu-id="c68cb-149">Download Bandwidth</span></span>  |<span data-ttu-id="c68cb-150">上载带宽</span><span class="sxs-lookup"><span data-stu-id="c68cb-150">Upload Bandwidth</span></span>  |<span data-ttu-id="c68cb-151">通信流</span><span class="sxs-lookup"><span data-stu-id="c68cb-151">Traffic Flow</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="c68cb-152">**点对点音频通话**</span><span class="sxs-lookup"><span data-stu-id="c68cb-152">**Peer to peer Audio Call**</span></span>     |<span data-ttu-id="c68cb-153">0.1 Mb</span><span class="sxs-lookup"><span data-stu-id="c68cb-153">0.1 Mb</span></span>         |<span data-ttu-id="c68cb-154">0.1 Mb</span><span class="sxs-lookup"><span data-stu-id="c68cb-154">0.1Mb</span></span>         |<span data-ttu-id="c68cb-155">客户端 <> 客户端</span><span class="sxs-lookup"><span data-stu-id="c68cb-155">Client <> Client</span></span>         |
|<span data-ttu-id="c68cb-156">**点对点视频通话（全屏幕）**</span><span class="sxs-lookup"><span data-stu-id="c68cb-156">**Peer to peer Video Call (full screen)**</span></span>     |<span data-ttu-id="c68cb-157">4 Mb</span><span class="sxs-lookup"><span data-stu-id="c68cb-157">4 Mb</span></span>         |<span data-ttu-id="c68cb-158">4 Mb</span><span class="sxs-lookup"><span data-stu-id="c68cb-158">4Mb</span></span>         |<span data-ttu-id="c68cb-159">客户端 <> 客户端</span><span class="sxs-lookup"><span data-stu-id="c68cb-159">Client <> Client</span></span>          |
|<span data-ttu-id="c68cb-160">**点对点桌面共享（1920\*1080 分辨率）**</span><span class="sxs-lookup"><span data-stu-id="c68cb-160">**Peer to peer Desktop Sharing (19201080 resolution)**</span></span>     |<span data-ttu-id="c68cb-161">4 Mb</span><span class="sxs-lookup"><span data-stu-id="c68cb-161">4 Mb</span></span>         |<span data-ttu-id="c68cb-162">4 Mb</span><span class="sxs-lookup"><span data-stu-id="c68cb-162">4 Mb</span></span>         |<span data-ttu-id="c68cb-163">客户端 <> 客户端</span><span class="sxs-lookup"><span data-stu-id="c68cb-163">Client <> Client</span></span>          |
|<span data-ttu-id="c68cb-164">**2 个参与者的会议**</span><span class="sxs-lookup"><span data-stu-id="c68cb-164">**2 Participant Meeting**</span></span>     |<span data-ttu-id="c68cb-165">4 Mb</span><span class="sxs-lookup"><span data-stu-id="c68cb-165">4 Mb</span></span>         |<span data-ttu-id="c68cb-166">4 Mb</span><span class="sxs-lookup"><span data-stu-id="c68cb-166">4 Mb</span></span>         |<span data-ttu-id="c68cb-167">客户端 <> Office 365</span><span class="sxs-lookup"><span data-stu-id="c68cb-167">Client <> Office 365</span></span>         |
|<span data-ttu-id="c68cb-168">**3 个参与者的会议**</span><span class="sxs-lookup"><span data-stu-id="c68cb-168">**3 participant meeting**</span></span>     |<span data-ttu-id="c68cb-169">8 Mb</span><span class="sxs-lookup"><span data-stu-id="c68cb-169">8 Mb</span></span>         |<span data-ttu-id="c68cb-170">6.5 Mb</span><span class="sxs-lookup"><span data-stu-id="c68cb-170">6.5 Mb</span></span>         |<span data-ttu-id="c68cb-171">客户端 <> Office 365</span><span class="sxs-lookup"><span data-stu-id="c68cb-171">Client <> Office 365</span></span>           |
|<span data-ttu-id="c68cb-172">**4 个参与者的会议**</span><span class="sxs-lookup"><span data-stu-id="c68cb-172">**4 participant meeting**</span></span>     |<span data-ttu-id="c68cb-173">5.5 Mb</span><span class="sxs-lookup"><span data-stu-id="c68cb-173">5.5 Mb</span></span>         |<span data-ttu-id="c68cb-174">4 Mb</span><span class="sxs-lookup"><span data-stu-id="c68cb-174">4 Mb</span></span>         |<span data-ttu-id="c68cb-175">客户端 <> Office 365</span><span class="sxs-lookup"><span data-stu-id="c68cb-175">Client <> Office 365</span></span>           |
|<span data-ttu-id="c68cb-176">**5 个以上参与者的会议**</span><span class="sxs-lookup"><span data-stu-id="c68cb-176">**5 participant+ meeting**</span></span>     |<span data-ttu-id="c68cb-177">6 Mb</span><span class="sxs-lookup"><span data-stu-id="c68cb-177">6 Mb</span></span>         |<span data-ttu-id="c68cb-178">1.5 Mb</span><span class="sxs-lookup"><span data-stu-id="c68cb-178">1.5 Mb</span></span>         |<span data-ttu-id="c68cb-179">客户端 <> Office 365</span><span class="sxs-lookup"><span data-stu-id="c68cb-179">Client <> Office 365</span></span>           |


<a name="additional-network-considerations"></a><span data-ttu-id="c68cb-180">其他网络考虑事项</span><span class="sxs-lookup"><span data-stu-id="c68cb-180">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="c68cb-181">**外部名称解析**</span><span class="sxs-lookup"><span data-stu-id="c68cb-181">**External Name Resolution**</span></span>

<span data-ttu-id="c68cb-182">确保运行 Teams 客户端的所有客户端计算机都可以解析外部 DNS 查询以发现 Office 365 提供的服务。</span><span class="sxs-lookup"><span data-stu-id="c68cb-182">Ensure that all the client computers running Microsoft Teams client can resolve external DNS queries to discover the services provided by Office 365.</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="c68cb-183">**NAT 池大小**</span><span class="sxs-lookup"><span data-stu-id="c68cb-183">**NAT Pool Size**</span></span>

<span data-ttu-id="c68cb-184">多个用户/设备使用网络地址转换 (NAT) 或端口地址转换 (PAT) 访问 Office 365 时，你需要确保每个公开可路由 IP 地址后面隐藏的设备不超过支持的数量。</span><span class="sxs-lookup"><span data-stu-id="c68cb-184">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP addresses do not exceed the supported number.</span></span>

<span data-ttu-id="c68cb-185">为了缓解此风险，请确保为 NAT 池分配足够的公用 IP 地址以防止端口耗尽。</span><span class="sxs-lookup"><span data-stu-id="c68cb-185">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="c68cb-186">端口耗尽会导致内部最终用户和设备在连接到 Office 365 服务时遇到问题。</span><span class="sxs-lookup"><span data-stu-id="c68cb-186">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="c68cb-187">有关详细信息，请参阅 [Office 365 的 NAT 支持](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)指南。</span><span class="sxs-lookup"><span data-stu-id="c68cb-187">For more information, please refer to [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9) guide.</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="c68cb-188">**入侵检测和防护指导**</span><span class="sxs-lookup"><span data-stu-id="c68cb-188">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="c68cb-189">如果你的环境部署了入侵检测和/或防护系统 (IDS/IPS)，从而为出站连接附加了一层安全性，请确保目标为 Office 365 URL 的任何流量都列入白名单。</span><span class="sxs-lookup"><span data-stu-id="c68cb-189">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="c68cb-190">网络运行状况确定</span><span class="sxs-lookup"><span data-stu-id="c68cb-190">Network health determination</span></span>
-----------------

<span data-ttu-id="c68cb-191">规划在你的网络中实施 Teams 时，你必须确保有所需的带宽、有权访问所有所需的 IP 地址、打开了正确的端口以及满足实时媒体的性能要求。</span><span class="sxs-lookup"><span data-stu-id="c68cb-191">When planning on the implementation of Microsoft Teams within your network, you must ensure to have the required bandwidth, access to all required IP addresses, the correct ports opened, and are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="c68cb-192">你应清楚，如果你无法满足这些条件，那么你的最终用户在使用 Teams 时由于在通话和会议过程中质量较差而无法获得最优体验。</span><span class="sxs-lookup"><span data-stu-id="c68cb-192">If you know you will not meet these criteria, your end users will not get an optimal experience from Microsoft Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="c68cb-193">如果你未满足这些条件，现在应考虑暂停项目，以确保先满足条件，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="c68cb-193">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![决策点图标。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="c68cb-195">决策点</span><span class="sxs-lookup"><span data-stu-id="c68cb-195">Decision Point</span></span>         |<span data-ttu-id="c68cb-196">你是否评估了用于支持实时媒体的网络功能？</span><span class="sxs-lookup"><span data-stu-id="c68cb-196">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="c68cb-197">如果未正确评估你的网络，或者你知道它将无法支持实时媒体，你是否将禁用视频和屏幕共享功能以降低网络影响和糟糕的 Teams 体验？</span><span class="sxs-lookup"><span data-stu-id="c68cb-197">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![后续步骤图标。](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="c68cb-199">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c68cb-199">Next Steps</span></span>         |<span data-ttu-id="c68cb-200">网络质量未知：按照[网络就绪评估](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness)指导来确定你的网络是否可以支持实时媒体。</span><span class="sxs-lookup"><span data-stu-id="c68cb-200">Network Quality Unknown: Follow the Network Readiness Assessment guidance at skypeoperationsframework.com to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="c68cb-201">网络质量较差：执行网络补救步骤以提供合适的环境来支持高质量的实时媒体。</span><span class="sxs-lookup"><span data-stu-id="c68cb-201">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="c68cb-202">网络满意：确保可以正确访问所有 IP 地址和端口。</span><span class="sxs-lookup"><span data-stu-id="c68cb-202">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

