---
title: 中型组织的 Lync Server 2013 参考拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for medium-size organizations
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425939(v=OCS.15)
ms:contentKeyID: 48184026
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da4c29107a6ca3d33e76708be9eec07297eeaf93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a><span data-ttu-id="98ec2-102">中型组织中的 Lync Server 2013 参考拓扑</span><span class="sxs-lookup"><span data-stu-id="98ec2-102">Reference topology for Lync Server 2013 in medium-size organizations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98ec2-103">_**主题上次修改时间：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="98ec2-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="98ec2-p101">具有高可用性和单个数据中心的参考拓扑是为具有一个中央站点的中小型组织设计的。下图中的具体拓扑用于拥有 20,000 个用户的组织。</span><span class="sxs-lookup"><span data-stu-id="98ec2-p101">The reference topology with high availability and a single data center is designed for a small-to-medium size organization with one central site. The exact topology in the following diagram is for an organization of 20,000 users.</span></span>

<span data-ttu-id="98ec2-106">**中型组织的参考拓扑**</span><span class="sxs-lookup"><span data-stu-id="98ec2-106">**Reference topology for medium organizations**</span></span>

<span data-ttu-id="98ec2-107">![用于单个数据中心的参考拓扑图示](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "用于单个数据中心的参考拓扑图示")</span><span class="sxs-lookup"><span data-stu-id="98ec2-107">![Reference topology for single data center diagram](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "Reference topology for single data center diagram")</span></span>

  - <span data-ttu-id="98ec2-108">**通过添加更多前端服务器来容纳更多用户。**   此图中的确切拓扑具有三个前端服务器，可提供对20000用户的支持。</span><span class="sxs-lookup"><span data-stu-id="98ec2-108">**Accommodate more users by adding more Front End Servers.**   The exact topology in this diagram has three Front End Servers to provide support for 20,000 users.</span></span> <span data-ttu-id="98ec2-109">如果具有一个中央站点和更多用户，则只需将更多前端服务器添加到池中。</span><span class="sxs-lookup"><span data-stu-id="98ec2-109">If you have a single central site and more users, you can simply add more Front End Servers to the pool.</span></span> <span data-ttu-id="98ec2-110">每个池最多可支持 80,000 个用户，可包含 12 台前端服务器。</span><span class="sxs-lookup"><span data-stu-id="98ec2-110">The maximum number of users per pool is 80,000, with twelve Front End Servers.</span></span>
    
    <span data-ttu-id="98ec2-111">但是，单站点拓扑可以通过向该站点添加另一个前端池来支持更多的用户。</span><span class="sxs-lookup"><span data-stu-id="98ec2-111">However, the single site topology can support even more users by adding another Front End pool to the site.</span></span>

  - <span data-ttu-id="98ec2-112">**可以添加灾难恢复。**   对于此组织，其 Lync Server 服务的高可用性是必需的功能，但灾难恢复不是。</span><span class="sxs-lookup"><span data-stu-id="98ec2-112">**Disaster Recovery could be added.**   For this organization, high availability for their Lync Server services is a necessary feature, but disaster recovery is not.</span></span> <span data-ttu-id="98ec2-113">其部署的前端服务器池可提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="98ec2-113">The pool of Front End Servers they have deployed provides high availability.</span></span>
    
    <span data-ttu-id="98ec2-p104">如果需要添加灾难恢复功能，可以考虑建立另一个数据中心并添加另一个前端池，同时将其当前数据中心内的前端池配对。之后，如果发生影响其主池的灾难，则管理员可以将用户故障转移到备份池。</span><span class="sxs-lookup"><span data-stu-id="98ec2-p104">If they wanted to add disaster recovery ability, they could consider establishing another datacenter and adding another Front End pool there, and pairing it with the Front End pool in their current datacenter. Then, if there was a disaster affecting their primary pool, the administrators could fail over users to the backup pool.</span></span>

  - <span data-ttu-id="98ec2-116">**对后端服务器进行镜像**   以提供基本用户功能的更高可用性，组织为每个前端池部署了镜像对后端服务器。</span><span class="sxs-lookup"><span data-stu-id="98ec2-116">**Back End Servers are mirrored**   To provide more high availability for basic user features, the organization has deployed a mirrored pair of Back End Servers for each Front End pool.</span></span> <span data-ttu-id="98ec2-117">这是 Lync Server 2013 的新拓扑选项，它是可选的。</span><span class="sxs-lookup"><span data-stu-id="98ec2-117">This is a new topology option for Lync Server 2013, and is optional.</span></span> <span data-ttu-id="98ec2-118">可以改为选择部署一台后端服务器。</span><span class="sxs-lookup"><span data-stu-id="98ec2-118">You could choose to deploy a single Back End Server instead.</span></span>

  - <span data-ttu-id="98ec2-119">**监视服务器数据库选项。**   此组织已部署监控，以确保企业语音通话质量和 A/V 会议的质量。</span><span class="sxs-lookup"><span data-stu-id="98ec2-119">**Monitoring Server database options.**   This organization has deployed Monitoring to ensure the quality of Enterprise Voice calls and A/V conferences.</span></span> <span data-ttu-id="98ec2-120">在每个前端服务器上部署监控，并且监控数据库将与后端服务器并置。</span><span class="sxs-lookup"><span data-stu-id="98ec2-120">Monitoring is deployed on every Front End Server, and the Monitoring database is collocated with the Back End Servers.</span></span> <span data-ttu-id="98ec2-121">我们还支持监控数据库在其中位于单独的服务器上的拓扑。</span><span class="sxs-lookup"><span data-stu-id="98ec2-121">We also support topologies in which the Monitoring database is located on a separate server.</span></span>

  - <span data-ttu-id="98ec2-122">**边缘服务器高可用性**    在此示例组织中，对于20000用户，只有一台边缘服务器才足够性能。</span><span class="sxs-lookup"><span data-stu-id="98ec2-122">**Edge Server high availability**    In this example organization with 20,000 users, just one Edge Server would be sufficient for performance.</span></span> <span data-ttu-id="98ec2-123">但是，部署了两个边缘服务器的池来提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="98ec2-123">However, there is a pool of two Edge Servers deployed to provide high availability.</span></span>

  - <span data-ttu-id="98ec2-124">**分支站点部署选项。**   此拓扑中的组织已将企业语音部署为其语音解决方案。</span><span class="sxs-lookup"><span data-stu-id="98ec2-124">**Branch site deployment options.**   The organization in this topology has Enterprise Voice deployed as their voice solution.</span></span> <span data-ttu-id="98ec2-125">分支站点1没有指向中心站点的复原广域网（WAN）链接，因此它具有一个 Survivable 分支设备，可用于维护许多 Lync 服务器功能，以防指向中央站点的 WAN 链接断开。</span><span class="sxs-lookup"><span data-stu-id="98ec2-125">Branch Site 1 does not have a resilient wide area network (WAN) link to the central site, so it has a Survivable Branch Appliance deployed to maintain many Lync Server features in case the WAN link to the central site goes down.</span></span> <span data-ttu-id="98ec2-126">但是，分支站点 2 具有可恢复 WAN 链路，因此只需一个公用电话交换网 (PSTN) 网关。</span><span class="sxs-lookup"><span data-stu-id="98ec2-126">Branch Site 2 however has a resilient WAN link, so only a public switched telephone network (PSTN) gateway is needed.</span></span> <span data-ttu-id="98ec2-127">该处部署的 PSTN 网关支持媒体旁路，因此分支站点 2 上不需要中介服务器。</span><span class="sxs-lookup"><span data-stu-id="98ec2-127">The PSTN gateway deployed there supports media bypass, so no Mediation Server is needed at Branch Site 2.</span></span> <span data-ttu-id="98ec2-128">有关决定在分支站点部署哪些内容的详细信息，请参阅规划文档中的[在 Lync Server 2013 中规划分支站点语音复原](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。</span><span class="sxs-lookup"><span data-stu-id="98ec2-128">For details about deciding what to deploy at a branch site, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="98ec2-129">**DNS 负载平衡。**   前端池 andEdge 服务器池已部署 SIP 流量的 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="98ec2-129">**DNS load balancing.**   The Front End pool andEdge Server pool, have DNS load balancing for SIP traffic deployed.</span></span> <span data-ttu-id="98ec2-130">这样就无需为边缘服务器部署硬件负载平衡器，并可以显著减少为其他池设置和维护硬件负载平衡器的工作量，因为只有 HTTP 流量需要使用硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="98ec2-130">This eliminates the need for hardware load balancers for the Edge Servers, and significantly lessens the setup and maintenance of the hardware load balancers for the other pools, as the hardware load balancers are needed only for HTTP traffic.</span></span> <span data-ttu-id="98ec2-131">有关 DNS 负载平衡的详细信息，请参阅规划文档中[Lync Server 2013 中的 "DNS 负载平衡](lync-server-2013-dns-load-balancing.md)"。</span><span class="sxs-lookup"><span data-stu-id="98ec2-131">For details about DNS load balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="98ec2-132">**Exchange UM 部署。**</span><span class="sxs-lookup"><span data-stu-id="98ec2-132">**Exchange UM deployment.**</span></span> <span data-ttu-id="98ec2-133">此参考拓扑包括一个 Exchange 统一消息（UM）服务器，该服务器运行 Microsoft Exchange Server，而不是 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="98ec2-133">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="98ec2-134">有关 Exchange UM 的详细信息，请参阅规划文档中的 lync [server 2013 中的 "规划 Exchange 统一消息集成](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)" 和 " [lync server 2013" 中的托管 exchange 统一消息集成](lync-server-2013-hosted-exchange-unified-messaging-integration.md)。</span><span class="sxs-lookup"><span data-stu-id="98ec2-134">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="98ec2-135">**Office Web Apps 服务器。**</span><span class="sxs-lookup"><span data-stu-id="98ec2-135">**Office Web Apps Server.**</span></span> <span data-ttu-id="98ec2-136">我们建议在每个使用 Web 会议的组织内部署一个 Office Web Apps 服务器或 Office Web Apps 服务器场。</span><span class="sxs-lookup"><span data-stu-id="98ec2-136">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="98ec2-137">利用 Office Web Apps 服务器，可以在 Web 会议中演示 PowerPoint 幻灯片。</span><span class="sxs-lookup"><span data-stu-id="98ec2-137">Office Web Apps Server makes it possible for Powerpoint slides to be presented in web conferences.</span></span> <span data-ttu-id="98ec2-138">有关详细信息，请参阅[配置与 Office Web Apps server 和 Lync server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="98ec2-138">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="98ec2-139">**推荐使用边缘服务器。**   虽然不需要部署边缘服务器，但我们建议在任何规模的部署中使用。</span><span class="sxs-lookup"><span data-stu-id="98ec2-139">**Edge Servers are recommended.**   Although deploying an Edge Server is not required, we recommend it for any size of deployment.</span></span> <span data-ttu-id="98ec2-140">你可以通过部署边缘服务器来为当前组织防火墙外部的用户提供服务，从而最大化 Lync 服务器投资。</span><span class="sxs-lookup"><span data-stu-id="98ec2-140">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="98ec2-141">其优点包括：</span><span class="sxs-lookup"><span data-stu-id="98ec2-141">The benefits include the following:</span></span>
    
      - <span data-ttu-id="98ec2-142">如果您的组织的用户在家里工作或在路上工作，您的组织的用户可以使用 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="98ec2-142">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="98ec2-143">您的用户可以邀请外部用户参加会议。</span><span class="sxs-lookup"><span data-stu-id="98ec2-143">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="98ec2-144">如果您有一个也使用 Lync Server 的合作伙伴、供应商或客户组织，则可以与该组织建立*联盟关系*。</span><span class="sxs-lookup"><span data-stu-id="98ec2-144">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="98ec2-145">然后，您的 Lync 服务器部署将识别该联合组织的用户，从而更好地协作。</span><span class="sxs-lookup"><span data-stu-id="98ec2-145">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="98ec2-146">用户可以与公共 IM 服务的用户交换即时消息，包括以下任何或所有内容： Windows Live、AOL、Yahoo\!和 Google 通话。</span><span class="sxs-lookup"><span data-stu-id="98ec2-146">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="98ec2-147">对于使用这些服务的公共 IM 连接，可能需要单独的许可证。</span><span class="sxs-lookup"><span data-stu-id="98ec2-147">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="98ec2-148">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或续订协议。</span><span class="sxs-lookup"><span data-stu-id="98ec2-148">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="98ec2-149">具有活动许可证的客户将能够继续与 Yahoo！进行联盟</span><span class="sxs-lookup"><span data-stu-id="98ec2-149">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="98ec2-150">Messenger，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="98ec2-150">Messenger until the service shut down date.</span></span> <span data-ttu-id="98ec2-151">AOL 和 Yahoo！的有效期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="98ec2-151">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="98ec2-152">已宣布。</span><span class="sxs-lookup"><span data-stu-id="98ec2-152">has been announced.</span></span> <span data-ttu-id="98ec2-153">有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</span><span class="sxs-lookup"><span data-stu-id="98ec2-153">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="98ec2-154">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="98ec2-154">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="98ec2-155">Messenger.</span><span class="sxs-lookup"><span data-stu-id="98ec2-155">Messenger.</span></span> <span data-ttu-id="98ec2-156">Microsoft 提供此服务的能力已作为对 Yahoo！的支持，它的底层协议被向下缠绕。</span><span class="sxs-lookup"><span data-stu-id="98ec2-156">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="98ec2-157">Lync 比以往更多，是一种强大的工具，用于跨组织和全球各地的人员进行连接。</span><span class="sxs-lookup"><span data-stu-id="98ec2-157">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="98ec2-158">与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="98ec2-158">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="98ec2-159">Skype 联盟将添加到此列表，使 Lync 用户可以通过 IM 和语音与成百上千人联系。</span><span class="sxs-lookup"><span data-stu-id="98ec2-159">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="98ec2-160">**可以添加董事。**   如果此组织希望帮助增强安全以防拒绝服务攻击，它还可以部署一个控制器池。</span><span class="sxs-lookup"><span data-stu-id="98ec2-160">**Directors could be added.**   If this organization wanted to help to increase security against denial of service attacks, it could also deploy a pool of Directors.</span></span> <span data-ttu-id="98ec2-161">Director 是 Lync Server 中的一种独立的可选服务器角色，它不会家庭用户帐户，也不能提供状态或会议服务。</span><span class="sxs-lookup"><span data-stu-id="98ec2-161">A Director is a separate, optional server role in Lync Server that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="98ec2-162">它充当一个内部下一个跃点服务器，边缘服务器将入站 SIP 流量路由到内部服务器。</span><span class="sxs-lookup"><span data-stu-id="98ec2-162">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="98ec2-163">控制器对入站请求进行预身份验证，并将其重定向到用户的主池或服务器。</span><span class="sxs-lookup"><span data-stu-id="98ec2-163">The Director pre-authenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="98ec2-164">控制器进行的预先身份验证允许放弃来自部署中未知的用户帐户的请求。</span><span class="sxs-lookup"><span data-stu-id="98ec2-164">Pre-authentication at the Director allows for dropping of requests from user accounts unknown to the deployment.</span></span> <span data-ttu-id="98ec2-165">控制器可帮助将前端服务器与恶意流量（如拒绝服务（DoS）攻击）隔离。</span><span class="sxs-lookup"><span data-stu-id="98ec2-165">A Director helps insulate Front End Servers from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="98ec2-166">如果网络被此类攻击中的无效外部通信所淹没，则流量将在 Director 处结束。</span><span class="sxs-lookup"><span data-stu-id="98ec2-166">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span>

  - <span data-ttu-id="98ec2-167">**建议使用 System Center Operations Manager。**  我们建议你监视 Lync Server 部署的运行状况，以帮助确保最终用户的服务可用性。</span><span class="sxs-lookup"><span data-stu-id="98ec2-167">**System Center Operations Manager is recommended.**  We recommend that you monitor the health of your Lync Server deployment to help ensure service availability for end-users.</span></span> <span data-ttu-id="98ec2-168">你可以使用适用于 Microsoft 的免费下载，通过适用于 Lync 的 System Center Operations Manager 管理包监控 Lync。</span><span class="sxs-lookup"><span data-stu-id="98ec2-168">You can monitor Lync with the System Center Operations Manager Management Pack for Lync that is available as a free download from Microsoft.</span></span> <span data-ttu-id="98ec2-169">使用 Lync 管理包，你可以在出现问题时主动获得实时警报，运行合成事务以测试端到端 Lync 功能，获取有关服务可用性的报告等。</span><span class="sxs-lookup"><span data-stu-id="98ec2-169">With the Lync Management Pack, you can proactively get real-time alerts when issues occur, run synthetic transactions to test end-to-end Lync functionality, get reports for service availability, and so on.</span></span> <span data-ttu-id="98ec2-170">This helps you to proactively respond to issues with your deployment before end-users experience them.</span><span class="sxs-lookup"><span data-stu-id="98ec2-170"> This helps you to proactively respond to issues with your deployment before end-users experience them.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

