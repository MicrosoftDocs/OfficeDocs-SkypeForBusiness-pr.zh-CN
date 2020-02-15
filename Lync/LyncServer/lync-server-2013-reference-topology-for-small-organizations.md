---
title: 适用于小型组织的 Lync Server 2013 参考拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f4c9d99e95dea0edd0b5990b0bb198dfe59dc61
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a><span data-ttu-id="7c06c-102">小型组织中 Lync Server 2013 的参考拓扑</span><span class="sxs-lookup"><span data-stu-id="7c06c-102">Reference topology for Lync Server 2013 in small organizations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c06c-103">_**上次修改的主题：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="7c06c-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="7c06c-104">小型组织的参考拓扑显示了如何通过仅部署运行 Lync Server 的三台服务器来部署强健、高可用性的解决方案。</span><span class="sxs-lookup"><span data-stu-id="7c06c-104">The reference topology for small organizations shows how you can deploy a robust, highly available solution by deploying only three servers running Lync Server.</span></span>

<span data-ttu-id="7c06c-105">**小型组织的参考拓扑**</span><span class="sxs-lookup"><span data-stu-id="7c06c-105">**Reference topology for small organizations**</span></span>

<span data-ttu-id="7c06c-106">![部署三个服务器关系图的引用拓扑](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "部署三个服务器关系图的引用拓扑")</span><span class="sxs-lookup"><span data-stu-id="7c06c-106">![Reference topology deploying three servers diagram](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Reference topology deploying three servers diagram")</span></span>

  - <span data-ttu-id="7c06c-107">**部署此组织的一对标准版服务器**   在其中央站点有4000个用户。</span><span class="sxs-lookup"><span data-stu-id="7c06c-107">**Pair of Standard Edition Servers Deployed**    This organization has 4,000 users at their central site.</span></span> <span data-ttu-id="7c06c-108">组织已部署两个 Standard Edition 服务器并将它们配对在一起，以实现高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="7c06c-108">The organization has deployed two Standard Edition servers and paired them together to enable high availability and disaster recovery.</span></span> <span data-ttu-id="7c06c-109">每台服务器住宅2000用户，但在两台服务器之间同步所有用户的相关信息。</span><span class="sxs-lookup"><span data-stu-id="7c06c-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span></span> <span data-ttu-id="7c06c-110">如果一台服务器出现故障，管理员可以将这些用户故障转移到其他服务器，并至少对用户造成中断。</span><span class="sxs-lookup"><span data-stu-id="7c06c-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span></span> <span data-ttu-id="7c06c-111">有关 Lync Server 2013 中的高可用性和灾难恢复功能的详细信息，请参阅[在 Lync server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="7c06c-111">For more information about high availability and disaster recovery features in Lync Server 2013, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="7c06c-112">**建议使用边缘服务器部署。**   尽管内部 IM、状态和会议不需要部署边缘服务器，但我们建议您在小型部署中进行部署。</span><span class="sxs-lookup"><span data-stu-id="7c06c-112">**Edge Server deployment is recommended.**   Although deploying an Edge Server is not required for internal IM, presence and conferencing, we recommend it even for small deployments.</span></span> <span data-ttu-id="7c06c-113">您可以部署边缘服务器以向当前组织防火墙外部的用户提供服务，从而最大化 Lync Server 投资。</span><span class="sxs-lookup"><span data-stu-id="7c06c-113">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="7c06c-114">优势包括：</span><span class="sxs-lookup"><span data-stu-id="7c06c-114">The benefits include the following:</span></span>
    
      - <span data-ttu-id="7c06c-115">如果您的组织的用户在家中或在路上工作，则您的组织自己的用户可以使用 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="7c06c-115">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="7c06c-116">您的用户可以邀请外部用户参加会议。</span><span class="sxs-lookup"><span data-stu-id="7c06c-116">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="7c06c-117">如果您有一个也使用 Lync Server 的合作伙伴、供应商或客户组织，则可以与该组织建立*联合关系*。</span><span class="sxs-lookup"><span data-stu-id="7c06c-117">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="7c06c-118">然后，你的 Lync Server 部署将识别来自该联合组织的用户，从而实现更好的协作。</span><span class="sxs-lookup"><span data-stu-id="7c06c-118">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="7c06c-119">您的用户可以与公共 IM 服务的用户交换即时消息，包括以下任一或所有内容： Windows Live、AOL、Yahoo\!和 Google 谈话。</span><span class="sxs-lookup"><span data-stu-id="7c06c-119">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="7c06c-120">对于使用这些服务的公共 IM 连接，可能需要单独的许可证。</span><span class="sxs-lookup"><span data-stu-id="7c06c-120">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="7c06c-121">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或更新的协议。</span><span class="sxs-lookup"><span data-stu-id="7c06c-121">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="7c06c-122">拥有主动许可证的客户将能够继续与 Yahoo！联合联合</span><span class="sxs-lookup"><span data-stu-id="7c06c-122">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="7c06c-123">信使，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="7c06c-123">Messenger until the service shut down date.</span></span> <span data-ttu-id="7c06c-124">AOL 和 Yahoo！的生命周期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="7c06c-124">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="7c06c-125">已宣布。</span><span class="sxs-lookup"><span data-stu-id="7c06c-125">has been announced.</span></span> <span data-ttu-id="7c06c-126">有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</span><span class="sxs-lookup"><span data-stu-id="7c06c-126">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="7c06c-127">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="7c06c-127">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="7c06c-128">Messenger.</span><span class="sxs-lookup"><span data-stu-id="7c06c-128">Messenger.</span></span> <span data-ttu-id="7c06c-129">Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</span><span class="sxs-lookup"><span data-stu-id="7c06c-129">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="7c06c-130">Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。</span><span class="sxs-lookup"><span data-stu-id="7c06c-130">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="7c06c-131">与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="7c06c-131">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="7c06c-132">Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</span><span class="sxs-lookup"><span data-stu-id="7c06c-132">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="7c06c-133">**分支站点的留存能力。**   此组织正在运行 Lync Server 的企业语音功能的试点计划。</span><span class="sxs-lookup"><span data-stu-id="7c06c-133">**Branch site survivability.**   This organization is running a pilot program of the Enterprise Voice feature of Lync Server.</span></span> <span data-ttu-id="7c06c-134">某些用户使用 Lync Server 作为其唯一的语音解决方案。</span><span class="sxs-lookup"><span data-stu-id="7c06c-134">Some users are using Lync Server as their sole voice solution.</span></span> <span data-ttu-id="7c06c-135">其中一些语音试点用户位于分支站点。</span><span class="sxs-lookup"><span data-stu-id="7c06c-135">Some of these Voice pilot users are located at the branch site.</span></span> <span data-ttu-id="7c06c-136">分支站点没有到中央站点的可靠广域网（WAN）链接，因此在此部署了 Survivable 分支设备。</span><span class="sxs-lookup"><span data-stu-id="7c06c-136">The branch site does not have a reliable wide area network (WAN) link to the central site, so a Survivable Branch Appliance is deployed there.</span></span> <span data-ttu-id="7c06c-137">在部署此功能的情况下，如果 WAN 链接断开，分支站点的用户仍可以拨打和接听呼叫（组织中的呼叫和 PSTN 呼叫），具有语音邮件功能，并与两方即时消息（IM）进行通信。</span><span class="sxs-lookup"><span data-stu-id="7c06c-137">With this deployed, if the WAN link goes down, users at the branch site can still make and receive calls (both calls within the organization and PSTN calls), have voice mail functionality, and communicate with two-party instant messaging (IM).</span></span> <span data-ttu-id="7c06c-138">此外，在 WAN 链接不可用时，也可以对用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="7c06c-138">Users can also be authenticated when the WAN link is unavailable as well.</span></span>

  - <span data-ttu-id="7c06c-139">**Exchange UM 部署。**</span><span class="sxs-lookup"><span data-stu-id="7c06c-139">**Exchange UM deployment.**</span></span> <span data-ttu-id="7c06c-140">此参考拓扑包括一个 Exchange 统一消息（UM）服务器，该服务器运行 Microsoft Exchange Server，而不是 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="7c06c-140">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="7c06c-141">有关 Exchange UM 的详细信息，请参阅规划文档中的在 lync server [2013 中规划 Exchange 统一消息集成](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)和[lync server 2013 中的托管 exchange 统一消息集成](lync-server-2013-hosted-exchange-unified-messaging-integration.md)。</span><span class="sxs-lookup"><span data-stu-id="7c06c-141">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="7c06c-142">**Office Web Apps 服务器。**</span><span class="sxs-lookup"><span data-stu-id="7c06c-142">**Office Web Apps Server.**</span></span> <span data-ttu-id="7c06c-143">我们建议在每个使用 Web 会议的组织内部署一个 Office Web Apps 服务器或 Office Web Apps 服务器场。</span><span class="sxs-lookup"><span data-stu-id="7c06c-143">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="7c06c-144">Office Web Apps Server 使 PowerPoint 幻灯片可以显示在 Web 会议中。</span><span class="sxs-lookup"><span data-stu-id="7c06c-144">Office Web Apps Server makes it possible for PowerPoint slides to be presented in web conferences.</span></span> <span data-ttu-id="7c06c-145">有关详细信息，请参阅[配置与 Office Web Apps Server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="7c06c-145">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

