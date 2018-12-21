---
title: Skype 加密业务服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype 业务服务器使用 TLS 和 MTLS 来加密即时消息。 无论通信是限制在内部网络还是跨内部网络外围，所有服务器到服务器的通信都需要使用 MTLS。 当业务服务器 Skype 连接到第三方 IPPBX 系统或 SIP 中继 TLS 是可选的但强烈建议在中介服务器与媒体网关之间。 如果在此链接上配置了 TLS，则 MTLS 是必需的。 因此，必须使用从中介服务器信任的 CA 证书配置网关。
ms.openlocfilehash: d6793af3329918af6d566199f8d9fd752df49a71
ms.sourcegitcommit: 81b38b389bfe3acd1aa13ce61c221b7b368c0e2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2018
ms.locfileid: "27382866"
---
# <a name="encryption-for-skype-for-business-server"></a><span data-ttu-id="bae38-107">Skype 加密业务服务器</span><span class="sxs-lookup"><span data-stu-id="bae38-107">Encryption for Skype for Business Server</span></span>
 
<span data-ttu-id="bae38-108">Skype 业务服务器使用 TLS 和 MTLS 来加密即时消息。</span><span class="sxs-lookup"><span data-stu-id="bae38-108">Skype for Business Server uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="bae38-109">无论通信是限制在内部网络还是跨内部网络外围，所有服务器到服务器的通信都需要使用 MTLS。</span><span class="sxs-lookup"><span data-stu-id="bae38-109">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="bae38-110">当业务服务器 Skype 连接到第三方 IPPBX 系统或 SIP 中继 TLS 是可选的但强烈建议在中介服务器与媒体网关之间。</span><span class="sxs-lookup"><span data-stu-id="bae38-110">When connecting Skype for Business Server to third-party IPPBX systems or SIP trunks TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="bae38-111">如果在此链接上配置了 TLS，则 MTLS 是必需的。</span><span class="sxs-lookup"><span data-stu-id="bae38-111">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="bae38-112">因此，必须使用从中介服务器信任的 CA 证书配置网关。</span><span class="sxs-lookup"><span data-stu-id="bae38-112">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bae38-113">2014 年发布了关于 SSL 3.0 的安全公告。</span><span class="sxs-lookup"><span data-stu-id="bae38-113">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="bae38-114">为业务服务器 2015年禁用中 Skype SSL 3.0 是受支持的选项。</span><span class="sxs-lookup"><span data-stu-id="bae38-114">Disabling SSL 3.0 in Skype for Business Server 2015 is a supported option.</span></span> <span data-ttu-id="bae38-115">若要了解有关顾问的安全性的详细信息，请参阅[Lync Server 2013 和 Skype 的业务服务器 2015年中禁用 SSL 3.0](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/)。</span><span class="sxs-lookup"><span data-stu-id="bae38-115">To learn more about the security advisory, see [Disabling SSL 3.0 in Lync Server 2013 and Skype for Business Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/).</span></span><br/>
<span data-ttu-id="bae38-116">**安全说明：** 要确保使用的最强的加密协议，业务服务器 2015年的 Skype 将按以下顺序的 TLS 加密协议为客户端提供： **TLS 1.2 TLS 1.1、 TLS 1.0**。</span><span class="sxs-lookup"><span data-stu-id="bae38-116">**Security note:** To ensure the strongest cryptographic protocol is used, Skype for Business Server 2015 will offer TLS encryption protocols in the following order to clients: **TLS 1.2 , TLS 1.1, TLS 1.0**.</span></span> <span data-ttu-id="bae38-117">TLS 是业务服务器 2015年的 Skype 的一个重要方面，因此需要为了保持受支持的环境。</span><span class="sxs-lookup"><span data-stu-id="bae38-117">TLS is a critical aspect of Skype for Business Server 2015 and thus it is required in order to maintain a supported environment.</span></span><br/>
<span data-ttu-id="bae38-118">**安全说明：** 要确保使用的最强的加密协议，业务服务器 2019年的 Skype 将按以下顺序的 TLS 加密协议为客户端提供： **TLS 1.3、 TLS 1.2**。</span><span class="sxs-lookup"><span data-stu-id="bae38-118">**Security note:** To ensure the strongest cryptographic protocol is used, Skype for Business Server 2019 will offer TLS encryption protocols in the following order to clients: **TLS 1.3, TLS 1.2**.</span></span> <span data-ttu-id="bae38-119">TLS 是业务服务器 2019年的 Skype 的一个重要方面，因此需要为了保持受支持的环境。</span><span class="sxs-lookup"><span data-stu-id="bae38-119">TLS is a critical aspect of Skype for Business Server 2019 and thus it is required in order to maintain a supported environment.</span></span> 
  
<span data-ttu-id="bae38-120">下表汇总了每种类型的通信的协议要求。</span><span class="sxs-lookup"><span data-stu-id="bae38-120">The following table summarizes the protocol requirements for each type of traffic.</span></span> 
  
<span data-ttu-id="bae38-121">**通信保护**</span><span class="sxs-lookup"><span data-stu-id="bae38-121">**Traffic Protection**</span></span>

|<span data-ttu-id="bae38-122">**通信类型**</span><span class="sxs-lookup"><span data-stu-id="bae38-122">**Traffic type**</span></span>|<span data-ttu-id="bae38-123">**保护协议**</span><span class="sxs-lookup"><span data-stu-id="bae38-123">**Protected by**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bae38-124">服务器到服务器</span><span class="sxs-lookup"><span data-stu-id="bae38-124">Server-to-server</span></span>  <br/> |<span data-ttu-id="bae38-125">MTLS</span><span class="sxs-lookup"><span data-stu-id="bae38-125">MTLS</span></span>  <br/> |
|<span data-ttu-id="bae38-126">客户端到服务器</span><span class="sxs-lookup"><span data-stu-id="bae38-126">Client-to-server</span></span>  <br/> |<span data-ttu-id="bae38-127">TLS</span><span class="sxs-lookup"><span data-stu-id="bae38-127">TLS</span></span>  <br/> |
|<span data-ttu-id="bae38-128">即时消息和状态</span><span class="sxs-lookup"><span data-stu-id="bae38-128">Instant messaging and presence</span></span>  <br/> |<span data-ttu-id="bae38-129">TLS</span><span class="sxs-lookup"><span data-stu-id="bae38-129">TLS</span></span>  <br/> |
|<span data-ttu-id="bae38-130">音频、视频和媒体的桌面共享</span><span class="sxs-lookup"><span data-stu-id="bae38-130">Audio and video and desktop sharing of media</span></span>  <br/> |<span data-ttu-id="bae38-131">SRTP</span><span class="sxs-lookup"><span data-stu-id="bae38-131">SRTP</span></span>  <br/> |
|<span data-ttu-id="bae38-132">桌面共享（信号）</span><span class="sxs-lookup"><span data-stu-id="bae38-132">Desktop sharing (signaling)</span></span>  <br/> |<span data-ttu-id="bae38-133">TLS</span><span class="sxs-lookup"><span data-stu-id="bae38-133">TLS</span></span>  <br/> |
|<span data-ttu-id="bae38-134">Web 会议</span><span class="sxs-lookup"><span data-stu-id="bae38-134">Web conferencing</span></span>  <br/> |<span data-ttu-id="bae38-135">TLS</span><span class="sxs-lookup"><span data-stu-id="bae38-135">TLS</span></span>  <br/> |
|<span data-ttu-id="bae38-136">会议内容下载、通讯簿下载和通讯组扩展</span><span class="sxs-lookup"><span data-stu-id="bae38-136">Meeting content download, address book download, distribution group expansion</span></span>  <br/> |<span data-ttu-id="bae38-137">HTTPS</span><span class="sxs-lookup"><span data-stu-id="bae38-137">HTTPS</span></span>  <br/> |
   
## <a name="media-encryption"></a><span data-ttu-id="bae38-138">媒体加密</span><span class="sxs-lookup"><span data-stu-id="bae38-138">Media Encryption</span></span>

<span data-ttu-id="bae38-p106">媒体通信使用安全 RTP (SRTP) 进行加密，SRTP 是为 RTP 通信提供保密性、身份验证和重播攻击保护的实时传输协议 (RTP) 的配置文件。此外，中介服务器与其内部下一个跃点之间的双向媒体流也使用 SRTP 进行加密。中介服务器与媒体网关之间的双向媒体流的加密是可选的，但建议进行加密。中介服务器能够支持对媒体网关进行加密，但该网关必须支持 MTLS 和证书存储。</span><span class="sxs-lookup"><span data-stu-id="bae38-p106">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic. In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP. Media flowing in both directions between the Mediation Server and a media gateway is optionally encrypted and recommended. The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bae38-143">如果要实现混合环境，您还必须修改业务服务器加密级别 Skype。</span><span class="sxs-lookup"><span data-stu-id="bae38-143">If you are implementing a hybrid environment, you must also modify the Skype for Business Server encryption level.</span></span> <span data-ttu-id="bae38-144">默认情况下，加密级别为“必需”。</span><span class="sxs-lookup"><span data-stu-id="bae38-144">By default, the encryption level is Required.</span></span> <span data-ttu-id="bae38-145">使用 Skype 业务 Server 命令行管理程序，必须对支持更改此设置。</span><span class="sxs-lookup"><span data-stu-id="bae38-145">You must change this setting to Supported by using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="bae38-146">有关设置混合的详细信息，请参阅[规划 Skype 业务服务器和 Skype 业务 online 之间的混合连接](../../../SfBServer2019/hybrid/plan-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="bae38-146">For more information about setting up hybrid, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfBServer2019/hybrid/plan-hybrid-connectivity.md).</span></span>
  
## <a name="fips"></a><span data-ttu-id="bae38-147">FIPS</span><span class="sxs-lookup"><span data-stu-id="bae38-147">FIPS</span></span>

<span data-ttu-id="bae38-148">如果在 Windows Server 操作系统配置为使用 FIPS 140-2 算法来进行系统加密 Business Server 和 Microsoft Exchange Server 2016 Skype 操作联邦信息处理标准 (FIPS) 140-2 算法的支持.</span><span class="sxs-lookup"><span data-stu-id="bae38-148">Skype for Business Server and Microsoft Exchange Server 2016 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="bae38-149">若要实现 FIPS 支持，必须配置每台运行 Skype 业务服务器支持它。</span><span class="sxs-lookup"><span data-stu-id="bae38-149">To implement FIPS support, you must configure each server running Skype for Business Server to support it.</span></span>
  

