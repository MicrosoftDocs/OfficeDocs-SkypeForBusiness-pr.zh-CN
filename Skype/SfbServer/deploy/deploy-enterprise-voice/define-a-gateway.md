---
title: 在 Skype for Business Server 的拓扑生成器中定义网关
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 摘要：了解如何在 Skype for Business Server 的拓扑生成器中定义 PSTN 网关。
ms.openlocfilehash: 41f5f37d7da23848c8a19d11347183d0c0697532
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767725"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a><span data-ttu-id="f41cc-103">在 Skype for Business Server 的拓扑生成器中定义网关</span><span class="sxs-lookup"><span data-stu-id="f41cc-103">Define a gateway in Topology Builder in Skype for Business Server</span></span>
 
<span data-ttu-id="f41cc-104">**摘要：** 了解如何在 Skype for Business Server 的拓扑生成器中定义 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="f41cc-104">**Summary:** Learn how to define a PSTN gateway in Topology Builder in Skype for Business Server.</span></span>
  
<span data-ttu-id="f41cc-105">请按照以下步骤使用拓扑生成器定义对等，你可以将中介服务器与之关联，以便为已启用企业语音的用户提供与公共交换电话网络（PSTN）的连接。</span><span class="sxs-lookup"><span data-stu-id="f41cc-105">Follow these steps to use Topology Builder to define a peer with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="f41cc-106">对中介服务器的对等可以是 PSTN 网关、IP PBX，或通过配置 SIP 主干连接的 Internet 电话服务提供商（ITSP）的会话边界控制器（SBC）。</span><span class="sxs-lookup"><span data-stu-id="f41cc-106">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>
  
### <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="f41cc-107">定义中介服务器的对等方</span><span class="sxs-lookup"><span data-stu-id="f41cc-107">To define a peer for the Mediation Server</span></span>

1. <span data-ttu-id="f41cc-108">启动拓扑生成器：单击 "**开始**"，单击 "**所有程序**"，单击 "skype for business **server 2015**"，然后单击 "skype for business**服务器2015Topology 生成器**"。</span><span class="sxs-lookup"><span data-stu-id="f41cc-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server 2015Topology Builder**.</span></span>
    
2. <span data-ttu-id="f41cc-109">在 "Skype for Business 服务器" 下，您的网站名称，"共享组件"，右键单击 " **Pstn 网**关" 节点，然后单击 "**新建 pstn 网关**"。</span><span class="sxs-lookup"><span data-stu-id="f41cc-109">Under Skype for Business Server, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
3. <span data-ttu-id="f41cc-110">在“定义新的 IP/PSTN 网关”\*\*\*\* 中，键入对等方的完全限定的域名 (FQDN) 或 IP 地址，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f41cc-110">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f41cc-111">如果将传输层安全性（TLS）指定为传输类型，则必须指定 FQDN，而不是中介服务器对等的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f41cc-111">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span> 
  
4. <span data-ttu-id="f41cc-112">定义新的 PSTN 网关的 IP 地址的侦听模式（IPv4 或 IPv6），然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f41cc-112">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>

5. <span data-ttu-id="f41cc-113">定义 PSTN 网关的 根中继。</span><span class="sxs-lookup"><span data-stu-id="f41cc-113">Define a root trunk for the PSTN gateway.</span></span> <span data-ttu-id="f41cc-114">主干是中介服务器和由元组唯一标识的网关之间的逻辑连接。</span><span class="sxs-lookup"><span data-stu-id="f41cc-114">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="f41cc-115">{中介服务器 FQDN、中介服务器侦听端口（TLS 或 TCP）：网关 IP 和 FQDN，网关侦听端口}</span><span class="sxs-lookup"><span data-stu-id="f41cc-115">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
     - <span data-ttu-id="f41cc-116">在拓扑生成器中定义 PSTN 网关时，必须定义根干线才能成功地将 PSTN 网关添加到拓扑。</span><span class="sxs-lookup"><span data-stu-id="f41cc-116">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
     - <span data-ttu-id="f41cc-117">在删除关联的 PSTN 网关之前，无法删除根中继。</span><span class="sxs-lookup"><span data-stu-id="f41cc-117">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
6. <span data-ttu-id="f41cc-118">在 " **IP/PSTN 网关侦听端口**" 下，键入网关、PBX 或 SBC 将用于来自中介服务器的将与 PSTN 网关根干线关联的 SIP 消息的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="f41cc-118">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="f41cc-119">（默认情况下，在 PSTN 网关、PBX 或 SBC 上，端口是传输控制协议（TCP）和5067的传输层安全性（TLS）的5066。</span><span class="sxs-lookup"><span data-stu-id="f41cc-119">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="f41cc-120">在分支站点的 Survivable 分支设备上，默认端口为适用于 TLS 的 TCP 和5082的默认端口5081。）</span><span class="sxs-lookup"><span data-stu-id="f41cc-120">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>
    
7. <span data-ttu-id="f41cc-121">在“SIP 传输协议”\*\*\*\* 下，单击对等方使用的传输类型，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f41cc-121">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f41cc-122">出于安全原因，强烈建议你将对等部署到可以使用 TLS 的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="f41cc-122">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span> 
  
8. <span data-ttu-id="f41cc-123">在 "**关联的中介服务器**" 下，选择要与此 PSTN 网关的根中继相关联的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="f41cc-123">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>
    
9. <span data-ttu-id="f41cc-124">在 "**关联的中介服务器端口**" 下，键入中介服务器将用于来自网关的 SIP 消息的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="f41cc-124">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f41cc-125">通过 Skype for Business Server 中的多个中继支持，你可以在中介服务器上定义多个 SIP 信号端口，以便与多个 PSTN 网关进行通信。</span><span class="sxs-lookup"><span data-stu-id="f41cc-125">With multiple trunk support in Skype for Business Server, you can define multiple SIP signaling ports on the Mediation Server for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="f41cc-126">定义主干时，关联的**中介服务器端口**必须位于中介服务器允许的各个协议的侦听端口范围内。</span><span class="sxs-lookup"><span data-stu-id="f41cc-126">When defining a trunk, the **Associated Mediation Server port** must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="f41cc-127">此端口范围在 "Skype for Business 服务器" 和 "中介池" 下定义。</span><span class="sxs-lookup"><span data-stu-id="f41cc-127">This port range is defined under Skype for Business Server and Mediation Pools.</span></span> <span data-ttu-id="f41cc-128">右键单击感兴趣的中介服务器池，然后选择 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="f41cc-128">Right-click the Mediation Server pool of interest, and select **Edit Properties**.</span></span> <span data-ttu-id="f41cc-129">Specify the port range in the **Listening ports** field.</span><span class="sxs-lookup"><span data-stu-id="f41cc-129">Specify the port range in the **Listening ports** field.</span></span>
  
10. <span data-ttu-id="f41cc-130">确保您定义的对等方正在运行并使用指定的 FQDN 或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f41cc-130">Be sure that the peer you defined is running and using the FQDN or IP address that you specified.</span></span> <span data-ttu-id="f41cc-131">然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f41cc-131">Then click **Finish**.</span></span>
    
11. <span data-ttu-id="f41cc-132">右键单击“Skype for Business Server”\*\*\*\* 节点，然后单击“发布拓扑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f41cc-132">Right-click the **Skype for Business Server** node, and then click **Publish Topology**.</span></span>
    

