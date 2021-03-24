---
title: Skype for Business Server 加密
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype for Business Server 使用 TLS 和 MTLS 加密即时消息。 所有服务器到服务器流量都需要 MTLS，无论通信是限制在内部网络还是跨内部网络外围。 将 Skype for Business Server 连接到第三方 IPPBX 系统或 SIP 中继时，TLS 是可选的，但强烈建议在中介服务器和媒体网关之间使用 TLS。 如果在此链接上配置了 TLS，则 MTLS 是必需的。 因此，必须使用中介服务器信任的 CA 颁发的证书配置网关。
ms.openlocfilehash: 269a5394f5438802c68dabed17081c71a353a2b5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104228"
---
# <a name="encryption-for-skype-for-business-server"></a><span data-ttu-id="fa281-107">Skype for Business Server 加密</span><span class="sxs-lookup"><span data-stu-id="fa281-107">Encryption for Skype for Business Server</span></span>
 
<span data-ttu-id="fa281-108">Skype for Business Server 使用 TLS 和 MTLS 加密即时消息。</span><span class="sxs-lookup"><span data-stu-id="fa281-108">Skype for Business Server uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="fa281-109">所有服务器到服务器流量都需要 MTLS，无论通信是限制在内部网络还是跨内部网络外围。</span><span class="sxs-lookup"><span data-stu-id="fa281-109">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="fa281-110">将 Skype for Business Server 连接到第三方 IPPBX 系统或 SIP 中继 TLS 是可选的，但强烈建议在中介服务器和媒体网关之间使用 TLS。</span><span class="sxs-lookup"><span data-stu-id="fa281-110">When connecting Skype for Business Server to third-party IPPBX systems or SIP trunks TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="fa281-111">如果在此链接上配置了 TLS，则 MTLS 是必需的。</span><span class="sxs-lookup"><span data-stu-id="fa281-111">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="fa281-112">因此，必须使用中介服务器信任的 CA 颁发的证书配置网关。</span><span class="sxs-lookup"><span data-stu-id="fa281-112">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fa281-113">2014 年发布了关于 SSL 3.0 的安全公告。</span><span class="sxs-lookup"><span data-stu-id="fa281-113">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="fa281-114">支持在 Skype for Business Server 2015 中禁用 SSL 3.0。</span><span class="sxs-lookup"><span data-stu-id="fa281-114">Disabling SSL 3.0 in Skype for Business Server 2015 is a supported option.</span></span> <span data-ttu-id="fa281-115">若要了解有关安全公告的详细信息，请参阅[Disabling SSL 3.0 in Lync Server 2013 and Skype for Business Server 2015。](/archive/blogs/uclobby/disabling-ssl-3-0-in-lync-server-2013)</span><span class="sxs-lookup"><span data-stu-id="fa281-115">To learn more about the security advisory, see [Disabling SSL 3.0 in Lync Server 2013 and Skype for Business Server 2015](/archive/blogs/uclobby/disabling-ssl-3-0-in-lync-server-2013).</span></span><br/>
<span data-ttu-id="fa281-116">**安全说明：** 为了确保使用最强加密协议，Skype for Business Server 2015 将按以下顺序向客户端提供 TLS 加密协议 **：TLS 1.2、TLS 1.1、TLS 1.0。**</span><span class="sxs-lookup"><span data-stu-id="fa281-116">**Security note:** To ensure the strongest cryptographic protocol is used, Skype for Business Server 2015 will offer TLS encryption protocols in the following order to clients: **TLS 1.2 , TLS 1.1, TLS 1.0**.</span></span> <span data-ttu-id="fa281-117">TLS 是 Skype for Business Server 2015 的关键方面，因此维护支持的环境需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="fa281-117">TLS is a critical aspect of Skype for Business Server 2015 and thus it is required in order to maintain a supported environment.</span></span><br/>
<span data-ttu-id="fa281-118">**安全说明：** 为了确保使用最强加密协议，Skype for Business Server 2019 将按以下顺序向客户端提供 TLS 加密协议 **：TLS 1.3、TLS 1.2。**</span><span class="sxs-lookup"><span data-stu-id="fa281-118">**Security note:** To ensure the strongest cryptographic protocol is used, Skype for Business Server 2019 will offer TLS encryption protocols in the following order to clients: **TLS 1.3, TLS 1.2**.</span></span> <span data-ttu-id="fa281-119">TLS 是 Skype for Business Server 2019 的一个关键方面，因此需要 TLS 才能维护支持的环境。</span><span class="sxs-lookup"><span data-stu-id="fa281-119">TLS is a critical aspect of Skype for Business Server 2019 and thus it is required in order to maintain a supported environment.</span></span> 
  
<span data-ttu-id="fa281-120">下表汇总了每种类型的通信的协议要求。</span><span class="sxs-lookup"><span data-stu-id="fa281-120">The following table summarizes the protocol requirements for each type of traffic.</span></span> 
  
<span data-ttu-id="fa281-121">**通信保护**</span><span class="sxs-lookup"><span data-stu-id="fa281-121">**Traffic Protection**</span></span>

|<span data-ttu-id="fa281-122">**通信类型**</span><span class="sxs-lookup"><span data-stu-id="fa281-122">**Traffic type**</span></span>|<span data-ttu-id="fa281-123">**保护协议**</span><span class="sxs-lookup"><span data-stu-id="fa281-123">**Protected by**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fa281-124">服务器到服务器</span><span class="sxs-lookup"><span data-stu-id="fa281-124">Server-to-server</span></span>  <br/> |<span data-ttu-id="fa281-125">MTLS</span><span class="sxs-lookup"><span data-stu-id="fa281-125">MTLS</span></span>  <br/> |
|<span data-ttu-id="fa281-126">客户端到服务器</span><span class="sxs-lookup"><span data-stu-id="fa281-126">Client-to-server</span></span>  <br/> |<span data-ttu-id="fa281-127">TLS</span><span class="sxs-lookup"><span data-stu-id="fa281-127">TLS</span></span>  <br/> |
|<span data-ttu-id="fa281-128">即时消息和状态</span><span class="sxs-lookup"><span data-stu-id="fa281-128">Instant messaging and presence</span></span>  <br/> |<span data-ttu-id="fa281-129">TLS</span><span class="sxs-lookup"><span data-stu-id="fa281-129">TLS</span></span>  <br/> |
|<span data-ttu-id="fa281-130">音频、视频和媒体的桌面共享</span><span class="sxs-lookup"><span data-stu-id="fa281-130">Audio and video and desktop sharing of media</span></span>  <br/> |<span data-ttu-id="fa281-131">SRTP</span><span class="sxs-lookup"><span data-stu-id="fa281-131">SRTP</span></span>  <br/> |
|<span data-ttu-id="fa281-132">桌面共享（信号）</span><span class="sxs-lookup"><span data-stu-id="fa281-132">Desktop sharing (signaling)</span></span>  <br/> |<span data-ttu-id="fa281-133">TLS</span><span class="sxs-lookup"><span data-stu-id="fa281-133">TLS</span></span>  <br/> |
|<span data-ttu-id="fa281-134">Web 会议</span><span class="sxs-lookup"><span data-stu-id="fa281-134">Web conferencing</span></span>  <br/> |<span data-ttu-id="fa281-135">TLS</span><span class="sxs-lookup"><span data-stu-id="fa281-135">TLS</span></span>  <br/> |
|<span data-ttu-id="fa281-136">会议内容下载、通讯簿下载和通讯组扩展</span><span class="sxs-lookup"><span data-stu-id="fa281-136">Meeting content download, address book download, distribution group expansion</span></span>  <br/> |<span data-ttu-id="fa281-137">HTTPS</span><span class="sxs-lookup"><span data-stu-id="fa281-137">HTTPS</span></span>  <br/> |
   
## <a name="media-encryption"></a><span data-ttu-id="fa281-138">媒体加密</span><span class="sxs-lookup"><span data-stu-id="fa281-138">Media Encryption</span></span>

<span data-ttu-id="fa281-139">媒体通信是使用安全 RTP (SRTP) 进行加密的，SRTP 是为 RTP 通信提供保密性、身份验证和重播攻击保护的实时传输协议 (RTP) 的配置文件。</span><span class="sxs-lookup"><span data-stu-id="fa281-139">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="fa281-140">此外，在中介服务器和其内部下一个跃点之间的双向媒体也使用 SRTP 进行加密。</span><span class="sxs-lookup"><span data-stu-id="fa281-140">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="fa281-141">中介服务器与媒体网关之间的两个方向的媒体流（可选）已加密，建议进行加密。</span><span class="sxs-lookup"><span data-stu-id="fa281-141">Media flowing in both directions between the Mediation Server and a media gateway is optionally encrypted and recommended.</span></span> <span data-ttu-id="fa281-142">中介服务器能够支持对媒体网关进行加密，但该网关必须支持 MTLS 和证书存储。</span><span class="sxs-lookup"><span data-stu-id="fa281-142">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fa281-143">有关设置混合连接的信息，请参阅规划 [混合连接](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="fa281-143">For more information about setting up hybrid, see [Plan hybrid connectivity](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).</span></span>
  
## <a name="fips"></a><span data-ttu-id="fa281-144">FIPS</span><span class="sxs-lookup"><span data-stu-id="fa281-144">FIPS</span></span>

<span data-ttu-id="fa281-145">如果 Windows Server 操作系统配置为使用 FIPS 140-2 算法进行系统加密，则 Skype for Business Server 和 Microsoft Exchange Server 2016 支持联邦信息处理标准 (FIPS) 140-2 算法。</span><span class="sxs-lookup"><span data-stu-id="fa281-145">Skype for Business Server and Microsoft Exchange Server 2016 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="fa281-146">若要实现 FIPS 支持，必须配置运行 Skype for Business Server 的每台服务器以支持它。</span><span class="sxs-lookup"><span data-stu-id="fa281-146">To implement FIPS support, you must configure each server running Skype for Business Server to support it.</span></span>
