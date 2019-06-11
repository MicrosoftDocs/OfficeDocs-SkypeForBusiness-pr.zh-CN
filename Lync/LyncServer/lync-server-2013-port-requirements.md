---
title: Lync Server 2013 端口要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port requirements
ms:assetid: 9a6c1300-ef88-4181-a8f1-43cd3093962b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398798(v=OCS.15)
ms:contentKeyID: 48184886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fddb9e1ad518196b3ac2ac1d8c5d2dc0ebeac972
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-requirements-for-lync-server-2013"></a><span data-ttu-id="c9e2f-102">Lync Server 2013 的端口要求</span><span class="sxs-lookup"><span data-stu-id="c9e2f-102">Port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9e2f-103">_**主题上次修改时间:** 2013-03-27_</span><span class="sxs-lookup"><span data-stu-id="c9e2f-103">_**Topic Last Modified:** 2013-03-27_</span></span>

<span data-ttu-id="c9e2f-104">Lync 服务器要求防火墙上的特定端口处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="c9e2f-104">Lync Server requires that specific ports on the firewall be open.</span></span> <span data-ttu-id="c9e2f-105">此外，如果在您的组织中部署了 Internet 协议安全性 (IPsec)，则必须在用于传送音频、视频和全景视频的端口范围内禁用 IPSec。</span><span class="sxs-lookup"><span data-stu-id="c9e2f-105">Additionally, if Internet Protocol security (IPsec) is deployed in your organization, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c9e2f-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="c9e2f-106">In This Section</span></span>

<span data-ttu-id="c9e2f-107">本部分包含以下主题:</span><span class="sxs-lookup"><span data-stu-id="c9e2f-107">This section includes the following topics:</span></span>

  - [<span data-ttu-id="c9e2f-108">Lync Server 2013 中内部服务器的端口和协议</span><span class="sxs-lookup"><span data-stu-id="c9e2f-108">Ports and protocols for internal servers in Lync Server 2013</span></span>](lync-server-2013-ports-and-protocols-for-internal-servers.md)

  - [<span data-ttu-id="c9e2f-109">Lync Server 2013 中的 IPsec 例外</span><span class="sxs-lookup"><span data-stu-id="c9e2f-109">IPsec exceptions in Lync Server 2013</span></span>](lync-server-2013-ipsec-exceptions.md)

  - [<span data-ttu-id="c9e2f-110">Lync Server 2013 中的端口摘要 - 单一合并边缘（使用 NAT 通过专用 IP 地址进行）</span><span class="sxs-lookup"><span data-stu-id="c9e2f-110">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="c9e2f-111">Lync Server 2013 中的端口摘要 - 使用公用 IP 地址的单一合并边缘</span><span class="sxs-lookup"><span data-stu-id="c9e2f-111">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="c9e2f-112">Lync Server 2013 中的端口摘要 - 扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="c9e2f-112">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="c9e2f-113">Lync Server 2013 中的端口摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="c9e2f-113">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="c9e2f-114">Lync Server 2013 中的端口摘要 - 使用硬件负载平衡器的扩展的合并边缘</span><span class="sxs-lookup"><span data-stu-id="c9e2f-114">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="c9e2f-115">Lync Server 2013 中的端口摘要 - 反向代理</span><span class="sxs-lookup"><span data-stu-id="c9e2f-115">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="c9e2f-116">端口摘要-Lync Server 2013 中的 SIP、XMPP 联盟和公共即时消息</span><span class="sxs-lookup"><span data-stu-id="c9e2f-116">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

