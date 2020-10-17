---
title: Lync Server 2013：端口摘要-反向代理
description: Lync Server 2013：端口摘要-反向代理。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf07800c91f5a28165eb05e14e2d775758460f50
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555248"
---
# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="52df1-103">Lync Server 2013 中的端口摘要-反向代理</span><span class="sxs-lookup"><span data-stu-id="52df1-103">Port summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52df1-104">_**上次修改的主题：** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="52df1-104">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="52df1-105">反向代理对于防火墙和端口/协议具有最低要求。</span><span class="sxs-lookup"><span data-stu-id="52df1-105">The reverse proxy has minimal requirements for firewall and port/protocol.</span></span>

  - <span data-ttu-id="52df1-106">外部防火墙要求是 HTTPS/TCP/443 以及可选的 HTTP/TCP/80。</span><span class="sxs-lookup"><span data-stu-id="52df1-106">External firewall requirements are the HTTPS/TCP/443 and the optional HTTP/TCP/80.</span></span> <span data-ttu-id="52df1-107">HTTPS 用于通过反向代理的 SSL 和 TLS 安全通信。</span><span class="sxs-lookup"><span data-stu-id="52df1-107">HTTPS is used for SSL and TLS secure communications through the reverse proxy.</span></span> <span data-ttu-id="52df1-108">如果您选择允许在修改证书时访问自动发现服务，则可能会证明困难或不会导致成本降低。</span><span class="sxs-lookup"><span data-stu-id="52df1-108">HTTP is used if you choose to allow access to the Autodiscover Service when modifying certificates might prove difficult or not cost justified.</span></span>

  - <span data-ttu-id="52df1-109">客户端希望与 HTTPS 上的 Office Web Apps Server 联系。</span><span class="sxs-lookup"><span data-stu-id="52df1-109">Clients expect to contact the Office Web Apps Server on HTTPS.</span></span> <span data-ttu-id="52df1-110">Office Web Apps Server 需要来自 HTTPS/TCP/443 上的内部客户端的通信。</span><span class="sxs-lookup"><span data-stu-id="52df1-110">The Office Web Apps Server expects communication from internal clients on HTTPS/TCP/443.</span></span> <span data-ttu-id="52df1-111">建议的配置是允许从反向代理到 Office Web Apps Server 的 HTTPS/TCP/443。</span><span class="sxs-lookup"><span data-stu-id="52df1-111">The recommended configuration is to allow HTTPS/TCP/443 from the reverse proxy to the Office Web Apps Server.</span></span>

  - <span data-ttu-id="52df1-112">端口8080用于将流量从反向代理内部接口路由到前端服务器、前端池虚拟 IP (VIP) 或可选控制器或控制器池 VIP。</span><span class="sxs-lookup"><span data-stu-id="52df1-112">Port 8080 is used to route traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP.</span></span> <span data-ttu-id="52df1-113">如果在修改外部 web 服务发布规则证书的情况下，运行 Lync 的移动设备需要使用端口 TCP 8080，以查找自动发现服务 (例如，如果您有大量 SIP 域) 。</span><span class="sxs-lookup"><span data-stu-id="52df1-113">Port TCP 8080 is required for mobile devices running Lync to locate the Autodiscover Service in situations where modifying the external web service publishing rule certificate is undesirable (for example, if you have a large number of SIP domains).</span></span> <span data-ttu-id="52df1-114">如果选择使用必需的 SAN 项获取新证书，则端口 TCP 8080 是不需要的并且是可选的。</span><span class="sxs-lookup"><span data-stu-id="52df1-114">If you choose to acquire new certificates with the necessary SAN entries, the port TCP 8080 is not needed and is optional.</span></span>

  - <span data-ttu-id="52df1-115">端口4443用于从反向代理内部接口到前端服务器、前端池虚拟 IP (VIP) 或可选控制器或控制器池 VIP 的流量</span><span class="sxs-lookup"><span data-stu-id="52df1-115">Port 4443 is used for traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP</span></span>
    
    <span data-ttu-id="52df1-116">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="52df1-116">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>  
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="52df1-117">请勿将4443通过 TCP 从反向代理与从管理中央管理存储角色的 Standard Edition 服务器或前端池的 TCP 流量相混淆的端口4443的内部部署相混淆。</span><span class="sxs-lookup"><span data-stu-id="52df1-117">Do not confuse the 4443 over TCP from the reverse proxy to the internal deployment for the port 4443 over TCP traffic from the Standard Edition server or the Front End pool that manages the Central Management store role.</span></span>

    
    </div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="52df1-118">端口和协议详细信息</span><span class="sxs-lookup"><span data-stu-id="52df1-118">Port and Protocol Details</span></span>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="52df1-119">反向代理服务器的防火墙详细信息：外部接口</span><span class="sxs-lookup"><span data-stu-id="52df1-119">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52df1-120">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="52df1-120">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="52df1-121">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="52df1-121">Source IP Address</span></span></th>
<th><span data-ttu-id="52df1-122">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="52df1-122">Destination IP Address</span></span></th>
<th><span data-ttu-id="52df1-123">注释</span><span class="sxs-lookup"><span data-stu-id="52df1-123">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52df1-124">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="52df1-124">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="52df1-125">任何</span><span class="sxs-lookup"><span data-stu-id="52df1-125">Any</span></span></p></td>
<td><p><span data-ttu-id="52df1-126">反向代理侦听器</span><span class="sxs-lookup"><span data-stu-id="52df1-126">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="52df1-127"> (可选) 重定向到 HTTPS （如果用户进入 http:// &lt; publishedSiteFQDN &gt; 。</span><span class="sxs-lookup"><span data-stu-id="52df1-127">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span></p>
<p><span data-ttu-id="52df1-128">如果在组织不想修改外部 Web 服务发布规则证书的情况下，使用 Office Web Apps for 会议和运行 Lync 的移动设备的自动发现服务，也需要使用此属性。</span><span class="sxs-lookup"><span data-stu-id="52df1-128">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52df1-129">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="52df1-129">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="52df1-130">任何</span><span class="sxs-lookup"><span data-stu-id="52df1-130">Any</span></span></p></td>
<td><p><span data-ttu-id="52df1-131">反向代理侦听器</span><span class="sxs-lookup"><span data-stu-id="52df1-131">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="52df1-132">通讯簿下载、通讯簿 Web 查询服务、自动发现、客户端更新、会议内容、设备更新、组扩展、Office Web Apps for 会议、电话拨入式会议和会议。</span><span class="sxs-lookup"><span data-stu-id="52df1-132">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="52df1-133">反向代理服务器的防火墙详细信息：内部接口</span><span class="sxs-lookup"><span data-stu-id="52df1-133">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52df1-134">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="52df1-134">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="52df1-135">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="52df1-135">Source IP Address</span></span></th>
<th><span data-ttu-id="52df1-136">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="52df1-136">Destination IP Address</span></span></th>
<th><span data-ttu-id="52df1-137">注释</span><span class="sxs-lookup"><span data-stu-id="52df1-137">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52df1-138">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="52df1-138">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="52df1-139">内部反向代理接口</span><span class="sxs-lookup"><span data-stu-id="52df1-139">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="52df1-140">前端服务器、前端池、控制器、控制器池</span><span class="sxs-lookup"><span data-stu-id="52df1-140">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="52df1-141">如果组织不想修改外部 web 服务发布规则证书的情况下，使用运行 Lync 的移动设备的自动发现服务，则为必需。</span><span class="sxs-lookup"><span data-stu-id="52df1-141">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p>
<p><span data-ttu-id="52df1-142">发送到反向代理外部接口上的端口 80 的流量将从反向代理内部接口重定向到端口 8080 上的池，以便池 Web 服务可将其与内部 Web 流量区分开来。</span><span class="sxs-lookup"><span data-stu-id="52df1-142">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52df1-143">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="52df1-143">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="52df1-144">内部反向代理接口</span><span class="sxs-lookup"><span data-stu-id="52df1-144">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="52df1-145">前端服务器、前端池、控制器、控制器池</span><span class="sxs-lookup"><span data-stu-id="52df1-145">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="52df1-146">发送到反向代理外部接口上的端口 443 的流量将从反向代理内部接口重定向到端口 4443 上的池，以便池 Web 服务可将其与内部 Web 流量区分开来。</span><span class="sxs-lookup"><span data-stu-id="52df1-146">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52df1-147">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="52df1-147">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="52df1-148">内部反向代理接口</span><span class="sxs-lookup"><span data-stu-id="52df1-148">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="52df1-149">Office Web Apps for 会议</span><span class="sxs-lookup"><span data-stu-id="52df1-149">Office Web Apps for conferencing</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

