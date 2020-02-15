---
title: 规划 Lync Server 和 Office 通信服务器联合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22c94254921e3aa1cde8d93998f8fe5bf122ac92
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a><span data-ttu-id="37137-102">规划 Lync Server 2013 和 Office 通信服务器联盟</span><span class="sxs-lookup"><span data-stu-id="37137-102">Planning for Lync Server 2013 and Office Communications Server federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37137-103">_**上次修改的主题：** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="37137-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="37137-104">Microsoft Lync Server 2013、Lync Server 2010 和 Office 通信服务器之间的联合支持对等通信和多方通信。</span><span class="sxs-lookup"><span data-stu-id="37137-104">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="37137-105">对等对话可升级为多方会话，从而允许临时会议。</span><span class="sxs-lookup"><span data-stu-id="37137-105">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="37137-106">可以安排会议（即 Web 会议或音频/视频会议）以包含您组织内的联系人以及您的联盟合作伙伴内的联系人。</span><span class="sxs-lookup"><span data-stu-id="37137-106">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="37137-107">联合身份验证首次出现在 Microsoft Office Live 通信服务器2005中，并支持一种联合联合，即直接联盟。</span><span class="sxs-lookup"><span data-stu-id="37137-107">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="37137-108">直接联盟需要您知道联盟伙伴的会话初始协议（SIP）域和合作伙伴的边缘服务器的完全限定域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="37137-108">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="37137-109">Live 通信服务器 2005 SP1 引入了其他联合类型，所有必需的域名系统（DNS） SRV 记录都将由联盟伙伴发布，以找到其边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="37137-109">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="37137-110">该版本的术语有：</span><span class="sxs-lookup"><span data-stu-id="37137-110">The terminology for that release was:</span></span>

  - <span data-ttu-id="37137-111">*打开增强联盟*：接受任何 SIP 域名并使用 DNS SRV 查找合作伙伴边缘服务器</span><span class="sxs-lookup"><span data-stu-id="37137-111">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="37137-112">*增强联盟*：将合作伙伴的 SIP 域名配置为组织的联盟伙伴，并使用 DNS SRV 查找合作伙伴边缘服务器</span><span class="sxs-lookup"><span data-stu-id="37137-112">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="37137-113">*直接联盟*：将合作伙伴的 SIP 域名和 FQDN 配置为合作伙伴的边缘服务器</span><span class="sxs-lookup"><span data-stu-id="37137-113">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="37137-114">*服务器允许列表*：接受任何域，使用 DNS SRV 查找承载提供程序或公共即时消息（IM）连接提供程序的边缘服务器</span><span class="sxs-lookup"><span data-stu-id="37137-114">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="37137-115">Microsoft Office 通信服务器2007引入了联合身份验证类型的更新命名，以便更好地定义每个联合类型实际完成的操作：</span><span class="sxs-lookup"><span data-stu-id="37137-115">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="37137-116">开放增强联盟变为*已发现的伙伴域*</span><span class="sxs-lookup"><span data-stu-id="37137-116">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="37137-117">增强联盟变为*允许的伙伴域*</span><span class="sxs-lookup"><span data-stu-id="37137-117">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="37137-118">直接联盟变为*允许的伙伴服务器*</span><span class="sxs-lookup"><span data-stu-id="37137-118">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="37137-119">服务器允许列表变为*宿主提供程序* 和*公共 IM 提供程序*</span><span class="sxs-lookup"><span data-stu-id="37137-119">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="37137-120">Microsoft Lync Server 2010 根据 Microsoft Lync Online 2010 和 Microsoft Office 365 引入了更窄的托管提供程序定义，同时还使其遵守允许的合作伙伴域联合类型定义的相同允许列表。</span><span class="sxs-lookup"><span data-stu-id="37137-120">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="37137-121">启用 Microsoft Lync Server 2013 之间的联盟。 Lync Server 2010 和 Office 通信服务器使用边缘服务器和反向代理来强制实施所定义的规则和允许的合作伙伴域。</span><span class="sxs-lookup"><span data-stu-id="37137-121">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="37137-122">从规划的角度来看，与其他 Lync Server 进行联盟，Office 通信服务器需要满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="37137-122">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="37137-123">在拓扑生成器中启用联盟。</span><span class="sxs-lookup"><span data-stu-id="37137-123">Enable federation in Topology Builder.</span></span> <span data-ttu-id="37137-124">有关详细信息，请参阅部署主题[在 Lync Server 2013 中配置 SIP 联盟、XMPP 联盟和公共即时消息](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)。</span><span class="sxs-lookup"><span data-stu-id="37137-124">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="37137-125">确定您的联盟域发现的要求：</span><span class="sxs-lookup"><span data-stu-id="37137-125">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="37137-126">若要手动配置联盟，您必须具有合作伙伴的边缘服务器和域名（FQDN）的完全限定域名（FQDN），或者在 Lync Server 控制面板、**联合访问和外部访问**（ **SIP 联盟域**）中输入的联机域名。</span><span class="sxs-lookup"><span data-stu-id="37137-126">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="37137-127">创建“新”\*\*\*\* 策略或“编辑”\*\*\*\* 现有策略以通过 FQDN 允许或阻止域。</span><span class="sxs-lookup"><span data-stu-id="37137-127">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="37137-128">如果合作伙伴更改了其边缘服务器的 IP 地址，则联合合作伙伴的边缘服务器的手动配置容易出现故障。</span><span class="sxs-lookup"><span data-stu-id="37137-128">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="37137-129">对于<STRONG>新的 SIP 联盟域</STRONG>，您必须为 Microsoft Lync Online （microsoft Office 365 <STRONG>）提供域名（或 FQDN）</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="37137-129">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="37137-130">对于 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通信服务器，你还必须提供<STRONG>访问边缘服务（FQDN）</STRONG></span><span class="sxs-lookup"><span data-stu-id="37137-130">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="37137-131">对于已发现的合作伙伴联盟（合作伙伴可以在其中发现你的边缘服务器），请在外部 DNS- \_sipfederationtls 中创建一个 SRV 记录。\_tcp.contoso.com –指向边缘服务器的端口5061和主机（A）记录</span><span class="sxs-lookup"><span data-stu-id="37137-131">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="37137-132">如果要在 Windows Phone 或 Apple iPhone、iPad 或其他 Apple 设备上支持 Microsoft Lync 移动客户端，并且使用的是推送通知服务或推送通知服务，则必须规划 _sipfederationtls _tcp。</span><span class="sxs-lookup"><span data-stu-id="37137-132">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="37137-133">&lt;您拥有&gt; Lync 移动客户端的每个 sip 域的 SIP 域 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="37137-133">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="37137-134">Android 和 Nokia Symbian Lync Mobile 不使用推送通知，也不受此要求的制约。</span><span class="sxs-lookup"><span data-stu-id="37137-134">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="37137-135">配置外部用户访问策略以支持联盟域</span><span class="sxs-lookup"><span data-stu-id="37137-135">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="37137-136">开放会话初始协议 (SIP)、Web 会议和音频/视频会议的防火墙端口以适应您启用的联盟或联系人。</span><span class="sxs-lookup"><span data-stu-id="37137-136">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="37137-137">有关详细信息，请参阅：[确定外部 A/V 防火墙和端口要求（针对 Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) ）</span><span class="sxs-lookup"><span data-stu-id="37137-137">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="37137-138">以下信息将帮助您定义证书、端口/协议以及与 Microsoft Lync Server 2013 和 Lync Server 2010 联合的 DNS 要求。</span><span class="sxs-lookup"><span data-stu-id="37137-138">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="37137-139">如果计划或部署了 Microsoft Lync Server 2013 边缘服务器，则在规划证书、防火墙和端口/协议要求以及 DNS 要求时，通常是一个直接的转发过程。</span><span class="sxs-lookup"><span data-stu-id="37137-139">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="37137-140">由于联盟是另一个使用现有边缘服务器的功能，因此规划要求通常由边缘服务器规划和部署所满足。</span><span class="sxs-lookup"><span data-stu-id="37137-140">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="37137-141">您应使用下表确定是否已满足您的要求并相应地更改端口/协议和 DNS。</span><span class="sxs-lookup"><span data-stu-id="37137-141">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="37137-142">如果您有一池的边缘服务器，并且要与 Lync Server 2013 或 Lync Server 2010 合作伙伴进行联盟，则可以在边缘服务器的内部边缘和外部面上使用 DNS 负载平衡或硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="37137-142">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="37137-143">如果要与 Office 通信服务器2007或 Office 通信服务器 2007 R2 进行联盟，则硬件负载平衡将在边缘服务器的事件中提供故障转移支持。</span><span class="sxs-lookup"><span data-stu-id="37137-143">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="37137-144">Office 通信服务器2007和 Office 通信服务器 2007 R2 不是 DNS 负载平衡感知。</span><span class="sxs-lookup"><span data-stu-id="37137-144">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="37137-145">合作伙伴边缘服务器将与池中的第一台边缘服务器建立通信，以进行响应。</span><span class="sxs-lookup"><span data-stu-id="37137-145">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="37137-146">如果该边缘服务器出现故障，通信不会自动进行故障转移。</span><span class="sxs-lookup"><span data-stu-id="37137-146">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="37137-147">证书要求通常通过规划所选边缘服务器或池边缘服务器计划的证书来满足。</span><span class="sxs-lookup"><span data-stu-id="37137-147">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="37137-148">本部分内容</span><span class="sxs-lookup"><span data-stu-id="37137-148">In This Section</span></span>

  - [<span data-ttu-id="37137-149">Lync Server 2013 中的证书摘要-SIP、XMPP 联合身份验证和公共即时消息</span><span class="sxs-lookup"><span data-stu-id="37137-149">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="37137-150">Lync Server 2013 中的端口摘要-SIP、XMPP 联合身份验证和公共即时消息</span><span class="sxs-lookup"><span data-stu-id="37137-150">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="37137-151">Lync Server 2013 中的 DNS 摘要-SIP、XMPP 联合身份验证和公共即时消息</span><span class="sxs-lookup"><span data-stu-id="37137-151">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="37137-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37137-152">See Also</span></span>


[<span data-ttu-id="37137-153">在 Lync Server 2013 中配置用于控制联合用户访问的策略</span><span class="sxs-lookup"><span data-stu-id="37137-153">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="37137-154">Lync Server 2013 中的外部用户访问方案</span><span class="sxs-lookup"><span data-stu-id="37137-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="37137-155">确定 Lync Server 2013 的外部 A/V 防火墙和端口要求</span><span class="sxs-lookup"><span data-stu-id="37137-155">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="37137-156">确定 Lync Server 2013 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="37137-156">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="37137-157">在 Lync Server 2013 中管理您的组织的访问边缘配置</span><span class="sxs-lookup"><span data-stu-id="37137-157">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="37137-158">在 Lync Server 2013 中管理组织的 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="37137-158">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="37137-159">在 Lync Server 2013 中管理组织的 SIP 联合提供程序</span><span class="sxs-lookup"><span data-stu-id="37137-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

