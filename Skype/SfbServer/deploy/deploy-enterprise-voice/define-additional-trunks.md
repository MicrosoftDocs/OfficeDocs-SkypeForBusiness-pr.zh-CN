---
title: 在 Skype for Business Server 2015 拓扑生成器中定义其他中继
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 摘要： 了解如何定义中介服务器之间的网关等其他干线在拓扑生成器在 Skype 业务服务器 2015年。
ms.openlocfilehash: 67d378a794ed6a80b5721f9eb2e9e988ee4db048
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server-2015"></a><span data-ttu-id="c3282-103">在 Skype for Business Server 2015 拓扑生成器中定义其他中继</span><span class="sxs-lookup"><span data-stu-id="c3282-103">Define additional trunks in Topology Builder in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c3282-104">**摘要：**了解如何定义中介服务器之间的网关等其他干线在拓扑生成器在 Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="c3282-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c3282-105">请按照以下步骤定义的可与中介服务器关联对等其他干线。</span><span class="sxs-lookup"><span data-stu-id="c3282-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="c3282-106">对等方提供用户启用企业语音连接到公共的交换电话网络 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="c3282-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="c3282-107">对等方可以是用于 Internet 电话服务提供商 (ITSP) 的 PSTN 网关、IP-PBX 或会话边界控制器 (SBC)。</span><span class="sxs-lookup"><span data-stu-id="c3282-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="c3282-108">主干是中介服务器和网关之间的逻辑连接。</span><span class="sxs-lookup"><span data-stu-id="c3282-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c3282-109">本主题假定您已经安装的 PSTN 网关和根中继线与至少一个按顺序排列或独立中介服务器或池的所述[定义业务服务器 2015年的 Skype 在拓扑生成器中的网关](define-a-gateway.md)部署文档中。</span><span class="sxs-lookup"><span data-stu-id="c3282-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server 2015](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="c3282-110">若要定义中介服务器之间的网关等其他干线</span><span class="sxs-lookup"><span data-stu-id="c3282-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="c3282-111">起始拓扑生成器中： 单击**开始**，单击**所有程序**、 都单击**业务服务器 2015年的 Skype**，然后都单击**Skype 业务服务器 2015Topology 生成器**。</span><span class="sxs-lookup"><span data-stu-id="c3282-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="c3282-112">在 Skype 业务服务器**共享组件**，在站点名称，**中继**节点中，用鼠标右键单击，然后单击**新干线**。</span><span class="sxs-lookup"><span data-stu-id="c3282-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
    3. <span data-ttu-id="c3282-p102">在“定义新的 Trunk”****中，指定唯一标识中继的友好名称。您不得有两个具有相同名称的中继。</span><span class="sxs-lookup"><span data-stu-id="c3282-p102">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk. You cannot have two trunks with the same name.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c3282-115">如果您指定传输层安全 (TLS) 作为传输类型，则必须指定 FQDN 而不是中介服务器的对等方的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c3282-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="c3282-116">在“关联的 PSTN 网关”****下，选择 PSTN 对等网关以与此中继相关联。</span><span class="sxs-lookup"><span data-stu-id="c3282-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="c3282-117">在**PSTN 网关的侦听端口**下, 键入侦听端口的对等方 （PSTN 网关，IP PBX 或 SBC） 将接收从中介服务器将与该干线的 SIP 消息。</span><span class="sxs-lookup"><span data-stu-id="c3282-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="c3282-118">对于传输控制协议 (TCP) 来说，默认对等端口为 5066，对于传输层安全性 (TLS)，默认端口为 5067。</span><span class="sxs-lookup"><span data-stu-id="c3282-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="c3282-119">默认高存活力的分支装置的端口为 TCP 的 5081 和 TLS 的 5082。</span><span class="sxs-lookup"><span data-stu-id="c3282-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
6. <span data-ttu-id="c3282-120">在“SIP 传输协议”****下，单击对等方使用的传输类型。</span><span class="sxs-lookup"><span data-stu-id="c3282-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c3282-121">出于安全原因，强烈建议将对等部署到可以使用 TLS 中介服务器。</span><span class="sxs-lookup"><span data-stu-id="c3282-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
7. <span data-ttu-id="c3282-122">在下，**相关中介服务器**，选择要与此对等机器的根主干的中介服务器池</span><span class="sxs-lookup"><span data-stu-id="c3282-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
8. <span data-ttu-id="c3282-123">在**关联的中介服务器端口**下, 键入中介服务器将接收来自对等方的 SIP 消息的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="c3282-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c3282-124">多业务服务器在 Skype 的干线支持，不能与其他干线名称的两种中继配置使用同一**相关中介服务器端口**和**IP/PSTN 网关的侦听端口**</span><span class="sxs-lookup"><span data-stu-id="c3282-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="c3282-125">多业务服务器在 Skype 的干线支持，多个 SIP 信号端口可以通信的中介服务器上定义多个对等方。</span><span class="sxs-lookup"><span data-stu-id="c3282-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="c3282-126">当定义中继，**相关中介服务器的端口**号必须在各自的协议所允许的中介服务器的侦听端口的范围内。</span><span class="sxs-lookup"><span data-stu-id="c3282-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="c3282-127">此端口范围定义下 Skype 业务服务器和中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="c3282-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="c3282-128">相关的中介服务器池，右键单击并选择**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="c3282-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="c3282-129">在**侦听端口**字段中指定的端口范围。</span><span class="sxs-lookup"><span data-stu-id="c3282-129">Specify the port range in the **Listening ports** field.</span></span>
  
9. <span data-ttu-id="c3282-130">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="c3282-130">Click **OK**.</span></span> 
    

