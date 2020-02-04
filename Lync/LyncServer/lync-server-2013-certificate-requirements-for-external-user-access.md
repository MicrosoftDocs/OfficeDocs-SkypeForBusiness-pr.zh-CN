---
title: Lync Server 2013：外部用户访问的证书要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b6495dbad5350f94873099985922f1adc198f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="8da0d-102">Lync Server 2013 中外部用户访问的证书要求</span><span class="sxs-lookup"><span data-stu-id="8da0d-102">Certificate requirements for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8da0d-103">_**主题上次修改时间：** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="8da0d-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="8da0d-104">Microsoft Lync Server 2013 通信软件支持使用单个公共证书访问和网络会议边缘外部接口，以及 A/V 身份验证服务。</span><span class="sxs-lookup"><span data-stu-id="8da0d-104">Microsoft Lync Server 2013 communications software supports the use of a single public certificate for access and web conferencing Edge external interfaces, plus the A/V Authentication service.</span></span> <span data-ttu-id="8da0d-105">Edge 内部接口通常使用由内部证书颁发机构（CA）颁发的专用证书，但也可以使用公共证书（前提是该证书来自受信任的公共 CA）。</span><span class="sxs-lookup"><span data-stu-id="8da0d-105">The Edge internal interface typically uses a private certificate issued by an internal certification authority (CA), but can also use a public certificate, provided that it is from a trusted public CA.</span></span> <span data-ttu-id="8da0d-106">部署中的反向代理使用公共证书，并使用 HTTP （即通过 HTTP 传输层安全性）将反向代理和反向代理的通信加密到内部服务器。</span><span class="sxs-lookup"><span data-stu-id="8da0d-106">The reverse proxy in your deployment uses a public certificate and encrypts the communication from the reverse proxy to clients and the reverse proxy to internal servers by using HTTP (that is, Transport Layer Security over HTTP).</span></span>

<span data-ttu-id="8da0d-107">下面是用于访问和网络会议边缘外部接口以及 A/V 身份验证服务的公共证书的要求：</span><span class="sxs-lookup"><span data-stu-id="8da0d-107">Following are the requirements for the public certificate used for access and web conferencing Edge external interfaces, and the A/V authentication service:</span></span>

  - <span data-ttu-id="8da0d-108">证书必须由支持使用者备用名称的已批准公共 CA 颁发。</span><span class="sxs-lookup"><span data-stu-id="8da0d-108">The certificate must be issued by an approved public CA that supports subject alternative name.</span></span> <span data-ttu-id="8da0d-109">有关详细信息，请参阅 Microsoft 知识库文章929395： "Exchange Server 的统一通信证书合作伙伴和通信服务器" [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)。</span><span class="sxs-lookup"><span data-stu-id="8da0d-109">For details, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

  - <span data-ttu-id="8da0d-110">如果要在 Edge 池中使用证书，则该证书必须创建为可导出，并且在 Edge 池中的每个边缘服务器上使用相同的证书。</span><span class="sxs-lookup"><span data-stu-id="8da0d-110">If the certificate will be used on an Edge pool, it must be created as exportable, with the same certificate used on each Edge Server in the Edge pool.</span></span> <span data-ttu-id="8da0d-111">可导出私钥要求用于 A/V 身份验证服务，该服务必须在池中的所有边缘服务器上使用相同的私钥。</span><span class="sxs-lookup"><span data-stu-id="8da0d-111">The exportable private key requirement is for the purposes of the A/V Authentication service, which must use the same private key across all Edge Servers in the pool.</span></span>

  - <span data-ttu-id="8da0d-112">如果你想要最大化音频/视频服务的正常运行时间，请查看用于实现已解除的 A/V 边缘服务证书的证书要求（即来自其他外部边缘证书用途的单独的 A/V 边缘服务证书）。</span><span class="sxs-lookup"><span data-stu-id="8da0d-112">If you want to maximize the uptime for your Audio/Video services, review the certificate requirements for implementing a decoupled A/V Edge service certificate (that is, a separate A/V Edge service certificate from the other External Edge certificate purposes).</span></span> <span data-ttu-id="8da0d-113">有关详细信息，请参阅[影响边缘服务器规划的 Lync server 2013 中的更改](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)、在 lync server [2013 中规划 edge 服务器证书](lync-server-2013-plan-for-edge-server-certificates.md)和在[LYNC server 2013 中暂存 AV 和 OAuth 证书 CsCertificate 中的 "使用-滚](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)"。</span><span class="sxs-lookup"><span data-stu-id="8da0d-113">For details, see [Changes in Lync Server 2013 that affect Edge Server planning](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) and [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span></span>

  - <span data-ttu-id="8da0d-114">证书的使用者名称是访问边缘服务外部接口完全限定的域名（FQDN）或硬件负载平衡器 VIP （例如，access.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="8da0d-114">The subject name of the certificate is the Access Edge service external interface fully qualified domain name (FQDN) or hardware load balancer VIP (for example, access.contoso.com).</span></span> <span data-ttu-id="8da0d-115">).</span><span class="sxs-lookup"><span data-stu-id="8da0d-115">).</span></span> <span data-ttu-id="8da0d-116">主题名称不能包含通配符，它必须是显式名称。</span><span class="sxs-lookup"><span data-stu-id="8da0d-116">The subject name can’t have a wildcard character, it must be an explicit name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8da0d-117">对于 Lync Server 2013，不再需要这种情况，但仍建议使用它来与 Office 通信服务器兼容。</span><span class="sxs-lookup"><span data-stu-id="8da0d-117">For Lync Server 2013, this is no longer a requirement, but it is still recommended for compatibility with Office Communications Server.</span></span>

    
    </div>

  - <span data-ttu-id="8da0d-118">"主题备用名称" 列表包含以下各项的 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="8da0d-118">The subject alternative name list contains the FQDNs of the following:</span></span>
    
      - <span data-ttu-id="8da0d-119">访问边缘服务外部接口或硬件负载平衡器 VIP （例如，sip.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="8da0d-119">The Access Edge service external interface or hardware load balancer VIP (for example, sip.contoso.com).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="8da0d-120">即使证书使用者名称等于访问边缘 FQDN，"主题" 备用名称也必须包含访问边缘 FQDN，因为传输层安全性（TLS）会忽略使用者名称并使用 "主题备用名称" 条目进行验证.</span><span class="sxs-lookup"><span data-stu-id="8da0d-120">Even though the certificate subject name is equal to the access Edge FQDN, the subject alternative name must also contain the access Edge FQDN because Transport Layer Security (TLS) ignores the subject name and uses the subject alternative name entries for validation.</span></span>

        
        </div>
    
      - <span data-ttu-id="8da0d-121">Web 会议边缘外部接口或硬件负载平衡器 VIP （例如，webcon.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="8da0d-121">The web conferencing Edge external interface or hardware load balancer VIP (for example, webcon.contoso.com).</span></span>
    
      - <span data-ttu-id="8da0d-122">如果你使用的是客户端自动配置或联盟，还包括你的公司内使用的任何 SIP 域 Fqdn （例如，sip.contoso.com、sip.fabrikam.com）。</span><span class="sxs-lookup"><span data-stu-id="8da0d-122">If you are using client auto-configuration or federation, also include any SIP domain FQDNs used within your company (for example, sip.contoso.com, sip.fabrikam.com).</span></span>
    
      - <span data-ttu-id="8da0d-123">A/V 边缘服务不使用 "主题名称" 或 "主题备用名称" 条目。</span><span class="sxs-lookup"><span data-stu-id="8da0d-123">The A/V Edge service does not use the subject name or the subject alternative names entries.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8da0d-124">"主题备用名称" 列表中的 Fqdn 顺序无关紧要。</span><span class="sxs-lookup"><span data-stu-id="8da0d-124">The order of the FQDNs in the subject alternative names list does not matter.</span></span>

    
    </div>

<span data-ttu-id="8da0d-125">如果要在网站上部署多个负载平衡的边缘服务器，则每台边缘服务器上安装的 A/V 身份验证服务证书必须来自同一 CA，并且必须使用相同的私钥。</span><span class="sxs-lookup"><span data-stu-id="8da0d-125">If you are deploying multiple, load-balanced Edge Servers at a site, the A/V authentication service certificate that is installed on each Edge Server must be from the same CA and must use the same private key.</span></span> <span data-ttu-id="8da0d-126">请注意，证书的私钥必须是可导出的，无论它是在一台边缘服务器还是在多台边缘服务器上使用。</span><span class="sxs-lookup"><span data-stu-id="8da0d-126">Note that the certificate's private key must be exportable, regardless of whether it is used on one Edge Server or many Edge Servers.</span></span> <span data-ttu-id="8da0d-127">如果从除 Edge 服务器之外的任何计算机请求证书，也必须是可导出的。</span><span class="sxs-lookup"><span data-stu-id="8da0d-127">It must also be exportable if you request the certificate from any computer other than the Edge Server.</span></span> <span data-ttu-id="8da0d-128">由于 A/V 身份验证服务不使用使用者名称或使用者备用名称，因此你可以重复使用访问边缘证书，前提是访问边缘的主题名称和主题备用名称要求已达到访问边缘，并且证书的私钥可导出。</span><span class="sxs-lookup"><span data-stu-id="8da0d-128">Because the A/V authentication service does not use the subject name or subject alternative name, you can reuse the access Edge certificate as long as the subject name and subject alternative name requirements are met for the access Edge and the web conferencing Edge and the certificate’s private key is exportable.</span></span>

<span data-ttu-id="8da0d-129">用于 Edge 内部接口的专用（或公用）证书要求如下所示：</span><span class="sxs-lookup"><span data-stu-id="8da0d-129">Requirements for the private (or public) certificate used for the Edge internal interface are as follows:</span></span>

  - <span data-ttu-id="8da0d-130">证书可以由内部 CA 或已批准的公共证书 CA 颁发。</span><span class="sxs-lookup"><span data-stu-id="8da0d-130">The certificate can be issued by an internal CA or an approved public certificate CA.</span></span>

  - <span data-ttu-id="8da0d-131">证书的使用者名称通常是边缘内部接口 FQDN 或硬件负载平衡器 VIP （例如，lsedge.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="8da0d-131">The subject name of the certificate is typically the Edge internal interface FQDN or hardware load balancer VIP (for example, lsedge.contoso.com).</span></span> <span data-ttu-id="8da0d-132">但是，你可以在内部边缘使用通配符证书。</span><span class="sxs-lookup"><span data-stu-id="8da0d-132">However, you can use a wildcard certificate on the Edge internal.</span></span>

  - <span data-ttu-id="8da0d-133">不需要 "主题备用名称" 列表。</span><span class="sxs-lookup"><span data-stu-id="8da0d-133">No subject alternative name list is required.</span></span>

<span data-ttu-id="8da0d-134">部署服务中的反向代理请求：</span><span class="sxs-lookup"><span data-stu-id="8da0d-134">The reverse proxy in your deployment services requests for:</span></span>

  - <span data-ttu-id="8da0d-135">对会议内容的外部用户访问</span><span class="sxs-lookup"><span data-stu-id="8da0d-135">External user access to meeting content for meetings</span></span>

  - <span data-ttu-id="8da0d-136">用于展开和显示通讯组成员的外部用户访问权限</span><span class="sxs-lookup"><span data-stu-id="8da0d-136">External user access to expand and display members of distribution groups</span></span>

  - <span data-ttu-id="8da0d-137">外部用户从通讯簿服务访问可下载的文件</span><span class="sxs-lookup"><span data-stu-id="8da0d-137">External user access to downloadable files from the Address Book Service</span></span>

  - <span data-ttu-id="8da0d-138">对 Lync Web App 客户端的外部用户访问</span><span class="sxs-lookup"><span data-stu-id="8da0d-138">External user access to the Lync Web App client</span></span>

  - <span data-ttu-id="8da0d-139">外部用户访问电话拨入式会议设置网页</span><span class="sxs-lookup"><span data-stu-id="8da0d-139">External user access to the Dial-in Conferencing Settings web page</span></span>

  - <span data-ttu-id="8da0d-140">外部用户对位置信息服务的访问权限</span><span class="sxs-lookup"><span data-stu-id="8da0d-140">External user access to the Location Information Service</span></span>

  - <span data-ttu-id="8da0d-141">外部设备访问设备更新服务并获取更新</span><span class="sxs-lookup"><span data-stu-id="8da0d-141">External device access to the Device Update Service and obtain updates</span></span>

<span data-ttu-id="8da0d-142">反向代理发布内部服务器 Web 组件 Url。</span><span class="sxs-lookup"><span data-stu-id="8da0d-142">The reverse proxy publishes the internal server Web Components URLs.</span></span> <span data-ttu-id="8da0d-143">Web 组件 Url 在 "Director"、"前端服务器" 或 "前端池" 上定义为拓扑生成器中的**外部 Web 服务**。</span><span class="sxs-lookup"><span data-stu-id="8da0d-143">The Web Components URLs are defined on the Director, Front End Server or Front End pool as the **External web services** in Topology Builder.</span></span>

<span data-ttu-id="8da0d-144">在分配给反向代理的证书的 "主题备用名称" 字段中支持通配符条目。</span><span class="sxs-lookup"><span data-stu-id="8da0d-144">Wildcard entries are supported in the subject alternative name field of the certificate assigned to the reverse proxy.</span></span> <span data-ttu-id="8da0d-145">有关如何配置反向代理的证书申请的详细信息，请参阅[在 Lync Server 2013 中为您的反向 HTTP 代理请求和配置证书](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)。</span><span class="sxs-lookup"><span data-stu-id="8da0d-145">For details about how to configure the certificate request for the reverse proxy, see [Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8da0d-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8da0d-146">See Also</span></span>


[<span data-ttu-id="8da0d-147">Lync Server 2013 中的通配符证书支持</span><span class="sxs-lookup"><span data-stu-id="8da0d-147">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

