---
title: 'Lync Server 2013: 定义拓扑生成器中的其他中继'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b18d12762566258051d5fe0e7c71921b9fff160c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="d1c9a-102">在 Lync Server 2013 的拓扑生成器中定义其他中继</span><span class="sxs-lookup"><span data-stu-id="d1c9a-102">Define additional trunks in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1c9a-103">_**主题上次修改时间:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="d1c9a-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="d1c9a-104">按照以下步骤使用拓扑生成器定义可将*对等*与中介服务器相关联的其他主干。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-104">Follow these steps to use Topology Builder to define an additional trunk to which you can associate a *peer* with a Mediation Server.</span></span> <span data-ttu-id="d1c9a-105">对等用户可通过连接到公共交换电话网络 (PSTN) 来为企业语音启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-105">A peer provides users enabled for Enterprise Voice with connectivity to the public switched telephone network (PSTN).</span></span> <span data-ttu-id="d1c9a-106">对等方可以是用于 Internet 电话服务提供商 (ITSP) 的 PSTN 网关、IP-PBX 或会话边界控制器 (SBC)。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-106">A peer can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP).</span></span> <span data-ttu-id="d1c9a-107">主干在中介服务器和对等之间定义此连接。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-107">The trunk defines this connection between the Mediation Server and peer.</span></span> <span data-ttu-id="d1c9a-108">可以为每个中介服务器定义多个中继。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-108">Multiple trunks can be defined per Mediation Server.</span></span> <span data-ttu-id="d1c9a-109">中介服务器可以与多个对等方关联。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-109">A Mediation Server can be associated with multiple peers.</span></span>

<span data-ttu-id="d1c9a-110">主干是中介服务器与元组唯一标识的网关之间的逻辑连接:</span><span class="sxs-lookup"><span data-stu-id="d1c9a-110">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple:</span></span>

<span data-ttu-id="d1c9a-111">{中介服务器 FQDN、中介服务器侦听端口 (TLS 或 TCP): 网关 IP 和 FQDN, 网关侦听端口}</span><span class="sxs-lookup"><span data-stu-id="d1c9a-111">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d1c9a-112">本主题假定你已使用至少一个 collocated 或独立中介服务器或池设置 PSTN 网关和根中继, 如在部署文档的<A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013 中的 "拓扑生成器" 中定义的网关</A>中所述。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-112">This topic assumes that you have setup a PSTN gateway and root trunk with at least one collocated or stand-alone Mediation Server or pool as described in <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d1c9a-113">本主题假设你已至少在一个中心网站中设置了一个前端池或标准版服务器, 如在<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 中定义和配置前端池或标准版服务器</A>以及在<A href="lync-server-2013-publish-the-topology.md">lync 中发布拓扑中所述。</A>部署文档中的服务器2013。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-113">This topic assumes that you have set up at least one Front End pool or Standard Edition server in at least one central site, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a><span data-ttu-id="d1c9a-114">在中介服务器和网关对等之间定义其他主干</span><span class="sxs-lookup"><span data-stu-id="d1c9a-114">To Define an additional Trunk between a Mediation Server and a Gateway Peer</span></span>

1.  <span data-ttu-id="d1c9a-115">启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-115">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="d1c9a-116">在 "Lync Server 2013" 下, 选择 "网站名称"、"**共享组件**", 右键单击**中继**节点, 然后单击 "**新建主干**"。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-116">Under Lync Server 2013, your site name, **Shared Components**, right-click the **Trunks** node, and then click **New Trunk**.</span></span>
    
    <span data-ttu-id="d1c9a-117">![Lync Server 拓扑生成器文件结构屏幕](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server 拓扑生成器文件结构屏幕")</span><span class="sxs-lookup"><span data-stu-id="d1c9a-117">![Lync Server Topology Builder file structure screen](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server Topology Builder file structure screen")</span></span>

3.  <span data-ttu-id="d1c9a-118">在“定义新的 Trunk”\*\*\*\* 中，指定唯一标识中继的友好名称。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-118">In **Define New Trunk**, specify a friendly name to uniquely identify the trunk.</span></span> <span data-ttu-id="d1c9a-119">您不得有两个具有相同名称的中继。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-119">You cannot have two trunks with the same name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1c9a-120">如果将传输层安全性 (TLS) 指定为传输类型, 则必须指定 FQDN, 而不是中介服务器对等的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-120">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="d1c9a-121">在“关联的 PSTN 网关”\*\*\*\* 下，选择 PSTN 对等网关以与此中继相关联。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-121">Under **Associated PSTN gateway**, select the PSTN gateway peer to associate with this trunk.</span></span>
    
    <span data-ttu-id="d1c9a-122">用于![干线的 PSTN 网关对等的属性设置]用于(images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "干线的 PSTN 网关对等的属性设置")</span><span class="sxs-lookup"><span data-stu-id="d1c9a-122">![Property settings for PSTN gateway peer for trunk](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Property settings for PSTN gateway peer for trunk")</span></span>

5.  <span data-ttu-id="d1c9a-123">在 " **PSTN 网关的侦听端口**" 下, 键入对等 (PSTN 网关、IP PBX 或 SBC) 将从要与该主干关联的中介服务器接收 SIP 消息的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-123">Under **Listening Port for PSTN gateway**, type the listening port that the peer (PSTN gateway, IP-PBX, or SBC) will receive SIP messages from the Mediation Server that is to be associated with this trunk.</span></span> <span data-ttu-id="d1c9a-124">对于传输控制协议 (TCP) 来说，默认对等端口为 5066，对于传输层安全性 (TLS)，默认端口为 5067。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-124">The default peer ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS).</span></span> <span data-ttu-id="d1c9a-125">默认的 Survivable 分支装置端口为用于 TLS 的 TCP 和5082的5081。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-125">The default Survivable Branch Appliance ports are 5081 for TCP and 5082 for TLS.</span></span>

6.  <span data-ttu-id="d1c9a-126">在“SIP 传输协议”\*\*\*\* 下，单击对等方使用的传输类型。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-126">Under **SIP Transport Protocol**, click the transport type that the peer uses.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1c9a-127">出于安全原因, 强烈建议你将对等部署到可以使用 TLS 的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

7.  <span data-ttu-id="d1c9a-128">在 "**关联的中介服务器**" 下, 选择要与此对等方的根中继相关联的中介服务器池</span><span class="sxs-lookup"><span data-stu-id="d1c9a-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this peer</span></span>

8.  <span data-ttu-id="d1c9a-129">在 "**关联的中介服务器端口**" 下, 键入中介服务器将从对等方接收 SIP 消息的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will receive SIP messages from the peer.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1c9a-130">在 Lync Server 2013 中有多个中继支持, 具有不同中继名称的两个中继不能配置为与<STRONG>IP/PSTN 网关</STRONG>相同的<STRONG>关联中介服务器端口</STRONG>和侦听端口</span><span class="sxs-lookup"><span data-stu-id="d1c9a-130">With multiple trunk support in Lync Server 2013, two trunks with different trunk names cannot be configured with the same <STRONG>Associated Mediation Server port</STRONG> and <STRONG>Listening Port for IP/PSTN gateway</STRONG></span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1c9a-131">在 Lync Server 2013 中有多个中继支持, 可以在中介服务器上定义多个 SIP 信号端口, 以便与多个对等方通信。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-131">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server for communication with multiple peers.</span></span> <span data-ttu-id="d1c9a-132">定义主干时, 关联的<STRONG>中介服务器端口</STRONG>号必须位于中介服务器允许的各个协议的侦听端口范围内。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-132">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> number must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="d1c9a-133">此端口范围在 Lync Server 2013 和中介服务器池下定义。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-133">This port range is defined under Lync Server 2013 and Mediation Server pools.</span></span> <span data-ttu-id="d1c9a-134">右键单击相关的中介服务器池, 然后选择 "<STRONG>编辑属性</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-134">Right-click the relevant Mediation Server pool, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="d1c9a-135">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span><span class="sxs-lookup"><span data-stu-id="d1c9a-135">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

9.  <span data-ttu-id="d1c9a-136">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="d1c9a-136">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d1c9a-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1c9a-137">See Also</span></span>


[<span data-ttu-id="d1c9a-138">在 Lync Server 2013 中的拓扑生成器中修改主干</span><span class="sxs-lookup"><span data-stu-id="d1c9a-138">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

