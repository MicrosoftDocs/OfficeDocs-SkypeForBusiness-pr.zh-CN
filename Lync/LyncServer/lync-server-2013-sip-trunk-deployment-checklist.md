---
title: Lync Server 2013：SIP 中继部署清单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7854693702f1583ccaeb2ae6d54a1c7cb9bbcbcd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="67458-102">Lync Server 2013 的 SIP 中继部署清单</span><span class="sxs-lookup"><span data-stu-id="67458-102">SIP trunk deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67458-103">_**主题上次修改时间:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="67458-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="67458-104">你和你的服务提供商必须交换有关你的各个 SIP 中继终结点的一些基本连接信息, 你才能部署 SIP 主干。</span><span class="sxs-lookup"><span data-stu-id="67458-104">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="67458-105">获取将连接到的每个 ITSP 网关的以下信息:</span><span class="sxs-lookup"><span data-stu-id="67458-105">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="67458-106">IP 地址</span><span class="sxs-lookup"><span data-stu-id="67458-106">IP address</span></span>

  - <span data-ttu-id="67458-107">完全限定的域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="67458-107">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="67458-108">服务提供商可能要求您连接到多个 ITSP 网关。</span><span class="sxs-lookup"><span data-stu-id="67458-108">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="67458-109">在这种情况下, 必须在池中的每个 ITSP 网关和每个中介服务器之间配置连接。</span><span class="sxs-lookup"><span data-stu-id="67458-109">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="67458-110">您提供给服务提供商的信息取决于 SIP 中继连接类型:</span><span class="sxs-lookup"><span data-stu-id="67458-110">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="67458-111">对于多协议标签交换 (MPLS) 或专用网络连接, 请为 ITSP 提供你的外围网络 (也称为 DMZ、隔离区域和屏蔽子网) 中的路由器的公共可路由 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="67458-111">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="67458-112">验证 ITSP 上的网关或会话边界控制器 (SBC) 是否可以访问此地址。</span><span class="sxs-lookup"><span data-stu-id="67458-112">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="67458-113">还为 ITSP 提供中介服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="67458-113">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="67458-114">对于虚拟专用网络 (VPN) 连接, 请为 ITSP 提供 VPN 服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="67458-114">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="67458-115">证书注意事项</span><span class="sxs-lookup"><span data-stu-id="67458-115">Certificate Considerations</span></span>

<span data-ttu-id="67458-116">若要确定是否需要用于 SIP 中继的证书, 请查看有关协议支持的 ITSP:</span><span class="sxs-lookup"><span data-stu-id="67458-116">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="67458-117">如果你的 ITSP 仅支持传输控制协议 (TCP), 则不需要证书。</span><span class="sxs-lookup"><span data-stu-id="67458-117">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="67458-118">如果你的 ITSP 支持传输层安全 (TLS), 则 ITSP 必须为你提供证书。</span><span class="sxs-lookup"><span data-stu-id="67458-118">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="67458-119">SIP 与实时传输协议 (RTP) 或安全实时传输协议 (SRTP) 结合使用, 这些协议通过 Internet 协议 (VoIP) 呼叫以语音方式管理实际语音数据。</span><span class="sxs-lookup"><span data-stu-id="67458-119">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="67458-120">部署过程</span><span class="sxs-lookup"><span data-stu-id="67458-120">Deployment Process</span></span>

<span data-ttu-id="67458-121">若要实现 SIP 中继连接的 Lync Server 一方, 请按照下列步骤操作:</span><span class="sxs-lookup"><span data-stu-id="67458-121">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="67458-122">使用 Lync Server 拓扑生成器创建和配置 SIP 域拓扑。</span><span class="sxs-lookup"><span data-stu-id="67458-122">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="67458-123">有关详细信息, 请参阅在部署文档中的[Lync Server 2013 的拓扑生成器中定义和配置拓扑](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)。</span><span class="sxs-lookup"><span data-stu-id="67458-123">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="67458-124">使用 Lync Server "控制面板" 为新的 SIP 域配置语音路由。</span><span class="sxs-lookup"><span data-stu-id="67458-124">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="67458-125">有关详细信息, 请参阅部署文档中[Lync Server 2013 中的 "配置中继](lync-server-2013-configuring-trunks.md)"。</span><span class="sxs-lookup"><span data-stu-id="67458-125">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="67458-126">使用**CsPstnOutboundCall** cmdlet 测试连接性。</span><span class="sxs-lookup"><span data-stu-id="67458-126">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="67458-127">有关详细信息, 请参阅 lync server Management Shell 文档或 Lync Server 命令行管理程序的帮助。</span><span class="sxs-lookup"><span data-stu-id="67458-127">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

