---
title: 为业务服务器中 Skype 的拓扑生成器中定义其他中继
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 摘要： 了解如何为业务服务器中 Skype 的拓扑生成器中定义其他中继的中介服务器和对等网关之间。
ms.openlocfilehash: 874d32053f4c3d91f16818bd34dc11806de8692c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223160"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="283d6-103">为业务服务器中 Skype 的拓扑生成器中定义其他中继</span><span class="sxs-lookup"><span data-stu-id="283d6-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="283d6-104">**摘要：** 了解如何为业务服务器中 Skype 的拓扑生成器中定义其他中继的中介服务器和对等网关之间。</span><span class="sxs-lookup"><span data-stu-id="283d6-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="283d6-105">按照以下步骤来定义其他中继到可与中介服务器关联的对等方。</span><span class="sxs-lookup"><span data-stu-id="283d6-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="283d6-106">对等方提供连接到公共公用电话交换网 (PSTN) 启用了企业语音的用户。</span><span class="sxs-lookup"><span data-stu-id="283d6-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="283d6-107">对等方可以是用于 Internet 电话服务提供商 (ITSP) 的 PSTN 网关、IP-PBX 或会话边界控制器 (SBC)。</span><span class="sxs-lookup"><span data-stu-id="283d6-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="283d6-108">中继是中介服务器和网关之间的逻辑连接。</span><span class="sxs-lookup"><span data-stu-id="283d6-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="283d6-109">本主题假定您具有安装 PSTN 网关和根 trunk 与至少一个并置或独立中介服务器或池的如部署文档中所述[定义拓扑生成器中的业务服务器 Skype 的网关](define-a-gateway.md)。</span><span class="sxs-lookup"><span data-stu-id="283d6-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="283d6-110">若要定义其他中继的中介服务器和对等网关之间</span><span class="sxs-lookup"><span data-stu-id="283d6-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="283d6-111">启动拓扑生成器： 单击**开始**，单击**所有程序**、 都单击**业务服务器 2015年的 Skype**，，然后都单击**业务 Server 2015Topology 生成器的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="283d6-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="283d6-112">下 Skype 业务服务器**共享组件**，在您网站的名称，右键单击**Trunk**节点，然后单击**新建 Trunk**。</span><span class="sxs-lookup"><span data-stu-id="283d6-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="283d6-113">在“定义新的 Trunk”\*\*\*\* 中，指定唯一标识中继的友好名称。</span><span class="sxs-lookup"><span data-stu-id="283d6-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="283d6-114">您不得有两个具有相同名称的中继。</span><span class="sxs-lookup"><span data-stu-id="283d6-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="283d6-115">如果您作为传输类型指定传输层安全性 (TLS)，则必须指定而不是中介服务器的对等的 IP 地址的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="283d6-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="283d6-116">在“关联的 PSTN 网关”\*\*\*\* 下，选择 PSTN 对等网关以与此中继相关联。</span><span class="sxs-lookup"><span data-stu-id="283d6-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="283d6-117">在**PSTN 网关的侦听端口**框中，键入侦听端口的对等方 （PSTN 网关、 IP-PBX 或 SBC） 将从要与此中继相关联的中介服务器接收 SIP 消息。</span><span class="sxs-lookup"><span data-stu-id="283d6-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="283d6-118">对于传输控制协议 (TCP) 来说，默认对等端口为 5066，对于传输层安全性 (TLS)，默认端口为 5067。</span><span class="sxs-lookup"><span data-stu-id="283d6-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="283d6-119">默认 Survivable Branch Appliance 端口是 5081 tcp 和 tls 5082。</span><span class="sxs-lookup"><span data-stu-id="283d6-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="283d6-120">在“SIP 传输协议”\*\*\*\* 下，单击对等方使用的传输类型。</span><span class="sxs-lookup"><span data-stu-id="283d6-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="283d6-121">出于安全考虑，强烈建议您将对等部署到中介服务器可以使用 TLS 的。</span><span class="sxs-lookup"><span data-stu-id="283d6-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="283d6-122">**关联的中介服务器**下，选择要与此对等方的根中继关联的中介服务器池</span><span class="sxs-lookup"><span data-stu-id="283d6-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="283d6-123">在**关联的中介服务器端口**框中，键入中介服务器，将从对等方接收 SIP 消息的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="283d6-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="283d6-124">使用多个业务服务器中 Skype 的中继支持，具有不同中继名称的两个中继无法配置具有同一**关联的中介服务器端口**和**IP/PSTN 网关的侦听端口**</span><span class="sxs-lookup"><span data-stu-id="283d6-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="283d6-125">使用多个业务服务器中 Skype 的中继支持，多个 SIP 信号端口可用于通信的中介服务器上定义与多个对等方。</span><span class="sxs-lookup"><span data-stu-id="283d6-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="283d6-126">定义中继时,**关联的中介服务器端口**号必须在各自的协议允许中介服务器的侦听端口的范围内。</span><span class="sxs-lookup"><span data-stu-id="283d6-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="283d6-127">此端口范围为业务服务器和中介服务器池定义 Skype 下。</span><span class="sxs-lookup"><span data-stu-id="283d6-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="283d6-128">右键单击相关的中介服务器池，然后选择**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="283d6-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="283d6-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="283d6-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="283d6-130">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="283d6-130">Click **OK**.</span></span> 
    

