---
title: Lync Server 2013：更改 Web 服务 URL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 934e448f48413df2938deab8a0d08389cfad37bd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a><span data-ttu-id="d2ff4-102">在 Lync Server 2013 中更改 Web 服务 URL</span><span class="sxs-lookup"><span data-stu-id="d2ff4-102">Change the Web Services URL in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2ff4-103">_**主题上次修改时间：** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="d2ff4-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="d2ff4-104">设置前端池和标准版服务器时，可以选择配置外部 Web 场完全限定的域名（FQDN）和关联的端口。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-104">When you set up your Front End pools and Standard Edition servers, you have the option to configure an external Web farm fully qualified domain name (FQDN) and associated ports.</span></span> <span data-ttu-id="d2ff4-105">如果您运行 Lync Server 部署向导时未配置此 URL，则需要手动配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-105">If you did not configure this URL when you ran the Lync Server Deployment Wizard, you need to manually configure these settings.</span></span> <span data-ttu-id="d2ff4-106">管理员通常不需要修改这些设置，因为它们是推荐的和默认的端口。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-106">An administrator typically does not need to modify these settings, as these are the recommended and default ports.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d2ff4-107">配置标准版服务器时，将会执行以下屏幕截图，因此将禁用替代 FQDN 选项。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-107">The following screen shot was taken while configuring a Standard Edition server, so the Override FQDN option is disabled.</span></span> <span data-ttu-id="d2ff4-108">在前端池中配置企业版服务器时，将启用该选项。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-108">That option is enabled when configuring an Enterprise Edition server in a Front End pool.</span></span>



</div>

<span data-ttu-id="d2ff4-109">![编辑 Web 服务池设置](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "编辑 Web 服务池设置")</span><span class="sxs-lookup"><span data-stu-id="d2ff4-109">![Edit Web Services Pool Settings](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Edit Web Services Pool Settings")</span></span>

<div>

## <a name="to-configure-web-services"></a><span data-ttu-id="d2ff4-110">配置 web 服务</span><span class="sxs-lookup"><span data-stu-id="d2ff4-110">To configure web services</span></span>

1.  <span data-ttu-id="d2ff4-111">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="d2ff4-112">启动拓扑生成器：单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-112">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="d2ff4-113">在拓扑生成器中，在 "**标准版前端服务器**"、"**企业版前端池**" 和 "**目录池**" 下的控制台树中，选择 "池名称"。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-113">In Topology Builder, in the console tree under **Standard Edition Front End Servers**, **Enterprise Edition Front End pools**, and **Directory pools**, select the pool name.</span></span> <span data-ttu-id="d2ff4-114">右键单击该名称，单击 "**编辑属性**"，然后单击 " **Web 服务**"。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-114">Right-click the name, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="d2ff4-115">添加或编辑**外部 Web 服务 FQDN**，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-115">Add or edit the **External Web Services FQDN**, and then click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d2ff4-116">如果您有多个前端池或前端服务器，则外部 Web 服务 FQDN 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-116">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="d2ff4-117">例如，如果你将前端服务器的外部 Web 服务 FQDN 定义为<STRONG>pool01.contoso.com</STRONG>，则不能将<STRONG>Pool01.contoso.com</STRONG>用于其他前端池或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-117">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="d2ff4-118">如果你还部署控制器，则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须是任何其他 Director 或控制器池以及任何前端池或前端服务器的唯一。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-118">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="d2ff4-119">验证是否为你的环境正确配置了侦听和已发布端口。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-119">Verify the listening and published ports are configured correctly for your environment.</span></span>

6.  <span data-ttu-id="d2ff4-120">对你的环境中的所有标准版服务器、前端池和控制器池重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-120">Repeat these steps for all Standard Edition servers, Front End Pools, and Director pools in your environment.</span></span>

7.  <span data-ttu-id="d2ff4-121">在控制台树中，单击 " **Lync Server 2013**"，然后在 "**操作**" 窗格中，单击 "**发布拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-121">In the console tree, click **Lync Server 2013**, and then, in the **Actions** pane, click **Publish Topology**.</span></span>

<span data-ttu-id="d2ff4-122">配置侦听和发布端口时，应注意以下几点要求：</span><span class="sxs-lookup"><span data-stu-id="d2ff4-122">There are a few requirements you should be aware of when configuring the Listening and Publishing ports:</span></span>

  - <span data-ttu-id="d2ff4-123">所示的侦听端口是针对每台前端服务器上的 Internet 信息服务器（IIS）配置的端口。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-123">The listening ports shown are the ports that are configured for Internet Information Server (IIS) on each Front End Server.</span></span>

  - <span data-ttu-id="d2ff4-124">对于 IIS，内部和外部侦听端口必须不同。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-124">The internal and external listening ports must be different for IIS.</span></span> <span data-ttu-id="d2ff4-125">对于外部侦听端口，这些端口通常是相同的，因为一个表示内部 web 流量的硬件负载平衡器，另一个表示用于外部 web 流量的反向代理服务器。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-125">For the external listening ports, these are typically the same because one represents the hardware load balancer for internal web traffic and one represents the reverse proxy server for external web traffic.</span></span>

  - <span data-ttu-id="d2ff4-126">你可以替代前端池、Director 或控制器池上的内部 web 服务，并定义自己的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-126">You can override the Internal web services on a Front End pool, Director or a Director pool and define your own FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d2ff4-127">如果你决定使用自定义的 FQDN 替代内部 web 服务，则每个 FQDN 都必须与任何其他前端池、Director 或控制器池唯一。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-127">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

  - <span data-ttu-id="d2ff4-128">必须在反向代理或硬件负载平衡器上将已发布的端口配置为侦听端口。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-128">The published ports must be configured on the reverse proxy or hardware load balancer as listening ports.</span></span>

  - <span data-ttu-id="d2ff4-129">对于前端池（在示例中未显示），内部 SIP 池 FQDN 必须与内部 web 服务 FQDN 不同，因为 web 流量通过硬件负载平衡器，并且内部 SIP 池流量通过 DNS 负载平衡器进行传输.</span><span class="sxs-lookup"><span data-stu-id="d2ff4-129">For an Front End pool (not shown in the example), the internal SIP pool FQDN must be different from the internal web services FQDN, because web traffic comes through the hardware load balancer and the internal SIP pool traffic travels comes through the DNS load balancer.</span></span> <span data-ttu-id="d2ff4-130">必须满足此要求。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-130">This requirement must be met.</span></span>

  - <span data-ttu-id="d2ff4-131">Lync Server 标准版部署不需要或允许覆盖内部 web 服务 FQDN，因为此服务器无法进行负载平衡。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-131">A Lync Server Standard Edition deployment does not need or allow an internal web services FQDN to be overridden because this server cannot be load balanced.</span></span>

  - <span data-ttu-id="d2ff4-132">如果你的环境中有一个硬件负载平衡器，用于内部 SIP 和 web 流量，拓扑生成器将无法进行区分。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-132">If you have a hardware load balancer in your environment that you use for both internal SIP and web traffic, the Topology Builder cannot make the distinction.</span></span>
    
    <span data-ttu-id="d2ff4-133">Web 服务 Fqdn 应该易于区分;这有助于确保 URL 重定向将客户定向到相应的服务器。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-133">Web service FQDNs should be easily-differentiated from one another; that helps to ensure that URL redirection points clients towards the appropriate server.</span></span> <span data-ttu-id="d2ff4-134">例如，如果您有两个 Fqdn，则可以考虑为一个 meeting.contoso.com 和另一个 conferencing.contoso.com 命名。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-134">For example, if you have two FQDNs you might consider naming one meeting.contoso.com and the other conferencing.contoso.com.</span></span> <span data-ttu-id="d2ff4-135">如果你的 Fqdn 具有更相似的名称，例如 meet1.contoso.com 和 meet2.contoso.com，则可能会遇到重定向问题。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-135">You could potentially run into redirection issues if you have FQDNs with more similar names, such as meet1.contoso.com and meet2.contoso.com.</span></span>

<span data-ttu-id="d2ff4-136">外部 web 服务与外围网络中的反向代理协同工作。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-136">The external web services works in conjunction with a reverse proxy in the perimeter network.</span></span> <span data-ttu-id="d2ff4-137">它通过使用这些 web 服务向客户提供对外部访问的访问权限。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-137">It provides clients external access to by using these web services.</span></span> <span data-ttu-id="d2ff4-138">此处配置的 Fqdn 将在客户端登录时发送到客户端，并用于在远程连接时将 HTTPS 连接回反向代理。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-138">The FQDNs configured here are sent to clients when they log on, and are used to make an HTTPS connection back to the reverse proxy when connecting remotely.</span></span> <span data-ttu-id="d2ff4-139">反向代理服务器将外部 web 服务 FQDN 转发到内部硬件负载平衡器，或直接转发到池。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-139">The reverse-proxy server forwards the external web service FQDN to an internal hardware load balancer, or directly to the pool.</span></span> <span data-ttu-id="d2ff4-140">反向代理必须能够将外部 web 服务 FQDN 解析为内部 Web 服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-140">The reverse proxy must be able to resolve the external web services FQDN to the IP address of the internal Web server.</span></span> <span data-ttu-id="d2ff4-141">外部 web 服务 FDQN 必须可在公共 Internet 中解析。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-141">The external web services FDQN must be resolvable in the public Internet.</span></span>

<span data-ttu-id="d2ff4-142">如果内部服务器是标准版服务器，则内部 FQDN 是标准版服务器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-142">If your internal server is a Standard Edition server, the internal FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="d2ff4-143">如果内部服务器是一个前端池，则 FQDN 是一个硬件负载平衡器虚拟 IP （VIP），用于加载内部 web 场服务器的平衡。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-143">If your internal server is a Front End pool, the FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="d2ff4-144">在具有多个企业版服务器的前端池中需要硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-144">A hardware load balancer is required in a Front End pool with more than one Enterprise Edition server.</span></span> <span data-ttu-id="d2ff4-145">标准版服务器或单个企业版前端服务器不需要负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="d2ff4-145">A load balancer is not required for a Standard Edition server or a single Enterprise Edition Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

