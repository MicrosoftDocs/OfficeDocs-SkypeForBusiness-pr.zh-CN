---
title: Lync Server 2013 证书基础结构要求
description: Lync Server 2013 证书基础结构要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02c7e69f272c29f0ba9386f403db326b4d39bbff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544288"
---
# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="e912d-103">Lync Server 2013 的证书基础结构要求</span><span class="sxs-lookup"><span data-stu-id="e912d-103">Certificate infrastructure requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e912d-104">_**上次修改的主题：** 2016-06-23_</span><span class="sxs-lookup"><span data-stu-id="e912d-104">_**Topic Last Modified:** 2016-06-23_</span></span>

<span data-ttu-id="e912d-105">Lync Server 2013 要求 (PKI) 的公钥基础结构，以支持 TLS 和相互 TLS (MTLS) 连接。</span><span class="sxs-lookup"><span data-stu-id="e912d-105">Lync Server 2013 requires a public key infrastructure (PKI) to support TLS and mutual TLS (MTLS) connections.</span></span>

<span data-ttu-id="e912d-106">Lync Server 使用证书实现以下目的：</span><span class="sxs-lookup"><span data-stu-id="e912d-106">Lync Server uses certificates for the following purposes:</span></span>

  - <span data-ttu-id="e912d-107">客户端和服务器之间的 TLS 连接</span><span class="sxs-lookup"><span data-stu-id="e912d-107">TLS connections between client and server</span></span>

  - <span data-ttu-id="e912d-108">服务器之间的 MTLS 连接</span><span class="sxs-lookup"><span data-stu-id="e912d-108">MTLS connections between servers</span></span>

  - <span data-ttu-id="e912d-109">使用自动发现伙伴 DNS 的联盟</span><span class="sxs-lookup"><span data-stu-id="e912d-109">Federation using automatic DNS discovery of partners</span></span>

  - <span data-ttu-id="e912d-110">远程用户访问即时消息 (IM)</span><span class="sxs-lookup"><span data-stu-id="e912d-110">Remote user access for instant messaging (IM)</span></span>

  - <span data-ttu-id="e912d-111">外部用户访问音频/视频 (A/V) 会话、应用程序共享和会议</span><span class="sxs-lookup"><span data-stu-id="e912d-111">External user access to audio/video (A/V) sessions, application sharing, and conferencing</span></span>

  - <span data-ttu-id="e912d-112">使用 Web 服务的自动发现的移动请求</span><span class="sxs-lookup"><span data-stu-id="e912d-112">Mobile requests using automatic discovery of Web Services</span></span>

<span data-ttu-id="e912d-113">对于 Lync Server，以下常见要求适用：</span><span class="sxs-lookup"><span data-stu-id="e912d-113">For Lync Server, the following common requirements apply:</span></span>

  - <span data-ttu-id="e912d-114">所有服务器证书都必须支持服务器授权（服务器 EKU）。</span><span class="sxs-lookup"><span data-stu-id="e912d-114">All server certificates must support server authorization (Server EKU).</span></span>

  - <span data-ttu-id="e912d-115">所有服务器证书都必须包含一个 CRL 分发点 (CDP)。</span><span class="sxs-lookup"><span data-stu-id="e912d-115">All server certificates must contain a CRL Distribution Point (CDP).</span></span>

  - <span data-ttu-id="e912d-116">必须使用操作系统支持的签名算法对所有证书进行签名。</span><span class="sxs-lookup"><span data-stu-id="e912d-116">All certificates must be signed using a signing algorithm supported by the operating system.</span></span> <span data-ttu-id="e912d-117">Lync Server 2013 支持 SHA-1 和 SHA-1 套件的摘要大小 (224、256、384和512位) ，并满足或超过操作系统要求。</span><span class="sxs-lookup"><span data-stu-id="e912d-117">Lync Server 2013 supports the SHA-1 and SHA-2 suite of digest sizes (224, 256, 384 and 512-bit), and meets or exceeds the operating system requirements.</span></span> <span data-ttu-id="e912d-118">有关操作系统支持，请参阅 [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002) 。</span><span class="sxs-lookup"><span data-stu-id="e912d-118">For operating system support, see [https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e912d-119">不支持使用 RSASSA-PSS 签名算法，这可能会导致登录和呼叫转发问题，以及其他问题中的错误。</span><span class="sxs-lookup"><span data-stu-id="e912d-119">Using the RSASSA-PSS signature algorithm is unsupported, and may lead to errors on login and call forwarding issues, among other problems.</span></span>

    
    </div>

  - <span data-ttu-id="e912d-120">运行 Lync Server 的内部服务器支持自动注册。</span><span class="sxs-lookup"><span data-stu-id="e912d-120">Auto-enrollment is supported for internal servers running Lync Server.</span></span>

  - <span data-ttu-id="e912d-121">Lync Server Edge 服务器不支持自动注册。</span><span class="sxs-lookup"><span data-stu-id="e912d-121">Auto-enrollment is not supported for Lync Server Edge Servers.</span></span>

  - <span data-ttu-id="e912d-122">向 Windows Server 2003 CA 提交基于 Web 的证书请求时，必须在运行 Windows Server 2003 SP2 或 Windows XP 的计算机上进行提交。</span><span class="sxs-lookup"><span data-stu-id="e912d-122">When you submit a web-based certificate request to a Windows Server 2003 CA, you must submit it from a computer running either Windows Server 2003 with SP2 or Windows XP.</span></span>
    
    <span data-ttu-id="e912d-123">请注意，虽然 KB922706 针对 Windows Server 2003 证书服务 Web 注册为解决 Web 证书注册问题提供支持，但这并不意味着可以使用 Windows Server 2008、Windows Vista 或 Windows 7 从 Windows Server 2003 CA 请求证书。</span><span class="sxs-lookup"><span data-stu-id="e912d-123">Note that although KB922706 provides support for resolving issues with enrolling web certificates against a Windows Server 2003 Certificate Services web enrollment, it does not make it possible to use Windows Server 2008, Windows Vista, or Windows 7 to request a certificate from a Windows Server 2003 CA.</span></span>

  - <span data-ttu-id="e912d-124">支持的加密密钥长度为1024、2048和4096。</span><span class="sxs-lookup"><span data-stu-id="e912d-124">Encryption key lengths of 1024, 2048, and 4096 are supported.</span></span> <span data-ttu-id="e912d-125">建议使用大于或等于2048的密钥长度。</span><span class="sxs-lookup"><span data-stu-id="e912d-125">Key lengths of 2048 and greater are recommended.</span></span>

  - <span data-ttu-id="e912d-126">默认摘要或哈希签名算法为 RSA。</span><span class="sxs-lookup"><span data-stu-id="e912d-126">The default digest, or hash signing, algorithm is RSA.</span></span> <span data-ttu-id="e912d-127">此外， \_ 还支持 ecdh P256、ecdh \_ P384 和 ECDH \_ P521 算法。</span><span class="sxs-lookup"><span data-stu-id="e912d-127">The ECDH\_P256, ECDH\_P384, and ECDH\_P521 algorithms are also supported.</span></span> 

<div>

## <a name="in-this-section"></a><span data-ttu-id="e912d-128">本部分内容</span><span class="sxs-lookup"><span data-stu-id="e912d-128">In This Section</span></span>

  - [<span data-ttu-id="e912d-129">Lync Server 2013 中的内部服务器的证书要求</span><span class="sxs-lookup"><span data-stu-id="e912d-129">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [<span data-ttu-id="e912d-130">Lync Server 2013 中的外部用户访问的证书要求</span><span class="sxs-lookup"><span data-stu-id="e912d-130">Certificate requirements for external user access in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [<span data-ttu-id="e912d-131">Lync Server 2013 中持久聊天服务器的证书要求</span><span class="sxs-lookup"><span data-stu-id="e912d-131">Certificate requirements for Persistent Chat server in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="e912d-132">Lync Server 2013 中的移动性证书要求</span><span class="sxs-lookup"><span data-stu-id="e912d-132">Certificate requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

