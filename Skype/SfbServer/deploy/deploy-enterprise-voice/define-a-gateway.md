---
title: 为业务服务器中 Skype 的拓扑生成器中定义网关
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 摘要： 了解如何为业务服务器中 Skype 的拓扑生成器中定义 PSTN 网关。
ms.openlocfilehash: 40658bf91513701cc41eb6efdb02e3976672f1f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892865"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="63ec9-103">为业务服务器中 Skype 的拓扑生成器中定义网关</span><span class="sxs-lookup"><span data-stu-id="63ec9-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="63ec9-104">**摘要：** 了解如何为业务服务器中 Skype 的拓扑生成器中定义 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="63ec9-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="63ec9-105">按照以下步骤使用拓扑生成器定义可以与其关联将为用户启用企业语音提供连接到公用电话交换网 (PSTN) 的中介服务器的对等方。</span><span class="sxs-lookup"><span data-stu-id="63ec9-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="63ec9-106">PSTN 网关、 IP PBX 或会话边界控制器 (SBC) 的 Internet 电话服务提供商 (ITSP) 您通过配置 SIP 中继连接，可以是到中介服务器的对等方。</span><span class="sxs-lookup"><span data-stu-id="63ec9-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="63ec9-107">定义中介服务器的对等方</span><span class="sxs-lookup"><span data-stu-id="63ec9-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="63ec9-108">启动拓扑生成器： 单击**开始**，单击**所有程序**、 都单击**业务服务器 2015年的 Skype**，，然后都单击**业务 Server 2015Topology 生成器的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="63ec9-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="63ec9-109">下 Skype 业务服务器共享组件下，在您网站的名称，右键单击**PSTN 网关**节点中，，然后单击**新建 PSTN 网关**。</span><span class="sxs-lookup"><span data-stu-id="63ec9-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="63ec9-110">在“定义新的 IP/PSTN 网关”\*\*\*\* 中，键入对等方的完全限定的域名 (FQDN) 或 IP 地址，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63ec9-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="63ec9-111">如果您作为传输类型指定传输层安全性 (TLS)，则必须指定而不是中介服务器的对等的 IP 地址的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="63ec9-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="63ec9-112">定义新的 PSTN 网关的 IP 地址的侦听模式（IPv4 或 IPv6），然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63ec9-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="63ec9-113">定义 PSTN 网关的 根中继。</span><span class="sxs-lookup"><span data-stu-id="63ec9-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="63ec9-114">中继是中介服务器与由元组唯一标识的网关之间的逻辑连接。</span><span class="sxs-lookup"><span data-stu-id="63ec9-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="63ec9-115">{中介服务器 FQDN，中介服务器侦听端口 （TLS 或 TCP）： 网关 IP 和 FQDN，网关侦听端口}</span><span class="sxs-lookup"><span data-stu-id="63ec9-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="63ec9-116">在拓扑生成器中定义 PSTN 网关时，您必须定义根中继才能成功添加到拓扑的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="63ec9-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="63ec9-117">在删除关联的 PSTN 网关之前，无法删除根中继。</span><span class="sxs-lookup"><span data-stu-id="63ec9-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="63ec9-118">在**IP/PSTN 网关的侦听端口**框中，键入网关、 PBX、 或 SBC 将用于从将与 PSTN 网关的根中继关联的中介服务器的 SIP 消息的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="63ec9-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="63ec9-119">（默认情况下的端口可以是 5066 传输控制协议 (TCP) 和 PSTN 网关，PBX 或 SBC 5067 传输层安全性 (TLS)。</span><span class="sxs-lookup"><span data-stu-id="63ec9-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="63ec9-120">在分支站点为 Survivable Branch Appliance 上的默认端口是 5081 tcp 和 tls 5082。）</span><span class="sxs-lookup"><span data-stu-id="63ec9-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="63ec9-121">在“SIP 传输协议”\*\*\*\* 下，单击对等方使用的传输类型，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63ec9-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="63ec9-122">出于安全考虑，强烈建议您将对等部署到中介服务器可以使用 TLS 的。</span><span class="sxs-lookup"><span data-stu-id="63ec9-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="63ec9-123">**关联的中介服务器**下，选择要与此 PSTN 网关的根中继关联的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="63ec9-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="63ec9-124">在**关联的中介服务器端口**框中，键入中介服务器将用于来自网关的 SIP 消息的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="63ec9-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="63ec9-125">使用多个业务服务器中 Skype 的中继支持，您可以定义多个 SIP 信号中介服务器与多个 PSTN 网关进行通信的端口。</span><span class="sxs-lookup"><span data-stu-id="63ec9-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="63ec9-126">定义中继时,**关联的中介服务器端口**必须在各自的协议允许中介服务器的侦听端口的范围内。</span><span class="sxs-lookup"><span data-stu-id="63ec9-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="63ec9-127">此端口范围为业务服务器和中介池定义 Skype 下。</span><span class="sxs-lookup"><span data-stu-id="63ec9-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="63ec9-128">右键单击感兴趣，中介服务器池，然后选择**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="63ec9-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="63ec9-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="63ec9-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="63ec9-130">确保您定义的对等方正在运行并使用指定的 FQDN 或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="63ec9-130">Be sure that the peer you defined is running and using the FQDN or IP address that you specified.</span></span> <span data-ttu-id="63ec9-131">然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63ec9-131">Then click **Finish**.</span></span>
    
11. <span data-ttu-id="63ec9-132">右键单击“Skype for Business Server”\*\*\*\* 节点，然后单击“发布拓扑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63ec9-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

