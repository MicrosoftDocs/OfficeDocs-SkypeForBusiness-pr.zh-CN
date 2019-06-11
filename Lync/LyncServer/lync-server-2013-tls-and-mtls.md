---
title: 'Lync Server 2013: TLS 和 MTLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 066612f08c61ad1df342b4f2dd9b61ff5a5cc286
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a><span data-ttu-id="3cf61-102">Lync Server 2013 的 TLS 和 MTLS</span><span class="sxs-lookup"><span data-stu-id="3cf61-102">TLS and MTLS for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cf61-103">_**主题上次修改时间:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="3cf61-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="3cf61-104">传输层安全性 (TLS) 和相互传输层安全性 (MTLS) 协议提供 Internet 上的加密通信和终结点身份验证。</span><span class="sxs-lookup"><span data-stu-id="3cf61-104">Transport Layer Security (TLS) and Mutual Transport Layer Security (MTLS) protocols provide encrypted communications and endpoint authentication on the Internet.</span></span> <span data-ttu-id="3cf61-105">Microsoft Lync Server 2013 使用这两个协议创建受信任服务器的网络, 并确保通过该网络的所有通信均已加密。</span><span class="sxs-lookup"><span data-stu-id="3cf61-105">Microsoft Lync Server 2013 uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted.</span></span> <span data-ttu-id="3cf61-106">服务器之间的所有 SIP 通信都通过 MTLS 进行。</span><span class="sxs-lookup"><span data-stu-id="3cf61-106">All SIP communications between servers occur over MTLS.</span></span> <span data-ttu-id="3cf61-107">从客户端到服务器的 SIP 通信都通过 TLS 进行。</span><span class="sxs-lookup"><span data-stu-id="3cf61-107">SIP communications from client to server occur over TLS.</span></span>

<span data-ttu-id="3cf61-108">TLS 允许用户通过其客户端软件对其连接到的 Lync Server 2013 服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="3cf61-108">TLS enables users, through their client software, to authenticate the Lync Server 2013 servers to which they connect.</span></span> <span data-ttu-id="3cf61-109">在 TLS 连接上，客户端从服务器请求有效证书。</span><span class="sxs-lookup"><span data-stu-id="3cf61-109">On a TLS connection, the client requests a valid certificate from the server.</span></span> <span data-ttu-id="3cf61-110">有效证书必须满足以下条件：由受客户端信任的 CA 颁发，且服务器的 DNS 名称必须与证书上的 DNS 名称一致。</span><span class="sxs-lookup"><span data-stu-id="3cf61-110">To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate.</span></span> <span data-ttu-id="3cf61-111">如果证书有效，则客户端使用证书中的公钥对用于通信的对称加密密钥进行加密，因此只有证书的原始所有者可以使用其私钥对通信内容进行解密。</span><span class="sxs-lookup"><span data-stu-id="3cf61-111">If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication.</span></span> <span data-ttu-id="3cf61-112">生成的连接将会受到信任，之后再不会受到其他受信任的服务器或客户端的质询。</span><span class="sxs-lookup"><span data-stu-id="3cf61-112">The resulting connection is trusted and from that point is not challenged by other trusted servers or clients.</span></span> <span data-ttu-id="3cf61-113">在此上下文中，可将用于 Web 服务的安全套接字层 (SSL) 视为是基于 TLS 的。</span><span class="sxs-lookup"><span data-stu-id="3cf61-113">Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.</span></span>

<span data-ttu-id="3cf61-114">服务器到服务器的连接依赖 MTLS 来进行相互身份验证。</span><span class="sxs-lookup"><span data-stu-id="3cf61-114">Server-to-server connections rely on MTLS for mutual authentication.</span></span> <span data-ttu-id="3cf61-115">在 MTLS 连接上，发出消息的服务器和接收消息的服务器交换来自相互信任的 CA 的证书。</span><span class="sxs-lookup"><span data-stu-id="3cf61-115">On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA.</span></span> <span data-ttu-id="3cf61-116">证书可向一台服务器证明另一台服务器的身份。</span><span class="sxs-lookup"><span data-stu-id="3cf61-116">The certificates prove the identity of each server to the other.</span></span> <span data-ttu-id="3cf61-117">在 Lync Server 2013 部署中, 由所有内部客户端和服务器 (由于 Active Directory 域的所有成员) 在其有效期内颁发的企业 CA 颁发的证书被自动视为有效的所有内部客户端和服务器。信任该域中的企业 CA。</span><span class="sxs-lookup"><span data-stu-id="3cf61-117">In Lync Server 2013 deployments, certificates issued by the enterprise CA that are during their validity period and not revoked by the issuing CA are automatically considered valid by all internal clients and servers because all members of an Active Directory domain trust the Enterprise CA in that domain.</span></span> <span data-ttu-id="3cf61-118">在联盟方案中，发证 CA 必须得到联盟伙伴双方的信任。</span><span class="sxs-lookup"><span data-stu-id="3cf61-118">In federated scenarios, the issuing CA must be trusted by both federated partners.</span></span> <span data-ttu-id="3cf61-119">如果需要，任一伙伴均可以使用不同的 CA，只要该 CA 同时获得另一个伙伴的信任即可。</span><span class="sxs-lookup"><span data-stu-id="3cf61-119">Each partner can use a different CA, if desired, so long as that CA is also trusted by the other partner.</span></span> <span data-ttu-id="3cf61-120">通过在边缘服务器的受信任的根 CA 中包含伙伴的根 CA 证书，或通过使用双方信任的第三方 CA，可以很轻松地建立此信任。</span><span class="sxs-lookup"><span data-stu-id="3cf61-120">This trust is most easily accomplished by the Edge Servers having the partner’s root CA certificate in their trusted root CAs, or by use of a third-party CA that is trusted by both parties.</span></span>

<span data-ttu-id="3cf61-121">TLS 和 MTLS 有助于防止窃听攻击和中间人攻击。</span><span class="sxs-lookup"><span data-stu-id="3cf61-121">TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks.</span></span> <span data-ttu-id="3cf61-122">在中间人攻击中，攻击者将通过其计算机重新路由两个网络实体之间的通信，而这两个网络实体对此毫不知情。</span><span class="sxs-lookup"><span data-stu-id="3cf61-122">In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party.</span></span> <span data-ttu-id="3cf61-123">TLS 和 Lync Server 2013 规范的受信任服务器 (仅在拓扑生成器中指定的服务器) 可通过使用公钥加密协调的端到端加密来减少部分在应用程序层上受到中间人攻击的风险在两个终结点之间, 攻击者必须拥有具有相应私钥的有效且受信任的证书, 并将该证书颁发给客户进行通信的服务的名称以解密通信。</span><span class="sxs-lookup"><span data-stu-id="3cf61-123">TLS and Lync Server 2013 specification of trusted servers (only those specified in Topology Builder) mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication.</span></span> <span data-ttu-id="3cf61-124">不过，最终，您还是必须遵循有关您的网络基础结构（在此示例中为企业 DNS）的最佳安全做法。</span><span class="sxs-lookup"><span data-stu-id="3cf61-124">Ultimately, however, you must follow best security practices with your networking infrastructure (in this case corporate DNS).</span></span> <span data-ttu-id="3cf61-125">Lync Server 2013 假定 DNS 服务器的信任方式与域控制器和全局编录的信任方式相同, 但 DNS 确实提供了针对 DNS 劫持攻击的保护级别, 防止攻击者的服务器成功响应申请哄骗名称。</span><span class="sxs-lookup"><span data-stu-id="3cf61-125">Lync Server 2013 assumes that the DNS server is trusted in the same way that domain controllers and global catalogs are trusted, but DNS does provide a level of safeguard against DNS hijack attacks by preventing an attacker’s server from responding successfully to a request to the spoofed name.</span></span>

<span data-ttu-id="3cf61-126">下图显示了 Lync Server 2013 如何使用 MTLS 创建受信任服务器网络的高级别。</span><span class="sxs-lookup"><span data-stu-id="3cf61-126">The following figure shows at a high level how Lync Server 2013 uses MTLS to create a network of trusted servers.</span></span>

<span data-ttu-id="3cf61-127">**Lync Server 网络中的受信任连接**</span><span class="sxs-lookup"><span data-stu-id="3cf61-127">**Trusted connections in a Lync Server network**</span></span>

<span data-ttu-id="3cf61-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span><span class="sxs-lookup"><span data-stu-id="3cf61-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

