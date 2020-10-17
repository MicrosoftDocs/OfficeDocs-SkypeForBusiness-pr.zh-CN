---
title: Lync Server 2013： MPLS 网络上的呼叫允许控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on an MPLS network
ms:assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398168(v=OCS.15)
ms:contentKeyID: 48183387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efed0826aa35a557628dd64bfdcea9bc22ced28a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535175"
---
# <a name="call-admission-control-on-an-mpls-network-with-lync-server-2013"></a><span data-ttu-id="234f8-102">具有 Lync Server 2013 的 MPLS 网络上的呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="234f8-102">Call admission control on an MPLS network with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="234f8-103">_**上次修改的主题：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="234f8-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="234f8-p101">在多协议标签交换 (MPLS) 网络中，所有站点均以全连通的方式连接。也就是说，所有站点都直接连接到 Internet 服务提供商的 MPLS 主干线，并且每个站点都设置了带宽，以用于通过 WAN 链路连接到 MPLS 云。没有控制 IP 路由的网络集线器或中心站点。下图显示了基于 MPLS 技术的简单网络。</span><span class="sxs-lookup"><span data-stu-id="234f8-p101">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="234f8-108">**MPLS 网络示例**</span><span class="sxs-lookup"><span data-stu-id="234f8-108">**Example MPLS network**</span></span>

<span data-ttu-id="234f8-109">![带有 MPLS 的 CAC](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "带有 MPLS 的 CAC")</span><span class="sxs-lookup"><span data-stu-id="234f8-109">![CAC with MPLS](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "CAC with MPLS")</span></span>

<span data-ttu-id="234f8-p102">要在 MPLS 网络中部署呼叫允许控制 (CAC)，需创建代表 MPLS 云的网络区域，以及代表每个 MPLS 分支站点的网络站点。下图说明如何配置代表上图中的示例 MPLS 网络的网络区域和网络站点。之后，总体带宽限制和带宽会话限制将取决于从每个网络站点连接到代表 MPLS 云的网络区域的 WAN 链路容量。</span><span class="sxs-lookup"><span data-stu-id="234f8-p102">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="234f8-113">**MPLS 网络的网络区域和网络站点**</span><span class="sxs-lookup"><span data-stu-id="234f8-113">**Network region and network sites for an MPLS network**</span></span>

<span data-ttu-id="234f8-114">![使用 MPLS 图 (CAC) 的呼叫允许控制](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "使用 MPLS 图 (CAC) 的呼叫允许控制")</span><span class="sxs-lookup"><span data-stu-id="234f8-114">![Call Admission Control (CAC) with MPLS diagram](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Call Admission Control (CAC) with MPLS diagram")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

