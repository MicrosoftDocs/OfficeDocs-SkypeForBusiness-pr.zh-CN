---
title: Lync Server 2013： SIP 中继部署清单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08beaff401b8f261d311ad0d05a07f5221131864
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="04fd6-102">Lync Server 2013 的 SIP 中继部署清单</span><span class="sxs-lookup"><span data-stu-id="04fd6-102">SIP trunk deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04fd6-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="04fd6-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="04fd6-104">您和服务提供商必须先交换有关各自 SIP 中继终结点的一些基本连接信息，然后才能部署 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="04fd6-104">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="04fd6-105">为您将连接到的每个 ITSP 网关获取以下信息：</span><span class="sxs-lookup"><span data-stu-id="04fd6-105">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="04fd6-106">IP 地址</span><span class="sxs-lookup"><span data-stu-id="04fd6-106">IP address</span></span>

  - <span data-ttu-id="04fd6-107">完全限定的域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="04fd6-107">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="04fd6-108">服务提供商可能会要求您连接到多个 ITSP 网关。</span><span class="sxs-lookup"><span data-stu-id="04fd6-108">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="04fd6-109">在这种情况下，必须在池中的每个 ITSP 网关和每个中介服务器之间配置连接。</span><span class="sxs-lookup"><span data-stu-id="04fd6-109">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="04fd6-110">您为服务提供商提供的信息取决于您的 SIP 中继连接类型：</span><span class="sxs-lookup"><span data-stu-id="04fd6-110">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="04fd6-111">对于多协议标签交换（MPLS）或专用网络连接，请为 ITSP 提供外围网络（也称为 DMZ、网络隔离区域和屏蔽子网）中的路由器的可公开路由的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="04fd6-111">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="04fd6-112">验证 ITSP 上的网关或会话边界控制器（SBC）是否可以访问此地址。</span><span class="sxs-lookup"><span data-stu-id="04fd6-112">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="04fd6-113">同时为 ITSP 提供中介服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="04fd6-113">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="04fd6-114">对于虚拟专用网络（VPN）连接，请为 ITSP 提供 VPN 服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="04fd6-114">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="04fd6-115">证书注意事项</span><span class="sxs-lookup"><span data-stu-id="04fd6-115">Certificate Considerations</span></span>

<span data-ttu-id="04fd6-116">若要确定是否需要用于 SIP 中继的证书，请咨询您的 ITSP 关于协议支持：</span><span class="sxs-lookup"><span data-stu-id="04fd6-116">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="04fd6-117">如果您的 ITSP 仅支持传输控制协议（TCP），则不需要证书。</span><span class="sxs-lookup"><span data-stu-id="04fd6-117">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="04fd6-118">如果您的 ITSP 支持传输层安全性（TLS），则 ITSP 必须为你提供证书。</span><span class="sxs-lookup"><span data-stu-id="04fd6-118">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="04fd6-119">SIP 与实时传输协议（RTP）或安全实时传输协议（SRTP）（用于管理通过 Internet 协议（VoIP）呼叫中的实际语音数据）相关的协议协同工作。</span><span class="sxs-lookup"><span data-stu-id="04fd6-119">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="04fd6-120">部署过程</span><span class="sxs-lookup"><span data-stu-id="04fd6-120">Deployment Process</span></span>

<span data-ttu-id="04fd6-121">若要实现 SIP 中继连接的 Lync Server 端，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="04fd6-121">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="04fd6-122">使用 Lync Server 拓扑生成器创建并配置 SIP 域拓扑。</span><span class="sxs-lookup"><span data-stu-id="04fd6-122">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="04fd6-123">有关详细信息，请参阅部署文档中的在[拓扑生成器中定义和配置拓扑，以使用 Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) 。</span><span class="sxs-lookup"><span data-stu-id="04fd6-123">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="04fd6-124">使用 "Lync Server 控制面板" 为新的 SIP 域配置语音路由。</span><span class="sxs-lookup"><span data-stu-id="04fd6-124">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="04fd6-125">有关详细信息，请参阅部署文档中的在[Lync Server 2013 中配置中继](lync-server-2013-configuring-trunks.md)。</span><span class="sxs-lookup"><span data-stu-id="04fd6-125">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="04fd6-126">使用**CsPstnOutboundCall** cmdlet 测试连接性。</span><span class="sxs-lookup"><span data-stu-id="04fd6-126">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="04fd6-127">有关详细信息，请参阅 lync server 命令行管理程序文档或 Lync Server 命令行管理程序帮助。</span><span class="sxs-lookup"><span data-stu-id="04fd6-127">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

