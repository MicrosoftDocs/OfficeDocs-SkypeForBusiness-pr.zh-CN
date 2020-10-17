---
title: Lync Server 2013 针对中型组织的参考拓扑
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
ms.openlocfilehash: b2549acbf8b5eac2ac909eb213d6d73e8233b0a2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536699"
---
# <a name="reference-topology-for-lync-server-2013-in-medium-size-organizations"></a><span data-ttu-id="0bc9e-102">中型组织中 Lync Server 2013 的参考拓扑</span><span class="sxs-lookup"><span data-stu-id="0bc9e-102">Reference topology for Lync Server 2013 in medium-size organizations</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bc9e-103">_**上次修改的主题：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="0bc9e-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="0bc9e-104">具有高可用性和单个数据中心的参考拓扑是为具有一个中央站点的中小型组织设计的。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-104">The reference topology with high availability and a single data center is designed for a small-to-medium size organization with one central site.</span></span> <span data-ttu-id="0bc9e-105">下图中的具体拓扑适用于20000用户的组织。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-105">The exact topology in the following diagram is for an organization of 20,000 users.</span></span>

<span data-ttu-id="0bc9e-106">**中型组织的参考拓扑**</span><span class="sxs-lookup"><span data-stu-id="0bc9e-106">**Reference topology for medium organizations**</span></span>

<span data-ttu-id="0bc9e-107">![单一数据中心图表的参考拓扑](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "单一数据中心图表的参考拓扑")</span><span class="sxs-lookup"><span data-stu-id="0bc9e-107">![Reference topology for single data center diagram](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "Reference topology for single data center diagram")</span></span>

  - <span data-ttu-id="0bc9e-108">**通过添加更多前端服务器来容纳更多用户。**    此图中的具体拓扑包含三台前端服务器，以支持20000用户。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-108">**Accommodate more users by adding more Front End Servers.**   The exact topology in this diagram has three Front End Servers to provide support for 20,000 users.</span></span> <span data-ttu-id="0bc9e-109">如果您有一个中央站点和更多用户，则只需向池中添加更多的前端服务器即可。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-109">If you have a single central site and more users, you can simply add more Front End Servers to the pool.</span></span> <span data-ttu-id="0bc9e-110">每个池的最大用户数为80000，使用12台前端服务器。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-110">The maximum number of users per pool is 80,000, with twelve Front End Servers.</span></span>
    
    <span data-ttu-id="0bc9e-111">但是，单站点拓扑可以通过向该站点添加另一个前端池来支持更多的用户。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-111">However, the single site topology can support even more users by adding another Front End pool to the site.</span></span>

  - <span data-ttu-id="0bc9e-112">**可以添加灾难恢复。**    对于此组织，其 Lync Server 服务的高可用性是必需的功能，但不需要进行灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-112">**Disaster Recovery could be added.**   For this organization, high availability for their Lync Server services is a necessary feature, but disaster recovery is not.</span></span> <span data-ttu-id="0bc9e-113">他们已部署的前端服务器池可提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-113">The pool of Front End Servers they have deployed provides high availability.</span></span>
    
    <span data-ttu-id="0bc9e-114">如果他们想要添加灾难恢复能力，他们可以考虑建立另一个数据中心并在其中添加另一个前端池，并将其与当前数据中心中的前端池配对。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-114">If they wanted to add disaster recovery ability, they could consider establishing another datacenter and adding another Front End pool there, and pairing it with the Front End pool in their current datacenter.</span></span> <span data-ttu-id="0bc9e-115">然后，如果存在影响其主池的灾难，则管理员可以将用户故障转移到备份池。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-115">Then, if there was a disaster affecting their primary pool, the administrators could fail over users to the backup pool.</span></span>

  - <span data-ttu-id="0bc9e-116">**对后端服务器进行镜像**    为为基本用户功能提供更高的可用性，组织已为每个前端池部署了一个镜像对后端服务器。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-116">**Back End Servers are mirrored**   To provide more high availability for basic user features, the organization has deployed a mirrored pair of Back End Servers for each Front End pool.</span></span> <span data-ttu-id="0bc9e-117">这是 Lync Server 2013 的新拓扑选项，它是可选的。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-117">This is a new topology option for Lync Server 2013, and is optional.</span></span> <span data-ttu-id="0bc9e-118">您可以选择部署一台后端服务器。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-118">You could choose to deploy a single Back End Server instead.</span></span>

  - <span data-ttu-id="0bc9e-119">**监视服务器数据库选项。**    此组织已部署监控，以确保企业语音呼叫和 A/V 会议的质量。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-119">**Monitoring Server database options.**   This organization has deployed Monitoring to ensure the quality of Enterprise Voice calls and A/V conferences.</span></span> <span data-ttu-id="0bc9e-120">监视部署在每台前端服务器上，监视数据库与后端服务器并置。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-120">Monitoring is deployed on every Front End Server, and the Monitoring database is collocated with the Back End Servers.</span></span> <span data-ttu-id="0bc9e-121">此外，我们还支持监视数据库位于单独服务器上的拓扑。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-121">We also support topologies in which the Monitoring database is located on a separate server.</span></span>

  - <span data-ttu-id="0bc9e-122">**边缘服务器高可用性**    在此示例中，有20000个用户的组织，只要一台边缘服务器的性能就足够了。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-122">**Edge Server high availability**    In this example organization with 20,000 users, just one Edge Server would be sufficient for performance.</span></span> <span data-ttu-id="0bc9e-123">但是，部署了两台边缘服务器的池以提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-123">However, there is a pool of two Edge Servers deployed to provide high availability.</span></span>

  - <span data-ttu-id="0bc9e-124">**分支站点部署选项。**    此拓扑中的组织已将企业语音部署为其语音解决方案。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-124">**Branch site deployment options.**   The organization in this topology has Enterprise Voice deployed as their voice solution.</span></span> <span data-ttu-id="0bc9e-125">分支站点1没有可 (WAN) 链接到中央站点的弹性广域网络，因此它部署了一个 Survivable 分支设备来维护许多 Lync Server 功能，以防指向中央站点的 WAN 链接断开。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-125">Branch Site 1 does not have a resilient wide area network (WAN) link to the central site, so it has a Survivable Branch Appliance deployed to maintain many Lync Server features in case the WAN link to the central site goes down.</span></span> <span data-ttu-id="0bc9e-126">但是，分支站点 2 具有可恢复 WAN 链接，因此只需一个公用电话交换网 (PSTN) 网关。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-126">Branch Site 2 however has a resilient WAN link, so only a public switched telephone network (PSTN) gateway is needed.</span></span> <span data-ttu-id="0bc9e-127">该处部署的 PSTN 网关支持媒体绕过，因此分支站点 2 上不需要中介服务器。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-127">The PSTN gateway deployed there supports media bypass, so no Mediation Server is needed at Branch Site 2.</span></span> <span data-ttu-id="0bc9e-128">有关决定在分支站点部署的内容的详细信息，请参阅规划文档中的在 [Lync Server 2013 中规划分支站点语音恢复](lync-server-2013-planning-for-branch-site-voice-resiliency.md) 。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-128">For details about deciding what to deploy at a branch site, see [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="0bc9e-129">**DNS 负载平衡。**    前端池 andEdge 服务器池具有部署的 SIP 流量的 DNS 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-129">**DNS load balancing.**   The Front End pool andEdge Server pool, have DNS load balancing for SIP traffic deployed.</span></span> <span data-ttu-id="0bc9e-130">这样就无需为边缘服务器部署硬件负载平衡器，并可以显著减少为其他池设置和维护硬件负载平衡器的工作量，因为只有 HTTP 流量需要使用硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-130">This eliminates the need for hardware load balancers for the Edge Servers, and significantly lessens the setup and maintenance of the hardware load balancers for the other pools, as the hardware load balancers are needed only for HTTP traffic.</span></span> <span data-ttu-id="0bc9e-131">有关 DNS 负载平衡的详细信息，请参阅规划文档中的 [Lync Server 2013 中的 DNS 负载平衡](lync-server-2013-dns-load-balancing.md) 。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-131">For details about DNS load balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="0bc9e-132">**Exchange UM 部署。**</span><span class="sxs-lookup"><span data-stu-id="0bc9e-132">**Exchange UM deployment.**</span></span> <span data-ttu-id="0bc9e-133">此参考拓扑包括 Exchange 统一消息 (UM) 服务器，该服务器运行 Microsoft Exchange Server，而不是 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-133">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="0bc9e-134">有关 Exchange UM 的详细信息，请参阅规划文档中的在 lync server [2013 中规划 Exchange 统一消息集成](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 和 [lync server 2013 中的托管 exchange 统一消息集成](lync-server-2013-hosted-exchange-unified-messaging-integration.md) 。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-134">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="0bc9e-135">**Office Web Apps 服务器。**</span><span class="sxs-lookup"><span data-stu-id="0bc9e-135">**Office Web Apps Server.**</span></span> <span data-ttu-id="0bc9e-136">我们建议在每个使用 Web 会议的组织内部署一个 Office Web Apps 服务器或 Office Web Apps 服务器场。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-136">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="0bc9e-137">利用 Office Web Apps 服务器，可以在 Web 会议中演示 Powerpoint 幻灯片。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-137">Office Web Apps Server makes it possible for Powerpoint slides to be presented in web conferences.</span></span> <span data-ttu-id="0bc9e-138">有关详细信息，请参阅 [配置与 Office Web Apps Server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-138">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

  - <span data-ttu-id="0bc9e-139">**建议使用边缘服务器。**    尽管不需要部署边缘服务器，但我们建议将其用于任意规模的部署。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-139">**Edge Servers are recommended.**   Although deploying an Edge Server is not required, we recommend it for any size of deployment.</span></span> <span data-ttu-id="0bc9e-140">您可以部署边缘服务器以向当前组织防火墙外部的用户提供服务，从而最大化 Lync Server 投资。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-140">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="0bc9e-141">优势包括：</span><span class="sxs-lookup"><span data-stu-id="0bc9e-141">The benefits include the following:</span></span>
    
      - <span data-ttu-id="0bc9e-142">如果您的组织的用户在家中或在路上工作，则您的组织自己的用户可以使用 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-142">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="0bc9e-143">您的用户可以邀请外部用户参加会议。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-143">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="0bc9e-144">如果您有一个也使用 Lync Server 的合作伙伴、供应商或客户组织，则可以与该组织建立 *联合关系* 。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-144">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="0bc9e-145">然后，你的 Lync Server 部署将识别来自该联合组织的用户，从而实现更好的协作。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-145">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="0bc9e-146">您的用户可以与公共 IM 服务的用户交换即时消息，包括以下任一或所有内容： Windows Live、AOL、Yahoo \! 和 Google 谈话。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-146">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="0bc9e-147">对于使用这些服务的公共 IM 连接，可能需要单独的许可证。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-147">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="0bc9e-148">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证 ( "PIC USL" ) 不再可用于购买新的或更新的协议。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-148">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="0bc9e-149">拥有主动许可证的客户将能够继续与 Yahoo！联合联合</span><span class="sxs-lookup"><span data-stu-id="0bc9e-149">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="0bc9e-150">信使，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-150">Messenger until the service shut down date.</span></span> <span data-ttu-id="0bc9e-151">AOL 和 Yahoo！的生命周期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="0bc9e-151">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="0bc9e-152">已宣布。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-152">has been announced.</span></span> <span data-ttu-id="0bc9e-153">有关详细信息，请参阅 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-153">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="0bc9e-154">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-154">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="0bc9e-155">Messenger.</span><span class="sxs-lookup"><span data-stu-id="0bc9e-155">Messenger.</span></span> <span data-ttu-id="0bc9e-156">Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-156">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="0bc9e-157">Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-157">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="0bc9e-158">与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-158">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="0bc9e-159">Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-159">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="0bc9e-160">可**添加控制器。**    如果此组织希望帮助提高抵御拒绝服务攻击的安全性，它还可以部署一个控制器池。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-160">**Directors could be added.**   If this organization wanted to help to increase security against denial of service attacks, it could also deploy a pool of Directors.</span></span> <span data-ttu-id="0bc9e-161">Director 是 Lync Server 中的一个单独的可选服务器角色，它不会家庭用户帐户，也不提供状态或会议服务。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-161">A Director is a separate, optional server role in Lync Server that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="0bc9e-162">它充当内部下一个跃点服务器，边缘服务器将入站 SIP 流量路由到内部服务器。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-162">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="0bc9e-163">控制器对入站请求进行预身份验证，并将其重定向到用户的主池或服务器。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-163">The Director pre-authenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="0bc9e-164">控制器进行的预先身份验证允许放弃来自部署中未知的用户帐户的请求。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-164">Pre-authentication at the Director allows for dropping of requests from user accounts unknown to the deployment.</span></span> <span data-ttu-id="0bc9e-165">控制器可帮助将前端服务器与恶意流量（如拒绝服务 (DoS) 攻击）隔离。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-165">A Director helps insulate Front End Servers from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="0bc9e-166">如果网络在此类攻击中遇到无效的外部通信，则流量将在 Director 处结束。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-166">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span>

  - <span data-ttu-id="0bc9e-167">**建议使用 System Center Operations Manager。**   建议您监视 Lync Server 部署的运行状况，以帮助确保最终用户的服务可用性。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-167">**System Center Operations Manager is recommended.**  We recommend that you monitor the health of your Lync Server deployment to help ensure service availability for end-users.</span></span> <span data-ttu-id="0bc9e-168">您可以使用可从 Microsoft 免费下载的 Lync 的 System Center Operations Manager 管理包监视 Lync。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-168">You can monitor Lync with the System Center Operations Manager Management Pack for Lync that is available as a free download from Microsoft.</span></span> <span data-ttu-id="0bc9e-169">使用 Lync 管理包，您可在问题出现时主动获取实时警报、运行综合事务测试端到端的 Lync 功能以及获取服务可用性的报告等。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-169">With the Lync Management Pack, you can proactively get real-time alerts when issues occur, run synthetic transactions to test end-to-end Lync functionality, get reports for service availability, and so on.</span></span> <span data-ttu-id="0bc9e-170">这有助于您在最终用户遇到部署相关问题之前主动响应这些问题。</span><span class="sxs-lookup"><span data-stu-id="0bc9e-170"> This helps you to proactively respond to issues with your deployment before end-users experience them.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

