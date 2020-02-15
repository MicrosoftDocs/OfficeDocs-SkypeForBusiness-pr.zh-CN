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
ms.openlocfilehash: 7000456629a91742350b9866dc9e1441c18eee57
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="085fc-102">Lync Server 2013 中的外部用户访问的证书要求</span><span class="sxs-lookup"><span data-stu-id="085fc-102">Certificate requirements for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="085fc-103">_**上次修改的主题：** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="085fc-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="085fc-104">Microsoft Lync Server 2013 通信软件支持对访问和 web 会议边缘外部接口以及 A/V 身份验证服务使用一个公共证书。</span><span class="sxs-lookup"><span data-stu-id="085fc-104">Microsoft Lync Server 2013 communications software supports the use of a single public certificate for access and web conferencing Edge external interfaces, plus the A/V Authentication service.</span></span> <span data-ttu-id="085fc-105">边缘内部接口通常使用内部证书颁发机构 (CA) 颁发的专用证书，但同时也可以使用公共证书，前提是该证书是由受信任的公共 CA 颁发的。</span><span class="sxs-lookup"><span data-stu-id="085fc-105">The Edge internal interface typically uses a private certificate issued by an internal certification authority (CA), but can also use a public certificate, provided that it is from a trusted public CA.</span></span> <span data-ttu-id="085fc-106">部署中的反向代理使用公共证书，并会使用 HTTP 对反向代理与客户端以及反向代理与内部服务器之间的通信进行加密（即 HTTP 上的传输层安全性）。</span><span class="sxs-lookup"><span data-stu-id="085fc-106">The reverse proxy in your deployment uses a public certificate and encrypts the communication from the reverse proxy to clients and the reverse proxy to internal servers by using HTTP (that is, Transport Layer Security over HTTP).</span></span>

<span data-ttu-id="085fc-107">以下是用于访问、Web 会议边缘外部接口以及 A/V 身份验证服务的公共证书的要求：</span><span class="sxs-lookup"><span data-stu-id="085fc-107">Following are the requirements for the public certificate used for access and web conferencing Edge external interfaces, and the A/V authentication service:</span></span>

  - <span data-ttu-id="085fc-108">证书必须由经过批准的公共 CA 颁发，且该 CA 支持使用者替代名称。</span><span class="sxs-lookup"><span data-stu-id="085fc-108">The certificate must be issued by an approved public CA that supports subject alternative name.</span></span> <span data-ttu-id="085fc-109">有关详细信息，请参阅 Microsoft 知识库文章 929395 "Exchange Server 和通信服务器的统一通信证书合作伙伴"，网址[http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)为。</span><span class="sxs-lookup"><span data-stu-id="085fc-109">For details, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

  - <span data-ttu-id="085fc-p103">如果证书要在边缘池上使用，必须将其创建为可导出的证书，并在边缘池中的每台边缘服务器上使用相同的证书。可导出的私钥要求针对的是 A/V 身份验证服务，该服务必须在池中所有边缘服务器上使用同一私钥。</span><span class="sxs-lookup"><span data-stu-id="085fc-p103">If the certificate will be used on an Edge pool, it must be created as exportable, with the same certificate used on each Edge Server in the Edge pool. The exportable private key requirement is for the purposes of the A/V Authentication service, which must use the same private key across all Edge Servers in the pool.</span></span>

  - <span data-ttu-id="085fc-112">如果要最大限度地提高音频/视频服务的正常运行时间，请查看实现分离的 A/V 边缘服务证书（即，与其他外部边缘证书目的的单独 A/V 边缘服务证书）的证书要求。</span><span class="sxs-lookup"><span data-stu-id="085fc-112">If you want to maximize the uptime for your Audio/Video services, review the certificate requirements for implementing a decoupled A/V Edge service certificate (that is, a separate A/V Edge service certificate from the other External Edge certificate purposes).</span></span> <span data-ttu-id="085fc-113">有关详细信息，请参阅 lync server 2013 中的[更改，它会影响边缘服务器规划](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)、在 lync server [2013 中规划边缘服务器证书](lync-server-2013-plan-for-edge-server-certificates.md)，以及在[set-cscertificate 中使用-回滚在 LYNC server 2013 中暂存 AV 和 OAuth 证书](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)。</span><span class="sxs-lookup"><span data-stu-id="085fc-113">For details, see [Changes in Lync Server 2013 that affect Edge Server planning](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) and [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span></span>

  - <span data-ttu-id="085fc-114">证书的使用者名称是访问边缘服务外部接口完全限定的域名（FQDN）或硬件负载平衡器 VIP （例如，access.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="085fc-114">The subject name of the certificate is the Access Edge service external interface fully qualified domain name (FQDN) or hardware load balancer VIP (for example, access.contoso.com).</span></span> <span data-ttu-id="085fc-115">).</span><span class="sxs-lookup"><span data-stu-id="085fc-115">).</span></span> <span data-ttu-id="085fc-116">使用者名称不能包含通配符，它必须是显式名称。</span><span class="sxs-lookup"><span data-stu-id="085fc-116">The subject name can’t have a wildcard character, it must be an explicit name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="085fc-117">对于 Lync Server 2013，这不再是必需的，但仍建议与 Office 通信服务器兼容。</span><span class="sxs-lookup"><span data-stu-id="085fc-117">For Lync Server 2013, this is no longer a requirement, but it is still recommended for compatibility with Office Communications Server.</span></span>

    
    </div>

  - <span data-ttu-id="085fc-118">使用者替代名称列表包含以下各项的 FQDN：</span><span class="sxs-lookup"><span data-stu-id="085fc-118">The subject alternative name list contains the FQDNs of the following:</span></span>
    
      - <span data-ttu-id="085fc-119">访问边缘服务外部接口或硬件负载平衡器 VIP （例如，sip.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="085fc-119">The Access Edge service external interface or hardware load balancer VIP (for example, sip.contoso.com).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="085fc-120">即使证书使用者名称是访问边缘 FQDN，使用者替代名称还必须包含访问边缘 FQDN，因为传输层安全性 (TLS) 将忽略使用者名称，而使用使用者替代名称条目进行验证。</span><span class="sxs-lookup"><span data-stu-id="085fc-120">Even though the certificate subject name is equal to the access Edge FQDN, the subject alternative name must also contain the access Edge FQDN because Transport Layer Security (TLS) ignores the subject name and uses the subject alternative name entries for validation.</span></span>

        
        </div>
    
      - <span data-ttu-id="085fc-121">Web 会议边缘外部接口或硬件负载平衡器 VIP（例如，webcon.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="085fc-121">The web conferencing Edge external interface or hardware load balancer VIP (for example, webcon.contoso.com).</span></span>
    
      - <span data-ttu-id="085fc-122">如果要使用客户端自动配置或联盟，还需要包含公司内部使用的任何 SIP 域 FQDN（例如，sip.contoso.com、sip.fabrikam.com）。</span><span class="sxs-lookup"><span data-stu-id="085fc-122">If you are using client auto-configuration or federation, also include any SIP domain FQDNs used within your company (for example, sip.contoso.com, sip.fabrikam.com).</span></span>
    
      - <span data-ttu-id="085fc-123">A/V 边缘服务不使用主题名称或主题备用名称条目。</span><span class="sxs-lookup"><span data-stu-id="085fc-123">The A/V Edge service does not use the subject name or the subject alternative names entries.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="085fc-124">使用者替代名称列表中的 FQDN 顺序无关紧要。</span><span class="sxs-lookup"><span data-stu-id="085fc-124">The order of the FQDNs in the subject alternative names list does not matter.</span></span>

    
    </div>

<span data-ttu-id="085fc-p106">如果要在站点上部署多台负载平衡边缘服务器，则安装在每台边缘服务器上的 A/V 身份验证服务证书必须由同一 CA 颁发且必须使用同一私钥。请注意，证书的私钥必须是可导出的，不管是在一台边缘服务器上使用还是在多台边缘服务器上使用。如果要从任何计算机（边缘服务器除外）请求证书，则私钥也必须可导出。由于 A/V 身份验证服务不使用使用者名称或使用者替代名称，因此，一旦满足访问边缘和 Web 会议边缘的使用者名称和使用者替代名称要求，且证书的私钥是可导出的，您就能重用访问边缘证书。</span><span class="sxs-lookup"><span data-stu-id="085fc-p106">If you are deploying multiple, load-balanced Edge Servers at a site, the A/V authentication service certificate that is installed on each Edge Server must be from the same CA and must use the same private key. Note that the certificate's private key must be exportable, regardless of whether it is used on one Edge Server or many Edge Servers. It must also be exportable if you request the certificate from any computer other than the Edge Server. Because the A/V authentication service does not use the subject name or subject alternative name, you can reuse the access Edge certificate as long as the subject name and subject alternative name requirements are met for the access Edge and the web conferencing Edge and the certificate’s private key is exportable.</span></span>

<span data-ttu-id="085fc-129">用于边缘内部接口的专用（或公共）证书的要求如下所示：</span><span class="sxs-lookup"><span data-stu-id="085fc-129">Requirements for the private (or public) certificate used for the Edge internal interface are as follows:</span></span>

  - <span data-ttu-id="085fc-130">证书可由内部 CA 或经过批准的公共证书 CA 颁发。</span><span class="sxs-lookup"><span data-stu-id="085fc-130">The certificate can be issued by an internal CA or an approved public certificate CA.</span></span>

  - <span data-ttu-id="085fc-p107">证书的使用者名称通常是边缘内部接口 FQDN 或硬件负载平衡器 VIP（例如，lsedge.contoso.com）。但是，可以在边缘内部上使用通配证书。</span><span class="sxs-lookup"><span data-stu-id="085fc-p107">The subject name of the certificate is typically the Edge internal interface FQDN or hardware load balancer VIP (for example, lsedge.contoso.com). However, you can use a wildcard certificate on the Edge internal.</span></span>

  - <span data-ttu-id="085fc-133">不需要使用者替代名称列表。</span><span class="sxs-lookup"><span data-stu-id="085fc-133">No subject alternative name list is required.</span></span>

<span data-ttu-id="085fc-134">部署服务中的反向代理请求：</span><span class="sxs-lookup"><span data-stu-id="085fc-134">The reverse proxy in your deployment services requests for:</span></span>

  - <span data-ttu-id="085fc-135">对会议的会议内容的外部用户访问权</span><span class="sxs-lookup"><span data-stu-id="085fc-135">External user access to meeting content for meetings</span></span>

  - <span data-ttu-id="085fc-136">用于扩展和显示通讯组成员的外部用户访问权</span><span class="sxs-lookup"><span data-stu-id="085fc-136">External user access to expand and display members of distribution groups</span></span>

  - <span data-ttu-id="085fc-137">对可从通讯簿服务下载的文件的外部用户访问权</span><span class="sxs-lookup"><span data-stu-id="085fc-137">External user access to downloadable files from the Address Book Service</span></span>

  - <span data-ttu-id="085fc-138">外部用户对 Lync Web App 客户端的访问权限</span><span class="sxs-lookup"><span data-stu-id="085fc-138">External user access to the Lync Web App client</span></span>

  - <span data-ttu-id="085fc-139">对“电话拨入式会议设置”网页的外部用户访问权</span><span class="sxs-lookup"><span data-stu-id="085fc-139">External user access to the Dial-in Conferencing Settings web page</span></span>

  - <span data-ttu-id="085fc-140">对位置信息服务的外部用户访问权</span><span class="sxs-lookup"><span data-stu-id="085fc-140">External user access to the Location Information Service</span></span>

  - <span data-ttu-id="085fc-141">对设备更新服务的外部设备访问权并获取更新</span><span class="sxs-lookup"><span data-stu-id="085fc-141">External device access to the Device Update Service and obtain updates</span></span>

<span data-ttu-id="085fc-142">反向代理会发布内部服务器 Web 组件 URL。</span><span class="sxs-lookup"><span data-stu-id="085fc-142">The reverse proxy publishes the internal server Web Components URLs.</span></span> <span data-ttu-id="085fc-143">Web 组件 Url 在控制器、前端服务器或前端池上定义为拓扑生成器中的**外部 Web 服务**。</span><span class="sxs-lookup"><span data-stu-id="085fc-143">The Web Components URLs are defined on the Director, Front End Server or Front End pool as the **External web services** in Topology Builder.</span></span>

<span data-ttu-id="085fc-144">可以在分配给反向代理的证书的使用者替代名称字段中使用通配符条目。</span><span class="sxs-lookup"><span data-stu-id="085fc-144">Wildcard entries are supported in the subject alternative name field of the certificate assigned to the reverse proxy.</span></span> <span data-ttu-id="085fc-145">有关如何为反向代理配置证书申请的详细信息，请参阅[在 Lync Server 2013 中为您的反向 HTTP 代理请求和配置证书](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)。</span><span class="sxs-lookup"><span data-stu-id="085fc-145">For details about how to configure the certificate request for the reverse proxy, see [Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="085fc-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="085fc-146">See Also</span></span>


[<span data-ttu-id="085fc-147">Lync Server 2013 中的通配符证书支持</span><span class="sxs-lookup"><span data-stu-id="085fc-147">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

