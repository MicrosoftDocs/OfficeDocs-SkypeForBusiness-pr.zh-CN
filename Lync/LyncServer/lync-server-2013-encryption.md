---
title: Lync Server 2013：加密
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f4b655ff632a50d2c28451a577f5be03bfabc82
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a><span data-ttu-id="0a13f-102">Lync Server 2013 的加密</span><span class="sxs-lookup"><span data-stu-id="0a13f-102">Encryption for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a13f-103">_**主题上次修改时间：** 2017-09-14_</span><span class="sxs-lookup"><span data-stu-id="0a13f-103">_**Topic Last Modified:** 2017-09-14_</span></span>

<span data-ttu-id="0a13f-104">Microsoft Lync Server 2013 使用 TLS 和 MTLS 对即时消息进行加密。</span><span class="sxs-lookup"><span data-stu-id="0a13f-104">Microsoft Lync Server 2013 uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="0a13f-105">无论通信是限制在内部网络还是跨内部网络外围，所有服务器到服务器的通信都需要使用 MTLS。</span><span class="sxs-lookup"><span data-stu-id="0a13f-105">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="0a13f-106">TLS 是可选的，但强烈建议在中介服务器和媒体网关之间使用 TLS。</span><span class="sxs-lookup"><span data-stu-id="0a13f-106">TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="0a13f-107">如果在此链接上配置了 TLS，则 MTLS 是必需的。</span><span class="sxs-lookup"><span data-stu-id="0a13f-107">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="0a13f-108">因此，网关必须配置来自中介服务器信任的 CA 的证书。</span><span class="sxs-lookup"><span data-stu-id="0a13f-108">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0a13f-109">2014 年发布了关于 SSL 3.0 的安全公告。</span><span class="sxs-lookup"><span data-stu-id="0a13f-109">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="0a13f-110">在 Lync Server 2013 中禁用 SSL 3.0 是受支持的选项。</span><span class="sxs-lookup"><span data-stu-id="0a13f-110">Disabling SSL 3.0 in Lync Server 2013 is a supported option.</span></span> <span data-ttu-id="0a13f-111">若要了解有关安全公告的详细信息<A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>，请参阅。</span><span class="sxs-lookup"><span data-stu-id="0a13f-111">To learn more about the security advisory, see <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.</span></span>



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全" alt="security" /><span data-ttu-id="0a13f-113">安全说明：</span><span class="sxs-lookup"><span data-stu-id="0a13f-113">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0a13f-114">为确保使用最强的加密协议，Lync Server 2013 将按以下顺序向客户端提供 TLS 加密协议： <strong>tls 1.2</strong> 、 <strong>tls 1.1</strong>、 <strong>tls 1.0</strong>。</span><span class="sxs-lookup"><span data-stu-id="0a13f-114">To ensure the strongest cryptographic protocol is used, Lync Server 2013 will offer TLS encryption protocols in the following order to clients: <strong>TLS 1.2</strong> , <strong>TLS 1.1</strong>, <strong>TLS 1.0</strong>.</span></span> <span data-ttu-id="0a13f-115">TLS 是 Lync Server 2013 的一个重要方面，因此它是维护受支持的环境所必需的。</span><span class="sxs-lookup"><span data-stu-id="0a13f-115">TLS is a critical aspect of Lync Server 2013 and thus it is required in order to maintain a supported environment.</span></span></td>
</tr>
</tbody>
</table>


</div>

<span data-ttu-id="0a13f-116">客户端到客户端流量的要求取决于该流量是否与内部公司防火墙相交叉。</span><span class="sxs-lookup"><span data-stu-id="0a13f-116">Requirements for client-to-client traffic depend on whether that traffic crosses the internal corporate firewall.</span></span> <span data-ttu-id="0a13f-117">严格的内部流量可以使用 TLS，在这种情况下，会对即时消息进行加密或 TCP，在这种情况下不会进行加密。</span><span class="sxs-lookup"><span data-stu-id="0a13f-117">Strictly internal traffic can use either TLS, in which case the instant message is encrypted, or TCP, in which case it is not.</span></span>

<span data-ttu-id="0a13f-118">下表汇总了每种类型的通信的协议要求。</span><span class="sxs-lookup"><span data-stu-id="0a13f-118">The following table summarizes the protocol requirements for each type of traffic.</span></span>

### <a name="traffic-protection"></a><span data-ttu-id="0a13f-119">通信保护</span><span class="sxs-lookup"><span data-stu-id="0a13f-119">Traffic Protection</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0a13f-120">通信类型</span><span class="sxs-lookup"><span data-stu-id="0a13f-120">Traffic type</span></span></th>
<th><span data-ttu-id="0a13f-121">保护协议</span><span class="sxs-lookup"><span data-stu-id="0a13f-121">Protected by</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a13f-122">服务器到服务器</span><span class="sxs-lookup"><span data-stu-id="0a13f-122">Server-to-server</span></span></p></td>
<td><p><span data-ttu-id="0a13f-123">MTLS</span><span class="sxs-lookup"><span data-stu-id="0a13f-123">MTLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a13f-124">客户端到服务器</span><span class="sxs-lookup"><span data-stu-id="0a13f-124">Client-to-server</span></span></p></td>
<td><p><span data-ttu-id="0a13f-125">TLS</span><span class="sxs-lookup"><span data-stu-id="0a13f-125">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a13f-126">即时消息和状态</span><span class="sxs-lookup"><span data-stu-id="0a13f-126">Instant messaging and presence</span></span></p></td>
<td><p><span data-ttu-id="0a13f-127">TLS（如果已配置 TLS）</span><span class="sxs-lookup"><span data-stu-id="0a13f-127">TLS (if configured for TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a13f-128">音频、视频和媒体的桌面共享</span><span class="sxs-lookup"><span data-stu-id="0a13f-128">Audio and video and desktop sharing of media</span></span></p></td>
<td><p><span data-ttu-id="0a13f-129">SRTP</span><span class="sxs-lookup"><span data-stu-id="0a13f-129">SRTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a13f-130">桌面共享（信号）</span><span class="sxs-lookup"><span data-stu-id="0a13f-130">Desktop sharing (signaling)</span></span></p></td>
<td><p><span data-ttu-id="0a13f-131">TLS</span><span class="sxs-lookup"><span data-stu-id="0a13f-131">TLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a13f-132">Web 会议</span><span class="sxs-lookup"><span data-stu-id="0a13f-132">Web conferencing</span></span></p></td>
<td><p><span data-ttu-id="0a13f-133">TLS</span><span class="sxs-lookup"><span data-stu-id="0a13f-133">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0a13f-134">会议内容下载、通讯簿下载和通讯组扩展</span><span class="sxs-lookup"><span data-stu-id="0a13f-134">Meeting content download, address book download, distribution group expansion</span></span></p></td>
<td><p><span data-ttu-id="0a13f-135">HTTPS</span><span class="sxs-lookup"><span data-stu-id="0a13f-135">HTTPS</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a><span data-ttu-id="0a13f-136">媒体加密</span><span class="sxs-lookup"><span data-stu-id="0a13f-136">Media Encryption</span></span>

<span data-ttu-id="0a13f-137">媒体通信使用安全 RTP (SRTP) 进行加密，SRTP 是为 RTP 通信提供保密性、身份验证和重播攻击保护的实时传输协议 (RTP) 的配置文件。</span><span class="sxs-lookup"><span data-stu-id="0a13f-137">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="0a13f-138">此外，中介服务器与其内部下一个跃点之间的双向媒体流也使用 SRTP 进行加密。</span><span class="sxs-lookup"><span data-stu-id="0a13f-138">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="0a13f-139">默认情况下，中介服务器和媒体网关之间的两个方向的媒体均未加密。</span><span class="sxs-lookup"><span data-stu-id="0a13f-139">Media flowing in both directions between the Mediation Server and a media gateway is not encrypted by default.</span></span> <span data-ttu-id="0a13f-140">中介服务器能够支持对媒体网关进行加密，但该网关必须支持 MTLS 和证书存储。</span><span class="sxs-lookup"><span data-stu-id="0a13f-140">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0a13f-141">新版本的 Windows Live Messenger 支持音频/视频（A/V）。</span><span class="sxs-lookup"><span data-stu-id="0a13f-141">Audio/Video (A/V) is supported with the new version of Windows Live Messenger.</span></span> <span data-ttu-id="0a13f-142">如果要实现与 Windows Live Messenger 的 A/V 联合，还必须修改 Lync 服务器加密级别。</span><span class="sxs-lookup"><span data-stu-id="0a13f-142">If you are implementing A/V federation with Windows Live Messenger, you must also modify the Lync Server encryption level.</span></span> <span data-ttu-id="0a13f-143">默认情况下，加密级别为“必需”。</span><span class="sxs-lookup"><span data-stu-id="0a13f-143">By default, the encryption level is Required.</span></span> <span data-ttu-id="0a13f-144">您必须使用 Lync Server 命令行管理程序将此设置更改为 "支持"。</span><span class="sxs-lookup"><span data-stu-id="0a13f-144">You must change this setting to Supported by using the Lync Server Management Shell.</span></span> <span data-ttu-id="0a13f-145">有关详细信息，请参阅部署文档中<A href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013 中的 "部署外部用户访问</A>"。</span><span class="sxs-lookup"><span data-stu-id="0a13f-145">For more information, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="0a13f-146">音频和视频媒体流量不会在 Microsoft Lync 2013 和 Windows Live 客户端之间加密。</span><span class="sxs-lookup"><span data-stu-id="0a13f-146">Audio and video media traffic is not encrypted between Microsoft Lync 2013 and Windows Live clients.</span></span>

</div>

<div>

## <a name="fips"></a><span data-ttu-id="0a13f-147">FIPS</span><span class="sxs-lookup"><span data-stu-id="0a13f-147">FIPS</span></span>

<span data-ttu-id="0a13f-148">如果将 Windows Server 操作系统配置为使用适用于系统加密的 FIPS 140-2 算法，则 Lync Server 2013 和 Microsoft Exchange Server 2013 将使用联邦信息处理标准（FIPS）140-2 算法的支持操作。</span><span class="sxs-lookup"><span data-stu-id="0a13f-148">Lync Server 2013 and Microsoft Exchange Server 2013 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="0a13f-149">若要实现 FIPS 支持，必须配置运行 Lync Server 2013 的每台服务器以支持它。</span><span class="sxs-lookup"><span data-stu-id="0a13f-149">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="0a13f-150">有关使用 FIPS 兼容的算法以及如何实现 FIPS 支持的详细信息，请参阅 Microsoft 知识库文章811833：启用 "系统加密：在 Windows XP 和 Windows 的更高版本中使用 FIPS 兼容的算法进行加密、哈希和签名" 安全设置的效果[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)。</span><span class="sxs-lookup"><span data-stu-id="0a13f-150">For details about the use of FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, The effects of enabling the “System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing" security setting in Windows XP and in later versions of Windows at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="0a13f-151">有关 FIPS 140-2 支持和 Exchange 2010 中的限制的详细信息，请参阅 Exchange 2010 SP1 和支持 FIPS 兼容[https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)的算法。</span><span class="sxs-lookup"><span data-stu-id="0a13f-151">For details about FIPS 140-2 support and limitations in Exchange 2010, see Exchange 2010 SP1 and Support for FIPS Compliant Algorithms at [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

