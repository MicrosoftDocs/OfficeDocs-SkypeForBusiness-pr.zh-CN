---
title: Lync Server 2013：了解自动发现
description: Lync Server 2013：了解自动发现。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 295aba4bffbe5d17070702203cfd933284cb12c0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547348"
---
# <a name="understanding-autodiscover-in-lync-server-2013"></a><span data-ttu-id="1debf-103">了解 Lync Server 2013 中的自动发现</span><span class="sxs-lookup"><span data-stu-id="1debf-103">Understanding Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1debf-104">_**上次修改的主题：** 2013-06-03_</span><span class="sxs-lookup"><span data-stu-id="1debf-104">_**Topic Last Modified:** 2013-06-03_</span></span>

<span data-ttu-id="1debf-105">Lync Server 2013 自动发现服务是最初在 Microsoft Lync Server 2010 中引入的一项功能，作为 Lync Server 2010 累积更新的一部分：11月2011。</span><span class="sxs-lookup"><span data-stu-id="1debf-105">The Lync Server 2013 Autodiscover Service is a feature that was originally introduced in Microsoft Lync Server 2010 as part of the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="1debf-106">除修补外，此累积更新提供了对 Lync Mobile 和 Lync 2013 客户端的支持。</span><span class="sxs-lookup"><span data-stu-id="1debf-106">In addition to fixes, this cumulative update delivered support for Lync Mobile and Lync 2013 clients.</span></span>

<span data-ttu-id="1debf-107">在 Lync Server 2013 中，自动发现服务是外部和内部移动客户端的操作不可或缺的一部分，自动发现也扩展到新客户端，如最近引入的适用于 Windows 8 的 Lync Windows 应用商店应用程序。</span><span class="sxs-lookup"><span data-stu-id="1debf-107">In Lync Server 2013, the Autodiscover Service is an integral part of the operation of external and internal mobile clients, and Autodiscover is also extended to new clients, such as the recently introduced Lync Windows Store app for Windows 8.</span></span> <span data-ttu-id="1debf-108">Lync 2013 桌面客户端也使用自动发现。</span><span class="sxs-lookup"><span data-stu-id="1debf-108">Autodiscover is also used by the Lync 2013 desktop clients.</span></span> <span data-ttu-id="1debf-109">在 Lync Server 中，根据所需的域名系统 (DNS) 记录 lyncdiscover. 中识别自动发现 \*\*。 \<domain\> \*\*</span><span class="sxs-lookup"><span data-stu-id="1debf-109">Autodiscover is recognized in Lync Server by the required domain name system (DNS) records **lyncdiscover.\<domain\>**</span></span> <span data-ttu-id="1debf-110">和\*\*lyncdiscoverinternal.。 \<domain\> \*\*</span><span class="sxs-lookup"><span data-stu-id="1debf-110">and **lyncdiscoverinternal.\<domain\>**.</span></span> <span data-ttu-id="1debf-111">此外，Lync 2010 和 Lync 2013 桌面客户端的较新版本更喜欢通过域名系统的自动发现 (DNS) SRV 记录，仅在 lyncdiscover. 时使用 DNS SRV 记录。\<domain\></span><span class="sxs-lookup"><span data-stu-id="1debf-111">Additionally, newer versions of the Lync 2010 and Lync 2013 desktop client prefer Autodiscover over the domain name system (DNS) SRV records, using DNS SRV records only if lyncdiscover.\<domain\></span></span> <span data-ttu-id="1debf-112">或 lyncdiscoverinternal.。\<domain\></span><span class="sxs-lookup"><span data-stu-id="1debf-112">or lyncdiscoverinternal.\<domain\></span></span> <span data-ttu-id="1debf-113">不响应或不解决问题。</span><span class="sxs-lookup"><span data-stu-id="1debf-113">does not respond or does not resolve.</span></span> <span data-ttu-id="1debf-114">适用于 Windows 8 和 Lync Mobile 的 Lync Windows 应用商店应用程序以独占方式使用自动发现，不会引用传统的 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="1debf-114">The Lync Windows Store app for Windows 8 and Lync Mobile uses Autodiscover exclusively and will not refer to the traditional DNS SRV records.</span></span>

<span data-ttu-id="1debf-115">在 Lync Server 2013 中，自动发现功能已展开，以与客户端通信，以便客户端可以使用哪些元素、功能和通信方法。</span><span class="sxs-lookup"><span data-stu-id="1debf-115">In Lync Server 2013, Autodiscover is expanded to communicate to the client which elements, features, and communication methods are available to the client.</span></span> <span data-ttu-id="1debf-116">该信息通过从客户端发送的请求进行传递，并且 Lync Server web 服务使用明确定义的响应来响应客户端可以使用的信息，以及如何与自动发现响应文档的格式联系这些功能。</span><span class="sxs-lookup"><span data-stu-id="1debf-116">The information is communicated through a request that is sent from the client, and the Lync Server web services responds with a clearly defined response that names what is available to the client, and how to contact those features in the format of the Autodiscover Response document.</span></span>

<span data-ttu-id="1debf-117">了解自动发现响应文档（包括 web 服务如何通过此文档向客户端传达功能）的最佳方式是 dissect，并在来自 Lync web 服务自动发现响应文档的典型响应中定义每行。</span><span class="sxs-lookup"><span data-stu-id="1debf-117">The best way to understand the Autodiscover response document, including how the web services communicate features to clients through this document, is to dissect and define each line in a typical response from the Lync web service Autodiscover response document.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="1debf-118">在下面的详细信息中，用户已通过响应身份验证请求向主服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="1debf-118">In the details that follow, the user has already authenticated to the home server by responding to an authentication request.</span></span>



</div>

<div class="">


> [!NOTE]  
> <span data-ttu-id="1debf-119">Lync 自动发现 Web 服务在<STRONG>Microsoft Developer Network</STRONG> (MSDN) 库的 "<STRONG>打开规范</STRONG>" 部分中的 " <STRONG>microsoft Office 协议</STRONG>" 中定义。</span><span class="sxs-lookup"><span data-stu-id="1debf-119">The Lync Autodiscover Web Service is defined in the <STRONG>Microsoft Office Protocols</STRONG> in the <STRONG>Open Specifications</STRONG> section of the <STRONG>Microsoft Developer Network</STRONG> (MSDN) library.</span></span> <span data-ttu-id="1debf-120">有关详细信息，请参阅：中的完整规范文档 "Lync 自动发现 Web 服务协议" <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A> 。</span><span class="sxs-lookup"><span data-stu-id="1debf-120">For details, see the full specification document, "Lync Autodiscover Web Service Protocol," at: <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A>.</span></span> <span data-ttu-id="1debf-121">有关身份验证的详细信息，请参阅处的 "OC 身份验证 Web 服务协议" <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A> 。</span><span class="sxs-lookup"><span data-stu-id="1debf-121">For details about authentication, see "OC Authentication Web Service Protocol" at <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A>.</span></span>



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a><span data-ttu-id="1debf-122">Lync Server Web 服务自动发现响应</span><span class="sxs-lookup"><span data-stu-id="1debf-122">The Lync Server Web Service Autodiscover Response</span></span>

<span data-ttu-id="1debf-123">向内部或外部客户端发送自动发现请求时返回的响应是相同的。</span><span class="sxs-lookup"><span data-stu-id="1debf-123">The response returned when the Autodiscover request is sent is the same for an internal or an external client.</span></span> <span data-ttu-id="1debf-124">某些可感知位置的参数可能会发生变化。</span><span class="sxs-lookup"><span data-stu-id="1debf-124">Some parameters that are location–aware may change.</span></span> <span data-ttu-id="1debf-125">如果收到客户端请求，但实际池不是已联系的池，则将为该用户设置用户的主池。</span><span class="sxs-lookup"><span data-stu-id="1debf-125">If a client request is received, but the actual pool is other than the one that has been contacted, the user’s home pool will be set for that user.</span></span> <span data-ttu-id="1debf-126">如果同事的用户帐户位于不同的池，但从同一个办公室登录，则响应会略有不同。</span><span class="sxs-lookup"><span data-stu-id="1debf-126">A colleague whose user account is on a different pool, but logging in from the same office, would get a slightly different response.</span></span> <span data-ttu-id="1debf-127">响应指示该用户的正确的前端服务器或前端池。</span><span class="sxs-lookup"><span data-stu-id="1debf-127">The response indicates the correct Front End Server or Front End pool for that user.</span></span>

<span data-ttu-id="1debf-128">自动发现响应文档的示例：</span><span class="sxs-lookup"><span data-stu-id="1debf-128">An example of an Autodiscover Response document:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">
       <User>
          <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
          <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
          <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
          <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
          <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
          <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
          <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
          <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
          <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
          <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
          <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
          <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
          <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>
       </User>
    </AutodiscoverResponse>

<div>

## <a name="autodiscover-response-document-details"></a><span data-ttu-id="1debf-129">自动发现响应文档详细信息</span><span class="sxs-lookup"><span data-stu-id="1debf-129">Autodiscover Response Document Details</span></span>

<span data-ttu-id="1debf-130">自动发现响应文档可采用两种格式之一。</span><span class="sxs-lookup"><span data-stu-id="1debf-130">The Autodiscover Response document can be in one of two formats.</span></span> <span data-ttu-id="1debf-131">默认格式是 (JSON) 的 JavaScript 对象表示法。</span><span class="sxs-lookup"><span data-stu-id="1debf-131">The default format is a JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="1debf-132">另一种格式是 (XML) document 的可扩展标记语言。</span><span class="sxs-lookup"><span data-stu-id="1debf-132">The other format is extensible markup language (XML) document.</span></span> <span data-ttu-id="1debf-133">此示例使用 XML。</span><span class="sxs-lookup"><span data-stu-id="1debf-133">The XML is used for this example.</span></span> <span data-ttu-id="1debf-134">请求和响应是可预测的，因为文档具有确定格式的定义架构。</span><span class="sxs-lookup"><span data-stu-id="1debf-134">The request and response are predictable because the document has a defined schema that determines the format.</span></span> <span data-ttu-id="1debf-135">文档中描述所使用的架构的行是请求或响应中的第一行：</span><span class="sxs-lookup"><span data-stu-id="1debf-135">The line in the document that describes the schema used is the first line in the request or response:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

<span data-ttu-id="1debf-136">**AccessLocation = "External"** 的定义表明请求是从外部用户发出的。</span><span class="sxs-lookup"><span data-stu-id="1debf-136">The definition of **AccessLocation=”External”** indicates that the request was made from an external user.</span></span>

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

<span data-ttu-id="1debf-137">当前未使用 SipServerInternalAccess 和 SipServerExternalAccess。</span><span class="sxs-lookup"><span data-stu-id="1debf-137">SipServerInternalAccess and SipServerExternalAccess are currently not used.</span></span> <span data-ttu-id="1debf-138">保留这些项以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="1debf-138">These entries are reserved for future use.</span></span>

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

<span data-ttu-id="1debf-139">SipClientInternalAccess 和 SipClientExternalAccess 描述内部或外部客户端将用于访问定义的 SIP 服务器的完全限定的域名和端口。</span><span class="sxs-lookup"><span data-stu-id="1debf-139">SipClientInternalAccess and SipClientExternalAccess describe the fully qualified domain name and port that an internal or external client will use to access the defined SIP Server.</span></span> <span data-ttu-id="1debf-140">Lync 桌面客户端和 Lync Windows 应用商店应用使用这些条目，具体取决于其在内部或外部) 的位置 (查找控制器或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="1debf-140">The Lync desktop client and the Lync Windows Store app use these entries, based on their location (internal or external) to find the Director or Front End Server.</span></span>

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

<span data-ttu-id="1debf-141">这些 `Autodiscover` 引用包含自动发现服务的服务入口点。</span><span class="sxs-lookup"><span data-stu-id="1debf-141">The `Autodiscover` references contain the service entry points for the Autodiscover service.</span></span> <span data-ttu-id="1debf-142">令牌属性包含服务的名称，href 是为可在其中找到服务的客户端定义的 URL。</span><span class="sxs-lookup"><span data-stu-id="1debf-142">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="1debf-143">外部网络上的客户端使用 `External/Autodiscover` 。</span><span class="sxs-lookup"><span data-stu-id="1debf-143">Clients on an external network use the `External/Autodiscover`.</span></span> <span data-ttu-id="1debf-144">自动发现服务作为部署过程的一部分进行安装。</span><span class="sxs-lookup"><span data-stu-id="1debf-144">The Autodiscover service is installed as part of the deployment process.</span></span> <span data-ttu-id="1debf-145">`Internal/Autodiscover` 当前未使用，并保留以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="1debf-145">`Internal/Autodiscover` is not currently used, and is reserved for future use.</span></span>

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

<span data-ttu-id="1debf-146">这些 `AuthBroker` 引用包含内部和外部身份验证代理服务的服务入口点（在此示例中为 "sip."）。</span><span class="sxs-lookup"><span data-stu-id="1debf-146">The `AuthBroker` references contain the service entry points for the internal and the external authentication broker service, in this case, sip.svc.</span></span> <span data-ttu-id="1debf-147">令牌属性包含服务的名称，href 是为可在其中找到服务的客户端定义的 URL。</span><span class="sxs-lookup"><span data-stu-id="1debf-147">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="1debf-148">内部网络上使用的客户端 `Internal/AuthBroker` 。</span><span class="sxs-lookup"><span data-stu-id="1debf-148">Clients on the internal network with use `Internal/AuthBroker`.</span></span> <span data-ttu-id="1debf-149">外部网络上的客户端使用 `External/AuthBroker` 。</span><span class="sxs-lookup"><span data-stu-id="1debf-149">Clients on an external network use the `External/AuthBroker`.</span></span> <span data-ttu-id="1debf-150">AuthBroker 服务作为内部 Lync Server 2013 部署 web 服务部署过程的一部分安装。</span><span class="sxs-lookup"><span data-stu-id="1debf-150">The AuthBroker service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

<span data-ttu-id="1debf-151">`WebScheduler`令牌引用用于客户端访问的 url，以供客户端访问 Lync Server 会议的基于 web 的计划。</span><span class="sxs-lookup"><span data-stu-id="1debf-151">The `WebScheduler` token references the URLs for client access to the web-based scheduling for Lync Server conferences.</span></span> <span data-ttu-id="1debf-152">目前，仅 `External/WebScheduler` 使用。</span><span class="sxs-lookup"><span data-stu-id="1debf-152">Currently, only the `External/WebScheduler` is used.</span></span> <span data-ttu-id="1debf-153">WebScheduler 作为内部 Lync Server 2013 部署 web 服务部署过程的一部分进行安装。</span><span class="sxs-lookup"><span data-stu-id="1debf-153">The WebScheduler is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

<span data-ttu-id="1debf-154">`Internal/Mcx` 以及 `External/Mcx` 在 Lync Server 2010 的累积更新中引入的移动服务的位置：11月2011。</span><span class="sxs-lookup"><span data-stu-id="1debf-154">`Internal/Mcx` and `External/Mcx` are the locations of the Mobility services, introduced in Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="1debf-155">在所有受支持的设备上，Lync 2010 Mobile 将继续使用这些引用。</span><span class="sxs-lookup"><span data-stu-id="1debf-155">These references will continue to be used by Lync 2010 Mobile on all supported devices.</span></span> <span data-ttu-id="1debf-156">Mcx 服务作为内部 Lync Server 2013 部署 web 服务部署过程的一部分安装。</span><span class="sxs-lookup"><span data-stu-id="1debf-156">The Mcx service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

<span data-ttu-id="1debf-157">**Internal/Ucwa**、 **External/Ucwa** 和 **Ucwa** 为客户端提供了一种方法，用于访问统一通信 WEB 应用程序编程接口 (Ucwa API 或仅仅是 Ucwa) 。</span><span class="sxs-lookup"><span data-stu-id="1debf-157">**Internal/Ucwa**, **External/Ucwa** and **Ucwa** provide a means for clients to access the Unified Communications Web Application Programming Interface (UCWA API, or simply UCWA).</span></span> <span data-ttu-id="1debf-158">`Internal/Ucwa` 和 `External/Ucwa` 虚拟目录是保留用于未来功能增强的访问点，不使用。</span><span class="sxs-lookup"><span data-stu-id="1debf-158">`Internal/Ucwa` and `External/Ucwa` virtual directories are access points reserved for future feature enhancement, and are not used.</span></span> <span data-ttu-id="1debf-159">`Ucwa`虚拟目录用于 Microsoft Lync Mobile (在所有受支持的设备上通过 Lync Server 2013) 引入。</span><span class="sxs-lookup"><span data-stu-id="1debf-159">The `Ucwa` virtual directory is used for Microsoft Lync Mobile (introduced with Lync Server 2013) on all supported devices.</span></span> <span data-ttu-id="1debf-160">UCWA 服务作为内部 Lync Server 2013 部署 web 服务部署过程的一部分安装。</span><span class="sxs-lookup"><span data-stu-id="1debf-160">The UCWA service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

<span data-ttu-id="1debf-161">`Internal/XFrame`、 **External/XFrame** 和 **XFrame** 提供对基于 UCWA 的服务器应用程序的访问权限。</span><span class="sxs-lookup"><span data-stu-id="1debf-161">`Internal/XFrame`, **External/XFrame** and **XFrame** provide access for UCWA-based server applications.</span></span> <span data-ttu-id="1debf-162">XFrame 作为内部 Lync Server 2013 部署 web 服务部署过程的一部分进行安装。</span><span class="sxs-lookup"><span data-stu-id="1debf-162">XFrame is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

<span data-ttu-id="1debf-163">`Self`令牌是指发出请求的客户端 (用户响应类型) 的特定信息。</span><span class="sxs-lookup"><span data-stu-id="1debf-163">The `Self` token refers to information specific to the client (user response type) that is making the request.</span></span> <span data-ttu-id="1debf-164">发出此请求的客户端是外部客户端，而此自动发现参考是对自动发现服务的用户部分。</span><span class="sxs-lookup"><span data-stu-id="1debf-164">The client that made this request was external, and this Autodiscover reference is to the user portion of the Autodiscover service.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1debf-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1debf-165">See Also</span></span>


[<span data-ttu-id="1debf-166">Lync Server 2013 的外部用户访问组件的系统要求</span><span class="sxs-lookup"><span data-stu-id="1debf-166">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[<span data-ttu-id="1debf-167">在 Lync Server 2013 中规划自动发现</span><span class="sxs-lookup"><span data-stu-id="1debf-167">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

