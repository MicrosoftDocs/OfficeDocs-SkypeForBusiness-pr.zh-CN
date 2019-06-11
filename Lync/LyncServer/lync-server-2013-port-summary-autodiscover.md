---
title: 'Lync Server 2013: 端口摘要-自动发现'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a40d86799b4922a819642aedf2461f038330593
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="0e4ff-102">端口摘要-Lync Server 2013 中的自动发现</span><span class="sxs-lookup"><span data-stu-id="0e4ff-102">Port summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e4ff-103">_**主题上次修改时间:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="0e4ff-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="0e4ff-104">Lync Server 2013 自动发现服务在 Director 和前端池服务器上运行, 并且当使用和`lyncdiscover.<domain>` `lyncdiscoverinternal.<domain>`主机记录在 DNS 中发布时, 客户端可以使用该服务查找 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="0e4ff-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="0e4ff-105">为使 Lync Mobile 运行的移动设备使用自动发现, 你可能需要首先在运行自动发现服务的任何控制器和前端服务器上修改证书主题备用名称列表。</span><span class="sxs-lookup"><span data-stu-id="0e4ff-105">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="0e4ff-106">此外, 可能还需要修改用于反向代理上的外部 web 服务发布规则的证书上的使用者备用名称列表。</span><span class="sxs-lookup"><span data-stu-id="0e4ff-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="0e4ff-107">有关是否在反向代理上使用主题备用名称列表的决策取决于你是在端口80还是在端口443上发布自动发现服务:</span><span class="sxs-lookup"><span data-stu-id="0e4ff-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="0e4ff-108">**已在端口 80**   上发布对于移动设备, 如果对自动发现服务的初始查询通过端口80进行, 则不需要进行证书更改。</span><span class="sxs-lookup"><span data-stu-id="0e4ff-108">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="0e4ff-109">这是因为运行 Lync 的移动设备将外部访问端口80上的反向代理, 然后在内部将其重定向到端口8080上的 Director 或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="0e4ff-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="0e4ff-110">**在端口 443**   上发布在外部 web 服务发布规则使用的证书上的 "使用者备用名称" `lyncdiscover.<sipdomain>`列表中, 必须包含组织内每个 SIP 域的条目。</span><span class="sxs-lookup"><span data-stu-id="0e4ff-110">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0e4ff-111">对于部署了移动性的 Lync Server 2010 的全新安装或升级, 你可以使用端口80自动发现移动服务, 或者将证书重新颁发给适当的主题名称和主题备用名称。</span><span class="sxs-lookup"><span data-stu-id="0e4ff-111">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="0e4ff-112">查看控制器和前端服务器上的证书以确认您选择的路径。</span><span class="sxs-lookup"><span data-stu-id="0e4ff-112">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="0e4ff-113">反向代理服务器的防火墙详细信息: 外部接口</span><span class="sxs-lookup"><span data-stu-id="0e4ff-113">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e4ff-114">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="0e4ff-114">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="0e4ff-115">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="0e4ff-115">Source IP Address</span></span></th>
<th><span data-ttu-id="0e4ff-116">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="0e4ff-116">Destination IP Address</span></span></th>
<th><span data-ttu-id="0e4ff-117">注释</span><span class="sxs-lookup"><span data-stu-id="0e4ff-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e4ff-118">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="0e4ff-118">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="0e4ff-119">任意</span><span class="sxs-lookup"><span data-stu-id="0e4ff-119">Any</span></span></p></td>
<td><p><span data-ttu-id="0e4ff-120">反向代理侦听器</span><span class="sxs-lookup"><span data-stu-id="0e4ff-120">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="0e4ff-121">可选如果用户进入 http://&lt;publishedSiteFQDN&gt;, 则重定向到 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="0e4ff-121">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="0e4ff-122">如果在组织不希望修改外部 Web 服务发布规则证书的情况下, 使用适用于会议的 Office Web Apps 和适用于运行 Lync 的移动设备的自动发现服务, 也需要使用此参数。</span><span class="sxs-lookup"><span data-stu-id="0e4ff-122">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4ff-123">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="0e4ff-123">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="0e4ff-124">任意</span><span class="sxs-lookup"><span data-stu-id="0e4ff-124">Any</span></span></p></td>
<td><p><span data-ttu-id="0e4ff-125">反向代理侦听器</span><span class="sxs-lookup"><span data-stu-id="0e4ff-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="0e4ff-126">通讯簿下载, 通讯簿 Web 查询服务, 自动发现, 客户端更新, 会议内容, 设备更新, 组扩展, 适用于会议的 Office Web Apps, 电话拨入式会议和会议。</span><span class="sxs-lookup"><span data-stu-id="0e4ff-126">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="0e4ff-127">反向代理服务器的防火墙详细信息: 内部接口</span><span class="sxs-lookup"><span data-stu-id="0e4ff-127">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e4ff-128">协议/TCP 或 UDP/端口</span><span class="sxs-lookup"><span data-stu-id="0e4ff-128">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="0e4ff-129">源 IP 地址</span><span class="sxs-lookup"><span data-stu-id="0e4ff-129">Source IP Address</span></span></th>
<th><span data-ttu-id="0e4ff-130">目标 IP 地址</span><span class="sxs-lookup"><span data-stu-id="0e4ff-130">Destination IP Address</span></span></th>
<th><span data-ttu-id="0e4ff-131">注释</span><span class="sxs-lookup"><span data-stu-id="0e4ff-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e4ff-132">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="0e4ff-132">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="0e4ff-133">内部反向代理接口</span><span class="sxs-lookup"><span data-stu-id="0e4ff-133">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="0e4ff-134">前端服务器、前端池、导演、控制器池、Office Web Apps for 电话会议</span><span class="sxs-lookup"><span data-stu-id="0e4ff-134">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="0e4ff-135">如果在组织不希望修改外部 web 服务发布规则证书的情况下使用运行 Lync 的移动设备的自动发现服务, 则为必需。</span><span class="sxs-lookup"><span data-stu-id="0e4ff-135">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="0e4ff-136">发送到反向代理外部接口上的端口80的流量将从反向代理内部接口重定向到端口8080上的池, 以便池 Web 服务可以将其与内部 Web 流量区分开。</span><span class="sxs-lookup"><span data-stu-id="0e4ff-136">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e4ff-137">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="0e4ff-137">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="0e4ff-138">内部反向代理接口</span><span class="sxs-lookup"><span data-stu-id="0e4ff-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="0e4ff-139">前端服务器、前端池、导演、控制器池、Office Web Apps for 电话会议</span><span class="sxs-lookup"><span data-stu-id="0e4ff-139">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="0e4ff-140">发送到反向代理外部接口上的端口443的流量将从反向代理内部接口重定向到端口4443上的池, 以便池 web 服务可以将其与内部 web 流量区分开。</span><span class="sxs-lookup"><span data-stu-id="0e4ff-140">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

