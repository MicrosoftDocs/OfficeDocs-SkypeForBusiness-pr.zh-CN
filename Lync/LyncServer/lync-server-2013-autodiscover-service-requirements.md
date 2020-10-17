---
title: Lync Server 2013：自动发现服务要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5cf4a26c9f0b36cd239daabbc2538716e2bcd3c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515769"
---
# <a name="autodiscover-service-requirements-for-lync-server-2013"></a><span data-ttu-id="fac06-102">Lync Server 2013 的自动发现服务要求</span><span class="sxs-lookup"><span data-stu-id="fac06-102">Autodiscover service requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fac06-103">_**上次修改的主题：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="fac06-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="fac06-104">Microsoft Lync Server 2013 自动发现服务在控制器和前端池服务器上运行，并且在 DNS 中发布后，运行 Lync Mobile 的移动设备可以使用这些服务来查找移动服务。</span><span class="sxs-lookup"><span data-stu-id="fac06-104">The Microsoft Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by mobile devices running Lync Mobile to locate mobility services.</span></span> <span data-ttu-id="fac06-105">在运行 Lync Mobile 的移动设备可以充分利用自动发现的准备工作之前，需要在运行自动发现服务的任何控制器和前端服务器上修改证书主题备用名称列表。</span><span class="sxs-lookup"><span data-stu-id="fac06-105">Before mobile devices running Lync Mobile can take advantage of automatic discovery, you need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="fac06-106">此外，可能还必须修改证书上的供反向代理上的外部 Web 服务发布规则使用的使用者替代名称列表。</span><span class="sxs-lookup"><span data-stu-id="fac06-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="fac06-107">有关控制器、前端服务器和反向代理所需的主题替代名称条目的详细信息，请参阅规划移动性的 [Lync Server 2013 中的移动技术要求](lync-server-2013-technical-requirements-for-mobility.md) 。</span><span class="sxs-lookup"><span data-stu-id="fac06-107">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.</span></span>

<span data-ttu-id="fac06-108">有关在反向代理上利用使用者替代名称列表的决定基于您是在端口 80 还是端口 443 上发布自动发现服务：</span><span class="sxs-lookup"><span data-stu-id="fac06-108">The decision about using subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="fac06-109">**已在端口 80**     上发布如果对自动发现服务的初始查询在端口80上发生，则不需要进行证书更改。</span><span class="sxs-lookup"><span data-stu-id="fac06-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="fac06-110">这是因为运行 Lync 的移动设备将在外部端口80上访问反向代理，然后在内部将其重定向到端口8080上的控制器或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="fac06-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="fac06-111">有关详细信息，请参阅本主题中后面的“使用端口 80 的初始自动发现过程”一节。</span><span class="sxs-lookup"><span data-stu-id="fac06-111">For details, see the “Initial Autodiscover Process Using Port 80” section later in this topic.</span></span>

  - <span data-ttu-id="fac06-112">**已在端口 443**     上发布外部 web 服务发布规则所使用的证书上的 "主题备用名称" 列表必须包含*lyncdiscover. \<sipdomain\> 。*</span><span class="sxs-lookup"><span data-stu-id="fac06-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>*</span></span> <span data-ttu-id="fac06-113">组织中每个 SIP 域的条目。</span><span class="sxs-lookup"><span data-stu-id="fac06-113">entry for each SIP domain within your organization.</span></span>

<span data-ttu-id="fac06-114">使用内部证书颁发结构重新颁发证书通常是一个简单的过程，但对于 Web 服务发布规则所使用的公共证书，添加多个使用者替代名称条目的成本会很高。</span><span class="sxs-lookup"><span data-stu-id="fac06-114">Reissuing certificates using an internal certificate authority is typically a simple process but for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="fac06-115">若要解决此问题，我们支持通过端口80的初始自动发现连接，该连接随后将被重定向到控制器或前端服务器上的端口8080。</span><span class="sxs-lookup"><span data-stu-id="fac06-115">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<span data-ttu-id="fac06-116">例如，假设运行 Lync Mobile 的移动客户端配置为使用用于初始请求的 HTTP 的自动发现功能，登录到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="fac06-116">For example, assume that a mobile client running Lync Mobile is configured to sign in to Lync Server 2013 using the automatic discovery feature using HTTP for the initial request.</span></span>

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a><span data-ttu-id="fac06-117">使用端口80的移动设备的初始自动发现过程</span><span class="sxs-lookup"><span data-stu-id="fac06-117">Initial Autodiscover Process for Mobile Devices Using Port 80</span></span>

1.  <span data-ttu-id="fac06-118">运行 Lync Mobile 的移动设备使用 DNS 查找 lyncdiscover.contoso.com，其中存在 A 记录。</span><span class="sxs-lookup"><span data-stu-id="fac06-118">Mobile device running Lync Mobile looks up lyncdiscover.contoso.com using DNS, where an A record exists.</span></span>

2.  <span data-ttu-id="fac06-119">外部 DNS 将外部 web 服务的 IP 地址返回给客户端。</span><span class="sxs-lookup"><span data-stu-id="fac06-119">External DNS returns the IP address for the external web services to the client.</span></span>

3.  <span data-ttu-id="fac06-120">运行 Lync Mobile 的移动设备 http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com 向反向代理发送请求</span><span class="sxs-lookup"><span data-stu-id="fac06-120">Mobile device running Lync Mobile sends request http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com to the reverse proxy</span></span>

4.  <span data-ttu-id="fac06-121">Web 发布规则将端口80的请求从外部桥接到端口8080，然后将其路由到控制器或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="fac06-121">The web publishing rule will bridge the request from port 80 externally to port 8080 internally, which will then route it to either a Director or Front End Server.</span></span>
    
    <span data-ttu-id="fac06-122">由于该请求是 HTTP 而非 HTTPS，因此，无需对外部 Web 服务发布规则上的证书进行任何修改即可支持自动发现服务。</span><span class="sxs-lookup"><span data-stu-id="fac06-122">Since the request is HTTP and not HTTPS, no modifications are needed to the certificate on the external web service publishing rule to support the Autodiscover Service.</span></span>

5.  <span data-ttu-id="fac06-123">自动发现服务会返回外部 Web 服务 URL（采用 HTTPS 格式）。</span><span class="sxs-lookup"><span data-stu-id="fac06-123">The Autodiscover Service returns the external web service URLs (in HTTPS format).</span></span>

6.  <span data-ttu-id="fac06-124">运行 Lync Mobile 的移动设备可以重新连接到端口443上的反向代理，并通过4443重定向到在用户的主池上运行的移动服务。</span><span class="sxs-lookup"><span data-stu-id="fac06-124">The mobile device running Lync Mobile can then reconnect to the reverse proxy on port 443 and is redirected over 4443 to the mobility service running on the user’s home pool.</span></span>
    
    <span data-ttu-id="fac06-125">鉴于 HTTPS 查询是针对外部 Web 服务 URL 和自动发现服务 URL 的，因此操作会成功，原因是证书已经包含外部 Web 服务完全限定域名 (FQDN) 的使用者替代名称条目。</span><span class="sxs-lookup"><span data-stu-id="fac06-125">Since the HTTPS query is to the external web services URL vs. the Autodiscover Service URL, it succeeds because the certificate will already contain subject alternative name entries for the external web services fully qualified domain names (FQDNs).</span></span>
    
    <span data-ttu-id="fac06-126">在此方案中，不需要进行任何证书更改即可支持移动。</span><span class="sxs-lookup"><span data-stu-id="fac06-126">In this scenario, there are no certificate changes required to support mobility.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fac06-127">如果目标 Web 服务器的证书未包含针对 lyncdiscover.contoso.com 的作为使用者替代名称列表值的匹配值：</span><span class="sxs-lookup"><span data-stu-id="fac06-127">If the target web server has a certificate that does not have a matching value for lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="fac06-128">a。 &nbsp; &nbsp; &nbsp;Web 服务器使用 "服务器 Hello" 进行响应，无证书。</span><span class="sxs-lookup"><span data-stu-id="fac06-128">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server Hello” and no certificate.</span></span><BR><span data-ttu-id="fac06-129">b。 &nbsp; &nbsp; &nbsp;运行 Lync Mobile 的移动设备将立即终止会话。</span><span class="sxs-lookup"><span data-stu-id="fac06-129">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile immediately terminates the session.</span></span><BR><span data-ttu-id="fac06-130">如果目标 Web 服务器的证书包含 lyncdiscover.contoso.com 作为使用者替代名称列表值：</span><span class="sxs-lookup"><span data-stu-id="fac06-130">If the target web server has a certificate that includes lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="fac06-131">a。 &nbsp; &nbsp; &nbsp;Web 服务器使用 "服务器 hello" 和证书进行响应。</span><span class="sxs-lookup"><span data-stu-id="fac06-131">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server hello” and a certificate.</span></span><BR><span data-ttu-id="fac06-132">b。 &nbsp; &nbsp; &nbsp;运行 Lync Mobile 的移动设备将验证证书并完成握手。</span><span class="sxs-lookup"><span data-stu-id="fac06-132">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile validates the certificate and completes the handshake.</span></span>

    
    </div>

<span data-ttu-id="fac06-133">若要支持在反向代理服务器上使用端口 80 与自动发现服务进行初始连接，您可以创建一个类似于此 Forefront Threat Management Gateway 2010 反向代理 Web 发布规则示例的 http 发布规则：</span><span class="sxs-lookup"><span data-stu-id="fac06-133">To support an initial connection to the Autodiscover Service using port 80 on your reverse proxy server, you can create an http publishing rule similar to this example for a Forefront Threat Management Gateway 2010 reverse proxy web publishing rule:</span></span>

1.  <span data-ttu-id="fac06-134">创建新的 Web 发布规则（例如，**Lync Server Autodiscover (HTTP)**）。</span><span class="sxs-lookup"><span data-stu-id="fac06-134">Create a new web publishing rule (for example, **Lync Server Autodiscover (HTTP)**).</span></span>

2.  <span data-ttu-id="fac06-135">在“公共名称”\*\*\*\* 中，输入 lyncdiscover.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="fac06-135">In **Public Name**, enter lyncdiscover.contoso.com.</span></span>

3.  <span data-ttu-id="fac06-136">在“桥接”\*\*\*\* 选项卡上，仅选择用于将请求从端口 80 桥接到端口 8080 的选项。</span><span class="sxs-lookup"><span data-stu-id="fac06-136">On the **Bridging** tab, select only the option to bridge requests from Port 80 to Port 8080.</span></span>

4.  <span data-ttu-id="fac06-137">在“身份验证”\*\*\*\* 选项卡上，选择“无身份验证”\*\*\*\* 和“客户端无法直接进行身份验证”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fac06-137">On the **Authentication** tab, select **No authentication**, and **Client cannot authenticate directly**.</span></span>

5.  <span data-ttu-id="fac06-138">提交更改，并将规则移动到 Lync 规则列表的顶部， (在处理顺序) 中先进行。</span><span class="sxs-lookup"><span data-stu-id="fac06-138">Commit changes, and move the rule to the top of the list of Lync rules (first in processing order).</span></span>

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="fac06-139">拆分域部署的移动性</span><span class="sxs-lookup"><span data-stu-id="fac06-139">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="fac06-140">共享 SIP 地址空间也称为*拆分域* 或*混合部署*，它是一种跨内部部署和在线环境部署用户的配置。</span><span class="sxs-lookup"><span data-stu-id="fac06-140">A shared SIP address space, also known as a *split-domain*, or a *hybrid deployment* is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="fac06-141">期望的结果是无论用户的主服务器位于何处（内部部署还是在线），用户都能登录到部署并被重定向到其主服务器位置。</span><span class="sxs-lookup"><span data-stu-id="fac06-141">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), to log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="fac06-142">为实现此目的，Microsoft Lync Server 2013 的自动发现功能用于将联机用户重定向到联机拓扑。</span><span class="sxs-lookup"><span data-stu-id="fac06-142">To accomplish this, the Autodiscover feature of Microsoft Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="fac06-143">为此，请使用 Lync Server 命令行管理程序和 cmdlet **CsHostingProvider** And **CsHostingProvider 将**自动发现统一资源定位器配置 (URL) 。</span><span class="sxs-lookup"><span data-stu-id="fac06-143">This is done by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell and the cmdlets **Get-CsHostingProvider** and **Set-CsHostingProvider**.</span></span>

<span data-ttu-id="fac06-144">您需要收集和记录下列部署的属性：</span><span class="sxs-lookup"><span data-stu-id="fac06-144">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="fac06-145">在 Lync Server 命令行管理程序中，键入</span><span class="sxs-lookup"><span data-stu-id="fac06-145">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="fac06-p106">在结果中，查找具有属性 **ProxyFQDN** 的在线提供商。例如，sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="fac06-p106">In the results, find the online provider with the attribute **ProxyFQDN**. For example, sipfed.online.lync.com</span></span>

  - <span data-ttu-id="fac06-148">记录 ProxyFQDN 的值</span><span class="sxs-lookup"><span data-stu-id="fac06-148">Record the value of the ProxyFQDN</span></span>

  - <span data-ttu-id="fac06-149">在内部部署 Lync Server 控制面板中启用联合，以允许与联机提供程序进行联盟</span><span class="sxs-lookup"><span data-stu-id="fac06-149">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider</span></span>

  - <span data-ttu-id="fac06-p107">为在线提供商启用联盟。默认情况下，对所有在线用户启用域联盟，因此在线用户可以与所有域通信</span><span class="sxs-lookup"><span data-stu-id="fac06-p107">Enable federation for the online provider. By default, all online users are enabled for domain federation and can communicate with all domains</span></span>

  - <span data-ttu-id="fac06-152">如果要定义阻止域和允许域，请确定要明确允许或阻止的域</span><span class="sxs-lookup"><span data-stu-id="fac06-152">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block</span></span>

  - <span data-ttu-id="fac06-153">对于在线联盟，您必须规划防火墙例外、证书和 DNS 主机（如使用 IPv6，则为 A 或 AAAA）记录。</span><span class="sxs-lookup"><span data-stu-id="fac06-153">For online federation, you must plan for firewall exceptions, certificates and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="fac06-154">此外，您还必须配置联盟策略。</span><span class="sxs-lookup"><span data-stu-id="fac06-154">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="fac06-155">有关详细信息，请参阅 [规划 Lync Server 2013 和 Office 通信服务器联合身份验证](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="fac06-155">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

