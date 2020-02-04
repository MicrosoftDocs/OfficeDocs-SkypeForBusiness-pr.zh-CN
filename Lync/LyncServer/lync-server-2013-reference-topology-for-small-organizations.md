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
ms.openlocfilehash: 7e0171d9678d5d890cf4ecb81f6de25f9b558b05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a><span data-ttu-id="99b9a-102">小型组织中 Lync Server 2013 的参考拓扑</span><span class="sxs-lookup"><span data-stu-id="99b9a-102">Reference topology for Lync Server 2013 in small organizations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99b9a-103">_**主题上次修改时间：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="99b9a-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="99b9a-104">小型组织的参考拓扑显示如何通过仅部署三台运行 Lync Server 的服务器来部署强健、高可用性的解决方案。</span><span class="sxs-lookup"><span data-stu-id="99b9a-104">The reference topology for small organizations shows how you can deploy a robust, highly available solution by deploying only three servers running Lync Server.</span></span>

<span data-ttu-id="99b9a-105">**小型组织的参考拓扑**</span><span class="sxs-lookup"><span data-stu-id="99b9a-105">**Reference topology for small organizations**</span></span>

<span data-ttu-id="99b9a-106">![用于部署三台服务器的参考拓扑图示](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "用于部署三台服务器的参考拓扑图示")</span><span class="sxs-lookup"><span data-stu-id="99b9a-106">![Reference topology deploying three servers diagram](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Reference topology deploying three servers diagram")</span></span>

  - <span data-ttu-id="99b9a-107">**部署此组织的标准版服务器对**   其中心网站有4000用户。</span><span class="sxs-lookup"><span data-stu-id="99b9a-107">**Pair of Standard Edition Servers Deployed**    This organization has 4,000 users at their central site.</span></span> <span data-ttu-id="99b9a-108">组织部署了两个标准版服务器并将它们配对在一起以支持高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="99b9a-108">The organization has deployed two Standard Edition servers and paired them together to enable high availability and disaster recovery.</span></span> <span data-ttu-id="99b9a-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span><span class="sxs-lookup"><span data-stu-id="99b9a-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span></span> <span data-ttu-id="99b9a-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span><span class="sxs-lookup"><span data-stu-id="99b9a-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span></span> <span data-ttu-id="99b9a-111">有关 Lync Server 2013 中的高可用性和灾难恢复功能的详细信息，请参阅[Lync server 2013 中的 "规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)"。</span><span class="sxs-lookup"><span data-stu-id="99b9a-111">For more information about high availability and disaster recovery features in Lync Server 2013, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="99b9a-112">**建议使用边缘服务器部署。**   尽管内部即时消息、状态和会议不需要部署边缘服务器，但我们建议你在小型部署中使用。</span><span class="sxs-lookup"><span data-stu-id="99b9a-112">**Edge Server deployment is recommended.**   Although deploying an Edge Server is not required for internal IM, presence and conferencing, we recommend it even for small deployments.</span></span> <span data-ttu-id="99b9a-113">你可以通过部署边缘服务器来为当前组织防火墙外部的用户提供服务，从而最大化 Lync 服务器投资。</span><span class="sxs-lookup"><span data-stu-id="99b9a-113">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="99b9a-114">其优点包括：</span><span class="sxs-lookup"><span data-stu-id="99b9a-114">The benefits include the following:</span></span>
    
      - <span data-ttu-id="99b9a-115">如果您的组织的用户在家里工作或在路上工作，您的组织的用户可以使用 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="99b9a-115">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="99b9a-116">您的用户可以邀请外部用户参加会议。</span><span class="sxs-lookup"><span data-stu-id="99b9a-116">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="99b9a-117">如果您有一个也使用 Lync Server 的合作伙伴、供应商或客户组织，则可以与该组织建立*联盟关系*。</span><span class="sxs-lookup"><span data-stu-id="99b9a-117">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="99b9a-118">然后，您的 Lync 服务器部署将识别该联合组织的用户，从而更好地协作。</span><span class="sxs-lookup"><span data-stu-id="99b9a-118">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="99b9a-119">用户可以与公共 IM 服务的用户交换即时消息，包括以下任何或所有内容： Windows Live、AOL、Yahoo\!和 Google 通话。</span><span class="sxs-lookup"><span data-stu-id="99b9a-119">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="99b9a-120">对于使用这些服务的公共 IM 连接，可能需要单独的许可证。</span><span class="sxs-lookup"><span data-stu-id="99b9a-120">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="99b9a-121">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或续订协议。</span><span class="sxs-lookup"><span data-stu-id="99b9a-121">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="99b9a-122">具有活动许可证的客户将能够继续与 Yahoo！进行联盟</span><span class="sxs-lookup"><span data-stu-id="99b9a-122">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="99b9a-123">Messenger，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="99b9a-123">Messenger until the service shut down date.</span></span> <span data-ttu-id="99b9a-124">AOL 和 Yahoo！的有效期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="99b9a-124">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="99b9a-125">已宣布。</span><span class="sxs-lookup"><span data-stu-id="99b9a-125">has been announced.</span></span> <span data-ttu-id="99b9a-126">有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</span><span class="sxs-lookup"><span data-stu-id="99b9a-126">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="99b9a-127">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="99b9a-127">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="99b9a-128">Messenger.</span><span class="sxs-lookup"><span data-stu-id="99b9a-128">Messenger.</span></span> <span data-ttu-id="99b9a-129">Microsoft 提供此服务的能力已作为对 Yahoo！的支持，它的底层协议被向下缠绕。</span><span class="sxs-lookup"><span data-stu-id="99b9a-129">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="99b9a-130">Lync 比以往更多，是一种强大的工具，用于跨组织和全球各地的人员进行连接。</span><span class="sxs-lookup"><span data-stu-id="99b9a-130">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="99b9a-131">与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="99b9a-131">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="99b9a-132">Skype 联盟将添加到此列表，使 Lync 用户可以通过 IM 和语音与成百上千人联系。</span><span class="sxs-lookup"><span data-stu-id="99b9a-132">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="99b9a-133">**分支网站留存。**   此组织正在运行 Lync Server 的企业语音功能的试点计划。</span><span class="sxs-lookup"><span data-stu-id="99b9a-133">**Branch site survivability.**   This organization is running a pilot program of the Enterprise Voice feature of Lync Server.</span></span> <span data-ttu-id="99b9a-134">某些用户使用 Lync Server 作为其唯一的语音解决方案。</span><span class="sxs-lookup"><span data-stu-id="99b9a-134">Some users are using Lync Server as their sole voice solution.</span></span> <span data-ttu-id="99b9a-135">其中一些语音试点用户位于分支站点。</span><span class="sxs-lookup"><span data-stu-id="99b9a-135">Some of these Voice pilot users are located at the branch site.</span></span> <span data-ttu-id="99b9a-136">分支站点没有指向中心网站的可靠广域网（WAN）链接，因此 Survivable 分支装置将部署在此处。</span><span class="sxs-lookup"><span data-stu-id="99b9a-136">The branch site does not have a reliable wide area network (WAN) link to the central site, so a Survivable Branch Appliance is deployed there.</span></span> <span data-ttu-id="99b9a-137">这样一来，如果 WAN 链路出现故障，分支站点上的用户仍然可以发出和接收呼叫（组织内的呼叫和 PSTN 呼叫），继续使用语音邮件功能，并使用双方即时消息 (IM) 进行通信。</span><span class="sxs-lookup"><span data-stu-id="99b9a-137">With this deployed, if the WAN link goes down, users at the branch site can still make and receive calls (both calls within the organization and PSTN calls), have voice mail functionality, and communicate with two-party instant messaging (IM).</span></span> <span data-ttu-id="99b9a-138">当 WAN 链路不可用时，仍然能够对用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="99b9a-138">Users can also be authenticated when the WAN link is unavailable as well.</span></span>

  - <span data-ttu-id="99b9a-139">**Exchange UM 部署。**</span><span class="sxs-lookup"><span data-stu-id="99b9a-139">**Exchange UM deployment.**</span></span> <span data-ttu-id="99b9a-140">此参考拓扑包括一个 Exchange 统一消息（UM）服务器，该服务器运行 Microsoft Exchange Server，而不是 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="99b9a-140">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="99b9a-141">有关 Exchange UM 的详细信息，请参阅规划文档中的 lync [server 2013 中的 "规划 Exchange 统一消息集成](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)" 和 " [lync server 2013" 中的托管 exchange 统一消息集成](lync-server-2013-hosted-exchange-unified-messaging-integration.md)。</span><span class="sxs-lookup"><span data-stu-id="99b9a-141">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="99b9a-142">**Office Web Apps 服务器。**</span><span class="sxs-lookup"><span data-stu-id="99b9a-142">**Office Web Apps Server.**</span></span> <span data-ttu-id="99b9a-143">我们建议在每个使用 Web 会议的组织内部署一个 Office Web Apps 服务器或 Office Web Apps 服务器场。</span><span class="sxs-lookup"><span data-stu-id="99b9a-143">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="99b9a-144">Office Web Apps 服务器使 PowerPoint 幻灯片可以在 Web 会议中显示。</span><span class="sxs-lookup"><span data-stu-id="99b9a-144">Office Web Apps Server makes it possible for PowerPoint slides to be presented in web conferences.</span></span> <span data-ttu-id="99b9a-145">有关详细信息，请参阅[配置与 Office Web Apps server 和 Lync server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="99b9a-145">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

