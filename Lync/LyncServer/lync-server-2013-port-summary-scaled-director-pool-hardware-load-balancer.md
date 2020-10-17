---
title: Lync Server 2013：端口摘要-扩展的控制器池、硬件负载平衡器
description: Lync Server 2013：端口摘要-扩展的控制器池、硬件负载平衡器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled Director pool, hardware load balancer
ms:assetid: 6ae2f4ac-5b64-4e45-8253-133308f5812d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204983(v=OCS.15)
ms:contentKeyID: 48184434
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10bfb3a3ad3a38b6cb0e46414bf22deecc71d7b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564548"
---
# <a name="port-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="c8558-103">Lync Server 2013 中的端口摘要-扩展的控制器池、硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="c8558-103">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8558-104">_**上次修改的主题：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="c8558-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="c8558-105">控制器池的防火墙端口要求由用于从边缘服务器的内部接口或反向代理的面向内部接口的内部接口与控制器建立通信的端口组成。</span><span class="sxs-lookup"><span data-stu-id="c8558-105">Firewall port requirements for a Director pool consist of the ports that are used to establish communication with the Director from the internal interface of the Edge Server or internal-facing interface of the reverse proxy.</span></span> <span data-ttu-id="c8558-106">Microsoft Lync Server 2013 默认情况下需要从反向代理向控制器以及前端池和前端服务器打开端口 HTTP/TCP 8080 和 HTTPS/TCP 4443。</span><span class="sxs-lookup"><span data-stu-id="c8558-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="c8558-107">此外，还必须有会话初始协议 (SIP) 从边缘服务器内部接口到控制器以及前端池和前端服务器的通信。</span><span class="sxs-lookup"><span data-stu-id="c8558-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="c8558-108">SIP 协议使用从边缘服务器到前端池和前端服务器的 SIP/MTLS/TCP 5061。</span><span class="sxs-lookup"><span data-stu-id="c8558-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="c8558-109">还必须创建一个允许从 Director、前端池和前端服务器到边缘服务器内部接口的 SIP/MTLS/TCP 5061 通信的规则。</span><span class="sxs-lookup"><span data-stu-id="c8558-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="c8558-110">用于防火墙定义的控制器端口和协议</span><span class="sxs-lookup"><span data-stu-id="c8558-110">Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8558-111">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="c8558-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c8558-112">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="c8558-112">Source IP address</span></span></th>
<th><span data-ttu-id="c8558-113">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="c8558-113">Destination IP address</span></span></th>
<th><span data-ttu-id="c8558-114">注释</span><span class="sxs-lookup"><span data-stu-id="c8558-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8558-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="c8558-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="c8558-116">反向代理内部接口</span><span class="sxs-lookup"><span data-stu-id="c8558-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="c8558-117">控制器硬件负载平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="c8558-117">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="c8558-118">该通信最初由反向代理的外部端接收，并发送到控制器 HLB VIP 和前端服务器 web 服务</span><span class="sxs-lookup"><span data-stu-id="c8558-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8558-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="c8558-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="c8558-120">反向代理内部接口</span><span class="sxs-lookup"><span data-stu-id="c8558-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="c8558-121">控制器硬件负载平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="c8558-121">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="c8558-122">该通信最初由反向代理的外部端接收，并发送到控制器 HLB VIP 和前端服务器 web 服务</span><span class="sxs-lookup"><span data-stu-id="c8558-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Servers web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8558-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="c8558-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="c8558-124">控制器</span><span class="sxs-lookup"><span data-stu-id="c8558-124">Director</span></span></p></td>
<td><p><span data-ttu-id="c8558-125">前端服务器或前端池</span><span class="sxs-lookup"><span data-stu-id="c8558-125">Front End Server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="c8558-126">控制器 HLB VIP 与前端服务器之间的服务器间通信</span><span class="sxs-lookup"><span data-stu-id="c8558-126">Inter-server communication between the Director HLB VIP and the Front End Servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8558-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="c8558-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="c8558-128">内部客户端</span><span class="sxs-lookup"><span data-stu-id="c8558-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="c8558-129">控制器硬件负载平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="c8558-129">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="c8558-130">Director 向内部和外部客户端提供 web 服务。</span><span class="sxs-lookup"><span data-stu-id="c8558-130">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8558-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="c8558-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="c8558-132">内部客户端</span><span class="sxs-lookup"><span data-stu-id="c8558-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="c8558-133">控制器硬件负载平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="c8558-133">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="c8558-134">Director 向内部和外部客户端提供 web 服务。</span><span class="sxs-lookup"><span data-stu-id="c8558-134">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8558-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="c8558-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="c8558-136">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="c8558-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c8558-137">控制器硬件负载平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="c8558-137">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="c8558-138">从边缘服务器到控制器和前端服务器的 SIP 通信。</span><span class="sxs-lookup"><span data-stu-id="c8558-138">SIP communication from the Edge Server to the Director, and Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8558-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="c8558-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="c8558-140">任何</span><span class="sxs-lookup"><span data-stu-id="c8558-140">Any</span></span></p></td>
<td><p><span data-ttu-id="c8558-141">控制器</span><span class="sxs-lookup"><span data-stu-id="c8558-141">Director</span></span></p></td>
<td><p><span data-ttu-id="c8558-142">集中日志记录服务控制器 ( # A0) 或代理 ( # A1) 命令和日志集合</span><span class="sxs-lookup"><span data-stu-id="c8558-142">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8558-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="c8558-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="c8558-144">任何</span><span class="sxs-lookup"><span data-stu-id="c8558-144">Any</span></span></p></td>
<td><p><span data-ttu-id="c8558-145">控制器</span><span class="sxs-lookup"><span data-stu-id="c8558-145">Director</span></span></p></td>
<td><p><span data-ttu-id="c8558-146">集中日志记录服务控制器 ( # A0) 或代理 ( # A1) 命令和日志集合</span><span class="sxs-lookup"><span data-stu-id="c8558-146">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8558-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="c8558-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="c8558-148">任何</span><span class="sxs-lookup"><span data-stu-id="c8558-148">Any</span></span></p></td>
<td><p><span data-ttu-id="c8558-149">控制器</span><span class="sxs-lookup"><span data-stu-id="c8558-149">Director</span></span></p></td>
<td><p><span data-ttu-id="c8558-150">集中日志记录服务控制器 ( # A0) 或代理 ( # A1) 命令和日志集合</span><span class="sxs-lookup"><span data-stu-id="c8558-150">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

