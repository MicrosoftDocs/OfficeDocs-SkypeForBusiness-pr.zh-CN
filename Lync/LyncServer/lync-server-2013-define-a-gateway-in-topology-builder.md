---
title: Lync Server 2013：在拓扑生成器中定义网关
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18f257648ba24930eaab0d314e34178ffd67a0c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="c946c-102">在 Lync Server 2013 的拓扑生成器中定义网关</span><span class="sxs-lookup"><span data-stu-id="c946c-102">Define a gateway in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c946c-103">_**主题上次修改时间：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="c946c-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="c946c-104">请按照以下步骤使用拓扑生成器定义*对等*，你可以将中介服务器与之关联，以便为已启用企业语音的用户提供与公共交换电话网络（PSTN）的连接。</span><span class="sxs-lookup"><span data-stu-id="c946c-104">Follow these steps to use Topology Builder to define a *peer* with which you can associate a Mediation Server to provide connectivity to the public switched telephone network (PSTN) for users enabled for Enterprise Voice.</span></span> <span data-ttu-id="c946c-105">对中介服务器的对等可以是 PSTN 网关、IP PBX，或通过配置 SIP 主干连接的 Internet 电话服务提供商（ITSP）的会话边界控制器（SBC）。</span><span class="sxs-lookup"><span data-stu-id="c946c-105">A peer to the Mediation Server can be a PSTN gateway, an IP-PBX, or a Session Border Controller (SBC) for an Internet Telephony Service Provider (ITSP) to which you connect by configuring a SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c946c-106">本主题假设你已至少在一个中心网站中设置了一个具有 collocated 或独立中介服务器的内部前端池或标准版服务器，如在<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 中定义和配置前端池或标准版服务器</A>以及在部署文档中<A href="lync-server-2013-publish-the-topology.md">发布 lync server 2013 中的拓扑</A>中所述。</span><span class="sxs-lookup"><span data-stu-id="c946c-106">This topic assumes that you have set up at least one internal Front End pool or Standard Edition server in at least one central site with a collocated or stand-alone Mediation Server, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="c946c-107">本主题还假定你已验证你的基础结构是否满足 Lync server 2013 中的<A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">企业语音软件必备</A>条件中所述的先决条件，以及<A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">在 lync server 2013 中的企业语音的安全和配置先决条件</A>。</span><span class="sxs-lookup"><span data-stu-id="c946c-107">This topic also assumes that you have verified that your infrastructure meets the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a><span data-ttu-id="c946c-108">为中介服务器定义对等</span><span class="sxs-lookup"><span data-stu-id="c946c-108">To Define a Peer for the Mediation Server</span></span>

1.  <span data-ttu-id="c946c-109">启动拓扑生成器：单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="c946c-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="c946c-110">在 "Lync Server 2013" 下，您的网站名称，右键单击 " **PSTN 网**关" 节点，然后单击 "**新建 pstn 网关**"。</span><span class="sxs-lookup"><span data-stu-id="c946c-110">Under Lync Server 2013, your site name, Shared Components, right-click the **PSTN Gateways** node, and then click **New PSTN Gateway**.</span></span>
    
    <span data-ttu-id="c946c-111">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span><span class="sxs-lookup"><span data-stu-id="c946c-111">![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")</span></span>

3.  <span data-ttu-id="c946c-112">在“定义新的 IP/PSTN 网关”\*\*\*\* 中，键入对等方的完全限定的域名 (FQDN) 或 IP 地址，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c946c-112">In **Define New IP/PSTN Gateway**, type the fully qualified domain name (FQDN) or IP address of the peer, and click **Next**.</span></span>
    
    <span data-ttu-id="c946c-113">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span><span class="sxs-lookup"><span data-stu-id="c946c-113">![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c946c-114">如果将传输层安全性（TLS）指定为传输类型，则必须指定 FQDN，而不是中介服务器对等的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c946c-114">If you specify Transport Layer Security (TLS) as the transport type, you must specify the FQDN instead of the IP address of the peer of the Mediation Server.</span></span>

    
    </div>

4.  <span data-ttu-id="c946c-115">定义新的 PSTN 网关的 IP 地址的侦听模式（IPv4 或 IPv6），然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c946c-115">Define the listening mode (IPv4 or IPv6) of the IP address of your new PSTN gateway, and click **Next**.</span></span>
    
    <span data-ttu-id="c946c-116">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span><span class="sxs-lookup"><span data-stu-id="c946c-116">![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")</span></span>

5.  <span data-ttu-id="c946c-117">定义 PSTN 网关的 *根中继*。</span><span class="sxs-lookup"><span data-stu-id="c946c-117">Define a *root trunk* for the PSTN gateway.</span></span> <span data-ttu-id="c946c-118">主干是中介服务器和由元组唯一标识的网关之间的逻辑连接。</span><span class="sxs-lookup"><span data-stu-id="c946c-118">A trunk is a logical connection between a Mediation Server and a gateway uniquely identified by the tuple.</span></span>
    
    <span data-ttu-id="c946c-119">{中介服务器 FQDN、中介服务器侦听端口（TLS 或 TCP）：网关 IP 和 FQDN，网关侦听端口}</span><span class="sxs-lookup"><span data-stu-id="c946c-119">{Mediation Server FQDN, Mediation Server listening port (TLS or TCP) : gateway IP and FQDN, gateway listening port}</span></span>
    
      - <span data-ttu-id="c946c-120">在拓扑生成器中定义 PSTN 网关时，必须定义根干线才能成功地将 PSTN 网关添加到拓扑。</span><span class="sxs-lookup"><span data-stu-id="c946c-120">When defining a PSTN gateway in Topology Builder, you must define a root trunk to successfully add the PSTN gateway to your topology.</span></span>
    
      - <span data-ttu-id="c946c-121">在删除关联的 PSTN 网关之前，无法删除根中继。</span><span class="sxs-lookup"><span data-stu-id="c946c-121">The root trunk cannot be removed until the associated PSTN gateway is removed.</span></span>
    
    <span data-ttu-id="c946c-122">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span><span class="sxs-lookup"><span data-stu-id="c946c-122">![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")</span></span>

6.  <span data-ttu-id="c946c-123">在 " **IP/PSTN 网关侦听端口**" 下，键入网关、PBX 或 SBC 将用于来自中介服务器的将与 PSTN 网关根干线关联的 SIP 消息的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="c946c-123">Under **Listening Port for IP/PSTN Gateway**, type the listening port that the gateway, PBX, or SBC will use for SIP messages from the Mediation Server that will be associated with the root trunk of the PSTN gateway.</span></span> <span data-ttu-id="c946c-124">（默认情况下，在 PSTN 网关、PBX 或 SBC 上，端口是传输控制协议（TCP）和5067的传输层安全性（TLS）的5066。</span><span class="sxs-lookup"><span data-stu-id="c946c-124">(By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a PSTN gateway, PBX or SBC.</span></span> <span data-ttu-id="c946c-125">在分支站点的 Survivable 分支设备上，默认端口为适用于 TLS 的 TCP 和5082的默认端口5081。）</span><span class="sxs-lookup"><span data-stu-id="c946c-125">On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.)</span></span>

7.  <span data-ttu-id="c946c-126">在“SIP 传输协议”\*\*\*\* 下，单击对等方使用的传输类型，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c946c-126">Under **SIP Transport Protocol**, click the transport type that the peer uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c946c-127">出于安全原因，强烈建议你将对等部署到可以使用 TLS 的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="c946c-127">For security reasons, we strongly recommend that you deploy a peer to the Mediation Server that can use TLS.</span></span>

    
    </div>

8.  <span data-ttu-id="c946c-128">在 "**关联的中介服务器**" 下，选择要与此 PSTN 网关的根中继相关联的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="c946c-128">Under **Associated Mediation Server**, select the Mediation Server pool to associate with the root trunk of this PSTN Gateway.</span></span>

9.  <span data-ttu-id="c946c-129">在 "**关联的中介服务器端口**" 下，键入中介服务器将用于来自网关的 SIP 消息的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="c946c-129">Under **Associated Mediation Server port**, type the listening port that the Mediation Server will use for SIP messages from the gateway.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c946c-130">通过 Lync Server 2013 中的多个中继支持，可以在中介服务器上定义多个 SIP 信号端口，以便与多个 PSTN 网关进行通信。</span><span class="sxs-lookup"><span data-stu-id="c946c-130">With multiple trunk support in Lync Server 2013, multiple SIP signaling ports can be defined on the Mediation Server to be used for communication with multiple PSTN gateways.</span></span> <span data-ttu-id="c946c-131">定义主干时，关联的<STRONG>中介服务器端口</STRONG>必须位于中介服务器允许的各个协议的侦听端口范围内。</span><span class="sxs-lookup"><span data-stu-id="c946c-131">When defining a trunk, the <STRONG>Associated Mediation Server port</STRONG> must be within the range of the listening ports for the respective protocol allowed by the Mediation Server.</span></span> <span data-ttu-id="c946c-132">此端口范围在 Lync Server 2013 和中介池下定义。</span><span class="sxs-lookup"><span data-stu-id="c946c-132">This port range is defined under Lync Server 2013 and Mediation Pools.</span></span> <span data-ttu-id="c946c-133">右键单击感兴趣的中介服务器池，然后选择 "<STRONG>编辑属性</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="c946c-133">Right-click the Mediation Server pool of interest, and select <STRONG>Edit Properties</STRONG>.</span></span> <span data-ttu-id="c946c-134">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span><span class="sxs-lookup"><span data-stu-id="c946c-134">Specify the port range in the <STRONG>Listening ports</STRONG> field.</span></span>

    
    </div>

10. <span data-ttu-id="c946c-135">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="c946c-135">Click **Finish**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c946c-136">在完成此步骤之前，请确保你定义的对等正在运行，并使用你指定的 FQDN 或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c946c-136">Before you finish this step, be sure that the peer that you defined is running and using the FQDN or IP address that you specified.</span></span>



</div>

<span data-ttu-id="c946c-137">接下来，要将对等添加到拓扑中，请按照在 "部署" 文档中的[Lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)中的过程进行操作。</span><span class="sxs-lookup"><span data-stu-id="c946c-137">Next, to add the peer to the topology, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span> <span data-ttu-id="c946c-138">你必须在每次使用拓扑生成器构建或修改拓扑时发布你的拓扑，以便可以使用数据为运行 Lync Server 的服务器安装文件。</span><span class="sxs-lookup"><span data-stu-id="c946c-138">You must publish your topology each time that you use Topology Builder to build or modify your topology, so that the data can be used to install the files for servers that are running Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c946c-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c946c-139">See Also</span></span>


[<span data-ttu-id="c946c-140">在 Lync Server 2013 中的拓扑生成器中修改主干</span><span class="sxs-lookup"><span data-stu-id="c946c-140">Modify a trunk in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

