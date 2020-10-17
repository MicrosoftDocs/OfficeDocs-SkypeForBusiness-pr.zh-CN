---
title: Lync Server 2013： IP 和网络协议支持
description: Lync Server 2013： IP 和网络协议支持。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP and networking protocol support
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412848(v=OCS.15)
ms:contentKeyID: 48185128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbd8022dd7197524334e0c70ea0ad875a30446de
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553118"
---
# <a name="ip-and-networking-protocol-support-in-lync-server-2013"></a><span data-ttu-id="c3a0d-103">Lync Server 2013 中的 IP 和网络协议支持</span><span class="sxs-lookup"><span data-stu-id="c3a0d-103">IP and networking protocol support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3a0d-104">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c3a0d-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c3a0d-105">Lync Server 2013 支持以下 IP 和网络协议：</span><span class="sxs-lookup"><span data-stu-id="c3a0d-105">Lync Server 2013 supports the following IP and networking protocols:</span></span>

  - <span data-ttu-id="c3a0d-106">**IP 协议。**    Lync Server 2013 支持对服务器网络 (IPv4) 或 IP 版本 6 (IPv6) 中的一个 IP 版本4。</span><span class="sxs-lookup"><span data-stu-id="c3a0d-106">**IP Protocols.**   Lync Server 2013 supports either IP version 4 (IPv4) or IP version 6 (IPv6) for the server network.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c3a0d-107">Lync Server 2013 可以在启用了双 IP 堆栈的网络中正常运行。</span><span class="sxs-lookup"><span data-stu-id="c3a0d-107">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

    
    </div>

  - <span data-ttu-id="c3a0d-108">**SIP 传输协议。**    通常，SIP 可以使用至少三种传输类型：用户数据报协议 (UDP) 、传输控制协议 (TCP) 和传输层安全性 (TLS) 。</span><span class="sxs-lookup"><span data-stu-id="c3a0d-108">**SIP Transport Protocols.**   Generically, SIP can use at least three transport types: User Datagram Protocol (UDP), Transmission Control Protocol (TCP), and Transport Layer Security (TLS).</span></span> <span data-ttu-id="c3a0d-109">在默认 SIP 传输配置中，TLS 将取代 TCP。</span><span class="sxs-lookup"><span data-stu-id="c3a0d-109">In the default SIP transport configuration, TLS runs over TCP.</span></span> <span data-ttu-id="c3a0d-110">TLS 在 Lync Server 2013 网络中使用。</span><span class="sxs-lookup"><span data-stu-id="c3a0d-110">TLS is used within the Lync Server 2013 network.</span></span> <span data-ttu-id="c3a0d-111">在网络边缘，Lync Server 2013 可以通过 TCP 进行互操作。</span><span class="sxs-lookup"><span data-stu-id="c3a0d-111">At the edge of the network, Lync Server 2013 can interoperate over TCP.</span></span> <span data-ttu-id="c3a0d-112">Lync Server 2013 不支持 SIP 传输 UDP，因为它不符合企业通信安全性、可靠性和可伸缩性的最低标准。</span><span class="sxs-lookup"><span data-stu-id="c3a0d-112">Lync Server 2013 does not support UDP for SIP transport because it doesn’t meet the minimum standards for enterprise communications security, reliability, and scalability.</span></span> <span data-ttu-id="c3a0d-113">有关详细信息，请参阅 NextHop 博客文章，"到 UDP，或不是 UDP"，这是问题 "at" [https://go.microsoft.com/fwlink/p/?linkId=185369](https://go.microsoft.com/fwlink/p/?linkid=185369) 。</span><span class="sxs-lookup"><span data-stu-id="c3a0d-113">For details, see the NextHop blog article, "To UDP, or not to UDP, that is the question," at [https://go.microsoft.com/fwlink/p/?linkId=185369](https://go.microsoft.com/fwlink/p/?linkid=185369).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c3a0d-114">每个博客的内容及其 URL 如有更改，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="c3a0d-114">The content of each blog and its URL are subject to change without notice.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

