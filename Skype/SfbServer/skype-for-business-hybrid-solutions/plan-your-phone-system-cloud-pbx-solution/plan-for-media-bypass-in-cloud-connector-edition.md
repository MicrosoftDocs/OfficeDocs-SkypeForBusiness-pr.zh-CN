---
title: 在云连接器版本中规划媒体旁路
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
description: 阅读本主题，以了解使用云连接器版本 2.0 版和更高版本实现媒体旁路的规划注意事项。 有关部署媒体绕过的信息，请参阅在云连接器版本中部署媒体旁路。
ms.openlocfilehash: 67598cbe31dac074bf360ba6fe1462544fe12c5b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814490"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="db843-104">在云连接器版本中规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="db843-104">Plan for media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="db843-105">阅读本主题，以了解使用云连接器版本 2.0 版和更高版本实现媒体旁路的规划注意事项。</span><span class="sxs-lookup"><span data-stu-id="db843-105">Read this topic to review planning considerations for implementing media bypass with Cloud Connector Edition version 2.0 and later.</span></span> <span data-ttu-id="db843-106">有关部署媒体绕过的信息，请参阅[在云连接器版本中部署媒体旁路](deploy-media-bypass-in-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="db843-106">For information about deploying media bypass, see [Deploy media bypass in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md).</span></span>
  
<span data-ttu-id="db843-107">媒体绕过允许客户将媒体直接发送到公共交换式电话网络（PSTN）下一跃点（即网关或会话边界控制器（SBC）），并从媒体路径中删除云连接器版本组件。</span><span class="sxs-lookup"><span data-stu-id="db843-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span>
  
<span data-ttu-id="db843-108">媒体旁路功能可通过减少延迟、可能的数据包丢失和潜在的故障点数来提高语音质量。</span><span class="sxs-lookup"><span data-stu-id="db843-108">Media bypass can improve voice quality by reducing latency, the possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="db843-109">消除绕过通话的媒体处理可减少云连接线上的负载，从而实现更高的并发通话次数，并且可以提高可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="db843-109">Elimination of media processing for bypassed calls reduces the load on Cloud Connector, which enables a higher number of concurrent calls, and can improve scalability.</span></span> 
  
 <span data-ttu-id="db843-110">从媒体处理任务中释放云连接器可能会减少基础结构所需的云连接器装置的数量，因此应尽可能启用 "媒体绕过"。</span><span class="sxs-lookup"><span data-stu-id="db843-110">Freeing Cloud Connector from media processing tasks may reduce the number of Cloud Connector appliances an infrastructure requires, so you should enable media bypass whenever possible.</span></span>
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a><span data-ttu-id="db843-111">媒体旁路对媒体和信号路径的影响</span><span class="sxs-lookup"><span data-stu-id="db843-111">How media bypass affects media and signaling pathways</span></span>

<span data-ttu-id="db843-p104">在具有和没有媒体旁路时，虽然发送信号都会采用相同的路径，但媒体流会有所不同。下图显示了具有和没有媒体旁路功能的拓扑中的媒体和信号路径。</span><span class="sxs-lookup"><span data-stu-id="db843-p104">While signaling takes the same path with or without media bypass, the media flow will differ. The following diagrams show media and signaling pathways in topologies with and without media bypass.</span></span> 
  
<span data-ttu-id="db843-114">例如，在以下拓扑（不使用媒体旁路）中，Skype for Business 客户端将 PSTN 呼叫置于外部号码，SIP 信号转到 Office 365，然后 Office 365 将根据最终用户的语音指示信号流量设置.</span><span class="sxs-lookup"><span data-stu-id="db843-114">For example, in the following topology—which does not employ media bypass—a Skype for Business client places a PSTN call to an external number, the SIP signaling goes to Office 365, and Office 365 then directs the signaling traffic according to the end-user voice policy.</span></span> <span data-ttu-id="db843-115">对于云连接器用户，语音策略将通知流量定向到云连接器边缘服务器，然后通过云连接器中介服务器将信号流量路由到 PSTN 会话边界控制器（SBC）或网关。</span><span class="sxs-lookup"><span data-stu-id="db843-115">For Cloud Connector users, the voice policy directs signaling traffic to the Cloud Connector Edge Server, which then routes the signaling traffic to a PSTN Session Border Controller (SBC) or gateway via the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="db843-116">媒体从 Skype for Business 客户端流向云连接器中介服务器，然后指向 SBC 或网关，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="db843-116">Media flows from the Skype for Business client to the Cloud Connector Mediation Server, and then to the SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="db843-117">**没有媒体旁路功能的媒体和信号路径**</span><span class="sxs-lookup"><span data-stu-id="db843-117">**Media and signaling pathways without media bypass**</span></span>

![没有媒体旁路功能的信号](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
<span data-ttu-id="db843-119">来自 PSTN 的拨入通话将以相反方向使用相同的信号路径。</span><span class="sxs-lookup"><span data-stu-id="db843-119">An inbound call from the PSTN uses the same signaling path in the reverse direction.</span></span> <span data-ttu-id="db843-120">对于内部用户，媒体仍将在 Skype for Business 客户端和云连接器中介服务器以及 SBC 或网关之间最终流动。</span><span class="sxs-lookup"><span data-stu-id="db843-120">For internal users, media will still ultimately flow between the Skype for Business client and the Cloud Connector Mediation Server and then the SBC or gateway.</span></span>
  
<span data-ttu-id="db843-121">在下一个拓扑中，它可以使用媒体旁路-信号采用相同的路径，但媒体直接在 Skype for Business 客户端和 SBC 或网关之间流动，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="db843-121">In the next topology—which does employ media bypass—signaling takes the same path, but media flows directly between the Skype for Business client and the SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="db843-122">**具有媒体旁路功能的媒体和信号路径**</span><span class="sxs-lookup"><span data-stu-id="db843-122">**Media and signaling pathways with media bypass**</span></span>

![有媒体旁路功能的信号](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a><span data-ttu-id="db843-124">多站点方案和媒体旁路</span><span class="sxs-lookup"><span data-stu-id="db843-124">Multi-site scenario and media bypass</span></span>

<span data-ttu-id="db843-125">当您希望使用单个云连接器设备向多个站点提供电话服务时，媒体绕过功能也很有用。</span><span class="sxs-lookup"><span data-stu-id="db843-125">Media bypass is also useful when you want to provide telephony services to multiple sites using a single Cloud Connector appliance.</span></span> <span data-ttu-id="db843-126">由于云连接器无法基于源或目标号码路由呼叫，因此大多数企业都在云连接器背后部署 SBC 或网关以做出路由决策。</span><span class="sxs-lookup"><span data-stu-id="db843-126">Because Cloud Connector cannot route calls based on source or destination numbers, most enterprises deploy an SBC or gateway behind Cloud Connector to make routing decisions.</span></span> <span data-ttu-id="db843-127">在此方案中，媒体旁路使客户端与中心 SBC 或网关之间不再存在跃点，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="db843-127">Media bypass in this scenario eliminates the hop between the client and the central SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="db843-128">**多站点应用**</span><span class="sxs-lookup"><span data-stu-id="db843-128">**Multi-site application**</span></span>

![云连接器多站点示例](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. <span data-ttu-id="db843-130">SIP 流量从苏黎世用户流入到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="db843-130">The SIP traffic flows from the user in Zurich to Office 365.</span></span>
    
2. <span data-ttu-id="db843-131">然后，流量将按用户语音路由策略中指定的阿姆斯特丹路由到云连接器装置。</span><span class="sxs-lookup"><span data-stu-id="db843-131">The traffic then routes to the Cloud Connector appliance in Amsterdam as specified in the user voice routing policy.</span></span>
    
3. <span data-ttu-id="db843-132">阿姆斯特丹中的云连接器装置将 SIP 流量发送到位于阿姆斯特丹的中央网关。</span><span class="sxs-lookup"><span data-stu-id="db843-132">The Cloud Connector appliance in Amsterdam sends the SIP traffic to the central gateway in Amsterdam.</span></span>
    
4. <span data-ttu-id="db843-133">在阿姆斯特丹中，"中央网关" 建立适当的路由决策，然后将流量发送到苏黎世中的 SBC 或网关，而媒体直接在 Skype for Business 客户端和 SBC 或网关之间以阿姆斯特丹的形式流动。</span><span class="sxs-lookup"><span data-stu-id="db843-133">The central gateway in Amsterdam makes the appropriate routing decisions, and then sends the traffic to an SBC or gateway in Zurich, while media flows directly between the Skype for Business client and SBC or gateway in Amsterdam.</span></span>
    
   <span data-ttu-id="db843-134">此方法允许为每一个云连接器部署提供更多用户，其中云连接器是集中式的。</span><span class="sxs-lookup"><span data-stu-id="db843-134">This approach allows serving more users per one Cloud Connector deployment where Cloud Connector is centralized.</span></span> <span data-ttu-id="db843-135">即使从媒体路径中消除了云连接器，在集中式多站点方案媒体中，仍可能会根据需要将 WAN 传递两次，以流过集中的 SBC 或网关。</span><span class="sxs-lookup"><span data-stu-id="db843-135">Even though Cloud Connector is eliminated from the media path, in a centralized multi-site scenario media may still traverse the WAN twice as required to flow through the centralized SBC or gateway.</span></span>
  
<span data-ttu-id="db843-136">如果客户端在公司网络外部放置出站呼叫，则媒体流量将通过苏黎世和阿姆斯特丹之间的云连接器和 WAN 链接的边缘和中介服务器流动，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="db843-136">If a client is outside the corporate network placing an outbound call, the media traffic flows via the Edge and Mediation servers of Cloud Connector and WAN link between Zurich and Amsterdam, as shown in the following diagram:</span></span>
  
![云连接器多站点示例 2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a><span data-ttu-id="db843-138">支持使用媒体旁路的客户端</span><span class="sxs-lookup"><span data-stu-id="db843-138">Supported clients for media bypass</span></span>

<span data-ttu-id="db843-139">第一次发布媒体旁路时，唯一支持的客户是 Office 365 专业增强版的 Skype for business 2016 Windows 客户端，版本16.0.7870.2020 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="db843-139">With the first release of media bypass, the only supported client is the Skype for Business 2016 Windows Client that is part of Office 365 ProPlus, version 16.0.7870.2020 or greater.</span></span> <span data-ttu-id="db843-140">客户可以使用任意频道：当前、延期或首次发布延期频道。</span><span class="sxs-lookup"><span data-stu-id="db843-140">Customers can use any channel: Current, Deferred, or First Release Deferred.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="db843-141">如果你将客户端 VPN 解决方案与 Skype for Business 客户端结合使用，则只有 VPN 拆分隧道配置支持媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="db843-141">If you are using a client VPN solution in combination with the Skype for Business client, then media bypass is supported only with a VPN split-tunnel configuration.</span></span> 
  
<span data-ttu-id="db843-142">有关发布频道的详细信息，请参阅[Office 365 专业增强版更新频道概述](https://support.office.com/en-us/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="db843-142">For more information about the release channels, see [Overview of update channels for Office 365 ProPlus](https://support.office.com/en-us/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
<span data-ttu-id="db843-143">有关不同通道中的客户端的当前发行版本，请参阅[Office 365 专业增强版更新的发布信息](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)。</span><span class="sxs-lookup"><span data-stu-id="db843-143">For the current release version of the clients in different channels, see [Release information for updates to Office 365 ProPlus](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus).</span></span> 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a><span data-ttu-id="db843-144">使用媒体旁路功能时的云连接器容量注意事项</span><span class="sxs-lookup"><span data-stu-id="db843-144">Cloud Connector capacity considerations with media bypass</span></span>

<span data-ttu-id="db843-145">无需媒体绕过-根据硬件的不同，云连接器设备可以从50同时处理到500的同时通话，这需要媒体通过中介服务器旅行。</span><span class="sxs-lookup"><span data-stu-id="db843-145">Without media bypass—and depending on the hardware—a Cloud Connector appliance can handle from 50 to 500 simultaneous calls that require media to travel through a Mediation Server.</span></span> <span data-ttu-id="db843-146">有关详细信息，请参阅[规划 Skype for Business 云连接器版本](https://technet.microsoft.com/en-us/library/mt605227.aspx)。</span><span class="sxs-lookup"><span data-stu-id="db843-146">For more information, see [Plan for Skype for Business Cloud Connector Edition](https://technet.microsoft.com/en-us/library/mt605227.aspx).</span></span> 
  
<span data-ttu-id="db843-147">启用媒体旁路功能时，受支持版本的内部客户端不使用中介服务器，因此内部客户端数会显著增加。</span><span class="sxs-lookup"><span data-stu-id="db843-147">With media bypass enabled, internal clients on the supported version do not use the Mediation Server, so the number of internal clients can increase significantly.</span></span> 
  
<span data-ttu-id="db843-148">如上文所述，外部客户端或不支持的客户端将使用云连接线边缘和面向媒体的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="db843-148">As noted above, external clients or unsupported clients will use the Cloud Connector Edge and Mediation servers for media.</span></span> <span data-ttu-id="db843-149">计算网站中应放置多少个云连接器设备时，必须考虑来自外部用户和不受支持的客户端上的用户的流量。</span><span class="sxs-lookup"><span data-stu-id="db843-149">When calculating how many Cloud Connector appliances should be placed in a site, you must consider traffic from external users and users on unsupported clients.</span></span>
  
## <a name="cloud-connector-supports-always-bypass-mode"></a><span data-ttu-id="db843-150">云连接器支持“始终旁路”模式</span><span class="sxs-lookup"><span data-stu-id="db843-150">Cloud Connector supports Always Bypass mode</span></span>

<span data-ttu-id="db843-151">云连接器仅支持始终绕过模式。</span><span class="sxs-lookup"><span data-stu-id="db843-151">Cloud Connector supports Always Bypass mode only.</span></span> <span data-ttu-id="db843-152">在本地环境中，有两个选项：“始终旁路”和“使用站点和区域信息”。</span><span class="sxs-lookup"><span data-stu-id="db843-152">In on-premises environments, there are two options: Always Bypass and Use Site and Region Information.</span></span>
  
<span data-ttu-id="db843-p113">“始终旁路”意味着将对以内部客户端作为源或目标点的所有 PSTN 通话尝试媒体旁路功能。为确定客户端是内部客户端还是外部客户端，将使用中介服务器虚拟机上的网站。如果客户端可以访问该站点，则认为它是内部客户端，并将使用媒体旁路功能。如果客户端无法访问该站点（例如，客户端在家庭网络上），则不使用媒体旁路功能。</span><span class="sxs-lookup"><span data-stu-id="db843-p113">Always Bypass means that media bypass will be attempted for all PSTN calls with internal clients as an origin or destination point. To determine if the client is internal or external, a web site on the mediation server virtual machine is used. If the client can reach the site, it is considered internal and media bypass is used. If the client cannot reach the site (for example the client is on a home network), media bypass is not used.</span></span> 
  
<span data-ttu-id="db843-157">“始终旁路”要求用户与 PSTN 站点内的 PSTN 网关之间的连接畅通无阻。</span><span class="sxs-lookup"><span data-stu-id="db843-157">Always Bypass requires unobstructed connectivity between users and the PSTN gateways within a PSTN Site.</span></span> 
  
<span data-ttu-id="db843-158">有关详细信息，请参阅[规划 Skype for Business 云连接器版本](https://technet.microsoft.com/en-us/library/mt605227.aspx)。</span><span class="sxs-lookup"><span data-stu-id="db843-158">For more information, see [Plan for Skype for Business Cloud Connector Edition](https://technet.microsoft.com/en-us/library/mt605227.aspx).</span></span> 
  
<span data-ttu-id="db843-159">例如，在下图中，欧洲用户必须与三个讲座的边框控制器（SBCs）保持很好的联系，因为我们的西部用户必须与西雅图的两个 SBCs 保持很好的联系。</span><span class="sxs-lookup"><span data-stu-id="db843-159">For example, in the diagram below, Europe users must be well connected to the three Session Border Controllers (SBCs) in Amsterdam while US West users must be well connected to the two SBCs in Seattle.</span></span> <span data-ttu-id="db843-160">连接顺畅意味着它们与 SBC 或网关位于相同的网络站点中，或使用具有合适带宽的 WAN 链路。</span><span class="sxs-lookup"><span data-stu-id="db843-160">Well connected means that they are either located in the same network sites as the SBCs or gateways, or over WAN links that have proper bandwidth.</span></span>
  
![云连接器容量](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> <span data-ttu-id="db843-162">如果位于苏黎世的用户访问西雅图办公室，并且要使用内部网络在来访用户与欧洲网关之间发送媒体流量（而不是通过 Internet），则必须确保西雅图办公室与欧洲 SBC 或网关所在的阿姆斯特丹办公室之间连接顺畅。</span><span class="sxs-lookup"><span data-stu-id="db843-162">If a user from Zurich travels to the Seattle office, and you want to use the internal network to deliver media traffic between the traveling user and gateways in Europe (as opposed to going over the Internet), then you must make sure the Seattle office and the Amsterdam office where European SBCs or gateways are located qualify as well connected.</span></span> 
  
## <a name="codecs-used-in-media-bypass"></a><span data-ttu-id="db843-163">媒体旁路中使用的编解码器</span><span class="sxs-lookup"><span data-stu-id="db843-163">Codecs used in media bypass</span></span>

<span data-ttu-id="db843-164">启用媒体旁路功能后，客户端与 SBC 或网关之间的媒体流量将使用 G.711 编解码器。</span><span class="sxs-lookup"><span data-stu-id="db843-164">With media bypass enabled, media traffic between a client and an SBC or gateway uses the G.711 codec.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="db843-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db843-165">See also</span></span>

[<span data-ttu-id="db843-166">在云连接器版本中部署媒体旁路</span><span class="sxs-lookup"><span data-stu-id="db843-166">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md)
