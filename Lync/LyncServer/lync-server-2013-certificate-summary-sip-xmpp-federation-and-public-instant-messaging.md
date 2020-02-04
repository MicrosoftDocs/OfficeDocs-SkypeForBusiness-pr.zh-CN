---
title: 证书摘要-SIP、XMPP 联盟和公共即时消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fc3b7a1745d045954fb06403dbb3359fb699a29
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="9f611-102">证书摘要-Lync Server 2013 中的 SIP、XMPP 联盟和公共即时消息</span><span class="sxs-lookup"><span data-stu-id="9f611-102">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f611-103">_**主题上次修改时间：** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="9f611-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="9f611-104">您所需要的用于与 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通信服务器进行联盟的证书通常由您配置、请求和分配给 Edge 服务器的证书满足。</span><span class="sxs-lookup"><span data-stu-id="9f611-104">The certificates that you need for federating with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server will typically be met by the certificates that you configure, request and assign to your Edge Server.</span></span>

<span data-ttu-id="9f611-105">启用和建立与可扩展消息和状态协议（XMPP）合作伙伴的通信的证书要求需要为 XMPP 域添加条目。</span><span class="sxs-lookup"><span data-stu-id="9f611-105">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require addition of entries for your XMPP domains.</span></span> <span data-ttu-id="9f611-106">作为主题备用名称（SAN）包含在证书上的记录将是可参与 XMPP 通信的域。</span><span class="sxs-lookup"><span data-stu-id="9f611-106">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="9f611-107">如果你想要为整个域启用 XMPP，或者可以选择子域（例如 corp.contoso.com，finance.contoso.com），则域可以是根级别的域（例如 contoso.com），如果要为用户的子集启用 XMPP，也可以选择 "子域" （例如、）。</span><span class="sxs-lookup"><span data-stu-id="9f611-107">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<span data-ttu-id="9f611-108">若要配置公共即时消息连接的证书，请注意，与其他 SIP 联合类型或即使是标准边缘服务器证书没有什么不同，不同之处在于美国 Online （AOL）需要证书或证书（在边缘池的大小写）还包含客户端 EKU。</span><span class="sxs-lookup"><span data-stu-id="9f611-108">To configure certificates for public Instant Messaging connectivity, note that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="9f611-109">客户端 EKU 是证书的补充，并且是分配给 Edge 服务器的外部公共证书的一部分。</span><span class="sxs-lookup"><span data-stu-id="9f611-109">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<span data-ttu-id="9f611-110">若要确认你已满足 Edge 服务器部署的正确证书要求，请查看标题为 "**另请参阅**" 的部分中列出的主题。</span><span class="sxs-lookup"><span data-stu-id="9f611-110">To confirm that you have met the correct certificate requirements for your Edge Server deployment, review the topics listed in the section titled **See Also**.</span></span>

<div>



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f611-111">组件</span><span class="sxs-lookup"><span data-stu-id="9f611-111">Component</span></span></th>
<th><span data-ttu-id="9f611-112">主题名称</span><span class="sxs-lookup"><span data-stu-id="9f611-112">Subject name</span></span></th>
<th><span data-ttu-id="9f611-113">主题备用名称（SAN）</span><span class="sxs-lookup"><span data-stu-id="9f611-113">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="9f611-114">备注</span><span class="sxs-lookup"><span data-stu-id="9f611-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f611-115">外部/访问边缘</span><span class="sxs-lookup"><span data-stu-id="9f611-115">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="9f611-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9f611-116">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9f611-117">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9f611-117">sip.contoso.com</span></span></p>
<p><span data-ttu-id="9f611-118">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9f611-118">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="9f611-119">contoso.com</span><span class="sxs-lookup"><span data-stu-id="9f611-119">contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="9f611-120">若要支持 contoso.com XMPP 命名空间</span><span class="sxs-lookup"><span data-stu-id="9f611-120">To support the contoso.com XMPP namespace</span></span>


<p><span data-ttu-id="9f611-121">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9f611-121">sip.fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="9f611-122">支持 fabrikam.com SIP 命名空间</span><span class="sxs-lookup"><span data-stu-id="9f611-122">To support the fabrikam.com SIP namespace</span></span>


<p><span data-ttu-id="9f611-123">fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9f611-123">fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="9f611-124">若要支持 fabrikam.com XMPP 命名空间</span><span class="sxs-lookup"><span data-stu-id="9f611-124">To support the fabrikam.com XMPP namespace</span></span>

</td>
<td><p><span data-ttu-id="9f611-125">证书必须来自公共 CA，并且必须具有服务器 EKU 和客户端 EKU，前提是要部署与 AOL 的公共 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="9f611-125">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="9f611-126">证书已分配给以下对象的外部边缘服务器接口：</span><span class="sxs-lookup"><span data-stu-id="9f611-126">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f611-127">访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="9f611-127">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="9f611-128">Web 会议边缘服务</span><span class="sxs-lookup"><span data-stu-id="9f611-128">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="9f611-129">A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="9f611-129">A/V Edge service</span></span></p></li>
</ul>



> [!NOTE]
> <span data-ttu-id="9f611-130">从技术上讲，证书未分配给 A/V 边缘。</span><span class="sxs-lookup"><span data-stu-id="9f611-130">Technically, a certificate is not assigned to the A/V Edge.</span></span> <span data-ttu-id="9f611-131">安全通信和身份验证通过媒体中继身份验证服务（MRAS）进行管理。</span><span class="sxs-lookup"><span data-stu-id="9f611-131">Secure communication and authentication is managed by way of the Media Relay Authentication Service (MRAS).</span></span> <span data-ttu-id="9f611-132">MRAS 使用分配给 Edge 服务器内部接口的证书。</span><span class="sxs-lookup"><span data-stu-id="9f611-132">MRAS uses the certificate assigned to the Edge Server internal interface.</span></span>


<p><span data-ttu-id="9f611-133">请注意，San 会根据拓扑生成器中的定义自动添加到证书。</span><span class="sxs-lookup"><span data-stu-id="9f611-133">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder.</span></span> <span data-ttu-id="9f611-134">根据需要为其他 SIP 域和其他需要支持的条目添加 SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="9f611-134">You add SAN entries as needed for additional SIP domains and other entries that you need to support.</span></span> <span data-ttu-id="9f611-135">主题名称是在 SAN 中复制的，并且必须存在才能正确操作。</span><span class="sxs-lookup"><span data-stu-id="9f611-135">The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9f611-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f611-136">See Also</span></span>


[<span data-ttu-id="9f611-137">Lync Server 2013 中的示例 XMPP 配置 –  与 Google Talk 的 XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="9f611-137">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="9f611-138">在 Lync Server 2013 中规划边缘服务器证书</span><span class="sxs-lookup"><span data-stu-id="9f611-138">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="9f611-139">Lync Server 2013 中的证书摘要 - 单一合并边缘（使用 NAT 通过专用 IP 地址进行）</span><span class="sxs-lookup"><span data-stu-id="9f611-139">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[<span data-ttu-id="9f611-140">Lync Server 2013 中的证书摘要 - 使用公用 IP 地址的单一合并边缘</span><span class="sxs-lookup"><span data-stu-id="9f611-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[<span data-ttu-id="9f611-141">Lync Server 2013 中的证书摘要 - 扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="9f611-141">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[<span data-ttu-id="9f611-142">Lync Server 2013 中的证书摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="9f611-142">Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[<span data-ttu-id="9f611-143">Lync Server 2013 中的证书摘要 - 使用硬件负载平衡器的扩展的合并边缘</span><span class="sxs-lookup"><span data-stu-id="9f611-143">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

