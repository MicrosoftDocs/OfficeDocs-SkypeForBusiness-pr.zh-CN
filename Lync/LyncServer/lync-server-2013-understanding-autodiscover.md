---
title: Lync Server 2013：了解自动发现
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
ms.openlocfilehash: d9d885654f9222ce3d3e9fb7b03e9b388f0ca0a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a><span data-ttu-id="8d945-102">了解 Lync Server 2013 中的自动发现</span><span class="sxs-lookup"><span data-stu-id="8d945-102">Understanding Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d945-103">_**主题上次修改时间：** 2013-06-03_</span><span class="sxs-lookup"><span data-stu-id="8d945-103">_**Topic Last Modified:** 2013-06-03_</span></span>

<span data-ttu-id="8d945-104">Lync Server 2013 自动发现服务是最初在 Microsoft Lync Server 2010 中引入的一项功能，作为 Lync Server 2010 的累积更新的一部分：11月2011。</span><span class="sxs-lookup"><span data-stu-id="8d945-104">The Lync Server 2013 Autodiscover Service is a feature that was originally introduced in Microsoft Lync Server 2010 as part of the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="8d945-105">除了修补程序，此累积更新提供了对 Lync Mobile 和 Lync 2013 客户端的支持。</span><span class="sxs-lookup"><span data-stu-id="8d945-105">In addition to fixes, this cumulative update delivered support for Lync Mobile and Lync 2013 clients.</span></span>

<span data-ttu-id="8d945-106">在 Lync Server 2013 中，自动发现服务是外部和内部移动客户端的操作的一部分，并且自动发现也扩展到新客户端，如最近推出的适用于 Windows 8 的 Lync Windows 应用商店应用。</span><span class="sxs-lookup"><span data-stu-id="8d945-106">In Lync Server 2013, the Autodiscover Service is an integral part of the operation of external and internal mobile clients, and Autodiscover is also extended to new clients, such as the recently introduced Lync Windows Store app for Windows 8.</span></span> <span data-ttu-id="8d945-107">自动发现也由 Lync 2013 桌面客户端使用。</span><span class="sxs-lookup"><span data-stu-id="8d945-107">Autodiscover is also used by the Lync 2013 desktop clients.</span></span> <span data-ttu-id="8d945-108">在 Lync Server 中通过所需的域名系统（DNS）记录 lyncdiscover 识别自动发现 **。\<域\> **和**lyncdiscoverinternal。\<域\>**。</span><span class="sxs-lookup"><span data-stu-id="8d945-108">Autodiscover is recognized in Lync Server by the required domain name system (DNS) records **lyncdiscover.\<domain\>** and **lyncdiscoverinternal.\<domain\>**.</span></span> <span data-ttu-id="8d945-109">此外，Lync 2010 和 Lync 2013 桌面客户端的较新版本更喜欢通过域名系统（DNS） SRV 记录的自动发现，仅当 lyncdiscover 时才使用 DNS SRV 记录。\<domain\>或 lyncdiscoverinternal。\<域\>不响应或不解析。</span><span class="sxs-lookup"><span data-stu-id="8d945-109">Additionally, newer versions of the Lync 2010 and Lync 2013 desktop client prefer Autodiscover over the domain name system (DNS) SRV records, using DNS SRV records only if lyncdiscover.\<domain\> or lyncdiscoverinternal.\<domain\> does not respond or does not resolve.</span></span> <span data-ttu-id="8d945-110">适用于 Windows 8 和 Lync Mobile 的 Lync Windows 应用商店应用程序以独占方式使用自动发现，并且不会引用传统的 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="8d945-110">The Lync Windows Store app for Windows 8 and Lync Mobile uses Autodiscover exclusively and will not refer to the traditional DNS SRV records.</span></span>

<span data-ttu-id="8d945-111">在 Lync Server 2013 中，将扩展自动发现以与客户端通信，这些元素、功能和通信方法可用于客户端。</span><span class="sxs-lookup"><span data-stu-id="8d945-111">In Lync Server 2013, Autodiscover is expanded to communicate to the client which elements, features, and communication methods are available to the client.</span></span> <span data-ttu-id="8d945-112">信息通过从客户端发送的请求进行通信，并且 Lync Server web 服务以明确定义的响应来响应客户端可用的内容，以及如何以自动发现的格式联系这些功能响应文档。</span><span class="sxs-lookup"><span data-stu-id="8d945-112">The information is communicated through a request that is sent from the client, and the Lync Server web services responds with a clearly defined response that names what is available to the client, and how to contact those features in the format of the Autodiscover Response document.</span></span>

<span data-ttu-id="8d945-113">了解自动发现响应文档（包括 web 服务如何通过此文档向客户端传达功能）的最佳方式是 dissect，并在来自 Lync web 服务自动发现响应文档的典型响应中定义每一行。</span><span class="sxs-lookup"><span data-stu-id="8d945-113">The best way to understand the Autodiscover response document, including how the web services communicate features to clients through this document, is to dissect and define each line in a typical response from the Lync web service Autodiscover response document.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="8d945-114">在随后的详细信息中，用户已通过响应身份验证请求对主服务器进行了身份验证。</span><span class="sxs-lookup"><span data-stu-id="8d945-114">In the details that follow, the user has already authenticated to the home server by responding to an authentication request.</span></span>



</div>

<div class="">


> [!NOTE]  
> <span data-ttu-id="8d945-115">Lync 自动发现 Web 服务在<STRONG>Microsoft 开发人员网络</STRONG>（MSDN）库的 "<STRONG>打开规范</STRONG>" 部分中的<STRONG>microsoft Office 协议</STRONG>中定义。</span><span class="sxs-lookup"><span data-stu-id="8d945-115">The Lync Autodiscover Web Service is defined in the <STRONG>Microsoft Office Protocols</STRONG> in the <STRONG>Open Specifications</STRONG> section of the <STRONG>Microsoft Developer Network</STRONG> (MSDN) library.</span></span> <span data-ttu-id="8d945-116">有关详细信息，请参阅以下位置的完整规范文档： <A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>"Lync 自动发现 Web 服务协议"。</span><span class="sxs-lookup"><span data-stu-id="8d945-116">For details, see the full specification document, "Lync Autodiscover Web Service Protocol," at: <A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>.</span></span> <span data-ttu-id="8d945-117">有关身份验证的详细信息，请参阅中的 "OC 身份<A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>验证 Web 服务协议"。</span><span class="sxs-lookup"><span data-stu-id="8d945-117">For details about authentication, see "OC Authentication Web Service Protocol" at <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>.</span></span>



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a><span data-ttu-id="8d945-118">Lync Server Web 服务自动发现响应</span><span class="sxs-lookup"><span data-stu-id="8d945-118">The Lync Server Web Service Autodiscover Response</span></span>

<span data-ttu-id="8d945-119">向内部或外部客户端发送自动发现请求时，返回的响应是相同的。</span><span class="sxs-lookup"><span data-stu-id="8d945-119">The response returned when the Autodiscover request is sent is the same for an internal or an external client.</span></span> <span data-ttu-id="8d945-120">某些位置的可识别参数可能会发生变化。</span><span class="sxs-lookup"><span data-stu-id="8d945-120">Some parameters that are location–aware may change.</span></span> <span data-ttu-id="8d945-121">如果收到客户请求，但实际池不是已联系的池，则将为该用户设置用户的主池。</span><span class="sxs-lookup"><span data-stu-id="8d945-121">If a client request is received, but the actual pool is other than the one that has been contacted, the user’s home pool will be set for that user.</span></span> <span data-ttu-id="8d945-122">如果同事的用户帐户位于不同的池中，但从同一 office 登录，将获得稍有不同的答复。</span><span class="sxs-lookup"><span data-stu-id="8d945-122">A colleague whose user account is on a different pool, but logging in from the same office, would get a slightly different response.</span></span> <span data-ttu-id="8d945-123">该响应指示该用户的正确前端服务器或前端池。</span><span class="sxs-lookup"><span data-stu-id="8d945-123">The response indicates the correct Front End Server or Front End pool for that user.</span></span>

<span data-ttu-id="8d945-124">自动发现响应文档示例：</span><span class="sxs-lookup"><span data-stu-id="8d945-124">An example of an Autodiscover Response document:</span></span>

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

## <a name="autodiscover-response-document-details"></a><span data-ttu-id="8d945-125">自动发现响应文档详细信息</span><span class="sxs-lookup"><span data-stu-id="8d945-125">Autodiscover Response Document Details</span></span>

<span data-ttu-id="8d945-126">自动发现响应文档可以是两种格式中的一种。</span><span class="sxs-lookup"><span data-stu-id="8d945-126">The Autodiscover Response document can be in one of two formats.</span></span> <span data-ttu-id="8d945-127">默认格式是 JavaScript 对象表示法（JSON）。</span><span class="sxs-lookup"><span data-stu-id="8d945-127">The default format is a JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="8d945-128">另一种格式是可扩展标记语言（XML）文档。</span><span class="sxs-lookup"><span data-stu-id="8d945-128">The other format is extensible markup language (XML) document.</span></span> <span data-ttu-id="8d945-129">此示例使用 XML。</span><span class="sxs-lookup"><span data-stu-id="8d945-129">The XML is used for this example.</span></span> <span data-ttu-id="8d945-130">请求和响应可预测，因为文档具有确定格式的已定义架构。</span><span class="sxs-lookup"><span data-stu-id="8d945-130">The request and response are predictable because the document has a defined schema that determines the format.</span></span> <span data-ttu-id="8d945-131">文档中描述所使用的架构的行是请求或响应中的第一行：</span><span class="sxs-lookup"><span data-stu-id="8d945-131">The line in the document that describes the schema used is the first line in the request or response:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

<span data-ttu-id="8d945-132">**AccessLocation = "External"** 的定义指示从外部用户发出请求。</span><span class="sxs-lookup"><span data-stu-id="8d945-132">The definition of **AccessLocation=”External”** indicates that the request was made from an external user.</span></span>

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

<span data-ttu-id="8d945-133">SipServerInternalAccess 和 SipServerExternalAccess 当前未使用。</span><span class="sxs-lookup"><span data-stu-id="8d945-133">SipServerInternalAccess and SipServerExternalAccess are currently not used.</span></span> <span data-ttu-id="8d945-134">保留这些条目供将来使用。</span><span class="sxs-lookup"><span data-stu-id="8d945-134">These entries are reserved for future use.</span></span>

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

<span data-ttu-id="8d945-135">SipClientInternalAccess 和 SipClientExternalAccess 描述了内部或外部客户端用于访问定义的 SIP 服务器的完全限定的域名和端口。</span><span class="sxs-lookup"><span data-stu-id="8d945-135">SipClientInternalAccess and SipClientExternalAccess describe the fully qualified domain name and port that an internal or external client will use to access the defined SIP Server.</span></span> <span data-ttu-id="8d945-136">Lync 桌面客户端和 Lync Windows 应用商店应用将根据其位置（内部或外部）使用这些条目来查找控制器或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="8d945-136">The Lync desktop client and the Lync Windows Store app use these entries, based on their location (internal or external) to find the Director or Front End Server.</span></span>

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

<span data-ttu-id="8d945-137">这些`Autodiscover`引用包含自动发现服务的服务入口点。</span><span class="sxs-lookup"><span data-stu-id="8d945-137">The `Autodiscover` references contain the service entry points for the Autodiscover service.</span></span> <span data-ttu-id="8d945-138">令牌属性包含服务的名称，href 是定义可在其中找到服务的客户端的 URL。</span><span class="sxs-lookup"><span data-stu-id="8d945-138">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="8d945-139">外部网络上的客户端使用`External/Autodiscover`。</span><span class="sxs-lookup"><span data-stu-id="8d945-139">Clients on an external network use the `External/Autodiscover`.</span></span> <span data-ttu-id="8d945-140">自动发现服务作为部署过程的一部分进行安装。</span><span class="sxs-lookup"><span data-stu-id="8d945-140">The Autodiscover service is installed as part of the deployment process.</span></span> <span data-ttu-id="8d945-141">`Internal/Autodiscover`当前未使用，并保留供将来使用。</span><span class="sxs-lookup"><span data-stu-id="8d945-141">`Internal/Autodiscover` is not currently used, and is reserved for future use.</span></span>

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

<span data-ttu-id="8d945-142">这些`AuthBroker`引用包含内部和外部身份验证代理服务的服务入口点，在此情况下，为 "sip .svc"。</span><span class="sxs-lookup"><span data-stu-id="8d945-142">The `AuthBroker` references contain the service entry points for the internal and the external authentication broker service, in this case, sip.svc.</span></span> <span data-ttu-id="8d945-143">令牌属性包含服务的名称，href 是定义可在其中找到服务的客户端的 URL。</span><span class="sxs-lookup"><span data-stu-id="8d945-143">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="8d945-144">使用`Internal/AuthBroker`内部网络的客户端。</span><span class="sxs-lookup"><span data-stu-id="8d945-144">Clients on the internal network with use `Internal/AuthBroker`.</span></span> <span data-ttu-id="8d945-145">外部网络上的客户端使用`External/AuthBroker`。</span><span class="sxs-lookup"><span data-stu-id="8d945-145">Clients on an external network use the `External/AuthBroker`.</span></span> <span data-ttu-id="8d945-146">AuthBroker 服务作为内部 Lync Server 2013 部署 web 服务部署过程的一部分进行安装。</span><span class="sxs-lookup"><span data-stu-id="8d945-146">The AuthBroker service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

<span data-ttu-id="8d945-147">该`WebScheduler`令牌引用用于客户端访问 Lync Server 会议基于 web 的计划的 url。</span><span class="sxs-lookup"><span data-stu-id="8d945-147">The `WebScheduler` token references the URLs for client access to the web-based scheduling for Lync Server conferences.</span></span> <span data-ttu-id="8d945-148">当前仅`External/WebScheduler`使用。</span><span class="sxs-lookup"><span data-stu-id="8d945-148">Currently, only the `External/WebScheduler` is used.</span></span> <span data-ttu-id="8d945-149">WebScheduler 作为内部 Lync Server 2013 部署 web 服务部署过程的一部分进行安装。</span><span class="sxs-lookup"><span data-stu-id="8d945-149">The WebScheduler is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

<span data-ttu-id="8d945-150">`Internal/Mcx`并且`External/Mcx`是 Lync Server 2010 的累积更新中引入的移动服务的位置：11月2011。</span><span class="sxs-lookup"><span data-stu-id="8d945-150">`Internal/Mcx` and `External/Mcx` are the locations of the Mobility services, introduced in Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="8d945-151">这些参考将继续由 Lync 2010 Mobile 在所有支持的设备上使用。</span><span class="sxs-lookup"><span data-stu-id="8d945-151">These references will continue to be used by Lync 2010 Mobile on all supported devices.</span></span> <span data-ttu-id="8d945-152">Mcx 服务作为内部 Lync Server 2013 部署 web 服务部署过程的一部分进行安装。</span><span class="sxs-lookup"><span data-stu-id="8d945-152">The Mcx service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

<span data-ttu-id="8d945-153">**Internal/Ucwa**、 **External/Ucwa**和**Ucwa**为客户提供一种方法来访问统一通信 WEB 应用程序编程接口（UCWA API，或只是 Ucwa）。</span><span class="sxs-lookup"><span data-stu-id="8d945-153">**Internal/Ucwa**, **External/Ucwa** and **Ucwa** provide a means for clients to access the Unified Communications Web Application Programming Interface (UCWA API, or simply UCWA).</span></span> <span data-ttu-id="8d945-154">`Internal/Ucwa`和`External/Ucwa`虚拟目录是为未来功能增强保留的访问点，不使用。</span><span class="sxs-lookup"><span data-stu-id="8d945-154">`Internal/Ucwa` and `External/Ucwa` virtual directories are access points reserved for future feature enhancement, and are not used.</span></span> <span data-ttu-id="8d945-155">`Ucwa`虚拟目录用于 Microsoft Lync Mobile （在所有受支持的设备上引入了 Lync Server 2013）。</span><span class="sxs-lookup"><span data-stu-id="8d945-155">The `Ucwa` virtual directory is used for Microsoft Lync Mobile (introduced with Lync Server 2013) on all supported devices.</span></span> <span data-ttu-id="8d945-156">UCWA 服务作为内部 Lync Server 2013 部署 web 服务部署过程的一部分进行安装。</span><span class="sxs-lookup"><span data-stu-id="8d945-156">The UCWA service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

<span data-ttu-id="8d945-157">`Internal/XFrame`、**外部/XFrame**和**XFrame**提供对基于 UCWA 的服务器应用程序的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8d945-157">`Internal/XFrame`, **External/XFrame** and **XFrame** provide access for UCWA-based server applications.</span></span> <span data-ttu-id="8d945-158">XFrame 作为内部 Lync Server 2013 部署 web 服务部署过程的一部分进行安装。</span><span class="sxs-lookup"><span data-stu-id="8d945-158">XFrame is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

<span data-ttu-id="8d945-159">`Self`令牌是指特定于发出请求的客户端（用户响应类型）的信息。</span><span class="sxs-lookup"><span data-stu-id="8d945-159">The `Self` token refers to information specific to the client (user response type) that is making the request.</span></span> <span data-ttu-id="8d945-160">发出此请求的客户端是外部的，此自动发现参考是自动发现服务的用户部分。</span><span class="sxs-lookup"><span data-stu-id="8d945-160">The client that made this request was external, and this Autodiscover reference is to the user portion of the Autodiscover service.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8d945-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d945-161">See Also</span></span>


[<span data-ttu-id="8d945-162">Lync Server 2013 的外部用户访问组件的系统要求</span><span class="sxs-lookup"><span data-stu-id="8d945-162">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[<span data-ttu-id="8d945-163">在 Lync Server 2013 中规划自动发现</span><span class="sxs-lookup"><span data-stu-id="8d945-163">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

