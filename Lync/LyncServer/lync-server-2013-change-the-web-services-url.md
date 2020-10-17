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
ms.openlocfilehash: 9eb2922913ee95bad11273b2e943812850da4402
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517810"
---
# <a name="change-the-web-services-url-in-lync-server-2013"></a><span data-ttu-id="c0667-102">在 Lync Server 2013 中更改 Web 服务 URL</span><span class="sxs-lookup"><span data-stu-id="c0667-102">Change the Web Services URL in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0667-103">_**上次修改的主题：** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="c0667-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="c0667-104">设置前端池和 Standard Edition Server 时，可以选择配置外部 Web 场完全限定域名 (FQDN) 和关联端口。</span><span class="sxs-lookup"><span data-stu-id="c0667-104">When you set up your Front End pools and Standard Edition servers, you have the option to configure an external Web farm fully qualified domain name (FQDN) and associated ports.</span></span> <span data-ttu-id="c0667-105">如果您在运行 Lync Server 部署向导时未配置此 URL，则需要手动配置这些设置。</span><span class="sxs-lookup"><span data-stu-id="c0667-105">If you did not configure this URL when you ran the Lync Server Deployment Wizard, you need to manually configure these settings.</span></span> <span data-ttu-id="c0667-106">通常，管理员不需要修改这些设置，因为这些是建议的默认端口。</span><span class="sxs-lookup"><span data-stu-id="c0667-106">An administrator typically does not need to modify these settings, as these are the recommended and default ports.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c0667-107">配置 Standard Edition server 时采用了以下屏幕截图，因此禁用了替代 FQDN 选项。</span><span class="sxs-lookup"><span data-stu-id="c0667-107">The following screen shot was taken while configuring a Standard Edition server, so the Override FQDN option is disabled.</span></span> <span data-ttu-id="c0667-108">在前端池中配置 Enterprise Edition 服务器时，将启用该选项。</span><span class="sxs-lookup"><span data-stu-id="c0667-108">That option is enabled when configuring an Enterprise Edition server in a Front End pool.</span></span>



</div>

<span data-ttu-id="c0667-109">![编辑 Web 服务池设置](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "编辑 Web 服务池设置")</span><span class="sxs-lookup"><span data-stu-id="c0667-109">![Edit Web Services Pool Settings](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Edit Web Services Pool Settings")</span></span>

<div>

## <a name="to-configure-web-services"></a><span data-ttu-id="c0667-110">配置 web 服务</span><span class="sxs-lookup"><span data-stu-id="c0667-110">To configure web services</span></span>

1.  <span data-ttu-id="c0667-111">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="c0667-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="c0667-112">启动拓扑生成器：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="c0667-112">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="c0667-113">在拓扑生成器中，在 " **Standard Edition 前端服务器**"、" **Enterprise edition 前端池**" 和 " **目录池**" 下的控制台树中，选择池名称。</span><span class="sxs-lookup"><span data-stu-id="c0667-113">In Topology Builder, in the console tree under **Standard Edition Front End Servers**, **Enterprise Edition Front End pools**, and **Directory pools**, select the pool name.</span></span> <span data-ttu-id="c0667-114">右键单击该名称，再单击“编辑属性”\*\*\*\*，然后单击“Web 服务”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c0667-114">Right-click the name, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="c0667-115">添加或编辑“外部 Web 服务 FQDN”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c0667-115">Add or edit the **External Web Services FQDN**, and then click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="c0667-116">如果您有多个前端池或前端服务器，则外部 Web 服务 FQDN 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c0667-116">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="c0667-117">例如，如果将前端服务器的外部 Web 服务 FQDN 定义为 <STRONG>pool01.contoso.com</STRONG>，则不能将 <STRONG>pool01.contoso.com</STRONG> 用于另一个前端池或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="c0667-117">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="c0667-118">如果还部署控制器，则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须与任何其他控制器或控制器池以及任何前端池或前端服务器都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c0667-118">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="c0667-119">验证是否已为环境正确配置侦听端口和已发布端口。</span><span class="sxs-lookup"><span data-stu-id="c0667-119">Verify the listening and published ports are configured correctly for your environment.</span></span>

6.  <span data-ttu-id="c0667-120">对环境中的所有 Standard Edition Server、前端池和控制器池重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="c0667-120">Repeat these steps for all Standard Edition servers, Front End Pools, and Director pools in your environment.</span></span>

7.  <span data-ttu-id="c0667-121">在控制台树中，单击“Lync Server 2013”\*\*\*\*，然后在“操作”\*\*\*\* 窗格中，单击“发布拓扑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c0667-121">In the console tree, click **Lync Server 2013**, and then, in the **Actions** pane, click **Publish Topology**.</span></span>

<span data-ttu-id="c0667-122">配置侦听端口和发布端口时，应了解以下要求：</span><span class="sxs-lookup"><span data-stu-id="c0667-122">There are a few requirements you should be aware of when configuring the Listening and Publishing ports:</span></span>

  - <span data-ttu-id="c0667-123">显示的侦听端口是为每台前端服务器上的 Internet Information Server (IIS) 配置的端口。</span><span class="sxs-lookup"><span data-stu-id="c0667-123">The listening ports shown are the ports that are configured for Internet Information Server (IIS) on each Front End Server.</span></span>

  - <span data-ttu-id="c0667-p105">IIS 的内部侦听端口和外部侦听端口必须不同。外部侦听端口通常是相同的，因为一个代表内部 Web 流量的硬件负载平衡器，一个代表外部 Web 流量的反向代理服务器。</span><span class="sxs-lookup"><span data-stu-id="c0667-p105">The internal and external listening ports must be different for IIS. For the external listening ports, these are typically the same because one represents the hardware load balancer for internal web traffic and one represents the reverse proxy server for external web traffic.</span></span>

  - <span data-ttu-id="c0667-126">您可以重写前端池、控制器或控制器池上的内部 web 服务，并定义自己的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c0667-126">You can override the Internal web services on a Front End pool, Director or a Director pool and define your own FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="c0667-127">如果决定使用自定义的 FQDN 覆盖内部 web 服务，则每个 FQDN 必须与任何其他前端池、控制器或控制器池都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c0667-127">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

  - <span data-ttu-id="c0667-128">必须在反向代理或硬件负载平衡器上将已发布端口配置为侦听端口。</span><span class="sxs-lookup"><span data-stu-id="c0667-128">The published ports must be configured on the reverse proxy or hardware load balancer as listening ports.</span></span>

  - <span data-ttu-id="c0667-p106">对于前端池（未在示例中显示），内部 SIP 池 FQDN 必须与内部 Web 服务 FQDN 不同，这是因为 Web 流量通过硬件负载平衡器进行传输，而内部 SIP 池流量通过 DNS 负载平衡器进行传输。必须满足此要求。</span><span class="sxs-lookup"><span data-stu-id="c0667-p106">For an Front End pool (not shown in the example), the internal SIP pool FQDN must be different from the internal web services FQDN, because web traffic comes through the hardware load balancer and the internal SIP pool traffic travels comes through the DNS load balancer. This requirement must be met.</span></span>

  - <span data-ttu-id="c0667-131">Lync Server Standard Edition 部署不需要或允许覆盖内部 web 服务 FQDN，因为无法对此服务器进行负载平衡。</span><span class="sxs-lookup"><span data-stu-id="c0667-131">A Lync Server Standard Edition deployment does not need or allow an internal web services FQDN to be overridden because this server cannot be load balanced.</span></span>

  - <span data-ttu-id="c0667-132">如果你的环境中具有用于内部 SIP 和 web 流量的硬件负载平衡器，则拓扑生成器无法进行区分。</span><span class="sxs-lookup"><span data-stu-id="c0667-132">If you have a hardware load balancer in your environment that you use for both internal SIP and web traffic, the Topology Builder cannot make the distinction.</span></span>
    
    <span data-ttu-id="c0667-133">Web 服务 Fqdn 应易于区分; 而不是另一个。这有助于确保 URL 重定向将客户定向到适当的服务器。</span><span class="sxs-lookup"><span data-stu-id="c0667-133">Web service FQDNs should be easily-differentiated from one another; that helps to ensure that URL redirection points clients towards the appropriate server.</span></span> <span data-ttu-id="c0667-134">例如，如果您有两个 Fqdn，则可以考虑为一个 meeting.contoso.com 和另一个 conferencing.contoso.com 命名。</span><span class="sxs-lookup"><span data-stu-id="c0667-134">For example, if you have two FQDNs you might consider naming one meeting.contoso.com and the other conferencing.contoso.com.</span></span> <span data-ttu-id="c0667-135">如果您的 Fqdn 具有更相似的名称（如 meet1.contoso.com 和 meet2.contoso.com），则可能会遇到重定向问题。</span><span class="sxs-lookup"><span data-stu-id="c0667-135">You could potentially run into redirection issues if you have FQDNs with more similar names, such as meet1.contoso.com and meet2.contoso.com.</span></span>

<span data-ttu-id="c0667-136">在外围网络中，外部 Web 服务与反向代理结合使用。</span><span class="sxs-lookup"><span data-stu-id="c0667-136">The external web services works in conjunction with a reverse proxy in the perimeter network.</span></span> <span data-ttu-id="c0667-137">它通过使用这些 web 服务向客户端提供对外部的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c0667-137">It provides clients external access to by using these web services.</span></span> <span data-ttu-id="c0667-138">此处配置的 FQDN 会在客户端登录时发送到客户端，并在远程连接时用于建立与反向代理的 HTTPS 连接。</span><span class="sxs-lookup"><span data-stu-id="c0667-138">The FQDNs configured here are sent to clients when they log on, and are used to make an HTTPS connection back to the reverse proxy when connecting remotely.</span></span> <span data-ttu-id="c0667-139">反向代理服务器将外部 Web 服务 FQDN 转发到内部硬件负载平衡器或直接转发到池。</span><span class="sxs-lookup"><span data-stu-id="c0667-139">The reverse-proxy server forwards the external web service FQDN to an internal hardware load balancer, or directly to the pool.</span></span> <span data-ttu-id="c0667-140">反向代理必须能够将外部 Web 服务 FQDN 解析为内部 Web 服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c0667-140">The reverse proxy must be able to resolve the external web services FQDN to the IP address of the internal Web server.</span></span> <span data-ttu-id="c0667-141">外部 Web 服务 FQDN 必须可以在公共 Internet 中进行解析。</span><span class="sxs-lookup"><span data-stu-id="c0667-141">The external web services FDQN must be resolvable in the public Internet.</span></span>

<span data-ttu-id="c0667-142">如果内部服务器是 Standard Edition server，则内部 FQDN 为 Standard Edition server FQDN。</span><span class="sxs-lookup"><span data-stu-id="c0667-142">If your internal server is a Standard Edition server, the internal FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="c0667-143">如果内部服务器是前端池，则 FQDN 是用于平衡内部 Web 场服务器负载的硬件负载平衡器虚拟 IP (VIP)。</span><span class="sxs-lookup"><span data-stu-id="c0667-143">If your internal server is a Front End pool, the FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="c0667-144">在具有多个 Enterprise Edition Server 的前端池中，需要使用硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="c0667-144">A hardware load balancer is required in a Front End pool with more than one Enterprise Edition server.</span></span> <span data-ttu-id="c0667-145">Standard Edition Server 或单个 Enterprise Edition 前端服务器不需要使用负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="c0667-145">A load balancer is not required for a Standard Edition server or a single Enterprise Edition Front End Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

