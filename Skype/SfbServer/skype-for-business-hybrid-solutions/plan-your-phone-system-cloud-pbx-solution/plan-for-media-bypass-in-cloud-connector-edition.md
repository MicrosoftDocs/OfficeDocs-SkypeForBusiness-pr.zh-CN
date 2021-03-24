---
title: 云连接器版本中的媒体旁路规划
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: 阅读本主题，查看使用云连接器版本 2.0 版和更高版本实现媒体旁路的规划注意事项。 有关部署媒体旁路的信息，请参阅在云连接器版本中部署媒体旁路。
ms.openlocfilehash: bae10c77a6b382eaca7189ed6ae52960a6fb1bf9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096196"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="5ec42-104">云连接器版本中的媒体旁路规划</span><span class="sxs-lookup"><span data-stu-id="5ec42-104">Plan for media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="5ec42-105">阅读本主题，查看使用云连接器版本 2.0 版和更高版本实现媒体旁路的规划注意事项。</span><span class="sxs-lookup"><span data-stu-id="5ec42-105">Read this topic to review planning considerations for implementing media bypass with Cloud Connector Edition version 2.0 and later.</span></span> <span data-ttu-id="5ec42-106">有关部署媒体旁路的信息，请参阅 [在云连接器版本中部署媒体旁路](deploy-media-bypass-in-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="5ec42-106">For information about deploying media bypass, see [Deploy media bypass in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md).</span></span>
  
<span data-ttu-id="5ec42-107">媒体旁路允许客户端将媒体直接发送到公用电话交换网 (PSTN) 下一个跃点（网关或会话边界控制器 (SBC) ）并消除媒体路径中的云连接器版本组件。</span><span class="sxs-lookup"><span data-stu-id="5ec42-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span>
  
<span data-ttu-id="5ec42-108">媒体旁路功能可以通过降低延迟、丢失数据包的可能性以及潜在的故障点数来提高语音质量。</span><span class="sxs-lookup"><span data-stu-id="5ec42-108">Media bypass can improve voice quality by reducing latency, the possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="5ec42-109">消除旁路呼叫的媒体处理可以减少云连接器上的负载，从而增加并发呼叫数，并可以改进可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="5ec42-109">Elimination of media processing for bypassed calls reduces the load on Cloud Connector, which enables a higher number of concurrent calls, and can improve scalability.</span></span> 
  
 <span data-ttu-id="5ec42-110">从媒体处理任务中释放云连接器可能会减少基础结构所需的云连接器设备的数量，因此应尽可能启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="5ec42-110">Freeing Cloud Connector from media processing tasks may reduce the number of Cloud Connector appliances an infrastructure requires, so you should enable media bypass whenever possible.</span></span>
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a><span data-ttu-id="5ec42-111">媒体旁路如何影响媒体和信号路径</span><span class="sxs-lookup"><span data-stu-id="5ec42-111">How media bypass affects media and signaling pathways</span></span>

<span data-ttu-id="5ec42-112">虽然信号采用相同路径（带或不带媒体旁路功能）时，媒体流将有所不同。</span><span class="sxs-lookup"><span data-stu-id="5ec42-112">While signaling takes the same path with or without media bypass, the media flow will differ.</span></span> <span data-ttu-id="5ec42-113">下图显示了具有和没有媒体旁路的拓扑中的媒体和信号路径。</span><span class="sxs-lookup"><span data-stu-id="5ec42-113">The following diagrams show media and signaling pathways in topologies with and without media bypass.</span></span> 
  
<span data-ttu-id="5ec42-114">例如，在下列拓扑（不采用媒体旁路）中，Skype for Business 客户端向外部号码发出 PSTN 呼叫，SIP 信号将转到 Microsoft 365 或 Office 365，根据最终用户语音策略将信号流量引导到该拓扑。</span><span class="sxs-lookup"><span data-stu-id="5ec42-114">For example, in the following topology—which does not employ media bypass—a Skype for Business client places a PSTN call to an external number, the SIP signaling goes to Microsoft 365 or Office 365, which directs the signaling traffic according to the end-user voice policy.</span></span> <span data-ttu-id="5ec42-115">对于云连接器用户，语音策略将信号通信路由到云连接器边缘服务器，然后该服务器通过云连接器中介服务器将信号通信路由到 PSTN 会话边界控制器 (SBC) 或网关。</span><span class="sxs-lookup"><span data-stu-id="5ec42-115">For Cloud Connector users, the voice policy directs signaling traffic to the Cloud Connector Edge Server, which then routes the signaling traffic to a PSTN Session Border Controller (SBC) or gateway via the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="5ec42-116">媒体从 Skype for Business 客户端流到云连接器中介服务器，然后流到 SBC 或网关，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="5ec42-116">Media flows from the Skype for Business client to the Cloud Connector Mediation Server, and then to the SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="5ec42-117">**没有媒体旁路的媒体和信号路径**</span><span class="sxs-lookup"><span data-stu-id="5ec42-117">**Media and signaling pathways without media bypass**</span></span>

![无媒体旁路功能的信号](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
<span data-ttu-id="5ec42-119">来自 PSTN 的入站呼叫在相反方向使用相同的信号路径。</span><span class="sxs-lookup"><span data-stu-id="5ec42-119">An inbound call from the PSTN uses the same signaling path in the reverse direction.</span></span> <span data-ttu-id="5ec42-120">对于内部用户，媒体最终仍将在 Skype for Business 客户端和云连接器中介服务器之间流动，然后再在 SBC 或网关之间流动。</span><span class="sxs-lookup"><span data-stu-id="5ec42-120">For internal users, media will still ultimately flow between the Skype for Business client and the Cloud Connector Mediation Server and then the SBC or gateway.</span></span>
  
<span data-ttu-id="5ec42-121">在采用媒体旁路的下一个拓扑中，信号采用相同的路径，但媒体直接在 Skype for Business 客户端和 SBC 或网关之间流动，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="5ec42-121">In the next topology—which does employ media bypass—signaling takes the same path, but media flows directly between the Skype for Business client and the SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="5ec42-122">**具有媒体旁路的媒体和信号路径**</span><span class="sxs-lookup"><span data-stu-id="5ec42-122">**Media and signaling pathways with media bypass**</span></span>

![带媒体旁路的信号](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a><span data-ttu-id="5ec42-124">多站点方案和媒体旁路</span><span class="sxs-lookup"><span data-stu-id="5ec42-124">Multi-site scenario and media bypass</span></span>

<span data-ttu-id="5ec42-125">当你希望使用单个云连接器设备向多个站点提供电话服务时，媒体旁路也很有用。</span><span class="sxs-lookup"><span data-stu-id="5ec42-125">Media bypass is also useful when you want to provide telephony services to multiple sites using a single Cloud Connector appliance.</span></span> <span data-ttu-id="5ec42-126">由于云连接器无法基于源或目标号码路由呼叫，因此大多数企业在云连接器后面部署 SBC 或网关以做出路由决策。</span><span class="sxs-lookup"><span data-stu-id="5ec42-126">Because Cloud Connector cannot route calls based on source or destination numbers, most enterprises deploy an SBC or gateway behind Cloud Connector to make routing decisions.</span></span> <span data-ttu-id="5ec42-127">此方案中的媒体旁路消除了客户端与中央 SBC 或网关之间的跃点，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="5ec42-127">Media bypass in this scenario eliminates the hop between the client and the central SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="5ec42-128">**多站点应用程序**</span><span class="sxs-lookup"><span data-stu-id="5ec42-128">**Multi-site application**</span></span>

![云连接器多站点示例](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. <span data-ttu-id="5ec42-130">SIP 流量从苏黎世的用户流向 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="5ec42-130">The SIP traffic flows from the user in Zurich to Microsoft 365 or Office 365.</span></span>
    
2. <span data-ttu-id="5ec42-131">然后，流量将路由到位于阿姆斯特丹的云连接器设备，如用户语音路由策略中指定。</span><span class="sxs-lookup"><span data-stu-id="5ec42-131">The traffic then routes to the Cloud Connector appliance in Amsterdam as specified in the user voice routing policy.</span></span>
    
3. <span data-ttu-id="5ec42-132">位于阿姆斯特丹的云连接器设备将 SIP 流量发送到阿姆斯特丹的中央网关。</span><span class="sxs-lookup"><span data-stu-id="5ec42-132">The Cloud Connector appliance in Amsterdam sends the SIP traffic to the central gateway in Amsterdam.</span></span>
    
4. <span data-ttu-id="5ec42-133">阿姆斯特丹的中央网关做出相应的路由决策，然后将流量发送到位于阿姆斯特丹的 SBC 或网关，而媒体直接在 Skype for Business 客户端与位于阿姆斯特丹的 SBC 或网关之间流动。</span><span class="sxs-lookup"><span data-stu-id="5ec42-133">The central gateway in Amsterdam makes the appropriate routing decisions, and then sends the traffic to an SBC or gateway in Zurich, while media flows directly between the Skype for Business client and SBC or gateway in Amsterdam.</span></span>
    
   <span data-ttu-id="5ec42-134">此方法允许每个云连接器部署（其中云连接器集中）为更多用户服务。</span><span class="sxs-lookup"><span data-stu-id="5ec42-134">This approach allows serving more users per one Cloud Connector deployment where Cloud Connector is centralized.</span></span> <span data-ttu-id="5ec42-135">即使从媒体路径中消除云连接器，在集中的多站点方案中，媒体仍可能会按需要遍历 WAN 两次，以通过集中式 SBC 或网关。</span><span class="sxs-lookup"><span data-stu-id="5ec42-135">Even though Cloud Connector is eliminated from the media path, in a centralized multi-site scenario media may still traverse the WAN twice as required to flow through the centralized SBC or gateway.</span></span>
  
<span data-ttu-id="5ec42-136">如果客户端位于发出出站呼叫的企业网络外部，则媒体流量通过云连接器的边缘服务器和中介服务器以及位于阿姆斯特丹与阿姆斯特丹之间的 WAN 链路流动，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="5ec42-136">If a client is outside the corporate network placing an outbound call, the media traffic flows via the Edge and Mediation servers of Cloud Connector and WAN link between Zurich and Amsterdam, as shown in the following diagram:</span></span>
  
![云连接器多站点示例 2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a><span data-ttu-id="5ec42-138">支持媒体旁路的客户端</span><span class="sxs-lookup"><span data-stu-id="5ec42-138">Supported clients for media bypass</span></span>

<span data-ttu-id="5ec42-139">首次发布媒体旁路功能后，唯一受支持的客户端是 Skype for Business 2016 Windows 客户端，它是 Microsoft 365 企业应用版版本 16.0.7870.2020 或更大版本的一部分。</span><span class="sxs-lookup"><span data-stu-id="5ec42-139">With the first release of media bypass, the only supported client is the Skype for Business 2016 Windows Client that is part of Microsoft 365 Apps for enterprise, version 16.0.7870.2020 or greater.</span></span> <span data-ttu-id="5ec42-140">客户可以使用任何频道：Current、Deferred 或 First Release Deferred。</span><span class="sxs-lookup"><span data-stu-id="5ec42-140">Customers can use any channel: Current, Deferred, or First Release Deferred.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5ec42-141">如果你将客户端 VPN 解决方案与 Skype for Business 客户端结合使用，则媒体旁路仅受 VPN 拆分隧道配置支持。</span><span class="sxs-lookup"><span data-stu-id="5ec42-141">If you are using a client VPN solution in combination with the Skype for Business client, then media bypass is supported only with a VPN split-tunnel configuration.</span></span> 
  
<span data-ttu-id="5ec42-142">有关发布频道详细信息，请参阅 [Microsoft 365](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US)企业应用版更新频道概述。</span><span class="sxs-lookup"><span data-stu-id="5ec42-142">For more information about the release channels, see [Overview of update channels for Microsoft 365 Apps for enterprise](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
<span data-ttu-id="5ec42-143">有关不同渠道中客户端的当前发行版，请参阅 [Microsoft 365](/officeupdates/release-notes-office365-proplus)企业应用版更新的发布信息。</span><span class="sxs-lookup"><span data-stu-id="5ec42-143">For the current release version of the clients in different channels, see [Release information for updates to Microsoft 365 Apps for enterprise](/officeupdates/release-notes-office365-proplus).</span></span> 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a><span data-ttu-id="5ec42-144">媒体旁路的云连接器容量注意事项</span><span class="sxs-lookup"><span data-stu-id="5ec42-144">Cloud Connector capacity considerations with media bypass</span></span>

<span data-ttu-id="5ec42-145">没有媒体旁路功能（具体取决于硬件）云连接器设备可以处理 50 到 500 个同时呼叫，这些呼叫需要媒体通过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="5ec42-145">Without media bypass—and depending on the hardware—a Cloud Connector appliance can handle from 50 to 500 simultaneous calls that require media to travel through a Mediation Server.</span></span> <span data-ttu-id="5ec42-146">有关详细信息，请参阅[Plan for Skype for Business Cloud Connector Edition。](./plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="5ec42-146">For more information, see [Plan for Skype for Business Cloud Connector Edition](./plan-skype-for-business-cloud-connector-edition.md).</span></span> 
  
<span data-ttu-id="5ec42-147">启用媒体旁路后，受支持版本上的内部客户端不使用中介服务器，因此内部客户端的数量会显著增加。</span><span class="sxs-lookup"><span data-stu-id="5ec42-147">With media bypass enabled, internal clients on the supported version do not use the Mediation Server, so the number of internal clients can increase significantly.</span></span> 
  
<span data-ttu-id="5ec42-148">如上所述，外部客户端或不受支持的客户端将云连接器边缘和中介服务器用于媒体。</span><span class="sxs-lookup"><span data-stu-id="5ec42-148">As noted above, external clients or unsupported clients will use the Cloud Connector Edge and Mediation servers for media.</span></span> <span data-ttu-id="5ec42-149">在计算站点中应放置多少云连接器设备时，必须考虑来自外部用户的流量和不受支持客户端上的用户的流量。</span><span class="sxs-lookup"><span data-stu-id="5ec42-149">When calculating how many Cloud Connector appliances should be placed in a site, you must consider traffic from external users and users on unsupported clients.</span></span>
  
## <a name="cloud-connector-supports-always-bypass-mode"></a><span data-ttu-id="5ec42-150">云连接器支持"始终绕过"模式</span><span class="sxs-lookup"><span data-stu-id="5ec42-150">Cloud Connector supports Always Bypass mode</span></span>

<span data-ttu-id="5ec42-151">云连接器仅支持"始终绕过"模式。</span><span class="sxs-lookup"><span data-stu-id="5ec42-151">Cloud Connector supports Always Bypass mode only.</span></span> <span data-ttu-id="5ec42-152">在本地环境中，有两个选项："始终绕过"和"使用站点和地区信息"。</span><span class="sxs-lookup"><span data-stu-id="5ec42-152">In on-premises environments, there are two options: Always Bypass and Use Site and Region Information.</span></span>
  
<span data-ttu-id="5ec42-153">始终绕过意味着将尝试媒体旁路以将内部客户端作为源或目标点的所有 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="5ec42-153">Always Bypass means that media bypass will be attempted for all PSTN calls with internal clients as an origin or destination point.</span></span> <span data-ttu-id="5ec42-154">若要确定客户端是内部客户端还是外部客户端，需使用中介服务器虚拟机上的网站。</span><span class="sxs-lookup"><span data-stu-id="5ec42-154">To determine if the client is internal or external, a web site on the mediation server virtual machine is used.</span></span> <span data-ttu-id="5ec42-155">如果客户端可以到达该站点，则被视为内部站点，并且使用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="5ec42-155">If the client can reach the site, it is considered internal and media bypass is used.</span></span> <span data-ttu-id="5ec42-156">如果客户端无法访问站点 (例如，客户端位于家庭) ，则不能使用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="5ec42-156">If the client cannot reach the site (for example the client is on a home network), media bypass is not used.</span></span> 
  
<span data-ttu-id="5ec42-157">始终绕过需要在用户和 PSTN 站点内的 PSTN 网关之间建立无结构连接。</span><span class="sxs-lookup"><span data-stu-id="5ec42-157">Always Bypass requires unobstructed connectivity between users and the PSTN gateways within a PSTN Site.</span></span> 
  
<span data-ttu-id="5ec42-158">有关详细信息，请参阅[Plan for Skype for Business Cloud Connector Edition。](./plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="5ec42-158">For more information, see [Plan for Skype for Business Cloud Connector Edition](./plan-skype-for-business-cloud-connector-edition.md).</span></span> 
  
<span data-ttu-id="5ec42-159">例如，在下图中，欧洲用户必须很好地连接到位于阿姆斯特丹的三个会话边界控制器 (SDC) ，而美国西部的用户必须很好地连接到西雅图的两个 SDC。</span><span class="sxs-lookup"><span data-stu-id="5ec42-159">For example, in the diagram below, Europe users must be well connected to the three Session Border Controllers (SBCs) in Amsterdam while US West users must be well connected to the two SBCs in Seattle.</span></span> <span data-ttu-id="5ec42-160">连接良好意味着它们位于与 SDC 或网关相同的网络站点中，或者位于具有适当带宽的 WAN 链路上。</span><span class="sxs-lookup"><span data-stu-id="5ec42-160">Well connected means that they are either located in the same network sites as the SBCs or gateways, or over WAN links that have proper bandwidth.</span></span>
  
![云连接器容量](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> <span data-ttu-id="5ec42-162">如果来自阿姆斯特丹的用户出差到西雅图办事处，并且你想要使用内部网络在出差的用户和位于欧洲 (的网关之间传递媒体流量，而不是通过 Internet) ，则必须确保西雅图办事处和欧洲 SDC 或网关所在的阿姆斯特丹办事处符合连接条件。</span><span class="sxs-lookup"><span data-stu-id="5ec42-162">If a user from Zurich travels to the Seattle office, and you want to use the internal network to deliver media traffic between the traveling user and gateways in Europe (as opposed to going over the Internet), then you must make sure the Seattle office and the Amsterdam office where European SBCs or gateways are located qualify as well connected.</span></span> 
  
## <a name="codecs-used-in-media-bypass"></a><span data-ttu-id="5ec42-163">媒体旁路中使用的编解码器</span><span class="sxs-lookup"><span data-stu-id="5ec42-163">Codecs used in media bypass</span></span>

<span data-ttu-id="5ec42-164">启用媒体旁路后，客户端与 SBC 或网关之间的媒体流量将使用 G.711 编解码器。</span><span class="sxs-lookup"><span data-stu-id="5ec42-164">With media bypass enabled, media traffic between a client and an SBC or gateway uses the G.711 codec.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5ec42-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ec42-165">See also</span></span>

[<span data-ttu-id="5ec42-166">在云连接器版本中部署媒体旁路</span><span class="sxs-lookup"><span data-stu-id="5ec42-166">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md)