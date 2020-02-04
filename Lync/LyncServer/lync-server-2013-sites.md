---
title: Lync Server 2013 网站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2e5dc3323ad14f02a5b24258878512707f66f19
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a><span data-ttu-id="cdc77-102">Lync Server 2013 的 Lync Server 网站</span><span class="sxs-lookup"><span data-stu-id="cdc77-102">Lync Server sites for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdc77-103">_**主题上次修改时间：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="cdc77-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="cdc77-104">在 Lync Server 中，你可以在网络上定义包含 Lync Server 组件的*网站*。</span><span class="sxs-lookup"><span data-stu-id="cdc77-104">In Lync Server, you define *sites* on your network that contain Lync Server components.</span></span> <span data-ttu-id="cdc77-105">站点是一组由高速度、低延迟网络（例如，单个局域网 (LAN) 或由高速光纤网络连接的两个网络）完美连接的计算机。</span><span class="sxs-lookup"><span data-stu-id="cdc77-105">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="cdc77-106">请注意，Lync Server 网站是来自 Active Directory 域服务站点和 Microsoft Exchange Server 站点的独立概念。</span><span class="sxs-lookup"><span data-stu-id="cdc77-106">Note that Lync Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="cdc77-107">您的 Lync 服务器站点不需要对应于您的 Active Directory 站点。</span><span class="sxs-lookup"><span data-stu-id="cdc77-107">Your Lync Server sites do not need to correspond to your Active Directory sites.</span></span>

<div>

## <a name="site-types"></a><span data-ttu-id="cdc77-108">网站类型</span><span class="sxs-lookup"><span data-stu-id="cdc77-108">Site Types</span></span>

<span data-ttu-id="cdc77-109">每个网站都是一个*中心网站*，其中包含至少一个前端池或一个标准版服务器或一个*分支站点*。</span><span class="sxs-lookup"><span data-stu-id="cdc77-109">Each site is either a *central site*, which contains at least one Front End pool or a Standard Edition server, or a *branch site*.</span></span> <span data-ttu-id="cdc77-110">每个分支站点仅与一个中心网站相关联，并且分支网站中的用户可以从关联的中心网站上的服务器中获取大多数 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="cdc77-110">Each branch site is associated with exactly one central site, and the users at the branch site get most of their Lync Server functionality from the servers at the associated central site.</span></span>

<span data-ttu-id="cdc77-111">每个分支站点都包含下列内容之一：</span><span class="sxs-lookup"><span data-stu-id="cdc77-111">Each branch site contains one of the following:</span></span>

  - <span data-ttu-id="cdc77-112">*Survivable 分支装置（SBA）*，它是一台具有 Lync 服务器注册机构的行业标准刀片式服务器和在 Windows server 上运行的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="cdc77-112">A *Survivable Branch Appliance (SBA)*, which is an industry-standard blade server with a Lync Server Registrar and a Mediation Server running on Windows Server.</span></span> <span data-ttu-id="cdc77-113">Survivable 分支装置还包含一个公共交换电话网络（PSTN）网关。</span><span class="sxs-lookup"><span data-stu-id="cdc77-113">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="cdc77-114">Survivable 分支设备适用于25至1000用户之间的分支站点。</span><span class="sxs-lookup"><span data-stu-id="cdc77-114">The Survivable Branch Appliance is designed for branch sites with between 25 and 1000 users.</span></span>

  - <span data-ttu-id="cdc77-115">*Survivable 分支服务器（SBS）*，它是一台运行 Windows Server 的服务器，它满足指定的硬件要求，并且安装了 Lync Server 注册机构和中介服务器软件。</span><span class="sxs-lookup"><span data-stu-id="cdc77-115">A *Survivable Branch Server (SBS)*, which is a server running Windows Server that meets specified hardware requirements, and that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="cdc77-116">它必须连接到 PSTN 网关或电话服务提供商的 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="cdc77-116">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="cdc77-117">Survivable 分支服务器专为1000和5000用户之间的分支站点而设计。</span><span class="sxs-lookup"><span data-stu-id="cdc77-117">The Survivable Branch Server is designed for branch sites with between 1000 and 5000 users.</span></span>

  - <span data-ttu-id="cdc77-118">PSTN 网关和*中介服务器*（可选）。</span><span class="sxs-lookup"><span data-stu-id="cdc77-118">A PSTN gateway, and, optionally, a *Mediation Server*.</span></span> <span data-ttu-id="cdc77-119">有关此服务器角色和其他服务器角色的详细信息，请参阅[Lync server 2013 中的服务器角色](lync-server-2013-server-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="cdc77-119">For details on this and other server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="cdc77-120">对中央网站具有弹性广域网（WAN）链接的分支机构可以使用第三个选项： PSTN 网关，也可以使用中介服务器。</span><span class="sxs-lookup"><span data-stu-id="cdc77-120">A branch office with a resilient wide area network (WAN) link to a central site can use the third option—a PSTN gateway, and, optionally, a Mediation Server.</span></span> <span data-ttu-id="cdc77-121">具有不太弹性的链接的分支 office 网站应使用 Survivable 分支装置或 Survivable 分支服务器，这种服务可在广域网络故障的时间内提供恢复。</span><span class="sxs-lookup"><span data-stu-id="cdc77-121">Branch office sites with less-resilient links should use a Survivable Branch Appliance or Survivable Branch Server, which provide resiliency in times of wide-area network failures.</span></span> <span data-ttu-id="cdc77-122">例如，在具有 Survivable 分支装置或部署 Survivable 分支服务器的网站中，如果将分支站点连接到中心网站的 WAN 已关闭，则用户仍可以发出和接收企业语音呼叫。</span><span class="sxs-lookup"><span data-stu-id="cdc77-122">For example, in a site with a Survivable Branch Appliance or Survivable Branch Server deployed, users can still make and receive Enterprise Voice calls if the WAN connecting the branch site to the central site is down.</span></span> <span data-ttu-id="cdc77-123">有关 Survivable 分支装置、Survivable 分支服务器和复原的详细信息，请参阅规划文档中的[Lync server 2013 中的 "规划企业语音复原](lync-server-2013-planning-for-enterprise-voice-resiliency.md)"。</span><span class="sxs-lookup"><span data-stu-id="cdc77-123">For details about the Survivable Branch Appliance, Survivable Branch Server, and resiliency, see [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="site-topologies"></a><span data-ttu-id="cdc77-124">网站拓扑</span><span class="sxs-lookup"><span data-stu-id="cdc77-124">Site Topologies</span></span>

<span data-ttu-id="cdc77-125">你的部署必须包含至少一个中心网站，并且可以包含零个到多个分支网站。</span><span class="sxs-lookup"><span data-stu-id="cdc77-125">Your deployment must include at least one central site, and can include zero to many branch sites.</span></span> <span data-ttu-id="cdc77-126">每个分支站点都与一个中心站点关联。</span><span class="sxs-lookup"><span data-stu-id="cdc77-126">Each branch site is affiliated with one central site.</span></span> <span data-ttu-id="cdc77-127">中心网站向分支网站提供 Lync 服务器服务，该服务不是在本地的分支网站托管，例如状态和会议。</span><span class="sxs-lookup"><span data-stu-id="cdc77-127">The central site provides the Lync Server services to the branch site that are not hosted locally at the branch site, such as presence and conferencing.</span></span>

<span data-ttu-id="cdc77-128">如果你有多个网站，则可以将不同站点上的前端池结合在一起，以启用灾难恢复功能。</span><span class="sxs-lookup"><span data-stu-id="cdc77-128">If you have multiple sites, you can pair together the Front End pools at different sites to enable disaster recovery abilities.</span></span> <span data-ttu-id="cdc77-129">有关详细信息，请参阅[Lync Server 2013 中的高可用性和灾难恢复支持](lync-server-2013-high-availability-and-disaster-recovery-support.md)。</span><span class="sxs-lookup"><span data-stu-id="cdc77-129">For details, see [High availability and disaster recovery support in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cdc77-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cdc77-130">See Also</span></span>


[<span data-ttu-id="cdc77-131">Lync Server 2013 中的服务器角色</span><span class="sxs-lookup"><span data-stu-id="cdc77-131">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="cdc77-132">Lync Server 2013 中的高可用性和灾难恢复支持</span><span class="sxs-lookup"><span data-stu-id="cdc77-132">High availability and disaster recovery support in Lync Server 2013</span></span>](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[<span data-ttu-id="cdc77-133">在 Lync Server 2013 中规划企业语音恢复能力</span><span class="sxs-lookup"><span data-stu-id="cdc77-133">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

