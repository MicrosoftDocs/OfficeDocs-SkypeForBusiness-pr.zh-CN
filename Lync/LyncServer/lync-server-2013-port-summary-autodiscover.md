---
title: Lync Server 2013：端口摘要-自动发现
description: Lync Server 2013：端口摘要-自动发现。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20a5ef54d4ad8419fd6e73909f97764bf1290c22
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543138"
---
# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="c87e0-103">Lync Server 2013 中的端口摘要-自动发现</span><span class="sxs-lookup"><span data-stu-id="c87e0-103">Port summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c87e0-104">_**上次修改的主题：** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="c87e0-104">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="c87e0-105">Lync Server 2013 自动发现服务在控制器和前端池服务器上运行，并且在使用和主机记录在 DNS 中发布时， `lyncdiscover.<domain>` `lyncdiscoverinternal.<domain>` 客户端可以使用它们查找 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="c87e0-105">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="c87e0-106">为了使 Lync Mobile 运行的移动设备使用自动发现，您可能需要首先在运行自动发现服务的任何控制器和前端服务器上修改证书主题备用名称列表。</span><span class="sxs-lookup"><span data-stu-id="c87e0-106">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="c87e0-107">此外，可能还必须修改证书上的供反向代理上的外部 Web 服务发布规则使用的使用者替代名称列表。</span><span class="sxs-lookup"><span data-stu-id="c87e0-107">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="c87e0-108">有关是否在反向代理上使用主题备用名称列表的决策取决于您是在端口80上还是在端口443上发布自动发现服务：</span><span class="sxs-lookup"><span data-stu-id="c87e0-108">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="c87e0-109">**已在端口 80**     上发布对于移动设备，如果对自动发现服务的初始查询在端口80上发生，则不需要进行证书更改。</span><span class="sxs-lookup"><span data-stu-id="c87e0-109">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="c87e0-110">这是因为运行 Lync 的移动设备将在外部端口80上访问反向代理，然后在内部将其重定向到端口8080上的控制器或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="c87e0-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="c87e0-111">**已在端口 443**     上发布外部 web 服务发布规则所使用的证书上的 "主题备用名称" 列表必须包含 `lyncdiscover.<sipdomain>` 组织内每个 SIP 域的条目。</span><span class="sxs-lookup"><span data-stu-id="c87e0-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c87e0-112">对于部署了移动性的 Lync Server 2010 的全新安装或升级，您可以使用端口80自动发现移动服务，或者就地重新颁发具有正确主题名称和使用者备用名称的证书。</span><span class="sxs-lookup"><span data-stu-id="c87e0-112">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="c87e0-113">查看控制器和前端服务器上的证书，确认选择了哪个路径。</span><span class="sxs-lookup"><span data-stu-id="c87e0-113">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="c87e0-114">反向代理服务器的防火墙详细信息：外部接口</span><span class="sxs-lookup"><span data-stu-id="c87e0-114">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c87e0-115">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="c87e0-115">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c87e0-116">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="c87e0-116">Source IP Address</span></span></th>
<th><span data-ttu-id="c87e0-117">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="c87e0-117">Destination IP Address</span></span></th>
<th><span data-ttu-id="c87e0-118">注释</span><span class="sxs-lookup"><span data-stu-id="c87e0-118">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c87e0-119">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="c87e0-119">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="c87e0-120">任何</span><span class="sxs-lookup"><span data-stu-id="c87e0-120">Any</span></span></p></td>
<td><p><span data-ttu-id="c87e0-121">反向代理侦听器</span><span class="sxs-lookup"><span data-stu-id="c87e0-121">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="c87e0-122"> (可选) 重定向到 HTTPS （如果用户进入 http:// &lt; publishedSiteFQDN &gt; 。</span><span class="sxs-lookup"><span data-stu-id="c87e0-122">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="c87e0-123">如果在组织不想修改外部 Web 服务发布规则证书的情况下，使用 Office Web Apps for 会议和运行 Lync 的移动设备的自动发现服务，也需要使用此属性。</span><span class="sxs-lookup"><span data-stu-id="c87e0-123">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c87e0-124">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c87e0-124">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c87e0-125">任何</span><span class="sxs-lookup"><span data-stu-id="c87e0-125">Any</span></span></p></td>
<td><p><span data-ttu-id="c87e0-126">反向代理侦听器</span><span class="sxs-lookup"><span data-stu-id="c87e0-126">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="c87e0-127">通讯簿下载、通讯簿 Web 查询服务、自动发现、客户端更新、会议内容、设备更新、组扩展、Office Web Apps for 会议、电话拨入式会议和会议。</span><span class="sxs-lookup"><span data-stu-id="c87e0-127">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="c87e0-128">反向代理服务器的防火墙详细信息：内部接口</span><span class="sxs-lookup"><span data-stu-id="c87e0-128">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c87e0-129">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="c87e0-129">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c87e0-130">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="c87e0-130">Source IP Address</span></span></th>
<th><span data-ttu-id="c87e0-131">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="c87e0-131">Destination IP Address</span></span></th>
<th><span data-ttu-id="c87e0-132">注释</span><span class="sxs-lookup"><span data-stu-id="c87e0-132">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c87e0-133">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="c87e0-133">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="c87e0-134">内部反向代理接口</span><span class="sxs-lookup"><span data-stu-id="c87e0-134">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="c87e0-135">前端服务器、前端池、控制器、控制器池、适用于会议的 Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="c87e0-135">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="c87e0-136">如果组织不想修改外部 web 服务发布规则证书的情况下，使用运行 Lync 的移动设备的自动发现服务，则为必需。</span><span class="sxs-lookup"><span data-stu-id="c87e0-136">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="c87e0-137">发送到反向代理外部接口上的端口 80 的流量将从反向代理内部接口重定向到端口 8080 上的池，以便池 Web 服务可将其与内部 Web 流量区分开来。</span><span class="sxs-lookup"><span data-stu-id="c87e0-137">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c87e0-138">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="c87e0-138">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="c87e0-139">内部反向代理接口</span><span class="sxs-lookup"><span data-stu-id="c87e0-139">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="c87e0-140">前端服务器、前端池、控制器、控制器池、适用于会议的 Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="c87e0-140">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="c87e0-141">发送到反向代理外部接口上的端口 443 的流量将从反向代理内部接口重定向到端口 4443 上的池，以便池 Web 服务可将其与内部 Web 流量区分开来。</span><span class="sxs-lookup"><span data-stu-id="c87e0-141">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

