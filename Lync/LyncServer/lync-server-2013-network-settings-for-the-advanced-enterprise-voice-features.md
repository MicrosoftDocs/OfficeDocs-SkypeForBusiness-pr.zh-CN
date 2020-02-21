---
title: Lync Server 2013：高级企业语音功能的网络设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 340a1902137b6c675b154ef9ccf3d9fbcc882e88
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="b56da-102">Lync Server 2013 中的高级企业语音功能的网络设置</span><span class="sxs-lookup"><span data-stu-id="b56da-102">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b56da-103">_**上次修改的主题：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="b56da-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="b56da-104">Lync Server 具有三个高级企业语音功能：呼叫允许控制（CAC）、紧急服务（E9-1-1）和媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="b56da-104">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="b56da-105">这些功能将共享网络区域、网络站点以及 Lync Server 拓扑中每个子网与网络站点的关联的特定配置要求。</span><span class="sxs-lookup"><span data-stu-id="b56da-105">These features share certain configuration requirements for network regions, network sites, and association of each subnet in the Lync Server topology with a network site.</span></span> <span data-ttu-id="b56da-106">有关这些功能的部署规划的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="b56da-106">For details about planning for deployment of these features, see:</span></span>

  - [<span data-ttu-id="b56da-107">在 Lync Server 2013 中规划呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="b56da-107">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)

  - [<span data-ttu-id="b56da-108">在 Lync Server 2013 中规划紧急服务（E9-1-1）</span><span class="sxs-lookup"><span data-stu-id="b56da-108">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [<span data-ttu-id="b56da-109">在 Lync Server 2013 中规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="b56da-109">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)

<span data-ttu-id="b56da-110">有关部署上述每项功能的详细信息，请参阅部署文档中的在[Lync Server 2013 中部署高级企业语音功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)。</span><span class="sxs-lookup"><span data-stu-id="b56da-110">For details about deploying each of these features, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md) in the Deployment documentation.</span></span>

<span data-ttu-id="b56da-111">本主题概述了所有三种高级企业语音功能通用的配置要求。</span><span class="sxs-lookup"><span data-stu-id="b56da-111">This topic provides an overview of the configuration requirements that are common to all three advanced Enterprise Voice features.</span></span>

<div>

## <a name="network-regions"></a><span data-ttu-id="b56da-112">网络区域</span><span class="sxs-lookup"><span data-stu-id="b56da-112">Network Regions</span></span>

<span data-ttu-id="b56da-113">网络区域是仅在呼叫允许控制 (CAC)、E9-1-1 和媒体旁路的配置中使用的网络中心或网络中枢。</span><span class="sxs-lookup"><span data-stu-id="b56da-113">A network region is a network hub or network backbone used only in the configuration of call admission control (CAC), E9-1-1, and media bypass.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b56da-114">网络区域与 Lync Server 电话拨入式会议区域不同，这是将电话拨入式会议访问号码与一个或多个 Lync Server 拨号计划关联所必需的。</span><span class="sxs-lookup"><span data-stu-id="b56da-114">Network regions are not the same as Lync Server dial-in conferencing regions, which are required to associate dial-in conferencing access numbers with one or more Lync Server dial plans.</span></span> <span data-ttu-id="b56da-115">有关电话拨入式会议区域的详细信息，请参阅规划文档中的<A href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 中的电话拨入式会议要求</A>。</span><span class="sxs-lookup"><span data-stu-id="b56da-115">For details about dial-in conferencing regions, see <A href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<span data-ttu-id="b56da-116">CAC 要求每个网络区域都有一个关联的 Lync Server 中心站点，该站点管理区域内的媒体流量（即，根据已配置的策略做出决策，关于实时音频或视频会话是否可以建立）。</span><span class="sxs-lookup"><span data-stu-id="b56da-116">CAC requires that every network region have an associated Lync Server central site, which manages media traffic within the region (that is, it makes decisions based on policies that you have configured, regarding whether or not a real-time audio or video session can be established).</span></span> <span data-ttu-id="b56da-117">Lync Server 中心站点不代表地理位置，而是指配置为池或池集的服务器的逻辑组。</span><span class="sxs-lookup"><span data-stu-id="b56da-117">Lync Server central sites do not represent geographical locations, but rather logical groups of servers that are configured as a pool or a set of pools.</span></span> <span data-ttu-id="b56da-118">有关中心网站的详细信息，请参阅规划文档中的[Lync Server 2013 中的参考拓扑](lync-server-2013-reference-topologies.md)。</span><span class="sxs-lookup"><span data-stu-id="b56da-118">For details about central sites, see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="b56da-119">另请参阅可支持性文档中的[Lync Server 2013 中支持的拓扑](lync-server-2013-supported-topologies.md)。</span><span class="sxs-lookup"><span data-stu-id="b56da-119">Also see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md) in the Supportability documentation.</span></span>

<span data-ttu-id="b56da-120">若要配置网络区域，您可以使用 Lync Server 控制面板的 "**网络配置**" 部分中的 "**区域**" 选项卡，或者运行**CsNetworkRegion**或**CsNetworkRegion** Lync Server Management Shell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b56da-120">To configure a network region, you can either use the **Regions** tab on the **Network Configuration** section of Lync Server Control Panel, or run the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="b56da-121">有关说明，请参阅部署文档中的在[Lync server 2013 中创建或修改网络区域](lync-server-2013-create-or-modify-a-network-region.md)，或者参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="b56da-121">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

<span data-ttu-id="b56da-122">由所有三个高级企业语音功能共享相同的网络区域定义。</span><span class="sxs-lookup"><span data-stu-id="b56da-122">The same network region definitions are shared by all three advanced Enterprise Voice features.</span></span> <span data-ttu-id="b56da-123">如果已经为某个功能创建了网络区域，则不必再为其他功能新建网络区域。</span><span class="sxs-lookup"><span data-stu-id="b56da-123">If you have already created network regions for one feature, you do not need to create new network regions for the other features.</span></span> <span data-ttu-id="b56da-124">但是，可能需要修改现有的网络区域定义，以应用特定于功能的设置。</span><span class="sxs-lookup"><span data-stu-id="b56da-124">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="b56da-125">例如，如果已为 E9-1-1（它不要求有关联的中央站点）创建网络区域，稍后部署呼叫允许控制，则必须修改每个网络区域定义以指定中央站点。</span><span class="sxs-lookup"><span data-stu-id="b56da-125">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and, later, you deploy call admission control, you must modify each of the network region definitions to specify a central site.</span></span>

<span data-ttu-id="b56da-126">若要将 Lync Server 中央站点与网络区域关联，请使用 Lync Server 控制面板的 "**网络配置**" 部分或运行**CsNetworkRegion**或**CsNetworkRegion** Lync Server 命令行管理程序 cmdlet 来指定中心站点名称。</span><span class="sxs-lookup"><span data-stu-id="b56da-126">To associate a Lync Server central site with a network region, you specify the central site name, either by using the **Network Configuration** section of Lync Server Control Panel, or by running the **New-CsNetworkRegion** or **Set-CsNetworkRegion** Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="b56da-127">有关说明，请参阅部署文档中的在[Lync server 2013 中创建或修改网络区域](lync-server-2013-create-or-modify-a-network-region.md)，或者参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="b56da-127">For instructions, see [Create or modify a network region in Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="network-sites"></a><span data-ttu-id="b56da-128">网络站点</span><span class="sxs-lookup"><span data-stu-id="b56da-128">Network Sites</span></span>

<span data-ttu-id="b56da-p107">网络站点代表地理位置，例如分支机构、地区办事处或总部。每个网络站点都必须与特定网络区域相关联。</span><span class="sxs-lookup"><span data-stu-id="b56da-p107">A network site represents a geographical location, such as a branch office, a regional office, or a main office. Each network site must be associated with a specific network region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b56da-131">网络站点仅由高级企业语音功能使用。</span><span class="sxs-lookup"><span data-stu-id="b56da-131">Network sites are used only by the advanced Enterprise Voice features.</span></span> <span data-ttu-id="b56da-132">它们与您在 Lync Server 拓扑中配置的分支站点不同。</span><span class="sxs-lookup"><span data-stu-id="b56da-132">They are not the same as the branch sites that you configure in your Lync Server topology.</span></span> <span data-ttu-id="b56da-133">有关分支站点的详细信息，请参阅规划文档中的<A href="lync-server-2013-reference-topologies.md">Lync Server 2013 中的参考拓扑</A>。</span><span class="sxs-lookup"><span data-stu-id="b56da-133">For details about branch sites, see <A href="lync-server-2013-reference-topologies.md">Reference topologies in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="b56da-134">另请参阅可支持性文档中的<A href="lync-server-2013-supported-topologies.md">Lync Server 2013 中支持的拓扑</A>。</span><span class="sxs-lookup"><span data-stu-id="b56da-134">Also see <A href="lync-server-2013-supported-topologies.md">Supported topologies in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="b56da-135">若要配置网络站点并将其与网络区域相关联，可以使用 Lync Server 控制面板的 "**网络配置**" 部分，或者运行 Lync Server Management Shell **CsNetworkSite**或**CsNetworkSite** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b56da-135">To configure a network site and associate it with a network region, you can either use the **Network Configuration** section of Lync Server Control Panel, or run the Lync Server Management Shell **New-CsNetworkSite** or **Set-CsNetworkSite** cmdlets.</span></span> <span data-ttu-id="b56da-136">有关详细信息，请参阅部署文档中的在[Lync server 2013 中创建或修改网络站点](lync-server-2013-create-or-modify-a-network-site.md)，或者参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="b56da-136">For details, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="b56da-137">标识 IP 子网</span><span class="sxs-lookup"><span data-stu-id="b56da-137">Identify IP Subnets</span></span>

<span data-ttu-id="b56da-p110">对于每个网络站点，您将需要和网络管理员一起确定分配给每个网络站点的 IP 子网。如果网络管理员已经将 IP 子网组织到网络区域和网络站点中，则您的工作将大为简化。</span><span class="sxs-lookup"><span data-stu-id="b56da-p110">For each network site, you will need to work with your network administrator to determine which IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="b56da-p111">例如，可为北美区域中的纽约站点分配以下 IP 子网：172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。如果通常在底特律工作的 Bob 出差到纽约办事处接受培训，当他打开计算机并连接到网络时，他的计算机将获取分配给纽约的四个范围之一中的 IP 地址，例如 172.29.80.103。</span><span class="sxs-lookup"><span data-stu-id="b56da-p111">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York—for example, 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b56da-142">在服务器上的网络配置过程中指定的 IP 子网必须与客户端计算机提供的格式相匹配，以便能够正确地用于媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="b56da-142">The IP subnets specified during network configuration on the server must match the format that is provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="b56da-143">Lync 客户端获取其本地 IP 地址，并使用关联的子网掩码屏蔽 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b56da-143">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="b56da-144">在确定与每个客户端关联的绕过 ID 时，注册器会将与每个网络站点关联的 IP 子网的列表与客户端提供的子网进行比较，以实现精确匹配。</span><span class="sxs-lookup"><span data-stu-id="b56da-144">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet that is provided by the client for an exact match.</span></span> <span data-ttu-id="b56da-145">因此，在服务器上的网络配置过程中输入的子网是实际的子网而不是虚拟子网，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="b56da-145">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="b56da-146">（如果您部署了呼叫允许控制，但没有媒体旁路，则即使您配置了虚拟子网，呼叫允许控制也能正常运行。</span><span class="sxs-lookup"><span data-stu-id="b56da-146">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="b56da-147">例如，如果 Lync 客户端在 IP 地址为255.255.255.0 且 IP 子网掩码为255.255.255.0 的计算机上登录，则它将请求与子网172.29.81.0 关联的绕过 ID。</span><span class="sxs-lookup"><span data-stu-id="b56da-147">For example, if a Lync client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, it will request the bypass ID that is associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="b56da-148">如果子网定义为 172.29.0.0/16，那么即使客户端属于虚拟子网，注册器也不会将此看做匹配，因为注册器会专门查找子网 172.29.81.0。</span><span class="sxs-lookup"><span data-stu-id="b56da-148">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="b56da-149">因此，管理员应完全按照 Lync 客户端提供的方式输入子网（静态或动态主机配置协议（DHCP）为其预配子网）。</span><span class="sxs-lookup"><span data-stu-id="b56da-149">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration, either statically or by Dynamic Host Configuration Protocol (DHCP).)</span></span>



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a><span data-ttu-id="b56da-150">将子网与网络站点相关联</span><span class="sxs-lookup"><span data-stu-id="b56da-150">Associating Subnets with Network Sites</span></span>

<span data-ttu-id="b56da-151">企业网络中的每个子网都必须与网络站点相关联（即每个子网需要与一个地理位置相关联）。</span><span class="sxs-lookup"><span data-stu-id="b56da-151">Every subnet in the enterprise network must be associated with a network site (that is, every subnet needs to be associated with a geographic location).</span></span> <span data-ttu-id="b56da-152">此子网的关联使高级企业语音功能能够以地理位置查找终结点。</span><span class="sxs-lookup"><span data-stu-id="b56da-152">This association of subnets enables the advanced Enterprise Voice features to locate the endpoints geographically.</span></span> <span data-ttu-id="b56da-153">例如，通过找到终结点，CAC 可以调节往返于网络站点的实时音频和视频数据流。</span><span class="sxs-lookup"><span data-stu-id="b56da-153">For example, locating the endpoints enables CAC to regulate the flow of real-time audio and video data going to and from the network site.</span></span>

<span data-ttu-id="b56da-154">若要将子网与网络站点关联，可以使用 Lync Server 控制面板的 "**网络配置**" 部分，也可以使用 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="b56da-154">To associate subnets with network sites, you can either use the **Network Configuration** section of Lync Server Control Panel, or you can use the Lync Server Management Shell.</span></span> <span data-ttu-id="b56da-155">有关说明，请参阅部署文档中的在[Lync server 2013 中将子网与网络站点关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)，或参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="b56da-155">For instructions, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) in the Deployment documentation, or refer to the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b56da-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b56da-156">See Also</span></span>


[<span data-ttu-id="b56da-157">在 Lync Server 2013 中规划呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="b56da-157">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="b56da-158">在 Lync Server 2013 中规划紧急服务（E9-1-1）</span><span class="sxs-lookup"><span data-stu-id="b56da-158">Planning for emergency services (E9-1-1) in Lync Server 2013</span></span>](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[<span data-ttu-id="b56da-159">在 Lync Server 2013 中规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="b56da-159">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

