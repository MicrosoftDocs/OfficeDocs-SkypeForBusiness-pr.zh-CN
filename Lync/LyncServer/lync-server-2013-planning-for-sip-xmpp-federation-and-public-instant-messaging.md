---
title: 规划 SIP、XMPP 联盟和公共即时消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2070d9e977a730b7c667a2c49a7e896d1309eef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="2977d-102">在 Lync Server 2013 中规划 SIP、XMPP 联合身份验证和公共即时消息</span><span class="sxs-lookup"><span data-stu-id="2977d-102">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2977d-103">_**上次修改的主题：** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="2977d-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="2977d-104">可以将边缘服务器配置为允许您的内部和外部用户访问合作伙伴组织或服务的联系人。</span><span class="sxs-lookup"><span data-stu-id="2977d-104">Edge Servers can be configured to allow your internal and external users access to contacts at partner organizations or services.</span></span> <span data-ttu-id="2977d-105">在这些合作伙伴协议已知的情况下，联盟可以将任何或所有以下功能提供给加入伙伴联盟的贵组织中的联系人，或与贵组织联盟的合作伙伴组织中的联系人：</span><span class="sxs-lookup"><span data-stu-id="2977d-105">Federations, as these partner agreements are known, can provide any or all of the following to the contacts in your organization on the partner federation or contacts in the partner federation to yours:</span></span>

  - <span data-ttu-id="2977d-106">即时消息和状态</span><span class="sxs-lookup"><span data-stu-id="2977d-106">Instant messaging and presence</span></span>

  - <span data-ttu-id="2977d-107">协作和会议，例如 Web 会议</span><span class="sxs-lookup"><span data-stu-id="2977d-107">Collaboration and conferencing, for example – Web conferencing</span></span>

  - <span data-ttu-id="2977d-108">音频会议和/或视频会议</span><span class="sxs-lookup"><span data-stu-id="2977d-108">Audio conferencing, video conferencing, or both</span></span>

<span data-ttu-id="2977d-109">在某些情况下，这种通信（例如即时消息（IM）和在 Microsoft Lync Server 2013 和可扩展消息和状态协议（XMPP）联系人之间的状态）是仅支持对等用户，仅支持联合中的联系人。partner.</span><span class="sxs-lookup"><span data-stu-id="2977d-109">In some cases the communication, for example instant messaging (IM) and presence between a Microsoft Lync Server 2013 and an extensible messaging and presence protocol (XMPP) contact, is peer-to-peer only - supporting only you and the contact at the federated partner.</span></span> <span data-ttu-id="2977d-110">在其他情况下，例如 Lync Server、Lync server 2010 to Lync Server 2013 联盟，可以邀请多个参与者加入对话。</span><span class="sxs-lookup"><span data-stu-id="2977d-110">In other cases, such as a Lync Server, Lync Server 2010 to Lync Server 2013 federation, multiple participants can be invited to join into the conversation.</span></span>

<div>

## <a name="lync-server-and-office-communications-server-federation"></a><span data-ttu-id="2977d-111">Lync Server 和 Office 通信服务器联合</span><span class="sxs-lookup"><span data-stu-id="2977d-111">Lync Server and Office Communications Server Federation</span></span>

<span data-ttu-id="2977d-112">Microsoft Lync Server 2013、Lync Server 2010 和 Office 通信服务器之间的联合支持对等通信和多方通信。</span><span class="sxs-lookup"><span data-stu-id="2977d-112">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="2977d-113">对等对话可升级为多方会话，从而允许临时会议。</span><span class="sxs-lookup"><span data-stu-id="2977d-113">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="2977d-114">可以安排会议（即 Web 会议或音频/视频会议）以包含您组织内的联系人以及您的联盟合作伙伴内的联系人。</span><span class="sxs-lookup"><span data-stu-id="2977d-114">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="2977d-115">联合身份验证首次出现在 Microsoft Office Live 通信服务器2005中，并支持一种联合联合，即直接联盟。</span><span class="sxs-lookup"><span data-stu-id="2977d-115">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="2977d-116">直接联盟需要您知道联盟伙伴的会话初始协议（SIP）域和合作伙伴的边缘服务器的完全限定域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="2977d-116">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="2977d-117">Live 通信服务器 2005 SP1 引入了其他联合类型，所有必需的域名系统（DNS） SRV 记录都将由联盟伙伴发布，以找到其边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="2977d-117">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="2977d-118">该版本的术语有：</span><span class="sxs-lookup"><span data-stu-id="2977d-118">The terminology for that release was:</span></span>

  - <span data-ttu-id="2977d-119">*打开增强联盟*：接受任何 SIP 域名并使用 DNS SRV 查找合作伙伴边缘服务器</span><span class="sxs-lookup"><span data-stu-id="2977d-119">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="2977d-120">*增强联盟*：将合作伙伴的 SIP 域名配置为组织的联盟伙伴，并使用 DNS SRV 查找合作伙伴边缘服务器</span><span class="sxs-lookup"><span data-stu-id="2977d-120">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="2977d-121">*直接联盟*：将合作伙伴的 SIP 域名和 FQDN 配置为合作伙伴的边缘服务器</span><span class="sxs-lookup"><span data-stu-id="2977d-121">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="2977d-122">*服务器允许列表*：接受任何域，使用 DNS SRV 查找承载提供程序或公共即时消息（IM）连接提供程序的边缘服务器</span><span class="sxs-lookup"><span data-stu-id="2977d-122">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="2977d-123">Microsoft Office 通信服务器2007引入了联合身份验证类型的更新命名，以便更好地定义每个联合类型实际完成的操作：</span><span class="sxs-lookup"><span data-stu-id="2977d-123">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="2977d-124">开放增强联盟变为*已发现的伙伴域*</span><span class="sxs-lookup"><span data-stu-id="2977d-124">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="2977d-125">增强联盟变为*允许的伙伴域*</span><span class="sxs-lookup"><span data-stu-id="2977d-125">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="2977d-126">直接联盟变为*允许的伙伴服务器*</span><span class="sxs-lookup"><span data-stu-id="2977d-126">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="2977d-127">服务器允许列表变为*宿主提供程序* 和*公共 IM 提供程序*</span><span class="sxs-lookup"><span data-stu-id="2977d-127">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="2977d-128">Microsoft Lync Server 2010 根据 Microsoft Lync Online 2010 和 Microsoft Office 365 引入了更窄的托管提供程序定义，同时还使其遵守允许的合作伙伴域联合类型定义的相同允许列表。</span><span class="sxs-lookup"><span data-stu-id="2977d-128">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="2977d-129">启用 Microsoft Lync Server 2013 之间的联盟。 Lync Server 2010 和 Office 通信服务器使用边缘服务器和反向代理来强制实施所定义的规则和允许的合作伙伴域。</span><span class="sxs-lookup"><span data-stu-id="2977d-129">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="2977d-130">从规划的角度来看，与其他 Lync Server 进行联盟，Office 通信服务器需要满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="2977d-130">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="2977d-131">在拓扑生成器中启用联盟。</span><span class="sxs-lookup"><span data-stu-id="2977d-131">Enable federation in Topology Builder.</span></span> <span data-ttu-id="2977d-132">有关详细信息，请参阅部署主题[在 Lync Server 2013 中配置 SIP 联盟、XMPP 联盟和公共即时消息](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)。</span><span class="sxs-lookup"><span data-stu-id="2977d-132">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="2977d-133">确定您的联盟域发现的要求：</span><span class="sxs-lookup"><span data-stu-id="2977d-133">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="2977d-134">若要手动配置联盟，您必须具有合作伙伴的边缘服务器和域名（FQDN）的完全限定域名（FQDN），或者在 Lync Server 控制面板、**联合访问和外部访问**（ **SIP 联盟域**）中输入的联机域名。</span><span class="sxs-lookup"><span data-stu-id="2977d-134">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="2977d-135">创建“新”\*\*\*\* 策略或“编辑”\*\*\*\* 现有策略以通过 FQDN 允许或阻止域。</span><span class="sxs-lookup"><span data-stu-id="2977d-135">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="2977d-136">如果合作伙伴更改了其边缘服务器的 IP 地址，则联合合作伙伴的边缘服务器的手动配置容易出现故障。</span><span class="sxs-lookup"><span data-stu-id="2977d-136">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="2977d-137">对于<STRONG>新的 SIP 联盟域</STRONG>，您必须为 Microsoft Lync Online （microsoft Office 365 <STRONG>）提供域名（或 FQDN）</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="2977d-137">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="2977d-138">对于 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通信服务器，你还必须提供<STRONG>访问边缘服务（FQDN）</STRONG></span><span class="sxs-lookup"><span data-stu-id="2977d-138">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="2977d-139">对于已发现的合作伙伴联盟（合作伙伴可以在其中发现你的边缘服务器），请在外部 DNS- \_sipfederationtls 中创建一个 SRV 记录。\_tcp.contoso.com –指向边缘服务器的端口5061和主机（A）记录</span><span class="sxs-lookup"><span data-stu-id="2977d-139">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="2977d-140">如果要在 Windows Phone 或 Apple iPhone、iPad 或其他 Apple 设备上支持 Microsoft Lync 移动客户端，并且使用的是推送通知服务或推送通知服务，则必须规划 _sipfederationtls _tcp。</span><span class="sxs-lookup"><span data-stu-id="2977d-140">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="2977d-141">&lt;您拥有&gt; Lync 移动客户端的每个 sip 域的 SIP 域 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="2977d-141">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="2977d-142">Android 和 Nokia Symbian Lync Mobile 不使用推送通知，也不受此要求的制约。</span><span class="sxs-lookup"><span data-stu-id="2977d-142">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="2977d-143">配置外部用户访问策略以支持联盟域</span><span class="sxs-lookup"><span data-stu-id="2977d-143">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="2977d-144">开放会话初始协议 (SIP)、Web 会议和音频/视频会议的防火墙端口以适应您启用的联盟或联系人。</span><span class="sxs-lookup"><span data-stu-id="2977d-144">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="2977d-145">有关详细信息，请参阅：[确定外部 A/V 防火墙和端口要求（针对 Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) ）</span><span class="sxs-lookup"><span data-stu-id="2977d-145">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="2977d-146">以下信息将帮助您定义证书、端口/协议以及与 Microsoft Lync Server 2013 和 Lync Server 2010 联合的 DNS 要求。</span><span class="sxs-lookup"><span data-stu-id="2977d-146">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="2977d-147">如果计划或部署了 Microsoft Lync Server 2013 边缘服务器，则在规划证书、防火墙和端口/协议要求以及 DNS 要求时，通常是一个直接的转发过程。</span><span class="sxs-lookup"><span data-stu-id="2977d-147">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="2977d-148">由于联盟是另一个使用现有边缘服务器的功能，因此规划要求通常由边缘服务器规划和部署所满足。</span><span class="sxs-lookup"><span data-stu-id="2977d-148">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="2977d-149">您应使用下表确定是否已满足您的要求并相应地更改端口/协议和 DNS。</span><span class="sxs-lookup"><span data-stu-id="2977d-149">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="2977d-150">如果您有一池的边缘服务器，并且要与 Lync Server 2013 或 Lync Server 2010 合作伙伴进行联盟，则可以在边缘服务器的内部边缘和外部面上使用 DNS 负载平衡或硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="2977d-150">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="2977d-151">如果要与 Office 通信服务器2007或 Office 通信服务器 2007 R2 进行联盟，则硬件负载平衡将在边缘服务器的事件中提供故障转移支持。</span><span class="sxs-lookup"><span data-stu-id="2977d-151">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="2977d-152">Office 通信服务器2007和 Office 通信服务器 2007 R2 不是 DNS 负载平衡感知。</span><span class="sxs-lookup"><span data-stu-id="2977d-152">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="2977d-153">合作伙伴边缘服务器将与池中的第一台边缘服务器建立通信，以进行响应。</span><span class="sxs-lookup"><span data-stu-id="2977d-153">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="2977d-154">如果该边缘服务器出现故障，通信不会自动进行故障转移。</span><span class="sxs-lookup"><span data-stu-id="2977d-154">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="2977d-155">证书要求通常通过规划所选边缘服务器或池边缘服务器计划的证书来满足。</span><span class="sxs-lookup"><span data-stu-id="2977d-155">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a><span data-ttu-id="2977d-156">公共即时消息连接</span><span class="sxs-lookup"><span data-stu-id="2977d-156">Public Instant Messaging Connectivity</span></span>

<span data-ttu-id="2977d-157">公共即时消息连接是一类联合，配置为允许您的内部和外部 Lync Server 2013 用户从以下任一项添加联系人：</span><span class="sxs-lookup"><span data-stu-id="2977d-157">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="2977d-158">Messenger 联系人</span><span class="sxs-lookup"><span data-stu-id="2977d-158">Messenger contacts</span></span>

  - <span data-ttu-id="2977d-159">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="2977d-159">Yahoo\!</span></span> <span data-ttu-id="2977d-160">contacts</span><span class="sxs-lookup"><span data-stu-id="2977d-160">contacts</span></span>

  - <span data-ttu-id="2977d-161">America Online (AOL) 联系人</span><span class="sxs-lookup"><span data-stu-id="2977d-161">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="2977d-162">从9月1日起，2012，Microsoft Lync 公共 IM 连接用户订阅许可证（PIC USL）不再可用于购买新的或续订的协议。</span><span class="sxs-lookup"><span data-stu-id="2977d-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="2977d-163">拥有主动许可证的客户将能够继续与 Yahoo！联合联合</span><span class="sxs-lookup"><span data-stu-id="2977d-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="2977d-164">信使直到服务关闭日期（仍将决定确切日期，但不早于6月2013）。</span><span class="sxs-lookup"><span data-stu-id="2977d-164">Messenger until the service shutdown date (exact date is still to be decided, but no sooner than June 2013).</span></span></P>
> <LI>
> <P><span data-ttu-id="2977d-165">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每用户、每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="2977d-165">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="2977d-166">Messenger.</span><span class="sxs-lookup"><span data-stu-id="2977d-166">Messenger.</span></span> <span data-ttu-id="2977d-167">Microsoft 提供此服务的能力因 Yahoo！中的支持而异，将不会续订的底层协议。</span><span class="sxs-lookup"><span data-stu-id="2977d-167">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="2977d-168">Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。</span><span class="sxs-lookup"><span data-stu-id="2977d-168">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="2977d-169">与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="2977d-169">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="2977d-170">Skype 联盟将添加到此列表中，使 Lync 用户能够通过即时消息和语音访问数百个人。</span><span class="sxs-lookup"><span data-stu-id="2977d-170">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="2977d-171">此类联盟需要规划以下注意事项：</span><span class="sxs-lookup"><span data-stu-id="2977d-171">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="2977d-172">除了即时消息之外，Windows Live Messenger 用户可以与 Lync Server 2013 用户进行对等音频/视频通信。</span><span class="sxs-lookup"><span data-stu-id="2977d-172">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="2977d-173">您的边缘服务器必须满足特定的端口和协议要求。</span><span class="sxs-lookup"><span data-stu-id="2977d-173">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="2977d-174">有关详细信息，请参阅[确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2977d-174">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="2977d-175">Yahoo 即时消息没有独特的要求，而不是通常在提供联合的典型边缘服务器的规划和部署中使用的要求。</span><span class="sxs-lookup"><span data-stu-id="2977d-175">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="2977d-176">美洲在线要求分配给访问边缘服务的边缘服务器证书具有客户端增强型密钥用法（EKU）。</span><span class="sxs-lookup"><span data-stu-id="2977d-176">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a><span data-ttu-id="2977d-177">可扩展消息传递和状态协议（XMPP）联盟</span><span class="sxs-lookup"><span data-stu-id="2977d-177">Extensible Messaging and Presence Protocol (XMPP) Federation</span></span>

<span data-ttu-id="2977d-178">早期版本的 Lync Server 和 Office 通信服务器提供了可扩展消息和状态协议（XMPP）网关，可将其作为单独的服务器角色进行部署，以允许与 XMPP 部署进行联盟。</span><span class="sxs-lookup"><span data-stu-id="2977d-178">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="2977d-179">在 Microsoft Lync Server 2013 中，可以将 XMPP 功能部署为功能。</span><span class="sxs-lookup"><span data-stu-id="2977d-179">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="2977d-180">XMPP 功能安装在两个部分中：在边缘服务器上运行的 XMPP 代理，以及在前端服务器上运行的 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="2977d-180">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="2977d-181">在[Lync Server 2013 中部署外部用户访问权限](lync-server-2013-deploying-external-user-access.md)中介绍了 XMPP 的部署和配置。通过在防火墙上定义端口和协议规则、配置证书以及添加 DNS 记录，在您计划支持组织中的 XMPP。</span><span class="sxs-lookup"><span data-stu-id="2977d-181">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="2977d-182">本节中的以下主题汇总了为您的部署成功规划 XMPP 联合所需的信息。</span><span class="sxs-lookup"><span data-stu-id="2977d-182">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="2977d-183">Microsoft 对 Lync Server 2013 的 XMPP 功能进行了测试，并支持 Microsoft 实现与 Google 谈话的即时消息联盟。</span><span class="sxs-lookup"><span data-stu-id="2977d-183">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="2977d-184">对于任何其他 XMPP 系统，请联系第三方供应商以验证它们是否支持与 Lync Server 2013 联合，以及任何部署或疑难解答建议。</span><span class="sxs-lookup"><span data-stu-id="2977d-184">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>


> [!IMPORTANT]
> <span data-ttu-id="2977d-185">对于驻留在 survivable 分支设备上的用户，不支持 XMPP 联盟。</span><span class="sxs-lookup"><span data-stu-id="2977d-185">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="2977d-186">这适用于查看状态信息和交换 IM 消息。</span><span class="sxs-lookup"><span data-stu-id="2977d-186">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

</div>

<div id="sectionSection3" class="section">

<span data-ttu-id="2977d-187">下面的主题包含为受支持的联合身份验证方案的类型定义证书、防火墙端口和 DNS 条目的指南。</span><span class="sxs-lookup"><span data-stu-id="2977d-187">In the following topics contain guidance for defining certificates, firewall ports and DNS entries for the types of supported federation scenarios.</span></span>

  - <span></span>  
    [<span data-ttu-id="2977d-188">Lync Server 2013 中的证书摘要-SIP、XMPP 联合身份验证和公共即时消息</span><span class="sxs-lookup"><span data-stu-id="2977d-188">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="2977d-189">Lync Server 2013 中的端口摘要-SIP、XMPP 联合身份验证和公共即时消息</span><span class="sxs-lookup"><span data-stu-id="2977d-189">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="2977d-190">Lync Server 2013 中的 DNS 摘要-SIP、XMPP 联合身份验证和公共即时消息</span><span class="sxs-lookup"><span data-stu-id="2977d-190">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2977d-191">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2977d-191">See Also</span></span>


[<span data-ttu-id="2977d-192">在 Lync Server 2013 中配置用于控制联合用户访问的策略</span><span class="sxs-lookup"><span data-stu-id="2977d-192">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="2977d-193">Lync Server 2013 中的外部用户访问方案</span><span class="sxs-lookup"><span data-stu-id="2977d-193">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="2977d-194">确定 Lync Server 2013 的外部 A/V 防火墙和端口要求</span><span class="sxs-lookup"><span data-stu-id="2977d-194">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="2977d-195">确定 Lync Server 2013 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="2977d-195">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="2977d-196">在 Lync Server 2013 中管理您的组织的访问边缘配置</span><span class="sxs-lookup"><span data-stu-id="2977d-196">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="2977d-197">在 Lync Server 2013 中管理组织的 SIP 联盟域</span><span class="sxs-lookup"><span data-stu-id="2977d-197">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="2977d-198">在 Lync Server 2013 中管理组织的 SIP 联合提供程序</span><span class="sxs-lookup"><span data-stu-id="2977d-198">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

