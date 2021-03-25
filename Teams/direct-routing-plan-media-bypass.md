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
description: 了解如何使用电话系统直接路由规划媒体旁路，从而缩短媒体流量的路径并提高性能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bbd31a62bf6ebcd481a3cdafeabaf29bb4767f2d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115590"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="96ceb-103">使用直接路由规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="96ceb-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="96ceb-104">关于使用直接路由绕过媒体</span><span class="sxs-lookup"><span data-stu-id="96ceb-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="96ceb-105">使用媒体旁路可以缩短媒体流量的路径，并减少传输中的跃点数，以提高性能。</span><span class="sxs-lookup"><span data-stu-id="96ceb-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="96ceb-106">借助媒体旁路，媒体将保留在会话边界控制器 (SBC) 与客户端之间，而不是通过 Microsoft Phone System 发送。</span><span class="sxs-lookup"><span data-stu-id="96ceb-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="96ceb-107">若要配置媒体绕过，SBC 和客户端必须位于同一位置或网络中。</span><span class="sxs-lookup"><span data-stu-id="96ceb-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="96ceb-108">可以使用 **Set-CSOnlinePSTNGateway** 命令，将 **-MediaBypass** 参数设置为 true 或 false，控制每个 SBC 的媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="96ceb-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="96ceb-109">如果启用媒体旁路，这并不意味着所有媒体流量将位于企业网络中。</span><span class="sxs-lookup"><span data-stu-id="96ceb-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="96ceb-110">本文介绍不同方案中的调用流。</span><span class="sxs-lookup"><span data-stu-id="96ceb-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="96ceb-111">下图演示了在绕过媒体的情况下和没有媒体旁路的情况下呼叫流的差异。</span><span class="sxs-lookup"><span data-stu-id="96ceb-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="96ceb-112">如果不绕过媒体，当客户端发出或接听呼叫时，SBC、Microsoft Phone System 和 Teams 客户端之间的信号和媒体流，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="96ceb-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="96ceb-113">![显示无媒体旁路的信号和媒体流](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="96ceb-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="96ceb-114">但假设用户与 SBC 位于同一建筑物或网络中。</span><span class="sxs-lookup"><span data-stu-id="96ceb-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="96ceb-115">例如，假设位于法兰克福的一栋大楼中的用户呼叫 PSTN 用户：</span><span class="sxs-lookup"><span data-stu-id="96ceb-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="96ceb-116">**如果不绕过媒体**，媒体将流经阿姆斯特丹或都柏林 (将 Microsoft 数据中心部署到) 并返回到法兰克福的 SBC。</span><span class="sxs-lookup"><span data-stu-id="96ceb-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="96ceb-117">选择欧洲的数据中心是因为 SBC 位于欧洲，而 Microsoft 使用离 SBC 最近的数据中心。</span><span class="sxs-lookup"><span data-stu-id="96ceb-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="96ceb-118">尽管此方法不会由于在大多数地理位置的 Microsoft 网络内优化流量流而影响呼叫质量，但流量具有不必要的循环。</span><span class="sxs-lookup"><span data-stu-id="96ceb-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="96ceb-119">**借助媒体** 旁路，媒体直接保留在 Teams 用户与 SBC 之间，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="96ceb-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="96ceb-120">![使用媒体旁路显示信号和媒体流](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="96ceb-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="96ceb-121">媒体绕过利用 Teams 客户端上名为交互式连接 (ICE) SBC 上的 ICE lite 的协议。</span><span class="sxs-lookup"><span data-stu-id="96ceb-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="96ceb-122">这些协议使直接路由能够使用最直接的媒体路径以获得最佳质量。</span><span class="sxs-lookup"><span data-stu-id="96ceb-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="96ceb-123">ICE 和 ICE Lite 是 WebRTC 标准。</span><span class="sxs-lookup"><span data-stu-id="96ceb-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="96ceb-124">有关这些协议的详细信息，请参阅 RFC 5245。</span><span class="sxs-lookup"><span data-stu-id="96ceb-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="96ceb-125">呼叫流和防火墙规划</span><span class="sxs-lookup"><span data-stu-id="96ceb-125">Call flow and firewall planning</span></span>

<span data-ttu-id="96ceb-126">呼叫流和防火墙规划取决于用户是否直接访问 SBC 的公共 IP 地址，以及用户是在网络内部还是外部。</span><span class="sxs-lookup"><span data-stu-id="96ceb-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="96ceb-127">如果用户对 SBC 的公共 IP 地址具有直接访问权限，则调用流</span><span class="sxs-lookup"><span data-stu-id="96ceb-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="96ceb-128">如果用户直接访问 SBC 的公共 IP 地址，则调用流如下所示：</span><span class="sxs-lookup"><span data-stu-id="96ceb-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="96ceb-129">对于媒体旁路，Teams 客户端必须有权访问 SBC 的公共 IP 地址，即使从内部网络访问。</span><span class="sxs-lookup"><span data-stu-id="96ceb-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="96ceb-130">如果不需要直接媒体，则媒体可以通过传输中继流动。</span><span class="sxs-lookup"><span data-stu-id="96ceb-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="96ceb-131">当用户与 SBC 位于同一大楼和/或网络中时，这是建议的解决方案 - 从媒体路径中删除 Microsoft 云组件。</span><span class="sxs-lookup"><span data-stu-id="96ceb-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="96ceb-132">信令始终通过 Microsoft 云流动。</span><span class="sxs-lookup"><span data-stu-id="96ceb-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="96ceb-133">下图显示了启用媒体旁路、客户端在内部且客户端能够访问 SBC 的公共 IP 地址（直接媒体 (呼叫) ：</span><span class="sxs-lookup"><span data-stu-id="96ceb-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="96ceb-134">路径的箭头和数值与 Microsoft Teams 呼叫 [流一样](./microsoft-teams-online-call-flows.md)。</span><span class="sxs-lookup"><span data-stu-id="96ceb-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="96ceb-135">SIP 信号始终采用路径 4 和 4' (，具体取决于流量方向) 。</span><span class="sxs-lookup"><span data-stu-id="96ceb-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="96ceb-136">媒体保持本地，采用路径 5b。</span><span class="sxs-lookup"><span data-stu-id="96ceb-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="96ceb-137">![显示已启用媒体旁路的呼叫流，客户端在内部](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="96ceb-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="96ceb-138">如果用户无法访问 SBC 的公共 IP 地址，则调用流</span><span class="sxs-lookup"><span data-stu-id="96ceb-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="96ceb-139">下面介绍如果用户无法访问 SBC 的公共 IP 地址，则说明调用流。</span><span class="sxs-lookup"><span data-stu-id="96ceb-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="96ceb-140">例如，假设用户是外部用户，并且租户管理员决定不向 Internet 中的每个人开放 SBC 的公共 IP 地址，而只向 Microsoft 云开放。</span><span class="sxs-lookup"><span data-stu-id="96ceb-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="96ceb-141">流量的内部组件可以通过 Teams 传输中继流动。</span><span class="sxs-lookup"><span data-stu-id="96ceb-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="96ceb-142">比如以下几种情况：</span><span class="sxs-lookup"><span data-stu-id="96ceb-142">Consider the following:</span></span>

- <span data-ttu-id="96ceb-143">使用 Teams 传输中继。</span><span class="sxs-lookup"><span data-stu-id="96ceb-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="96ceb-144">对于媒体旁路，Microsoft 使用一个传输中继版本，该版本要求在 Teams 传输中继和 SBC (之间打开端口 50 000 到 59 999，我们计划在将来转移到仅需要 3478 和 3479 个端口) 的版本。</span><span class="sxs-lookup"><span data-stu-id="96ceb-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>


<span data-ttu-id="96ceb-145">下图显示了启用媒体旁路、客户端在外部以及客户端无法访问会话边界控制器的公共 IP 地址的呼叫流， (媒体由 Teams 传输中继中继) 。</span><span class="sxs-lookup"><span data-stu-id="96ceb-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="96ceb-146">路径的箭头和数值与 Microsoft Teams 呼叫 [流一样](./microsoft-teams-online-call-flows.md)。</span><span class="sxs-lookup"><span data-stu-id="96ceb-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="96ceb-147">媒体通过路径 3、3、4 和 4' 中继</span><span class="sxs-lookup"><span data-stu-id="96ceb-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="96ceb-148">![如果用户无法访问 SBC 的公共 IP，则显示呼叫流](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="96ceb-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="96ceb-149">如果用户位于网络外部且有权访问 SBC 的公共 IP，则调用流</span><span class="sxs-lookup"><span data-stu-id="96ceb-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="96ceb-150">这不是建议的配置，因为它不会利用 Teams 传输中继。</span><span class="sxs-lookup"><span data-stu-id="96ceb-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="96ceb-151">相反，应考虑以前的方案，其中用户无法访问 SBC 的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="96ceb-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="96ceb-152">下图显示了启用媒体旁路时呼叫流、客户端是外部的，并且客户端可以通过直接媒体服务访问 SBC (IP) 。</span><span class="sxs-lookup"><span data-stu-id="96ceb-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="96ceb-153">路径的箭头和数字值符合 Microsoft Teams 呼叫 [流一](./microsoft-teams-online-call-flows.md) 文。</span><span class="sxs-lookup"><span data-stu-id="96ceb-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md) article.</span></span>

- <span data-ttu-id="96ceb-154">SIP 信号始终采用路径 3 和 3' (，具体取决于流量方向) 。</span><span class="sxs-lookup"><span data-stu-id="96ceb-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="96ceb-155">使用路径 2 的媒体流。</span><span class="sxs-lookup"><span data-stu-id="96ceb-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="96ceb-156">![如果用户无法访问 SBC 的公共 IP，则显示呼叫流](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="96ceb-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="96ceb-157">媒体处理器和传输中继的使用</span><span class="sxs-lookup"><span data-stu-id="96ceb-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="96ceb-158">Microsoft 云中的两个组件可以在媒体流量的路径中：媒体处理器和传输中继。</span><span class="sxs-lookup"><span data-stu-id="96ceb-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="96ceb-159">媒体处理器是面向公众的组件，可处理非绕过情况下的媒体，并处理语音应用程序的媒体。</span><span class="sxs-lookup"><span data-stu-id="96ceb-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="96ceb-160">媒体处理器始终位于最终用户非绕过调用的路径中，但绝不会在绕过的调用的路径中。</span><span class="sxs-lookup"><span data-stu-id="96ceb-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="96ceb-161">媒体处理器始终位于所有语音应用程序的路径中，例如呼叫公园、组织自动助理和呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="96ceb-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="96ceb-162">传输中继用于连接到最近的传输服务，以发送实时流量。</span><span class="sxs-lookup"><span data-stu-id="96ceb-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="96ceb-163">传输中继可能位于（源自或目标为最终用户）的绕过调用的路径中，具体取决于用户位于何处以及网络的配置方式。</span><span class="sxs-lookup"><span data-stu-id="96ceb-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="96ceb-164">下图显示了两个呼叫流 - 一个已启用媒体旁路，另一个已禁用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="96ceb-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="96ceb-165">请注意，该图仅演示源自或目的地为最终用户的流量。</span><span class="sxs-lookup"><span data-stu-id="96ceb-165">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="96ceb-166">媒体控制器是 Azure 中的微服务，可分配媒体处理器，并创建 SDP (会话) 协议。</span><span class="sxs-lookup"><span data-stu-id="96ceb-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="96ceb-167">SIP 代理是一个组件，用于将 Teams 中使用的 HTTP REST 信号转换为 SIP。</span><span class="sxs-lookup"><span data-stu-id="96ceb-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="96ceb-168">![显示已启用和禁用媒体旁路的呼叫流](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="96ceb-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="96ceb-169">下表总结了媒体处理器与传输中继的区别。</span><span class="sxs-lookup"><span data-stu-id="96ceb-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="96ceb-170">媒体处理器</span><span class="sxs-lookup"><span data-stu-id="96ceb-170">Media Processors</span></span> | <span data-ttu-id="96ceb-171">传输中继</span><span class="sxs-lookup"><span data-stu-id="96ceb-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="96ceb-172">最终用户的非绕过呼叫的媒体路径</span><span class="sxs-lookup"><span data-stu-id="96ceb-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="96ceb-173">始终</span><span class="sxs-lookup"><span data-stu-id="96ceb-173">Always</span></span> | <span data-ttu-id="96ceb-174">如果客户端无法直接访问媒体处理器</span><span class="sxs-lookup"><span data-stu-id="96ceb-174">If client cannot reach the Media Processor directly</span></span> | 
<span data-ttu-id="96ceb-175">最终用户的旁路呼叫的媒体路径</span><span class="sxs-lookup"><span data-stu-id="96ceb-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="96ceb-176">从不</span><span class="sxs-lookup"><span data-stu-id="96ceb-176">Never</span></span> | <span data-ttu-id="96ceb-177">如果客户端无法访问公共 IP 地址上的 SBC</span><span class="sxs-lookup"><span data-stu-id="96ceb-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="96ceb-178">在语音应用程序的媒体路径中</span><span class="sxs-lookup"><span data-stu-id="96ceb-178">In media path for voice applications</span></span> | <span data-ttu-id="96ceb-179">始终</span><span class="sxs-lookup"><span data-stu-id="96ceb-179">Always</span></span> | <span data-ttu-id="96ceb-180">从不</span><span class="sxs-lookup"><span data-stu-id="96ceb-180">Never</span></span> | 
<span data-ttu-id="96ceb-181">可以在 B2BUA (转码) \*</span><span class="sxs-lookup"><span data-stu-id="96ceb-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="96ceb-182">是</span><span class="sxs-lookup"><span data-stu-id="96ceb-182">Yes</span></span> | <span data-ttu-id="96ceb-183">否，仅中继终结点之间的音频</span><span class="sxs-lookup"><span data-stu-id="96ceb-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="96ceb-184">全球实例数和位置</span><span class="sxs-lookup"><span data-stu-id="96ceb-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="96ceb-185">总共 10 个：美国东部和西部 2 个;2（阿姆斯特丹和都柏林）;2（香港特别行政区和新加坡）;2（日本）;澳大利亚东部和东南部 2 个</span><span class="sxs-lookup"><span data-stu-id="96ceb-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="96ceb-186">多个</span><span class="sxs-lookup"><span data-stu-id="96ceb-186">Multiple</span></span>

<span data-ttu-id="96ceb-187">IP 范围包括：</span><span class="sxs-lookup"><span data-stu-id="96ceb-187">The IP ranges are:</span></span>
- <span data-ttu-id="96ceb-188">52.112.0.0/14 (IP 地址从 52.112.0.1 到 52.115.255.254) </span><span class="sxs-lookup"><span data-stu-id="96ceb-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="96ceb-189">52.120.0.0/14 (IP 地址从 52.120.0.1 到 52.123.255.254) </span><span class="sxs-lookup"><span data-stu-id="96ceb-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="96ceb-190">\* 转码说明：</span><span class="sxs-lookup"><span data-stu-id="96ceb-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="96ceb-191">媒体处理器是 B2BUA，这意味着它可以将编解码器 (例如，SILK 从 Teams 客户端更改为 MP，在 MP 和 SBC 客户端之间更改 G.711) 。</span><span class="sxs-lookup"><span data-stu-id="96ceb-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="96ceb-192">传输中继不是 B2BUA，这意味着，即使流量通过中继流动，编解码器也永远不会在客户端和 SBC 之间更改。</span><span class="sxs-lookup"><span data-stu-id="96ceb-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="96ceb-193">如果为绕过媒体配置了中继，则使用 Teams 媒体处理器</span><span class="sxs-lookup"><span data-stu-id="96ceb-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="96ceb-194">在以下情况中，Teams 媒体处理器始终插入到媒体路径中：</span><span class="sxs-lookup"><span data-stu-id="96ceb-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="96ceb-195">通话从 1：1 升级到群组通话</span><span class="sxs-lookup"><span data-stu-id="96ceb-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="96ceb-196">呼叫将呼叫联合的 Teams 用户</span><span class="sxs-lookup"><span data-stu-id="96ceb-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="96ceb-197">呼叫转接或转接到 Skype for Business 用户</span><span class="sxs-lookup"><span data-stu-id="96ceb-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="96ceb-198">确保 SBC 有权访问媒体处理器和传输中继范围，如下所述。</span><span class="sxs-lookup"><span data-stu-id="96ceb-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="96ceb-199">SIP 信号：FQDN</span><span class="sxs-lookup"><span data-stu-id="96ceb-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="96ceb-200">对于 SIP 信号，FQDN 和防火墙要求与非绕过情况相同。</span><span class="sxs-lookup"><span data-stu-id="96ceb-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="96ceb-201">直接路由在下列 Microsoft 365 或 Office 365 环境中提供：</span><span class="sxs-lookup"><span data-stu-id="96ceb-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="96ceb-202">Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="96ceb-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="96ceb-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="96ceb-203">Office 365 GCC</span></span>
- <span data-ttu-id="96ceb-204">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="96ceb-204">Office 365 GCC High</span></span>
- <span data-ttu-id="96ceb-205">Office 365 DoD 详细了解 [Office 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) 和美国政府环境，例如 GCC、GCC High 和 DoD。</span><span class="sxs-lookup"><span data-stu-id="96ceb-205">Office 365 DoD Learn more about [Office 365 and US Government environments](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="96ceb-206">Microsoft 365、Office 365 和 Office 365 GCC 环境</span><span class="sxs-lookup"><span data-stu-id="96ceb-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="96ceb-207">直接路由的连接点为以下三个 FQDN：</span><span class="sxs-lookup"><span data-stu-id="96ceb-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="96ceb-208">**sip.pstnhub.microsoft.com** - 全局 FQDN – 必须先尝试。</span><span class="sxs-lookup"><span data-stu-id="96ceb-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="96ceb-209">当 SBC 发送解析此名称的请求时，Microsoft Azure DNS 服务器将返回指向分配给 SBC 的主要 Azure 数据中心的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="96ceb-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="96ceb-210">分配基于数据中心的性能指标和与 SBC 的地理邻近性。</span><span class="sxs-lookup"><span data-stu-id="96ceb-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="96ceb-211">返回的 IP 地址对应于主 FQDN。</span><span class="sxs-lookup"><span data-stu-id="96ceb-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="96ceb-212">**sip2.pstnhub.microsoft.com** - 辅助 FQDN - 在地理上映射到第二个优先级区域。</span><span class="sxs-lookup"><span data-stu-id="96ceb-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="96ceb-213">**sip3.pstnhub.microsoft.com** - 第三级 FQDN - 在地理上映射到第三个优先区域。</span><span class="sxs-lookup"><span data-stu-id="96ceb-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="96ceb-214">必须放置这三个 FQNS，以便：</span><span class="sxs-lookup"><span data-stu-id="96ceb-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="96ceb-215">通过查询第一个 FQDN (，在负载较少且最接近分配的 SBC 数据中心时提供最佳) 。</span><span class="sxs-lookup"><span data-stu-id="96ceb-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="96ceb-216">从 SBC 建立到遇到临时问题的数据中心的连接时，提供故障转移。</span><span class="sxs-lookup"><span data-stu-id="96ceb-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="96ceb-217">有关详细信息，请参阅下面的故障转移机制。</span><span class="sxs-lookup"><span data-stu-id="96ceb-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="96ceb-218">FQDN **sip.pstnhub.microsoft.com、sip2.pstnhub.microsoft.com** 和 **sip3.pstnhub.microsoft.com** 将解析为以下 IP 地址之一：</span><span class="sxs-lookup"><span data-stu-id="96ceb-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="96ceb-219">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="96ceb-219">52.114.148.0</span></span>
- <span data-ttu-id="96ceb-220">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="96ceb-220">52.114.132.46</span></span>
- <span data-ttu-id="96ceb-221">52.114.16.74</span><span class="sxs-lookup"><span data-stu-id="96ceb-221">52.114.16.74</span></span>
- <span data-ttu-id="96ceb-222">52.114.20.29</span><span class="sxs-lookup"><span data-stu-id="96ceb-222">52.114.20.29</span></span>
- <span data-ttu-id="96ceb-223">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="96ceb-223">52.114.75.24</span></span>
- <span data-ttu-id="96ceb-224">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="96ceb-224">52.114.76.76</span></span>
- <span data-ttu-id="96ceb-225">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="96ceb-225">52.114.7.24</span></span>
- <span data-ttu-id="96ceb-226">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="96ceb-226">52.114.14.70</span></span>

<span data-ttu-id="96ceb-227">需要在防火墙中打开所有这些 IP 地址的端口，以允许传入和传出流量传入和传出地址以发出信号。</span><span class="sxs-lookup"><span data-stu-id="96ceb-227">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="96ceb-228">如果防火墙支持 DNS 名称，FQDN **sip-all.pstnhub.microsoft.com** 解析为所有这些 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="96ceb-228">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="96ceb-229">Office 365 GCC DoD 环境</span><span class="sxs-lookup"><span data-stu-id="96ceb-229">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="96ceb-230">直接路由的连接点是以下 FQDN：</span><span class="sxs-lookup"><span data-stu-id="96ceb-230">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="96ceb-231">**sip.pstnhub.dod.teams.microsoft.us** - 全局 FQDN。</span><span class="sxs-lookup"><span data-stu-id="96ceb-231">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="96ceb-232">由于 Office 365 DoD 环境仅存在于美国数据中心，因此没有辅助和第三级 FQD。</span><span class="sxs-lookup"><span data-stu-id="96ceb-232">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="96ceb-233">FQNS – sip.pstnhub.dod.teams.microsoft.us 解析为以下 IP 地址之一：</span><span class="sxs-lookup"><span data-stu-id="96ceb-233">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="96ceb-234">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="96ceb-234">52.127.64.33</span></span>
- <span data-ttu-id="96ceb-235">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="96ceb-235">52.127.68.34</span></span>

<span data-ttu-id="96ceb-236">需要在防火墙中打开所有这些 IP 地址的端口，以允许传入和传出流量传入和传出地址以发出信号。</span><span class="sxs-lookup"><span data-stu-id="96ceb-236">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="96ceb-237">如果防火墙支持 DNS 名称，FQDN sip.pstnhub.dod.teams.microsoft.us 解析为所有这些 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="96ceb-237">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="96ceb-238">Office 365 GCC 高环境</span><span class="sxs-lookup"><span data-stu-id="96ceb-238">Office 365 GCC High environment</span></span>

<span data-ttu-id="96ceb-239">直接路由的连接点是以下 FQDN：</span><span class="sxs-lookup"><span data-stu-id="96ceb-239">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="96ceb-240">**sip.pstnhub.gov.teams.microsoft.us** - 全局 FQDN。</span><span class="sxs-lookup"><span data-stu-id="96ceb-240">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="96ceb-241">由于 GCC 高环境仅存在于美国数据中心，因此没有辅助 FQN 和第三级 FQNS。</span><span class="sxs-lookup"><span data-stu-id="96ceb-241">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="96ceb-242">FQNS – sip.pstnhub.gov.teams.microsoft.us 解析为以下 IP 地址之一：</span><span class="sxs-lookup"><span data-stu-id="96ceb-242">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="96ceb-243">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="96ceb-243">52.127.88.59</span></span>
- <span data-ttu-id="96ceb-244">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="96ceb-244">52.127.92.64</span></span>

<span data-ttu-id="96ceb-245">需要在防火墙中打开所有这些 IP 地址的端口，以允许传入和传出流量传入和传出地址以发出信号。</span><span class="sxs-lookup"><span data-stu-id="96ceb-245">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="96ceb-246">如果防火墙支持 DNS 名称，FQDN sip.pstnhub.gov.teams.microsoft.us 解析为所有这些 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="96ceb-246">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="96ceb-247">SIP 信号：端口</span><span class="sxs-lookup"><span data-stu-id="96ceb-247">SIP Signaling: Ports</span></span>

<span data-ttu-id="96ceb-248">对于提供直接路由的所有 Office 365 环境，端口要求相同：</span><span class="sxs-lookup"><span data-stu-id="96ceb-248">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="96ceb-249">Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="96ceb-249">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="96ceb-250">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="96ceb-250">Office 365 GCC</span></span>
- <span data-ttu-id="96ceb-251">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="96ceb-251">Office 365 GCC High</span></span>
- <span data-ttu-id="96ceb-252">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="96ceb-252">Office 365 DoD</span></span>

<span data-ttu-id="96ceb-253">必须使用以下端口：</span><span class="sxs-lookup"><span data-stu-id="96ceb-253">You must use the following ports:</span></span>

| <span data-ttu-id="96ceb-254">流量</span><span class="sxs-lookup"><span data-stu-id="96ceb-254">Traffic</span></span> | <span data-ttu-id="96ceb-255">从</span><span class="sxs-lookup"><span data-stu-id="96ceb-255">From</span></span> | <span data-ttu-id="96ceb-256">到</span><span class="sxs-lookup"><span data-stu-id="96ceb-256">To</span></span> | <span data-ttu-id="96ceb-257">源端口</span><span class="sxs-lookup"><span data-stu-id="96ceb-257">Source port</span></span> | <span data-ttu-id="96ceb-258">目标端口</span><span class="sxs-lookup"><span data-stu-id="96ceb-258">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="96ceb-259">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="96ceb-259">SIP/TLS</span></span>| <span data-ttu-id="96ceb-260">SIP 代理</span><span class="sxs-lookup"><span data-stu-id="96ceb-260">SIP Proxy</span></span> | <span data-ttu-id="96ceb-261">SBC</span><span class="sxs-lookup"><span data-stu-id="96ceb-261">SBC</span></span> | <span data-ttu-id="96ceb-262">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="96ceb-262">1024 - 65535</span></span> | <span data-ttu-id="96ceb-263">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="96ceb-263">Defined on the SBC</span></span> |
| <span data-ttu-id="96ceb-264">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="96ceb-264">SIP/TLS</span></span> | <span data-ttu-id="96ceb-265">SBC</span><span class="sxs-lookup"><span data-stu-id="96ceb-265">SBC</span></span> | <span data-ttu-id="96ceb-266">SIP 代理</span><span class="sxs-lookup"><span data-stu-id="96ceb-266">SIP Proxy</span></span> | <span data-ttu-id="96ceb-267">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="96ceb-267">Defined on the SBC</span></span> | <span data-ttu-id="96ceb-268">5061</span><span class="sxs-lookup"><span data-stu-id="96ceb-268">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="96ceb-269">媒体流量：IP 和端口范围</span><span class="sxs-lookup"><span data-stu-id="96ceb-269">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="96ceb-270">如果直接连接可用，则媒体流量在 SBC 和 Teams 客户端之间流动;如果客户端无法使用公共 IP 地址访问 SBC，则通过 Teams 传输中继。</span><span class="sxs-lookup"><span data-stu-id="96ceb-270">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="96ceb-271">Teams 客户端与 SBC (之间的直接媒体流量) </span><span class="sxs-lookup"><span data-stu-id="96ceb-271">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="96ceb-272">客户端必须有权访问指定的端口， (SBC) IP 地址上的表。</span><span class="sxs-lookup"><span data-stu-id="96ceb-272">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="96ceb-273">注意：如果客户端位于内部网络中，则媒体将流向 SBC 的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="96ceb-273">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="96ceb-274">可以在 NAT 设备上配置发固定，使流量永远不会离开企业网络设备。</span><span class="sxs-lookup"><span data-stu-id="96ceb-274">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="96ceb-275">流量</span><span class="sxs-lookup"><span data-stu-id="96ceb-275">Traffic</span></span> | <span data-ttu-id="96ceb-276">从</span><span class="sxs-lookup"><span data-stu-id="96ceb-276">From</span></span> | <span data-ttu-id="96ceb-277">到</span><span class="sxs-lookup"><span data-stu-id="96ceb-277">To</span></span> | <span data-ttu-id="96ceb-278">源端口</span><span class="sxs-lookup"><span data-stu-id="96ceb-278">Source port</span></span> | <span data-ttu-id="96ceb-279">目标端口</span><span class="sxs-lookup"><span data-stu-id="96ceb-279">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="96ceb-280">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="96ceb-280">UDP/SRTP</span></span> | <span data-ttu-id="96ceb-281">客户端</span><span class="sxs-lookup"><span data-stu-id="96ceb-281">Client</span></span> | <span data-ttu-id="96ceb-282">SBC</span><span class="sxs-lookup"><span data-stu-id="96ceb-282">SBC</span></span> | <span data-ttu-id="96ceb-283">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="96ceb-283">50 000 – 50 019</span></span>  | <span data-ttu-id="96ceb-284">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="96ceb-284">Defined on the SBC</span></span> |
| <span data-ttu-id="96ceb-285">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="96ceb-285">UDP/SRTP</span></span> | <span data-ttu-id="96ceb-286">SBC</span><span class="sxs-lookup"><span data-stu-id="96ceb-286">SBC</span></span> | <span data-ttu-id="96ceb-287">客户端</span><span class="sxs-lookup"><span data-stu-id="96ceb-287">Client</span></span> | <span data-ttu-id="96ceb-288">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="96ceb-288">Defined on the SBC</span></span> | <span data-ttu-id="96ceb-289">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="96ceb-289">50 000 – 50 019</span></span>  |


> [!NOTE]
> <span data-ttu-id="96ceb-290">如果有转换客户端源端口的网络设备，请确保在网络设备和 SBC 之间打开转换的端口。</span><span class="sxs-lookup"><span data-stu-id="96ceb-290">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="96ceb-291">使用传输中继的要求</span><span class="sxs-lookup"><span data-stu-id="96ceb-291">Requirements for using Transport Relays</span></span>

<span data-ttu-id="96ceb-292">对于非绕过情况，传输中继与媒体处理器 (相同) ：</span><span class="sxs-lookup"><span data-stu-id="96ceb-292">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="96ceb-293">Microsoft 365、Office 365 和 Office 365 GCC 环境</span><span class="sxs-lookup"><span data-stu-id="96ceb-293">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="96ceb-294">52.112.0.0 /14 (IP 地址从 52.112.0.1 到 52.115.255.254) </span><span class="sxs-lookup"><span data-stu-id="96ceb-294">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="96ceb-295">Office 365 GCC DoD 环境</span><span class="sxs-lookup"><span data-stu-id="96ceb-295">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="96ceb-296">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="96ceb-296">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="96ceb-297">Office 365 GCC 高环境</span><span class="sxs-lookup"><span data-stu-id="96ceb-297">Office 365 GCC High environment</span></span>

- <span data-ttu-id="96ceb-298">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="96ceb-298">52.127.88.0/21</span></span>


<span data-ttu-id="96ceb-299">适用于所有环境 (Teams 传输中继) 范围如下表所示：</span><span class="sxs-lookup"><span data-stu-id="96ceb-299">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="96ceb-300">流量</span><span class="sxs-lookup"><span data-stu-id="96ceb-300">Traffic</span></span> | <span data-ttu-id="96ceb-301">从</span><span class="sxs-lookup"><span data-stu-id="96ceb-301">From</span></span> | <span data-ttu-id="96ceb-302">到</span><span class="sxs-lookup"><span data-stu-id="96ceb-302">To</span></span> | <span data-ttu-id="96ceb-303">源端口</span><span class="sxs-lookup"><span data-stu-id="96ceb-303">Source port</span></span> | <span data-ttu-id="96ceb-304">目标端口</span><span class="sxs-lookup"><span data-stu-id="96ceb-304">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="96ceb-305">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="96ceb-305">UDP/SRTP</span></span> | <span data-ttu-id="96ceb-306">传输中继</span><span class="sxs-lookup"><span data-stu-id="96ceb-306">Transport Relay</span></span> | <span data-ttu-id="96ceb-307">SBC</span><span class="sxs-lookup"><span data-stu-id="96ceb-307">SBC</span></span> | <span data-ttu-id="96ceb-308">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="96ceb-308">50 000 -59 999</span></span>    | <span data-ttu-id="96ceb-309">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="96ceb-309">Defined on the SBC</span></span> |
| <span data-ttu-id="96ceb-310">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="96ceb-310">UDP/SRTP</span></span> | <span data-ttu-id="96ceb-311">SBC</span><span class="sxs-lookup"><span data-stu-id="96ceb-311">SBC</span></span> | <span data-ttu-id="96ceb-312">传输中继</span><span class="sxs-lookup"><span data-stu-id="96ceb-312">Transport Relay</span></span> | <span data-ttu-id="96ceb-313">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="96ceb-313">Defined on the SBC</span></span> | <span data-ttu-id="96ceb-314">50 000 – 59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="96ceb-314">50 000 – 59 999, 3478, 3479</span></span>     |


> [!NOTE]
> <span data-ttu-id="96ceb-315">Microsoft 建议在 SBC 上每个并发调用至少使用两个端口。</span><span class="sxs-lookup"><span data-stu-id="96ceb-315">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="96ceb-316">由于 Microsoft 有两个版本的传输中继，因此需要以下各项：</span><span class="sxs-lookup"><span data-stu-id="96ceb-316">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="96ceb-317">v4，只能使用端口范围 50 000 到 59 999</span><span class="sxs-lookup"><span data-stu-id="96ceb-317">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="96ceb-318">v6，适用于端口 3478、3479</span><span class="sxs-lookup"><span data-stu-id="96ceb-318">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="96ceb-319">目前，媒体绕过仅支持 v4 版本的传输中继。</span><span class="sxs-lookup"><span data-stu-id="96ceb-319">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="96ceb-320">我们将在将来引入对 v6 的支持。</span><span class="sxs-lookup"><span data-stu-id="96ceb-320">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="96ceb-321">需要打开端口 3478 和 3479 进行转换。</span><span class="sxs-lookup"><span data-stu-id="96ceb-321">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="96ceb-322">当 Microsoft 引入了对具有媒体旁路的 v6 传输中继的支持时，不需要重新配置网络设备或 SDC。</span><span class="sxs-lookup"><span data-stu-id="96ceb-322">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="96ceb-323">使用媒体处理器的要求</span><span class="sxs-lookup"><span data-stu-id="96ceb-323">Requirements for using media processors</span></span>

<span data-ttu-id="96ceb-324">媒体处理器始终位于语音应用程序和 Web 客户端的媒体路径中 (例如，Edge 或 Google Chrome 中的 Teams) 。</span><span class="sxs-lookup"><span data-stu-id="96ceb-324">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="96ceb-325">要求与非绕过配置相同。</span><span class="sxs-lookup"><span data-stu-id="96ceb-325">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="96ceb-326">媒体流量的 IP 范围为</span><span class="sxs-lookup"><span data-stu-id="96ceb-326">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="96ceb-327">Office 365 和 Office 365 GCC 环境</span><span class="sxs-lookup"><span data-stu-id="96ceb-327">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="96ceb-328">52.112.0.0 /14 (IP 地址从 52.112.0.1 到 52.115.255.254) </span><span class="sxs-lookup"><span data-stu-id="96ceb-328">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="96ceb-329">Office 365 GCC DoD 环境</span><span class="sxs-lookup"><span data-stu-id="96ceb-329">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="96ceb-330">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="96ceb-330">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="96ceb-331">Office 365 GCC 高环境</span><span class="sxs-lookup"><span data-stu-id="96ceb-331">Office 365 GCC High environment</span></span>

- <span data-ttu-id="96ceb-332">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="96ceb-332">52.127.88.0/21</span></span>

<span data-ttu-id="96ceb-333">下表显示了适用于所有 (环境的媒体处理器) 范围：</span><span class="sxs-lookup"><span data-stu-id="96ceb-333">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="96ceb-334">流量</span><span class="sxs-lookup"><span data-stu-id="96ceb-334">Traffic</span></span> | <span data-ttu-id="96ceb-335">从</span><span class="sxs-lookup"><span data-stu-id="96ceb-335">From</span></span> | <span data-ttu-id="96ceb-336">到</span><span class="sxs-lookup"><span data-stu-id="96ceb-336">To</span></span> | <span data-ttu-id="96ceb-337">源端口</span><span class="sxs-lookup"><span data-stu-id="96ceb-337">Source port</span></span> | <span data-ttu-id="96ceb-338">目标端口</span><span class="sxs-lookup"><span data-stu-id="96ceb-338">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="96ceb-339">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="96ceb-339">UDP/SRTP</span></span> | <span data-ttu-id="96ceb-340">媒体处理器</span><span class="sxs-lookup"><span data-stu-id="96ceb-340">Media Processor</span></span> | <span data-ttu-id="96ceb-341">SBC</span><span class="sxs-lookup"><span data-stu-id="96ceb-341">SBC</span></span> | <span data-ttu-id="96ceb-342">3478、3479 和 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="96ceb-342">3478, 3479 and 49 152 – 53 247</span></span>    | <span data-ttu-id="96ceb-343">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="96ceb-343">Defined on the SBC</span></span> |
| <span data-ttu-id="96ceb-344">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="96ceb-344">UDP/SRTP</span></span> | <span data-ttu-id="96ceb-345">SBC</span><span class="sxs-lookup"><span data-stu-id="96ceb-345">SBC</span></span> | <span data-ttu-id="96ceb-346">媒体处理器</span><span class="sxs-lookup"><span data-stu-id="96ceb-346">Media Processor</span></span> | <span data-ttu-id="96ceb-347">在 SBC 上定义</span><span class="sxs-lookup"><span data-stu-id="96ceb-347">Defined on the SBC</span></span> | <span data-ttu-id="96ceb-348">3478、3479 和 49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="96ceb-348">3478, 3479 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="96ceb-349">为媒体旁路和非媒体旁路配置单独的中继</span><span class="sxs-lookup"><span data-stu-id="96ceb-349">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="96ceb-350">如果要从非媒体旁路迁移到媒体旁路，并且想要在将所有使用迁移到媒体旁路之前确认功能，可以创建单独的中继和单独的联机语音路由策略，以路由到媒体旁路中继并分配给特定用户。</span><span class="sxs-lookup"><span data-stu-id="96ceb-350">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="96ceb-351">高级配置步骤：</span><span class="sxs-lookup"><span data-stu-id="96ceb-351">High-level configuration steps:</span></span>

- <span data-ttu-id="96ceb-352">标识要测试媒体绕过的用户。</span><span class="sxs-lookup"><span data-stu-id="96ceb-352">Identify users to test media bypass.</span></span>

- <span data-ttu-id="96ceb-353">使用不同的 FQDN 创建两个单独的中继：一个已启用媒体旁路;另一个不是。</span><span class="sxs-lookup"><span data-stu-id="96ceb-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="96ceb-354">这两个中继都指向同一 SBC。</span><span class="sxs-lookup"><span data-stu-id="96ceb-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="96ceb-355">TLS SIP 信号的端口必须不同。</span><span class="sxs-lookup"><span data-stu-id="96ceb-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="96ceb-356">媒体的端口必须相同。</span><span class="sxs-lookup"><span data-stu-id="96ceb-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="96ceb-357">创建新的联机语音路由策略，并将媒体旁路中继分配到与此策略的 PSTN 使用情况关联的相应路由。</span><span class="sxs-lookup"><span data-stu-id="96ceb-357">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="96ceb-358">将新的联机语音路由策略分配给标识为测试媒体绕过的用户。</span><span class="sxs-lookup"><span data-stu-id="96ceb-358">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="96ceb-359">以下示例演示了此逻辑。</span><span class="sxs-lookup"><span data-stu-id="96ceb-359">The example below illustrates this logic.</span></span>

| <span data-ttu-id="96ceb-360">一组用户</span><span class="sxs-lookup"><span data-stu-id="96ceb-360">Set of users</span></span> | <span data-ttu-id="96ceb-361">用户数</span><span class="sxs-lookup"><span data-stu-id="96ceb-361">Number of users</span></span> | <span data-ttu-id="96ceb-362">在 OVRP 中分配的中继 FQDN</span><span class="sxs-lookup"><span data-stu-id="96ceb-362">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="96ceb-363">已启用媒体旁路</span><span class="sxs-lookup"><span data-stu-id="96ceb-363">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="96ceb-364">具有非媒体旁路中继的用户</span><span class="sxs-lookup"><span data-stu-id="96ceb-364">Users with non-media bypass trunk</span></span> | <span data-ttu-id="96ceb-365">980</span><span class="sxs-lookup"><span data-stu-id="96ceb-365">980</span></span> | <span data-ttu-id="96ceb-366">sbc1.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="96ceb-366">sbc1.contoso.com:5060</span></span> | <span data-ttu-id="96ceb-367">true</span><span class="sxs-lookup"><span data-stu-id="96ceb-367">true</span></span>
<span data-ttu-id="96ceb-368">具有媒体旁路中继的用户</span><span class="sxs-lookup"><span data-stu-id="96ceb-368">Users with media bypass trunk</span></span> | <span data-ttu-id="96ceb-369">20</span><span class="sxs-lookup"><span data-stu-id="96ceb-369">20</span></span> | <span data-ttu-id="96ceb-370">sbc2.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="96ceb-370">sbc2.contoso.com:5061</span></span> | <span data-ttu-id="96ceb-371">false</span><span class="sxs-lookup"><span data-stu-id="96ceb-371">false</span></span> | 

<span data-ttu-id="96ceb-372">这两个中继可以指向同一公共 IP 地址相同的 SBC。</span><span class="sxs-lookup"><span data-stu-id="96ceb-372">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="96ceb-373">SBC 上的 TLS 信号端口必须不同，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="96ceb-373">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="96ceb-374">请注意，需要确保证书支持这两个中继。</span><span class="sxs-lookup"><span data-stu-id="96ceb-374">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="96ceb-375">在 SAN 中，需要具有两个名称 (sbc1.contoso.com **和** **sbc2.contoso.com)** 或具有通配符证书。</span><span class="sxs-lookup"><span data-stu-id="96ceb-375">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="96ceb-376">![显示两个中继可以指向同一公共 IP 相同的 SBC](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="96ceb-376">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="96ceb-377">若要了解如何在同一 SBC 上配置两个中继，请参阅 SBC 供应商提供的文档：</span><span class="sxs-lookup"><span data-stu-id="96ceb-377">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="96ceb-378">AudioCodes 部署文档</span><span class="sxs-lookup"><span data-stu-id="96ceb-378">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="96ceb-379">Oracle 部署文档</span><span class="sxs-lookup"><span data-stu-id="96ceb-379">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="96ceb-380">功能区通信部署文档</span><span class="sxs-lookup"><span data-stu-id="96ceb-380">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="96ceb-381">TE-Systems (anynode) 部署文档</span><span class="sxs-lookup"><span data-stu-id="96ceb-381">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="96ceb-382">媒体旁路支持的客户端终结点</span><span class="sxs-lookup"><span data-stu-id="96ceb-382">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="96ceb-383">所有独立的 Teams 桌面客户端、Android 和 iOS 客户端以及 Teams Phone 设备都支持媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="96ceb-383">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="96ceb-384">对于不支持媒体旁路的所有其他终结点，我们会将呼叫转换为非旁路，即使它作为绕过呼叫启动。</span><span class="sxs-lookup"><span data-stu-id="96ceb-384">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="96ceb-385">这会自动发生，不需要管理员执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="96ceb-385">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="96ceb-386">这包括 Skype for Business 3PIP 电话和 Teams Web 客户端，这些客户端支持在 Microsoft Edge、Google Chrome、Mozilla Firefox) 上运行的基于 (WebRTC 的客户端进行直接路由。</span><span class="sxs-lookup"><span data-stu-id="96ceb-386">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="96ceb-387">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96ceb-387">See also</span></span>

[<span data-ttu-id="96ceb-388">使用直接路由配置媒体旁路</span><span class="sxs-lookup"><span data-stu-id="96ceb-388">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)