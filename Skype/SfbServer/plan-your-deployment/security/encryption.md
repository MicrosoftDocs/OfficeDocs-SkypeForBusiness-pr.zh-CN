---
title: Skype for Business Server 2015 加密
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/15/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: 商业服务器 2015年的 Skype 使用 TLS 和 MTLS 即时消息进行加密。 无论通信是限制在内部网络还是跨内部网络外围，所有服务器到服务器的通信都需要使用 MTLS。 当连接到第三方 IPPBX 系统或 SIP 中继 TLS Skype 业务服务器 2015年时可选但强烈建议中介服务器和媒体网关之间。 如果在此链接上配置了 TLS，则 MTLS 是必需的。 因此，网关必须配置有中介服务器受信任的 CA 的证书。
ms.openlocfilehash: bf17f2c8ff8180fa5622957c665da3f4608ca833
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="encryption-for-skype-for-business-server-2015"></a><span data-ttu-id="9a098-107">Skype for Business Server 2015 加密</span><span class="sxs-lookup"><span data-stu-id="9a098-107">Encryption for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9a098-108">商业服务器 2015年的 Skype 使用 TLS 和 MTLS 即时消息进行加密。</span><span class="sxs-lookup"><span data-stu-id="9a098-108">Skype for Business Server 2015 uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="9a098-109">无论通信是限制在内部网络还是跨内部网络外围，所有服务器到服务器的通信都需要使用 MTLS。</span><span class="sxs-lookup"><span data-stu-id="9a098-109">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="9a098-110">当连接到第三方 IPPBX 系统或 SIP 中继 TLS Skype 业务服务器 2015年时可选但强烈建议中介服务器和媒体网关之间。</span><span class="sxs-lookup"><span data-stu-id="9a098-110">When connecting Skype for Business Server 2015 to 3rd party IPPBX systems or SIP trunks TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="9a098-111">如果在此链接上配置了 TLS，则 MTLS 是必需的。</span><span class="sxs-lookup"><span data-stu-id="9a098-111">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="9a098-112">因此，网关必须配置有中介服务器受信任的 CA 的证书。</span><span class="sxs-lookup"><span data-stu-id="9a098-112">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9a098-113">2014 年发布了关于 SSL 3.0 的安全公告。</span><span class="sxs-lookup"><span data-stu-id="9a098-113">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="9a098-114">为业务服务器 2015年禁用 SSL 3.0 在 Skype 是受支持的选项。</span><span class="sxs-lookup"><span data-stu-id="9a098-114">Disabling SSL 3.0 in Skype for Business Server 2015 is a supported option.</span></span> <span data-ttu-id="9a098-115">有关安全公告的详细信息，请参阅[在 Lync Server 2013 和 Skype 的业务服务器 2015年禁用 SSL 3.0](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/)。</span><span class="sxs-lookup"><span data-stu-id="9a098-115">To learn more about the security advisory, see [Disabling SSL 3.0 in Lync Server 2013 and Skype for Business Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/).</span></span> 
  
> [!安全说明]<span data-ttu-id="9a098-116"> 来确保最强的加密协议，Skype 的业务服务器 2015年将向客户端提供 TLS 加密协议顺序如下： **TLS 1.2，TLS 1.1，TLS 1.0**。</span><span class="sxs-lookup"><span data-stu-id="9a098-116"> To ensure the strongest cryptographic protocol is used, Skype for Business Server 2015 will offer TLS encryption protocols in the following order to clients: **TLS 1.2 , TLS 1.1, TLS 1.0**.</span></span> <span data-ttu-id="9a098-117">TLS 是 Skype 业务服务器 2015年的一个重要方面，因此需要以保持受支持的环境。</span><span class="sxs-lookup"><span data-stu-id="9a098-117">TLS is a critical aspect of Skype for Business Server 2015 and thus it is required in order to maintain a supported environment.</span></span> 
  
<span data-ttu-id="9a098-118">下表汇总了每种类型的通信的协议要求。</span><span class="sxs-lookup"><span data-stu-id="9a098-118">The following table summarizes the protocol requirements for each type of traffic.</span></span> 
  
<span data-ttu-id="9a098-119">**通信保护**</span><span class="sxs-lookup"><span data-stu-id="9a098-119">**Traffic Protection**</span></span>

|<span data-ttu-id="9a098-120">**通信量类型**</span><span class="sxs-lookup"><span data-stu-id="9a098-120">**Traffic type**</span></span>|<span data-ttu-id="9a098-121">**受**</span><span class="sxs-lookup"><span data-stu-id="9a098-121">**Protected by**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9a098-122">服务器到服务器</span><span class="sxs-lookup"><span data-stu-id="9a098-122">Server-to-server</span></span>  <br/> |<span data-ttu-id="9a098-123">MTLS</span><span class="sxs-lookup"><span data-stu-id="9a098-123">MTLS</span></span>  <br/> |
|<span data-ttu-id="9a098-124">客户端到服务器</span><span class="sxs-lookup"><span data-stu-id="9a098-124">Client-to-server</span></span>  <br/> |<span data-ttu-id="9a098-125">TLS</span><span class="sxs-lookup"><span data-stu-id="9a098-125">TLS</span></span>  <br/> |
|<span data-ttu-id="9a098-126">即时消息和状态</span><span class="sxs-lookup"><span data-stu-id="9a098-126">Instant messaging and presence</span></span>  <br/> |<span data-ttu-id="9a098-127">TLS</span><span class="sxs-lookup"><span data-stu-id="9a098-127">TLS</span></span>  <br/> |
|<span data-ttu-id="9a098-128">音频、视频和媒体的桌面共享</span><span class="sxs-lookup"><span data-stu-id="9a098-128">Audio and video and desktop sharing of media</span></span>  <br/> |<span data-ttu-id="9a098-129">SRTP</span><span class="sxs-lookup"><span data-stu-id="9a098-129">SRTP</span></span>  <br/> |
|<span data-ttu-id="9a098-130">桌面共享（信号）</span><span class="sxs-lookup"><span data-stu-id="9a098-130">Desktop sharing (signaling)</span></span>  <br/> |<span data-ttu-id="9a098-131">TLS</span><span class="sxs-lookup"><span data-stu-id="9a098-131">TLS</span></span>  <br/> |
|<span data-ttu-id="9a098-132">Web 会议</span><span class="sxs-lookup"><span data-stu-id="9a098-132">Web conferencing</span></span>  <br/> |<span data-ttu-id="9a098-133">TLS</span><span class="sxs-lookup"><span data-stu-id="9a098-133">TLS</span></span>  <br/> |
|<span data-ttu-id="9a098-134">会议内容下载、通讯簿下载和通讯组扩展</span><span class="sxs-lookup"><span data-stu-id="9a098-134">Meeting content download, address book download, distribution group expansion</span></span>  <br/> |<span data-ttu-id="9a098-135">HTTPS</span><span class="sxs-lookup"><span data-stu-id="9a098-135">HTTPS</span></span>  <br/> |
   
## <a name="media-encryption"></a><span data-ttu-id="9a098-136">媒体加密</span><span class="sxs-lookup"><span data-stu-id="9a098-136">Media Encryption</span></span>

<span data-ttu-id="9a098-p105">媒体通信使用安全 RTP (SRTP) 进行加密，SRTP 是为 RTP 通信提供保密性、身份验证和重播攻击保护的实时传输协议 (RTP) 的配置文件。此外，中介服务器与其内部下一个跃点之间的双向媒体流也使用 SRTP 进行加密。中介服务器与媒体网关之间的双向媒体流的加密是可选的，但建议进行加密。中介服务器能够支持对媒体网关进行加密，但该网关必须支持 MTLS 和证书存储。</span><span class="sxs-lookup"><span data-stu-id="9a098-p105">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic. In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP. Media flowing in both directions between the Mediation Server and a media gateway is optionally encrypted and recommended. The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9a098-141">如果您要实现的混合环境，还必须修改有关业务服务器 2015年加密级别 Skype。</span><span class="sxs-lookup"><span data-stu-id="9a098-141">If you are implementing a hybrid environment, you must also modify the Skype for Business Server 2015 encryption level.</span></span> <span data-ttu-id="9a098-142">默认情况下，加密级别为“必需”。</span><span class="sxs-lookup"><span data-stu-id="9a098-142">By default, the encryption level is Required.</span></span> <span data-ttu-id="9a098-143">通过 Skype 业务服务器管理外壳程序，必须为支持更改此设置。</span><span class="sxs-lookup"><span data-stu-id="9a098-143">You must change this setting to Supported by using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="9a098-144">有关混合设置的详细信息，请参阅部署文档中[移动业务联机到内部部署 Skype 的用户](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-skype-for-business-online-to-on-premises.md)。</span><span class="sxs-lookup"><span data-stu-id="9a098-144">For more information about setting up hybrid, see [Move users from Skype for Business Online to on premises](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-skype-for-business-online-to-on-premises.md) in the Deployment documentation.</span></span>
  
## <a name="fips"></a><span data-ttu-id="9a098-145">FIPS</span><span class="sxs-lookup"><span data-stu-id="9a098-145">FIPS</span></span>

<span data-ttu-id="9a098-146">如果 Windows 服务器操作系统的系统被配置为使用 FIPS 140-2 算法的系统支持联邦信息处理标准 (FIPS) 140-2 算法运行 Skype 业务服务器 2015年和 Microsoft Exchange Server 2016加密技术。</span><span class="sxs-lookup"><span data-stu-id="9a098-146">Skype for Business Server 2015 and Microsoft Exchange Server 2016 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="9a098-147">若要实现 FIPS 支持，您必须配置运行 Skype 业务服务器 2015 来支持它的每个服务器。</span><span class="sxs-lookup"><span data-stu-id="9a098-147">To implement FIPS support, you must configure each server running Skype for Business Server 2015 to support it.</span></span>
  

