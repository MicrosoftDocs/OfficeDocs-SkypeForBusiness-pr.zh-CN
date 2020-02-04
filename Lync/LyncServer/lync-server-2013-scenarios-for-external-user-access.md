---
title: Lync Server 2013：外部用户访问方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eab8323744615dc3f5d0b68f4325fbfb85bf911e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="0baff-102">Lync Server 2013 中的外部用户访问方案</span><span class="sxs-lookup"><span data-stu-id="0baff-102">Scenarios for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0baff-103">_**主题上次修改时间：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="0baff-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="0baff-104">为 Lync Server 2013 提供外部用户访问需要在你的外围网络中至少部署一个 Edge 服务器和一个反向代理。</span><span class="sxs-lookup"><span data-stu-id="0baff-104">Providing external user access for Lync Server 2013 requires that you deploy at least one Edge Server and one reverse proxy in your perimeter network.</span></span> <span data-ttu-id="0baff-105">或者，您可以在内部网络中部署 Director 或控制器池。</span><span class="sxs-lookup"><span data-stu-id="0baff-105">Optionally, you may deploy a Director or Director pool in your internal network.</span></span>

<span data-ttu-id="0baff-106">如果你需要比单个 Edge 服务器提供的容量更大的容量，或者如果你的 Edge 服务器部署需要高可用性，则可以在负载平衡的池中配置负载平衡和部署多台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="0baff-106">If you need greater capacity than a single Edge Server can provide, or if you need high availability for your Edge Server deployment, you can configure load balancing and deploy multiple Edge Servers in a load balanced pool.</span></span> <span data-ttu-id="0baff-107">如果您的组织有多个数据中心，则可以在多个位置拥有 Edge 服务器或边缘池部署。</span><span class="sxs-lookup"><span data-stu-id="0baff-107">If your organization has multiple data centers, you can have Edge Server or Edge pool deployments at more than one location.</span></span> <span data-ttu-id="0baff-108">但是，只能将一个边缘服务器部署指定为联盟路由。</span><span class="sxs-lookup"><span data-stu-id="0baff-108">However, only one of the Edge Server deployments can be designated as the federation route.</span></span>

<span data-ttu-id="0baff-109">本部分定义了边缘服务器部署的方案，并将计划分区映射到可能的方案。</span><span class="sxs-lookup"><span data-stu-id="0baff-109">This section defines the scenarios for Edge Server deployments and maps the planning sections to the possible scenarios.</span></span> <span data-ttu-id="0baff-110">例如，如果你的部署需要高可用性、具有可扩展消息和状态（XMPP）联系人的联盟以及 Lync 移动性，你可以选择下表中满足这些要求的匹配条目，并使用引用的计划分区来定义你的部署，如下流程图所示。</span><span class="sxs-lookup"><span data-stu-id="0baff-110">For example, if your deployment requires high availability, federation with extensible messaging and presence (XMPP) contacts, and Lync mobility, you would select the matching entries in the following table that would satisfy these requirements and use the referenced planning sections to define your deployment, as illustrated in the following flowchart.</span></span>

<span data-ttu-id="0baff-111">**边缘服务器部署方案选择过程**</span><span class="sxs-lookup"><span data-stu-id="0baff-111">**Edge Server deployment scenario selection process**</span></span>

<span data-ttu-id="0baff-112">![示例部署流程图](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "示例部署流程图")</span><span class="sxs-lookup"><span data-stu-id="0baff-112">![Sample deployment flowchart](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Sample deployment flowchart")</span></span>

<span data-ttu-id="0baff-113">通过使用此过程，你可以为你希望为用户部署的所有潜在功能的配置进行规划和记录。</span><span class="sxs-lookup"><span data-stu-id="0baff-113">By using this process, you can plan for and document the configuration of all potential features that you intend to deploy for your users.</span></span> <span data-ttu-id="0baff-114">但是，你可以在部署 Edge 服务器之后添加联盟和移动服务，并在添加其他功能之前确认了正确的操作。</span><span class="sxs-lookup"><span data-stu-id="0baff-114">However, you can add federation and mobility services after you have deployed the Edge Server and have confirmed the correct operation before adding other features.</span></span> <span data-ttu-id="0baff-115">在 "部署" 部分中介绍了将功能添加到现有边缘服务器部署的过程。</span><span class="sxs-lookup"><span data-stu-id="0baff-115">The process of adding features to an existing Edge Server deployment is covered in the Deployment section.</span></span> <span data-ttu-id="0baff-116">有关部署的详细信息，请参阅在[Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)通过在初始计划过程中包括计划执行这些功能，你可以为已添加的功能准备 dns、防火墙和证书要求，从而使你能够提前获取证书并配置 dns 和端口/协议要求。</span><span class="sxs-lookup"><span data-stu-id="0baff-116">For details on deployment, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) By including planning for these features during the initial planning process, you can prepare for the DNS, firewall, and certificate requirements for the added features, which enables you to acquire the certificates and configure DNS and port/protocol requirements in advance.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="0baff-117">如果你打算安装 Edge 服务器和反向代理，然后稍后添加功能（例如，联盟和移动），请确定部署后所有服务所需的证书。</span><span class="sxs-lookup"><span data-stu-id="0baff-117">If you are planning to install the Edge Servers and reverse proxy and then add features later (for example, federation and mobility), determine what certificates you will require for all services after deployment.</span></span> <span data-ttu-id="0baff-118">提前计划和获取所有功能的证书，最初部署或不是，您不必订购新的证书来满足联盟（即在 Edge 服务器上）或反向代理（即移动性）的要求。服务）。</span><span class="sxs-lookup"><span data-stu-id="0baff-118">Planning for and acquiring the certificates for all features in advance, initially deployed or not, saves you from having to order new certificates to satisfy the requirements of federation (that is, on the Edge Servers) or the reverse proxy (that is, for mobility services).</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="0baff-119">所有 edge 服务都在每台边缘服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="0baff-119">All edge services run on each Edge Server.</span></span> <span data-ttu-id="0baff-120">无法在两台不同的边缘服务器之间拆分服务。</span><span class="sxs-lookup"><span data-stu-id="0baff-120">Services cannot be split between two different Edge Servers.</span></span> <span data-ttu-id="0baff-121">如果为可伸缩性部署边缘池，则会在池中的每台边缘服务器上部署所有 Edge 服务。</span><span class="sxs-lookup"><span data-stu-id="0baff-121">If you deploy an Edge pool for scalability, all edge services are deployed on each Edge Server in the pool.</span></span> <span data-ttu-id="0baff-122">XMPP 联盟、Office 通信服务器和 Lync 服务器联盟、公共 IM 连接和客户移动性是部署第一台边缘服务器或边缘池后可以部署的其他服务。</span><span class="sxs-lookup"><span data-stu-id="0baff-122">XMPP federation, Office Communications Server, and Lync Server federation, public IM connectivity and client mobility are additional services that can be deployed after you have deployed your first Edge Server or Edge pool.</span></span> <span data-ttu-id="0baff-123">移动服务是使用反向代理的功能。</span><span class="sxs-lookup"><span data-stu-id="0baff-123">Mobility services is a feature that uses the reverse proxy.</span></span> <span data-ttu-id="0baff-124">安装移动服务不会将功能添加到 Edge 服务器，但需要重新配置反向代理。</span><span class="sxs-lookup"><span data-stu-id="0baff-124">Installation of mobility services will not add features to your Edge Servers, but will require reconfiguration of your reverse proxy.</span></span> <span data-ttu-id="0baff-125">列出这些功能的 "<STRONG>安装目标</STRONG>" 列在 "<STRONG>边缘服务器计划" 部分</STRONG>下的关联列中提供规划指南，或者在安装和配置边缘服务器时，用于同时计划要部署的这些功能的部分。</span><span class="sxs-lookup"><span data-stu-id="0baff-125">The <STRONG>Installation goal</STRONG> column that lists these features provides planning guidance in the associated column under <STRONG>Edge Server planning section or sections</STRONG> for concurrently planning these features to be deployed when the Edge Servers are installed and configured.</span></span>



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a><span data-ttu-id="0baff-126">标识和映射部署目标</span><span class="sxs-lookup"><span data-stu-id="0baff-126">Identifying and Mapping Your Deployment Goals</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0baff-127">安装目标</span><span class="sxs-lookup"><span data-stu-id="0baff-127">Installation goal</span></span></th>
<th><span data-ttu-id="0baff-128">边缘服务器规划文档</span><span class="sxs-lookup"><span data-stu-id="0baff-128">Edge Server planning documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0baff-129">你已确定单个服务器已足够用于你的基础结构中的 Edge 服务。</span><span class="sxs-lookup"><span data-stu-id="0baff-129">You have decided that a single server is sufficient for Edge services in your infrastructure.</span></span> <span data-ttu-id="0baff-130">你还打算将 Edge 服务器的专用 IP 地址用于带有 NAT 的外部接口到 Internet。</span><span class="sxs-lookup"><span data-stu-id="0baff-130">You also intend to use private IP addresses for the Edge server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="0baff-131">如果您在您的周边环境中部署单个边缘服务器，请使用此规划部分。</span><span class="sxs-lookup"><span data-stu-id="0baff-131">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="0baff-132">你将部署分配给 Edge 服务器的专用 IP 地址的边缘服务器，并将使用 NAT 为 Internet 上的外部用户提供公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="0baff-132">You will deploy an Edge Server with private IP addresses assigned to the Edge Server and will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="0baff-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Lync Server 2013 中使用专用 IP 地址和 NAT 的单一合并边缘</a></span><span class="sxs-lookup"><span data-stu-id="0baff-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baff-134">你已确定单个服务器已足够用于你的基础结构中的 Edge 服务。</span><span class="sxs-lookup"><span data-stu-id="0baff-134">You have decided that a single server is sufficient for Edge services in your infrastructure.</span></span> <span data-ttu-id="0baff-135">你还打算将边缘服务器外部接口的公共 IP 地址用于 Internet。</span><span class="sxs-lookup"><span data-stu-id="0baff-135">You also intend to use public IP addresses for the Edge server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="0baff-136">如果您在您的周边环境中部署单个边缘服务器，请使用此规划部分。</span><span class="sxs-lookup"><span data-stu-id="0baff-136">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="0baff-137">你将部署分配给 Edge 服务器的公共 IP 地址的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="0baff-137">You will deploy an Edge Server with public IP addresses assigned to the Edge Server.</span></span> <span data-ttu-id="0baff-138">在此方案中，您将使用路由，而不是 NAT。</span><span class="sxs-lookup"><span data-stu-id="0baff-138">Instead of NAT, you will use routing in this scenario.</span></span> <span data-ttu-id="0baff-139">边缘服务器的实际公共 IP 地址可用于外部用户连接。</span><span class="sxs-lookup"><span data-stu-id="0baff-139">The actual public IP address of the Edge Server are made available for external user connections.</span></span></p></td>
<td><p><span data-ttu-id="0baff-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Lync Server 2013 中使用公用 IP 地址的单一合并边缘</a></span><span class="sxs-lookup"><span data-stu-id="0baff-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Single consolidated edge with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0baff-141">你已确定 Edge 服务的高可用性对你的用户很重要，你将在此池中部署两台或多台 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="0baff-141">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="0baff-142">你还打算将 Edge 服务器的专用 IP 地址用于带有 NAT 的外部接口到 Internet。</span><span class="sxs-lookup"><span data-stu-id="0baff-142">You also intend to use private IP addresses for the Edge Server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="0baff-143">如果您在您的外围环境中部署了一个 Edge 服务器池，请使用此规划部分。</span><span class="sxs-lookup"><span data-stu-id="0baff-143">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="0baff-144">你将使用分配给 Edge 服务器的专用 IP 地址部署边缘服务器，使用 DNS 负载平衡在池中分布通信。</span><span class="sxs-lookup"><span data-stu-id="0baff-144">You will deploy the Edge Servers with private IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="0baff-145">你将使用 NAT 为 Internet 上的外部用户提供公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="0baff-145">You will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="0baff-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Lync Server 2013 中的扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</a></span><span class="sxs-lookup"><span data-stu-id="0baff-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baff-147">你已确定 Edge 服务的高可用性对你的用户很重要，你将在此池中部署两台或多台 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="0baff-147">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="0baff-148">你还打算将边缘服务器外部接口的公共 IP 地址用于 Internet。</span><span class="sxs-lookup"><span data-stu-id="0baff-148">You also intend to use public IP addresses for the Edge Server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="0baff-149">如果您在您的外围环境中部署了一个 Edge 服务器池，请使用此规划部分。</span><span class="sxs-lookup"><span data-stu-id="0baff-149">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="0baff-150">你将使用分配给 Edge 服务器的公共 IP 地址部署边缘服务器，使用 DNS 负载平衡在池中分布通信。</span><span class="sxs-lookup"><span data-stu-id="0baff-150">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="0baff-151">您将使用路由来为 Internet 上的外部用户提供公共 IP 地址，而不是 NAT。</span><span class="sxs-lookup"><span data-stu-id="0baff-151">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="0baff-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Lync Server 2013 中的扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）</a></span><span class="sxs-lookup"><span data-stu-id="0baff-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0baff-153">你已确定 Edge 服务的高可用性对你的用户很重要，你将使用硬件负载平衡器在此池中部署两台或多台 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="0baff-153">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool using a hardware load balancer.</span></span></p>
<p><span data-ttu-id="0baff-154">如果您在您的外围环境中部署了一个 Edge 服务器池，请使用此规划部分。</span><span class="sxs-lookup"><span data-stu-id="0baff-154">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="0baff-155">你将使用分配给 Edge 服务器的公共 IP 地址部署边缘服务器，使用硬件负载平衡器在池中分布通信。</span><span class="sxs-lookup"><span data-stu-id="0baff-155">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using hardware load balancers to distribute communication across the pool.</span></span> <span data-ttu-id="0baff-156">您将使用路由来为 Internet 上的外部用户提供公共 IP 地址，而不是 NAT。</span><span class="sxs-lookup"><span data-stu-id="0baff-156">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="0baff-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013 中使用硬件负载平衡器的扩展的合并边缘</a></span><span class="sxs-lookup"><span data-stu-id="0baff-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Scaled consolidated edge with hardware load balancers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0baff-158">联合身份验证方案允许你对将扩展你的用户可以与之通信的合作伙伴类型的功能进行规划。</span><span class="sxs-lookup"><span data-stu-id="0baff-158">The federation scenarios allow you to plan for the feature that will extend the types of partners that your users can communicate with.</span></span></p>
<ul>
<li><p><span data-ttu-id="0baff-159">Lync Server 联合身份验证</span><span class="sxs-lookup"><span data-stu-id="0baff-159">Lync Server federation</span></span></p></li>
<li><p><span data-ttu-id="0baff-160">Office 通信服务器联合</span><span class="sxs-lookup"><span data-stu-id="0baff-160">Office Communications Server federation</span></span></p></li>
<li><p><span data-ttu-id="0baff-161">公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="0baff-161">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="0baff-162">XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="0baff-162">XMPP federation</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0baff-163">规划联盟方案</span><span class="sxs-lookup"><span data-stu-id="0baff-163">Planning for Federation Scenarios</span></span></p>
<ul>
<li><p><span data-ttu-id="0baff-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">规划 Lync Server 2013 和 Office 通信服务器联合</a></span><span class="sxs-lookup"><span data-stu-id="0baff-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 and Office Communications Server federation</a></span></span></p></li>
<li><p><span data-ttu-id="0baff-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">在 Lync Server 2013 中规划公共即时消息连接</a></span><span class="sxs-lookup"><span data-stu-id="0baff-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planning for public instant messaging connectivity in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="0baff-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">在 Lync Server 2013 中规划可扩展消息和状态协议（XMPP）联合</a></span><span class="sxs-lookup"><span data-stu-id="0baff-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0baff-167">移动服务通过反向代理提供。</span><span class="sxs-lookup"><span data-stu-id="0baff-167">Mobility services are offered through the reverse proxy.</span></span> <span data-ttu-id="0baff-168">为外部用户启用移动能力的服务将部署在前端服务器或前端池。</span><span class="sxs-lookup"><span data-stu-id="0baff-168">Services that enable mobility for external users are deployed on the Front End Server or Front End pool.</span></span> <span data-ttu-id="0baff-169">在反向代理服务器上创建或修改现有发布规则，以便为外部用户启用移动服务。</span><span class="sxs-lookup"><span data-stu-id="0baff-169">You create or modify existing publishing rules on the reverse proxy to enable mobility services for your external users.</span></span></p></td>
<td><p><span data-ttu-id="0baff-170"><a href="lync-server-2013-planning-for-mobility.md">在 Lync Server 2013 中规划移动功能</a></span><span class="sxs-lookup"><span data-stu-id="0baff-170"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> <span data-ttu-id="0baff-171">在以下方案部分中，参考体系结构、示例 DNS、端口/协议定义和证书要求。</span><span class="sxs-lookup"><span data-stu-id="0baff-171">In the following Scenarios sections are reference architectures, example DNS, port/protocol definitions, and certificate requirements.</span></span> <span data-ttu-id="0baff-172">还包括用于你的 DNS、端口/协议定义和证书需求的图表。</span><span class="sxs-lookup"><span data-stu-id="0baff-172">Also included are diagrams for your DNS, port/protocol definitions and certificate needs.</span></span> <span data-ttu-id="0baff-173">图表将提供模板供你填写和分发到其他团队（例如，你的组织的网络团队、公共密钥基础结构团队和服务器部署团队）。</span><span class="sxs-lookup"><span data-stu-id="0baff-173">The diagrams will provide a template for you to fill in and distribute to other teams (for example, your organization’s Network Team, Public Key Infrastructure Team, and Server Deployment Team).</span></span> <span data-ttu-id="0baff-174">图表的目标是增强通信，并确保在将所需的边缘服务器配置元素与将执行实际配置工作的人员进行通信时确保成功。</span><span class="sxs-lookup"><span data-stu-id="0baff-174">The goal of the diagrams is to enhance communication and to ensure success when communicating the required Edge Server configuration elements to the people who will do the actual configuration work.</span></span> <span data-ttu-id="0baff-175">我们建议你使用图表和关联的参考体系结构来规划你的部署。</span><span class="sxs-lookup"><span data-stu-id="0baff-175">We recommend that you use the diagrams and associated reference architectures to plan your deployment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

