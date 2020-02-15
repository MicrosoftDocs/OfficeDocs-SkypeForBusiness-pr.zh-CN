---
title: Lync Server 2013：外部用户访问的部署清单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a624a60ba219d7707d1dcbfb060a0df409c6290
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="516a8-102">Lync Server 2013 中的外部用户访问的部署清单</span><span class="sxs-lookup"><span data-stu-id="516a8-102">Deployment checklist for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="516a8-103">_**上次修改的主题：** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="516a8-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="516a8-104">在部署外围网络并实现对外部用户的支持之前，必须已部署 Microsoft Lync Server 2013 内部服务器，包括前端池或 Standard Edition 服务器。</span><span class="sxs-lookup"><span data-stu-id="516a8-104">Before you deploy your perimeter network and implement support for external users, you must already have deployed your Microsoft Lync Server 2013 internal servers, including a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="516a8-105">如果计划在内部网络中部署可选控制器，还应在部署边缘服务器之前部署它们。</span><span class="sxs-lookup"><span data-stu-id="516a8-105">If you plan to deploy the optional Directors in your internal network, you should also deploy them prior to deploying Edge Servers.</span></span> <span data-ttu-id="516a8-106">有关控制器部署过程的详细信息，请参阅规划文档中的[Lync Server 2013 中的 Director 应用场景](lync-server-2013-scenarios-for-the-director.md)。</span><span class="sxs-lookup"><span data-stu-id="516a8-106">For details about the Director deployment process, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

<span data-ttu-id="516a8-107">Microsoft Lync Server 2013 包括便于规划和部署内部服务器和边缘服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="516a8-107">Microsoft Lync Server 2013 includes tools to facilitate planning and deployment of both internal servers and Edge Servers.</span></span> <span data-ttu-id="516a8-108">在完成拓扑后，可将生成的拓扑定义发布到您的生产环境。</span><span class="sxs-lookup"><span data-stu-id="516a8-108">After the topology is completed, publish the resulting topology definition to your production environment.</span></span> <span data-ttu-id="516a8-109">为此，您必须具有 **Domain Admins** 组和 **RTCUniversalServerAdmins** 组的成员身份。</span><span class="sxs-lookup"><span data-stu-id="516a8-109">To do this, you must be a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group.</span></span>

  - <span data-ttu-id="516a8-110">**规划工具**   Office 通信服务器 2007 R2 包含一个规划工具和一个边缘规划工具，可用于帮助引导拓扑设计。</span><span class="sxs-lookup"><span data-stu-id="516a8-110">**Planning Tool**   Office Communications Server 2007 R2 included a Planning Tool and an Edge Planning Tool that you could use to help guide topology design.</span></span> <span data-ttu-id="516a8-111">在 Lync Server 2010 中，这两个工具组合在一起，后者具有其他特性和功能，例如，收集计划的用户计数、语音要求、外部用户访问类型和联合身份验证选项。</span><span class="sxs-lookup"><span data-stu-id="516a8-111">In Lync Server 2010, these two tools were combined into a single Planning Tool that has additional features and functionality, such as collecting planned user count, voice requirements, external user access types, and federation options.</span></span> <span data-ttu-id="516a8-112">另外，您还可以规划基础结构的网络参数，例如 IP 地址、负载平衡器类型和其他外围网络注意事项。</span><span class="sxs-lookup"><span data-stu-id="516a8-112">Additionally, you can plan your infrastructure’s network parameters, such as IP addresses, load balancer types and other perimeter network considerations.</span></span>

  - <span data-ttu-id="516a8-113">**拓扑生成器**   Lync Server 2013 拓扑生成器可帮助你定义拓扑和组件。</span><span class="sxs-lookup"><span data-stu-id="516a8-113">**Topology Builder**   Lync Server 2013 Topology Builder helps you define your topology and components.</span></span> <span data-ttu-id="516a8-114">拓扑生成器是部署运行 Lync Server 2013 的服务器所必需的。</span><span class="sxs-lookup"><span data-stu-id="516a8-114">Topology Builder is essential to deploying servers running Lync Server 2013.</span></span> <span data-ttu-id="516a8-115">拓扑生成器将结果发布到一个中央管理存储区，该存储用于配置组织中运行 Lync Server 2013 的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="516a8-115">Topology Builder publishes the results to a Central Management store that is used to configure all of the servers running Lync Server 2013 in your organization.</span></span> <span data-ttu-id="516a8-116">在不使用拓扑生成器的情况下无法在服务器上安装 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="516a8-116">You cannot install Lync Server 2013 on servers without using Topology Builder.</span></span>

<span data-ttu-id="516a8-117">如果您在规划过程中设计了边缘拓扑，包括运行拓扑生成器以定义边缘拓扑，则可以使用这些结果来启动边缘服务器部署。</span><span class="sxs-lookup"><span data-stu-id="516a8-117">If you designed your edge topology during your planning process, including running Topology Builder to define your edge topology, you can use those results to start your Edge Server deployment.</span></span> <span data-ttu-id="516a8-118">如果您之前未完成建立边缘拓扑或要更改以前指定的信息，则必须先完成运行拓扑生成器，然后再继续执行其他部署步骤。</span><span class="sxs-lookup"><span data-stu-id="516a8-118">If you did not finish building your edge topology earlier or you want to change the information you previously specified, you must finish running Topology Builder before proceeding with other deployment steps.</span></span> <span data-ttu-id="516a8-119">有关如何构建拓扑的详细信息，请参阅[Lync Server 2013 中的外部用户访问应用场景](lync-server-2013-scenarios-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="516a8-119">For details about how to build your topology, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="516a8-120">有关规划工具和拓扑生成器的详细信息，请参阅规划文档中的[开始规划 Lync Server 2013 的规划过程](lync-server-2013-beginning-the-planning-process.md)。</span><span class="sxs-lookup"><span data-stu-id="516a8-120">For details about the Planning Tool and Topology Builder, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<span data-ttu-id="516a8-121">下表概述了边缘服务器部署过程。</span><span class="sxs-lookup"><span data-stu-id="516a8-121">The following table provides an overview of the Edge Server deployment process.</span></span> <span data-ttu-id="516a8-122">若要查看在部署外部用户访问之前必须做出的规划决策，请参阅[Lync Server 2013 中的外部用户访问应用场景](lync-server-2013-scenarios-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="516a8-122">To review the planning decisions that must be made before deploying external user access, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="516a8-123">下表中的信息主要涉及新的部署。</span><span class="sxs-lookup"><span data-stu-id="516a8-123">The information in the following table focuses on a new deployment.</span></span> <span data-ttu-id="516a8-124">如果已在 Lync Server 2010、Office 通信服务器 2007 R2 或 Office 通信服务器2007环境中部署了边缘服务器，请参阅<A href="migration.md">迁移</A>以了解有关迁移到 Lync Server 2013 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="516a8-124">If you have deployed Edge Servers in a Lync Server 2010, Office Communications Server 2007 R2 or Office Communications Server 2007 environment, see the <A href="migration.md">Migration</A> for details about migrating to Lync Server 2013.</span></span> <span data-ttu-id="516a8-125">Office 通信服务器 2007 R2 之前的任何版本都不支持迁移，包括 Office 通信服务器2007、Live 通信服务器2005和 Live 通信服务器2003。</span><span class="sxs-lookup"><span data-stu-id="516a8-125">Migration is not supported from any version prior to Office Communications Server 2007 R2, including Office Communications Server 2007, Live Communications Server 2005, and Live Communications Server 2003.</span></span>



</div>

<span data-ttu-id="516a8-126">为了提高边缘服务器的性能和安全性，同时为了方便部署，在部署外围网络和边缘服务器时，请应用以下最佳做法：</span><span class="sxs-lookup"><span data-stu-id="516a8-126">To enhance Edge Server performance and security, and to facilitate deployment, apply the following best practices when you deploy your perimeter network and Edge Servers:</span></span>

  - <span data-ttu-id="516a8-127">只有在组织内部的 Lync Server 2013 经过测试和验证后，才部署边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="516a8-127">Deploy Edge Servers only after you have tested and verified operation of Lync Server 2013 inside your organization.</span></span>

  - <span data-ttu-id="516a8-p108">我们建议您将边缘服务器部署到工作组中，而不是域中。这样做可以简化安装，并将 Active Directory 域服务 (AD DS) 置于外围网络外面。将 AD DS 置于外围网络中可能会造成严重的安全风险。</span><span class="sxs-lookup"><span data-stu-id="516a8-p108">We recommend that you deploy Edge Servers in a workgroup rather than a domain. Doing so simplifies installation and keeps Active Directory Domain Services (AD DS) out of the perimeter network. Locating AD DS in the perimeter network can present a significant security risk.</span></span>

  - <span data-ttu-id="516a8-p109">支持将边缘服务器加入完全位于外围网络中的域，但不建议这样做。将边缘服务器作为内部域的一部分将影响受信任的网络边界，在此类环境中，Internet 是最不受信任的，外围网络比 Internet 的受信任程度略高，而内部网络是最受信任的。边缘服务器作为域成员将自动成为最受信任网络的一部分，但它却位于受信任程序较低的网络中（外围）。</span><span class="sxs-lookup"><span data-stu-id="516a8-p109">Joining an Edge Server to a domain located entirely in the perimeter network is supported but not recommended. An Edge Server as part of the internal domain violates trusted network boundaries, where the Internet is least trusted, perimeter network is more trusted than the Internet, and the internal network is most trusted. An Edge server as a member of the domain is automatically a part of the most trusted network, but resides in a less trusted network (the perimeter).</span></span>

<div>

## <a name="deployment-process-for-edge-servers"></a><span data-ttu-id="516a8-134">边缘服务器的部署过程</span><span class="sxs-lookup"><span data-stu-id="516a8-134">Deployment Process for Edge Servers</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="516a8-135">阶段</span><span class="sxs-lookup"><span data-stu-id="516a8-135">Phase</span></span></th>
<th><span data-ttu-id="516a8-136">步骤</span><span class="sxs-lookup"><span data-stu-id="516a8-136">Steps</span></span></th>
<th><span data-ttu-id="516a8-137">Permissions</span><span class="sxs-lookup"><span data-stu-id="516a8-137">Permissions</span></span></th>
<th><span data-ttu-id="516a8-138">文档</span><span class="sxs-lookup"><span data-stu-id="516a8-138">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="516a8-139">创建相应的边缘拓扑并确定相应的组件。</span><span class="sxs-lookup"><span data-stu-id="516a8-139">Create the appropriate edge topology and determine the appropriate components.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="516a8-140">运行拓扑生成器以配置边缘服务器设置，并创建和发布拓扑，然后使用 Lync Server 命令行管理程序导出拓扑配置文件。</span><span class="sxs-lookup"><span data-stu-id="516a8-140">Run Topology Builder to configure Edge Server settings and create and publish the topology, and then use Lync Server Management Shell to export the topology configuration file.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="516a8-141"><strong>Domain Admins</strong>组和<strong>RTCUniversalServerAdmins</strong>或<strong>CsAdmins</strong>组</span><span class="sxs-lookup"><span data-stu-id="516a8-141"><strong>Domain Admins</strong> group and <strong>RTCUniversalServerAdmins</strong> or <strong>CsAdmins</strong> group</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="516a8-142">可以使用本地 Users 组成员的帐户定义拓扑，但发布拓扑需要使用 <STRONG>Domain Admins</STRONG> 组和 <STRONG>RTCUniversalServerAdmins</STRONG> 组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="516a8-142">You can define a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group.</span></span>


</div></td>
<td><p><span data-ttu-id="516a8-143">在部署文档的<a href="lync-server-2013-building-an-edge-and-director-topology.md">Lync Server 2013 中构建边缘和控制器拓扑</a></span><span class="sxs-lookup"><span data-stu-id="516a8-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="516a8-144">准备安装。</span><span class="sxs-lookup"><span data-stu-id="516a8-144">Prepare for setup.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="516a8-145">确保满足系统先决条件。</span><span class="sxs-lookup"><span data-stu-id="516a8-145">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="516a8-146">配置每台边缘服务器上面向内部网络接口和面向公共网络接口的 IP 地址（如果使用，则为 IPv4 和 IPv6）。</span><span class="sxs-lookup"><span data-stu-id="516a8-146">Configure IP addresses (IPv4 and IPv6, if used) for both internal and public facing network interfaces on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="516a8-147">配置内部和外部 DNS 记录（IPv4 和 IPv6 的主机 A 和 AAAA），包括配置要部署为边缘服务器的计算机上的 DNS 后缀。</span><span class="sxs-lookup"><span data-stu-id="516a8-147">Configure internal and external DNS records (host A and AAAA for IPv4 and IPv6), including configuring the DNS suffix on the computer to be deployed as an Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="516a8-p110">（可选）创建并安装公共证书。获取证书所需的时间取决于颁发证书的证书颁发机构 (CA)。如果此时不执行该步骤，则必须在安装边缘服务器期间执行。在获取并安装证书之前，无法启动边缘服务器服务。</span><span class="sxs-lookup"><span data-stu-id="516a8-p110">(Optional) Create and install public certificates. The time required to obtain certificates depends on which certification authority (CA) issues the certificate. If you do not perform this step at this point, you must do it during Edge Server installation. The Edge Server services cannot be started until certificates are obtained and installed.</span></span></p></li>
<li><p><span data-ttu-id="516a8-p111">如果部署支持与 Windows Live、AOL 或 Yahoo! 用户通信，则设置对公共 IM 连接的支持。</span><span class="sxs-lookup"><span data-stu-id="516a8-p111">Provision support for public IM connectivity, if your deployment is to support communications with Windows Live, AOL, or Yahoo! users.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="516a8-154">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或更新的协议。</span><span class="sxs-lookup"><span data-stu-id="516a8-154">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="516a8-155">拥有主动许可证的客户将能够继续与 Yahoo！联合联合</span><span class="sxs-lookup"><span data-stu-id="516a8-155">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="516a8-156">信使，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="516a8-156">Messenger until the service shut down date.</span></span> <span data-ttu-id="516a8-157">AOL 和 Yahoo！的生命周期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="516a8-157">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="516a8-158">已宣布。</span><span class="sxs-lookup"><span data-stu-id="516a8-158">has been announced.</span></span> <span data-ttu-id="516a8-159">有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</span><span class="sxs-lookup"><span data-stu-id="516a8-159">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="516a8-160">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="516a8-160">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="516a8-161">Messenger.</span><span class="sxs-lookup"><span data-stu-id="516a8-161">Messenger.</span></span> <span data-ttu-id="516a8-162">Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</span><span class="sxs-lookup"><span data-stu-id="516a8-162">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="516a8-163">Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。</span><span class="sxs-lookup"><span data-stu-id="516a8-163">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="516a8-164">与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="516a8-164">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="516a8-165">Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</span><span class="sxs-lookup"><span data-stu-id="516a8-165">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
<li><p><span data-ttu-id="516a8-166">如果您的部署将使用这些服务，则对 Office 通信服务器2007、Office 通信服务器 2007 R2 和 Lync Server 2010 合作伙伴的 XMPP 和联合支持的预配支持</span><span class="sxs-lookup"><span data-stu-id="516a8-166">Provision support for XMPP and federation support for Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 partners, if your deployment will use these</span></span></p></li>
<li><p><span data-ttu-id="516a8-167">配置防火墙。</span><span class="sxs-lookup"><span data-stu-id="516a8-167">Configure firewalls.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="516a8-168">根据组织需要</span><span class="sxs-lookup"><span data-stu-id="516a8-168">As appropriate to your organization</span></span></p></td>
<td><p><span data-ttu-id="516a8-169">准备在部署文档中为<a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Lync Server 2013 在外围网络中安装服务器</a></span><span class="sxs-lookup"><span data-stu-id="516a8-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="516a8-170">安装反向代理。</span><span class="sxs-lookup"><span data-stu-id="516a8-170">Set up reverse proxy.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="516a8-171">在外围网络中设置反向代理（例如，对于 Microsoft Forefront 威胁管理网关2010或 Microsoft Internet Security and 加速（ISA） Server，使用 Service Pack 1），获取必要的公共证书，并配置反向代理服务器上的 web 发布规则。</span><span class="sxs-lookup"><span data-stu-id="516a8-171">Set up the reverse proxy (for example, for Microsoft Forefront Threat Management Gateway 2010 or Microsoft Internet Security and Acceleration (ISA) Server with Service Pack 1) in the perimeter network, obtain the necessary public certificates, and configure the web publishing rules on the reverse proxy server.</span></span></p>
<p><span data-ttu-id="516a8-172">如果您制定了移动计划并且要在前端池或 Standard Edition Server 上部署移动服务，请准备反向代理以提供移动服务。</span><span class="sxs-lookup"><span data-stu-id="516a8-172">Prepare the reverse proxy for Mobility services if you have planned for Mobility and are deploying the Mobility services on the Front End pool or Standard Edition server.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="516a8-173"><strong>Administrators</strong> 组或反向代理管理员</span><span class="sxs-lookup"><span data-stu-id="516a8-173"><strong>Administrators</strong> group or Reverse Proxy administrator</span></span></p></td>
<td><p><span data-ttu-id="516a8-174">在部署文档中<a href="lync-server-2013-setting-up-reverse-proxy-servers.md">为 Lync Server 2013 设置反向代理服务器</a></span><span class="sxs-lookup"><span data-stu-id="516a8-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="516a8-175">安装控制器（可选）。</span><span class="sxs-lookup"><span data-stu-id="516a8-175">Setup a Director (optional).</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="516a8-176">（可选）在内部网络中安装并配置一个或多个控制器。</span><span class="sxs-lookup"><span data-stu-id="516a8-176">(Optional) Install and configure one or more Directors in the internal network.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="516a8-177"><strong>Administrators</strong> 组</span><span class="sxs-lookup"><span data-stu-id="516a8-177"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="516a8-178">在部署文档的<a href="lync-server-2013-setting-up-the-director.md">Lync Server 2013 中设置控制器</a></span><span class="sxs-lookup"><span data-stu-id="516a8-178"><a href="lync-server-2013-setting-up-the-director.md">Setting up the Director in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="516a8-179">安装边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="516a8-179">Set up Edge Servers.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="516a8-180">安装系统必备软件。</span><span class="sxs-lookup"><span data-stu-id="516a8-180">Install prerequisite software.</span></span></p></li>
<li><p><span data-ttu-id="516a8-181">将导出的拓扑配置文件传输到每台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="516a8-181">Transport the exported topology configuration file to each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="516a8-182">在每台边缘服务器上安装 Lync Server 2013 软件。</span><span class="sxs-lookup"><span data-stu-id="516a8-182">Install the Lync Server 2013 software on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="516a8-183">配置边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="516a8-183">Configure the Edge Servers.</span></span></p></li>
<li><p><span data-ttu-id="516a8-184">为每台边缘服务器请求并安装证书。</span><span class="sxs-lookup"><span data-stu-id="516a8-184">Request and install certificates for each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="516a8-185">启动边缘服务器服务。</span><span class="sxs-lookup"><span data-stu-id="516a8-185">Start the Edge Server services.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="516a8-186"><strong>Administrators</strong> 组</span><span class="sxs-lookup"><span data-stu-id="516a8-186"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="516a8-187">在部署文档中<a href="lync-server-2013-setting-up-edge-servers.md">设置 Lync Server 2013 中的边缘服务器</a></span><span class="sxs-lookup"><span data-stu-id="516a8-187"><a href="lync-server-2013-setting-up-edge-servers.md">Setting up Edge Servers in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="516a8-188">配置外部用户访问部署。</span><span class="sxs-lookup"><span data-stu-id="516a8-188">Configure deployment for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="516a8-189">使用 Lync Server 控制面板配置对以下各项（如果适用）的支持：</span><span class="sxs-lookup"><span data-stu-id="516a8-189">Use the Lync Server Control Panel to configure support for each of the following (as applicable):</span></span></p>
<ul>
<li><p><span data-ttu-id="516a8-190">媒体中继</span><span class="sxs-lookup"><span data-stu-id="516a8-190">Media relay</span></span></p></li>
<li><p><span data-ttu-id="516a8-191">联盟路由</span><span class="sxs-lookup"><span data-stu-id="516a8-191">Federation route</span></span></p></li>
<li><p><span data-ttu-id="516a8-192">远程用户访问</span><span class="sxs-lookup"><span data-stu-id="516a8-192">Remote user access</span></span></p></li>
<li><p><span data-ttu-id="516a8-193">与 Lync Server、Office 通信服务器和实时通信服务器的联盟</span><span class="sxs-lookup"><span data-stu-id="516a8-193">Federation with Lync Server, Office Communications Server and Live Communications Server</span></span></p></li>
<li><p><span data-ttu-id="516a8-194">公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="516a8-194">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="516a8-195">XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="516a8-195">XMPP federation</span></span></p></li>
<li><p><span data-ttu-id="516a8-196">匿名用户</span><span class="sxs-lookup"><span data-stu-id="516a8-196">Anonymous users</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="516a8-197">为实现远程用户访问、联盟、公共 IM 连接、XMPP 和匿名用户支持配置用户帐户（如果适用）</span><span class="sxs-lookup"><span data-stu-id="516a8-197">Configure user accounts for remote user access, federation, public IM connectivity, XMPP and anonymous user support (as applicable)</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="516a8-198"><strong>RTCUniversalServerAdmins</strong> 组或分配给 <strong>CSAdministrator</strong> 角色的用户帐户</span><span class="sxs-lookup"><span data-stu-id="516a8-198"><strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p></td>
<td><p><span data-ttu-id="516a8-199">在部署文档中<a href="lync-server-2013-configuring-support-for-external-user-access.md">配置对 Lync Server 2013 中的外部用户访问的支持</a></span><span class="sxs-lookup"><span data-stu-id="516a8-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="516a8-200">验证边缘服务器配置。</span><span class="sxs-lookup"><span data-stu-id="516a8-200">Verify your Edge Server configuration.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="516a8-201">验证服务器连接和从内部服务器复制的配置数据。</span><span class="sxs-lookup"><span data-stu-id="516a8-201">Verify server connectivity and replication of configuration data from internal servers.</span></span></p></li>
<li><p><span data-ttu-id="516a8-202">根据您的部署，验证外部用户（包括远程用户、联盟域中的用户、公共 IM 用户和匿名用户）能否进行连接。</span><span class="sxs-lookup"><span data-stu-id="516a8-202">Verify that external users can connect, including remote users, users in federated domains, public IM users, and anonymous users, as appropriate to your deployment.</span></span></p></li>
<li><p><span data-ttu-id="516a8-203">使用 Lync Server 远程连接分析器验证配置和通信<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span><span class="sxs-lookup"><span data-stu-id="516a8-203">Verify configuration and communication using the Lync Server Remote Connectivity Analyzer <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span></span></p></li>
<li><p><span data-ttu-id="516a8-204">解决配置和通信难题</span><span class="sxs-lookup"><span data-stu-id="516a8-204">Troubleshoot configuration and communication difficulties</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="516a8-205">对于复制验证，<strong>RTCUniversalServerAdmins</strong> 组或分配给 <strong>CSAdministrator</strong> 角色的用户帐户</span><span class="sxs-lookup"><span data-stu-id="516a8-205">For verification of replication, <strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p>
<p><span data-ttu-id="516a8-206">对于用户连接验证，支持的各种类型的外部用户访问的用户</span><span class="sxs-lookup"><span data-stu-id="516a8-206">For verification of user connectivity, a user for each type of external user access that you support</span></span></p>
<p><span data-ttu-id="516a8-207">远程用户</span><span class="sxs-lookup"><span data-stu-id="516a8-207">Remote users</span></span></p></td>
<td><p><span data-ttu-id="516a8-208">在部署文档中<a href="lync-server-2013-verifying-your-edge-deployment.md">验证 Lync Server 2013 中的边缘部署</a></span><span class="sxs-lookup"><span data-stu-id="516a8-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

