---
title: 'Lync Server 2013: 证书摘要-自动发现'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59c3777f9b13dc18e3e52e80120009f93c20db3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="5104b-102">证书摘要-Lync Server 2013 中的自动发现</span><span class="sxs-lookup"><span data-stu-id="5104b-102">Certificate summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5104b-103">_**主题上次修改时间:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="5104b-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="5104b-104">Lync Server 2013 自动发现服务在 Director 和前端池服务器上运行, 并且当在 DNS 中发布时, 可供 Lync 客户端用于查找服务器和用户服务。</span><span class="sxs-lookup"><span data-stu-id="5104b-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="5104b-105">如果从 Lync Server 2010 升级, 并且未部署移动性, 则在客户端可以使用自动发现之前, 必须在运行自动发现服务的任何控制器和前端服务器上修改证书使用者备用名称列表。</span><span class="sxs-lookup"><span data-stu-id="5104b-105">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="5104b-106">此外, 可能还需要修改用于反向代理上的外部 web 服务发布规则的证书上的使用者备用名称列表。</span><span class="sxs-lookup"><span data-stu-id="5104b-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="5104b-107">有关是否在反向代理上使用主题备用名称列表的决策取决于你是在端口80还是在端口443上发布自动发现服务:</span><span class="sxs-lookup"><span data-stu-id="5104b-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="5104b-108">**已在端口 80**   上发布如果自动发现服务的初始查询通过端口80进行, 则不需要进行证书更改。</span><span class="sxs-lookup"><span data-stu-id="5104b-108">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="5104b-109">这是因为运行 Lync 的移动设备将外部访问端口80上的反向代理, 然后在内部将其桥接到端口8080上的 Director 或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="5104b-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="5104b-110">有关详细信息, 请参阅[Lync Server 2013 中的移动技术要求](lync-server-2013-technical-requirements-for-mobility.md)"使用端口80初始自动发现过程" 部分。</span><span class="sxs-lookup"><span data-stu-id="5104b-110">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="5104b-111">**在端口 443**   上发布在外部 web 服务发布规则使用的证书上的 "主题" 备用名称列表中必须包含\*lyncdiscover。\<组织\> \*中每个 SIP 域的 sipdomain 条目。</span><span class="sxs-lookup"><span data-stu-id="5104b-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5104b-112">强烈建议通过 HTTP 使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="5104b-112">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="5104b-113">HTTPS 使用证书加密通信。</span><span class="sxs-lookup"><span data-stu-id="5104b-113">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="5104b-114">HTTP 不提供加密, 并且发送的任何数据都将是纯文本。</span><span class="sxs-lookup"><span data-stu-id="5104b-114">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="5104b-115">使用内部证书颁发机构重新发起证书通常是一个简单的过程。</span><span class="sxs-lookup"><span data-stu-id="5104b-115">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="5104b-116">但对于用于 web 服务发布规则的公共证书, 添加多个使用者可选名称条目可能会很高。</span><span class="sxs-lookup"><span data-stu-id="5104b-116">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="5104b-117">若要解决此问题, 我们通过端口80支持初始自动发现连接, 该连接随后将被重定向到 Director 或前端服务器上的端口8080。</span><span class="sxs-lookup"><span data-stu-id="5104b-117">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5104b-118">如果您的 Lync Server 2013 基础结构使用由内部证书颁发机构 (CA) 颁发的内部证书, 并且您计划支持以无线方式连接的移动设备, 则必须安装来自内部 CA 的根证书链在移动设备上, 或者必须在 Lync Server 2013 基础结构上更改为公共证书。</span><span class="sxs-lookup"><span data-stu-id="5104b-118">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="5104b-119">本主题介绍了 Director、前端服务器和反向代理所需的已添加主题备用名称。</span><span class="sxs-lookup"><span data-stu-id="5104b-119">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="5104b-120">仅引用已添加的主题备用名称 (SAN)。</span><span class="sxs-lookup"><span data-stu-id="5104b-120">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="5104b-121">有关证书的其他条目的指南, 请参阅规划部分。</span><span class="sxs-lookup"><span data-stu-id="5104b-121">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="5104b-122">有关详细信息, 请参阅 lync [server 2013 中的主管方案](lync-server-2013-scenarios-for-the-director.md)、 [lync server 2013 中的外部用户访问应用场景](lync-server-2013-scenarios-for-external-user-access.md)和[lync server 2013 中的反向代理](lync-server-2013-scenarios-for-reverse-proxy.md)方案。</span><span class="sxs-lookup"><span data-stu-id="5104b-122">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="5104b-123">下表定义了控制器池、前端池和反向代理的自动发现 SAN 条目:</span><span class="sxs-lookup"><span data-stu-id="5104b-123">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="5104b-124">控制器池证书要求</span><span class="sxs-lookup"><span data-stu-id="5104b-124">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5104b-125">说明</span><span class="sxs-lookup"><span data-stu-id="5104b-125">Description</span></span></th>
<th><span data-ttu-id="5104b-126">主题可选名称条目</span><span class="sxs-lookup"><span data-stu-id="5104b-126">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5104b-127">内部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="5104b-127">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="5104b-128">SAN = lyncdiscoverinternal。&lt;内部域名&gt;</span><span class="sxs-lookup"><span data-stu-id="5104b-128">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5104b-129">外部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="5104b-129">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="5104b-130">SAN = lyncdiscover。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5104b-130">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="5104b-131">将新的已更新证书分配给默认证书的新的 SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="5104b-131">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="5104b-132">或者, 您可以使用 SAN = \*。&lt;sipdomain&gt;。</span><span class="sxs-lookup"><span data-stu-id="5104b-132">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="5104b-133">前端池证书要求</span><span class="sxs-lookup"><span data-stu-id="5104b-133">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5104b-134">说明</span><span class="sxs-lookup"><span data-stu-id="5104b-134">Description</span></span></th>
<th><span data-ttu-id="5104b-135">主题可选名称条目</span><span class="sxs-lookup"><span data-stu-id="5104b-135">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5104b-136">内部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="5104b-136">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="5104b-137">SAN = lyncdiscoverinternal。&lt;内部域名&gt;</span><span class="sxs-lookup"><span data-stu-id="5104b-137">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5104b-138">外部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="5104b-138">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="5104b-139">SAN = lyncdiscover。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5104b-139">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="5104b-140">将新的已更新证书分配给默认证书的新的 SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="5104b-140">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="5104b-141">或者, 您可以使用 SAN = \*。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5104b-141">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="5104b-142">反向代理 (公共 CA) 证书要求</span><span class="sxs-lookup"><span data-stu-id="5104b-142">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5104b-143">说明</span><span class="sxs-lookup"><span data-stu-id="5104b-143">Description</span></span></th>
<th><span data-ttu-id="5104b-144">主题可选名称条目</span><span class="sxs-lookup"><span data-stu-id="5104b-144">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5104b-145">外部自动发现服务 URL</span><span class="sxs-lookup"><span data-stu-id="5104b-145">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="5104b-146">SAN = lyncdiscover。&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5104b-146">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="5104b-147">将新更新的证书和新的 SAN 条目分配给反向代理上的 SSL 侦听器。</span><span class="sxs-lookup"><span data-stu-id="5104b-147">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

