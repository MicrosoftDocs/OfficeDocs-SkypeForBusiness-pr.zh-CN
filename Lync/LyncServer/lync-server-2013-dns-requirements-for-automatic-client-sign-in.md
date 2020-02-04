---
title: Lync Server 2013：自动客户端登录的 DNS 要求
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
ms.openlocfilehash: 6d033621382587367630d9119c2176e976cb2c2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a><span data-ttu-id="b23e8-102">Lync Server 2013 中自动客户端登录的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="b23e8-102">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b23e8-103">_**主题上次修改时间：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="b23e8-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="b23e8-104">本部分介绍自动客户端登录所需的域名系统（DNS）记录。</span><span class="sxs-lookup"><span data-stu-id="b23e8-104">This section explains the Domain Name System (DNS) records that are required for automatic client sign-in.</span></span> <span data-ttu-id="b23e8-105">部署标准版服务器或前端池时，可以将客户端配置为使用自动发现登录到相应的标准版服务器或前端池。</span><span class="sxs-lookup"><span data-stu-id="b23e8-105">When you deploy your Standard Edition servers or Front End pools, you can configure your clients to use automatic discovery to sign in to the appropriate Standard Edition server or Front End pool.</span></span> <span data-ttu-id="b23e8-106">如果您计划要求客户手动连接到 Lync Server 2013，则可以跳过本主题。</span><span class="sxs-lookup"><span data-stu-id="b23e8-106">If you plan to require your clients to connect manually to Lync Server 2013, you can skip this topic.</span></span>

<span data-ttu-id="b23e8-107">若要支持自动客户端登录，必须：</span><span class="sxs-lookup"><span data-stu-id="b23e8-107">To support automatic client sign-in, you must:</span></span>

  - <span data-ttu-id="b23e8-108">指定单个服务器或池以分发和验证客户端登录请求。</span><span class="sxs-lookup"><span data-stu-id="b23e8-108">Designate a single server or pool to distribute and authenticate client sign-in requests.</span></span> <span data-ttu-id="b23e8-109">这可以是组织中托管用户的现有服务器或池，也可以指定专用服务器或池用于托管无用户的此用途。</span><span class="sxs-lookup"><span data-stu-id="b23e8-109">This can be an existing server or pool in your organization that hosts users, or you can designate a dedicated server or pool for this purpose that hosts no users.</span></span> <span data-ttu-id="b23e8-110">为了获得高可用性，建议你为此函数指定一个前端池。</span><span class="sxs-lookup"><span data-stu-id="b23e8-110">For high availability, we recommend that you designate a Front End pool for this function.</span></span>

  - <span data-ttu-id="b23e8-111">创建内部 DNS SRV 记录以支持此服务器或池的自动客户端登录。</span><span class="sxs-lookup"><span data-stu-id="b23e8-111">Create an internal DNS SRV record to support automatic client sign-in for this server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b23e8-112">在以下记录要求中，SIP 域指的是分配给用户的 SIP Uri 的主机部分。</span><span class="sxs-lookup"><span data-stu-id="b23e8-112">In the following record requirements, SIP domain refers to the host portion of the SIP URIs assigned to users.</span></span> <span data-ttu-id="b23e8-113">例如，如果 SIP Uri 的形式是 \* @contoso，则 contoso.com 是 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="b23e8-113">For example, if SIP URIs are of the form \*@contoso.com, contoso.com is the SIP domain.</span></span> <span data-ttu-id="b23e8-114">SIP 域通常与内部 Active Directory 域不同。</span><span class="sxs-lookup"><span data-stu-id="b23e8-114">The SIP domain is often different from the internal Active Directory domain.</span></span> <span data-ttu-id="b23e8-115">组织还可以支持多个 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="b23e8-115">An organization can also support multiple SIP domains.</span></span>

    
    </div>

<span data-ttu-id="b23e8-116">若要为你的客户端启用自动配置，你必须创建内部 DNS SRV 记录，将以下记录之一映射到分发来自 Lync 的登录请求的前端池或标准版服务器的完全限定的域名（FQDN）台</span><span class="sxs-lookup"><span data-stu-id="b23e8-116">To enable automatic configuration for your clients, you must create an internal DNS SRV record that maps one of the following records to the fully qualified domain name (FQDN) of the Front End pool or Standard Edition server that distributes sign-in requests from Lync clients:</span></span>

  - <span data-ttu-id="b23e8-117">\_sipinternaltls.\_tcp。\<域\> -用于内部 TLS 连接</span><span class="sxs-lookup"><span data-stu-id="b23e8-117">\_sipinternaltls.\_tcp.\<domain\> - for internal TLS connections</span></span>

<span data-ttu-id="b23e8-118">你只需要为前端池或标准版服务器创建单个 SRV 记录，或者将分发登录请求。</span><span class="sxs-lookup"><span data-stu-id="b23e8-118">You only need to create a single SRV record for the Front End pool or Standard Edition server or that will distribute sign-in requests.</span></span>

<span data-ttu-id="b23e8-119">下表显示了虚构公司 Contoso 所需的一些示例记录，它支持 contoso.com 和 retail.contoso.com 的 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="b23e8-119">The following table shows some example records required for the fictitious company Contoso, which supports SIP domains of contoso.com and retail.contoso.com.</span></span>

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a><span data-ttu-id="b23e8-120">自动客户端登录多个 SIP 域所需的 DNS 记录示例</span><span class="sxs-lookup"><span data-stu-id="b23e8-120">Example of DNS Records Required for Automatic Client Sign-in with Multiple SIP Domains</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b23e8-121">用于分发登录请求的前端池的 FQDN</span><span class="sxs-lookup"><span data-stu-id="b23e8-121">FQDN of Front End pool used to distribute sign-in requests</span></span></th>
<th><span data-ttu-id="b23e8-122">SIP 域</span><span class="sxs-lookup"><span data-stu-id="b23e8-122">SIP domain</span></span></th>
<th><span data-ttu-id="b23e8-123">DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="b23e8-123">DNS SRV record</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b23e8-124">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b23e8-124">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b23e8-125">contoso.com</span><span class="sxs-lookup"><span data-stu-id="b23e8-125">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b23e8-126">映射到 pool01.contoso.com 的端口5061上的 _sipinternaltls _tcp .com 域的 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="b23e8-126">An SRV record for _sipinternaltls._tcp.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b23e8-127">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b23e8-127">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b23e8-128">retail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b23e8-128">retail.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b23e8-129">将 pool01.contoso.com 映射到的端口5061上的 _sipinternaltls 的 _tcp retail .com 域的 SRV 记录</span><span class="sxs-lookup"><span data-stu-id="b23e8-129">An SRV record for _sipinternaltls._tcp.retail.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b23e8-130">默认情况下，DNS 记录的查询将遵循用户名和 SRV 记录中的域之间的严格域名匹配。</span><span class="sxs-lookup"><span data-stu-id="b23e8-130">By default, queries for DNS records adhere to strict domain name matching between the domain in the user name and the SRV record.</span></span> <span data-ttu-id="b23e8-131">如果你希望客户端 DNS 查询改为使用后缀匹配，则可以配置 DisableStrictDNSNaming 组策略。</span><span class="sxs-lookup"><span data-stu-id="b23e8-131">If you prefer that client DNS queries use suffix matching instead, you can configure the DisableStrictDNSNaming Group Policy.</span></span> <span data-ttu-id="b23e8-132">有关详细信息，请参阅规划文档中的<A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013 中的客户端和设备规划</A>。</span><span class="sxs-lookup"><span data-stu-id="b23e8-132">For details, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a><span data-ttu-id="b23e8-133">自动客户端登录所需的证书和 DNS 记录示例</span><span class="sxs-lookup"><span data-stu-id="b23e8-133">Example of the Certificates and DNS Records Required for Automatic Client Sign-In</span></span>

<span data-ttu-id="b23e8-134">此示例使用上表中的相同示例名称。</span><span class="sxs-lookup"><span data-stu-id="b23e8-134">This example uses the same example names in the preceding table.</span></span> <span data-ttu-id="b23e8-135">Contoso 组织支持 contoso.com 和 retail.contoso.com 的 SIP 域，并且其所有用户都具有以下形式之一的 SIP URI：</span><span class="sxs-lookup"><span data-stu-id="b23e8-135">The Contoso organization supports the SIP domains of contoso.com and retail.contoso.com, and all of its users have a SIP URI in one of the following forms:</span></span>

  - <span data-ttu-id="b23e8-136">\<用户\>@retail contoso.com</span><span class="sxs-lookup"><span data-stu-id="b23e8-136">\<user\>@retail.contoso.com</span></span>

  - <span data-ttu-id="b23e8-137">\<用户\>@contoso .com</span><span class="sxs-lookup"><span data-stu-id="b23e8-137">\<user\>@contoso.com</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

