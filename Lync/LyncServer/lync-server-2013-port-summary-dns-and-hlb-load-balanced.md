---
title: Lync Server 2013：端口摘要-DNS 和 HLB 负载平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - DNS and HLB load balanced
ms:assetid: b07c37e4-820e-46ee-a678-1da95d1b87af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205179(v=OCS.15)
ms:contentKeyID: 48185149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e6175f83e1cea20e21ed25c372849c0e6b80b49
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="2b936-102">Lync Server 2013 中的端口摘要-DNS 和 HLB 负载平衡</span><span class="sxs-lookup"><span data-stu-id="2b936-102">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b936-103">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="2b936-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="2b936-104">单个控制器的防火墙端口要求由用于从内部接口或反向代理的面向内部网络中的控制器建立通信的端口组成。</span><span class="sxs-lookup"><span data-stu-id="2b936-104">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="2b936-105">Microsoft Lync Server 2013 默认情况下需要从反向代理向控制器以及前端池和前端服务器打开端口 HTTP/TCP 8080 和 HTTPS/TCP 4443。</span><span class="sxs-lookup"><span data-stu-id="2b936-105">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="2b936-106">此外，还必须存在从边缘服务器内部接口到控制器以及前端池和前端服务器的会话初始协议（SIP）通信。</span><span class="sxs-lookup"><span data-stu-id="2b936-106">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="2b936-107">SIP 协议使用从边缘服务器到前端池和前端服务器的 SIP/MTLS/TCP 5061。</span><span class="sxs-lookup"><span data-stu-id="2b936-107">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="2b936-108">还必须创建一个允许从 Director、前端池和前端服务器到边缘服务器内部接口的 SIP/MTLS/TCP 5061 通信的规则。</span><span class="sxs-lookup"><span data-stu-id="2b936-108">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="2b936-109">防火墙定义的单个控制器端口和协议</span><span class="sxs-lookup"><span data-stu-id="2b936-109">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b936-110">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="2b936-110">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="2b936-111">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="2b936-111">Source IP address</span></span></th>
<th><span data-ttu-id="2b936-112">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="2b936-112">Destination IP address</span></span></th>
<th><span data-ttu-id="2b936-113">备注</span><span class="sxs-lookup"><span data-stu-id="2b936-113">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b936-114">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="2b936-114">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="2b936-115">反向代理内部接口</span><span class="sxs-lookup"><span data-stu-id="2b936-115">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="2b936-116">控制器硬件负载平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="2b936-116">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="2b936-117">该通信最初由反向代理的外部端接收，并发送到控制器 HLB VIP 和前端服务器 web 服务。</span><span class="sxs-lookup"><span data-stu-id="2b936-117">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b936-118">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="2b936-118">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="2b936-119">反向代理内部接口</span><span class="sxs-lookup"><span data-stu-id="2b936-119">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="2b936-120">控制器硬件负载平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="2b936-120">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="2b936-121">该通信最初由反向代理的外部端接收，并发送到控制器 HLB VIP 和前端服务器 web 服务。</span><span class="sxs-lookup"><span data-stu-id="2b936-121">Initially received by the external side of the reverse proxy, the communication is sent on to the Director HLB VIP and Front End Server web services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b936-122">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="2b936-122">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="2b936-123">控制器</span><span class="sxs-lookup"><span data-stu-id="2b936-123">Director</span></span></p></td>
<td><p><span data-ttu-id="2b936-124">前端池或前端服务器</span><span class="sxs-lookup"><span data-stu-id="2b936-124">Front End pool or Front End Server</span></span></p></td>
<td><p><span data-ttu-id="2b936-125">控制器 HLB VIP 与前端服务器或前端服务器之间的服务器间通信。</span><span class="sxs-lookup"><span data-stu-id="2b936-125">Inter-server communication between the Director HLB VIP and the Front End Server or Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b936-126">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="2b936-126">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="2b936-127">内部客户端</span><span class="sxs-lookup"><span data-stu-id="2b936-127">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="2b936-128">控制器硬件负载平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="2b936-128">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="2b936-129">Director 向内部和外部客户端提供 web 服务。</span><span class="sxs-lookup"><span data-stu-id="2b936-129">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b936-130">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="2b936-130">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="2b936-131">内部客户端</span><span class="sxs-lookup"><span data-stu-id="2b936-131">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="2b936-132">控制器硬件负载平衡器 VIP</span><span class="sxs-lookup"><span data-stu-id="2b936-132">Director Hardware Load Balancer VIP</span></span></p></td>
<td><p><span data-ttu-id="2b936-133">Director 向内部和外部客户端提供 web 服务。</span><span class="sxs-lookup"><span data-stu-id="2b936-133">The Director provides web services to internal as well as external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b936-134">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="2b936-134">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="2b936-135">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="2b936-135">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="2b936-136">控制器</span><span class="sxs-lookup"><span data-stu-id="2b936-136">Director</span></span></p></td>
<td><p><span data-ttu-id="2b936-137">从边缘服务器到控制器以及前端服务器的 SIP 通信。</span><span class="sxs-lookup"><span data-stu-id="2b936-137">SIP communication from the Edge Server to the Director, as well as the Front End Servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b936-138">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="2b936-138">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="2b936-139">任意</span><span class="sxs-lookup"><span data-stu-id="2b936-139">Any</span></span></p></td>
<td><p><span data-ttu-id="2b936-140">控制器</span><span class="sxs-lookup"><span data-stu-id="2b936-140">Director</span></span></p></td>
<td><p><span data-ttu-id="2b936-141">集中日志记录服务控制器（ClsController）或代理（ClsAgent）命令和日志集合</span><span class="sxs-lookup"><span data-stu-id="2b936-141">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b936-142">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="2b936-142">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="2b936-143">任意</span><span class="sxs-lookup"><span data-stu-id="2b936-143">Any</span></span></p></td>
<td><p><span data-ttu-id="2b936-144">控制器</span><span class="sxs-lookup"><span data-stu-id="2b936-144">Director</span></span></p></td>
<td><p><span data-ttu-id="2b936-145">集中日志记录服务控制器（ClsController）或代理（ClsAgent）命令和日志集合</span><span class="sxs-lookup"><span data-stu-id="2b936-145">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b936-146">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="2b936-146">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="2b936-147">任意</span><span class="sxs-lookup"><span data-stu-id="2b936-147">Any</span></span></p></td>
<td><p><span data-ttu-id="2b936-148">控制器</span><span class="sxs-lookup"><span data-stu-id="2b936-148">Director</span></span></p></td>
<td><p><span data-ttu-id="2b936-149">集中日志记录服务控制器（ClsController）或代理（ClsAgent）命令和日志集合</span><span class="sxs-lookup"><span data-stu-id="2b936-149">Centralized Logging Service controller (ClsController.exe) or agent (ClsAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

