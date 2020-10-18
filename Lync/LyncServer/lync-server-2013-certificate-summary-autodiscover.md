---
title: Lync Server 2013：证书摘要-自动发现
description: Lync Server 2013：证书摘要-自动发现。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae421401421434a4c4069c1d90ee287dfb016997
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574708"
---
# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="31b3d-103">证书摘要-Lync Server 2013 中的自动发现</span><span class="sxs-lookup"><span data-stu-id="31b3d-103">Certificate summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31b3d-104">_**上次修改的主题：** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="31b3d-104">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="31b3d-105">Lync Server 2013 自动发现服务在控制器和前端池服务器上运行，并且在 DNS 中发布时可供 Lync 客户端用来查找服务器和用户服务。</span><span class="sxs-lookup"><span data-stu-id="31b3d-105">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="31b3d-106">如果要从 Lync Server 2010 升级且未部署移动性，则在客户端可以使用自动发现之前，必须在运行自动发现服务的任何控制器和前端服务器上修改证书使用者备用名称列表。</span><span class="sxs-lookup"><span data-stu-id="31b3d-106">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="31b3d-107">此外，可能还必须修改证书上的供反向代理上的外部 Web 服务发布规则使用的使用者替代名称列表。</span><span class="sxs-lookup"><span data-stu-id="31b3d-107">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="31b3d-108">有关是否在反向代理上使用主题备用名称列表的决策取决于您是在端口80上还是在端口443上发布自动发现服务：</span><span class="sxs-lookup"><span data-stu-id="31b3d-108">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="31b3d-109">**已在端口 80**     上发布如果对自动发现服务的初始查询在端口80上发生，则不需要进行证书更改。</span><span class="sxs-lookup"><span data-stu-id="31b3d-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="31b3d-110">这是因为运行 Lync 的移动设备将在外部端口80上访问反向代理，然后在内部桥接到端口8080上的控制器或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="31b3d-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="31b3d-111">有关详细信息，请参阅 [Lync Server 2013 中的移动性技术要求](lync-server-2013-technical-requirements-for-mobility.md)一节中的 "使用端口80初始自动发现过程" 一节。</span><span class="sxs-lookup"><span data-stu-id="31b3d-111">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="31b3d-112">**已在端口 443**     上发布外部 web 服务发布规则所使用的证书上的 "主题备用名称" 列表必须包含*lyncdiscover. \<sipdomain\> 。*</span><span class="sxs-lookup"><span data-stu-id="31b3d-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>*</span></span> <span data-ttu-id="31b3d-113">组织中每个 SIP 域的条目。</span><span class="sxs-lookup"><span data-stu-id="31b3d-113">entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="31b3d-114">强烈建议使用 HTTPS over HTTP。</span><span class="sxs-lookup"><span data-stu-id="31b3d-114">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="31b3d-115">HTTPS 使用证书对流量进行加密。</span><span class="sxs-lookup"><span data-stu-id="31b3d-115">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="31b3d-116">HTTP 不提供加密功能，发送的任何数据将为纯文本。</span><span class="sxs-lookup"><span data-stu-id="31b3d-116">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="31b3d-117">使用内部证书颁发机构重新发起证书通常是一个简单的过程。</span><span class="sxs-lookup"><span data-stu-id="31b3d-117">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="31b3d-118">但对于 web 服务发布规则上使用的公共证书，添加多个使用者可选名称条目可能会变得昂贵。</span><span class="sxs-lookup"><span data-stu-id="31b3d-118">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="31b3d-119">若要解决此问题，我们支持通过端口80的初始自动发现连接，该连接随后将被重定向到控制器或前端服务器上的端口8080。</span><span class="sxs-lookup"><span data-stu-id="31b3d-119">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="31b3d-120">如果你的 Lync Server 2013 基础结构使用从内部证书颁发机构颁发的内部证书 (CA) ，并且计划支持通过无线方式连接的移动设备，则必须在移动设备上安装内部 CA 的根证书链，或者必须将其更改为 Lync Server 2013 基础结构上的公共证书。</span><span class="sxs-lookup"><span data-stu-id="31b3d-120">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="31b3d-121">本主题介绍了控制器、前端服务器和反向代理所需的已添加主题替代名称。</span><span class="sxs-lookup"><span data-stu-id="31b3d-121">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="31b3d-122">仅引用添加的主题替代名称 (SAN) 。</span><span class="sxs-lookup"><span data-stu-id="31b3d-122">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="31b3d-123">有关证书的其他条目的指导，请参阅规划部分。</span><span class="sxs-lookup"><span data-stu-id="31b3d-123">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="31b3d-124">有关详细信息，请参阅 lync server [2013 中的 Director 方案](lync-server-2013-scenarios-for-the-director.md)、 [lync server 2013 中的外部用户访问](lync-server-2013-scenarios-for-external-user-access.md)方案和 [lync server 2013 中的反向代理](lync-server-2013-scenarios-for-reverse-proxy.md)方案。</span><span class="sxs-lookup"><span data-stu-id="31b3d-124">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="31b3d-125">下表定义了控制器池、前端池和反向代理的自动发现 SAN 条目：</span><span class="sxs-lookup"><span data-stu-id="31b3d-125">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="31b3d-126">控制器池证书要求</span><span class="sxs-lookup"><span data-stu-id="31b3d-126">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31b3d-127">说明</span><span class="sxs-lookup"><span data-stu-id="31b3d-127">Description</span></span></th>
<th><span data-ttu-id="31b3d-128">使用者替代名称条目</span><span class="sxs-lookup"><span data-stu-id="31b3d-128">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31b3d-129">内部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="31b3d-129">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="31b3d-130">SAN = lyncdiscoverinternal.。 &lt;内部域名&gt;</span><span class="sxs-lookup"><span data-stu-id="31b3d-130">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31b3d-131">外部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="31b3d-131">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="31b3d-132">SAN = lyncdiscover.。 &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="31b3d-132">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="31b3d-133">将新更新的证书和新的 SAN 条目分配给默认证书。</span><span class="sxs-lookup"><span data-stu-id="31b3d-133">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="31b3d-134">或者，也可以使用 SAN = \*。 &lt;sipdomain &gt; 。</span><span class="sxs-lookup"><span data-stu-id="31b3d-134">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="31b3d-135">前端池证书要求</span><span class="sxs-lookup"><span data-stu-id="31b3d-135">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31b3d-136">说明</span><span class="sxs-lookup"><span data-stu-id="31b3d-136">Description</span></span></th>
<th><span data-ttu-id="31b3d-137">使用者替代名称条目</span><span class="sxs-lookup"><span data-stu-id="31b3d-137">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31b3d-138">内部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="31b3d-138">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="31b3d-139">SAN = lyncdiscoverinternal.。 &lt;内部域名&gt;</span><span class="sxs-lookup"><span data-stu-id="31b3d-139">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31b3d-140">外部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="31b3d-140">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="31b3d-141">SAN = lyncdiscover.。 &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="31b3d-141">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="31b3d-142">将新更新的证书和新的 SAN 条目分配给默认证书。</span><span class="sxs-lookup"><span data-stu-id="31b3d-142">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="31b3d-143">或者，也可以使用 SAN = \*。 &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="31b3d-143">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="31b3d-144">反向代理（公共 CA）证书要求</span><span class="sxs-lookup"><span data-stu-id="31b3d-144">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31b3d-145">说明</span><span class="sxs-lookup"><span data-stu-id="31b3d-145">Description</span></span></th>
<th><span data-ttu-id="31b3d-146">使用者替代名称条目</span><span class="sxs-lookup"><span data-stu-id="31b3d-146">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31b3d-147">外部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="31b3d-147">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="31b3d-148">SAN = lyncdiscover.。 &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="31b3d-148">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="31b3d-149">将新更新的证书和新的 SAN 条目分配给反向代理上的 SSL 侦听器。</span><span class="sxs-lookup"><span data-stu-id="31b3d-149">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

