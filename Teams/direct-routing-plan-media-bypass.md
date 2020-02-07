---
title: 使用直接路由规划媒体旁路
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 阅读本主题，了解如何使用手机系统直接路由规划媒体旁路。
ms.openlocfilehash: 98f09d00960615c09dca8dcd78275a418d650f3e
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835972"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="397e9-103">使用直接路由规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="397e9-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="397e9-104">关于直接路由的媒体旁路</span><span class="sxs-lookup"><span data-stu-id="397e9-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="397e9-105">媒体绕过使你可以缩短媒体流量的路径，并减少传输中的跃点数，从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="397e9-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="397e9-106">通过媒体绕过，媒体将保留在会话边界控制器（SBC）和客户端之间，而不是通过 Microsoft Phone 系统发送。</span><span class="sxs-lookup"><span data-stu-id="397e9-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="397e9-107">要配置绕过媒体，SBC 和客户端必须位于同一位置或网络。</span><span class="sxs-lookup"><span data-stu-id="397e9-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="397e9-108">你可以通过使用**CSOnlinePSTNGateway**命令，将 **-MediaBypass**参数设置为 true 或 false 来控制每个 SBC 的媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="397e9-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="397e9-109">如果启用 "媒体绕过"，这并不意味着所有媒体流量都将保留在公司网络中。</span><span class="sxs-lookup"><span data-stu-id="397e9-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="397e9-110">本文介绍不同方案中的调用流。</span><span class="sxs-lookup"><span data-stu-id="397e9-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="397e9-111">下图展示了通话流程的区别和不使用媒体旁路的情况。</span><span class="sxs-lookup"><span data-stu-id="397e9-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="397e9-112">如果不使用媒体绕过，则在客户端发出或接收呼叫时，SBC、Microsoft Phone 系统和团队客户端之间的信号和媒体流均为，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="397e9-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

![显示不使用媒体旁路的信号和媒体流](media/direct-routing-media-bypass-1.png)


<span data-ttu-id="397e9-114">但是，假设用户与 SBC 位于同一建筑物或网络中。</span><span class="sxs-lookup"><span data-stu-id="397e9-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="397e9-115">例如，假设法兰克福中的大楼的用户拨打 PSTN 用户的电话：</span><span class="sxs-lookup"><span data-stu-id="397e9-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="397e9-116">如果**没有媒体绕过**，媒体将通过阿姆斯特丹或都柏林（在 Microsoft 数据中心的部署位置）和返回到法兰克福中的 SBC 传送。</span><span class="sxs-lookup"><span data-stu-id="397e9-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="397e9-117">由于 SBC 位于欧洲，Microsoft 使用最接近 SBC 的数据中心，因此已选中 "欧洲数据中心"。</span><span class="sxs-lookup"><span data-stu-id="397e9-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="397e9-118">虽然此方法不会影响在大多数地理区域内的 Microsoft 网络中的流量流量优化时的通话质量，但流量有不必要的循环。</span><span class="sxs-lookup"><span data-stu-id="397e9-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="397e9-119">**通过媒体绕过**，媒体将直接保留在团队用户和 SBC 之间，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="397e9-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

![显示媒体绕过的信号和媒体流](media/direct-routing-media-bypass-2.png)

<span data-ttu-id="397e9-121">媒体旁路利用在 SBC 上的团队客户端和 ICE lite 上称为交互式连接建立（ICE）的协议。</span><span class="sxs-lookup"><span data-stu-id="397e9-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="397e9-122">这些协议使直接路由能够使用最直接的媒体路径来获得最佳质量。</span><span class="sxs-lookup"><span data-stu-id="397e9-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="397e9-123">冰和 ICE Lite 是 WebRTC 标准。</span><span class="sxs-lookup"><span data-stu-id="397e9-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="397e9-124">有关这些协议的详细信息，请参阅 RFC 5245。</span><span class="sxs-lookup"><span data-stu-id="397e9-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="397e9-125">通话流程和防火墙规划</span><span class="sxs-lookup"><span data-stu-id="397e9-125">Call flow and firewall planning</span></span>

<span data-ttu-id="397e9-126">呼叫流程和防火墙规划取决于用户是否可以直接访问 SBC 的公共 IP 地址，以及用户是否在网络内部或外部。</span><span class="sxs-lookup"><span data-stu-id="397e9-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="397e9-127">如果用户对 SBC 的公共 IP 地址具有直接访问权限，则为呼叫流</span><span class="sxs-lookup"><span data-stu-id="397e9-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="397e9-128">如果用户对 SBC 的公共 IP 地址具有直接访问权限，则调用流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="397e9-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="397e9-129">对于媒体绕过，团队客户端必须有权访问 SBC 的公共 IP 地址（即使来自内部网络）。</span><span class="sxs-lookup"><span data-stu-id="397e9-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="397e9-130">如果直接媒体不是所需的，媒体可以通过传输中继进行通信。</span><span class="sxs-lookup"><span data-stu-id="397e9-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="397e9-131">当用户在与 SBC 相同的建筑物和/或网络中时，建议使用此方法-从媒体路径中删除 Microsoft 云组件。</span><span class="sxs-lookup"><span data-stu-id="397e9-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="397e9-132">信号始终通过 Microsoft 云发送流。</span><span class="sxs-lookup"><span data-stu-id="397e9-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="397e9-133">下图显示了启用媒体旁路时的调用流，客户端是内部客户端，并且客户端可以访问 SBC 的公共 IP 地址（直接媒体）：</span><span class="sxs-lookup"><span data-stu-id="397e9-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="397e9-134">路径的箭头和数值与[Microsoft 团队 "调用流](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)" 文章一致。</span><span class="sxs-lookup"><span data-stu-id="397e9-134">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="397e9-135">SIP 信号始终采用路径4和 4 "（具体取决于流量的方向）。</span><span class="sxs-lookup"><span data-stu-id="397e9-135">The SIP signaling always takes paths 4 and 4’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="397e9-136">媒体保持本地，并采用路径5b。</span><span class="sxs-lookup"><span data-stu-id="397e9-136">Media stays local and takes path 5b.</span></span>

![显示启用了媒体旁路的呼叫流，客户端为内部客户端](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="397e9-138">如果用户无权访问 SBC 的公共 IP 地址，则为呼叫流</span><span class="sxs-lookup"><span data-stu-id="397e9-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="397e9-139">如果用户无权访问 SBC 的公共 IP 地址，则以下描述调用流。</span><span class="sxs-lookup"><span data-stu-id="397e9-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="397e9-140">例如，假设用户是外部用户，并且租户管理员决定不将 SBC 的公共 IP 地址打开到 Internet 中的所有人，但仅限于 Microsoft Cloud。</span><span class="sxs-lookup"><span data-stu-id="397e9-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="397e9-141">流量的内部组件可以通过团队传输中继流出。</span><span class="sxs-lookup"><span data-stu-id="397e9-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="397e9-142">这是为企业网络外部的用户推荐的配置。</span><span class="sxs-lookup"><span data-stu-id="397e9-142">This is the recommended configuration for users outside of the corporate network.</span></span> <span data-ttu-id="397e9-143">请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="397e9-143">Consider the following:</span></span>

- <span data-ttu-id="397e9-144">使用团队传输中继。</span><span class="sxs-lookup"><span data-stu-id="397e9-144">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="397e9-145">对于媒体绕过，Microsoft 使用传输中继的版本，需要在团队传输中继和 SBC 之间打开端口 50 000 到 59 999 （将来我们计划移动到仅需要3478和3479端口的版本）。</span><span class="sxs-lookup"><span data-stu-id="397e9-145">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>

- <span data-ttu-id="397e9-146">对于媒体优化用途，Microsoft 建议仅将 SBC 的公共 IP 地址打开到团队传输中继。</span><span class="sxs-lookup"><span data-stu-id="397e9-146">For media optimization purposes, Microsoft recommends opening the public IP address of the SBC only to Teams Transport Relays.</span></span> <span data-ttu-id="397e9-147">对于公司网络外部的客户端，Microsoft 建议使用传输中继，而不是直接到达 SBC 的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="397e9-147">For clients outside of the corporate network, Microsoft recommends using Transport Relays instead of reaching the public IP address of the SBC directly.</span></span>

<span data-ttu-id="397e9-148">下图显示了启用媒体旁路时的调用流，客户端是外部的，并且客户端无法访问会话边界控制器的公共 IP 地址（媒体由团队传输中继进行中继）。</span><span class="sxs-lookup"><span data-stu-id="397e9-148">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="397e9-149">路径的箭头和数值与[Microsoft 团队 "调用流](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)" 文章一致。</span><span class="sxs-lookup"><span data-stu-id="397e9-149">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="397e9-150">媒体通过路径3、3 "、4和 4" 进行中继</span><span class="sxs-lookup"><span data-stu-id="397e9-150">Media is relayed via paths 3, 3', 4 and 4'</span></span>

![显示呼叫流（如果用户无权访问 SBC 的公共 IP）](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="397e9-152">如果用户在网络外部且拥有对 SBC 公共 IP 的访问权限，则为呼叫流</span><span class="sxs-lookup"><span data-stu-id="397e9-152">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="397e9-153">这不是建议的配置，因为它不会利用团队传输中继。</span><span class="sxs-lookup"><span data-stu-id="397e9-153">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="397e9-154">相反，你应该考虑以前的情况，即用户无法访问 SBC 的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="397e9-154">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="397e9-155">下图显示了启用媒体旁路时的调用流，客户端是外部的，并且客户端可以访问 SBC （直接媒体）的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="397e9-155">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="397e9-156">路径的箭头和数值与[Microsoft 团队 "调用流](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)" 文章一致。</span><span class="sxs-lookup"><span data-stu-id="397e9-156">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="397e9-157">SIP 信号始终采用路径3和 3 "（具体取决于流量的方向）。</span><span class="sxs-lookup"><span data-stu-id="397e9-157">The SIP signaling always takes paths 3 and 3’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="397e9-158">使用路径2进行媒体流。</span><span class="sxs-lookup"><span data-stu-id="397e9-158">Media flows using path 2.</span></span>

![显示呼叫流（如果用户无权访问 SBC 的公共 IP）](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="397e9-160">媒体处理器和传输中继的使用</span><span class="sxs-lookup"><span data-stu-id="397e9-160">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="397e9-161">Microsoft 云中有两个组件可以位于媒体流量的路径中：媒体处理器和传输中继。</span><span class="sxs-lookup"><span data-stu-id="397e9-161">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="397e9-162">媒体处理器是一个面向公众的组件，可在非绕过情况下处理媒体并处理语音应用程序媒体。</span><span class="sxs-lookup"><span data-stu-id="397e9-162">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="397e9-163">媒体处理器始终位于最终用户非绕过呼叫的路径中，但绝不会位于绕过呼叫的路径中。</span><span class="sxs-lookup"><span data-stu-id="397e9-163">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="397e9-164">媒体处理器始终位于所有语音应用程序的路径中，例如呼叫寄存、组织的自动助理和通话队列。</span><span class="sxs-lookup"><span data-stu-id="397e9-164">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="397e9-165">传输中继用于连接到最接近的传输服务以发送实时流量。</span><span class="sxs-lookup"><span data-stu-id="397e9-165">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="397e9-166">传输中继可能会（或可能不在绕过的呼叫）的路径中，具体取决于用户的位置和网络的配置方式。</span><span class="sxs-lookup"><span data-stu-id="397e9-166">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="397e9-167">下图显示了两个通话流-一个启用了媒体旁路，并且禁用了媒体旁路的第二个。</span><span class="sxs-lookup"><span data-stu-id="397e9-167">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="397e9-168">注意图表仅显示从--或目标到最终用户发起的流量。</span><span class="sxs-lookup"><span data-stu-id="397e9-168">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="397e9-169">媒体控制器是 Azure 中的 microservice，用于分配媒体处理器并创建会话描述协议（SDP）提供。</span><span class="sxs-lookup"><span data-stu-id="397e9-169">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="397e9-170">SIP 代理是将团队中使用的 HTTP REST 信号转换为 SIP 的组件。</span><span class="sxs-lookup"><span data-stu-id="397e9-170">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

![显示启用和禁用媒体旁路的呼叫流](media/direct-routing-media-bypass-6.png)


<span data-ttu-id="397e9-172">下表总结了媒体处理器和传输中继之间的区别。</span><span class="sxs-lookup"><span data-stu-id="397e9-172">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="397e9-173">媒体处理器</span><span class="sxs-lookup"><span data-stu-id="397e9-173">Media Processors</span></span> | <span data-ttu-id="397e9-174">传输中继</span><span class="sxs-lookup"><span data-stu-id="397e9-174">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="397e9-175">适用于最终用户的非绕过呼叫的媒体路径</span><span class="sxs-lookup"><span data-stu-id="397e9-175">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="397e9-176">都</span><span class="sxs-lookup"><span data-stu-id="397e9-176">Always</span></span> | <span data-ttu-id="397e9-177">绝对</span><span class="sxs-lookup"><span data-stu-id="397e9-177">Never</span></span> | 
<span data-ttu-id="397e9-178">适用于最终用户的绕过呼叫的媒体路径</span><span class="sxs-lookup"><span data-stu-id="397e9-178">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="397e9-179">绝对</span><span class="sxs-lookup"><span data-stu-id="397e9-179">Never</span></span> | <span data-ttu-id="397e9-180">如果客户无法访问公共 IP 地址上的 SBC</span><span class="sxs-lookup"><span data-stu-id="397e9-180">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="397e9-181">语音应用程序的媒体路径</span><span class="sxs-lookup"><span data-stu-id="397e9-181">In media path for voice applications</span></span> | <span data-ttu-id="397e9-182">都</span><span class="sxs-lookup"><span data-stu-id="397e9-182">Always</span></span> | <span data-ttu-id="397e9-183">绝对</span><span class="sxs-lookup"><span data-stu-id="397e9-183">Never</span></span> | 
<span data-ttu-id="397e9-184">可以执行转码（B2BUA）\*</span><span class="sxs-lookup"><span data-stu-id="397e9-184">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="397e9-185">是</span><span class="sxs-lookup"><span data-stu-id="397e9-185">Yes</span></span> | <span data-ttu-id="397e9-186">否，仅在终结点之间中继音频</span><span class="sxs-lookup"><span data-stu-id="397e9-186">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="397e9-187">全球实例数和位置</span><span class="sxs-lookup"><span data-stu-id="397e9-187">Number of instances worldwide and location</span></span> | <span data-ttu-id="397e9-188">总共8个：美国东部和西部2在阿姆斯特丹和都柏林中的2个;2在中国香港和新加坡中;在日本（在 Q1CY2019 中添加）的2</span><span class="sxs-lookup"><span data-stu-id="397e9-188">8 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan (being added in Q1CY2019)</span></span>  | <span data-ttu-id="397e9-189">名</span><span class="sxs-lookup"><span data-stu-id="397e9-189">Multiple</span></span>

<span data-ttu-id="397e9-190">IP 范围是 52.112.0.0/14 （从52.112.0.1 到52.115.255.254 的 IP 地址）。</span><span class="sxs-lookup"><span data-stu-id="397e9-190">The IP range is 52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span> 

<span data-ttu-id="397e9-191">\*代码解释解释：</span><span class="sxs-lookup"><span data-stu-id="397e9-191">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="397e9-192">媒体处理器是 B2BUA，这意味着它可以更改编解码器（例如，从团队客户端到 MP，以及 MP 和 SBC 之间的711）。</span><span class="sxs-lookup"><span data-stu-id="397e9-192">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="397e9-193">传输中继不是 B2BUA，这意味着在客户端和 SBC 之间不会更改编解码器-即使通信流通过中继流也是如此。</span><span class="sxs-lookup"><span data-stu-id="397e9-193">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="397e9-194">如果为媒体绕过配置了主干，则使用团队媒体处理器</span><span class="sxs-lookup"><span data-stu-id="397e9-194">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="397e9-195">在以下情况下，团队媒体处理器始终插入到媒体路径中：</span><span class="sxs-lookup"><span data-stu-id="397e9-195">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="397e9-196">通话从1:1 升级到群组通话</span><span class="sxs-lookup"><span data-stu-id="397e9-196">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="397e9-197">呼叫将转到联合团队用户</span><span class="sxs-lookup"><span data-stu-id="397e9-197">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="397e9-198">呼叫将转发或转移到 Skype for Business 用户</span><span class="sxs-lookup"><span data-stu-id="397e9-198">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="397e9-199">确保你的 SBC 有权访问媒体处理器和传输中继范围，如下所述。</span><span class="sxs-lookup"><span data-stu-id="397e9-199">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="397e9-200">SIP 信号： Fqdn</span><span class="sxs-lookup"><span data-stu-id="397e9-200">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="397e9-201">对于 SIP 信号，FQDN 和防火墙要求与非绕过事例的要求相同。</span><span class="sxs-lookup"><span data-stu-id="397e9-201">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="397e9-202">直接路由在以下 Office 365 环境中提供：</span><span class="sxs-lookup"><span data-stu-id="397e9-202">Direct Routing is offered in the following Office 365 environments:</span></span>
- <span data-ttu-id="397e9-203">Office 365</span><span class="sxs-lookup"><span data-stu-id="397e9-203">Office 365</span></span>
- <span data-ttu-id="397e9-204">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="397e9-204">Office 365 GCC</span></span>
- <span data-ttu-id="397e9-205">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="397e9-205">Office 365 GCC High</span></span>
- <span data-ttu-id="397e9-206">Office 365 DoD 了解有关[Office 365 和美国政府环境](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)（如 GCC、gcc 高级版和 DoD）的详细信息。</span><span class="sxs-lookup"><span data-stu-id="397e9-206">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="397e9-207">Office 365 和 Office 365 GCC 环境</span><span class="sxs-lookup"><span data-stu-id="397e9-207">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="397e9-208">直接路由的连接点是以下三个 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="397e9-208">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="397e9-209">**sip.pstnhub.microsoft.com** -必须首先尝试全局 FQDN。</span><span class="sxs-lookup"><span data-stu-id="397e9-209">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="397e9-210">当 SBC 发送一个请求来解析此名称时，Microsoft Azure DNS 服务器将返回指向分配给 SBC 的主 Azure 数据中心的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="397e9-210">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="397e9-211">该作业基于数据中心的性能指标和与 SBC 的地理位置的接近度。</span><span class="sxs-lookup"><span data-stu-id="397e9-211">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="397e9-212">返回的 IP 地址对应于主 FQDN。</span><span class="sxs-lookup"><span data-stu-id="397e9-212">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="397e9-213">**sip2.pstnhub.microsoft.com** -辅助 FQDN-地理位置映射到第二个优先级区域。</span><span class="sxs-lookup"><span data-stu-id="397e9-213">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="397e9-214">**sip3.pstnhub.microsoft.com** -第三方 FQDN-地理位置映射到第三个优先级区域。</span><span class="sxs-lookup"><span data-stu-id="397e9-214">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="397e9-215">必须放置这三个 Fqdn 才能：</span><span class="sxs-lookup"><span data-stu-id="397e9-215">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="397e9-216">提供最佳体验（加载时间最少且最接近通过查询第一个 FQDN 分配的 SBC 数据中心）。</span><span class="sxs-lookup"><span data-stu-id="397e9-216">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="397e9-217">在将来自 SBC 的连接建立到遇到暂时性问题的数据中心时提供故障转移。</span><span class="sxs-lookup"><span data-stu-id="397e9-217">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="397e9-218">有关详细信息，请参阅下面的故障转移机制。</span><span class="sxs-lookup"><span data-stu-id="397e9-218">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="397e9-219">Fqdn " **sip.pstnhub.microsoft.com**"、" **sip2.pstnhub.microsoft.com**" 和 " **sip3.pstnhub.microsoft.com** " 将解析为以下 IP 地址之一：</span><span class="sxs-lookup"><span data-stu-id="397e9-219">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="397e9-220">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="397e9-220">52.114.148.0</span></span>
- <span data-ttu-id="397e9-221">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="397e9-221">52.114.132.46</span></span>
- <span data-ttu-id="397e9-222">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="397e9-222">52.114.75.24</span></span>
- <span data-ttu-id="397e9-223">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="397e9-223">52.114.76.76</span></span>
- <span data-ttu-id="397e9-224">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="397e9-224">52.114.7.24</span></span>
- <span data-ttu-id="397e9-225">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="397e9-225">52.114.14.70</span></span>

<span data-ttu-id="397e9-226">您需要在防火墙中打开所有这些 IP 地址的端口，以允许传入和传出通信发送和接收来自地址的发送信号。</span><span class="sxs-lookup"><span data-stu-id="397e9-226">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="397e9-227">如果你的防火墙支持 DNS 名称，FQDN **sip-all.pstnhub.microsoft.com**将解析为所有这些 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="397e9-227">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="397e9-228">Office 365 GCC DoD 环境</span><span class="sxs-lookup"><span data-stu-id="397e9-228">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="397e9-229">直接路由的连接点是以下 FQDN：</span><span class="sxs-lookup"><span data-stu-id="397e9-229">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="397e9-230">**sip.pstnhub.dod.teams.microsoft.us** -全局 FQDN。</span><span class="sxs-lookup"><span data-stu-id="397e9-230">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="397e9-231">由于 Office 365 DoD 环境仅存在于美国数据中心，因此没有第二个和第三个 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="397e9-231">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="397e9-232">Fqdn-sip.pstnhub.dod.teams.microsoft.us 将解析为以下 IP 地址之一：</span><span class="sxs-lookup"><span data-stu-id="397e9-232">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="397e9-233">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="397e9-233">52.127.64.33</span></span>
- <span data-ttu-id="397e9-234">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="397e9-234">52.127.68.34</span></span>

<span data-ttu-id="397e9-235">您需要在防火墙中打开所有这些 IP 地址的端口，以允许传入和传出通信发送和接收来自地址的发送信号。</span><span class="sxs-lookup"><span data-stu-id="397e9-235">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="397e9-236">如果你的防火墙支持 DNS 名称，FQDN sip.pstnhub.dod.teams.microsoft.us 将解析为所有这些 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="397e9-236">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="397e9-237">Office 365 GCC 高环境</span><span class="sxs-lookup"><span data-stu-id="397e9-237">Office 365 GCC High environment</span></span>

<span data-ttu-id="397e9-238">直接路由的连接点是以下 FQDN：</span><span class="sxs-lookup"><span data-stu-id="397e9-238">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="397e9-239">**sip.pstnhub.gov.teams.microsoft.us** -全局 FQDN。</span><span class="sxs-lookup"><span data-stu-id="397e9-239">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="397e9-240">由于 GCC 的高环境仅存在于美国数据中心，因此没有第二个和第三个 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="397e9-240">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="397e9-241">Fqdn-sip.pstnhub.gov.teams.microsoft.us 将解析为以下 IP 地址之一：</span><span class="sxs-lookup"><span data-stu-id="397e9-241">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="397e9-242">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="397e9-242">52.127.88.59</span></span>
- <span data-ttu-id="397e9-243">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="397e9-243">52.127.92.64</span></span>

<span data-ttu-id="397e9-244">您需要在防火墙中打开所有这些 IP 地址的端口，以允许传入和传出通信发送和接收来自地址的发送信号。</span><span class="sxs-lookup"><span data-stu-id="397e9-244">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="397e9-245">如果你的防火墙支持 DNS 名称，FQDN sip.pstnhub.gov.teams.microsoft.us 将解析为所有这些 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="397e9-245">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="397e9-246">SIP 信号：端口</span><span class="sxs-lookup"><span data-stu-id="397e9-246">SIP Signaling: Ports</span></span>

<span data-ttu-id="397e9-247">对于提供直接路由的所有 Office 365 环境，端口要求是相同的：</span><span class="sxs-lookup"><span data-stu-id="397e9-247">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="397e9-248">Office 365</span><span class="sxs-lookup"><span data-stu-id="397e9-248">Office 365</span></span>
- <span data-ttu-id="397e9-249">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="397e9-249">Office 365 GCC</span></span>
- <span data-ttu-id="397e9-250">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="397e9-250">Office 365 GCC High</span></span>
- <span data-ttu-id="397e9-251">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="397e9-251">Office 365 DoD</span></span>

<span data-ttu-id="397e9-252">您必须使用以下端口：</span><span class="sxs-lookup"><span data-stu-id="397e9-252">You must use the following ports:</span></span>

| <span data-ttu-id="397e9-253">流量</span><span class="sxs-lookup"><span data-stu-id="397e9-253">Traffic</span></span> | <span data-ttu-id="397e9-254">从</span><span class="sxs-lookup"><span data-stu-id="397e9-254">From</span></span> | <span data-ttu-id="397e9-255">到</span><span class="sxs-lookup"><span data-stu-id="397e9-255">To</span></span> | <span data-ttu-id="397e9-256">源端口</span><span class="sxs-lookup"><span data-stu-id="397e9-256">Source port</span></span> | <span data-ttu-id="397e9-257">目标端口</span><span class="sxs-lookup"><span data-stu-id="397e9-257">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="397e9-258">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="397e9-258">SIP/TLS</span></span>| <span data-ttu-id="397e9-259">SIP 代理</span><span class="sxs-lookup"><span data-stu-id="397e9-259">SIP Proxy</span></span> | <span data-ttu-id="397e9-260">SBC</span><span class="sxs-lookup"><span data-stu-id="397e9-260">SBC</span></span> | <span data-ttu-id="397e9-261">1024-65535</span><span class="sxs-lookup"><span data-stu-id="397e9-261">1024 - 65535</span></span> | <span data-ttu-id="397e9-262">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="397e9-262">Defined on the SBC</span></span> |
| <span data-ttu-id="397e9-263">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="397e9-263">SIP/TLS</span></span> | <span data-ttu-id="397e9-264">SBC</span><span class="sxs-lookup"><span data-stu-id="397e9-264">SBC</span></span> | <span data-ttu-id="397e9-265">SIP 代理</span><span class="sxs-lookup"><span data-stu-id="397e9-265">SIP Proxy</span></span> | <span data-ttu-id="397e9-266">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="397e9-266">Defined on the SBC</span></span> | <span data-ttu-id="397e9-267">5061</span><span class="sxs-lookup"><span data-stu-id="397e9-267">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="397e9-268">媒体流量： IP 和端口范围</span><span class="sxs-lookup"><span data-stu-id="397e9-268">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="397e9-269">如果客户无法使用公共 IP 地址访问 SBC，则在 SBC 和团队客户端之间进行媒体通信流（如果直接连接可用或通过团队传输中继）。</span><span class="sxs-lookup"><span data-stu-id="397e9-269">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="397e9-270">直接媒体流量的要求（团队客户端和 SBC 之间）</span><span class="sxs-lookup"><span data-stu-id="397e9-270">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="397e9-271">客户端必须具有对 SBC 公共 IP 地址的指定端口（见表）的访问权限。</span><span class="sxs-lookup"><span data-stu-id="397e9-271">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="397e9-272">注意：如果客户端在内部网络中，则媒体将流向 SBC 的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="397e9-272">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="397e9-273">你可以在你的 NAT 设备上配置头发固定，以便流量永远不会离开企业网络设备。</span><span class="sxs-lookup"><span data-stu-id="397e9-273">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="397e9-274">流量</span><span class="sxs-lookup"><span data-stu-id="397e9-274">Traffic</span></span> | <span data-ttu-id="397e9-275">从</span><span class="sxs-lookup"><span data-stu-id="397e9-275">From</span></span> | <span data-ttu-id="397e9-276">到</span><span class="sxs-lookup"><span data-stu-id="397e9-276">To</span></span> | <span data-ttu-id="397e9-277">源端口</span><span class="sxs-lookup"><span data-stu-id="397e9-277">Source port</span></span> | <span data-ttu-id="397e9-278">目标端口</span><span class="sxs-lookup"><span data-stu-id="397e9-278">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="397e9-279">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="397e9-279">UDP/SRTP</span></span> | <span data-ttu-id="397e9-280">客户端</span><span class="sxs-lookup"><span data-stu-id="397e9-280">Client</span></span> | <span data-ttu-id="397e9-281">SBC</span><span class="sxs-lookup"><span data-stu-id="397e9-281">SBC</span></span> | <span data-ttu-id="397e9-282">50 000-50 019</span><span class="sxs-lookup"><span data-stu-id="397e9-282">50 000 – 50 019</span></span>  | <span data-ttu-id="397e9-283">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="397e9-283">Defined on the SBC</span></span> |
| <span data-ttu-id="397e9-284">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="397e9-284">UDP/SRTP</span></span> | <span data-ttu-id="397e9-285">SBC</span><span class="sxs-lookup"><span data-stu-id="397e9-285">SBC</span></span> | <span data-ttu-id="397e9-286">客户端</span><span class="sxs-lookup"><span data-stu-id="397e9-286">Client</span></span> | <span data-ttu-id="397e9-287">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="397e9-287">Defined on the SBC</span></span> | <span data-ttu-id="397e9-288">50 000-50 019</span><span class="sxs-lookup"><span data-stu-id="397e9-288">50 000 – 50 019</span></span>  |


<span data-ttu-id="397e9-289">注意：如果你有转换客户端源端口的网络设备，请确保在网络设备和 SBC 之间打开已转换的端口。</span><span class="sxs-lookup"><span data-stu-id="397e9-289">Note: If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="397e9-290">使用传输中继的要求</span><span class="sxs-lookup"><span data-stu-id="397e9-290">Requirements for using Transport Relays</span></span>

<span data-ttu-id="397e9-291">传输中继与媒体处理器位于同一范围内（对于非绕过的情况）：</span><span class="sxs-lookup"><span data-stu-id="397e9-291">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="397e9-292">Office 365 和 Office 365 GCC 环境</span><span class="sxs-lookup"><span data-stu-id="397e9-292">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="397e9-293">-52.112.0.0/14 （从52.112.0.1 到52.115.255.254 的 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="397e9-293">-52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="397e9-294">Office 365 GCC DoD 环境</span><span class="sxs-lookup"><span data-stu-id="397e9-294">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="397e9-295">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="397e9-295">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="397e9-296">Office 365 GCC 高环境</span><span class="sxs-lookup"><span data-stu-id="397e9-296">Office 365 GCC High environment</span></span>

- <span data-ttu-id="397e9-297">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="397e9-297">52.127.88.0/21</span></span>


<span data-ttu-id="397e9-298">下表显示了团队传输中继的端口范围（适用于所有环境）：</span><span class="sxs-lookup"><span data-stu-id="397e9-298">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="397e9-299">流量</span><span class="sxs-lookup"><span data-stu-id="397e9-299">Traffic</span></span> | <span data-ttu-id="397e9-300">从</span><span class="sxs-lookup"><span data-stu-id="397e9-300">From</span></span> | <span data-ttu-id="397e9-301">到</span><span class="sxs-lookup"><span data-stu-id="397e9-301">To</span></span> | <span data-ttu-id="397e9-302">源端口</span><span class="sxs-lookup"><span data-stu-id="397e9-302">Source port</span></span> | <span data-ttu-id="397e9-303">目标端口</span><span class="sxs-lookup"><span data-stu-id="397e9-303">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="397e9-304">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="397e9-304">UDP/SRTP</span></span> | <span data-ttu-id="397e9-305">传输中继</span><span class="sxs-lookup"><span data-stu-id="397e9-305">Transport Relay</span></span> | <span data-ttu-id="397e9-306">SBC</span><span class="sxs-lookup"><span data-stu-id="397e9-306">SBC</span></span> | <span data-ttu-id="397e9-307">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="397e9-307">50 000 -59 999</span></span>    | <span data-ttu-id="397e9-308">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="397e9-308">Defined on the SBC</span></span> |
| <span data-ttu-id="397e9-309">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="397e9-309">UDP/SRTP</span></span> | <span data-ttu-id="397e9-310">SBC</span><span class="sxs-lookup"><span data-stu-id="397e9-310">SBC</span></span> | <span data-ttu-id="397e9-311">传输中继</span><span class="sxs-lookup"><span data-stu-id="397e9-311">Transport Relay</span></span> | <span data-ttu-id="397e9-312">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="397e9-312">Defined on the SBC</span></span> | <span data-ttu-id="397e9-313">50 000-59 999、3478、3479</span><span class="sxs-lookup"><span data-stu-id="397e9-313">50 000 – 59 999, 3478, 3479</span></span>     |


<span data-ttu-id="397e9-314">注意： Microsoft 建议在 SBC 上对每个并发调用至少有两个端口。</span><span class="sxs-lookup"><span data-stu-id="397e9-314">Note: Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="397e9-315">由于 Microsoft 具有两个版本的传输中继，因此需要以下内容：</span><span class="sxs-lookup"><span data-stu-id="397e9-315">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>

- <span data-ttu-id="397e9-316">v4，它只能使用端口范围 50 000 到 59 999</span><span class="sxs-lookup"><span data-stu-id="397e9-316">v4, which can only work with port range 50 000 to 59 999</span></span>

- <span data-ttu-id="397e9-317">v6，它适用于端口3478、3479</span><span class="sxs-lookup"><span data-stu-id="397e9-317">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="397e9-318">此时，媒体绕过仅支持传输中继的 v4 版本。</span><span class="sxs-lookup"><span data-stu-id="397e9-318">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="397e9-319">我们将在将来介绍 v6 的支持。</span><span class="sxs-lookup"><span data-stu-id="397e9-319">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="397e9-320">您需要打开端口3478和3479以进行转换。</span><span class="sxs-lookup"><span data-stu-id="397e9-320">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="397e9-321">当 Microsoft 为具有媒体旁路的 v6 传输中继提供支持时，不需要重新配置网络设备或 SBCs。</span><span class="sxs-lookup"><span data-stu-id="397e9-321">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="397e9-322">使用媒体处理器的要求</span><span class="sxs-lookup"><span data-stu-id="397e9-322">Requirements for using media processors</span></span>

<span data-ttu-id="397e9-323">媒体处理器始终位于语音应用程序和 Web 客户端（如 Edge 或 Google Chrome 中的团队客户端）的媒体路径中。</span><span class="sxs-lookup"><span data-stu-id="397e9-323">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="397e9-324">要求与非绕过配置相同。</span><span class="sxs-lookup"><span data-stu-id="397e9-324">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="397e9-325">媒体流量的 IP 范围是</span><span class="sxs-lookup"><span data-stu-id="397e9-325">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="397e9-326">Office 365 和 Office 365 GCC 环境</span><span class="sxs-lookup"><span data-stu-id="397e9-326">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="397e9-327">-52.112.0.0/14 （从52.112.0.1 到52.115.255.254 的 IP 地址）</span><span class="sxs-lookup"><span data-stu-id="397e9-327">-52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="397e9-328">Office 365 GCC DoD 环境</span><span class="sxs-lookup"><span data-stu-id="397e9-328">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="397e9-329">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="397e9-329">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="397e9-330">Office 365 GCC 高环境</span><span class="sxs-lookup"><span data-stu-id="397e9-330">Office 365 GCC High environment</span></span>

- <span data-ttu-id="397e9-331">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="397e9-331">52.127.88.0/21</span></span>

<span data-ttu-id="397e9-332">下表显示了媒体处理器的端口范围（适用于所有环境）：</span><span class="sxs-lookup"><span data-stu-id="397e9-332">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="397e9-333">流量</span><span class="sxs-lookup"><span data-stu-id="397e9-333">Traffic</span></span> | <span data-ttu-id="397e9-334">从</span><span class="sxs-lookup"><span data-stu-id="397e9-334">From</span></span> | <span data-ttu-id="397e9-335">到</span><span class="sxs-lookup"><span data-stu-id="397e9-335">To</span></span> | <span data-ttu-id="397e9-336">源端口</span><span class="sxs-lookup"><span data-stu-id="397e9-336">Source port</span></span> | <span data-ttu-id="397e9-337">目标端口</span><span class="sxs-lookup"><span data-stu-id="397e9-337">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="397e9-338">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="397e9-338">UDP/SRTP</span></span> | <span data-ttu-id="397e9-339">媒体处理器</span><span class="sxs-lookup"><span data-stu-id="397e9-339">Media Processor</span></span> | <span data-ttu-id="397e9-340">SBC</span><span class="sxs-lookup"><span data-stu-id="397e9-340">SBC</span></span> | <span data-ttu-id="397e9-341">49 152-53 247</span><span class="sxs-lookup"><span data-stu-id="397e9-341">49 152 – 53 247</span></span>    | <span data-ttu-id="397e9-342">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="397e9-342">Defined on the SBC</span></span> |
| <span data-ttu-id="397e9-343">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="397e9-343">UDP/SRTP</span></span> | <span data-ttu-id="397e9-344">SBC</span><span class="sxs-lookup"><span data-stu-id="397e9-344">SBC</span></span> | <span data-ttu-id="397e9-345">媒体处理器</span><span class="sxs-lookup"><span data-stu-id="397e9-345">Media Processor</span></span> | <span data-ttu-id="397e9-346">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="397e9-346">Defined on the SBC</span></span> | <span data-ttu-id="397e9-347">49 152-53 247</span><span class="sxs-lookup"><span data-stu-id="397e9-347">49 152 – 53 247</span></span>     |

## <a name="considerations-if-you-have-skype-for-business-phones-in-your-network"></a><span data-ttu-id="397e9-348">在网络中使用 Skype for business 电话时的注意事项</span><span class="sxs-lookup"><span data-stu-id="397e9-348">Considerations if you have Skype for Business phones in your network</span></span>  

<span data-ttu-id="397e9-349">如果您的网络中有任何使用直接路由的 Skype for Business 终结点（例如，团队用户可以拥有基于 Skype for Business 客户端的3PIP 电话），则为这些用户提供服务的主干上的媒体旁路必须处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="397e9-349">If you have any Skype for Business end points in your network that are using Direct Routing--for example, a Teams user can have a 3PIP phone that is based on Skype for Business client--the media bypass on the trunk that serves these users must be turned off.</span></span>

<span data-ttu-id="397e9-350">你可以为这些用户创建单独的 trunk，并为其分配联机语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="397e9-350">You can create a separate trunk for these users and assign it an Online Voice Routing policy.</span></span>

<span data-ttu-id="397e9-351">高级别配置步骤：</span><span class="sxs-lookup"><span data-stu-id="397e9-351">High-level configuration steps:</span></span>

- <span data-ttu-id="397e9-352">按类型拆分用户-取决于用户是否具有3PIP 电话。</span><span class="sxs-lookup"><span data-stu-id="397e9-352">Split users by type – depending on whether the user has a 3PIP phone or not.</span></span>

- <span data-ttu-id="397e9-353">使用不同的 Fqdn 创建两个单独的中继：一个为媒体绕过启用;另一个不是。</span><span class="sxs-lookup"><span data-stu-id="397e9-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="397e9-354">这两个中继指向同一个 SBC。</span><span class="sxs-lookup"><span data-stu-id="397e9-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="397e9-355">TLS SIP 信号的端口必须不同。</span><span class="sxs-lookup"><span data-stu-id="397e9-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="397e9-356">媒体端口必须相同。</span><span class="sxs-lookup"><span data-stu-id="397e9-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="397e9-357">根据联机语音路由策略中的用户类型分配正确的主干。</span><span class="sxs-lookup"><span data-stu-id="397e9-357">Assign the correct trunk depending on the type of the user in the Online Voice Routing policy.</span></span>

<span data-ttu-id="397e9-358">下面的示例演示了此逻辑。</span><span class="sxs-lookup"><span data-stu-id="397e9-358">The example below illustrates this logic.</span></span>

| <span data-ttu-id="397e9-359">组用户</span><span class="sxs-lookup"><span data-stu-id="397e9-359">Set of users</span></span> | <span data-ttu-id="397e9-360">用户数</span><span class="sxs-lookup"><span data-stu-id="397e9-360">Number of users</span></span> | <span data-ttu-id="397e9-361">在 OVRP 中分配的中继 FQDN</span><span class="sxs-lookup"><span data-stu-id="397e9-361">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="397e9-362">媒体绕过启用</span><span class="sxs-lookup"><span data-stu-id="397e9-362">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="397e9-363">具有团队客户端和3PIP 手机的用户</span><span class="sxs-lookup"><span data-stu-id="397e9-363">Users with Teams clients and 3PIP phones</span></span> | <span data-ttu-id="397e9-364">名</span><span class="sxs-lookup"><span data-stu-id="397e9-364">20</span></span> | <span data-ttu-id="397e9-365">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="397e9-365">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="397e9-366">false</span><span class="sxs-lookup"><span data-stu-id="397e9-366">false</span></span> | 
<span data-ttu-id="397e9-367">只有团队终结点（包括为团队认证的新电话）的用户</span><span class="sxs-lookup"><span data-stu-id="397e9-367">Users with only Teams end points (including new phones certified for Teams)</span></span> | <span data-ttu-id="397e9-368">980</span><span class="sxs-lookup"><span data-stu-id="397e9-368">980</span></span> | <span data-ttu-id="397e9-369">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="397e9-369">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="397e9-370">true</span><span class="sxs-lookup"><span data-stu-id="397e9-370">true</span></span>

<span data-ttu-id="397e9-371">这两个中继都可以指向具有相同公共 IP 地址的同一 SBC。</span><span class="sxs-lookup"><span data-stu-id="397e9-371">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="397e9-372">SBC 的 TLS 信号端口必须不同，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="397e9-372">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="397e9-373">注意你需要确保你的证书支持这两个中继。</span><span class="sxs-lookup"><span data-stu-id="397e9-373">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="397e9-374">在 SAN 中，你需要具有两个名称（**sbc1.contoso.com**和**sbc2.contoso.com**）或具有通配符证书。</span><span class="sxs-lookup"><span data-stu-id="397e9-374">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>


![显示两个中继都可以指向具有相同公共 IP 的同一 SBC](media/direct-routing-media-bypass-7.png)

<span data-ttu-id="397e9-376">有关如何在同一 SBC 上配置两个中继的信息，请参阅 SBC 供应商提供的文档：</span><span class="sxs-lookup"><span data-stu-id="397e9-376">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="397e9-377">AudioCodes 部署文档</span><span class="sxs-lookup"><span data-stu-id="397e9-377">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="397e9-378">Oracle 部署文档</span><span class="sxs-lookup"><span data-stu-id="397e9-378">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="397e9-379">功能区通信部署文档</span><span class="sxs-lookup"><span data-stu-id="397e9-379">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="397e9-380">TE-系统（anynode）部署文档</span><span class="sxs-lookup"><span data-stu-id="397e9-380">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="397e9-381">媒体绕过支持的客户端终结点</span><span class="sxs-lookup"><span data-stu-id="397e9-381">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="397e9-382">所有团队终结点都支持媒体绕过。</span><span class="sxs-lookup"><span data-stu-id="397e9-382">Media bypass is supported with all Teams endpoints.</span></span>

<span data-ttu-id="397e9-383">注意对于 web 客户端（Microsoft Edge 中的 "团队" Web 应用、Google Chrome 或 Mozilla Firefox），我们会将调用转换为非旁路，即使它作为绕过调用启动也是如此。</span><span class="sxs-lookup"><span data-stu-id="397e9-383">Note for web clients (Teams Web app in Microsoft Edge, Google Chrome or Mozilla Firefox) we will covert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="397e9-384">这会自动发生，不需要管理员执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="397e9-384">This happens automatically and does not require any actions from the administrator.</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="397e9-385">另请参阅</span><span class="sxs-lookup"><span data-stu-id="397e9-385">See also</span></span>

[<span data-ttu-id="397e9-386">使用直接路由配置媒体旁路</span><span class="sxs-lookup"><span data-stu-id="397e9-386">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)



