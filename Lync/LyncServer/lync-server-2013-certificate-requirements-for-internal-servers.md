---
title: Lync Server 2013：内部服务器的证书要求
description: Lync Server 2013：内部服务器的证书要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc1a627dd762c849b848087a96e00e19d320ef01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575208"
---
# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="ba71d-103">Lync Server 2013 中的内部服务器的证书要求</span><span class="sxs-lookup"><span data-stu-id="ba71d-103">Certificate requirements for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba71d-104">_**上次修改的主题：** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="ba71d-104">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="ba71d-105">运行 Lync Server 且要求证书的内部服务器包括 Standard Edition server、Enterprise Edition 前端服务器、中介服务器和控制器。</span><span class="sxs-lookup"><span data-stu-id="ba71d-105">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="ba71d-106">下表显示了这些服务器的证书要求。</span><span class="sxs-lookup"><span data-stu-id="ba71d-106">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="ba71d-107">您可以使用 Lync Server 证书向导来请求这些证书。</span><span class="sxs-lookup"><span data-stu-id="ba71d-107">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="ba71d-108">对于与前端池、前端服务器或控制器上的简单 Url 相关联的使用者替代名称，支持通配符证书。</span><span class="sxs-lookup"><span data-stu-id="ba71d-108">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="ba71d-109">有关通配符证书支持的详细信息，请参阅 <A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013 中的通配符证书支持</A>。</span><span class="sxs-lookup"><span data-stu-id="ba71d-109">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="ba71d-110">虽然建议对内部服务器使用内部企业证书颁发机构 (CA)，但您也可以使用公共 CA。</span><span class="sxs-lookup"><span data-stu-id="ba71d-110">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="ba71d-111">有关公用 Ca 的列表，该列表提供符合统一通信 (UC) 证书的特定要求的证书，并已与 Microsoft 合作以确保它们使用 Lync Server 证书向导，请参阅文章 Microsoft 知识库 929395 "Exchange Server 的统一通信证书合作伙伴和通信服务器"，网址为 at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) 。</span><span class="sxs-lookup"><span data-stu-id="ba71d-111">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="ba71d-112">与其他应用程序和服务器（如 Exchange 2013）的通信需要其他应用程序和产品支持的证书。</span><span class="sxs-lookup"><span data-stu-id="ba71d-112">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="ba71d-113">对于2013版本，Lync Server 2013 和其他 Microsoft Server 产品（包括 Exchange 2013 和 SharePoint Server）支持开放授权 (OAuth) 协议用于服务器到服务器身份验证和授权。</span><span class="sxs-lookup"><span data-stu-id="ba71d-113">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="ba71d-114">有关详细信息，请参阅部署文档或操作文档中的 [管理服务器到服务器身份验证 (OAuth) 和在 Lync server 2013 中的合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 。</span><span class="sxs-lookup"><span data-stu-id="ba71d-114">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="ba71d-115">对于运行 Windows 7 操作系统、windows Server 2008 操作系统、Windows Server 2008 R2 操作系统、Windows Vista 操作系统和 Microsoft Lync Phone Edition 的客户端的连接，Lync Server 2013 支持 (，但不需要使用 SHA-256 加密哈希函数签署) 证书。</span><span class="sxs-lookup"><span data-stu-id="ba71d-115">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="ba71d-116">要支持使用 SHA-256 进行外部访问，外部证书必须由公共 CA 使用 SHA-256 颁发。</span><span class="sxs-lookup"><span data-stu-id="ba71d-116">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="ba71d-p106">下表按服务器角色显示了前端池和 Standard Edition Server 的证书要求。所有这些证书都是标准的 Web 服务器证书，具有私钥且不可导出。</span><span class="sxs-lookup"><span data-stu-id="ba71d-p106">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers. All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="ba71d-119">请注意，使用证书向导请求证书时会自动配置服务器增强型密钥使用 (EKU)。</span><span class="sxs-lookup"><span data-stu-id="ba71d-119">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ba71d-120">每个证书友好名称在计算机存储中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ba71d-120">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ba71d-121">如果您已在 DNS 中配置 sipinternal.contoso.com 或 sipexternal.contoso.com，则需要将其添加到证书的使用者备用名称中。</span><span class="sxs-lookup"><span data-stu-id="ba71d-121">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="ba71d-122">Standard Edition Server 的证书</span><span class="sxs-lookup"><span data-stu-id="ba71d-122">Certificates for Standard Edition Server</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba71d-123">证书</span><span class="sxs-lookup"><span data-stu-id="ba71d-123">Certificate</span></span></th>
<th><span data-ttu-id="ba71d-124">使用者名称/常用名称</span><span class="sxs-lookup"><span data-stu-id="ba71d-124">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="ba71d-125">使用者替代名称</span><span class="sxs-lookup"><span data-stu-id="ba71d-125">Subject alternative name</span></span></th>
<th><span data-ttu-id="ba71d-126">示例</span><span class="sxs-lookup"><span data-stu-id="ba71d-126">Example</span></span></th>
<th><span data-ttu-id="ba71d-127">Comments</span><span class="sxs-lookup"><span data-stu-id="ba71d-127">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba71d-128">默认值</span><span class="sxs-lookup"><span data-stu-id="ba71d-128">Default</span></span></p></td>
<td><p><span data-ttu-id="ba71d-129">池的完全限定的域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="ba71d-129">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="ba71d-130">池的 FQDN 和服务器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-130">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="ba71d-131">如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ba71d-131">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="ba71d-132">如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。</span><span class="sxs-lookup"><span data-stu-id="ba71d-132">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="ba71d-133">SN = se01;SAN = se01</span><span class="sxs-lookup"><span data-stu-id="ba71d-133">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="ba71d-134">如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="ba71d-134">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="ba71d-135">对于 Standard Edition Server，服务器 FQDN 与池 FQDN 相同。</span><span class="sxs-lookup"><span data-stu-id="ba71d-135">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="ba71d-136">证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者替代名称中。</span><span class="sxs-lookup"><span data-stu-id="ba71d-136">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="ba71d-137">您还可以使用此证书进行服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="ba71d-137">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba71d-138">Web 内部</span><span class="sxs-lookup"><span data-stu-id="ba71d-138">Web internal</span></span></p></td>
<td><p><span data-ttu-id="ba71d-139">服务器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-139">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="ba71d-140">以下各项：</span><span class="sxs-lookup"><span data-stu-id="ba71d-140">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ba71d-141">内部 Web FQDN（与服务器的 FQDN 相同）</span><span class="sxs-lookup"><span data-stu-id="ba71d-141">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="ba71d-142">会议简单 URL</span><span class="sxs-lookup"><span data-stu-id="ba71d-142">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="ba71d-143">拨入简单 URL</span><span class="sxs-lookup"><span data-stu-id="ba71d-143">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="ba71d-144">管理简单 URL</span><span class="sxs-lookup"><span data-stu-id="ba71d-144">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="ba71d-145">或者，简单 URL 的通配符条目</span><span class="sxs-lookup"><span data-stu-id="ba71d-145">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ba71d-146">SN = se01;SAN = se01;SAN = "contoso .com";SAN = 符合 fabrikam .com;SAN = contoso .com;SAN = .com</span><span class="sxs-lookup"><span data-stu-id="ba71d-146">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="ba71d-147">使用通配符证书：</span><span class="sxs-lookup"><span data-stu-id="ba71d-147">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="ba71d-148">SN = se01;SAN = se01;SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="ba71d-148">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ba71d-149">您不能在拓扑生成器中覆盖内部 web FQDN。</span><span class="sxs-lookup"><span data-stu-id="ba71d-149">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="ba71d-150">如果您具有多个会议简单 URL，则必须将它们作为使用者替代名称全部添加。</span><span class="sxs-lookup"><span data-stu-id="ba71d-150">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="ba71d-151">简单 URL 条目支持通配符条目。</span><span class="sxs-lookup"><span data-stu-id="ba71d-151">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba71d-152">Web 外部</span><span class="sxs-lookup"><span data-stu-id="ba71d-152">Web external</span></span></p></td>
<td><p><span data-ttu-id="ba71d-153">服务器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-153">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="ba71d-154">以下各项：</span><span class="sxs-lookup"><span data-stu-id="ba71d-154">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ba71d-155">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-155">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="ba71d-156">拨入简单 URL</span><span class="sxs-lookup"><span data-stu-id="ba71d-156">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="ba71d-157">满足每个 SIP 域的简单 Url</span><span class="sxs-lookup"><span data-stu-id="ba71d-157">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="ba71d-158">或者，简单 URL 的通配符条目</span><span class="sxs-lookup"><span data-stu-id="ba71d-158">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ba71d-159">SN = se01;SAN = webcon01;SAN = "contoso .com";SAN = 符合 fabrikam .com;SAN = "contoso .com"</span><span class="sxs-lookup"><span data-stu-id="ba71d-159">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="ba71d-160">使用通配符证书：</span><span class="sxs-lookup"><span data-stu-id="ba71d-160">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="ba71d-161">SN = se01;SAN = webcon01;SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="ba71d-161">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ba71d-162">如果您具有多个会议简单 URL，则必须将它们作为使用者替代名称全部添加。</span><span class="sxs-lookup"><span data-stu-id="ba71d-162">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="ba71d-163">简单 URL 条目支持通配符条目。</span><span class="sxs-lookup"><span data-stu-id="ba71d-163">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="ba71d-164">前端池中前端服务器的证书</span><span class="sxs-lookup"><span data-stu-id="ba71d-164">Certificates for Front End Server in a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba71d-165">证书</span><span class="sxs-lookup"><span data-stu-id="ba71d-165">Certificate</span></span></th>
<th><span data-ttu-id="ba71d-166">使用者名称/常用名称</span><span class="sxs-lookup"><span data-stu-id="ba71d-166">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="ba71d-167">使用者替代名称</span><span class="sxs-lookup"><span data-stu-id="ba71d-167">Subject alternative name</span></span></th>
<th><span data-ttu-id="ba71d-168">示例</span><span class="sxs-lookup"><span data-stu-id="ba71d-168">Example</span></span></th>
<th><span data-ttu-id="ba71d-169">Comments</span><span class="sxs-lookup"><span data-stu-id="ba71d-169">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba71d-170">默认值</span><span class="sxs-lookup"><span data-stu-id="ba71d-170">Default</span></span></p></td>
<td><p><span data-ttu-id="ba71d-171">池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-171">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="ba71d-172">池的 FQDN 和服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ba71d-172">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="ba71d-173">如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ba71d-173">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="ba71d-174">如果此池是客户端的自动登录服务器，且组策略要求执行严格的 DNS 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。</span><span class="sxs-lookup"><span data-stu-id="ba71d-174">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="ba71d-175">SN = eepool;SAN = eepool;SAN = ee01</span><span class="sxs-lookup"><span data-stu-id="ba71d-175">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="ba71d-176">如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="ba71d-176">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="ba71d-177">证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者替代名称中。</span><span class="sxs-lookup"><span data-stu-id="ba71d-177">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="ba71d-178">您还可以使用此证书进行服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="ba71d-178">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba71d-179">Web 内部</span><span class="sxs-lookup"><span data-stu-id="ba71d-179">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="ba71d-180">池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-180">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="ba71d-181">以下各项：</span><span class="sxs-lookup"><span data-stu-id="ba71d-181">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ba71d-182">内部 web FQDN (与服务器的 FQDN 不同) </span><span class="sxs-lookup"><span data-stu-id="ba71d-182">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="ba71d-183">服务器 FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-183">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="ba71d-184">Lync 池 FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-184">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="ba71d-185">会议简单 URL</span><span class="sxs-lookup"><span data-stu-id="ba71d-185">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="ba71d-186">拨入简单 URL</span><span class="sxs-lookup"><span data-stu-id="ba71d-186">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="ba71d-187">管理简单 URL</span><span class="sxs-lookup"><span data-stu-id="ba71d-187">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="ba71d-188">或者，简单 URL 的通配符条目</span><span class="sxs-lookup"><span data-stu-id="ba71d-188">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ba71d-189">SN = ee01;SAN = ee01;SAN = "contoso .com";SAN = 符合 fabrikam .com;SAN = contoso .com;SAN = .com</span><span class="sxs-lookup"><span data-stu-id="ba71d-189">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="ba71d-190">使用通配符证书：</span><span class="sxs-lookup"><span data-stu-id="ba71d-190">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="ba71d-191">SN = ee01;SAN = ee01;SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="ba71d-191">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ba71d-192">如果您具有多个会议简单 URL，则必须将它们作为使用者替代名称全部添加。</span><span class="sxs-lookup"><span data-stu-id="ba71d-192">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="ba71d-193">简单 URL 条目支持通配符条目。</span><span class="sxs-lookup"><span data-stu-id="ba71d-193">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba71d-194">Web 外部</span><span class="sxs-lookup"><span data-stu-id="ba71d-194">Web external</span></span></p></td>
<td><p><span data-ttu-id="ba71d-195">池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-195">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="ba71d-196">以下各项：</span><span class="sxs-lookup"><span data-stu-id="ba71d-196">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ba71d-197">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-197">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="ba71d-198">拨入简单 URL</span><span class="sxs-lookup"><span data-stu-id="ba71d-198">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="ba71d-199">管理简单 URL</span><span class="sxs-lookup"><span data-stu-id="ba71d-199">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="ba71d-200">或者，简单 URL 的通配符条目</span><span class="sxs-lookup"><span data-stu-id="ba71d-200">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ba71d-201">SN = ee01;SAN = webcon01;SAN = "contoso .com";SAN = 符合 fabrikam .com;SAN = "contoso .com"</span><span class="sxs-lookup"><span data-stu-id="ba71d-201">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="ba71d-202">使用通配符证书：</span><span class="sxs-lookup"><span data-stu-id="ba71d-202">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="ba71d-203">SN = ee01;SAN = webcon01;SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="ba71d-203">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ba71d-204">如果您具有多个会议简单 URL，则必须将它们作为使用者替代名称全部添加。</span><span class="sxs-lookup"><span data-stu-id="ba71d-204">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="ba71d-205">简单 URL 条目支持通配符条目。</span><span class="sxs-lookup"><span data-stu-id="ba71d-205">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="ba71d-206">控制器的证书</span><span class="sxs-lookup"><span data-stu-id="ba71d-206">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba71d-207">证书</span><span class="sxs-lookup"><span data-stu-id="ba71d-207">Certificate</span></span></th>
<th><span data-ttu-id="ba71d-208">使用者名称/常用名称</span><span class="sxs-lookup"><span data-stu-id="ba71d-208">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="ba71d-209">使用者替代名称</span><span class="sxs-lookup"><span data-stu-id="ba71d-209">Subject alternative name</span></span></th>
<th><span data-ttu-id="ba71d-210">示例</span><span class="sxs-lookup"><span data-stu-id="ba71d-210">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba71d-211">默认值</span><span class="sxs-lookup"><span data-stu-id="ba71d-211">Default</span></span></p></td>
<td><p><span data-ttu-id="ba71d-212">控制器池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-212">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="ba71d-213">控制器的 FQDN 和控制器池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-213">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="ba71d-214">如果此池是客户端的自动登录服务器，且组策略要求执行严格的 DNS 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。</span><span class="sxs-lookup"><span data-stu-id="ba71d-214">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="ba71d-215">SN = dir-pool.contoso.com;SAN = dir-pool.contoso.com;SAN = dir01</span><span class="sxs-lookup"><span data-stu-id="ba71d-215">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="ba71d-216">如果此控制器池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，那么您还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="ba71d-216">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba71d-217">Web 内部</span><span class="sxs-lookup"><span data-stu-id="ba71d-217">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="ba71d-218">服务器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-218">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="ba71d-219">以下各项：</span><span class="sxs-lookup"><span data-stu-id="ba71d-219">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ba71d-220">内部 Web FQDN（与服务器的 FQDN 相同）</span><span class="sxs-lookup"><span data-stu-id="ba71d-220">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="ba71d-221">服务器 FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-221">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="ba71d-222">Lync 池 FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-222">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="ba71d-223">会议简单 URL</span><span class="sxs-lookup"><span data-stu-id="ba71d-223">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="ba71d-224">拨入简单 URL</span><span class="sxs-lookup"><span data-stu-id="ba71d-224">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="ba71d-225">管理简单 URL</span><span class="sxs-lookup"><span data-stu-id="ba71d-225">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="ba71d-226">或者，简单 URL 的通配符条目</span><span class="sxs-lookup"><span data-stu-id="ba71d-226">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ba71d-227">SN = dir01;SAN = dir01;SAN = "contoso .com";SAN = 符合 fabrikam .com;SAN = contoso .com;SAN = .com</span><span class="sxs-lookup"><span data-stu-id="ba71d-227">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="ba71d-228">SN = dir01;SAN = dir01 SAN = （contoso .com）</span><span class="sxs-lookup"><span data-stu-id="ba71d-228">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba71d-229">Web 外部</span><span class="sxs-lookup"><span data-stu-id="ba71d-229">Web external</span></span></p></td>
<td><p><span data-ttu-id="ba71d-230">服务器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-230">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="ba71d-231">以下各项：</span><span class="sxs-lookup"><span data-stu-id="ba71d-231">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ba71d-232">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-232">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="ba71d-233">拨入简单 URL</span><span class="sxs-lookup"><span data-stu-id="ba71d-233">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="ba71d-234">管理简单 URL</span><span class="sxs-lookup"><span data-stu-id="ba71d-234">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="ba71d-235">或者，简单 URL 的通配符条目</span><span class="sxs-lookup"><span data-stu-id="ba71d-235">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ba71d-236">控制器外部 web FQDN 必须不同于前端池或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="ba71d-236">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="ba71d-237">SN = dir01;SAN = directorwebcon01 SAN = "contoso. .com";SAN = 符合 fabrikam .com;SAN = "contoso .com"</span><span class="sxs-lookup"><span data-stu-id="ba71d-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="ba71d-238">SN = dir01;SAN = directorwebcon01 SAN = （contoso .com）</span><span class="sxs-lookup"><span data-stu-id="ba71d-238">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ba71d-p107">如果具有独立中介服务器池，则其中的每个中介服务器需要使用下表中所列出的证书。如果将中介服务器与前端服务器并置，则使用本主题前面“前端池中前端服务器的证书”表所列的证书就足够了。</span><span class="sxs-lookup"><span data-stu-id="ba71d-p107">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table. If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="ba71d-241">独立中介服务器的证书</span><span class="sxs-lookup"><span data-stu-id="ba71d-241">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba71d-242">证书</span><span class="sxs-lookup"><span data-stu-id="ba71d-242">Certificate</span></span></th>
<th><span data-ttu-id="ba71d-243">使用者名称/常用名称</span><span class="sxs-lookup"><span data-stu-id="ba71d-243">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="ba71d-244">使用者替代名称</span><span class="sxs-lookup"><span data-stu-id="ba71d-244">Subject alternative name</span></span></th>
<th><span data-ttu-id="ba71d-245">示例</span><span class="sxs-lookup"><span data-stu-id="ba71d-245">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba71d-246">默认值</span><span class="sxs-lookup"><span data-stu-id="ba71d-246">Default</span></span></p></td>
<td><p><span data-ttu-id="ba71d-247">池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-247">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="ba71d-248">池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-248">FQDN of the pool</span></span></p>
<p><span data-ttu-id="ba71d-249">池成员服务器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-249">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="ba71d-250">SN = medsvr-pool.contoso.net;SAN = medsvr-pool.contoso.net;SAN = medsvr01</span><span class="sxs-lookup"><span data-stu-id="ba71d-250">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="ba71d-251">Survivable Branch Appliance 的证书</span><span class="sxs-lookup"><span data-stu-id="ba71d-251">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba71d-252">证书</span><span class="sxs-lookup"><span data-stu-id="ba71d-252">Certificate</span></span></th>
<th><span data-ttu-id="ba71d-253">使用者名称/常用名称</span><span class="sxs-lookup"><span data-stu-id="ba71d-253">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="ba71d-254">使用者替代名称</span><span class="sxs-lookup"><span data-stu-id="ba71d-254">Subject alternative name</span></span></th>
<th><span data-ttu-id="ba71d-255">示例</span><span class="sxs-lookup"><span data-stu-id="ba71d-255">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba71d-256">默认值</span><span class="sxs-lookup"><span data-stu-id="ba71d-256">Default</span></span></p></td>
<td><p><span data-ttu-id="ba71d-257">设备的 FQDN</span><span class="sxs-lookup"><span data-stu-id="ba71d-257">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="ba71d-258">SIP。 &lt;sipdomain &gt; (每个 SIP 域需要一个条目) </span><span class="sxs-lookup"><span data-stu-id="ba71d-258">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="ba71d-259">SN = sba01;SAN = "contoso .com";SAN = sip. .com</span><span class="sxs-lookup"><span data-stu-id="ba71d-259">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="ba71d-260">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba71d-260">See Also</span></span>


[<span data-ttu-id="ba71d-261">Lync Server 2013 中的通配符证书支持</span><span class="sxs-lookup"><span data-stu-id="ba71d-261">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

