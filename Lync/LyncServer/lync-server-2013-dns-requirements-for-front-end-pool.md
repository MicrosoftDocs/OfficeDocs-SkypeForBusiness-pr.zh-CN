---
title: Lync Server 2013：前端池的 DNS 要求
description: Lync Server 2013：前端池的 DNS 要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pool
ms:assetid: 02d2aa6b-9e01-437b-a2df-00590280150d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398082(v=OCS.15)
ms:contentKeyID: 48183249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfce90eccb8c8dff94d4122c96c4ca68ea9150f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574328"
---
# <a name="dns-requirements-for-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="2f9a9-103">Lync Server 2013 中的前端池的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="2f9a9-103">DNS requirements for Front End pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f9a9-104">_**上次修改的主题：** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="2f9a9-104">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="2f9a9-105">若要成功完成此过程，至少应以 Domain Admins 组或 DnsAdmins 组成员的身份登录到服务器或域。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="2f9a9-106">在拓扑生成器中发布拓扑之前，需要配置所需的域名系统 (DNS) 记录。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-106">You need to configure the required Domain Name System (DNS) records prior to publishing your topology in Topology Builder.</span></span> <span data-ttu-id="2f9a9-107">此外，在 Lync Server 2013 部署的配置中使用的某些完全限定域名 (Fqdn) 是逻辑的，而不是物理服务器 Fqdn，因此在发布之前需要额外的 DNS 配置。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-107">Additionally, some of the fully qualified domain names (FQDNs) used in the configuration of a Lync Server 2013 deployment are logical and not physical server FQDNs, so additional DNS configuration is required prior to publishing.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="2f9a9-108">Lync Server 2013 不支持单标签域。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-108">Lync Server 2013 does not support single-labeled domains.</span></span> <span data-ttu-id="2f9a9-109">例如，支持具有名为 <STRONG>contoso.local</STRONG> 的根域的林，但不支持名为 <STRONG>local</STRONG> 的根域。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-109">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="2f9a9-110">有关详细信息，请参阅 Microsoft 知识库文章300684，"有关为带有单标签 DNS 名称的域配置 Windows 的信息"，请参阅<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp http://go.microsoft.com/fwlink/?linkid=3052&kbid=823018 = 300684</A>。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-110">For details, see Microsoft Knowledge Base article 300684, “Information about configuring Windows for domains with single-label DNS names,” at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=300684">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=300684</A>.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2f9a9-111">指定的名称必须与在服务器上配置的计算机名称相同。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-111">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="2f9a9-112">默认情况下，未加入域的计算机的计算机名称是短名称，不是 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-112">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="2f9a9-113">拓扑生成器使用 FQDN，而不是短名称。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-113">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="2f9a9-114">在分配运行 Lync Server、边缘服务器和池的服务器的 Fqdn 时，<STRONG>仅使用标准字符</STRONG> (包括 A – z、A – z、0–9和连字符) 。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-114"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your servers running Lync Server, Edge Servers, and pools.</span></span> <span data-ttu-id="2f9a9-115">不要使用 Unicode 字符或下划线。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-115">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="2f9a9-116">FQDN 中的非标准字符通常不受外部 DNS 和公共证书颁发机构 (CA) 的支持（如必须向证书中的 SN 分配 FQDN 时）。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-116">Nonstandard characters in an FQDN are often not supported by external DNS and public certification authorities (CAs) (when the FQDN must be assigned to the SN in the certificate).</span></span>



</div>

<span data-ttu-id="2f9a9-117">在部署拓扑之后，请确保已创建以下 Active Directory 和 DNS 记录， (根据您对特定功能的需求进行操作时，应注意) ：</span><span class="sxs-lookup"><span data-stu-id="2f9a9-117">Prior to operating the topology after it has been deployed, ensure that the following Active Directory and DNS records are created (as your needs for specific features dictate):</span></span>

  - <span data-ttu-id="2f9a9-118">将在拓扑中存在的每个服务器角色发布为 Active Directory 对象 (将计算机加入域将完成此) 。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-118">Each server role that will exist in the topology is published as an Active Directory object (joining the computer to the domain will accomplish this).</span></span>

  - <span data-ttu-id="2f9a9-119">每台服务器都存在 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-119">A DNS A Record exists for each server.</span></span>

  - <span data-ttu-id="2f9a9-120">如果计划对 sipinternaltls tcp 形式的客户端使用自动登录，则每个 SIP 域都存在一个 DNS SRV 记录。 \_ \_ \<SIP domain\> 。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-120">A DNS SRV Record exists for each SIP domain if you plan to use automatic logon for clients in the form of \_sipinternaltls\_tcp.\<SIP domain\>.</span></span> <span data-ttu-id="2f9a9-121">如果使用客户端的手动配置，则不需要此记录。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-121">If you will use manual configuration for clients, this record is not necessary.</span></span>

  - <span data-ttu-id="2f9a9-122">每个配置的简单 URL（通常有四种：会议、拨入、LWA 和计划程序）的 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-122">A DNS A Record for each configured simple URL, of which there are typically four: meet, dialin, lwa, and scheduler.</span></span> <span data-ttu-id="2f9a9-123">此外，还提供了管理员简单的 URL，它是访问 Lync Server 2013 控制面板的特殊 URL。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-123">Additionally, there is the admin simple URL which is a special URL for access to the Lync Server 2013 Control Panel.</span></span>

  - <span data-ttu-id="2f9a9-124">运行 SQL Server 的服务器必须加入域，并且拓扑生成器正在发布的计算机可以访问该服务器。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-124">The server running SQL Server must be joined to the domain, and reachable by the computer that Topology Builder is publishing from.</span></span>

<span data-ttu-id="2f9a9-125">此表遵照规划部分中提供的参考体系结构。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-125">The table follows the reference architectures presented in the Planning section.</span></span> <span data-ttu-id="2f9a9-126">有关详细信息，请参阅规划文档中的 [Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md) 。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-126">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) in the Planning documentation.</span></span>

<div id="sectionSection0" class="section">

### <a name="dns-records-required-for-the-front-end-pool"></a><span data-ttu-id="2f9a9-127">前端池所需的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="2f9a9-127">DNS Records Required for the Front End pool</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f9a9-128">位置</span><span class="sxs-lookup"><span data-stu-id="2f9a9-128">Location</span></span></th>
<th><span data-ttu-id="2f9a9-129">类型</span><span class="sxs-lookup"><span data-stu-id="2f9a9-129">Type</span></span></th>
<th><span data-ttu-id="2f9a9-130">FQDN</span><span class="sxs-lookup"><span data-stu-id="2f9a9-130">FQDN</span></span></th>
<th><span data-ttu-id="2f9a9-131">映射位置/注释</span><span class="sxs-lookup"><span data-stu-id="2f9a9-131">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f9a9-132">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="2f9a9-132">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-133">A</span><span class="sxs-lookup"><span data-stu-id="2f9a9-133">A</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-134">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2f9a9-134">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-135">Pool01（DNS 负载平衡）。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-135">Pool01 (DNS load balancing).</span></span> <span data-ttu-id="2f9a9-136">要求池中的每台前端服务器的 IP 地址的 DNS A 记录，映射到池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-136">Requires a DNS A record for the IP address of each Front End Server within the pool, mapping to the pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f9a9-137">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="2f9a9-137">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-138">A</span><span class="sxs-lookup"><span data-stu-id="2f9a9-138">A</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-139">pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2f9a9-139">pool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-140">Pool01（硬件负载平衡器的虚拟 IP (VIP)）。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-140">Pool01 (virtual IP (VIP) of hardware load balancer).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f9a9-141">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="2f9a9-141">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-142">A</span><span class="sxs-lookup"><span data-stu-id="2f9a9-142">A</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-143">fe01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2f9a9-143">fe01.contoso.net</span></span></p>
<p><span data-ttu-id="2f9a9-144">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2f9a9-144">fe02.contoso.net</span></span></p>
<p><span data-ttu-id="2f9a9-145">fe03.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2f9a9-145">fe03.contoso.net</span></span></p>
<p><span data-ttu-id="2f9a9-146">…</span><span class="sxs-lookup"><span data-stu-id="2f9a9-146">…</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-147">Pool01 前端服务器 (节点 1) 。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-147">Pool01 Front End Server (NODE 1).</span></span></p>
<p><span data-ttu-id="2f9a9-148">Pool01 前端服务器 (节点 2) 。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-148">Pool01 Front End Server (NODE 2).</span></span></p>
<p><span data-ttu-id="2f9a9-149">Pool01 前端服务器 (节点 3) 。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-149">Pool01 Front End Server (NODE 3).</span></span></p>
<p><span data-ttu-id="2f9a9-150">…</span><span class="sxs-lookup"><span data-stu-id="2f9a9-150">…</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f9a9-151">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="2f9a9-151">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-152">A</span><span class="sxs-lookup"><span data-stu-id="2f9a9-152">A</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-153">fe02.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2f9a9-153">fe02.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-154">Pool01 前端服务器 (节点 2) 。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-154">Pool01 Front End Server (NODE 2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f9a9-155">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="2f9a9-155">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-156">A</span><span class="sxs-lookup"><span data-stu-id="2f9a9-156">A</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-157">lsweb.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2f9a9-157">lsweb.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-158">客户端到服务器的 Web 通信的 Pool01 (VIP)。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-158">Pool01 (VIP) for client-to-server web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f9a9-159">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="2f9a9-159">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-160">A</span><span class="sxs-lookup"><span data-stu-id="2f9a9-160">A</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-161">sqlbe.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2f9a9-161">sqlbe.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-162">运行 SQL Server 2008 R2 的 Pool01 后端服务器。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-162">Pool01 Back End Server running SQL Server 2008 R2.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f9a9-163">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="2f9a9-163">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-164">A</span><span class="sxs-lookup"><span data-stu-id="2f9a9-164">A</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-165">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a9-165">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-166">对于 Lync Phone Edition 是必需的，或者自动登录未安装 DNS SRV 记录的客户端，以及严格的域匹配。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-166">Required for Lync Phone Edition, or automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="2f9a9-167">并非在所有情况下都需要。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-167">Not required in all cases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f9a9-168">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="2f9a9-168">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-169">A</span><span class="sxs-lookup"><span data-stu-id="2f9a9-169">A</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-170">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2f9a9-170">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-171">假定存在第二个 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-171">Assumes a second SIP domain.</span></span> <span data-ttu-id="2f9a9-172">对于 Lync Phone Edition 是必需的，自动登录没有 DNS SRV 记录的客户端，以及严格的域匹配。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-172">Required for Lync Phone Edition, automatic logon of clients without DNS SRV records, and for strict domain matching.</span></span> <span data-ttu-id="2f9a9-173">并非在所有情况下都需要。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-173">Not required in all cases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f9a9-174">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="2f9a9-174">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-175">A</span><span class="sxs-lookup"><span data-stu-id="2f9a9-175">A</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-176">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a9-176">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-177">内部发布的电话拨入式会议的简单 URL –前端服务器 (或控制器，如果安装) 对简单 URL 查询做出响应。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-177">Simple URL for dial-in conferencing published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f9a9-178">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="2f9a9-178">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-179">A</span><span class="sxs-lookup"><span data-stu-id="2f9a9-179">A</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-180">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a9-180">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-181">用于内部发布的会议的简单 URL –前端服务器 (或控制器，如果安装) 响应简单 URL 查询。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-181">Simple URL for conferences published internally – Front End Server (or Director, if installed) responds to simple URL queries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f9a9-182">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="2f9a9-182">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-183">A</span><span class="sxs-lookup"><span data-stu-id="2f9a9-183">A</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-184">admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a9-184">admin.contoso.com</span></span></p>
<p><span data-ttu-id="2f9a9-185">admin</span><span class="sxs-lookup"><span data-stu-id="2f9a9-185">admin</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-186">可选记录、Lync Server 2013 控制面板的简单 URL 发布内部-前端服务器 (或控制器，如果安装) 响应简单 URL 查询。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-186">Optional record, simple URL for Lync Server 2013 Control Panel published internally - Front End Server (or Director, if installed) responds to simple URL queries.</span></span> <span data-ttu-id="2f9a9-187">建议只使用主机名（无域名）。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-187">Host name only (no domain name) is recommended.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="2f9a9-188">VIP 表示硬件负载平衡器的虚拟 IP 地址</span><span class="sxs-lookup"><span data-stu-id="2f9a9-188">VIP = Virtual IP address for hardware load balancer</span></span>



</div>

</div>

<div>

## <a name="dns-srv-records-for-the-front-end-pool"></a><span data-ttu-id="2f9a9-189">前端池的 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="2f9a9-189">DNS SRV Records for the Front End pool</span></span>


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f9a9-190">位置</span><span class="sxs-lookup"><span data-stu-id="2f9a9-190">Location</span></span></th>
<th><span data-ttu-id="2f9a9-191">类型</span><span class="sxs-lookup"><span data-stu-id="2f9a9-191">Type</span></span></th>
<th><span data-ttu-id="2f9a9-192">FQDN</span><span class="sxs-lookup"><span data-stu-id="2f9a9-192">FQDN</span></span></th>
<th><span data-ttu-id="2f9a9-193">目标 FQDN</span><span class="sxs-lookup"><span data-stu-id="2f9a9-193">Target FQDN</span></span></th>
<th><span data-ttu-id="2f9a9-194">端口</span><span class="sxs-lookup"><span data-stu-id="2f9a9-194">Port</span></span></th>
<th><span data-ttu-id="2f9a9-195">映射位置/注释</span><span class="sxs-lookup"><span data-stu-id="2f9a9-195">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f9a9-196">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="2f9a9-196">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-197">SRV</span><span class="sxs-lookup"><span data-stu-id="2f9a9-197">SRV</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-198">_sipinternaltls _sipinternaltls._tcp .com</span><span class="sxs-lookup"><span data-stu-id="2f9a9-198">_sipinternaltls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-199">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a9-199">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-200">5061</span><span class="sxs-lookup"><span data-stu-id="2f9a9-200">5061</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-201">自动配置 Lync 2013 客户端以在内部工作的必需。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-201">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f9a9-202">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="2f9a9-202">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-203">SRV</span><span class="sxs-lookup"><span data-stu-id="2f9a9-203">SRV</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-204">_sipinternaltls _sipinternaltls._tcp .com</span><span class="sxs-lookup"><span data-stu-id="2f9a9-204">_sipinternaltls._tcp.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-205">pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2f9a9-205">pool01.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-206">5061</span><span class="sxs-lookup"><span data-stu-id="2f9a9-206">5061</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-207">自动配置 Lync 2013 客户端以在内部工作的必需。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-207">Required for automatic configuration of Lync 2013 clients to work internally.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f9a9-208">内部 DNS</span><span class="sxs-lookup"><span data-stu-id="2f9a9-208">Internal DNS</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-209">SRV</span><span class="sxs-lookup"><span data-stu-id="2f9a9-209">SRV</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-210">_ntp _ntp._udp .com</span><span class="sxs-lookup"><span data-stu-id="2f9a9-210">_ntp._udp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-211">dc01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2f9a9-211">dc01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-212">123</span><span class="sxs-lookup"><span data-stu-id="2f9a9-212">123</span></span></p></td>
<td><p><span data-ttu-id="2f9a9-213">运行 Lync Phone Edition 的设备所需的网络时间协议 (NTP) 源。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-213">Network Time Protocol (NTP) source required for devices running Lync Phone Edition.</span></span> <span data-ttu-id="2f9a9-214">在内部，它应指向域控制器。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-214">Internally, this should point to the domain controller.</span></span> <span data-ttu-id="2f9a9-215">如果未定义域控制器，则会尝试使用 NTP 服务器 time.windows.com。</span><span class="sxs-lookup"><span data-stu-id="2f9a9-215">If the domain controller is not defined, it will try to use the NTP server time.windows.com.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

