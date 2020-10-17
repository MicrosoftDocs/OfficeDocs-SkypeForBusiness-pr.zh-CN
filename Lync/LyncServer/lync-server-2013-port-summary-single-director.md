---
title: Lync Server 2013：端口摘要-单个控制器
description: Lync Server 2013：端口摘要-单个控制器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single Director
ms:assetid: 079c1414-723f-4499-b7d4-a0d7121c1626
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204648(v=OCS.15)
ms:contentKeyID: 48183322
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a46e394121dbc7dd6158016d39511e9487cec1ff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566368"
---
# <a name="port-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="d2292-103">Lync Server 2013 中的端口摘要-单一控制器</span><span class="sxs-lookup"><span data-stu-id="d2292-103">Port summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2292-104">_**上次修改的主题：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="d2292-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="d2292-105">单个控制器的防火墙端口要求由用于从内部接口或反向代理的面向内部网络中的控制器建立通信的端口组成。</span><span class="sxs-lookup"><span data-stu-id="d2292-105">Firewall port requirements for a single Director consist of the ports that are used to establish communication with the Director from the internal interface or internal-facing network of the reverse proxy.</span></span> <span data-ttu-id="d2292-106">Microsoft Lync Server 2013 默认情况下需要从反向代理向控制器以及前端池和前端服务器打开端口 HTTP/TCP 8080 和 HTTPS/TCP 4443。</span><span class="sxs-lookup"><span data-stu-id="d2292-106">Microsoft Lync Server 2013 by default expects ports HTTP/TCP 8080 and HTTPS/TCP 4443 to be open from the reverse proxy to the Director, as well as the Front End pool and Front End Server.</span></span> <span data-ttu-id="d2292-107">此外，还必须有会话初始协议 (SIP) 从边缘服务器内部接口到控制器以及前端池和前端服务器的通信。</span><span class="sxs-lookup"><span data-stu-id="d2292-107">Additionally, there must be session initiation protocol (SIP) communication from the Edge Server internal interface to the Director and to the Front End pool and Front End Server.</span></span> <span data-ttu-id="d2292-108">SIP 协议使用从边缘服务器到前端池和前端服务器的 SIP/MTLS/TCP 5061。</span><span class="sxs-lookup"><span data-stu-id="d2292-108">The SIP protocol uses SIP/MTLS/TCP 5061 from the Edge Server to the Front End pool and Front End Server.</span></span> <span data-ttu-id="d2292-109">还必须创建一个允许从 Director、前端池和前端服务器到边缘服务器内部接口的 SIP/MTLS/TCP 5061 通信的规则。</span><span class="sxs-lookup"><span data-stu-id="d2292-109">A rule that allows SIP/MTLS/TCP 5061 communication from the Director, Front End pool and Front End Server to the Edge Server internal interface must be created as well.</span></span>

### <a name="single-director-ports-and-protocols-for-firewall-definitions"></a><span data-ttu-id="d2292-110">防火墙定义的单个控制器端口和协议</span><span class="sxs-lookup"><span data-stu-id="d2292-110">Single Director Ports and Protocols for Firewall Definitions</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2292-111">角色/协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="d2292-111">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d2292-112">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="d2292-112">Source IP address</span></span></th>
<th><span data-ttu-id="d2292-113">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="d2292-113">Destination IP address</span></span></th>
<th><span data-ttu-id="d2292-114">注释</span><span class="sxs-lookup"><span data-stu-id="d2292-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2292-115">HTTP/TCP 8080</span><span class="sxs-lookup"><span data-stu-id="d2292-115">HTTP/TCP 8080</span></span></p></td>
<td><p><span data-ttu-id="d2292-116">反向代理内部接口</span><span class="sxs-lookup"><span data-stu-id="d2292-116">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="d2292-117">控制器</span><span class="sxs-lookup"><span data-stu-id="d2292-117">Director</span></span></p></td>
<td><p><span data-ttu-id="d2292-118">与反向代理的外部一方最初接收到的通信将发送到控制器和前端服务器 web 服务</span><span class="sxs-lookup"><span data-stu-id="d2292-118">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2292-119">HTTPS/TCP 4443</span><span class="sxs-lookup"><span data-stu-id="d2292-119">HTTPS/TCP 4443</span></span></p></td>
<td><p><span data-ttu-id="d2292-120">反向代理内部接口</span><span class="sxs-lookup"><span data-stu-id="d2292-120">Reverse proxy internal interface</span></span></p></td>
<td><p><span data-ttu-id="d2292-121">控制器</span><span class="sxs-lookup"><span data-stu-id="d2292-121">Director</span></span></p></td>
<td><p><span data-ttu-id="d2292-122">与反向代理的外部一方最初接收到的通信将发送到控制器和前端服务器 web 服务</span><span class="sxs-lookup"><span data-stu-id="d2292-122">Initially received by the external side of the reverse proxy, the communication is sent on to the Director and Front End Server web services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2292-123">HTTPS/TCP 444</span><span class="sxs-lookup"><span data-stu-id="d2292-123">HTTPS/TCP 444</span></span></p></td>
<td><p><span data-ttu-id="d2292-124">控制器</span><span class="sxs-lookup"><span data-stu-id="d2292-124">Director</span></span></p></td>
<td><p><span data-ttu-id="d2292-125">前端服务器或前端池</span><span class="sxs-lookup"><span data-stu-id="d2292-125">Front End server or Front End pool</span></span></p></td>
<td><p><span data-ttu-id="d2292-126">控制器与前端服务器之间的服务器间通信</span><span class="sxs-lookup"><span data-stu-id="d2292-126">Inter-server communication between the Director and the Front End Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2292-127">HTTP/TCP 80</span><span class="sxs-lookup"><span data-stu-id="d2292-127">HTTP/TCP 80</span></span></p></td>
<td><p><span data-ttu-id="d2292-128">内部客户端</span><span class="sxs-lookup"><span data-stu-id="d2292-128">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="d2292-129">控制器 web 服务</span><span class="sxs-lookup"><span data-stu-id="d2292-129">Director web services</span></span></p></td>
<td><p><span data-ttu-id="d2292-130">控制器向内部和外部客户端提供 web 服务。</span><span class="sxs-lookup"><span data-stu-id="d2292-130">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2292-131">HTTPS/TCP 443</span><span class="sxs-lookup"><span data-stu-id="d2292-131">HTTPS/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="d2292-132">内部客户端</span><span class="sxs-lookup"><span data-stu-id="d2292-132">Internal Clients</span></span></p></td>
<td><p><span data-ttu-id="d2292-133">控制器 web 服务</span><span class="sxs-lookup"><span data-stu-id="d2292-133">Director web services</span></span></p></td>
<td><p><span data-ttu-id="d2292-134">控制器向内部和外部客户端提供 web 服务。</span><span class="sxs-lookup"><span data-stu-id="d2292-134">The Director provides web services to internal and external clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2292-135">SIP/MTLS/TCP 5061</span><span class="sxs-lookup"><span data-stu-id="d2292-135">SIP/MTLS/TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="d2292-136">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="d2292-136">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d2292-137">控制器</span><span class="sxs-lookup"><span data-stu-id="d2292-137">Director</span></span></p></td>
<td><p><span data-ttu-id="d2292-138">从边缘服务器到控制器以及前端服务器的 SIP 通信。</span><span class="sxs-lookup"><span data-stu-id="d2292-138">SIP communication from the Edge Server to the Director, and the Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2292-139">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="d2292-139">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="d2292-140">任何</span><span class="sxs-lookup"><span data-stu-id="d2292-140">Any</span></span></p></td>
<td><p><span data-ttu-id="d2292-141">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="d2292-141">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d2292-142">集中日志记录服务控制器 (ClsController.exe) 或代理 (ClasAgent.exe) 命令和日志集合</span><span class="sxs-lookup"><span data-stu-id="d2292-142">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2292-143">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="d2292-143">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="d2292-144">任何</span><span class="sxs-lookup"><span data-stu-id="d2292-144">Any</span></span></p></td>
<td><p><span data-ttu-id="d2292-145">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="d2292-145">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d2292-146">集中日志记录服务控制器 (ClsController.exe) 或代理 (ClasAgent.exe) 命令和日志集合</span><span class="sxs-lookup"><span data-stu-id="d2292-146">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2292-147">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="d2292-147">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="d2292-148">任何</span><span class="sxs-lookup"><span data-stu-id="d2292-148">Any</span></span></p></td>
<td><p><span data-ttu-id="d2292-149">边缘服务器内部接口</span><span class="sxs-lookup"><span data-stu-id="d2292-149">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d2292-150">集中日志记录服务控制器 (ClsController.exe) 或代理 (ClasAgent.exe) 命令和日志集合</span><span class="sxs-lookup"><span data-stu-id="d2292-150">Centralized Logging Service controller (ClsController.exe) or agent (ClasAgent.exe)commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

