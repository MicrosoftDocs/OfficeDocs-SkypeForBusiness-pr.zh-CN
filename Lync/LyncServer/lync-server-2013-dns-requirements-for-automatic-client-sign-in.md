---
title: Lync Server 2013：自动客户端登录的 DNS 要求
description: Lync Server 2013：自动客户端登录的 DNS 要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2247c955e0a563a22fb5d0ec20735291a836cdfc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574368"
---
# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a><span data-ttu-id="80b0d-103">Lync Server 2013 中自动客户端登录的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="80b0d-103">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80b0d-104">_**上次修改的主题：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="80b0d-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="80b0d-105">本节介绍客户端自动登录所需的域名系统 (DNS) 记录。</span><span class="sxs-lookup"><span data-stu-id="80b0d-105">This section explains the Domain Name System (DNS) records that are required for automatic client sign-in.</span></span> <span data-ttu-id="80b0d-106">部署 Standard Edition Server 或前端池时，可以将客户端配置为使用自动发现登录相应的 Standard Edition Server 或前端池。</span><span class="sxs-lookup"><span data-stu-id="80b0d-106">When you deploy your Standard Edition servers or Front End pools, you can configure your clients to use automatic discovery to sign in to the appropriate Standard Edition server or Front End pool.</span></span> <span data-ttu-id="80b0d-107">如果计划要求客户端手动连接到 Lync Server 2013，则可以跳过此主题。</span><span class="sxs-lookup"><span data-stu-id="80b0d-107">If you plan to require your clients to connect manually to Lync Server 2013, you can skip this topic.</span></span>

<span data-ttu-id="80b0d-108">要支持自动客户端登录，必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="80b0d-108">To support automatic client sign-in, you must:</span></span>

  - <span data-ttu-id="80b0d-p102">指定单个服务器或池，以分发客户端登录请求并进行身份验证。它可以是组织中承载用户的现有服务器或池，您也可以指定一个未承载任何用户的专用服务器或池。为了获得高可用性，建议您为此功能指定前端池。</span><span class="sxs-lookup"><span data-stu-id="80b0d-p102">Designate a single server or pool to distribute and authenticate client sign-in requests. This can be an existing server or pool in your organization that hosts users, or you can designate a dedicated server or pool for this purpose that hosts no users. For high availability, we recommend that you designate a Front End pool for this function.</span></span>

  - <span data-ttu-id="80b0d-112">创建内部 DNS SRV 记录以支持此服务器或池的自动客户端登录。</span><span class="sxs-lookup"><span data-stu-id="80b0d-112">Create an internal DNS SRV record to support automatic client sign-in for this server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="80b0d-p103">在下列记录要求中，SIP 域是指分配给用户的 SIP URI 的主机部分。例如，如果 SIP URI 的形式为 \*@contoso.com，则 contoso.com 即为 SIP 域。SIP 域通常不同于内部 Active Directory 域。一个组织也可以支持多个 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="80b0d-p103">In the following record requirements, SIP domain refers to the host portion of the SIP URIs assigned to users. For example, if SIP URIs are of the form \*@contoso.com, contoso.com is the SIP domain. The SIP domain is often different from the internal Active Directory domain. An organization can also support multiple SIP domains.</span></span>

    
    </div>

<span data-ttu-id="80b0d-117">若要为你的客户端启用自动配置，必须创建内部 DNS SRV 记录，将以下记录之一映射到前端池或 Standard Edition 服务器的完全限定的域名 (FQDN) ，以便从 Lync 客户端分发登录请求：</span><span class="sxs-lookup"><span data-stu-id="80b0d-117">To enable automatic configuration for your clients, you must create an internal DNS SRV record that maps one of the following records to the fully qualified domain name (FQDN) of the Front End pool or Standard Edition server that distributes sign-in requests from Lync clients:</span></span>

  - <span data-ttu-id="80b0d-118">\_sipinternaltls。 \_rdp-tcp.\<domain\></span><span class="sxs-lookup"><span data-stu-id="80b0d-118">\_sipinternaltls.\_tcp.\<domain\></span></span> <span data-ttu-id="80b0d-119">-用于内部 TLS 连接</span><span class="sxs-lookup"><span data-stu-id="80b0d-119">- for internal TLS connections</span></span>

<span data-ttu-id="80b0d-120">您只需要为将分发登录请求的前端池或 Standard Edition Server 创建单个 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="80b0d-120">You only need to create a single SRV record for the Front End pool or Standard Edition server or that will distribute sign-in requests.</span></span>

<span data-ttu-id="80b0d-121">下表显示虚构的公司 Contoso 所需的某些记录示例，该公司支持 contoso.com 和 retail.contoso.com 这两个 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="80b0d-121">The following table shows some example records required for the fictitious company Contoso, which supports SIP domains of contoso.com and retail.contoso.com.</span></span>

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a><span data-ttu-id="80b0d-122">多 SIP 域客户端自动登录所需的 DNS 记录的示例</span><span class="sxs-lookup"><span data-stu-id="80b0d-122">Example of DNS Records Required for Automatic Client Sign-in with Multiple SIP Domains</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80b0d-123">用于分发登录请求的前端池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="80b0d-123">FQDN of Front End pool used to distribute sign-in requests</span></span></th>
<th><span data-ttu-id="80b0d-124">SIP 域</span><span class="sxs-lookup"><span data-stu-id="80b0d-124">SIP domain</span></span></th>
<th><span data-ttu-id="80b0d-125">DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="80b0d-125">DNS SRV record</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80b0d-126">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80b0d-126">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="80b0d-127">contoso.com</span><span class="sxs-lookup"><span data-stu-id="80b0d-127">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="80b0d-128">_sipinternaltls._tcp.contoso.com 域的 SRV 记录，通过端口 5061 映射到 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80b0d-128">An SRV record for _sipinternaltls._tcp.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80b0d-129">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80b0d-129">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="80b0d-130">retail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80b0d-130">retail.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="80b0d-131">_sipinternaltls._tcp.retail.contoso.com 域的 SRV 记录，通过端口 5061 映射到 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80b0d-131">An SRV record for _sipinternaltls._tcp.retail.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="80b0d-132">默认情况下，DNS 记录的查询遵守用户名与 SRV 记录中的域之间的严格域名匹配。</span><span class="sxs-lookup"><span data-stu-id="80b0d-132">By default, queries for DNS records adhere to strict domain name matching between the domain in the user name and the SRV record.</span></span> <span data-ttu-id="80b0d-133">如果更希望客户端 DNS 查询改用后缀匹配，可以配置 DisableStrictDNSNaming 组策略。</span><span class="sxs-lookup"><span data-stu-id="80b0d-133">If you prefer that client DNS queries use suffix matching instead, you can configure the DisableStrictDNSNaming Group Policy.</span></span> <span data-ttu-id="80b0d-134">有关详细信息，请参阅规划文档中的在 <A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013 中规划客户端和设备</A> 。</span><span class="sxs-lookup"><span data-stu-id="80b0d-134">For details, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a><span data-ttu-id="80b0d-135">客户端自动登录所需证书和 DNS 记录的示例</span><span class="sxs-lookup"><span data-stu-id="80b0d-135">Example of the Certificates and DNS Records Required for Automatic Client Sign-In</span></span>

<span data-ttu-id="80b0d-p106">本示例使用上表中相同的示例名称。Contoso 组织支持 contoso.com 和 retail.contoso.com 这两个 SIP 域，该组织的所有用户都具有下列某种形式的 SIP URI：</span><span class="sxs-lookup"><span data-stu-id="80b0d-p106">This example uses the same example names in the preceding table. The Contoso organization supports the SIP domains of contoso.com and retail.contoso.com, and all of its users have a SIP URI in one of the following forms:</span></span>

  - <span data-ttu-id="80b0d-138">\<user\>@retail contoso.com</span><span class="sxs-lookup"><span data-stu-id="80b0d-138">\<user\>@retail.contoso.com</span></span>

  - <span data-ttu-id="80b0d-139">\<user\>@contoso .com</span><span class="sxs-lookup"><span data-stu-id="80b0d-139">\<user\>@contoso.com</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

