---
title: 证书摘要-SIP、XMPP 联合身份验证和公共即时消息
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
ms.openlocfilehash: 284a633a2c5ce820009c6672058837bbecb7ecd6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517869"
---
# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="d3df5-102">Lync Server 2013 中的证书摘要-SIP、XMPP 联合身份验证和公共即时消息</span><span class="sxs-lookup"><span data-stu-id="d3df5-102">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3df5-103">_**上次修改的主题：** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="d3df5-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="d3df5-104">您需要用于与 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通信服务器进行联盟的证书通常由您配置的证书满足，请求并分配给您的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="d3df5-104">The certificates that you need for federating with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server will typically be met by the certificates that you configure, request and assign to your Edge Server.</span></span>

<span data-ttu-id="d3df5-105">启用和建立与可扩展邮件和状态协议 (XMPP) 合作伙伴的通信的证书要求需要添加 XMPP 域的条目。</span><span class="sxs-lookup"><span data-stu-id="d3df5-105">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require addition of entries for your XMPP domains.</span></span> <span data-ttu-id="d3df5-106">作为使用者替代名称 (SAN) 包含在证书上的记录将成为可以参与 XMPP 通信的域。</span><span class="sxs-lookup"><span data-stu-id="d3df5-106">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="d3df5-107">如果要针对整个域启用 XMPP，则该域可以是根级别域（例如，contoso.com），或者如果要针对用户的子集启用 XMPP，该域也可以是选定的子域（例如，corp.contoso.com、finance.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="d3df5-107">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<span data-ttu-id="d3df5-108">若要为公用即时消息连接配置证书，请注意，与其他 SIP 联合类型或甚至标准边缘服务器证书没有什么不同，只是在边缘池 (AOL) 需要证书或证书 (在边缘池) 也包含客户端 EKU 的情况下。</span><span class="sxs-lookup"><span data-stu-id="d3df5-108">To configure certificates for public Instant Messaging connectivity, note that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="d3df5-109">客户端 EKU 是对证书的补充，并且是分配给边缘服务器的外部公用证书的一部分。</span><span class="sxs-lookup"><span data-stu-id="d3df5-109">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<span data-ttu-id="d3df5-110">若要确认您已满足边缘服务器部署的正确证书要求，请查看标题为 " **另请参阅**" 的部分中列出的主题。</span><span class="sxs-lookup"><span data-stu-id="d3df5-110">To confirm that you have met the correct certificate requirements for your Edge Server deployment, review the topics listed in the section titled **See Also**.</span></span>

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
<th><span data-ttu-id="d3df5-111">组件</span><span class="sxs-lookup"><span data-stu-id="d3df5-111">Component</span></span></th>
<th><span data-ttu-id="d3df5-112">使用者名称</span><span class="sxs-lookup"><span data-stu-id="d3df5-112">Subject name</span></span></th>
<th><span data-ttu-id="d3df5-113">使用者替代名称 (SAN)</span><span class="sxs-lookup"><span data-stu-id="d3df5-113">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="d3df5-114">Comments</span><span class="sxs-lookup"><span data-stu-id="d3df5-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3df5-115">访问/边缘外部</span><span class="sxs-lookup"><span data-stu-id="d3df5-115">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="d3df5-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d3df5-116">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d3df5-117">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d3df5-117">sip.contoso.com</span></span></p>
<p><span data-ttu-id="d3df5-118">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d3df5-118">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="d3df5-119">contoso.com</span><span class="sxs-lookup"><span data-stu-id="d3df5-119">contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="d3df5-120">支持 contoso.com XMPP 命名空间</span><span class="sxs-lookup"><span data-stu-id="d3df5-120">To support the contoso.com XMPP namespace</span></span>


<p><span data-ttu-id="d3df5-121">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d3df5-121">sip.fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="d3df5-122">支持 fabrikam.com SIP 命名空间</span><span class="sxs-lookup"><span data-stu-id="d3df5-122">To support the fabrikam.com SIP namespace</span></span>


<p><span data-ttu-id="d3df5-123">fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d3df5-123">fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="d3df5-124">支持 fabrikam.com XMPP 命名空间</span><span class="sxs-lookup"><span data-stu-id="d3df5-124">To support the fabrikam.com XMPP namespace</span></span>

</td>
<td><p><span data-ttu-id="d3df5-125">证书必须来自公共 CA，并且必须具有服务器 EKU 和客户端 EKU （如果要部署具有 AOL 的公共 IM 连接）。</span><span class="sxs-lookup"><span data-stu-id="d3df5-125">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="d3df5-126">将证书分配给外部边缘服务器接口：</span><span class="sxs-lookup"><span data-stu-id="d3df5-126">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="d3df5-127">Access Edge service － 访问边缘服务</span><span class="sxs-lookup"><span data-stu-id="d3df5-127">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="d3df5-128">Web 会议边缘服务</span><span class="sxs-lookup"><span data-stu-id="d3df5-128">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="d3df5-129">A/V 边缘服务</span><span class="sxs-lookup"><span data-stu-id="d3df5-129">A/V Edge service</span></span></p></li>
</ul>



> [!NOTE]
> <span data-ttu-id="d3df5-130">从技术上讲，证书未分配给 A/V 边缘。</span><span class="sxs-lookup"><span data-stu-id="d3df5-130">Technically, a certificate is not assigned to the A/V Edge.</span></span> <span data-ttu-id="d3df5-131">通过媒体中继身份验证服务 (/MRAS) 来管理安全通信和身份验证。</span><span class="sxs-lookup"><span data-stu-id="d3df5-131">Secure communication and authentication is managed by way of the Media Relay Authentication Service (MRAS).</span></span> <span data-ttu-id="d3df5-132">/MRAS 使用分配给边缘服务器内部接口的证书。</span><span class="sxs-lookup"><span data-stu-id="d3df5-132">MRAS uses the certificate assigned to the Edge Server internal interface.</span></span>


<p><span data-ttu-id="d3df5-p105">请注意，根据拓扑生成器中的定义，SAN 将自动添加到证书中。根据需要为其他 SIP 域和其他需要支持的条目添加 SAN 条目。将在 SAN 中复制使用者名称，并且该名称必须在正确的操作中显示。</span><span class="sxs-lookup"><span data-stu-id="d3df5-p105">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d3df5-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3df5-136">See Also</span></span>


[<span data-ttu-id="d3df5-137">Lync Server 2013 中的示例 XMPP 配置–与 Google 对话的 XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="d3df5-137">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="d3df5-138">在 Lync Server 2013 中规划边缘服务器证书</span><span class="sxs-lookup"><span data-stu-id="d3df5-138">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="d3df5-139">Lync Server 2013 中的证书摘要-使用 NAT 的专用 IP 地址的单一合并边缘</span><span class="sxs-lookup"><span data-stu-id="d3df5-139">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[<span data-ttu-id="d3df5-140">Lync Server 2013 中的证书摘要-使用公用 IP 地址的单一合并边缘</span><span class="sxs-lookup"><span data-stu-id="d3df5-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[<span data-ttu-id="d3df5-141">Lync Server 2013 中的证书摘要-扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="d3df5-141">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[<span data-ttu-id="d3df5-142">Lync Server 2013 中的证书摘要-扩展的合并边缘（使用公用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="d3df5-142">Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[<span data-ttu-id="d3df5-143">Lync Server 2013 中的证书摘要-使用硬件负载平衡器的扩展的合并边缘</span><span class="sxs-lookup"><span data-stu-id="d3df5-143">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

