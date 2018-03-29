---
title: 在 Skype for Business Server 2015 拓扑生成器中定义网关
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 摘要： 了解如何在拓扑生成器在 Skype 的 PSTN 网关定义为业务服务器 2015年。
ms.openlocfilehash: 7fa7f95fd04cf491dad32b0ab6cc050c5ebb0b0e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server-2015"></a><span data-ttu-id="743ad-103">在 Skype for Business Server 2015 拓扑生成器中定义网关</span><span class="sxs-lookup"><span data-stu-id="743ad-103">Define a gateway in Topology Builder in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="743ad-104">**摘要：**了解如何定义业务服务器 2015年在拓扑生成器在 Skype 的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="743ad-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="743ad-105">请按照以下步骤使用拓扑生成器来定义可以将中介服务器的用户启用了企业语音提供公用交换的电话网 (PSTN) 的连接关联的对等。</span><span class="sxs-lookup"><span data-stu-id="743ad-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="743ad-106">PSTN 网关，IP PBX 或会话边框控制器 (SBC) 的互联网电话服务提供程序 (ITSP) 所通过配置 SIP 中继连接可以是到中介服务器的对等方。</span><span class="sxs-lookup"><span data-stu-id="743ad-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="743ad-107">定义中介服务器的对等方</span><span class="sxs-lookup"><span data-stu-id="743ad-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="743ad-108">起始拓扑生成器中： 单击**开始**，单击**所有程序**、 都单击**业务服务器 2015年的 Skype**，然后都单击**Skype 业务服务器 2015Topology 生成器**。</span><span class="sxs-lookup"><span data-stu-id="743ad-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="743ad-109">在 Skype 业务服务器共享组件，在站点名称， **PSTN 网关**节点中，用鼠标右键单击，然后单击**新的 PSTN 网关**。</span><span class="sxs-lookup"><span data-stu-id="743ad-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="743ad-110">在“定义新的 IP/PSTN 网关”****中，键入对等方的完全限定的域名 (FQDN) 或 IP 地址，然后单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="743ad-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="743ad-111">如果您指定传输层安全 (TLS) 作为传输类型，则必须指定 FQDN 而不是中介服务器的对等方的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="743ad-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="743ad-112">定义新的 PSTN 网关的 IP 地址的侦听模式（IPv4 或 IPv6），然后单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="743ad-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="743ad-113">定义的 PSTN 网关根主干。</span><span class="sxs-lookup"><span data-stu-id="743ad-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="743ad-114">主干是由元组唯一标识一个网关中介服务器之间的逻辑连接。</span><span class="sxs-lookup"><span data-stu-id="743ad-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="743ad-115">{中介服务器 FQDN，中介服务器侦听端口 （TLS 或 TCP）： 网关 IP 和 FQDN，网关监听端口}</span><span class="sxs-lookup"><span data-stu-id="743ad-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="743ad-116">在 PSTN 网关定义在拓扑生成器时，您必须定义已成功添加到您的拓扑的 PSTN 网关根主干。</span><span class="sxs-lookup"><span data-stu-id="743ad-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="743ad-117">在删除关联的 PSTN 网关之前，无法删除根中继。</span><span class="sxs-lookup"><span data-stu-id="743ad-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="743ad-118">在**IP/PSTN 网关的侦听端口**下, 键入网关、 PBX、 或 SBC 将用于将与根主干的 PSTN 网关关联的中介服务器的 SIP 消息的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="743ad-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="743ad-119">（默认情况下，端口可以是 5066 传输控制协议 (TCP) 和 PSTN 网关，PBX 或 SBC 5067 传输层安全 (TLS)。</span><span class="sxs-lookup"><span data-stu-id="743ad-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="743ad-120">高存活力的分支装置在分支站点，默认端口为 TCP 的 5081 和 TLS 的 5082。）</span><span class="sxs-lookup"><span data-stu-id="743ad-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="743ad-121">在“SIP 传输协议”****下，单击对等方使用的传输类型，然后单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="743ad-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="743ad-122">出于安全原因，强烈建议将对等部署到可以使用 TLS 中介服务器。</span><span class="sxs-lookup"><span data-stu-id="743ad-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="743ad-123">下**相关中介服务器**，选择要与此 PSTN 网关根主干的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="743ad-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="743ad-124">在**关联的中介服务器端口**下, 键入 SIP 消息从网关将使用中介服务器的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="743ad-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="743ad-125">使用中的多中继支持 Skype 业务服务器，您可以定义多个 SIP 信号中介服务器与多个 PSTN 网关的通信端口。</span><span class="sxs-lookup"><span data-stu-id="743ad-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="743ad-126">当定义中继，**相关中介服务器端口**必须各自的协议所允许的中介服务器的侦听端口的范围内。</span><span class="sxs-lookup"><span data-stu-id="743ad-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="743ad-127">此端口范围定义下 Skype 业务服务器和中介池。</span><span class="sxs-lookup"><span data-stu-id="743ad-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="743ad-128">中介服务器池感兴趣，用鼠标右键单击并选择**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="743ad-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="743ad-129">在**侦听端口**字段中指定的端口范围。</span><span class="sxs-lookup"><span data-stu-id="743ad-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="743ad-p105">确保您定义的对等方正在运行并使用指定的 FQDN 或 IP 地址。然后单击“完成”****。</span><span class="sxs-lookup"><span data-stu-id="743ad-p105">Be sure that the peer you defined is running and using the FQDN or IP address that you specified. Then click **Finish**.</span></span>
    
11. <span data-ttu-id="743ad-132">右键单击“**Skype for Business Server**”节点，然后单击“**发布拓扑**”。</span><span class="sxs-lookup"><span data-stu-id="743ad-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

