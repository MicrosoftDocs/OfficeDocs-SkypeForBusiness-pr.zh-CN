---
title: 在 Skype for Business Server 的拓扑生成器中定义其他中继
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 摘要：了解如何在 Skype for Business Server 的拓扑生成器中定义中介服务器和网关对等方之间的其他中继。
ms.openlocfilehash: 3aab744761420ab631f17e6b56391f1fab120ccf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836992"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="d9343-103">在 Skype for Business Server 的拓扑生成器中定义其他中继</span><span class="sxs-lookup"><span data-stu-id="d9343-103">Define additional trunks in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="d9343-104">**摘要：** 了解如何在 Skype for Business Server 的拓扑生成器中定义中介服务器和对等网关之间的附加中继。</span><span class="sxs-lookup"><span data-stu-id="d9343-104">**Summary:** Learn how to define an additional trunk between a Mediation Server and a gateway peer in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="d9343-105">按照以下步骤定义可以将对等方与中介服务器关联的其他中继。</span><span class="sxs-lookup"><span data-stu-id="d9343-105">Follow these steps to define an additional trunk to which you can associate a peer with a Mediation Server.</span></span> <span data-ttu-id="d9343-106">对等为启用呼叫企业语音 PSTN (公用电话交换网) 。</span><span class="sxs-lookup"><span data-stu-id="d9343-106">A peer provides users enabled for Enterprise Voice with connectivity to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="d9343-107">对等方可以是用于 Internet 电话服务提供商电话服务提供商 (ITSP) 的 PSTN 网关、IP-PBX 或会话边界控制器 (SBC)。</span><span class="sxs-lookup"><span data-stu-id="d9343-107">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span>
  
<span data-ttu-id="d9343-108">中继是中介服务器和网关之间的逻辑连接。</span><span class="sxs-lookup"><span data-stu-id="d9343-108">A trunk is a logical connection between a Mediation Server and a gateway.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d9343-109">本主题假定你已设置 PSTN 网关和根中继，其中至少具有一个并站或独立中介服务器或池，如部署文档中的"在 [Skype for Business Server](define-a-gateway.md) 的拓扑生成器中定义网关"中所述。</span><span class="sxs-lookup"><span data-stu-id="d9343-109">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in [Define a gateway in Topology Builder in Skype for Business Server](define-a-gateway.md) in the Deployment documentation.</span></span>
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="d9343-110">在中介服务器和对等网关之间定义其他中继</span><span class="sxs-lookup"><span data-stu-id="d9343-110">To define an additional trunk between a Mediation Server and a gateway peer</span></span>

1. <span data-ttu-id="d9343-111">启动拓扑生成器 **：单击"** 开始"，**单击"** 所有程序"，再单击 **"Skype for Business Server 2015"，** 然后单击 **"Skype for Business Server 2015Topology Builder"。**</span><span class="sxs-lookup"><span data-stu-id="d9343-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="d9343-112">在 Skype for Business Server 下，站点名称 **、共享组件**、右键单击 **Trunk 节点**，然后单击 **"新建中继"。**</span><span class="sxs-lookup"><span data-stu-id="d9343-112">Under Skype for Business Server, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
   1. <span data-ttu-id="d9343-113">在“定义新的 Trunk”中，指定唯一标识中继的友好名称。</span><span class="sxs-lookup"><span data-stu-id="d9343-113">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="d9343-114">您不得有两个具有相同名称的中继。</span><span class="sxs-lookup"><span data-stu-id="d9343-114">You cannot have two trunks with the same name.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="d9343-115">如果指定传输层安全性 (TLS) 作为传输类型，则必须指定 FQDN，而不是中介服务器的对等方 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d9343-115">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
3. <span data-ttu-id="d9343-116">在“关联的 PSTN 网关”下，选择 PSTN 对等网关以与此中继相关联。</span><span class="sxs-lookup"><span data-stu-id="d9343-116">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    5. <span data-ttu-id="d9343-117">在 **PSTN** 网关的"侦听端口"下，键入对等 (PSTN 网关、IP-PBX 或 SBC) 将接收来自中介服务器（将与此中继关联的 SIP 消息）的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="d9343-117">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="d9343-118">对于传输控制协议 (TCP) 来说，默认对等端口为 5066，对于传输层安全性 (TLS)，默认端口为 5067。</span><span class="sxs-lookup"><span data-stu-id="d9343-118">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="d9343-119">默认的 Survivable Branch Appliance 端口为 5081（TCP）和 5082（对于 TLS）。</span><span class="sxs-lookup"><span data-stu-id="d9343-119">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>
    
4. <span data-ttu-id="d9343-120">在“SIP 传输协议”下，单击对等方使用的传输类型。</span><span class="sxs-lookup"><span data-stu-id="d9343-120">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d9343-121">出于安全考虑，强烈建议您部署可使用 TLS 的对等方中介服务器。</span><span class="sxs-lookup"><span data-stu-id="d9343-121">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
5. <span data-ttu-id="d9343-122">在 **"关联的中介服务器"下**，选择要与此对等方根中继关联的中介服务器池</span><span class="sxs-lookup"><span data-stu-id="d9343-122">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>
    
6. <span data-ttu-id="d9343-123">在 **"关联的中介服务器端口**"下，键入中介服务器将接收来自对等方 SIP 消息的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="d9343-123">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d9343-124">在 Skype for Business Server 中具有多个中继支持时，不能使用相同的关联中介服务器端口和 **IP/PSTN** 网关的侦听端口配置两个中继名称不同的中继</span><span class="sxs-lookup"><span data-stu-id="d9343-124">With multiple trunk support in Skype for Business Server, two trunks with different trunk names cannot be configured with the same **Associated Mediation Server port** and **Listening Port for IP/PSTN gateway**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="d9343-125">通过 Skype for Business Server 中的多个中继支持，可以在中介服务器上定义多个 SIP 信号端口，以与多个对等方通信。</span><span class="sxs-lookup"><span data-stu-id="d9343-125">With multiple trunk support in Skype for Business Server, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="d9343-126">定义中继时，关联的中介 **服务器端口** 号必须位于中介服务器允许的各自协议的侦听端口范围内。</span><span class="sxs-lookup"><span data-stu-id="d9343-126">When defining a trunk, the **Associated Mediation Server port** number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="d9343-127">此端口范围在 Skype for Business Server 和中介服务器池下定义。</span><span class="sxs-lookup"><span data-stu-id="d9343-127">This port range is defined under Skype for Business Server and Mediation Server pools.</span></span> <span data-ttu-id="d9343-128">右键单击相关的中介服务器池，然后选择"**编辑属性"。**</span><span class="sxs-lookup"><span data-stu-id="d9343-128">Right-click the relevant Mediation Server pool, and select **Edit Properties**.</span></span> <span data-ttu-id="d9343-129">在“侦听端口”字段中指定端口范围。</span><span class="sxs-lookup"><span data-stu-id="d9343-129">Specify the port range in the **Listening ports** field.</span></span>
  
7. <span data-ttu-id="d9343-130">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="d9343-130">Click **OK**.</span></span> 
    

