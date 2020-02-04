---
title: Lync Server 2013：为外部用户访问配置防火墙和端口
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure firewalls and ports for external user access
ms:assetid: cacb3832-f8db-4009-bfcf-6f5c15c236ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398848(v=OCS.15)
ms:contentKeyID: 48185430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b10ad0826e0b15ff42b47dc6c732b2b60500f8b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-firewalls-and-ports-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="4d253-102">在 Lync Server 2013 中为外部用户访问配置防火墙和端口</span><span class="sxs-lookup"><span data-stu-id="4d253-102">Configure firewalls and ports for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d253-103">_**主题上次修改时间：** 2012-05-21_</span><span class="sxs-lookup"><span data-stu-id="4d253-103">_**Topic Last Modified:** 2012-05-21_</span></span>

<span data-ttu-id="4d253-104">若要配置防火墙和端口，你需要为 Edge 服务器、反向代理服务器和可能的硬件负载平衡器（对于不使用 DNS 负载平衡的缩放部署）配置它们。</span><span class="sxs-lookup"><span data-stu-id="4d253-104">To configure firewalls and ports, you need to configure them for Edge Servers, reverse proxy servers, and possibly hardware load balancers (for a scaled deployment that does not use DNS load balancing).</span></span> <span data-ttu-id="4d253-105">本部分提供有关所有 Edge 服务器组件的防火墙和端口要求以及边缘服务器的防火墙端口的配置的信息。</span><span class="sxs-lookup"><span data-stu-id="4d253-105">This section provides information about firewall and port requirements for all Edge Server components and the configuration of firewall ports for Edge Servers.</span></span> <span data-ttu-id="4d253-106">有关为反向代理服务器配置端口的详细信息，请参阅[为 Lync Server 2013 设置反向代理服务器](lync-server-2013-setting-up-reverse-proxy-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="4d253-106">For details about configuring ports for reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md).</span></span> <span data-ttu-id="4d253-107">如果你正在部署缩放的边缘拓扑，并且使用的是硬件负载平衡，而不是 DNS 负载平衡，请参阅计划文档中的在[Lync Server 2013 中使用硬件负载平衡器缩放的合并边界](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)，了解有关配置硬件负载平衡器端口的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d253-107">If you are deploying a scaled edge topology and are using hardware load balancing instead of DNS load balancing, see [Scaled consolidated edge with hardware load balancers in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md) in the Planning documentation for details about configuring ports for hardware load balancers.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4d253-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d253-108">See Also</span></span>


[<span data-ttu-id="4d253-109">确定 Lync Server 2013 的外部 A/V 防火墙和端口要求</span><span class="sxs-lookup"><span data-stu-id="4d253-109">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

