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
description: 了解如何使用手机系统直接路由规划媒体旁路，这使你能够缩短媒体流量的路径并提高性能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: efd6d4275d1e83df7821f178ddac8027039b6fce
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790654"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="467e3-103">使用直接路由规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="467e3-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="467e3-104">关于直接路由的媒体旁路</span><span class="sxs-lookup"><span data-stu-id="467e3-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="467e3-105">媒体绕过使你可以缩短媒体流量的路径，并减少传输中的跃点数，从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="467e3-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="467e3-106">通过媒体绕过，媒体将保留在会话边界控制器 (SBC) 和客户端之间，而不是通过 Microsoft Phone 系统发送。</span><span class="sxs-lookup"><span data-stu-id="467e3-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="467e3-107">要配置绕过媒体，SBC 和客户端必须位于同一位置或网络。</span><span class="sxs-lookup"><span data-stu-id="467e3-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="467e3-108">你可以通过使用 **CSOnlinePSTNGateway** 命令，将 **-MediaBypass** 参数设置为 true 或 false 来控制每个 SBC 的媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="467e3-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="467e3-109">如果启用 "媒体绕过"，这并不意味着所有媒体流量都将保留在公司网络中。</span><span class="sxs-lookup"><span data-stu-id="467e3-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="467e3-110">本文介绍不同方案中的调用流。</span><span class="sxs-lookup"><span data-stu-id="467e3-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="467e3-111">下图展示了通话流程的区别和不使用媒体旁路的情况。</span><span class="sxs-lookup"><span data-stu-id="467e3-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="467e3-112">如果不使用媒体绕过，则在客户端发出或接收呼叫时，SBC、Microsoft Phone 系统和团队客户端之间的信号和媒体流均为，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="467e3-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="467e3-113">![显示不使用媒体旁路的信号和媒体流](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="467e3-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="467e3-114">但是，假设用户与 SBC 位于同一建筑物或网络中。</span><span class="sxs-lookup"><span data-stu-id="467e3-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="467e3-115">例如，假设法兰克福中的大楼的用户拨打 PSTN 用户的电话：</span><span class="sxs-lookup"><span data-stu-id="467e3-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="467e3-116">如果 **没有媒体绕过** ，则媒体将通过阿姆斯特丹或都柏林 (进行通信，其中 Microsoft 数据中心) 部署到法兰克福中的 SBC。</span><span class="sxs-lookup"><span data-stu-id="467e3-116">**Without media bypass** , media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="467e3-117">由于 SBC 位于欧洲，Microsoft 使用最接近 SBC 的数据中心，因此已选中 "欧洲数据中心"。</span><span class="sxs-lookup"><span data-stu-id="467e3-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="467e3-118">虽然此方法不会影响在大多数地理区域内的 Microsoft 网络中的流量流量优化时的通话质量，但流量有不必要的循环。</span><span class="sxs-lookup"><span data-stu-id="467e3-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="467e3-119">**通过媒体绕过** ，媒体将直接保留在团队用户和 SBC 之间，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="467e3-119">**With media bypass** , the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="467e3-120">![显示媒体绕过的信号和媒体流](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="467e3-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="467e3-121">媒体旁路利用称为交互式连接的协议在 SBC 上 (ICE) 团队客户端和 ICE 精简。</span><span class="sxs-lookup"><span data-stu-id="467e3-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="467e3-122">这些协议使直接路由能够使用最直接的媒体路径来获得最佳质量。</span><span class="sxs-lookup"><span data-stu-id="467e3-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="467e3-123">冰和 ICE Lite 是 WebRTC 标准。</span><span class="sxs-lookup"><span data-stu-id="467e3-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="467e3-124">有关这些协议的详细信息，请参阅 RFC 5245。</span><span class="sxs-lookup"><span data-stu-id="467e3-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="467e3-125">通话流程和防火墙规划</span><span class="sxs-lookup"><span data-stu-id="467e3-125">Call flow and firewall planning</span></span>

<span data-ttu-id="467e3-126">呼叫流程和防火墙规划取决于用户是否可以直接访问 SBC 的公共 IP 地址，以及用户是否在网络内部或外部。</span><span class="sxs-lookup"><span data-stu-id="467e3-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="467e3-127">如果用户对 SBC 的公共 IP 地址具有直接访问权限，则为呼叫流</span><span class="sxs-lookup"><span data-stu-id="467e3-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="467e3-128">如果用户对 SBC 的公共 IP 地址具有直接访问权限，则调用流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="467e3-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="467e3-129">对于媒体绕过，团队客户端必须有权访问 SBC 的公共 IP 地址（即使来自内部网络）。</span><span class="sxs-lookup"><span data-stu-id="467e3-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="467e3-130">如果直接媒体不是所需的，媒体可以通过传输中继进行通信。</span><span class="sxs-lookup"><span data-stu-id="467e3-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="467e3-131">当用户在与 SBC 相同的建筑物和/或网络中时，建议使用此方法-从媒体路径中删除 Microsoft 云组件。</span><span class="sxs-lookup"><span data-stu-id="467e3-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="467e3-132">信号始终通过 Microsoft 云发送流。</span><span class="sxs-lookup"><span data-stu-id="467e3-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="467e3-133">下图显示了启用媒体旁路时的呼叫流，客户端是内部客户端，并且客户端可以访问 SBC 的公共 IP 地址 (直接媒体) ：</span><span class="sxs-lookup"><span data-stu-id="467e3-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="467e3-134">路径的箭头和数值与 [Microsoft 团队通话流](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)相符。</span><span class="sxs-lookup"><span data-stu-id="467e3-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span></span>

- <span data-ttu-id="467e3-135">SIP 信号始终采用路径4和 4 " (，具体取决于流量) 的方向。</span><span class="sxs-lookup"><span data-stu-id="467e3-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="467e3-136">媒体保持本地，并采用路径5b。</span><span class="sxs-lookup"><span data-stu-id="467e3-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="467e3-137">![显示启用了媒体旁路的呼叫流，客户端为内部客户端](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="467e3-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="467e3-138">如果用户无权访问 SBC 的公共 IP 地址，则为呼叫流</span><span class="sxs-lookup"><span data-stu-id="467e3-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="467e3-139">如果用户无权访问 SBC 的公共 IP 地址，则以下描述调用流。</span><span class="sxs-lookup"><span data-stu-id="467e3-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="467e3-140">例如，假设用户是外部用户，并且租户管理员决定不将 SBC 的公共 IP 地址打开到 Internet 中的所有人，但仅限于 Microsoft Cloud。</span><span class="sxs-lookup"><span data-stu-id="467e3-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="467e3-141">流量的内部组件可以通过团队传输中继流出。</span><span class="sxs-lookup"><span data-stu-id="467e3-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="467e3-142">比如以下几种情况：</span><span class="sxs-lookup"><span data-stu-id="467e3-142">Consider the following:</span></span>

- <span data-ttu-id="467e3-143">使用团队传输中继。</span><span class="sxs-lookup"><span data-stu-id="467e3-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="467e3-144">对于媒体旁路，Microsoft 使用传输中继的版本，需要在团队传输中继和 SBC (之间打开端口 50 000 到 59 999，我们计划移动到仅需要3478和3479端口) 的版本。</span><span class="sxs-lookup"><span data-stu-id="467e3-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>


<span data-ttu-id="467e3-145">下图显示了启用媒体跳过后的呼叫流，客户端是外部的，并且客户端无法访问会话边界控制器的公共 IP 地址 (媒体由团队传输中继) 中继。</span><span class="sxs-lookup"><span data-stu-id="467e3-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="467e3-146">路径的箭头和数值与 [Microsoft 团队通话流](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)相符。</span><span class="sxs-lookup"><span data-stu-id="467e3-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows).</span></span>

- <span data-ttu-id="467e3-147">媒体通过路径3、3 "、4和 4" 进行中继</span><span class="sxs-lookup"><span data-stu-id="467e3-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="467e3-148">![显示呼叫流（如果用户无权访问 SBC 的公共 IP）](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="467e3-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="467e3-149">如果用户在网络外部且拥有对 SBC 公共 IP 的访问权限，则为呼叫流</span><span class="sxs-lookup"><span data-stu-id="467e3-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="467e3-150">这不是建议的配置，因为它不会利用团队传输中继。</span><span class="sxs-lookup"><span data-stu-id="467e3-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="467e3-151">相反，你应该考虑以前的情况，即用户无法访问 SBC 的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="467e3-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="467e3-152">下图显示了启用媒体旁路时的呼叫流，客户端是外部的，并且客户端可以访问 SBC 的公共 IP 地址 (直接媒体) 。</span><span class="sxs-lookup"><span data-stu-id="467e3-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="467e3-153">路径的箭头和数值与 [Microsoft 团队 "调用流](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) " 文章一致。</span><span class="sxs-lookup"><span data-stu-id="467e3-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="467e3-154">SIP 信号始终采用路径3和 3 " (，具体取决于流量) 的方向。</span><span class="sxs-lookup"><span data-stu-id="467e3-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="467e3-155">使用路径2进行媒体流。</span><span class="sxs-lookup"><span data-stu-id="467e3-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="467e3-156">![显示呼叫流（如果用户无权访问 SBC 的公共 IP）](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="467e3-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="467e3-157">媒体处理器和传输中继的使用</span><span class="sxs-lookup"><span data-stu-id="467e3-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="467e3-158">Microsoft 云中有两个组件可以位于媒体流量的路径中：媒体处理器和传输中继。</span><span class="sxs-lookup"><span data-stu-id="467e3-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="467e3-159">媒体处理器是一个面向公众的组件，可在非绕过情况下处理媒体并处理语音应用程序媒体。</span><span class="sxs-lookup"><span data-stu-id="467e3-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="467e3-160">媒体处理器始终位于最终用户非绕过呼叫的路径中，但绝不会位于绕过呼叫的路径中。</span><span class="sxs-lookup"><span data-stu-id="467e3-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="467e3-161">媒体处理器始终位于所有语音应用程序的路径中，例如呼叫寄存、组织的自动助理和通话队列。</span><span class="sxs-lookup"><span data-stu-id="467e3-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="467e3-162">传输中继用于连接到最接近的传输服务以发送实时流量。</span><span class="sxs-lookup"><span data-stu-id="467e3-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="467e3-163">传输中继可能会（或可能不在绕过的呼叫）的路径中，具体取决于用户的位置和网络的配置方式。</span><span class="sxs-lookup"><span data-stu-id="467e3-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="467e3-164">下图显示了两个通话流-一个启用了媒体旁路，并且禁用了媒体旁路的第二个。</span><span class="sxs-lookup"><span data-stu-id="467e3-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="467e3-165">注意图表仅显示从--或目标到最终用户发起的流量。</span><span class="sxs-lookup"><span data-stu-id="467e3-165">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="467e3-166">媒体控制器是 Azure 中的 microservice，用于分配媒体处理器并创建会话描述协议 (SDP) 提供。</span><span class="sxs-lookup"><span data-stu-id="467e3-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="467e3-167">SIP 代理是将团队中使用的 HTTP REST 信号转换为 SIP 的组件。</span><span class="sxs-lookup"><span data-stu-id="467e3-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="467e3-168">![显示启用和禁用媒体旁路的呼叫流](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="467e3-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="467e3-169">下表总结了媒体处理器和传输中继之间的区别。</span><span class="sxs-lookup"><span data-stu-id="467e3-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="467e3-170">媒体处理器</span><span class="sxs-lookup"><span data-stu-id="467e3-170">Media Processors</span></span> | <span data-ttu-id="467e3-171">传输中继</span><span class="sxs-lookup"><span data-stu-id="467e3-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="467e3-172">适用于最终用户的非绕过呼叫的媒体路径</span><span class="sxs-lookup"><span data-stu-id="467e3-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="467e3-173">都</span><span class="sxs-lookup"><span data-stu-id="467e3-173">Always</span></span> | <span data-ttu-id="467e3-174">绝对</span><span class="sxs-lookup"><span data-stu-id="467e3-174">Never</span></span> | 
<span data-ttu-id="467e3-175">适用于最终用户的绕过呼叫的媒体路径</span><span class="sxs-lookup"><span data-stu-id="467e3-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="467e3-176">绝对</span><span class="sxs-lookup"><span data-stu-id="467e3-176">Never</span></span> | <span data-ttu-id="467e3-177">如果客户无法访问公共 IP 地址上的 SBC</span><span class="sxs-lookup"><span data-stu-id="467e3-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="467e3-178">语音应用程序的媒体路径</span><span class="sxs-lookup"><span data-stu-id="467e3-178">In media path for voice applications</span></span> | <span data-ttu-id="467e3-179">都</span><span class="sxs-lookup"><span data-stu-id="467e3-179">Always</span></span> | <span data-ttu-id="467e3-180">绝对</span><span class="sxs-lookup"><span data-stu-id="467e3-180">Never</span></span> | 
<span data-ttu-id="467e3-181"> (B2BUA 中可以执行转换) \*</span><span class="sxs-lookup"><span data-stu-id="467e3-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="467e3-182">是</span><span class="sxs-lookup"><span data-stu-id="467e3-182">Yes</span></span> | <span data-ttu-id="467e3-183">否，仅在终结点之间中继音频</span><span class="sxs-lookup"><span data-stu-id="467e3-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="467e3-184">全球实例数和位置</span><span class="sxs-lookup"><span data-stu-id="467e3-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="467e3-185">总共10个：在美国东部和西部2在阿姆斯特丹和都柏林中的2个;2在中国香港和新加坡中;2在日本;澳大利亚东部和东南部的2</span><span class="sxs-lookup"><span data-stu-id="467e3-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="467e3-186">名</span><span class="sxs-lookup"><span data-stu-id="467e3-186">Multiple</span></span>

<span data-ttu-id="467e3-187">IP 范围包括：</span><span class="sxs-lookup"><span data-stu-id="467e3-187">The IP ranges are:</span></span>
- <span data-ttu-id="467e3-188">52.112.0.0/14 (IP 地址从52.112.0.1 到 52.115.255.254) </span><span class="sxs-lookup"><span data-stu-id="467e3-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="467e3-189">52.120.0.0/14 (IP 地址从52.120.0.1 到 52.123.255.254) </span><span class="sxs-lookup"><span data-stu-id="467e3-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="467e3-190">\* 代码解释解释：</span><span class="sxs-lookup"><span data-stu-id="467e3-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="467e3-191">媒体处理器为 B2BUA，这意味着它可以更改编解码器 (例如，从团队客户端到 MP 的，以及 MP 和 SBC) 之间的711。</span><span class="sxs-lookup"><span data-stu-id="467e3-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="467e3-192">传输中继不是 B2BUA，这意味着在客户端和 SBC 之间不会更改编解码器-即使通信流通过中继流也是如此。</span><span class="sxs-lookup"><span data-stu-id="467e3-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="467e3-193">如果为媒体绕过配置了主干，则使用团队媒体处理器</span><span class="sxs-lookup"><span data-stu-id="467e3-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="467e3-194">在以下情况下，团队媒体处理器始终插入到媒体路径中：</span><span class="sxs-lookup"><span data-stu-id="467e3-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="467e3-195">通话从1:1 升级到群组通话</span><span class="sxs-lookup"><span data-stu-id="467e3-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="467e3-196">呼叫将转到联合团队用户</span><span class="sxs-lookup"><span data-stu-id="467e3-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="467e3-197">呼叫将转发或转移到 Skype for Business 用户</span><span class="sxs-lookup"><span data-stu-id="467e3-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="467e3-198">确保你的 SBC 有权访问媒体处理器和传输中继范围，如下所述。</span><span class="sxs-lookup"><span data-stu-id="467e3-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="467e3-199">SIP 信号： Fqdn</span><span class="sxs-lookup"><span data-stu-id="467e3-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="467e3-200">对于 SIP 信号，FQDN 和防火墙要求与非绕过事例的要求相同。</span><span class="sxs-lookup"><span data-stu-id="467e3-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="467e3-201">直接路由在以下 Microsoft 365 或 Office 365 环境中提供：</span><span class="sxs-lookup"><span data-stu-id="467e3-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="467e3-202">Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="467e3-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="467e3-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="467e3-203">Office 365 GCC</span></span>
- <span data-ttu-id="467e3-204">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="467e3-204">Office 365 GCC High</span></span>
- <span data-ttu-id="467e3-205">Office 365 DoD 了解有关 [Office 365 和美国政府环境](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) （如 GCC、gcc 高级版和 DoD）的详细信息。</span><span class="sxs-lookup"><span data-stu-id="467e3-205">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="467e3-206">Microsoft 365、Office 365 和 Office 365 GCC 环境</span><span class="sxs-lookup"><span data-stu-id="467e3-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="467e3-207">直接路由的连接点是以下三个 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="467e3-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="467e3-208">**sip.pstnhub.microsoft.com** -必须首先尝试全局 FQDN。</span><span class="sxs-lookup"><span data-stu-id="467e3-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="467e3-209">当 SBC 发送一个请求来解析此名称时，Microsoft Azure DNS 服务器将返回指向分配给 SBC 的主 Azure 数据中心的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="467e3-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="467e3-210">该作业基于数据中心的性能指标和与 SBC 的地理位置的接近度。</span><span class="sxs-lookup"><span data-stu-id="467e3-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="467e3-211">返回的 IP 地址对应于主 FQDN。</span><span class="sxs-lookup"><span data-stu-id="467e3-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="467e3-212">**sip2.pstnhub.microsoft.com** -辅助 FQDN-地理位置映射到第二个优先级区域。</span><span class="sxs-lookup"><span data-stu-id="467e3-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="467e3-213">**sip3.pstnhub.microsoft.com** -第三方 FQDN-地理位置映射到第三个优先级区域。</span><span class="sxs-lookup"><span data-stu-id="467e3-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="467e3-214">必须放置这三个 Fqdn 才能：</span><span class="sxs-lookup"><span data-stu-id="467e3-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="467e3-215">通过查询第一个 FQDN) ，提供最佳体验， (比所分配的 SBC 数据中心更少的加载和最近的体验。</span><span class="sxs-lookup"><span data-stu-id="467e3-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="467e3-216">在将来自 SBC 的连接建立到遇到暂时性问题的数据中心时提供故障转移。</span><span class="sxs-lookup"><span data-stu-id="467e3-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="467e3-217">有关详细信息，请参阅下面的故障转移机制。</span><span class="sxs-lookup"><span data-stu-id="467e3-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="467e3-218">Fqdn " **sip.pstnhub.microsoft.com** "、" **sip2.pstnhub.microsoft.com** " 和 " **sip3.pstnhub.microsoft.com** " 将解析为以下 IP 地址之一：</span><span class="sxs-lookup"><span data-stu-id="467e3-218">The FQDNs **sip.pstnhub.microsoft.com** , **sip2.pstnhub.microsoft.com** , and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="467e3-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="467e3-219">52.114.148.0</span></span>
- <span data-ttu-id="467e3-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="467e3-220">52.114.132.46</span></span>
- <span data-ttu-id="467e3-221">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="467e3-221">52.114.16.74</span></span>
- <span data-ttu-id="467e3-222">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="467e3-222">52.114.20.29</span></span>
- <span data-ttu-id="467e3-223">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="467e3-223">52.114.75.24</span></span>
- <span data-ttu-id="467e3-224">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="467e3-224">52.114.76.76</span></span>
- <span data-ttu-id="467e3-225">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="467e3-225">52.114.7.24</span></span>
- <span data-ttu-id="467e3-226">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="467e3-226">52.114.14.70</span></span>

<span data-ttu-id="467e3-227">您需要在防火墙中打开所有这些 IP 地址的端口，以允许传入和传出通信发送和接收来自地址的发送信号。</span><span class="sxs-lookup"><span data-stu-id="467e3-227">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="467e3-228">如果你的防火墙支持 DNS 名称，FQDN **sip-all.pstnhub.microsoft.com** 将解析为所有这些 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="467e3-228">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="467e3-229">Office 365 GCC DoD 环境</span><span class="sxs-lookup"><span data-stu-id="467e3-229">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="467e3-230">直接路由的连接点是以下 FQDN：</span><span class="sxs-lookup"><span data-stu-id="467e3-230">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="467e3-231">**sip.pstnhub.dod.teams.microsoft.us** -全局 FQDN。</span><span class="sxs-lookup"><span data-stu-id="467e3-231">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="467e3-232">由于 Office 365 DoD 环境仅存在于美国数据中心，因此没有第二个和第三个 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="467e3-232">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="467e3-233">Fqdn-sip.pstnhub.dod.teams.microsoft.us 将解析为以下 IP 地址之一：</span><span class="sxs-lookup"><span data-stu-id="467e3-233">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="467e3-234">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="467e3-234">52.127.64.33</span></span>
- <span data-ttu-id="467e3-235">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="467e3-235">52.127.68.34</span></span>

<span data-ttu-id="467e3-236">您需要在防火墙中打开所有这些 IP 地址的端口，以允许传入和传出通信发送和接收来自地址的发送信号。</span><span class="sxs-lookup"><span data-stu-id="467e3-236">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="467e3-237">如果你的防火墙支持 DNS 名称，FQDN sip.pstnhub.dod.teams.microsoft.us 将解析为所有这些 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="467e3-237">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="467e3-238">Office 365 GCC 高环境</span><span class="sxs-lookup"><span data-stu-id="467e3-238">Office 365 GCC High environment</span></span>

<span data-ttu-id="467e3-239">直接路由的连接点是以下 FQDN：</span><span class="sxs-lookup"><span data-stu-id="467e3-239">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="467e3-240">**sip.pstnhub.gov.teams.microsoft.us** -全局 FQDN。</span><span class="sxs-lookup"><span data-stu-id="467e3-240">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="467e3-241">由于 GCC 的高环境仅存在于美国数据中心，因此没有第二个和第三个 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="467e3-241">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="467e3-242">Fqdn-sip.pstnhub.gov.teams.microsoft.us 将解析为以下 IP 地址之一：</span><span class="sxs-lookup"><span data-stu-id="467e3-242">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="467e3-243">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="467e3-243">52.127.88.59</span></span>
- <span data-ttu-id="467e3-244">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="467e3-244">52.127.92.64</span></span>

<span data-ttu-id="467e3-245">您需要在防火墙中打开所有这些 IP 地址的端口，以允许传入和传出通信发送和接收来自地址的发送信号。</span><span class="sxs-lookup"><span data-stu-id="467e3-245">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="467e3-246">如果你的防火墙支持 DNS 名称，FQDN sip.pstnhub.gov.teams.microsoft.us 将解析为所有这些 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="467e3-246">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="467e3-247">SIP 信号：端口</span><span class="sxs-lookup"><span data-stu-id="467e3-247">SIP Signaling: Ports</span></span>

<span data-ttu-id="467e3-248">对于提供直接路由的所有 Office 365 环境，端口要求是相同的：</span><span class="sxs-lookup"><span data-stu-id="467e3-248">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="467e3-249">Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="467e3-249">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="467e3-250">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="467e3-250">Office 365 GCC</span></span>
- <span data-ttu-id="467e3-251">Office 365 GCC 高</span><span class="sxs-lookup"><span data-stu-id="467e3-251">Office 365 GCC High</span></span>
- <span data-ttu-id="467e3-252">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="467e3-252">Office 365 DoD</span></span>

<span data-ttu-id="467e3-253">您必须使用以下端口：</span><span class="sxs-lookup"><span data-stu-id="467e3-253">You must use the following ports:</span></span>

| <span data-ttu-id="467e3-254">流量</span><span class="sxs-lookup"><span data-stu-id="467e3-254">Traffic</span></span> | <span data-ttu-id="467e3-255">从</span><span class="sxs-lookup"><span data-stu-id="467e3-255">From</span></span> | <span data-ttu-id="467e3-256">到</span><span class="sxs-lookup"><span data-stu-id="467e3-256">To</span></span> | <span data-ttu-id="467e3-257">源端口</span><span class="sxs-lookup"><span data-stu-id="467e3-257">Source port</span></span> | <span data-ttu-id="467e3-258">目标端口</span><span class="sxs-lookup"><span data-stu-id="467e3-258">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="467e3-259">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="467e3-259">SIP/TLS</span></span>| <span data-ttu-id="467e3-260">SIP 代理</span><span class="sxs-lookup"><span data-stu-id="467e3-260">SIP Proxy</span></span> | <span data-ttu-id="467e3-261">SBC</span><span class="sxs-lookup"><span data-stu-id="467e3-261">SBC</span></span> | <span data-ttu-id="467e3-262">1024-65535</span><span class="sxs-lookup"><span data-stu-id="467e3-262">1024 - 65535</span></span> | <span data-ttu-id="467e3-263">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="467e3-263">Defined on the SBC</span></span> |
| <span data-ttu-id="467e3-264">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="467e3-264">SIP/TLS</span></span> | <span data-ttu-id="467e3-265">SBC</span><span class="sxs-lookup"><span data-stu-id="467e3-265">SBC</span></span> | <span data-ttu-id="467e3-266">SIP 代理</span><span class="sxs-lookup"><span data-stu-id="467e3-266">SIP Proxy</span></span> | <span data-ttu-id="467e3-267">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="467e3-267">Defined on the SBC</span></span> | <span data-ttu-id="467e3-268">5061</span><span class="sxs-lookup"><span data-stu-id="467e3-268">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="467e3-269">媒体流量： IP 和端口范围</span><span class="sxs-lookup"><span data-stu-id="467e3-269">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="467e3-270">如果客户无法使用公共 IP 地址访问 SBC，则在 SBC 和团队客户端之间进行媒体通信流（如果直接连接可用或通过团队传输中继）。</span><span class="sxs-lookup"><span data-stu-id="467e3-270">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="467e3-271">团队客户端和 SBC)  (直接媒体通信的要求</span><span class="sxs-lookup"><span data-stu-id="467e3-271">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="467e3-272">客户端必须有权访问指定的端口 (请参阅 SBC 的公共 IP 地址上的表) 。</span><span class="sxs-lookup"><span data-stu-id="467e3-272">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="467e3-273">注意：如果客户端在内部网络中，则媒体将流向 SBC 的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="467e3-273">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="467e3-274">你可以在你的 NAT 设备上配置头发固定，以便流量永远不会离开企业网络设备。</span><span class="sxs-lookup"><span data-stu-id="467e3-274">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="467e3-275">流量</span><span class="sxs-lookup"><span data-stu-id="467e3-275">Traffic</span></span> | <span data-ttu-id="467e3-276">从</span><span class="sxs-lookup"><span data-stu-id="467e3-276">From</span></span> | <span data-ttu-id="467e3-277">到</span><span class="sxs-lookup"><span data-stu-id="467e3-277">To</span></span> | <span data-ttu-id="467e3-278">源端口</span><span class="sxs-lookup"><span data-stu-id="467e3-278">Source port</span></span> | <span data-ttu-id="467e3-279">目标端口</span><span class="sxs-lookup"><span data-stu-id="467e3-279">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="467e3-280">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="467e3-280">UDP/SRTP</span></span> | <span data-ttu-id="467e3-281">客户端</span><span class="sxs-lookup"><span data-stu-id="467e3-281">Client</span></span> | <span data-ttu-id="467e3-282">SBC</span><span class="sxs-lookup"><span data-stu-id="467e3-282">SBC</span></span> | <span data-ttu-id="467e3-283">50 000-50 019</span><span class="sxs-lookup"><span data-stu-id="467e3-283">50 000 – 50 019</span></span>  | <span data-ttu-id="467e3-284">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="467e3-284">Defined on the SBC</span></span> |
| <span data-ttu-id="467e3-285">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="467e3-285">UDP/SRTP</span></span> | <span data-ttu-id="467e3-286">SBC</span><span class="sxs-lookup"><span data-stu-id="467e3-286">SBC</span></span> | <span data-ttu-id="467e3-287">客户端</span><span class="sxs-lookup"><span data-stu-id="467e3-287">Client</span></span> | <span data-ttu-id="467e3-288">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="467e3-288">Defined on the SBC</span></span> | <span data-ttu-id="467e3-289">50 000-50 019</span><span class="sxs-lookup"><span data-stu-id="467e3-289">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="467e3-290">如果你有转换客户端源端口的网络设备，请确保在网络设备和 SBC 之间打开已转换的端口。</span><span class="sxs-lookup"><span data-stu-id="467e3-290">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="467e3-291">使用传输中继的要求</span><span class="sxs-lookup"><span data-stu-id="467e3-291">Requirements for using Transport Relays</span></span>

<span data-ttu-id="467e3-292">对于非绕过的情况，传输继电器与媒体处理器的范围相同 () ：</span><span class="sxs-lookup"><span data-stu-id="467e3-292">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="467e3-293">Microsoft 365、Office 365 和 Office 365 GCC 环境</span><span class="sxs-lookup"><span data-stu-id="467e3-293">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="467e3-294">52.112.0.0/14 (IP 地址从52.112.0.1 到 52.115.255.254) </span><span class="sxs-lookup"><span data-stu-id="467e3-294">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="467e3-295">Office 365 GCC DoD 环境</span><span class="sxs-lookup"><span data-stu-id="467e3-295">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="467e3-296">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="467e3-296">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="467e3-297">Office 365 GCC 高环境</span><span class="sxs-lookup"><span data-stu-id="467e3-297">Office 365 GCC High environment</span></span>

- <span data-ttu-id="467e3-298">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="467e3-298">52.127.88.0/21</span></span>


<span data-ttu-id="467e3-299">团队传输中继的端口范围 (适用于所有环境) 如下表所示：</span><span class="sxs-lookup"><span data-stu-id="467e3-299">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="467e3-300">流量</span><span class="sxs-lookup"><span data-stu-id="467e3-300">Traffic</span></span> | <span data-ttu-id="467e3-301">从</span><span class="sxs-lookup"><span data-stu-id="467e3-301">From</span></span> | <span data-ttu-id="467e3-302">到</span><span class="sxs-lookup"><span data-stu-id="467e3-302">To</span></span> | <span data-ttu-id="467e3-303">源端口</span><span class="sxs-lookup"><span data-stu-id="467e3-303">Source port</span></span> | <span data-ttu-id="467e3-304">目标端口</span><span class="sxs-lookup"><span data-stu-id="467e3-304">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="467e3-305">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="467e3-305">UDP/SRTP</span></span> | <span data-ttu-id="467e3-306">传输中继</span><span class="sxs-lookup"><span data-stu-id="467e3-306">Transport Relay</span></span> | <span data-ttu-id="467e3-307">SBC</span><span class="sxs-lookup"><span data-stu-id="467e3-307">SBC</span></span> | <span data-ttu-id="467e3-308">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="467e3-308">50 000 -59 999</span></span>    | <span data-ttu-id="467e3-309">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="467e3-309">Defined on the SBC</span></span> |
| <span data-ttu-id="467e3-310">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="467e3-310">UDP/SRTP</span></span> | <span data-ttu-id="467e3-311">SBC</span><span class="sxs-lookup"><span data-stu-id="467e3-311">SBC</span></span> | <span data-ttu-id="467e3-312">传输中继</span><span class="sxs-lookup"><span data-stu-id="467e3-312">Transport Relay</span></span> | <span data-ttu-id="467e3-313">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="467e3-313">Defined on the SBC</span></span> | <span data-ttu-id="467e3-314">50 000-59 999、3478、3479</span><span class="sxs-lookup"><span data-stu-id="467e3-314">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="467e3-315">Microsoft 建议在 SBC 上对每个并发调用至少有两个端口。</span><span class="sxs-lookup"><span data-stu-id="467e3-315">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="467e3-316">由于 Microsoft 具有两个版本的传输中继，因此需要以下内容：</span><span class="sxs-lookup"><span data-stu-id="467e3-316">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="467e3-317">v4，它只能使用端口范围 50 000 到 59 999</span><span class="sxs-lookup"><span data-stu-id="467e3-317">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="467e3-318">v6，它适用于端口3478、3479</span><span class="sxs-lookup"><span data-stu-id="467e3-318">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="467e3-319">此时，媒体绕过仅支持传输中继的 v4 版本。</span><span class="sxs-lookup"><span data-stu-id="467e3-319">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="467e3-320">我们将在将来介绍 v6 的支持。</span><span class="sxs-lookup"><span data-stu-id="467e3-320">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="467e3-321">您需要打开端口3478和3479以进行转换。</span><span class="sxs-lookup"><span data-stu-id="467e3-321">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="467e3-322">当 Microsoft 为具有媒体旁路的 v6 传输中继提供支持时，不需要重新配置网络设备或 SBCs。</span><span class="sxs-lookup"><span data-stu-id="467e3-322">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="467e3-323">使用媒体处理器的要求</span><span class="sxs-lookup"><span data-stu-id="467e3-323">Requirements for using media processors</span></span>

<span data-ttu-id="467e3-324">媒体处理器始终位于语音应用程序和 Web 客户端的媒体路径中 (例如，在 Edge 或 Google Chrome) 中的团队客户端。</span><span class="sxs-lookup"><span data-stu-id="467e3-324">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="467e3-325">要求与非绕过配置相同。</span><span class="sxs-lookup"><span data-stu-id="467e3-325">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="467e3-326">媒体流量的 IP 范围是</span><span class="sxs-lookup"><span data-stu-id="467e3-326">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="467e3-327">Office 365 和 Office 365 GCC 环境</span><span class="sxs-lookup"><span data-stu-id="467e3-327">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="467e3-328">52.112.0.0/14 (IP 地址从52.112.0.1 到 52.115.255.254) </span><span class="sxs-lookup"><span data-stu-id="467e3-328">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="467e3-329">Office 365 GCC DoD 环境</span><span class="sxs-lookup"><span data-stu-id="467e3-329">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="467e3-330">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="467e3-330">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="467e3-331">Office 365 GCC 高环境</span><span class="sxs-lookup"><span data-stu-id="467e3-331">Office 365 GCC High environment</span></span>

- <span data-ttu-id="467e3-332">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="467e3-332">52.127.88.0/21</span></span>

<span data-ttu-id="467e3-333">适用于所有环境) 的媒体处理器的端口范围 (如下表所示：</span><span class="sxs-lookup"><span data-stu-id="467e3-333">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="467e3-334">流量</span><span class="sxs-lookup"><span data-stu-id="467e3-334">Traffic</span></span> | <span data-ttu-id="467e3-335">从</span><span class="sxs-lookup"><span data-stu-id="467e3-335">From</span></span> | <span data-ttu-id="467e3-336">到</span><span class="sxs-lookup"><span data-stu-id="467e3-336">To</span></span> | <span data-ttu-id="467e3-337">源端口</span><span class="sxs-lookup"><span data-stu-id="467e3-337">Source port</span></span> | <span data-ttu-id="467e3-338">目标端口</span><span class="sxs-lookup"><span data-stu-id="467e3-338">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="467e3-339">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="467e3-339">UDP/SRTP</span></span> | <span data-ttu-id="467e3-340">媒体处理器</span><span class="sxs-lookup"><span data-stu-id="467e3-340">Media Processor</span></span> | <span data-ttu-id="467e3-341">SBC</span><span class="sxs-lookup"><span data-stu-id="467e3-341">SBC</span></span> | <span data-ttu-id="467e3-342">3478、3479和 49 152-53 247</span><span class="sxs-lookup"><span data-stu-id="467e3-342">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="467e3-343">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="467e3-343">Defined on the SBC</span></span> |
| <span data-ttu-id="467e3-344">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="467e3-344">UDP/SRTP</span></span> | <span data-ttu-id="467e3-345">SBC</span><span class="sxs-lookup"><span data-stu-id="467e3-345">SBC</span></span> | <span data-ttu-id="467e3-346">媒体处理器</span><span class="sxs-lookup"><span data-stu-id="467e3-346">Media Processor</span></span> | <span data-ttu-id="467e3-347">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="467e3-347">Defined on the SBC</span></span> | <span data-ttu-id="467e3-348">3478、3479和 49 152-53 247</span><span class="sxs-lookup"><span data-stu-id="467e3-348">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="467e3-349">为媒体绕过和非媒体旁路配置单独的中继</span><span class="sxs-lookup"><span data-stu-id="467e3-349">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="467e3-350">如果从非媒体旁路迁移到 "媒体绕过" 并希望在将所有使用迁移到媒体绕过之前确认功能，则可以创建单独的主干和单独的联机语音路由策略以路由到媒体绕过主干并分配给特定用户。</span><span class="sxs-lookup"><span data-stu-id="467e3-350">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="467e3-351">高级别配置步骤：</span><span class="sxs-lookup"><span data-stu-id="467e3-351">High-level configuration steps:</span></span>

- <span data-ttu-id="467e3-352">标识要测试媒体绕过的用户。</span><span class="sxs-lookup"><span data-stu-id="467e3-352">Identify users to test media bypass.</span></span>

- <span data-ttu-id="467e3-353">使用不同的 Fqdn 创建两个单独的中继：一个为媒体绕过启用;另一个不是。</span><span class="sxs-lookup"><span data-stu-id="467e3-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="467e3-354">这两个中继指向同一个 SBC。</span><span class="sxs-lookup"><span data-stu-id="467e3-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="467e3-355">TLS SIP 信号的端口必须不同。</span><span class="sxs-lookup"><span data-stu-id="467e3-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="467e3-356">媒体端口必须相同。</span><span class="sxs-lookup"><span data-stu-id="467e3-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="467e3-357">创建新的联机语音路由策略，并将媒体绕过主干分配给与此策略的 PSTN 使用相关联的相应路由。</span><span class="sxs-lookup"><span data-stu-id="467e3-357">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="467e3-358">将新的联机语音路由策略分配给已识别测试媒体绕过的用户。</span><span class="sxs-lookup"><span data-stu-id="467e3-358">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="467e3-359">下面的示例演示了此逻辑。</span><span class="sxs-lookup"><span data-stu-id="467e3-359">The example below illustrates this logic.</span></span>

| <span data-ttu-id="467e3-360">组用户</span><span class="sxs-lookup"><span data-stu-id="467e3-360">Set of users</span></span> | <span data-ttu-id="467e3-361">用户数</span><span class="sxs-lookup"><span data-stu-id="467e3-361">Number of users</span></span> | <span data-ttu-id="467e3-362">在 OVRP 中分配的中继 FQDN</span><span class="sxs-lookup"><span data-stu-id="467e3-362">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="467e3-363">媒体绕过启用</span><span class="sxs-lookup"><span data-stu-id="467e3-363">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="467e3-364">具有非媒体旁路主干的用户</span><span class="sxs-lookup"><span data-stu-id="467e3-364">Users with non-media bypass trunk</span></span> | <span data-ttu-id="467e3-365">980</span><span class="sxs-lookup"><span data-stu-id="467e3-365">980</span></span> | <span data-ttu-id="467e3-366">sbc1.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="467e3-366">sbc1.contoso.com:5060</span></span> | <span data-ttu-id="467e3-367">true</span><span class="sxs-lookup"><span data-stu-id="467e3-367">true</span></span>
<span data-ttu-id="467e3-368">具有媒体绕过主干的用户</span><span class="sxs-lookup"><span data-stu-id="467e3-368">Users with media bypass trunk</span></span> | <span data-ttu-id="467e3-369">名</span><span class="sxs-lookup"><span data-stu-id="467e3-369">20</span></span> | <span data-ttu-id="467e3-370">sbc2.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="467e3-370">sbc2.contoso.com:5061</span></span> | <span data-ttu-id="467e3-371">false</span><span class="sxs-lookup"><span data-stu-id="467e3-371">false</span></span> | 

<span data-ttu-id="467e3-372">这两个中继都可以指向具有相同公共 IP 地址的同一 SBC。</span><span class="sxs-lookup"><span data-stu-id="467e3-372">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="467e3-373">SBC 的 TLS 信号端口必须不同，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="467e3-373">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="467e3-374">注意你需要确保你的证书支持这两个中继。</span><span class="sxs-lookup"><span data-stu-id="467e3-374">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="467e3-375">在 SAN 中，你需要具有两个名称 ( **sbc1.contoso.com** 和 **sbc2.contoso.com** ) 或拥有通配符证书。</span><span class="sxs-lookup"><span data-stu-id="467e3-375">In SAN, you need to have two names ( **sbc1.contoso.com** and **sbc2.contoso.com** ) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="467e3-376">![显示两个中继都可以指向具有相同公共 IP 的同一 SBC](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="467e3-376">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="467e3-377">有关如何在同一 SBC 上配置两个中继的信息，请参阅 SBC 供应商提供的文档：</span><span class="sxs-lookup"><span data-stu-id="467e3-377">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="467e3-378">AudioCodes 部署文档</span><span class="sxs-lookup"><span data-stu-id="467e3-378">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="467e3-379">Oracle 部署文档</span><span class="sxs-lookup"><span data-stu-id="467e3-379">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="467e3-380">功能区通信部署文档</span><span class="sxs-lookup"><span data-stu-id="467e3-380">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="467e3-381">TE-系统 (anynode) 部署文档</span><span class="sxs-lookup"><span data-stu-id="467e3-381">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="467e3-382">媒体绕过支持的客户端终结点</span><span class="sxs-lookup"><span data-stu-id="467e3-382">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="467e3-383">所有独立团队桌面客户端、Android 和 iOS 客户端和团队电话设备均支持媒体绕过。</span><span class="sxs-lookup"><span data-stu-id="467e3-383">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="467e3-384">对于不支持媒体绕过的所有其他终结点，我们会将调用转换为非旁路，即使它是绕过呼叫启动的。</span><span class="sxs-lookup"><span data-stu-id="467e3-384">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="467e3-385">这会自动发生，不需要管理员执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="467e3-385">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="467e3-386">这包括 Skype for Business 3PIP 手机和团队 Web 客户端，这些客户支持直接路由调用 (WebRTC 基于 Microsoft Edge、Google Chrome、Mozilla Firefox) 的客户端运行。</span><span class="sxs-lookup"><span data-stu-id="467e3-386">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="467e3-387">另请参阅</span><span class="sxs-lookup"><span data-stu-id="467e3-387">See also</span></span>

[<span data-ttu-id="467e3-388">使用直接路由配置媒体旁路</span><span class="sxs-lookup"><span data-stu-id="467e3-388">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)


