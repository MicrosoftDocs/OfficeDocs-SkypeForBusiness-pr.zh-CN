---
title: 在 Skype for Business Server 的拓扑生成器中定义其他中继
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: '摘要: 了解如何在 Skype for Business Server 的拓扑生成器中定义中介服务器与网关对等之间的其他主干。'
ms.openlocfilehash: de6cfd45c9e5f8440fcbcf6b6098a82edda752f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303310"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="b6e2b-103">在 Skype for Business Server 的拓扑生成器中定义其他中继</span><span class="sxs-lookup"><span data-stu-id="b6e2b-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="b6e2b-104">**摘要:** 了解如何在 Skype for Business Server 的拓扑生成器中定义中介服务器与网关对等之间的其他主干。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="b6e2b-105">按照以下步骤定义可将对等与中介服务器相关联的其他主干。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="b6e2b-106">对等用户可通过连接到公共交换电话网络 (PSTN) 来为企业语音启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="b6e2b-107">对等方可以是用于 Internet 电话服务提供商 (ITSP) 的 PSTN 网关、IP-PBX 或会话边界控制器 (SBC)。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="b6e2b-108">主干是中介服务器和网关之间的逻辑连接。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b6e2b-109">本主题假定你已使用至少一个 collocated 或独立中介服务器或池设置 PSTN 网关和根中继, 如在部署文档中的[Skype for Business 服务器的拓扑生成器中定义网关](define-a-gateway.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="b6e2b-110">在中介服务器和网关对等之间定义其他主干</span><span class="sxs-lookup"><span data-stu-id="b6e2b-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="b6e2b-111">启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 "skype for business **server 2015**", 然后单击 "skype for business**服务器2015Topology 生成器**"。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="b6e2b-112">在 "Skype for Business 服务器" 下, 您的网站名称、**共享组件**, 右键单击**中继**节点, 然后单击 "**新建主干**"。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="b6e2b-113">在“定义新的 Trunk”\*\*\*\* 中，指定唯一标识中继的友好名称。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="b6e2b-114">您不得有两个具有相同名称的中继。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="b6e2b-115">如果将传输层安全性 (TLS) 指定为传输类型, 则必须指定 FQDN, 而不是中介服务器对等的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="b6e2b-116">在“关联的 PSTN 网关”\*\*\*\* 下，选择 PSTN 对等网关以与此中继相关联。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="b6e2b-117">在 " **PSTN 网关的侦听端口**" 下, 键入对等 (PSTN 网关、IP PBX 或 SBC) 将从要与该主干关联的中介服务器接收 SIP 消息的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="b6e2b-118">对于传输控制协议 (TCP) 来说，默认对等端口为 5066，对于传输层安全性 (TLS)，默认端口为 5067。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="b6e2b-119">默认的 Survivable 分支装置端口为用于 TLS 的 TCP 和5082的5081。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="b6e2b-120">在“SIP 传输协议”\*\*\*\* 下，单击对等方使用的传输类型。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b6e2b-121">出于安全原因, 强烈建议你将对等部署到可以使用 TLS 的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="b6e2b-122">在 "**关联的中介服务器**" 下, 选择要与此对等方的根中继相关联的中介服务器池</span><span class="sxs-lookup"><span data-stu-id="b6e2b-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="b6e2b-123">在 "**关联的中介服务器端口**" 下, 键入中介服务器将从对等方接收 SIP 消息的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b6e2b-124">利用 Skype for Business 服务器中的多个中继支持, 具有不同主干名称的两个中继不能配置为与**IP/PSTN 网关**相同的**关联中介服务器端口**和侦听端口</span><span class="sxs-lookup"><span data-stu-id="b6e2b-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="b6e2b-125">通过 Skype for Business 服务器中的多个中继支持, 可以在中介服务器上定义多个 SIP 信号端口, 以便与多个对等方通信。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="b6e2b-126">定义主干时, 关联的**中介服务器端口**号必须位于中介服务器允许的各个协议的侦听端口范围内。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="b6e2b-127">此端口范围在 "Skype for Business 服务器" 和 "中介服务器池" 下定义。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="b6e2b-128">右键单击相关的中介服务器池, 然后选择 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="b6e2b-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="b6e2b-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="b6e2b-130">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="b6e2b-130">Click **OK**.</span></span> 
    

