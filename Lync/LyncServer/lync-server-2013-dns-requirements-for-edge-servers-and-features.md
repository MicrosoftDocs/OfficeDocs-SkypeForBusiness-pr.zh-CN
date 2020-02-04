---
title: Lync Server 2013： Edge 服务器和功能的 DNS 要求
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
ms.openlocfilehash: 9e9f0cb2eb68ed29984811f1c42a97dab4693a2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-edge-servers-and-features-in-lync-server-2013"></a><span data-ttu-id="ccae6-102">Lync Server 2013 中的边缘服务器和功能的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="ccae6-102">DNS requirements for Edge Servers and features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccae6-103">_**主题上次修改时间：** 2014-04-08_</span><span class="sxs-lookup"><span data-stu-id="ccae6-103">_**Topic Last Modified:** 2014-04-08_</span></span>

<span data-ttu-id="ccae6-104">Lync Server 2013 Edge 服务器、边缘池和反向代理对域名系统（DNS）记录具有特定的要求。</span><span class="sxs-lookup"><span data-stu-id="ccae6-104">Lync Server 2013 Edge Servers, Edge pools, and reverse proxies have specific requirements for Domain Name System (DNS) records.</span></span> <span data-ttu-id="ccae6-105">在 Lync Server 2013 中，当 IPv4 和 IPv6 正在使用时，必须为主机 A 和 AAAA 记录进行规划。</span><span class="sxs-lookup"><span data-stu-id="ccae6-105">In Lync Server 2013 when IPv4 and IPv6 are in use, you must plan for both host A and AAAA records.</span></span>

<span data-ttu-id="ccae6-106">下面列出的主题定义了用于部署规划的 DNS 记录的使用：</span><span class="sxs-lookup"><span data-stu-id="ccae6-106">The topics listed below define the use of DNS records for your deployment planning:</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ccae6-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="ccae6-107">In This Section</span></span>

  - [<span data-ttu-id="ccae6-108">Lync Server 2013 中的 DNS 摘要 - 单一合并边缘（使用 NAT 通过专用 IP 地址进行）</span><span class="sxs-lookup"><span data-stu-id="ccae6-108">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="ccae6-109">Lync Server 2013 中的证书摘要 - 使用公用 IP 地址的单一合并边缘</span><span class="sxs-lookup"><span data-stu-id="ccae6-109">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="ccae6-110">Lync Server 2013 中的 DNS 摘要 - 扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="ccae6-110">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="ccae6-111">Lync Server 2013 中的 DNS 摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="ccae6-111">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="ccae6-112">Lync Server 2013 中的 DNS 摘要 - 使用硬件负载平衡器的扩展的合并边缘</span><span class="sxs-lookup"><span data-stu-id="ccae6-112">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="ccae6-113">Lync Server 2013 中的 DNS 摘要 - 反向代理</span><span class="sxs-lookup"><span data-stu-id="ccae6-113">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

  - [<span data-ttu-id="ccae6-114">DNS 摘要-Lync Server 2013 中的 SIP、XMPP 联盟和公共即时消息</span><span class="sxs-lookup"><span data-stu-id="ccae6-114">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

