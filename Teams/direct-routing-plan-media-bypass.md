---
title: 使用直接路由规划媒体旁路
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: 阅读本主题可了解如何规划媒体绕过与电话系统直接路由。
ms.openlocfilehash: b3a31e23ef065840d830c111c64e0618d90aa71b
ms.sourcegitcommit: 856793c99fc02fb016383d0b6f8411c386d78886
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2019
ms.locfileid: "31827878"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="3dc71-103">使用直接路由规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="3dc71-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="3dc71-104">有关直接路由的媒体绕过</span><span class="sxs-lookup"><span data-stu-id="3dc71-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="3dc71-105">媒体绕过，可以缩短媒体流量的路径，并降低的更好的性能途中跃点数。</span><span class="sxs-lookup"><span data-stu-id="3dc71-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="3dc71-106">使用媒体旁路，媒体会话边界控制器 (SBC) 而不是通过 Microsoft 电话系统发送它与客户端之间保留。</span><span class="sxs-lookup"><span data-stu-id="3dc71-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="3dc71-107">若要配置媒体绕过、 SBC 和客户端必须相同的位置或网络中。</span><span class="sxs-lookup"><span data-stu-id="3dc71-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="3dc71-108">通过使用**Set CSOnlinePSTNGateway**命令 **-MediaBypass**参数设置为 true 或 false，您可以针对每个 SBC 控制媒体绕过。</span><span class="sxs-lookup"><span data-stu-id="3dc71-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="3dc71-109">如果您启用媒体绕过，这并不意味着在企业网络内，将保持所有媒体通信。</span><span class="sxs-lookup"><span data-stu-id="3dc71-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="3dc71-110">本文介绍在不同方案中的呼叫流程。</span><span class="sxs-lookup"><span data-stu-id="3dc71-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="3dc71-111">下图说明了具有和没有媒体绕过呼叫流的差异。</span><span class="sxs-lookup"><span data-stu-id="3dc71-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="3dc71-112">媒体旁路的情况下当客户端使或接收呼叫，请信号和媒体之间流动 SBC、 Microsoft 电话系统，和团队客户端，如下图中所示：</span><span class="sxs-lookup"><span data-stu-id="3dc71-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

![显示信号和媒体流不存在媒体旁路](media/direct-routing-media-bypass-1.png)


<span data-ttu-id="3dc71-114">但我们假设用户是在同一构建或作为 SBC 网络。</span><span class="sxs-lookup"><span data-stu-id="3dc71-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="3dc71-115">例如，假定正在构建中法兰克福使到 PSTN 用户的呼叫的用户：</span><span class="sxs-lookup"><span data-stu-id="3dc71-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="3dc71-116">**没有媒体绕过**，通过阿姆斯特丹或都柏林 （Microsoft 数据中心部署在此） 并返回到在法兰克福 SBC 将流媒体。</span><span class="sxs-lookup"><span data-stu-id="3dc71-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="3dc71-117">在欧洲数据中心处于选中状态，因为 SBC 在欧洲，并且 Microsoft 使用 SBC 最接近的数据中心。</span><span class="sxs-lookup"><span data-stu-id="3dc71-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="3dc71-118">虽然此方法不会影响由于优化的通信流大多数地理区域中的 Microsoft 网络内的呼叫质量，流量具有不必要的循环。</span><span class="sxs-lookup"><span data-stu-id="3dc71-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="3dc71-119">**使用媒体绕过**，媒体仍保留团队用户直接之间 SBC 下图中所示：</span><span class="sxs-lookup"><span data-stu-id="3dc71-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

![显示信号和媒体绕过使用的媒体流](media/direct-routing-media-bypass-2.png)

<span data-ttu-id="3dc71-121">媒体绕过利用协议上团队客户端和 ICE 设备 SBC 调用互动式连接建立 (ICE)。</span><span class="sxs-lookup"><span data-stu-id="3dc71-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE light on the SBC.</span></span> <span data-ttu-id="3dc71-122">这些协议启用直接路由中的最直接的媒体路径用于最佳的质量。</span><span class="sxs-lookup"><span data-stu-id="3dc71-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="3dc71-123">ICE 和 ICE Lite 是 WebRTC 标准。</span><span class="sxs-lookup"><span data-stu-id="3dc71-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="3dc71-124">有关这些协议的详细信息，请参阅 RFC 5245。</span><span class="sxs-lookup"><span data-stu-id="3dc71-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="3dc71-125">呼叫流和防火墙的规划</span><span class="sxs-lookup"><span data-stu-id="3dc71-125">Call flow and firewall planning</span></span>

<span data-ttu-id="3dc71-126">呼叫流和防火墙的规划取决于用户是否具有直接访问公共 IP 地址的 SBC，以及用户是否为内部或外部网络。</span><span class="sxs-lookup"><span data-stu-id="3dc71-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="3dc71-127">如果用户具有直接访问公共 IP 地址的 SBC，呼叫流</span><span class="sxs-lookup"><span data-stu-id="3dc71-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="3dc71-128">如果用户具有直接访问 SBC 的公共 IP 地址，呼叫流如下所示：</span><span class="sxs-lookup"><span data-stu-id="3dc71-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="3dc71-129">媒体绕过团队客户端必须能够访问到公用 IP 地址的 SBC 甚至是从内部网络。</span><span class="sxs-lookup"><span data-stu-id="3dc71-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="3dc71-130">如果不需要直接媒体，媒体能否通过传输中继。</span><span class="sxs-lookup"><span data-stu-id="3dc71-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="3dc71-131">这是建议的解决方案，当用户在相同生成和/或 SBC 网络 – 从媒体路径中删除 Microsoft 云组件。</span><span class="sxs-lookup"><span data-stu-id="3dc71-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="3dc71-132">通过 Microsoft 云始终信号流。</span><span class="sxs-lookup"><span data-stu-id="3dc71-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="3dc71-133">下图显示启用媒体绕过时的呼叫流和客户端是内部客户端可达到 SBC （直接媒体） 的公共 IP 地址：</span><span class="sxs-lookup"><span data-stu-id="3dc71-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="3dc71-134">箭头和数字值的路径是根据[Microsoft 团队呼叫流](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)文章。</span><span class="sxs-lookup"><span data-stu-id="3dc71-134">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="3dc71-135">SIP 信号总是采用路径 4 和 4 （取决于通信的方向）。</span><span class="sxs-lookup"><span data-stu-id="3dc71-135">The SIP signaling always takes paths 4 and 4’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="3dc71-136">媒体保持本地和采用路径 5b。</span><span class="sxs-lookup"><span data-stu-id="3dc71-136">Media stays local and takes path 5b.</span></span>

![显示使用媒体旁路的呼叫流启用、 客户端是内部，可达到公用 IP 的会话边界控制器 （直接媒体）](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="3dc71-138">如果用户不具有访问公共 IP 地址的 SBC，呼叫流</span><span class="sxs-lookup"><span data-stu-id="3dc71-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="3dc71-139">以下介绍了呼叫流，如果用户不具有访问权的 SBC 的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3dc71-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="3dc71-140">例如，假定该用户是外部，并且租户管理员决定不打开 SBC 到 Internet 中的所有人，但仅对 Microsoft 云的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3dc71-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="3dc71-141">通信的内部组件可以通过团队传输中继流动。</span><span class="sxs-lookup"><span data-stu-id="3dc71-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="3dc71-142">这是公司网络外部的用户的推荐的配置。</span><span class="sxs-lookup"><span data-stu-id="3dc71-142">This is the recommended configuration for users outside of the corporate network.</span></span> <span data-ttu-id="3dc71-143">请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="3dc71-143">Consider the following:</span></span>

- <span data-ttu-id="3dc71-144">使用团队传输中继。</span><span class="sxs-lookup"><span data-stu-id="3dc71-144">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="3dc71-145">媒体绕过，Microsoft 使用需要 （在我们计划将移到的版本，这需要仅 3478 和 3479 端口未来） 中打开端口 50 000 到 59 999 团队传输中继和 SBC 之间的传输中继的版本。</span><span class="sxs-lookup"><span data-stu-id="3dc71-145">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>

- <span data-ttu-id="3dc71-146">为了优化媒体，Microsoft 建议打开仅对团队传输中继 SBC 的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3dc71-146">For media optimization purposes, Microsoft recommends opening the public IP address of the SBC only to Teams Transport Relays.</span></span> <span data-ttu-id="3dc71-147">对于公司网络外部的客户端，Microsoft 建议使用传输中继而不直接达到 SBC 的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3dc71-147">For clients outside of the corporate network, Microsoft recommends using Transport Relays instead of reaching the public IP address of the SBC directly.</span></span>

<span data-ttu-id="3dc71-148">下图显示启用媒体绕过时的呼叫流和客户端是外部客户端无法访问的会话边界控制器 （媒体中继的团队传输中继） 的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3dc71-148">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="3dc71-149">箭头和数字值的路径是根据[Microsoft 团队呼叫流](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)文章。</span><span class="sxs-lookup"><span data-stu-id="3dc71-149">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="3dc71-150">媒体中继通过路径 3，3，4，4</span><span class="sxs-lookup"><span data-stu-id="3dc71-150">Media is relayed via paths 3, 3', 4 and 4'</span></span>

![如果用户不具有访问公用 IP 的 SBC 显示呼叫流）](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="3dc71-152">如果某用户是网络外部的并有权访问公用 IP 的 SBC，呼叫流</span><span class="sxs-lookup"><span data-stu-id="3dc71-152">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="3dc71-153">这不是建议的配置，因为它不能利用团队传输中继。</span><span class="sxs-lookup"><span data-stu-id="3dc71-153">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="3dc71-154">相反，您应考虑前一个场景用户没有访问 SBC 的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3dc71-154">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="3dc71-155">下图显示启用媒体绕过时的呼叫流和客户端是外部客户端可达到 SBC （直接媒体） 的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3dc71-155">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="3dc71-156">箭头和数字值的路径是根据[Microsoft 团队呼叫流](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)文章。</span><span class="sxs-lookup"><span data-stu-id="3dc71-156">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="3dc71-157">SIP 信号总是采用路径 3 和 3 （取决于通信的方向）。</span><span class="sxs-lookup"><span data-stu-id="3dc71-157">The SIP signaling always takes paths 3 and 3’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="3dc71-158">使用路径 2 的媒体流。</span><span class="sxs-lookup"><span data-stu-id="3dc71-158">Media flows using path 2.</span></span>

![如果用户不具有访问公用 IP 的 SBC 显示呼叫流）](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="3dc71-160">使用媒体处理器和传输中继</span><span class="sxs-lookup"><span data-stu-id="3dc71-160">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="3dc71-161">媒体流量的路径中可以是 Microsoft 云中有两个组件： 媒体处理器和传输中继。</span><span class="sxs-lookup"><span data-stu-id="3dc71-161">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="3dc71-162">媒体处理器是公共面向组件的处理媒体的非绕过的情况下，并处理语音应用程序的媒体。</span><span class="sxs-lookup"><span data-stu-id="3dc71-162">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="3dc71-163">媒体处理器通常在最终用户非绕过呼叫的路径，但从不绕过呼叫路径中。</span><span class="sxs-lookup"><span data-stu-id="3dc71-163">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="3dc71-164">媒体处理器始终位于如呼叫寄存、 组织的自动助理和呼叫的队列的所有语音应用程序的路径。</span><span class="sxs-lookup"><span data-stu-id="3dc71-164">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="3dc71-165">传输中继用于连接到最接近的传输服务，以发送实时通信。</span><span class="sxs-lookup"><span data-stu-id="3dc71-165">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="3dc71-166">传输中继可能或可能不是来自或最终用户-具体取决于用户和网络的配置方式发往绕过呼叫-路径中。</span><span class="sxs-lookup"><span data-stu-id="3dc71-166">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="3dc71-167">下图显示两个呼叫流 – 启用媒体绕过与一个和第二个与媒体绕过已禁用。</span><span class="sxs-lookup"><span data-stu-id="3dc71-167">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="3dc71-168">注意图表仅说明来自-或往-最终用户通信。</span><span class="sxs-lookup"><span data-stu-id="3dc71-168">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="3dc71-169">媒体控制器是在分配媒体处理器并创建会话描述协议 (SDP) 提供的 Azure microservice。</span><span class="sxs-lookup"><span data-stu-id="3dc71-169">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="3dc71-170">SIP 代理服务器是转换 HTTP REST 信号 SIP 团队中使用的组件。</span><span class="sxs-lookup"><span data-stu-id="3dc71-170">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

![显示两个呼叫流 – 一个启用媒体绕过，存在媒体绕过禁用第二个）](media/direct-routing-media-bypass-6.png)


<span data-ttu-id="3dc71-172">下表总结了媒体处理器和传输中继之间的差异。</span><span class="sxs-lookup"><span data-stu-id="3dc71-172">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="3dc71-173">媒体处理器</span><span class="sxs-lookup"><span data-stu-id="3dc71-173">Media Processors</span></span> | <span data-ttu-id="3dc71-174">传输中继</span><span class="sxs-lookup"><span data-stu-id="3dc71-174">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="3dc71-175">面向最终用户的非绕过呼叫的媒体路径中</span><span class="sxs-lookup"><span data-stu-id="3dc71-175">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="3dc71-176">始终</span><span class="sxs-lookup"><span data-stu-id="3dc71-176">Always</span></span> | <span data-ttu-id="3dc71-177">从不</span><span class="sxs-lookup"><span data-stu-id="3dc71-177">Never</span></span> | 
<span data-ttu-id="3dc71-178">面向最终用户的绕过呼叫的媒体路径中</span><span class="sxs-lookup"><span data-stu-id="3dc71-178">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="3dc71-179">从不</span><span class="sxs-lookup"><span data-stu-id="3dc71-179">Never</span></span> | <span data-ttu-id="3dc71-180">如果客户端无法访问公共 IP 地址 SBC</span><span class="sxs-lookup"><span data-stu-id="3dc71-180">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="3dc71-181">语音应用程序的媒体路径中</span><span class="sxs-lookup"><span data-stu-id="3dc71-181">In media path for voice applications</span></span> | <span data-ttu-id="3dc71-182">始终</span><span class="sxs-lookup"><span data-stu-id="3dc71-182">Always</span></span> | <span data-ttu-id="3dc71-183">从不</span><span class="sxs-lookup"><span data-stu-id="3dc71-183">Never</span></span> | 
<span data-ttu-id="3dc71-184">可以执行转码 (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="3dc71-184">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="3dc71-185">是</span><span class="sxs-lookup"><span data-stu-id="3dc71-185">Yes</span></span> | <span data-ttu-id="3dc71-186">否，仅中继终结点之间的音频</span><span class="sxs-lookup"><span data-stu-id="3dc71-186">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="3dc71-187">全球实例的数量和位置</span><span class="sxs-lookup"><span data-stu-id="3dc71-187">Number of instances worldwide and location</span></span> | <span data-ttu-id="3dc71-188">总 8： 在美国东和西; 2在阿姆斯特丹和都柏林; 2香港特别行政区和新加坡; 2日本 （正在添加中 Q1CY2019） 2</span><span class="sxs-lookup"><span data-stu-id="3dc71-188">8 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan (being added in Q1CY2019)</span></span>  | <span data-ttu-id="3dc71-189">多个</span><span class="sxs-lookup"><span data-stu-id="3dc71-189">Multiple</span></span>

<span data-ttu-id="3dc71-190">IP 范围是 52.112.0.0 /14 （IP 地址从 52.112.0.1 52.115.255.254）。</span><span class="sxs-lookup"><span data-stu-id="3dc71-190">The IP range is 52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span> 

<span data-ttu-id="3dc71-191">\*转码说明：</span><span class="sxs-lookup"><span data-stu-id="3dc71-191">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="3dc71-192">媒体处理器是 B2BUA，这意味着可以将其更改编解码器 （例如，绞丝团队客户端从 MP 和 G.711 MP 和 SBC 之间）。</span><span class="sxs-lookup"><span data-stu-id="3dc71-192">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="3dc71-193">传输中继不 B2BUA，这意味着即使通信流通过中继的编解码器永远不会更改客户端和 SBC-之间。</span><span class="sxs-lookup"><span data-stu-id="3dc71-193">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-transport-relays-in-escalation-scenarios-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="3dc71-194">使用团队传输中继的升级情况下是否中继配置了媒体绕过</span><span class="sxs-lookup"><span data-stu-id="3dc71-194">Use of Teams Transport Relays in escalation scenarios if trunk is configured for media bypass</span></span>

<span data-ttu-id="3dc71-195">团队传输中继始终是以下方案中的媒体路径中：</span><span class="sxs-lookup"><span data-stu-id="3dc71-195">Teams Transport Relays are always in the media path in the following scenarios:</span></span>

- <span data-ttu-id="3dc71-196">呼叫呈报从 1:1 到的组呼叫</span><span class="sxs-lookup"><span data-stu-id="3dc71-196">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="3dc71-197">呼叫转到联盟团队用户</span><span class="sxs-lookup"><span data-stu-id="3dc71-197">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="3dc71-198">转接呼叫或将其转接到业务用户 Skype</span><span class="sxs-lookup"><span data-stu-id="3dc71-198">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="3dc71-199">确保您的 SBC 有权访问传输中继，如下所述。</span><span class="sxs-lookup"><span data-stu-id="3dc71-199">Ensure your SBC has access to the Transport Relays as described below.</span></span>    


## <a name="sip-signaling-fqdns-and-firewall-ports"></a><span data-ttu-id="3dc71-200">SIP 信号： Fqdn 和防火墙端口</span><span class="sxs-lookup"><span data-stu-id="3dc71-200">SIP Signaling: FQDNs and firewall ports</span></span>

<span data-ttu-id="3dc71-201">SIP 信号的 FQDN 和防火墙要求是与非绕过的情况下相同。</span><span class="sxs-lookup"><span data-stu-id="3dc71-201">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="3dc71-202">直接路由的连接点是具有以下三个 Fqdn:</span><span class="sxs-lookup"><span data-stu-id="3dc71-202">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="3dc71-203">必须首先尝试**sip.pstnhub.microsoft.com** – 全局 FQDN –。</span><span class="sxs-lookup"><span data-stu-id="3dc71-203">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="3dc71-204">当 SBC 发送请求，若要解决此名称时，Microsoft Azure DNS 服务器返回指向主 Azure 数据中心 IP 地址分配给 SBC。</span><span class="sxs-lookup"><span data-stu-id="3dc71-204">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="3dc71-205">性能指标的数据中心和地理接近 SBC 基于工作分配。</span><span class="sxs-lookup"><span data-stu-id="3dc71-205">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="3dc71-206">返回的 IP 地址对应于主要的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="3dc71-206">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="3dc71-207">**sip2.pstnhub.microsoft.com** – 辅助 FQDN – 地理位置映射到第二个优先级区域。</span><span class="sxs-lookup"><span data-stu-id="3dc71-207">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="3dc71-208">**sip3.pstnhub.microsoft.com** – 第三级 FQDN – 地理位置映射到第三个优先级区域。</span><span class="sxs-lookup"><span data-stu-id="3dc71-208">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="3dc71-209">必须放置在以下三个 Fqdn:</span><span class="sxs-lookup"><span data-stu-id="3dc71-209">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="3dc71-210">提供最佳用户体验 （不加载和 SBC 数据中心通过查询的第一个 FQDN 分配最接近）。</span><span class="sxs-lookup"><span data-stu-id="3dc71-210">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="3dc71-211">从 SBC 连接建立到数据中心的临时问题时提供故障转移。</span><span class="sxs-lookup"><span data-stu-id="3dc71-211">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="3dc71-212">有关详细信息，请参阅下面的故障转移机制。</span><span class="sxs-lookup"><span data-stu-id="3dc71-212">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="3dc71-213">Fqdn **sip.pstnhub.microsoft.com**、 **sip2.pstnhub.microsoft.com**和**sip3.pstnhub.microsoft.com**将解析为以下 IP 地址之一：</span><span class="sxs-lookup"><span data-stu-id="3dc71-213">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="3dc71-214">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="3dc71-214">52.114.148.0</span></span>
- <span data-ttu-id="3dc71-215">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="3dc71-215">52.114.132.46</span></span>
- <span data-ttu-id="3dc71-216">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="3dc71-216">52.114.75.24</span></span>
- <span data-ttu-id="3dc71-217">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="3dc71-217">52.114.76.76</span></span>
- <span data-ttu-id="3dc71-218">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="3dc71-218">52.114.7.24</span></span>
- <span data-ttu-id="3dc71-219">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="3dc71-219">52.114.14.70</span></span>

<span data-ttu-id="3dc71-220">您需要打开防火墙以允许与地址的传入和传出流量信号中的所有这些 IP 地址的端口。</span><span class="sxs-lookup"><span data-stu-id="3dc71-220">You will need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="3dc71-221">如果您的防火墙支持 DNS 名称解析为上面的所有 IP 地址的 FQDN **sip all.pstnhub.microsoft.com** 。</span><span class="sxs-lookup"><span data-stu-id="3dc71-221">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all the IP addresses above.</span></span> <span data-ttu-id="3dc71-222">您必须使用以下端口：</span><span class="sxs-lookup"><span data-stu-id="3dc71-222">You must use the following ports:</span></span>

| <span data-ttu-id="3dc71-223">流量</span><span class="sxs-lookup"><span data-stu-id="3dc71-223">Traffic</span></span> | <span data-ttu-id="3dc71-224">从</span><span class="sxs-lookup"><span data-stu-id="3dc71-224">From</span></span> | <span data-ttu-id="3dc71-225">到</span><span class="sxs-lookup"><span data-stu-id="3dc71-225">To</span></span> | <span data-ttu-id="3dc71-226">源端口</span><span class="sxs-lookup"><span data-stu-id="3dc71-226">Source port</span></span> | <span data-ttu-id="3dc71-227">目标端口</span><span class="sxs-lookup"><span data-stu-id="3dc71-227">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="3dc71-228">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="3dc71-228">SIP/TLS</span></span>| <span data-ttu-id="3dc71-229">SIP 代理服务器</span><span class="sxs-lookup"><span data-stu-id="3dc71-229">SIP Proxy</span></span> | <span data-ttu-id="3dc71-230">SBC</span><span class="sxs-lookup"><span data-stu-id="3dc71-230">SBC</span></span> | <span data-ttu-id="3dc71-231">1024-65535</span><span class="sxs-lookup"><span data-stu-id="3dc71-231">1024 - 65535</span></span> | <span data-ttu-id="3dc71-232">SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="3dc71-232">Defined on the SBC</span></span> |
| <span data-ttu-id="3dc71-233">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="3dc71-233">SIP/TLS</span></span> | <span data-ttu-id="3dc71-234">SBC</span><span class="sxs-lookup"><span data-stu-id="3dc71-234">SBC</span></span> | <span data-ttu-id="3dc71-235">SIP 代理服务器</span><span class="sxs-lookup"><span data-stu-id="3dc71-235">SIP Proxy</span></span> | <span data-ttu-id="3dc71-236">SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="3dc71-236">Defined on the SBC</span></span> | <span data-ttu-id="3dc71-237">5061</span><span class="sxs-lookup"><span data-stu-id="3dc71-237">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="3dc71-238">媒体流量： IP 和端口范围</span><span class="sxs-lookup"><span data-stu-id="3dc71-238">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="3dc71-239">媒体流量之间流动 SBC 和团队客户端直接连接是否可用，或通过团队传输中继如果客户端无法访问 SBC 使用公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3dc71-239">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="3dc71-240">直接媒体流量 （团队客户端和 SBC） 之间的要求</span><span class="sxs-lookup"><span data-stu-id="3dc71-240">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="3dc71-241">客户端必须具有对 SBC 的公共 IP 地址上的指定端口 （请参见表） 的访问。</span><span class="sxs-lookup"><span data-stu-id="3dc71-241">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="3dc71-242">注意： 如果客户端位于内部网络，媒体流的 SBC 的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3dc71-242">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="3dc71-243">您可以配置 hairpinning NAT 设备上，以便流量从不离开企业网络设备。</span><span class="sxs-lookup"><span data-stu-id="3dc71-243">You can configure hairpinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="3dc71-244">流量</span><span class="sxs-lookup"><span data-stu-id="3dc71-244">Traffic</span></span> | <span data-ttu-id="3dc71-245">从</span><span class="sxs-lookup"><span data-stu-id="3dc71-245">From</span></span> | <span data-ttu-id="3dc71-246">到</span><span class="sxs-lookup"><span data-stu-id="3dc71-246">To</span></span> | <span data-ttu-id="3dc71-247">源端口</span><span class="sxs-lookup"><span data-stu-id="3dc71-247">Source port</span></span> | <span data-ttu-id="3dc71-248">目标端口</span><span class="sxs-lookup"><span data-stu-id="3dc71-248">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="3dc71-249">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="3dc71-249">UDP/SRTP</span></span> | <span data-ttu-id="3dc71-250">客户端</span><span class="sxs-lookup"><span data-stu-id="3dc71-250">Client</span></span> | <span data-ttu-id="3dc71-251">SBC</span><span class="sxs-lookup"><span data-stu-id="3dc71-251">SBC</span></span> | <span data-ttu-id="3dc71-252">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="3dc71-252">50 000 – 50 019</span></span>  | <span data-ttu-id="3dc71-253">SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="3dc71-253">Defined on the SBC</span></span> |
| <span data-ttu-id="3dc71-254">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="3dc71-254">UDP/SRTP</span></span> | <span data-ttu-id="3dc71-255">SBC</span><span class="sxs-lookup"><span data-stu-id="3dc71-255">SBC</span></span> | <span data-ttu-id="3dc71-256">客户端</span><span class="sxs-lookup"><span data-stu-id="3dc71-256">Client</span></span> | <span data-ttu-id="3dc71-257">SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="3dc71-257">Defined on the SBC</span></span> | <span data-ttu-id="3dc71-258">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="3dc71-258">50 000 – 50 019</span></span>  |


<span data-ttu-id="3dc71-259">注意： 如果您有转换客户端的源端口的网络设备，请确保之间的网络设备和 SBC 打开转换后的端口。</span><span class="sxs-lookup"><span data-stu-id="3dc71-259">Note: If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="3dc71-260">使用传输中继要求</span><span class="sxs-lookup"><span data-stu-id="3dc71-260">Requirements for using Transport Relays</span></span>

<span data-ttu-id="3dc71-261">传输中继位于同一个范围为媒体处理器 （无绕过的情况下）： 52.112.0.0 /14 （IP 地址从 52.112.0.1 52.115.255.254）。</span><span class="sxs-lookup"><span data-stu-id="3dc71-261">Transport Relays are in the same range as Media Processors (for non-bypass cases):  52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span>

<span data-ttu-id="3dc71-262">下表中显示团队传输中继的端口范围：</span><span class="sxs-lookup"><span data-stu-id="3dc71-262">The port range of the Teams Transport Relays is shown in the following table:</span></span>


| <span data-ttu-id="3dc71-263">流量</span><span class="sxs-lookup"><span data-stu-id="3dc71-263">Traffic</span></span> | <span data-ttu-id="3dc71-264">从</span><span class="sxs-lookup"><span data-stu-id="3dc71-264">From</span></span> | <span data-ttu-id="3dc71-265">到</span><span class="sxs-lookup"><span data-stu-id="3dc71-265">To</span></span> | <span data-ttu-id="3dc71-266">源端口</span><span class="sxs-lookup"><span data-stu-id="3dc71-266">Source port</span></span> | <span data-ttu-id="3dc71-267">目标端口</span><span class="sxs-lookup"><span data-stu-id="3dc71-267">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="3dc71-268">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="3dc71-268">UDP/SRTP</span></span> | <span data-ttu-id="3dc71-269">传输中继</span><span class="sxs-lookup"><span data-stu-id="3dc71-269">Transport Relay</span></span> | <span data-ttu-id="3dc71-270">SBC</span><span class="sxs-lookup"><span data-stu-id="3dc71-270">SBC</span></span> | <span data-ttu-id="3dc71-271">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="3dc71-271">50 000 -59 999</span></span>    | <span data-ttu-id="3dc71-272">SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="3dc71-272">Defined on the SBC</span></span> |
| <span data-ttu-id="3dc71-273">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="3dc71-273">UDP/SRTP</span></span> | <span data-ttu-id="3dc71-274">SBC</span><span class="sxs-lookup"><span data-stu-id="3dc71-274">SBC</span></span> | <span data-ttu-id="3dc71-275">传输中继</span><span class="sxs-lookup"><span data-stu-id="3dc71-275">Transport Relay</span></span> | <span data-ttu-id="3dc71-276">SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="3dc71-276">Defined on the SBC</span></span> | <span data-ttu-id="3dc71-277">50 000 – 59 999，3478 3479</span><span class="sxs-lookup"><span data-stu-id="3dc71-277">50 000 – 59 999, 3478, 3479</span></span>     |


<span data-ttu-id="3dc71-278">注意： Microsoft 建议每个并发呼叫 SBC 上至少两个端口。</span><span class="sxs-lookup"><span data-stu-id="3dc71-278">Note: Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="3dc71-279">因为 Microsoft 拥有传输中继的两个版本，您需要：</span><span class="sxs-lookup"><span data-stu-id="3dc71-279">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>

- <span data-ttu-id="3dc71-280">v4，只能处理的端口范围 50 000 到 59 999</span><span class="sxs-lookup"><span data-stu-id="3dc71-280">v4, which can only work with port range 50 000 to 59 999</span></span>

- <span data-ttu-id="3dc71-281">v6，适用于端口 3478，3479</span><span class="sxs-lookup"><span data-stu-id="3dc71-281">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="3dc71-282">此时，媒体绕过仅支持传输中继的 v4 版本。</span><span class="sxs-lookup"><span data-stu-id="3dc71-282">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="3dc71-283">我们将在将来引入 v6 支持。</span><span class="sxs-lookup"><span data-stu-id="3dc71-283">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="3dc71-284">您需要打开端口 3478 和转换的 3479。</span><span class="sxs-lookup"><span data-stu-id="3dc71-284">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="3dc71-285">当 Microsoft 引入了对存在媒体绕过 v6 传输中继支持时，不需要重新配置您的网络设备或 SBCs。</span><span class="sxs-lookup"><span data-stu-id="3dc71-285">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="3dc71-286">使用媒体处理器的要求</span><span class="sxs-lookup"><span data-stu-id="3dc71-286">Requirements for using media processors</span></span>

<span data-ttu-id="3dc71-287">媒体处理器通常以语音应用程序的媒体路径中。</span><span class="sxs-lookup"><span data-stu-id="3dc71-287">Media Processors are always in the media path for voice applications.</span></span> <span data-ttu-id="3dc71-288">要求都与非绕过配置相同。</span><span class="sxs-lookup"><span data-stu-id="3dc71-288">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="3dc71-289">媒体流量的 IP 范围是 52.112.0.0 /14 （IP 地址从 52.112.0.1 52.115.255.254）。</span><span class="sxs-lookup"><span data-stu-id="3dc71-289">The IP range for media traffic is 52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span>

<span data-ttu-id="3dc71-290">下表中显示的媒体处理器的端口范围：</span><span class="sxs-lookup"><span data-stu-id="3dc71-290">The port range of the Media Processors is shown in the following table:</span></span>

| <span data-ttu-id="3dc71-291">流量</span><span class="sxs-lookup"><span data-stu-id="3dc71-291">Traffic</span></span> | <span data-ttu-id="3dc71-292">从</span><span class="sxs-lookup"><span data-stu-id="3dc71-292">From</span></span> | <span data-ttu-id="3dc71-293">到</span><span class="sxs-lookup"><span data-stu-id="3dc71-293">To</span></span> | <span data-ttu-id="3dc71-294">源端口</span><span class="sxs-lookup"><span data-stu-id="3dc71-294">Source port</span></span> | <span data-ttu-id="3dc71-295">目标端口</span><span class="sxs-lookup"><span data-stu-id="3dc71-295">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="3dc71-296">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="3dc71-296">UDP/SRTP</span></span> | <span data-ttu-id="3dc71-297">媒体处理器</span><span class="sxs-lookup"><span data-stu-id="3dc71-297">Media Processor</span></span> | <span data-ttu-id="3dc71-298">SBC</span><span class="sxs-lookup"><span data-stu-id="3dc71-298">SBC</span></span> | <span data-ttu-id="3dc71-299">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="3dc71-299">49 152 – 53 247</span></span>    | <span data-ttu-id="3dc71-300">SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="3dc71-300">Defined on the SBC</span></span> |
| <span data-ttu-id="3dc71-301">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="3dc71-301">UDP/SRTP</span></span> | <span data-ttu-id="3dc71-302">SBC</span><span class="sxs-lookup"><span data-stu-id="3dc71-302">SBC</span></span> | <span data-ttu-id="3dc71-303">媒体处理器</span><span class="sxs-lookup"><span data-stu-id="3dc71-303">Media Processor</span></span> | <span data-ttu-id="3dc71-304">SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="3dc71-304">Defined on the SBC</span></span> | <span data-ttu-id="3dc71-305">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="3dc71-305">49 152 – 53 247</span></span>     |

## <a name="considerations-if-you-have-skype-for-business-phones-in-your-network"></a><span data-ttu-id="3dc71-306">如果您有 Skype 业务电话的网络中的注意事项</span><span class="sxs-lookup"><span data-stu-id="3dc71-306">Considerations if you have Skype for Business phones in your network</span></span>  

<span data-ttu-id="3dc71-307">如果您有任何 Skype 的网络中的业务终结点使用直接路由-例如，用户可以基于业务客户端--Skype 3PIP 电话团队那些这些用户提供服务中继上的媒体绕过功能必须关闭。</span><span class="sxs-lookup"><span data-stu-id="3dc71-307">If you have any Skype for Business end points in your network that are using Direct Routing--for example, a Teams user can have a 3PIP phone that is based on Skype for Business client--the media bypass on the trunk that serves these users must be turned off.</span></span>

<span data-ttu-id="3dc71-308">您可以创建单独中继为这些用户，并将其分配的联机语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="3dc71-308">You can create a separate trunk for these users and assign it an Online Voice Routing policy.</span></span>

<span data-ttu-id="3dc71-309">高级配置步骤：</span><span class="sxs-lookup"><span data-stu-id="3dc71-309">High-level configuration steps:</span></span>

- <span data-ttu-id="3dc71-310">拆分按类型 – 根据用户是否具有 3PIP 电话的用户。</span><span class="sxs-lookup"><span data-stu-id="3dc71-310">Split users by type – depending on whether the user has a 3PIP phone or not.</span></span>

- <span data-ttu-id="3dc71-311">创建具有不同 Fqdn 的单独的两个中继： 一个启用媒体绕过;其他不。</span><span class="sxs-lookup"><span data-stu-id="3dc71-311">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="3dc71-312">这两个中继指向同一 SBC。</span><span class="sxs-lookup"><span data-stu-id="3dc71-312">Both trunks point to the same SBC.</span></span> <span data-ttu-id="3dc71-313">TLS SIP 信号端口必须不同。</span><span class="sxs-lookup"><span data-stu-id="3dc71-313">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="3dc71-314">媒体端口必须相同。</span><span class="sxs-lookup"><span data-stu-id="3dc71-314">The ports for media must be the same.</span></span>

- <span data-ttu-id="3dc71-315">分配正确中继根据联机语音路由策略中的用户的类型。</span><span class="sxs-lookup"><span data-stu-id="3dc71-315">Assign the correct trunk depending on the type of the user in the Online Voice Routing policy.</span></span>

<span data-ttu-id="3dc71-316">下面的示例说明了此逻辑。</span><span class="sxs-lookup"><span data-stu-id="3dc71-316">The example below illustrates this logic.</span></span>

| <span data-ttu-id="3dc71-317">用户组</span><span class="sxs-lookup"><span data-stu-id="3dc71-317">Set of users</span></span> | <span data-ttu-id="3dc71-318">用户数</span><span class="sxs-lookup"><span data-stu-id="3dc71-318">Number of users</span></span> | <span data-ttu-id="3dc71-319">中继中 OVRP 分配的 FQDN</span><span class="sxs-lookup"><span data-stu-id="3dc71-319">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="3dc71-320">启用媒体绕过</span><span class="sxs-lookup"><span data-stu-id="3dc71-320">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="3dc71-321">与团队客户端和 3PIP 电话的用户</span><span class="sxs-lookup"><span data-stu-id="3dc71-321">Users with Teams clients and 3PIP phones</span></span> | <span data-ttu-id="3dc71-322">20</span><span class="sxs-lookup"><span data-stu-id="3dc71-322">20</span></span> | <span data-ttu-id="3dc71-323">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="3dc71-323">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="3dc71-324">false</span><span class="sxs-lookup"><span data-stu-id="3dc71-324">false</span></span> | 
<span data-ttu-id="3dc71-325">用户 （包括新团队认证的电话） 的仅团队终结点</span><span class="sxs-lookup"><span data-stu-id="3dc71-325">Users with only Teams end points (including new phones certified for Teams)</span></span> | <span data-ttu-id="3dc71-326">980</span><span class="sxs-lookup"><span data-stu-id="3dc71-326">980</span></span> | <span data-ttu-id="3dc71-327">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="3dc71-327">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="3dc71-328">true</span><span class="sxs-lookup"><span data-stu-id="3dc71-328">true</span></span>

<span data-ttu-id="3dc71-329">这两个中继可以指向同一 SBC 具有相同的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3dc71-329">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="3dc71-330">下图中所示，必须不同，TLS 信号 SBC 上的端口。</span><span class="sxs-lookup"><span data-stu-id="3dc71-330">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="3dc71-331">请注意，您将需要确保您的证书支持两个中继。</span><span class="sxs-lookup"><span data-stu-id="3dc71-331">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="3dc71-332">在 SAN，您需要有两个名称 （**sbc1.contoso.com**和**sbc2.contoso.com**） 或拥有通配符证书。</span><span class="sxs-lookup"><span data-stu-id="3dc71-332">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>


![显示两个中继可以指向同一 SBC 与同一个公共 IP）](media/direct-routing-media-bypass-7.png)

<span data-ttu-id="3dc71-334">有关如何在相同的 SBC 上配置的两个中继的信息，请参阅您的 SBC 供应商提供的文档：</span><span class="sxs-lookup"><span data-stu-id="3dc71-334">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

- <span data-ttu-id="3dc71-335">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="3dc71-335">AudioCodes</span></span>
- <span data-ttu-id="3dc71-336">功能区</span><span class="sxs-lookup"><span data-stu-id="3dc71-336">Ribbon</span></span>
- <span data-ttu-id="3dc71-337">TE 系统 (Anynode)</span><span class="sxs-lookup"><span data-stu-id="3dc71-337">TE-Systems (Anynode)</span></span>   

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="3dc71-338">客户端终结点支持媒体绕过</span><span class="sxs-lookup"><span data-stu-id="3dc71-338">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="3dc71-339">支持媒体绕过所有团队终结点，直到进一步通知团队 Web 客户端除外。</span><span class="sxs-lookup"><span data-stu-id="3dc71-339">Media bypass is supported with all Teams endpoints, except Teams Web clients until further notice.</span></span> 

<span data-ttu-id="3dc71-340">如果用户希望 Microsoft 边缘，Google Chrome 或 Mozilla Firefox 中的团队 Web 应用程序必须关闭此类用户的媒体绕过。</span><span class="sxs-lookup"><span data-stu-id="3dc71-340">If your users prefer Teams Web app in Microsoft Edge, Google Chrome or Mozilla Firefox, the media bypass for such users must be turned off.</span></span> <span data-ttu-id="3dc71-341">我们将介绍调用将来使用媒体绕过启用中继。</span><span class="sxs-lookup"><span data-stu-id="3dc71-341">We will introduce calling using a media bypass enabled trunk in the future.</span></span>   
 
## <a name="see-also"></a><span data-ttu-id="3dc71-342">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3dc71-342">See also</span></span>

[<span data-ttu-id="3dc71-343">使用直接路由配置媒体旁路</span><span class="sxs-lookup"><span data-stu-id="3dc71-343">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)



