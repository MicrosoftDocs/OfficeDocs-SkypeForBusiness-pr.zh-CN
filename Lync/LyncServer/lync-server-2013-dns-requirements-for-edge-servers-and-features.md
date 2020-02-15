---
title: Lync Server 2013：边缘服务器和功能的 DNS 要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Edge Servers and features
ms:assetid: e3bf05c8-96fb-4dd2-acb1-f0d141c9e2ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721912(v=OCS.15)
ms:contentKeyID: 49733846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd9c14de1b25125e94a3019b4e3dcdbd192cbb13
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-edge-servers-and-features-in-lync-server-2013"></a><span data-ttu-id="aa3f1-102">Lync Server 2013 中的边缘服务器和功能的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="aa3f1-102">DNS requirements for Edge Servers and features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa3f1-103">_**上次修改的主题：** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="aa3f1-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="aa3f1-104">Lync Server 2013 边缘服务器、边缘池和反向代理对域名系统（DNS）记录有特定的要求。</span><span class="sxs-lookup"><span data-stu-id="aa3f1-104">Lync Server 2013 Edge Servers, Edge pools, and reverse proxies have specific requirements for Domain Name System (DNS) records.</span></span> <span data-ttu-id="aa3f1-105">在 Lync Server 2013 中，如果使用 IPv4 和 IPv6，则必须规划主机 A 和 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="aa3f1-105">In Lync Server 2013 when IPv4 and IPv6 are in use, you must plan for both host A and AAAA records.</span></span>

<span data-ttu-id="aa3f1-106">下面列出的主题定义将 DNS 记录用于部署规划：</span><span class="sxs-lookup"><span data-stu-id="aa3f1-106">The topics listed below define the use of DNS records for your deployment planning:</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="aa3f1-107">本部分内容</span><span class="sxs-lookup"><span data-stu-id="aa3f1-107">In This Section</span></span>

  - [<span data-ttu-id="aa3f1-108">Lync Server 2013 中的 DNS 摘要-使用 NAT 的专用 IP 地址的单一合并边缘</span><span class="sxs-lookup"><span data-stu-id="aa3f1-108">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="aa3f1-109">Lync Server 2013 中的 DNS 摘要-使用公用 IP 地址的单一合并边缘</span><span class="sxs-lookup"><span data-stu-id="aa3f1-109">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="aa3f1-110">Lync Server 2013 中的 DNS 摘要-扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="aa3f1-110">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="aa3f1-111">Lync Server 2013 中的 DNS 摘要-扩展的合并边缘（使用公用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="aa3f1-111">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="aa3f1-112">Lync Server 2013 中的 DNS 摘要-使用硬件负载平衡器的扩展的合并边缘</span><span class="sxs-lookup"><span data-stu-id="aa3f1-112">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="aa3f1-113">Lync Server 2013 中的 DNS 摘要-反向代理</span><span class="sxs-lookup"><span data-stu-id="aa3f1-113">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

  - [<span data-ttu-id="aa3f1-114">Lync Server 2013 中的 DNS 摘要-SIP、XMPP 联合身份验证和公共即时消息</span><span class="sxs-lookup"><span data-stu-id="aa3f1-114">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

