---
title: Lync Server 2013：常见安全威胁在现代日计算中
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dffff9cfbc501a8e6a9a79439183966ef0a1956
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a><span data-ttu-id="a2fc6-102">现代的日期计算中的常见安全威胁</span><span class="sxs-lookup"><span data-stu-id="a2fc6-102">Common security threats in modern day computing</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2fc6-103">_**上次修改的主题：** 2013-09-10_</span><span class="sxs-lookup"><span data-stu-id="a2fc6-103">_**Topic Last Modified:** 2013-09-10_</span></span>

<span data-ttu-id="a2fc6-104">由于 Lync Server 2013 是企业级通信系统，因此应注意可能影响其基础结构和通信的常见安全攻击。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-104">Because Lync Server 2013 is an enterprise-class communications system, you should be aware of common security attacks that could affect its infrastructure and communications.</span></span>

<div>

## <a name="compromised-key-attack"></a><span data-ttu-id="a2fc6-105">破解密钥攻击</span><span class="sxs-lookup"><span data-stu-id="a2fc6-105">Compromised-Key Attack</span></span>

<span data-ttu-id="a2fc6-106">密钥是用于加密、解密或验证机密信息的机密代码或数字。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-106">A key is a secret code or number that is used to encrypt, decrypt, or validate secret information.</span></span> <span data-ttu-id="a2fc6-107">必须考虑在公钥基础结构（PKI）中使用两个敏感密钥：。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-107">There are two sensitive keys in use in public key infrastructure (PKI) that must be considered: .</span></span>

  - <span data-ttu-id="a2fc6-108">每个证书持有者拥有的私钥</span><span class="sxs-lookup"><span data-stu-id="a2fc6-108">The private key that each certificate holder has</span></span>

  - <span data-ttu-id="a2fc6-109">在通信合作伙伴成功进行身份验证和会话密钥交换之后使用的会话密钥</span><span class="sxs-lookup"><span data-stu-id="a2fc6-109">The session key that is used after a successful identification and session key exchange by the communicating partners</span></span>

<span data-ttu-id="a2fc6-110">破解密钥攻击是指攻击者破解私钥或会话密钥的行为。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-110">A compromised-key attack occurs when the attacker determines the private key or the session key.</span></span> <span data-ttu-id="a2fc6-111">攻击者在成功破解密钥之后，可以使用此密钥对已加密的数据进行解密，而数据的发送者对此毫不知情。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-111">When the attacker is successful in determining the key, the attacker can use the key to decrypt encrypted data without the knowledge of the sender.</span></span>

<span data-ttu-id="a2fc6-112">Lync Server 2013 使用 Windows Server 操作系统中的 PKI 功能来保护用于加密传输层安全性（TLS）连接的密钥数据。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-112">Lync Server 2013 uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="a2fc6-113">用于媒体加密的密钥通过 TLS 连接进行交换。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-113">The keys used for media encryption are exchanged over TLS connections.</span></span>

</div>

<div>

## <a name="network-denial-of-service-attack"></a><span data-ttu-id="a2fc6-114">网络拒绝服务攻击</span><span class="sxs-lookup"><span data-stu-id="a2fc6-114">Network Denial-of-Service Attack</span></span>

<span data-ttu-id="a2fc6-115">当攻击者阻止正常网络使用和有效用户正常运行时，会发生*拒绝服务攻击*。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-115">The *denial-of-service attack* occurs when the attacker prevents normal network use and function by valid users.</span></span> <span data-ttu-id="a2fc6-116">这是在攻击者使用严重请求使服务与合法用户一起使用服务的合法请求一起完成时实现的。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-116">This is done when the attacker floods the service with legitimate requests that overwhelm the use of the service by legitimate users.</span></span> <span data-ttu-id="a2fc6-117">通过使用拒绝服务攻击，攻击者可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a2fc6-117">By using a denial-of-service attack, the attacker can do the following:</span></span>

  - <span data-ttu-id="a2fc6-118">向受到攻击的网络中正在运行的应用程序和服务发送无效数据，干扰它们的正常工作。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-118">Send invalid data to applications and services running in the attacked network to disrupt their normal function.</span></span>

  - <span data-ttu-id="a2fc6-119">发送大量流量以造成系统过载，直到系统停止对合理请求做出响应或对合理请求做出响应的速度变得很慢。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-119">Send a large amount of traffic, overloading the system until it stops responding or responds slowly to legitimate requests.</span></span>

  - <span data-ttu-id="a2fc6-120">隐藏攻击证据。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-120">Hide the evidence of the attacks.</span></span>

  - <span data-ttu-id="a2fc6-121">阻止用户访问网络资源。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-121">Prevent users from accessing network resources.</span></span>

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a><span data-ttu-id="a2fc6-122">窃听（嗅探、窥探）</span><span class="sxs-lookup"><span data-stu-id="a2fc6-122">Eavesdropping (Sniffing, Snooping)</span></span>

<span data-ttu-id="a2fc6-123">当攻击者获得对网络中数据路径的访问权限并能够监控和读取流量时，可能会发生*窃听*。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-123">*Eavesdropping* can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic.</span></span> <span data-ttu-id="a2fc6-124">这也称为 "*嗅探*" 或 "*窥探*"。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-124">This is also called *sniffing* or *snooping*.</span></span> <span data-ttu-id="a2fc6-125">如果流量内容采用纯文本形式，则攻击者在获取路径的访问权之后即可读取流量内容。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-125">If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path.</span></span> <span data-ttu-id="a2fc6-126">例如，通过控制数据路径上的路由器进行攻击。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-126">An example is an attack performed by controlling a router on the data path.</span></span>

<span data-ttu-id="a2fc6-127">Microsoft Lync Server 2013 中的流量的默认建议和设置是在受信任的服务器和从客户端到服务器之间的 TLS 之间使用相互 TLS （MTLS）。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-127">The default recommendation and setting for traffic within Microsoft Lync Server 2013 is to use mutual TLS (MTLS) between trusted servers and TLS from client to server.</span></span> <span data-ttu-id="a2fc6-128">此保护措施将使得攻击非常困难，或者在给定对话发生的时间段内无法实现。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-128">This protective measure would make an attack very difficult or impossible to achieve within the time period in which a given conversation occurs.</span></span> <span data-ttu-id="a2fc6-129">TLS 可对各方执行身份验证，并对所有流量内容进行加密。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-129">TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="a2fc6-130">这样不能阻止窃听，但攻击者不能读取流量内容，除非破坏加密。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-130">This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.</span></span>

<span data-ttu-id="a2fc6-131">使用中继 NAT （TURN）协议的遍历不会要求加密通信，并且要发送的信息受消息完整性保护。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-131">The Traversal Using Relay NAT (TURN) protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity.</span></span> <span data-ttu-id="a2fc6-132">尽管它是开放的，但它发送的信息（即 IP 地址和端口）可以直接提取，只需查看数据包的源地址和目标地址即可。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-132">Although it is open to eavesdropping, the information it is sending (that is, the IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets.</span></span> <span data-ttu-id="a2fc6-133">A/V 边缘服务可确保数据有效，方法是使用从少数几个项目派生的密钥检查邮件的消息完整性，包括密码（从不以明文形式发送）。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-133">The A/V Edge service ensures that the data is valid by checking the Message Integrity of the message by using the key derived from a few items, including a TURN password, which is never sent in clear text.</span></span> <span data-ttu-id="a2fc6-134">如果使用安全实时协议（SRTP），则媒体流量也会进行加密。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-134">If Secure Real Time Protocol (SRTP) is used, media traffic is also encrypted.</span></span>

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a><span data-ttu-id="a2fc6-135">身份欺骗（IP 地址欺骗）</span><span class="sxs-lookup"><span data-stu-id="a2fc6-135">Identity Spoofing (IP Address Spoofing)</span></span>

<span data-ttu-id="a2fc6-136">当攻击者在未经授权的情况下确定和使用网络、计算机或网络组件的 IP 地址时，会发生*欺骗*。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-136">*Spoofing* occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so.</span></span> <span data-ttu-id="a2fc6-137">一旦攻击成功，攻击者便可以假借 IP 地址通常标识的实体的身份执行操作。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-137">A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address.</span></span> <span data-ttu-id="a2fc6-138">在 Microsoft Lync Server 2013 的上下文中，仅当管理员已执行以下两项操作时，才会发生这种情况：</span><span class="sxs-lookup"><span data-stu-id="a2fc6-138">Within the context of Microsoft Lync Server 2013, this situation comes into play only if an administrator has done both of the following:</span></span>

  - <span data-ttu-id="a2fc6-139">已配置仅支持传输控制协议 (TCP) 的连接（建议不要这样做，因为 TCP 通信未经过加密）。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-139">Configured connections that support only Transmission Control Protocol (TCP) (which is not recommended, because TCP communications are unencrypted).</span></span>

  - <span data-ttu-id="a2fc6-140">将这些连接的 IP 地址标记为受信任的主机。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-140">Marked the IP addresses of those connections as trusted hosts.</span></span>

<span data-ttu-id="a2fc6-141">此操作对于传输层安全性 (TLS) 连接而言不成问题，因为 TLS 对所有方进行验证并加密所有通信。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-141">This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="a2fc6-142">使用 TLS 可防止攻击者对特定连接（例如，相互 TLS 连接）执行 IP 地址欺骗攻击。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-142">Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections).</span></span> <span data-ttu-id="a2fc6-143">但是，攻击者仍然可以哄骗 Lync Server 2013 使用的 DNS 服务器的地址。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-143">But an attacker could still spoof the address of the DNS server that Lync Server 2013 uses.</span></span> <span data-ttu-id="a2fc6-144">但是，因为 Lync 中的身份验证是通过证书执行的，所以攻击者将没有欺骗通信中的任何一方所需的有效证书。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-144">However, because authentication in Lync is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.</span></span>

</div>

<div>

## <a name="man-in-the-middle-attack"></a><span data-ttu-id="a2fc6-145">中间人攻击</span><span class="sxs-lookup"><span data-stu-id="a2fc6-145">Man-in-the-Middle Attack</span></span>

<span data-ttu-id="a2fc6-146">当攻击者在发生通信的两个用户不知情的情况下，通过自己的计算机重新路由这两个用户之间的通信时，就会发生中间人攻击。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-146">A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users.</span></span> <span data-ttu-id="a2fc6-147">攻击者可以在将通信内容发送到预期接收人之前监控和读取通信内容。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-147">The attacker can monitor and read the traffic before sending it on to the intended recipient.</span></span> <span data-ttu-id="a2fc6-148">通信中的每个用户在不知情的情况下向攻击者发送通信和从攻击者接收通信，还以为自己只是在与预期用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-148">Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user.</span></span> <span data-ttu-id="a2fc6-149">如果攻击者可修改 Active Directory 域服务以将他（她）的服务器添加为受信任服务器或修改域名系统 (DNS) 以让客户端在与服务器通信时通过攻击者，则会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-149">This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server.</span></span> <span data-ttu-id="a2fc6-150">在两个客户端之间的媒体通信也会发生中间人攻击。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-150">A man-in-the-middle attack can also occur with media traffic between two clients.</span></span> <span data-ttu-id="a2fc6-151">但是，在 Microsoft Lync Server 2013 点到点音频、视频和应用程序共享中，流使用 SRTP 进行了加密，在使用通过 TLS 的会话初始协议（SIP）的对等方之间协商的加密密钥。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-151">However, in Microsoft Lync Server 2013 point-to-point audio, video, and application sharing, streams are encrypted with SRTP, using cryptographic keys that are negotiated between the peers that are using Session Initiation Protocol (SIP) over TLS.</span></span> <span data-ttu-id="a2fc6-152">诸如 Group Chat 的服务器使用 HTTPS 来增强 Web 通信的安全性。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-152">Servers such as Group Chat make use of HTTPS to enhance the security of web traffic.</span></span>

</div>

<div>

## <a name="rtp-replay-attack"></a><span data-ttu-id="a2fc6-153">RTP 重播攻击</span><span class="sxs-lookup"><span data-stu-id="a2fc6-153">RTP Replay Attack</span></span>

<span data-ttu-id="a2fc6-154">当两方之间的有效媒体传输因恶意目的而被截取和重新传输时，会发生*重播攻击*。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-154">A *replay attack* occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes.</span></span> <span data-ttu-id="a2fc6-155">通过允许接收人维护已收到的 RTP 数据包的索引并将每个新数据包与索引中已列出的数据包加以比较，安全信号协议连接中使用的 SRTP 可保护传输免受重播攻击。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-155">SRTP used in connection with a secure signaling protocol protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.</span></span>

</div>

<div>

## <a name="spim"></a><span data-ttu-id="a2fc6-156">Spim</span><span class="sxs-lookup"><span data-stu-id="a2fc6-156">Spim</span></span>

<span data-ttu-id="a2fc6-157">*Spim*是未经请求的商业即时消息或状态订阅请求。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-157">*Spim* is unsolicited commercial instant messages or presence subscription requests.</span></span> <span data-ttu-id="a2fc6-158">虽然 Spim 本身并不会导致网络问题，但至少会有些烦人，占用资源和生产时间，而且可能会导致网络问题。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-158">While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network.</span></span> <span data-ttu-id="a2fc6-159">例如，用户通过发送请求相互发送垃圾消息。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-159">An example of this is users spimming each other by sending requests.</span></span> <span data-ttu-id="a2fc6-160">用户可以相互阻止对方来防止出现这种情况，但对于联盟，如果建立了协作的 Spim 攻击，则很难防止出现这种情况，除非您禁用联盟伙伴关系。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-160">Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.</span></span>

</div>

<div>

## <a name="viruses-and-worms"></a><span data-ttu-id="a2fc6-161">病毒和蠕虫</span><span class="sxs-lookup"><span data-stu-id="a2fc6-161">Viruses and Worms</span></span>

<span data-ttu-id="a2fc6-162">*病毒*是一种代码单元，其目的是复制其他类似的代码单元。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-162">A *virus* is a unit of code whose purpose is to reproduce additional, similar code units.</span></span> <span data-ttu-id="a2fc6-163">病毒需要像文件、电子邮件或程序这样的宿主才能发挥作用。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-163">To work, a virus needs a host, such as a file, email, or program.</span></span> <span data-ttu-id="a2fc6-164">*蠕虫*是一种代码单元，其目的是复制其他类似的代码单元，但它不需要主机。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-164">A *worm* is a unit of code whose purpose is to reproduce additional, similar code units, but it does not need a host.</span></span> <span data-ttu-id="a2fc6-165">病毒和蠕虫主要是在客户端之间传送文件期间或从其他用户发送 URL 时出现。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-165">Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users.</span></span> <span data-ttu-id="a2fc6-166">例如，如果您的计算机上存在某种病毒，则该病毒可使用您的身份代表您发送即时消息。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-166">If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf.</span></span>

</div>

<div>

## <a name="personally-identifiable-information"></a><span data-ttu-id="a2fc6-167">个人身份信息</span><span class="sxs-lookup"><span data-stu-id="a2fc6-167">Personally Identifiable Information</span></span>

<span data-ttu-id="a2fc6-168">Microsoft Lync Server 2013 可能会泄露可链接到个人的公共网络的信息。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-168">Microsoft Lync Server 2013 has the potential to disclose information over a public network that might be able to be linked to an individual.</span></span> <span data-ttu-id="a2fc6-169">这些信息类型具体可分为两大类：</span><span class="sxs-lookup"><span data-stu-id="a2fc6-169">The information types can be broken down to two specific categories:</span></span>

  - <span data-ttu-id="a2fc6-170">**增强状态数据**增强状态数据是指用户可以选择共享或不共享到联盟伙伴或组织内联系人的链接的信息。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-170">**Enhanced presence data** Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization.</span></span> <span data-ttu-id="a2fc6-171">不与公用 IM 网络上的用户共享此数据。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-171">This data is not shared with users on a public IM network.</span></span> <span data-ttu-id="a2fc6-172">客户端策略和其他客户端配置可能会为系统管理员提供一些控制能力。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-172">Client policies and other client configuration may put some control with the system administrator.</span></span> <span data-ttu-id="a2fc6-173">在 Lync Server 2013 中，可为单个用户配置 "增强状态" 隐私模式，以防止 Lync 用户不在用户的 "联系人" 列表中查看用户的状态信息。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-173">In Lync Server 2013, enhanced presence privacy mode can be configured for an individual user to prevent Lync users not on the user’s Contacts list from seeing the user’s presence information.</span></span> <span data-ttu-id="a2fc6-174">增强状态隐私模式不会阻止 Microsoft Office Communicator 2007 和 Microsoft Office Communicator 2007 R2 的用户看到用户的状态信息。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-174">Enhanced presence privacy mode does not prevent users of Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2 from seeing a user’s presence information.</span></span> <span data-ttu-id="a2fc6-175">有关详细信息，请参阅部署文档中的入门文档和[在 Lync server 2013 中配置增强状态隐私模式](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)中的[客户端的新增功能： lync server 2013](lync-server-2013-what-s-new-for-clients.md) 。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-175">For details, see [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in the Getting Started documentation and [Configuring enhanced presence privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="a2fc6-176">**必需数据**必需的数据是服务器或客户端的正确操作所必需的，不受客户端或系统管理的控制。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-176">**Mandatory data** Mandatory data is required for the proper operation of the server or the client and is NOT under the control of the client or system administration.</span></span> <span data-ttu-id="a2fc6-177">对于路由、状态维护和信号传输而言，此信息是必需的服务器或网络级别信息。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-177">This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling.</span></span>

<span data-ttu-id="a2fc6-178">下表列出了通过公用网络公开的数据。</span><span class="sxs-lookup"><span data-stu-id="a2fc6-178">The following tables list the data that is exposed over a public network.</span></span>

### <a name="enhanced-presence-data"></a><span data-ttu-id="a2fc6-179">增强状态数据</span><span class="sxs-lookup"><span data-stu-id="a2fc6-179">Enhanced Presence Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2fc6-180">数据泄露</span><span class="sxs-lookup"><span data-stu-id="a2fc6-180">Data Disclosed</span></span></th>
<th><span data-ttu-id="a2fc6-181">可能的设置</span><span class="sxs-lookup"><span data-stu-id="a2fc6-181">Possible Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2fc6-182">个人数据</span><span class="sxs-lookup"><span data-stu-id="a2fc6-182">Personal Data</span></span></p></td>
<td><p><span data-ttu-id="a2fc6-183">名称、职务、公司、电子邮件地址、时区</span><span class="sxs-lookup"><span data-stu-id="a2fc6-183">Name, Title, Company, Email Address, Time Zone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2fc6-184">电话号码</span><span class="sxs-lookup"><span data-stu-id="a2fc6-184">Telephone Numbers</span></span></p></td>
<td><p><span data-ttu-id="a2fc6-185">工作电话号码、手机号码、住宅电话号码</span><span class="sxs-lookup"><span data-stu-id="a2fc6-185">Work, Mobile, Home</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2fc6-186">日历信息</span><span class="sxs-lookup"><span data-stu-id="a2fc6-186">Calendar Information</span></span></p></td>
<td><p><span data-ttu-id="a2fc6-187">忙/闲、不在城镇通知、会议详细信息（对具有日历访问权限的用户）</span><span class="sxs-lookup"><span data-stu-id="a2fc6-187">Free/Busy, Out-Of-Town Notice, Meeting Details (to those who have access to your calendar)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2fc6-188">状态</span><span class="sxs-lookup"><span data-stu-id="a2fc6-188">Presence Status</span></span></p></td>
<td><p><span data-ttu-id="a2fc6-189">离开、空闲、忙碌、请勿打扰、脱机</span><span class="sxs-lookup"><span data-stu-id="a2fc6-189">Away, Available, Busy, Do Not Disturb, Offline</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a><span data-ttu-id="a2fc6-190">必需数据</span><span class="sxs-lookup"><span data-stu-id="a2fc6-190">Mandatory Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a2fc6-191">数据泄露</span><span class="sxs-lookup"><span data-stu-id="a2fc6-191">Data Disclosed</span></span></th>
<th><span data-ttu-id="a2fc6-192">示例信息</span><span class="sxs-lookup"><span data-stu-id="a2fc6-192">Example Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2fc6-193">IP 地址</span><span class="sxs-lookup"><span data-stu-id="a2fc6-193">IP Address</span></span></p></td>
<td><p><span data-ttu-id="a2fc6-194">计算机的实际地址或经过 NAT 转换的地址</span><span class="sxs-lookup"><span data-stu-id="a2fc6-194">Actual address of computer or NATed address</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2fc6-195">SIP URI</span><span class="sxs-lookup"><span data-stu-id="a2fc6-195">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="a2fc6-196">jeremylos@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a2fc6-196">jeremylos@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

