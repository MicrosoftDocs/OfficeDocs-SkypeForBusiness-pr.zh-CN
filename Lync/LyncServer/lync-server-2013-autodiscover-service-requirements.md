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
ms.openlocfilehash: 777d70b20a51e5408fe9d9248028c3dbcaebeba2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a><span data-ttu-id="73502-102">Lync Server 2013 的自动发现服务要求</span><span class="sxs-lookup"><span data-stu-id="73502-102">Autodiscover service requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73502-103">_**主题上次修改时间：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="73502-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="73502-104">Microsoft Lync Server 2013 自动发现服务在 Director 和前端池服务器上运行，并且当在 DNS 中发布时，可以由运行 Lync Mobile 的移动设备使用，以找到移动服务。</span><span class="sxs-lookup"><span data-stu-id="73502-104">The Microsoft Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by mobile devices running Lync Mobile to locate mobility services.</span></span> <span data-ttu-id="73502-105">在运行 Lync Mobile 的移动设备可以充分利用自动发现之前，你需要在运行自动发现服务的任何控制器和前端服务器上修改证书主题备用名称列表。</span><span class="sxs-lookup"><span data-stu-id="73502-105">Before mobile devices running Lync Mobile can take advantage of automatic discovery, you need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="73502-106">此外，可能还需要修改用于反向代理上的外部 web 服务发布规则的证书上的使用者备用名称列表。</span><span class="sxs-lookup"><span data-stu-id="73502-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="73502-107">有关董事、前端服务器和反向代理所需的主题备用名称条目的详细信息，请参阅规划移动性的[Lync Server 2013 中的移动技术要求](lync-server-2013-technical-requirements-for-mobility.md)。</span><span class="sxs-lookup"><span data-stu-id="73502-107">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.</span></span>

<span data-ttu-id="73502-108">在反向代理上使用主题备用名称列表的决策取决于你是在端口80上还是在端口443上发布自动发现服务：</span><span class="sxs-lookup"><span data-stu-id="73502-108">The decision about using subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="73502-109">**已在端口 80**   上发布如果自动发现服务的初始查询通过端口80进行，则不需要进行证书更改。</span><span class="sxs-lookup"><span data-stu-id="73502-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="73502-110">这是因为运行 Lync 的移动设备将外部访问端口80上的反向代理，然后在内部将其重定向到端口8080上的 Director 或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="73502-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="73502-111">有关详细信息，请参阅本主题后面的 "使用端口80的初始自动发现过程" 部分。</span><span class="sxs-lookup"><span data-stu-id="73502-111">For details, see the “Initial Autodiscover Process Using Port 80” section later in this topic.</span></span>

  - <span data-ttu-id="73502-112">**在端口 443**   上发布在外部 web 服务发布规则使用的证书上的 "主题" 备用名称列表中必须包含\*lyncdiscover。\<组织\> \*中每个 SIP 域的 sipdomain 条目。</span><span class="sxs-lookup"><span data-stu-id="73502-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>

<span data-ttu-id="73502-113">使用内部证书颁发机构重新发起证书通常是一个简单的过程，但对于 web 服务发布规则中使用的公共证书，添加多个主题可选名称条目可能会很高。</span><span class="sxs-lookup"><span data-stu-id="73502-113">Reissuing certificates using an internal certificate authority is typically a simple process but for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="73502-114">若要解决此问题，我们通过端口80支持初始自动发现连接，该连接随后将被重定向到 Director 或前端服务器上的端口8080。</span><span class="sxs-lookup"><span data-stu-id="73502-114">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<span data-ttu-id="73502-115">例如，假设运行 Lync Mobile 的移动客户端配置为使用用于初始请求的 HTTP 的自动发现功能登录 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="73502-115">For example, assume that a mobile client running Lync Mobile is configured to sign in to Lync Server 2013 using the automatic discovery feature using HTTP for the initial request.</span></span>

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a><span data-ttu-id="73502-116">使用端口80的移动设备初始自动发现过程</span><span class="sxs-lookup"><span data-stu-id="73502-116">Initial Autodiscover Process for Mobile Devices Using Port 80</span></span>

1.  <span data-ttu-id="73502-117">运行 Lync Mobile 的移动设备使用 DNS 查找 lyncdiscover.contoso.com，其中存在 A 记录。</span><span class="sxs-lookup"><span data-stu-id="73502-117">Mobile device running Lync Mobile looks up lyncdiscover.contoso.com using DNS, where an A record exists.</span></span>

2.  <span data-ttu-id="73502-118">外部 DNS 将外部 web 服务的 IP 地址返回给客户端。</span><span class="sxs-lookup"><span data-stu-id="73502-118">External DNS returns the IP address for the external web services to the client.</span></span>

3.  <span data-ttu-id="73502-119">运行 Lync Mobile 的移动设备将http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com请求发送到反向代理</span><span class="sxs-lookup"><span data-stu-id="73502-119">Mobile device running Lync Mobile sends request http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com to the reverse proxy</span></span>

4.  <span data-ttu-id="73502-120">Web 发布规则将从外部端口80到内部端口8080的请求桥接该请求，然后将其路由到 Director 或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="73502-120">The web publishing rule will bridge the request from port 80 externally to port 8080 internally, which will then route it to either a Director or Front End Server.</span></span>
    
    <span data-ttu-id="73502-121">由于请求是 HTTP 而不是 HTTPS，因此外部 web 服务发布规则上的证书不需要修改即可支持自动发现服务。</span><span class="sxs-lookup"><span data-stu-id="73502-121">Since the request is HTTP and not HTTPS, no modifications are needed to the certificate on the external web service publishing rule to support the Autodiscover Service.</span></span>

5.  <span data-ttu-id="73502-122">自动发现服务返回外部 web 服务 Url （采用 HTTPS 格式）。</span><span class="sxs-lookup"><span data-stu-id="73502-122">The Autodiscover Service returns the external web service URLs (in HTTPS format).</span></span>

6.  <span data-ttu-id="73502-123">运行 Lync Mobile 的移动设备可以重新连接到端口443上的反向代理，并通过4443重定向到在用户的主池中运行的移动服务。</span><span class="sxs-lookup"><span data-stu-id="73502-123">The mobile device running Lync Mobile can then reconnect to the reverse proxy on port 443 and is redirected over 4443 to the mobility service running on the user’s home pool.</span></span>
    
    <span data-ttu-id="73502-124">由于 HTTPS 查询指向外部 web 服务 URL 而不是自动发现服务 URL，因此它将成功，因为该证书将已包含外部 web 服务完全限定的域名（Fqdn）的主题备用名称条目。</span><span class="sxs-lookup"><span data-stu-id="73502-124">Since the HTTPS query is to the external web services URL vs. the Autodiscover Service URL, it succeeds because the certificate will already contain subject alternative name entries for the external web services fully qualified domain names (FQDNs).</span></span>
    
    <span data-ttu-id="73502-125">在此方案中，无需更改任何证书来支持移动性。</span><span class="sxs-lookup"><span data-stu-id="73502-125">In this scenario, there are no certificate changes required to support mobility.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="73502-126">如果目标 web 服务器具有的证书与 lyncdiscover.contoso.com 的匹配值不是 "主题备用名称" 列表值，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="73502-126">If the target web server has a certificate that does not have a matching value for lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="73502-127">a.&nbsp;&nbsp;&nbsp;Web 服务器使用 "服务器 Hello" 响应，没有证书。</span><span class="sxs-lookup"><span data-stu-id="73502-127">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server Hello” and no certificate.</span></span><BR><span data-ttu-id="73502-128">b. 运行 Lync Mobile 的&nbsp;移动设备立即终止会话。&nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="73502-128">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile immediately terminates the session.</span></span><BR><span data-ttu-id="73502-129">如果目标 web 服务器的证书包含 lyncdiscover.contoso.com 作为主题备用名称列表值，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="73502-129">If the target web server has a certificate that includes lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="73502-130">a.&nbsp;&nbsp;&nbsp;Web 服务器使用 "服务器 hello" 和证书进行响应。</span><span class="sxs-lookup"><span data-stu-id="73502-130">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server hello” and a certificate.</span></span><BR><span data-ttu-id="73502-131">b. 运行 Lync Mobile 的&nbsp;移动设备将验证证书并完成握手。&nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="73502-131">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile validates the certificate and completes the handshake.</span></span>

    
    </div>

<span data-ttu-id="73502-132">若要支持使用反向代理服务器上的端口80的自动发现服务的初始连接，你可以创建类似于 Forefront 威胁管理网关的 http 发布规则2010反向代理 web 发布规则：</span><span class="sxs-lookup"><span data-stu-id="73502-132">To support an initial connection to the Autodiscover Service using port 80 on your reverse proxy server, you can create an http publishing rule similar to this example for a Forefront Threat Management Gateway 2010 reverse proxy web publishing rule:</span></span>

1.  <span data-ttu-id="73502-133">创建新的 web 发布规则（例如， **Lync Server 自动发现（HTTP）**）。</span><span class="sxs-lookup"><span data-stu-id="73502-133">Create a new web publishing rule (for example, **Lync Server Autodiscover (HTTP)**).</span></span>

2.  <span data-ttu-id="73502-134">在 "**公共名称**" 中，输入 lyncdiscover.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="73502-134">In **Public Name**, enter lyncdiscover.contoso.com.</span></span>

3.  <span data-ttu-id="73502-135">在 "**桥接**" 选项卡上，仅选择将来自端口80的请求桥接到端口8080的选项。</span><span class="sxs-lookup"><span data-stu-id="73502-135">On the **Bridging** tab, select only the option to bridge requests from Port 80 to Port 8080.</span></span>

4.  <span data-ttu-id="73502-136">在 "**身份验证**" 选项卡上，选择 "**无身份验证**"，**客户端无法直接身份验证**。</span><span class="sxs-lookup"><span data-stu-id="73502-136">On the **Authentication** tab, select **No authentication**, and **Client cannot authenticate directly**.</span></span>

5.  <span data-ttu-id="73502-137">提交更改，并将规则移动到 Lync 规则列表的顶部（首先在处理顺序中）。</span><span class="sxs-lookup"><span data-stu-id="73502-137">Commit changes, and move the rule to the top of the list of Lync rules (first in processing order).</span></span>

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="73502-138">拆分域部署的移动性</span><span class="sxs-lookup"><span data-stu-id="73502-138">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="73502-139">共享 SIP 地址空间（也称为*拆分域*）或*混合部署*是在内部部署和联机环境中部署用户的配置。</span><span class="sxs-lookup"><span data-stu-id="73502-139">A shared SIP address space, also known as a *split-domain*, or a *hybrid deployment* is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="73502-140">无论其主服务器位于何处（内部部署或联机），所需的结果是让用户登录到部署并重定向到其主服务器位置。</span><span class="sxs-lookup"><span data-stu-id="73502-140">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), to log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="73502-141">为了实现此目的，Microsoft Lync Server 2013 的自动发现功能用于将联机用户重定向到联机拓扑。</span><span class="sxs-lookup"><span data-stu-id="73502-141">To accomplish this, the Autodiscover feature of Microsoft Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="73502-142">通过使用 Lync Server 命令行管理程序和 cmdlet **CsHostingProvider**和**Set-CsHostingProvider**配置自动发现统一资源定位器（URL）来实现此操作。</span><span class="sxs-lookup"><span data-stu-id="73502-142">This is done by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell and the cmdlets **Get-CsHostingProvider** and **Set-CsHostingProvider**.</span></span>

<span data-ttu-id="73502-143">你将需要收集和记录以下已部署的属性：</span><span class="sxs-lookup"><span data-stu-id="73502-143">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="73502-144">从 Lync Server 命令行管理程序中，键入</span><span class="sxs-lookup"><span data-stu-id="73502-144">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="73502-145">在结果中，查找具有属性**ProxyFQDN**的联机提供程序。</span><span class="sxs-lookup"><span data-stu-id="73502-145">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="73502-146">例如，sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="73502-146">For example, sipfed.online.lync.com</span></span>

  - <span data-ttu-id="73502-147">记录 ProxyFQDN 的值</span><span class="sxs-lookup"><span data-stu-id="73502-147">Record the value of the ProxyFQDN</span></span>

  - <span data-ttu-id="73502-148">在本地 Lync Server "控制面板" 中启用联盟，允许与联机提供商进行联盟</span><span class="sxs-lookup"><span data-stu-id="73502-148">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider</span></span>

  - <span data-ttu-id="73502-149">为联机提供程序启用联盟。</span><span class="sxs-lookup"><span data-stu-id="73502-149">Enable federation for the online provider.</span></span> <span data-ttu-id="73502-150">默认情况下，所有联机用户都启用了域联盟，并且可以与所有域进行通信</span><span class="sxs-lookup"><span data-stu-id="73502-150">By default, all online users are enabled for domain federation and can communicate with all domains</span></span>

  - <span data-ttu-id="73502-151">如果你要定义阻止的域和允许的域，请确定你将明确允许或显式阻止的域</span><span class="sxs-lookup"><span data-stu-id="73502-151">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block</span></span>

  - <span data-ttu-id="73502-152">对于联机联盟，你必须为防火墙例外、证书和 DNS 主机（如果使用 IPv6）记录制定计划。</span><span class="sxs-lookup"><span data-stu-id="73502-152">For online federation, you must plan for firewall exceptions, certificates and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="73502-153">此外，必须配置联合身份验证策略。</span><span class="sxs-lookup"><span data-stu-id="73502-153">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="73502-154">有关详细信息，请参阅[规划 Lync Server 2013 和 Office 通信服务器联合](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="73502-154">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

