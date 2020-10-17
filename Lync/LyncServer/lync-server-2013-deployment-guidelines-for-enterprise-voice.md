---
title: Lync Server 2013：企业语音的部署指南
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05cde2a845dd6314d8822e6b58445eed5c6a1d19
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531069"
---
# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="573ab-102">Lync Server 2013 中的企业语音部署指南</span><span class="sxs-lookup"><span data-stu-id="573ab-102">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="573ab-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="573ab-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="573ab-104">本主题介绍在计划部署 Lync Server 2013 和企业语音工作负载时需要考虑的先决条件和其他准则。</span><span class="sxs-lookup"><span data-stu-id="573ab-104">This topic describes prerequisites and other guidelines to consider when you are planning to deploy Lync Server 2013 and the Enterprise Voice workload.</span></span>

<div>

## <a name="deployment-prerequisites"></a><span data-ttu-id="573ab-105">部署的先决条件</span><span class="sxs-lookup"><span data-stu-id="573ab-105">Deployment Prerequisites</span></span>

<span data-ttu-id="573ab-106">若要在部署企业语音时获得最佳体验，请确保您的 IT 基础结构、网络和系统满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="573ab-106">For an optimum experience when deploying Enterprise Voice, make sure that your IT infrastructure, network, and systems meet the following prerequisites:</span></span>

  - <span data-ttu-id="573ab-107">在网络上安装并运行 Lync Server 2013 Standard Edition 或 Enterprise Edition。</span><span class="sxs-lookup"><span data-stu-id="573ab-107">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="573ab-108">所有边缘服务器都在外围网络中部署和运行，包括具有访问边缘服务的边缘服务器、A/V 边缘服务、Web 会议边缘服务和反向代理。</span><span class="sxs-lookup"><span data-stu-id="573ab-108">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers with Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="573ab-109">已为 Lync Server 创建并启用了一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="573ab-109">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="573ab-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) 或最新的 service pack 或 Microsoft Exchange Server 2010 已安装。</span><span class="sxs-lookup"><span data-stu-id="573ab-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack, or Microsoft Exchange Server 2010 is installed.</span></span> <span data-ttu-id="573ab-111">在将 Exchange 统一消息 (UM) 与 Lync Server 集成并向客户端终结点提供丰富通知和呼叫日志信息时，需要使用其中一种方式。</span><span class="sxs-lookup"><span data-stu-id="573ab-111">One of these is required for integrating Exchange Unified Messaging (UM) with Lync Server and to provide rich notifications and call log information to client endpoints.</span></span>

  - <span data-ttu-id="573ab-112">为要启用企业语音的每个用户指定、规范化并将其复制到 **msRTCSIP** 属性的唯一主电话号码。</span><span class="sxs-lookup"><span data-stu-id="573ab-112">A unique primary phone number has been designated, normalized, and copied to the **msRTCSIP-line** attribute for each user who is to be enabled for Enterprise Voice.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="573ab-113">Lync Server 支持 e.164 号码和非直接向内拨号 (已) 号码。</span><span class="sxs-lookup"><span data-stu-id="573ab-113">Lync Server supports E.164 numbers and non-Direct Inward Dialing (DID) numbers.</span></span> <span data-ttu-id="573ab-114">未完成的号码可以采用 ". 164"、" <STRONG> &lt; &gt; ext = &lt; &gt; 分机</STRONG>" 或数字字符串的形式表示，要求专用扩展在整个企业中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="573ab-114">Non-DID numbers can be represented in the format <STRONG>&lt;E.164&gt;;ext=&lt;extension&gt;</STRONG> or as a string of digits, with the requirement that the private extension is unique across the enterprise.</span></span> <span data-ttu-id="573ab-115">例如，可以使用 <STRONG>+1425550100;ext=1001</STRONG> 或 <STRONG>1001</STRONG> 表示专用号码 1001。</span><span class="sxs-lookup"><span data-stu-id="573ab-115">For example, a private number of 1001 can be represented as <STRONG>+1425550100;ext=1001</STRONG>, or as <STRONG>1001</STRONG>.</span></span> <span data-ttu-id="573ab-116">使用 <STRONG>1001</STRONG> 表示时，预期此专用号码在整个企业中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="573ab-116">When represented as <STRONG>1001</STRONG>, the expectation is that this private number is unique across the enterprise.</span></span>

    
    </div>

  - <span data-ttu-id="573ab-117">部署企业语音的管理员应是 RTCUniversalServerAdmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="573ab-117">Administrators who deploy Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="573ab-118">至少已成功部署 Office Communicator 2007。</span><span class="sxs-lookup"><span data-stu-id="573ab-118">At a minimum, Office Communicator 2007 is successfully deployed.</span></span> <span data-ttu-id="573ab-119">若要使用此版本中新增的功能，请部署 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="573ab-119">To use features new to this release, Lync 2013 is deployed.</span></span>

  - <span data-ttu-id="573ab-120">使用 Microsoft 或第三方证书颁发机构 (CA) 基础结构，部署并配置了管理密钥基础结构 (MKI)。</span><span class="sxs-lookup"><span data-stu-id="573ab-120">Managed key infrastructure (MKI) is deployed and configured, using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>

  - <span data-ttu-id="573ab-121">安装中介服务器的每台计算机必须：</span><span class="sxs-lookup"><span data-stu-id="573ab-121">Each computer on which you install Mediation Server must be:</span></span>
    
      - <span data-ttu-id="573ab-122">域的成员服务器和 Active Directory 域服务的准备工作。</span><span class="sxs-lookup"><span data-stu-id="573ab-122">A member server of a domain, and prepared for Active Directory Domain Services.</span></span> <span data-ttu-id="573ab-123">有关 Active Directory 域服务的准备过程，请参阅部署文档中的为 [Lync Server 2013 准备 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md) 。</span><span class="sxs-lookup"><span data-stu-id="573ab-123">For Active Directory Domain Services preparation procedures, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="573ab-124">运行以下操作系统之一：</span><span class="sxs-lookup"><span data-stu-id="573ab-124">Running one of the following operating systems:</span></span>
        
          - <span></span>  
            <span data-ttu-id="573ab-125">64 位版本的 Windows Server 2008 Standard 操作系统</span><span class="sxs-lookup"><span data-stu-id="573ab-125">The 64-bit edition of the Windows Server 2008 Standard operating system</span></span>
        
          - <span></span>  
            <span data-ttu-id="573ab-126">64 位版本的 Windows Server 2008 Enterprise 操作系统</span><span class="sxs-lookup"><span data-stu-id="573ab-126">The 64-bit edition of the Windows Server 2008 Enterprise operating system</span></span>

  - <span data-ttu-id="573ab-p105">如果与公用电话交换网 (PSTN) 或专用交换机 (PBX) 的连接采用的是时分多路复用 (TDM) 连接，则有一个或多个 PSTN 网关可供部署。（如果连接使用的是 SIP 中继，则不需要 PSTN 网关。）</span><span class="sxs-lookup"><span data-stu-id="573ab-p105">If the connection to the public switched telephone network (PSTN) or private branch exchange (PBX) is by means of a Time Division Multiplexing (TDM) connection, one or more PSTN gateways are available for deployment. (If the connection is by means of a SIP trunk, a PSTN gateway is not required.)</span></span>

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a><span data-ttu-id="573ab-129">电源、网络或电话服务中断</span><span class="sxs-lookup"><span data-stu-id="573ab-129">Power, Network, or Telephone Service Outages</span></span>

<span data-ttu-id="573ab-130">如果你所在地的电源、网络或电话服务出现中断、中断或其他降级，则语音、即时消息、状态以及 Lync Server 和任何连接到 Lync Server 的设备的其他功能可能无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="573ab-130">If there is an outage, disruption, or other degradation of the power, network, or telephone services at your location, the voice, instant messaging, presence, and other features of Lync Server and any device connected to Lync Server may not work properly.</span></span>

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a><span data-ttu-id="573ab-131">企业语音依赖于服务器可用性以及语音客户端和硬件的可操作性</span><span class="sxs-lookup"><span data-stu-id="573ab-131">Enterprise Voice Depends on Server Availability and Voice Client and Hardware Operability</span></span>

<span data-ttu-id="573ab-132">与 Lync Server 的语音通信取决于服务器软件的可用性以及连接到服务器软件的语音客户端或硬件电话设备是否正常运行。</span><span class="sxs-lookup"><span data-stu-id="573ab-132">Voice communications with Lync Server depend upon the availability of the server software and the proper functioning of the voice clients or the hardware phone devices connecting to the server software.</span></span>

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a><span data-ttu-id="573ab-133">访问紧急服务的其他方式</span><span class="sxs-lookup"><span data-stu-id="573ab-133">Alternative Means of Accessing Emergency Services</span></span>

<span data-ttu-id="573ab-134">对于安装语音客户端的那些位置 (例如，运行 Lync 客户端或 Lync Phone Edition 设备的电脑) ，我们建议您为用户维护用于呼叫紧急服务的备份选项 (例如，在断电、网络连接降级、电话服务中断或可能阻止 Lync Server、Lync 或 Lync Phone Edition 设备的操作的其他问题时，请使用911或 999) 。</span><span class="sxs-lookup"><span data-stu-id="573ab-134">For those locations where you install a voice client (for example, a PC running Lync client or an Lync Phone Edition device), we recommend that you maintain a backup option for users to call emergency services (for example, 911 or 999) in case of a power failure, network connectivity degradation, telephone service outage, or other issue that may inhibit operation of Lync Server, Lync, or Lync Phone Edition devices.</span></span> <span data-ttu-id="573ab-135">此类备用选项可能包括连接到标准公用电话交换网线路的电话或移动电话。</span><span class="sxs-lookup"><span data-stu-id="573ab-135">Such alternative options could include a telephone connected to a standard public switched telephone network line or a cell phone.</span></span>

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a><span data-ttu-id="573ab-136">紧急呼叫和多路电话系统</span><span class="sxs-lookup"><span data-stu-id="573ab-136">Emergency Calls and Multi-Line Telephone Systems</span></span>

<span data-ttu-id="573ab-137">对多路电话系统 (MLTS) 的使用须遵守美国（州或联邦）法律或其他国家/地区的法律，这些法律要求 MLTS 在呼叫者呼叫紧急服务（例如拨打诸如 911 或 999 之类的紧急访问号码）时，为适用的紧急服务机构提供呼叫者的电话号码、分机号和/或物理位置。</span><span class="sxs-lookup"><span data-stu-id="573ab-137">The use of a multiline telephone system (MLTS) may be subject to U.S state or federal laws or the laws of other countries/regions that require the MLTS to provide a caller’s telephone number, extension, and/or physical location to applicable emergency services when a caller is placed to emergency services (for example, when dialing an emergency access number such as 911 or 999).</span></span> <span data-ttu-id="573ab-138">在此版本中，可以将 Lync Server 配置为向紧急服务提供商提供呼叫者的物理位置，如在 [Lync Server 2013 中规划紧急服务 (E9-1-1) 中](lync-server-2013-planning-for-emergency-services-e9-1-1.md)所述。</span><span class="sxs-lookup"><span data-stu-id="573ab-138">In this release, Lync Server can be configured to provide a caller’s physical location to an emergency services provider, as described in [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span> <span data-ttu-id="573ab-139">遵守 MLTS 法律是 Lync Server、Lync 客户端和 Lync Phone Edition 设备的买方的唯一责任。</span><span class="sxs-lookup"><span data-stu-id="573ab-139">Compliance with MLTS laws is the sole responsibility of the purchaser of Lync Server, Lync client, and Lync Phone Edition devices.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

