---
title: Lync Server 2013：端口摘要-反向代理
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
ms.openlocfilehash: 203acca41c3e759bb05787c2bc23fd0ac773355f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="98a1f-102">Lync Server 2013 中的端口摘要-反向代理</span><span class="sxs-lookup"><span data-stu-id="98a1f-102">Port summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98a1f-103">_**上次修改的主题：** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="98a1f-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="98a1f-104">反向代理对于防火墙和端口/协议具有最低要求。</span><span class="sxs-lookup"><span data-stu-id="98a1f-104">The reverse proxy has minimal requirements for firewall and port/protocol.</span></span>

  - <span data-ttu-id="98a1f-105">外部防火墙要求是 HTTPS/TCP/443 以及可选的 HTTP/TCP/80。</span><span class="sxs-lookup"><span data-stu-id="98a1f-105">External firewall requirements are the HTTPS/TCP/443 and the optional HTTP/TCP/80.</span></span> <span data-ttu-id="98a1f-106">HTTPS 用于通过反向代理的 SSL 和 TLS 安全通信。</span><span class="sxs-lookup"><span data-stu-id="98a1f-106">HTTPS is used for SSL and TLS secure communications through the reverse proxy.</span></span> <span data-ttu-id="98a1f-107">如果您选择允许在修改证书时访问自动发现服务，则可能会证明困难或不会导致成本降低。</span><span class="sxs-lookup"><span data-stu-id="98a1f-107">HTTP is used if you choose to allow access to the Autodiscover Service when modifying certificates might prove difficult or not cost justified.</span></span>

  - <span data-ttu-id="98a1f-108">客户端希望与 HTTPS 上的 Office Web Apps Server 联系。</span><span class="sxs-lookup"><span data-stu-id="98a1f-108">Clients expect to contact the Office Web Apps Server on HTTPS.</span></span> <span data-ttu-id="98a1f-109">Office Web Apps Server 需要来自 HTTPS/TCP/443 上的内部客户端的通信。</span><span class="sxs-lookup"><span data-stu-id="98a1f-109">The Office Web Apps Server expects communication from internal clients on HTTPS/TCP/443.</span></span> <span data-ttu-id="98a1f-110">建议的配置是允许从反向代理到 Office Web Apps Server 的 HTTPS/TCP/443。</span><span class="sxs-lookup"><span data-stu-id="98a1f-110">The recommended configuration is to allow HTTPS/TCP/443 from the reverse proxy to the Office Web Apps Server.</span></span>

  - <span data-ttu-id="98a1f-111">端口8080用于将流量从反向代理内部接口路由到前端服务器、前端池虚拟 IP （VIP）或可选控制器或控制器池 VIP。</span><span class="sxs-lookup"><span data-stu-id="98a1f-111">Port 8080 is used to route traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP.</span></span> <span data-ttu-id="98a1f-112">在需要修改外部 web 服务发布规则证书（例如，如果有大量 SIP 域）的情况下，运行 Lync 的移动设备需要使用端口 TCP 8080 来查找自动发现服务。</span><span class="sxs-lookup"><span data-stu-id="98a1f-112">Port TCP 8080 is required for mobile devices running Lync to locate the Autodiscover Service in situations where modifying the external web service publishing rule certificate is undesirable (for example, if you have a large number of SIP domains).</span></span> <span data-ttu-id="98a1f-113">如果选择使用必需的 SAN 项获取新证书，则端口 TCP 8080 是不需要的并且是可选的。</span><span class="sxs-lookup"><span data-stu-id="98a1f-113">If you choose to acquire new certificates with the necessary SAN entries, the port TCP 8080 is not needed and is optional.</span></span>

  - <span data-ttu-id="98a1f-114">端口4443用于从反向代理内部接口到前端服务器、前端池虚拟 IP （VIP）或可选控制器或控制器池 VIP 的流量</span><span class="sxs-lookup"><span data-stu-id="98a1f-114">Port 4443 is used for traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP</span></span>
    
    <span data-ttu-id="98a1f-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="98a1f-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>  
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="98a1f-116">请勿将4443通过 TCP 从反向代理与从管理中央管理存储角色的 Standard Edition 服务器或前端池的 TCP 流量相混淆的端口4443的内部部署相混淆。</span><span class="sxs-lookup"><span data-stu-id="98a1f-116">Do not confuse the 4443 over TCP from the reverse proxy to the internal deployment for the port 4443 over TCP traffic from the Standard Edition server or the Front End pool that manages the Central Management store role.</span></span>

    
    </div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="98a1f-117">端口和协议详细信息</span><span class="sxs-lookup"><span data-stu-id="98a1f-117">Port and Protocol Details</span></span>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="98a1f-118">反向代理服务器的防火墙详细信息：外部接口</span><span class="sxs-lookup"><span data-stu-id="98a1f-118">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98a1f-119">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="98a1f-119">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="98a1f-120">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="98a1f-120">Source IP Address</span></span></th>
<th><span data-ttu-id="98a1f-121">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="98a1f-121">Destination IP Address</span></span></th>
<th><span data-ttu-id="98a1f-122">备注</span><span class="sxs-lookup"><span data-stu-id="98a1f-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98a1f-123">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="98a1f-123">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="98a1f-124">任意</span><span class="sxs-lookup"><span data-stu-id="98a1f-124">Any</span></span></p></td>
<td><p><span data-ttu-id="98a1f-125">反向代理侦听器</span><span class="sxs-lookup"><span data-stu-id="98a1f-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="98a1f-126">Optional如果用户进入 http://&lt;publishedSiteFQDN&gt;，则重定向到 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="98a1f-126">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span></p>
<p><span data-ttu-id="98a1f-127">如果在组织不想修改外部 Web 服务发布规则证书的情况下，使用 Office Web Apps for 会议和运行 Lync 的移动设备的自动发现服务，也需要使用此属性。</span><span class="sxs-lookup"><span data-stu-id="98a1f-127">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98a1f-128">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="98a1f-128">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="98a1f-129">任意</span><span class="sxs-lookup"><span data-stu-id="98a1f-129">Any</span></span></p></td>
<td><p><span data-ttu-id="98a1f-130">反向代理侦听器</span><span class="sxs-lookup"><span data-stu-id="98a1f-130">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="98a1f-131">通讯簿下载、通讯簿 Web 查询服务、自动发现、客户端更新、会议内容、设备更新、组扩展、Office Web Apps for 会议、电话拨入式会议和会议。</span><span class="sxs-lookup"><span data-stu-id="98a1f-131">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="98a1f-132">反向代理服务器的防火墙详细信息：内部接口</span><span class="sxs-lookup"><span data-stu-id="98a1f-132">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98a1f-133">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="98a1f-133">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="98a1f-134">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="98a1f-134">Source IP Address</span></span></th>
<th><span data-ttu-id="98a1f-135">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="98a1f-135">Destination IP Address</span></span></th>
<th><span data-ttu-id="98a1f-136">备注</span><span class="sxs-lookup"><span data-stu-id="98a1f-136">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98a1f-137">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="98a1f-137">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="98a1f-138">内部反向代理接口</span><span class="sxs-lookup"><span data-stu-id="98a1f-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="98a1f-139">前端服务器、前端池、控制器、控制器池</span><span class="sxs-lookup"><span data-stu-id="98a1f-139">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="98a1f-140">如果组织不想修改外部 web 服务发布规则证书的情况下，使用运行 Lync 的移动设备的自动发现服务，则为必需。</span><span class="sxs-lookup"><span data-stu-id="98a1f-140">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p>
<p><span data-ttu-id="98a1f-141">发送到反向代理外部接口上的端口 80 的流量将从反向代理内部接口重定向到端口 8080 上的池，以便池 Web 服务可将其与内部 Web 流量区分开来。</span><span class="sxs-lookup"><span data-stu-id="98a1f-141">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98a1f-142">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="98a1f-142">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="98a1f-143">内部反向代理接口</span><span class="sxs-lookup"><span data-stu-id="98a1f-143">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="98a1f-144">前端服务器、前端池、控制器、控制器池</span><span class="sxs-lookup"><span data-stu-id="98a1f-144">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="98a1f-145">发送到反向代理外部接口上的端口 443 的流量将从反向代理内部接口重定向到端口 4443 上的池，以便池 Web 服务可将其与内部 Web 流量区分开来。</span><span class="sxs-lookup"><span data-stu-id="98a1f-145">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98a1f-146">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="98a1f-146">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="98a1f-147">内部反向代理接口</span><span class="sxs-lookup"><span data-stu-id="98a1f-147">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="98a1f-148">Office Web Apps for 会议</span><span class="sxs-lookup"><span data-stu-id="98a1f-148">Office Web Apps for conferencing</span></span></p></td>
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

