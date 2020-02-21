---
title: Lync Server 2013：内部服务器的证书要求
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
ms.openlocfilehash: 38bd350a4b552d63b635f8ec5a25ed7803de4b55
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="fa1b6-102">Lync Server 2013 中的内部服务器的证书要求</span><span class="sxs-lookup"><span data-stu-id="fa1b6-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa1b6-103">_**上次修改的主题：** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="fa1b6-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="fa1b6-104">运行 Lync Server 且要求证书的内部服务器包括 Standard Edition server、Enterprise Edition 前端服务器、中介服务器和控制器。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="fa1b6-105">下表显示了这些服务器的证书要求。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="fa1b6-106">您可以使用 Lync Server 证书向导来请求这些证书。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="fa1b6-107">对于与前端池、前端服务器或控制器上的简单 Url 相关联的使用者替代名称，支持通配符证书。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="fa1b6-108">有关通配符证书支持的详细信息，请参阅<A href="lync-server-2013-wildcard-certificate-support.md">Lync Server 2013 中的通配符证书支持</A>。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="fa1b6-109">虽然建议对内部服务器使用内部企业证书颁发机构 (CA)，但您也可以使用公共 CA。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="fa1b6-110">有关公用 Ca 的列表，这些 Ca 提供符合统一通信（UC）证书的特定要求的证书，并已与 Microsoft 合作以确保它们使用 Lync Server 证书向导，请参阅文章 Microsoft 知识库 929395 "Exchange Server 的统一通信证书合作伙伴和通信服务器"，网址为 at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="fa1b6-111">与其他应用程序和服务器（如 Exchange 2013）的通信需要其他应用程序和产品支持的证书。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="fa1b6-112">对于2013版本，Lync Server 2013 和其他 Microsoft Server 产品（包括 Exchange 2013 和 SharePoint Server）支持用于服务器到服务器身份验证和授权的开放授权（OAuth）协议。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="fa1b6-113">有关详细信息，请参阅部署文档或操作文档中的[管理 Lync server 2013 中的服务器到服务器身份验证（OAuth）和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="fa1b6-114">对于运行 Windows 7 操作系统的客户端的连接、Windows Server 2008 操作系统、Windows Server 2008 R2 操作系统、Windows Vista 操作系统和 Microsoft Lync Phone Edition，Lync Server 2013 支持（但不要求）使用 SHA-256 加密哈希函数对证书进行签名。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="fa1b6-115">要支持使用 SHA-256 进行外部访问，外部证书必须由公共 CA 使用 SHA-256 颁发。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="fa1b6-p106">下表按服务器角色显示了前端池和 Standard Edition Server 的证书要求。所有这些证书都是标准的 Web 服务器证书，具有私钥且不可导出。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-p106">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers. All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="fa1b6-118">请注意，使用证书向导请求证书时会自动配置服务器增强型密钥使用 (EKU)。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fa1b6-119">每个证书友好名称在计算机存储中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="fa1b6-120">如果您已在 DNS 中配置 sipinternal.contoso.com 或 sipexternal.contoso.com，则需要将其添加到证书的使用者备用名称中。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="fa1b6-121">Standard Edition Server 的证书</span><span class="sxs-lookup"><span data-stu-id="fa1b6-121">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="fa1b6-122">证书</span><span class="sxs-lookup"><span data-stu-id="fa1b6-122">Certificate</span></span></th>
<th><span data-ttu-id="fa1b6-123">使用者名称/常用名称</span><span class="sxs-lookup"><span data-stu-id="fa1b6-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="fa1b6-124">使用者替代名称</span><span class="sxs-lookup"><span data-stu-id="fa1b6-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="fa1b6-125">示例</span><span class="sxs-lookup"><span data-stu-id="fa1b6-125">Example</span></span></th>
<th><span data-ttu-id="fa1b6-126">注释</span><span class="sxs-lookup"><span data-stu-id="fa1b6-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa1b6-127">默认值</span><span class="sxs-lookup"><span data-stu-id="fa1b6-127">Default</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-128">池的完全限定的域名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="fa1b6-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-129">池的 FQDN 和服务器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="fa1b6-130">如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="fa1b6-131">如果此池是客户端的自动登录服务器，而且组策略要求执行严格的域名系统 (DNS) 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-132">SN = se01;SAN = se01</span><span class="sxs-lookup"><span data-stu-id="fa1b6-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="fa1b6-133">如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-134">对于 Standard Edition Server，服务器 FQDN 与池 FQDN 相同。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="fa1b6-135">证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者替代名称中。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="fa1b6-136">您还可以使用此证书进行服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa1b6-137">Web 内部</span><span class="sxs-lookup"><span data-stu-id="fa1b6-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-138">服务器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-139">以下各项：</span><span class="sxs-lookup"><span data-stu-id="fa1b6-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fa1b6-140">内部 Web FQDN（与服务器的 FQDN 相同）</span><span class="sxs-lookup"><span data-stu-id="fa1b6-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-141">会议简单 URL</span><span class="sxs-lookup"><span data-stu-id="fa1b6-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-142">拨入简单 URL</span><span class="sxs-lookup"><span data-stu-id="fa1b6-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-143">管理简单 URL</span><span class="sxs-lookup"><span data-stu-id="fa1b6-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-144">或者，简单 URL 的通配符条目</span><span class="sxs-lookup"><span data-stu-id="fa1b6-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="fa1b6-145">SN = se01;SAN = se01;SAN = "contoso .com";SAN = 符合 fabrikam .com;SAN = contoso .com;SAN = .com</span><span class="sxs-lookup"><span data-stu-id="fa1b6-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="fa1b6-146">使用通配符证书：</span><span class="sxs-lookup"><span data-stu-id="fa1b6-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="fa1b6-147">SN = se01;SAN = se01;SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="fa1b6-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-148">您不能在拓扑生成器中覆盖内部 web FQDN。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="fa1b6-149">如果您具有多个会议简单 URL，则必须将它们作为使用者替代名称全部添加。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="fa1b6-150">简单 URL 条目支持通配符条目。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa1b6-151">Web 外部</span><span class="sxs-lookup"><span data-stu-id="fa1b6-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-152">服务器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-153">以下各项：</span><span class="sxs-lookup"><span data-stu-id="fa1b6-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fa1b6-154">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-155">拨入简单 URL</span><span class="sxs-lookup"><span data-stu-id="fa1b6-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-156">满足每个 SIP 域的简单 Url</span><span class="sxs-lookup"><span data-stu-id="fa1b6-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-157">或者，简单 URL 的通配符条目</span><span class="sxs-lookup"><span data-stu-id="fa1b6-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="fa1b6-158">SN = se01;SAN = webcon01;SAN = "contoso .com";SAN = 符合 fabrikam .com;SAN = "contoso .com"</span><span class="sxs-lookup"><span data-stu-id="fa1b6-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="fa1b6-159">使用通配符证书：</span><span class="sxs-lookup"><span data-stu-id="fa1b6-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="fa1b6-160">SN = se01;SAN = webcon01;SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="fa1b6-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-161">如果您具有多个会议简单 URL，则必须将它们作为使用者替代名称全部添加。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="fa1b6-162">简单 URL 条目支持通配符条目。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="fa1b6-163">前端池中前端服务器的证书</span><span class="sxs-lookup"><span data-stu-id="fa1b6-163">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="fa1b6-164">证书</span><span class="sxs-lookup"><span data-stu-id="fa1b6-164">Certificate</span></span></th>
<th><span data-ttu-id="fa1b6-165">使用者名称/常用名称</span><span class="sxs-lookup"><span data-stu-id="fa1b6-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="fa1b6-166">使用者替代名称</span><span class="sxs-lookup"><span data-stu-id="fa1b6-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="fa1b6-167">示例</span><span class="sxs-lookup"><span data-stu-id="fa1b6-167">Example</span></span></th>
<th><span data-ttu-id="fa1b6-168">注释</span><span class="sxs-lookup"><span data-stu-id="fa1b6-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa1b6-169">默认值</span><span class="sxs-lookup"><span data-stu-id="fa1b6-169">Default</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-170">池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-171">池的 FQDN 和服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="fa1b6-172">如果具有多个 SIP 域并已启用自动客户端配置，则证书向导会检测并添加所有受支持的 SIP 域 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="fa1b6-173">如果此池是客户端的自动登录服务器，且组策略要求执行严格的 DNS 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-174">SN = eepool;SAN = eepool;SAN = ee01</span><span class="sxs-lookup"><span data-stu-id="fa1b6-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="fa1b6-175">如果此池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，则还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-176">证书向导会检测您在安装过程中所指定的任何 SIP 域，然后自动将它们添加到使用者替代名称中。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="fa1b6-177">您还可以使用此证书进行服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa1b6-178">Web 内部</span><span class="sxs-lookup"><span data-stu-id="fa1b6-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-179">池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-180">以下各项：</span><span class="sxs-lookup"><span data-stu-id="fa1b6-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fa1b6-181">内部 web FQDN （与服务器的 FQDN 不同）</span><span class="sxs-lookup"><span data-stu-id="fa1b6-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-182">服务器 FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-183">Lync 池 FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-184">会议简单 URL</span><span class="sxs-lookup"><span data-stu-id="fa1b6-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-185">拨入简单 URL</span><span class="sxs-lookup"><span data-stu-id="fa1b6-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-186">管理简单 URL</span><span class="sxs-lookup"><span data-stu-id="fa1b6-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-187">或者，简单 URL 的通配符条目</span><span class="sxs-lookup"><span data-stu-id="fa1b6-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="fa1b6-188">SN = ee01;SAN = ee01;SAN = "contoso .com";SAN = 符合 fabrikam .com;SAN = contoso .com;SAN = .com</span><span class="sxs-lookup"><span data-stu-id="fa1b6-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="fa1b6-189">使用通配符证书：</span><span class="sxs-lookup"><span data-stu-id="fa1b6-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="fa1b6-190">SN = ee01;SAN = ee01;SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="fa1b6-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-191">如果您具有多个会议简单 URL，则必须将它们作为使用者替代名称全部添加。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="fa1b6-192">简单 URL 条目支持通配符条目。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa1b6-193">Web 外部</span><span class="sxs-lookup"><span data-stu-id="fa1b6-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-194">池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-195">以下各项：</span><span class="sxs-lookup"><span data-stu-id="fa1b6-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fa1b6-196">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-197">拨入简单 URL</span><span class="sxs-lookup"><span data-stu-id="fa1b6-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-198">管理简单 URL</span><span class="sxs-lookup"><span data-stu-id="fa1b6-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-199">或者，简单 URL 的通配符条目</span><span class="sxs-lookup"><span data-stu-id="fa1b6-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="fa1b6-200">SN = ee01;SAN = webcon01;SAN = "contoso .com";SAN = 符合 fabrikam .com;SAN = "contoso .com"</span><span class="sxs-lookup"><span data-stu-id="fa1b6-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="fa1b6-201">使用通配符证书：</span><span class="sxs-lookup"><span data-stu-id="fa1b6-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="fa1b6-202">SN = ee01;SAN = webcon01;SAN = \* .com</span><span class="sxs-lookup"><span data-stu-id="fa1b6-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-203">如果您具有多个会议简单 URL，则必须将它们作为使用者替代名称全部添加。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="fa1b6-204">简单 URL 条目支持通配符条目。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="fa1b6-205">控制器的证书</span><span class="sxs-lookup"><span data-stu-id="fa1b6-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa1b6-206">证书</span><span class="sxs-lookup"><span data-stu-id="fa1b6-206">Certificate</span></span></th>
<th><span data-ttu-id="fa1b6-207">使用者名称/常用名称</span><span class="sxs-lookup"><span data-stu-id="fa1b6-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="fa1b6-208">使用者替代名称</span><span class="sxs-lookup"><span data-stu-id="fa1b6-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="fa1b6-209">示例</span><span class="sxs-lookup"><span data-stu-id="fa1b6-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa1b6-210">默认值</span><span class="sxs-lookup"><span data-stu-id="fa1b6-210">Default</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-211">控制器池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-212">控制器的 FQDN 和控制器池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="fa1b6-213">如果此池是客户端的自动登录服务器，且组策略要求执行严格的 DNS 匹配，那么还需要 sip.sipdomain 条目（对应于您拥有的每个 SIP 域）。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-214">SN = dir-pool.contoso.com;SAN = dir-pool.contoso.com;SAN = dir01</span><span class="sxs-lookup"><span data-stu-id="fa1b6-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="fa1b6-215">如果此控制器池是客户端的自动登录服务器，而且组策略要求执行严格的 DNS 匹配，那么您还需要 SAN=sip.contoso.com; SAN=sip.fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa1b6-216">Web 内部</span><span class="sxs-lookup"><span data-stu-id="fa1b6-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-217">服务器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-218">以下各项：</span><span class="sxs-lookup"><span data-stu-id="fa1b6-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fa1b6-219">内部 Web FQDN（与服务器的 FQDN 相同）</span><span class="sxs-lookup"><span data-stu-id="fa1b6-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-220">服务器 FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-221">Lync 池 FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-222">会议简单 URL</span><span class="sxs-lookup"><span data-stu-id="fa1b6-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-223">拨入简单 URL</span><span class="sxs-lookup"><span data-stu-id="fa1b6-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-224">管理简单 URL</span><span class="sxs-lookup"><span data-stu-id="fa1b6-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-225">或者，简单 URL 的通配符条目</span><span class="sxs-lookup"><span data-stu-id="fa1b6-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="fa1b6-226">SN = dir01;SAN = dir01;SAN = "contoso .com";SAN = 符合 fabrikam .com;SAN = contoso .com;SAN = .com</span><span class="sxs-lookup"><span data-stu-id="fa1b6-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="fa1b6-227">SN = dir01;SAN = dir01 SAN = （contoso .com）</span><span class="sxs-lookup"><span data-stu-id="fa1b6-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa1b6-228">Web 外部</span><span class="sxs-lookup"><span data-stu-id="fa1b6-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-229">服务器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-230">以下各项：</span><span class="sxs-lookup"><span data-stu-id="fa1b6-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fa1b6-231">外部 Web FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-232">拨入简单 URL</span><span class="sxs-lookup"><span data-stu-id="fa1b6-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-233">管理简单 URL</span><span class="sxs-lookup"><span data-stu-id="fa1b6-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="fa1b6-234">或者，简单 URL 的通配符条目</span><span class="sxs-lookup"><span data-stu-id="fa1b6-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="fa1b6-235">控制器外部 web FQDN 必须不同于前端池或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="fa1b6-236">SN = dir01;SAN = directorwebcon01 SAN = "contoso. .com";SAN = 符合 fabrikam .com;SAN = "contoso .com"</span><span class="sxs-lookup"><span data-stu-id="fa1b6-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="fa1b6-237">SN = dir01;SAN = directorwebcon01 SAN = （contoso .com）</span><span class="sxs-lookup"><span data-stu-id="fa1b6-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fa1b6-p107">如果具有独立中介服务器池，则其中的每个中介服务器需要使用下表中所列出的证书。如果将中介服务器与前端服务器并置，则使用本主题前面“前端池中前端服务器的证书”表所列的证书就足够了。</span><span class="sxs-lookup"><span data-stu-id="fa1b6-p107">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table. If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="fa1b6-240">独立中介服务器的证书</span><span class="sxs-lookup"><span data-stu-id="fa1b6-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa1b6-241">证书</span><span class="sxs-lookup"><span data-stu-id="fa1b6-241">Certificate</span></span></th>
<th><span data-ttu-id="fa1b6-242">使用者名称/常用名称</span><span class="sxs-lookup"><span data-stu-id="fa1b6-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="fa1b6-243">使用者替代名称</span><span class="sxs-lookup"><span data-stu-id="fa1b6-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="fa1b6-244">示例</span><span class="sxs-lookup"><span data-stu-id="fa1b6-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa1b6-245">默认值</span><span class="sxs-lookup"><span data-stu-id="fa1b6-245">Default</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-246">池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-247">池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="fa1b6-248">池成员服务器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-249">SN = medsvr-pool.contoso.net;SAN = medsvr-pool.contoso.net;SAN = medsvr01</span><span class="sxs-lookup"><span data-stu-id="fa1b6-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="fa1b6-250">Survivable Branch Appliance 的证书</span><span class="sxs-lookup"><span data-stu-id="fa1b6-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa1b6-251">证书</span><span class="sxs-lookup"><span data-stu-id="fa1b6-251">Certificate</span></span></th>
<th><span data-ttu-id="fa1b6-252">使用者名称/常用名称</span><span class="sxs-lookup"><span data-stu-id="fa1b6-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="fa1b6-253">使用者替代名称</span><span class="sxs-lookup"><span data-stu-id="fa1b6-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="fa1b6-254">示例</span><span class="sxs-lookup"><span data-stu-id="fa1b6-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa1b6-255">默认值</span><span class="sxs-lookup"><span data-stu-id="fa1b6-255">Default</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-256">设备的 FQDN</span><span class="sxs-lookup"><span data-stu-id="fa1b6-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-257">SIP.&lt;sipdomain&gt; （每个 SIP 域需要一个条目）</span><span class="sxs-lookup"><span data-stu-id="fa1b6-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="fa1b6-258">SN = sba01;SAN = "contoso .com";SAN = sip. .com</span><span class="sxs-lookup"><span data-stu-id="fa1b6-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="fa1b6-259">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa1b6-259">See Also</span></span>


[<span data-ttu-id="fa1b6-260">Lync Server 2013 中的通配符证书支持</span><span class="sxs-lookup"><span data-stu-id="fa1b6-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

