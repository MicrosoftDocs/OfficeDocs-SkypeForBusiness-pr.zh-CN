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
ms.openlocfilehash: 37843e85f5da250b3cb3d8e0fa4cdccdf506176d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a><span data-ttu-id="f660c-102">Lync Server 2013 的 lync Server 网站</span><span class="sxs-lookup"><span data-stu-id="f660c-102">Lync Server sites for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f660c-103">_**上次修改的主题：** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="f660c-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="f660c-104">在 Lync Server 中，您需要定义网络上包含 Lync Server 组件的*网站*。</span><span class="sxs-lookup"><span data-stu-id="f660c-104">In Lync Server, you define *sites* on your network that contain Lync Server components.</span></span> <span data-ttu-id="f660c-105">站点是一组由高速度、低延迟网络（例如，单个局域网 (LAN) 或由高速光纤网络连接的两个网络）完美连接的计算机。</span><span class="sxs-lookup"><span data-stu-id="f660c-105">A site is a set of computers that is well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> <span data-ttu-id="f660c-106">请注意，Lync Server 站点是来自 Active Directory 域服务站点和 Microsoft Exchange Server 站点的单独概念。</span><span class="sxs-lookup"><span data-stu-id="f660c-106">Note that Lync Server sites are a separate concept from Active Directory Domain Services sites and Microsoft Exchange Server sites.</span></span> <span data-ttu-id="f660c-107">您的 Lync Server 网站不需要对应于 Active Directory 站点。</span><span class="sxs-lookup"><span data-stu-id="f660c-107">Your Lync Server sites do not need to correspond to your Active Directory sites.</span></span>

<div>

## <a name="site-types"></a><span data-ttu-id="f660c-108">站点类型</span><span class="sxs-lookup"><span data-stu-id="f660c-108">Site Types</span></span>

<span data-ttu-id="f660c-109">每个站点都是一个*中央站点*，其中至少包含一个前端池或一个标准版服务器或一个*分支站点*。</span><span class="sxs-lookup"><span data-stu-id="f660c-109">Each site is either a *central site*, which contains at least one Front End pool or a Standard Edition server, or a *branch site*.</span></span> <span data-ttu-id="f660c-110">每个分支站点只与一个中心站点相关联，而分支站点的用户从关联的中央站点的服务器获取其大多数 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="f660c-110">Each branch site is associated with exactly one central site, and the users at the branch site get most of their Lync Server functionality from the servers at the associated central site.</span></span>

<span data-ttu-id="f660c-111">每个分支站点包含以下设备之一：</span><span class="sxs-lookup"><span data-stu-id="f660c-111">Each branch site contains one of the following:</span></span>

  - <span data-ttu-id="f660c-112">一个*Survivable 分支设备（SBA）*，它是一个具有 Lync server 注册器的行业标准刀片服务器和在 Windows server 上运行的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="f660c-112">A *Survivable Branch Appliance (SBA)*, which is an industry-standard blade server with a Lync Server Registrar and a Mediation Server running on Windows Server.</span></span> <span data-ttu-id="f660c-113">Survivable 分支设备还包含一个公共交换电话网络（PSTN）网关。</span><span class="sxs-lookup"><span data-stu-id="f660c-113">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="f660c-114">Survivable 分支设备适用于25到1000个用户之间的分支站点。</span><span class="sxs-lookup"><span data-stu-id="f660c-114">The Survivable Branch Appliance is designed for branch sites with between 25 and 1000 users.</span></span>

  - <span data-ttu-id="f660c-115">一个*Survivable 分支服务器（SBS）*，它是一台运行 Windows Server 的服务器，它满足指定的硬件要求，并且安装了 Lync server 注册器和中介服务器软件。</span><span class="sxs-lookup"><span data-stu-id="f660c-115">A *Survivable Branch Server (SBS)*, which is a server running Windows Server that meets specified hardware requirements, and that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="f660c-116">它必须连接到 PSTN 网关或电话服务提供商的 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="f660c-116">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="f660c-117">Survivable Branch Server 是为具有 1000 至 5000 个用户的分支站点而设计的。</span><span class="sxs-lookup"><span data-stu-id="f660c-117">The Survivable Branch Server is designed for branch sites with between 1000 and 5000 users.</span></span>

  - <span data-ttu-id="f660c-118">PSTN 网关和可选的*中介服务器*。</span><span class="sxs-lookup"><span data-stu-id="f660c-118">A PSTN gateway, and, optionally, a *Mediation Server*.</span></span> <span data-ttu-id="f660c-119">有关此服务器角色和其他服务器角色的详细信息，请参阅[Lync server 2013 中的服务器角色](lync-server-2013-server-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="f660c-119">For details on this and other server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="f660c-120">具有指向中央站点的可恢复广域网 (WAN) 链接的分支机构可以使用第三个选项，即 PSTN 网关和可选的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="f660c-120">A branch office with a resilient wide area network (WAN) link to a central site can use the third option—a PSTN gateway, and, optionally, a Mediation Server.</span></span> <span data-ttu-id="f660c-121">具有较低弹性链接的分支机构网站应使用 Survivable 分支设备或 Survivable 分支服务器，这将在广域网络故障发生时提供恢复能力。</span><span class="sxs-lookup"><span data-stu-id="f660c-121">Branch office sites with less-resilient links should use a Survivable Branch Appliance or Survivable Branch Server, which provide resiliency in times of wide-area network failures.</span></span> <span data-ttu-id="f660c-122">例如，在部署了 Survivable 分支机构或 Survivable 分支服务器的站点中，如果将分支站点连接到中心站点的 WAN 处于关闭状态，则用户仍可以发出和接收企业语音呼叫。</span><span class="sxs-lookup"><span data-stu-id="f660c-122">For example, in a site with a Survivable Branch Appliance or Survivable Branch Server deployed, users can still make and receive Enterprise Voice calls if the WAN connecting the branch site to the central site is down.</span></span> <span data-ttu-id="f660c-123">有关 Survivable 分支装置、Survivable 分支服务器和恢复的详细信息，请参阅规划文档中的在[Lync server 2013 中规划企业语音恢复](lync-server-2013-planning-for-enterprise-voice-resiliency.md)。</span><span class="sxs-lookup"><span data-stu-id="f660c-123">For details about the Survivable Branch Appliance, Survivable Branch Server, and resiliency, see [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="site-topologies"></a><span data-ttu-id="f660c-124">站点拓扑</span><span class="sxs-lookup"><span data-stu-id="f660c-124">Site Topologies</span></span>

<span data-ttu-id="f660c-125">部署中必须至少包含一个中央站点，可以包含多个分支站点，也可以不包含分支站点。</span><span class="sxs-lookup"><span data-stu-id="f660c-125">Your deployment must include at least one central site, and can include zero to many branch sites.</span></span> <span data-ttu-id="f660c-126">每个分支站点都与一个中央站点关联。</span><span class="sxs-lookup"><span data-stu-id="f660c-126">Each branch site is affiliated with one central site.</span></span> <span data-ttu-id="f660c-127">中央站点向分支站点提供了 Lync Server 服务，该站点不在分支站点本地托管，如状态和会议。</span><span class="sxs-lookup"><span data-stu-id="f660c-127">The central site provides the Lync Server services to the branch site that are not hosted locally at the branch site, such as presence and conferencing.</span></span>

<span data-ttu-id="f660c-128">如果有多个站点，则可以将不同站点的前端池配对，以实现灾难恢复能力。</span><span class="sxs-lookup"><span data-stu-id="f660c-128">If you have multiple sites, you can pair together the Front End pools at different sites to enable disaster recovery abilities.</span></span> <span data-ttu-id="f660c-129">有关详细信息，请参阅[Lync Server 2013 中的高可用性和灾难恢复支持](lync-server-2013-high-availability-and-disaster-recovery-support.md)。</span><span class="sxs-lookup"><span data-stu-id="f660c-129">For details, see [High availability and disaster recovery support in Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f660c-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f660c-130">See Also</span></span>


[<span data-ttu-id="f660c-131">Lync Server 2013 中的服务器角色</span><span class="sxs-lookup"><span data-stu-id="f660c-131">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="f660c-132">Lync Server 2013 中的高可用性和灾难恢复支持</span><span class="sxs-lookup"><span data-stu-id="f660c-132">High availability and disaster recovery support in Lync Server 2013</span></span>](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[<span data-ttu-id="f660c-133">在 Lync Server 2013 中规划企业语音恢复能力</span><span class="sxs-lookup"><span data-stu-id="f660c-133">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

