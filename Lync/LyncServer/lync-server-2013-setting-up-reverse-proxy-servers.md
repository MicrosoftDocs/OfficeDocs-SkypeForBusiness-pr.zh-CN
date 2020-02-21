---
title: Lync Server 2013：设置反向代理服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f4ff853e3f31804e4bca55bd6a4576e25702b6c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a><span data-ttu-id="92ca0-102">为 Lync Server 2013 设置反向代理服务器</span><span class="sxs-lookup"><span data-stu-id="92ca0-102">Setting up reverse proxy servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92ca0-103">_**上次修改的主题：** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="92ca0-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="92ca0-104">对于 Microsoft Lync Server 2013 边缘服务器部署，外部客户端必须具有外围网络中的 HTTPS 反向代理，才能访问 Director 和用户的主池上的 Lync Server 2013 Web 服务（称为 Office 通信服务器中的*Web 组件*）。</span><span class="sxs-lookup"><span data-stu-id="92ca0-104">For Microsoft Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for external clients to access the Lync Server 2013 Web Services (called *Web Components* in Office Communications Server) on the Director and the user’s home pool.</span></span> <span data-ttu-id="92ca0-105">需要通过反向代理进行外部访问的部分功能包括：</span><span class="sxs-lookup"><span data-stu-id="92ca0-105">Some of the features that require external access through a reverse proxy include the following:</span></span>

  - <span data-ttu-id="92ca0-106">允许外部用户下载会议的会议内容。</span><span class="sxs-lookup"><span data-stu-id="92ca0-106">Enabling external users to download meeting content for your meetings.</span></span>

  - <span data-ttu-id="92ca0-107">允许外部用户展开通讯组。</span><span class="sxs-lookup"><span data-stu-id="92ca0-107">Enabling external users to expand distribution groups.</span></span>

  - <span data-ttu-id="92ca0-108">允许远程用户从通讯簿服务下载文件。</span><span class="sxs-lookup"><span data-stu-id="92ca0-108">Enabling remote users to download files from the Address Book service.</span></span>

  - <span data-ttu-id="92ca0-109">访问 Lync Web App 客户端。</span><span class="sxs-lookup"><span data-stu-id="92ca0-109">Accessing the Lync Web App client.</span></span>

  - <span data-ttu-id="92ca0-110">访问“电话拨入式会议设置”网页。</span><span class="sxs-lookup"><span data-stu-id="92ca0-110">Accessing the Dial-in Conferencing Settings webpage.</span></span>

  - <span data-ttu-id="92ca0-111">允许外部设备连接到设备更新 Web 服务并获得更新。</span><span class="sxs-lookup"><span data-stu-id="92ca0-111">Enabling external devices to connect to Device Update web service and obtain updates.</span></span>

  - <span data-ttu-id="92ca0-112">使移动应用程序能够自动发现和使用来自 Internet 的移动（Mcx） Url。</span><span class="sxs-lookup"><span data-stu-id="92ca0-112">Enabling mobile applications to automatically discover and use the mobility (Mcx) URLs from the Internet.</span></span>

  - <span data-ttu-id="92ca0-113">启用 Lync 2013 客户端、Lync Windows 应用商店应用和 Lync 2013 移动客户端，以找到 Lync 发现（自动发现） Url 并使用统一通信 Web API （UCWA）。</span><span class="sxs-lookup"><span data-stu-id="92ca0-113">Enabling the Lync 2013 client, Lync Windows Store app and Lync 2013 Mobile client to locate the Lync Discover (autodiscover) URLs and use Unified Communications Web API (UCWA).</span></span>

<span data-ttu-id="92ca0-114">建议配置 HTTP 反向代理以在所有池中发布所有 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="92ca0-114">We recommend that you configure your HTTP reverse proxy to publish all Web Services in all pools.</span></span> <span data-ttu-id="92ca0-115">发布 https://ExternalFQDN/\*发布池的所有 IIS 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="92ca0-115">Publishing https:// ExternalFQDN/\* publishes all IIS virtual directories for a pool.</span></span> <span data-ttu-id="92ca0-116">组织中每个 Standard Edition Server、前端池、控制器或控制器池都需要一个发布规则。</span><span class="sxs-lookup"><span data-stu-id="92ca0-116">You need one publishing rule for each Standard Edition server, Front End pool, or Director or Director pool in your organization.</span></span>

<span data-ttu-id="92ca0-117">此外，还需要发布简单 URL。</span><span class="sxs-lookup"><span data-stu-id="92ca0-117">In addition, you need to publish the simple URLs.</span></span> <span data-ttu-id="92ca0-118">如果组织中有控制器或控制器池，HTTP 反向代理则会侦听对简单 URL 的 HTTP/HTTPS 请求，并且还会将它们代理到控制器或控制器池上的外部 Web 服务虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="92ca0-118">If the organization has a Director or Director pool, the HTTP reverse proxy listens for HTTP/HTTPS requests to the simple URLs and proxies them to the external Web Services virtual directory on the Director or Director pool.</span></span> <span data-ttu-id="92ca0-119">如果尚未部署控制器，则需要指定一个池来处理连接简单 URL 的请求。</span><span class="sxs-lookup"><span data-stu-id="92ca0-119">If you have not deployed a Director, you need to designate one pool to handle requests to the simple URLs.</span></span> <span data-ttu-id="92ca0-120">（如果该池不是用户的主池，它会将这些请求重定向到用户主池上的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="92ca0-120">(If this is not the user’s home pool, it will redirect them onward to the Web Services on the user’s home pool).</span></span> <span data-ttu-id="92ca0-121">）简单 URL 可由专用 Web 发布规则进行处理，也可以将其添加到控制器 Web 发布规则的公共名称中。</span><span class="sxs-lookup"><span data-stu-id="92ca0-121">The simple URLs can be handled by a dedicated web publishing rule, or you can add it to the public names of the web publishing rule for the Director.</span></span> <span data-ttu-id="92ca0-122">此外，还需要发布外部自动发现服务 URL。</span><span class="sxs-lookup"><span data-stu-id="92ca0-122">You also need to publish the external Autodiscover Service URL.</span></span>

<span data-ttu-id="92ca0-123">您可以使用 Microsoft Forefront 威胁管理网关2010、Microsoft Internet 安全和加速（ISA） Server 2006 SP1 或 Internet Information Server 7.0、7.5 或8.0，并使用应用程序请求路由（IIS ARR）作为反向代理。</span><span class="sxs-lookup"><span data-stu-id="92ca0-123">You can use Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, or Internet Information Server 7.0, 7.5 or 8.0 with Application Request Routing (IIS ARR) as a reverse proxy.</span></span> <span data-ttu-id="92ca0-124">本节中的详细步骤介绍了如何配置 Forefront 威胁管理网关2010，以及配置 ISA Server 2006 的步骤几乎完全相同。</span><span class="sxs-lookup"><span data-stu-id="92ca0-124">The detailed steps in this section describe how to configure Forefront Threat Management Gateway 2010, and the steps for configuring ISA Server 2006 are almost identical.</span></span> <span data-ttu-id="92ca0-125">还为 IIS ARR 提供了指南。</span><span class="sxs-lookup"><span data-stu-id="92ca0-125">Guidance is also provided for IIS ARR.</span></span> <span data-ttu-id="92ca0-126">如果使用的是其他反向代理，请参阅该产品的文档，并将此处定义的要求映射到其他反向代理中的关联功能。</span><span class="sxs-lookup"><span data-stu-id="92ca0-126">If you are using a different reverse proxy, consult the documentation for that product and map the requirements defined here to the associated features in other reverse proxies.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="92ca0-127">Internet Information Server 应用程序请求路由（IIS ARR）是为 Lync Server 2010 和 Lync Server 2013 实施反向代理的经过完全测试且受支持的选项。</span><span class="sxs-lookup"><span data-stu-id="92ca0-127">Internet Information Server Application Request Routing (IIS ARR) is a fully tested and supported option for implementing a reverse proxy for Lync Server 2010 and Lync Server 2013.</span></span> <span data-ttu-id="92ca0-128">在11月，2012，Microsoft 停止了 ForeFront 威胁管理网关2010或 TMG 的许可证销售。</span><span class="sxs-lookup"><span data-stu-id="92ca0-128">In November, 2012, Microsoft ceased license sales of ForeFront Threat Management Gateway 2010, or TMG.</span></span> <span data-ttu-id="92ca0-129">TMG 仍是完全受支持的产品，仍可用于第三方销售的设备上的销售。</span><span class="sxs-lookup"><span data-stu-id="92ca0-129">TMG is still a fully supported product, and is still available for sale on appliances sold by third parties.</span></span> <span data-ttu-id="92ca0-130">此外，许多第三方硬件负载平衡器和防火墙提供反向代理支持。</span><span class="sxs-lookup"><span data-stu-id="92ca0-130">Also, many third party hardware load balancers and firewalls provide reverse proxy support.</span></span> <span data-ttu-id="92ca0-131">对于提供反向代理功能的硬件负载平衡器和防火墙，请与您的供应商联系，以获取有关如何配置其产品以为 Lync Server 提供反向代理支持的具体说明。</span><span class="sxs-lookup"><span data-stu-id="92ca0-131">For hardware load balancers and firewalls that provide reverse proxy features, check with your vendor for specific instructions on how to configure their product to provide reverse proxy support for Lync Server.</span></span> <span data-ttu-id="92ca0-132">您还可以查看已将其产品的文档提交给 Microsoft 的第三方。</span><span class="sxs-lookup"><span data-stu-id="92ca0-132">You can also view third parties that have submitted documentation for their product to Microsoft.</span></span> <span data-ttu-id="92ca0-133">由第三方为其解决方案提供支持。</span><span class="sxs-lookup"><span data-stu-id="92ca0-133">Support is provided by the third party for their solution.</span></span> <span data-ttu-id="92ca0-134">若要查看在提供解决方案时处于活动状态的第三方，请参阅<A href="https://go.microsoft.com/fwlink/?linkid=268730">Microsoft Lync 的基础结构限定</A>。</span><span class="sxs-lookup"><span data-stu-id="92ca0-134">To see third parties that are active in providing solutions, see <A href="https://go.microsoft.com/fwlink/?linkid=268730">Infrastructure qualified for Microsoft Lync</A>.</span></span>



</div>

<span data-ttu-id="92ca0-135">下面的主题和过程将 Forefront 威胁管理网关2010和 IIS ARR 用作部署和配置过程的基础。</span><span class="sxs-lookup"><span data-stu-id="92ca0-135">The following topics and procedures use Forefront Threat Management Gateway 2010 and IIS ARR as the basis for the deployment and configuration procedures.</span></span>

  - [<span data-ttu-id="92ca0-136">为 Lync Server 2013 配置 web 场 Fqdn</span><span class="sxs-lookup"><span data-stu-id="92ca0-136">Configure web farm FQDNs for Lync Server 2013</span></span>](lync-server-2013-configure-web-farm-fqdns.md)

  - [<span data-ttu-id="92ca0-137">在 Lync Server 2013 中配置网络适配器</span><span class="sxs-lookup"><span data-stu-id="92ca0-137">Configure network adapters in Lync Server 2013</span></span>](lync-server-2013-configure-network-adapters.md)

  - [<span data-ttu-id="92ca0-138">在 Lync Server 2013 中为您的反向 HTTP 代理请求和配置证书</span><span class="sxs-lookup"><span data-stu-id="92ca0-138">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [<span data-ttu-id="92ca0-139">在 Lync Server 2013 中为单个内部池配置 web 发布规则</span><span class="sxs-lookup"><span data-stu-id="92ca0-139">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [<span data-ttu-id="92ca0-140">在 Lync Server 2013 中验证或配置 IIS 虚拟目录的身份验证和证书</span><span class="sxs-lookup"><span data-stu-id="92ca0-140">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [<span data-ttu-id="92ca0-141">在 Lync Server 2013 中为反向代理服务器创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="92ca0-141">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [<span data-ttu-id="92ca0-142">通过你在 Lync Server 2013 中的反向代理验证访问权限</span><span class="sxs-lookup"><span data-stu-id="92ca0-142">Verify access through your reverse proxy in Lync Server 2013</span></span>](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a><span data-ttu-id="92ca0-143">开始之前</span><span class="sxs-lookup"><span data-stu-id="92ca0-143">Before You Begin</span></span>

<span data-ttu-id="92ca0-144">若要成功部署 Forefront 威胁管理网关2010作为反向代理，您需要使用 Forefront 威胁管理网关2010文档中定义的先决条件和硬件要求设置和配置服务器。</span><span class="sxs-lookup"><span data-stu-id="92ca0-144">To successfully deploy Forefront Threat Management Gateway 2010 as your reverse proxy, you need to setup and configure a server, using the prerequisites and hardware requirements defined in the Forefront Threat Management Gateway 2010 documentation.</span></span> <span data-ttu-id="92ca0-145">在继续之前，请参阅以下主题设置为正确配置硬件并在服务器上安装 Forefront 威胁管理网关2010。</span><span class="sxs-lookup"><span data-stu-id="92ca0-145">See the following topic set to properly configure the hardware and to install Forefront Threat Management Gateway 2010 on the server before proceeding.</span></span>

  - <span></span>  
    [<span data-ttu-id="92ca0-146">Forefront Threat Management Gateway (TMG) 2010</span><span class="sxs-lookup"><span data-stu-id="92ca0-146">Forefront Threat Management Gateway (TMG) 2010</span></span>](https://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [<span data-ttu-id="92ca0-147">Forefront TMG 2010 硬件建议</span><span class="sxs-lookup"><span data-stu-id="92ca0-147">Forefront TMG 2010 hardware recommendations</span></span>](https://go.microsoft.com/fwlink/?linkid=291293)

<span data-ttu-id="92ca0-148">若要成功地将 IIS ARR 部署为反向代理，请查看以下主题以配置硬件和必备软件。</span><span class="sxs-lookup"><span data-stu-id="92ca0-148">To successfully deploy IIS ARR as your reverse proxy, review the following topics to configure the hardware and the prerequisite software.</span></span>

  - <span></span>  
    <span data-ttu-id="92ca0-149">若要在 Windows Server 2008 或 Windows Server 2008 R2 上安装 IIS，请参阅[在 Windows server 2008 或 Windows server 2008 r2 上安装 iis 7](https://go.microsoft.com/fwlink/?linkid=291296)</span><span class="sxs-lookup"><span data-stu-id="92ca0-149">To install IIS on Windows Server 2008 or Windows Server 2008 R2, see [Installing IIS 7 on Windows Server 2008 or Windows Server 2008 R2](https://go.microsoft.com/fwlink/?linkid=291296)</span></span>

  - <span></span>  
    <span data-ttu-id="92ca0-150">若要在 Windows Server 2012 上安装 IIS，请参阅[在 Windows server 上安装 iis 8 2012](https://go.microsoft.com/fwlink/?linkid=291297)</span><span class="sxs-lookup"><span data-stu-id="92ca0-150">To install IIS on Windows Server 2012, see [Installing IIS 8 on Windows Server 2012](https://go.microsoft.com/fwlink/?linkid=291297)</span></span>

  - <span></span>  
    <span data-ttu-id="92ca0-151">若要在 Windows Server 2012 R2 上安装 IIS，请参阅[在 Windows server 上安装 iis 8.5 2012 R2](https://go.microsoft.com/fwlink/?linkid=330687)</span><span class="sxs-lookup"><span data-stu-id="92ca0-151">To install IIS on Windows Server 2012 R2, see [Installing IIS 8.5 on Windows Server 2012 R2](https://go.microsoft.com/fwlink/?linkid=330687)</span></span>

  - <span></span>  
    <span data-ttu-id="92ca0-152">若要下载 IIS 的应用程序请求路由扩展插件，请按照[应用程序请求路由](https://go.microsoft.com/fwlink/?linkid=291298)中的说明下载</span><span class="sxs-lookup"><span data-stu-id="92ca0-152">To download the Application Request Routing extension for IIS, follow the instructions at [Application Request Routing v2.5 Download](https://go.microsoft.com/fwlink/?linkid=291298)</span></span>

  - <span></span>  
    <span data-ttu-id="92ca0-153">若要安装 ARR，请参阅[安装应用程序请求路由版本 2](https://go.microsoft.com/fwlink/?linkid=291299)中的说明</span><span class="sxs-lookup"><span data-stu-id="92ca0-153">To install ARR, for the instructions at [Install Application Request Routing Version 2](https://go.microsoft.com/fwlink/?linkid=291299)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92ca0-154">当前发布的说明适用于 ARR 2.0。</span><span class="sxs-lookup"><span data-stu-id="92ca0-154">The instructions currently posted are for ARR 2.0.</span></span> <span data-ttu-id="92ca0-155">对于扩展安装，两个版本之间没有区别。</span><span class="sxs-lookup"><span data-stu-id="92ca0-155">For installation of the extension, there is no difference between the two versions.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

