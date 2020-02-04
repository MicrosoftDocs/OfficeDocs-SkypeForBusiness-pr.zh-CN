---
title: 用于会议的 Lync Server 2013 组件和拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db44e7c8430865fcf8138c9b51f6e700ff85dd7b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="89e87-102">Lync Server 2013 中用于会议的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="89e87-102">Components and topologies for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89e87-103">_**主题上次修改时间：** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="89e87-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="89e87-104">当您在拓扑生成器中选择 "会议" 时，会议将作为前端服务器或标准版服务器的一部分进行部署。</span><span class="sxs-lookup"><span data-stu-id="89e87-104">When you select conferencing in Topology Builder, conferencing is deployed as part of the Front End Server or Standard Edition server.</span></span> <span data-ttu-id="89e87-105">电话拨入式会议和 PowerPoint 共享需要其他组件和配置。</span><span class="sxs-lookup"><span data-stu-id="89e87-105">Dial-in conferencing and PowerPoint sharing requires additional components and configuration.</span></span> <span data-ttu-id="89e87-106">以下部分介绍了 web 会议、A/V 会议和电话拨入式会议所支持的组件和拓扑。</span><span class="sxs-lookup"><span data-stu-id="89e87-106">The following sections describe the supported components and topologies for web conferencing, A/V conferencing, and dial-in conferencing.</span></span>

<div>

## <a name="supported-components"></a><span data-ttu-id="89e87-107">支持的组件</span><span class="sxs-lookup"><span data-stu-id="89e87-107">Supported Components</span></span>

<span data-ttu-id="89e87-108">只有你的组织的前端服务器或标准版服务器才需要组件 web 会议和 A/V 会议。</span><span class="sxs-lookup"><span data-stu-id="89e87-108">The only components web conferencing and A/V conferencing require are your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="89e87-109">有关前端服务器和标准版服务器的硬件和软件要求的列表，请参阅 Lync Server 2013[支持的适用于 Lync server 2013](lync-server-2013-supported-hardware.md)和[服务器软件和基础结构支持](lync-server-2013-server-software-and-infrastructure-support.md)的硬件。</span><span class="sxs-lookup"><span data-stu-id="89e87-109">For a list of hardware and software requirements for the Front End Servers and Standard Edition servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

<span data-ttu-id="89e87-110">Lync Server 2013 使用 Office Web Apps 和 Office Web Apps 服务器处理 PowerPoint 演示文稿的共享和呈现。</span><span class="sxs-lookup"><span data-stu-id="89e87-110">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="89e87-111">有关安装和配置 Office Web Apps 服务器的详细信息，请参阅[配置与 Office web Apps server 和 Lync server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="89e87-111">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="89e87-112">除了 web 会议和 A/V 会议的要求外，电话拨入式会议使用以下 Lync Server 2013 组件：</span><span class="sxs-lookup"><span data-stu-id="89e87-112">In addition to the requirements for web conferencing and A/V conferencing, dial-in conferencing uses the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="89e87-113">**应用程序服务**   应用程序服务提供了用于部署、托管和管理统一通信（UC）应用程序的平台。</span><span class="sxs-lookup"><span data-stu-id="89e87-113">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications (UC) applications.</span></span> <span data-ttu-id="89e87-114">电话拨入式会议使用需要应用程序服务的两个 UC 应用程序：会议助理和会议公告。</span><span class="sxs-lookup"><span data-stu-id="89e87-114">Dial-in conferencing uses two UC applications that require Application service: Conferencing Attendant and Conferencing Announcement.</span></span> <span data-ttu-id="89e87-115">在部署会议工作负荷和选择 "电话拨入式会议" 选项时，默认情况下，应用程序服务在前端池的每个前端服务器上和每个标准版服务器上都安装和激活。</span><span class="sxs-lookup"><span data-stu-id="89e87-115">Application service is installed and activated by default on every Front End Server in a Front End pool and on every Standard Edition server when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="89e87-116">**会议助理应用程序**   会议助理应用程序是一个统一通信应用程序，可接受公共交换电话网络（PSTN）呼叫、播放提示以及将呼叫联接到 a/V 会议。</span><span class="sxs-lookup"><span data-stu-id="89e87-116">**Conferencing Attendant application**   Conferencing Attendant application is a unified communications application that accepts public switched telephone network (PSTN) calls, plays prompts, and joins the calls to an A/V conference.</span></span> <span data-ttu-id="89e87-117">当您部署会议工作负荷并选择 "电话拨入式会议" 选项时，会议助理应用程序默认安装并激活。</span><span class="sxs-lookup"><span data-stu-id="89e87-117">Conferencing Attendant application is installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="89e87-118">**会议公告应用程序**   会议公告应用程序是一种统一通信应用程序，用于在某些操作（如参与者加入或离开会议）中向 PSTN 参与者播放声音和提示，参与者是静音或已取消静音、某人进入了会议会议厅，或者会议已锁定或已解锁。</span><span class="sxs-lookup"><span data-stu-id="89e87-118">**Conferencing Announcement application**   Conferencing Announcement application is a unified communications application that plays tones and prompts to PSTN participants on certain actions, such as when participants join or leave a conference, participants are muted or unmuted, someone enters the conference lobby, or the conference is locked or unlocked.</span></span> <span data-ttu-id="89e87-119">会议公告应用程序还支持电话键盘中的双音调 multifrequency （DTMF）命令。</span><span class="sxs-lookup"><span data-stu-id="89e87-119">Conferencing Announcement application also supports dual-tone multifrequency (DTMF) commands from the phone keypad.</span></span> <span data-ttu-id="89e87-120">会议公告应用程序在你部署会议工作负荷和选择电话拨入式会议选项时，默认情况下会自动安装和激活。</span><span class="sxs-lookup"><span data-stu-id="89e87-120">Conferencing Announcement application is automatically installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="89e87-121">\*\*\*\*"电话拨入式会议设置" 页面，"电话拨入式会议设置" 页面显示会议拨入号码，其中包含其可用语言、分配的会议信息（即对于不需要安排的会议）和会议 DTMF 控制，并支持个人识别码（PIN）和分配的会议信息的管理。   </span><span class="sxs-lookup"><span data-stu-id="89e87-121">**Dial-in Conferencing Settings page**   The Dial-in Conferencing Settings page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="89e87-122">“电话拨入式会议设置”页作为 Web 服务的一部分自动安装。</span><span class="sxs-lookup"><span data-stu-id="89e87-122">The Dial-in Conferencing Settings page is automatically installed as part of Web Services.</span></span>

  - <span data-ttu-id="89e87-123">**Lync server 2013、中介服务器和 PSTN 网关**   电话拨入式会议需要中介服务器在 Lync server 2013 和 pstn 网关之间转换信号（和媒体，在某些配置中），以及用于在中介服务器和 pstn 网关之间转换信号和媒体的 pstn 网关。</span><span class="sxs-lookup"><span data-stu-id="89e87-123">**Lync Server 2013, Mediation Server and PSTN gateway**   Dial-in conferencing requires a Mediation Server to translate signaling (and media, in some configurations) between Lync Server 2013 and the PSTN gateway, and a PSTN gateway to translate signaling and media between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="89e87-124">对于电话拨入式会议，必须至少部署一个中介服务器和以下至少一个服务器：</span><span class="sxs-lookup"><span data-stu-id="89e87-124">For dial-in conferencing, you must deploy at least one Mediation Server and at least one of the following:</span></span>
    
      - <span data-ttu-id="89e87-125">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="89e87-125">PSTN gateway</span></span>
    
      - <span data-ttu-id="89e87-126">IP-PBX</span><span class="sxs-lookup"><span data-stu-id="89e87-126">IP-PBX</span></span>
    
      - <span data-ttu-id="89e87-127">会话边界控制器 (SBC)（用于通过配置 SIP 中继进行连接的 Internet 电话服务提供商）</span><span class="sxs-lookup"><span data-stu-id="89e87-127">Session Border Controller (SBC) (for an Internet telephony service provider to which you connect by configuring a SIP trunk)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="89e87-128">如果您还在部署企业语音，则中介服务器和 PSTN 网关是企业语音部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="89e87-128">If you are also deploying Enterprise Voice, Mediation Server and PSTN gateways are part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="89e87-129">如果不部署企业语音，则需要为电话拨入式会议至少部署一个中介服务器和至少一个 PSTN 网关、IP PBX 或 SBC。</span><span class="sxs-lookup"><span data-stu-id="89e87-129">If you are not deploying Enterprise Voice, you need to deploy at least one Mediation Server and at least one PSTN gateway, IP-PBX, or SBC for dial-in conferencing.</span></span>

    
    </div>

  - <span data-ttu-id="89e87-130">**文件存储**   文件存储用于录制的名称音频文件。</span><span class="sxs-lookup"><span data-stu-id="89e87-130">**File store**   File store is used for recorded name audio files.</span></span> <span data-ttu-id="89e87-131">文件存储是每个 Enterprise Edition 或 Standard Edition 部署中的标准组件。</span><span class="sxs-lookup"><span data-stu-id="89e87-131">File Store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="89e87-132">**用户存储**   用户存储用于存储用户 Lync Server 2013 pin。</span><span class="sxs-lookup"><span data-stu-id="89e87-132">**User store**   User store is used to store user Lync Server 2013 PINs.</span></span> <span data-ttu-id="89e87-133">PIN 是哈希值。</span><span class="sxs-lookup"><span data-stu-id="89e87-133">PINs are hashed.</span></span> <span data-ttu-id="89e87-134">用户存储是每个 Enterprise Edition 或 Standard Edition 部署中的标准组件。</span><span class="sxs-lookup"><span data-stu-id="89e87-134">The User store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="89e87-135">**Lync server 控制面板**   某些拨入设置可通过使用 Lync Server 控制面板进行配置。</span><span class="sxs-lookup"><span data-stu-id="89e87-135">**Lync Server Control Panel**   Some dial-in settings can be configured by using Lync Server Control Panel.</span></span>

  - <span data-ttu-id="89e87-136">**Lync server management shell**   可以使用 Lync Server management shell cmdlet 配置所有拨入设置。</span><span class="sxs-lookup"><span data-stu-id="89e87-136">**Lync Server Management Shell**   All dial-in settings can be configured by using Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="89e87-137">Lync Server Management Shell cmdlet 可用于部署、配置、运行、监视会议助理应用程序和会议公告应用程序以及对其进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="89e87-137">Lync Server Management Shell cmdlets are available for deploying, configuring, running, monitoring, and troubleshooting Conferencing Attendant application and Conferencing Announcement application.</span></span> <span data-ttu-id="89e87-138">有关特定 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="89e87-138">For details about specific cmdlets, see Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="89e87-139">支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="89e87-139">Supported Topologies</span></span>

<span data-ttu-id="89e87-140">在 Lync Server 2013 中，运行会议服务的服务器始终与前端服务器或标准版服务器 collocated。</span><span class="sxs-lookup"><span data-stu-id="89e87-140">In Lync Server 2013, the server running conferencing services is always collocated with the Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="89e87-141">在初始部署期间，拓扑生成器提供了在拓扑中包括会议的选项。</span><span class="sxs-lookup"><span data-stu-id="89e87-141">During your initial deployment, Topology Builder gives you the option to include conferencing in your topology.</span></span> <span data-ttu-id="89e87-142">还可以使用拓扑生成器将会议添加到现有部署。</span><span class="sxs-lookup"><span data-stu-id="89e87-142">You can also use Topology Builder to add conferencing to an existing deployment.</span></span> <span data-ttu-id="89e87-143">有关详细信息，请参阅[在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="89e87-143">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

<div>

## <a name="dial-in-conferencing-toplogies"></a><span data-ttu-id="89e87-144">拨入会议 Toplogies</span><span class="sxs-lookup"><span data-stu-id="89e87-144">Dial in Conferencing Toplogies</span></span>

<span data-ttu-id="89e87-145">可以在下列拓扑和配置中部署电话拨入式会议：</span><span class="sxs-lookup"><span data-stu-id="89e87-145">You can deploy dial-in conferencing in the following topologies and configurations:</span></span>

  - <span data-ttu-id="89e87-146">Lync Server 2013 标准版</span><span class="sxs-lookup"><span data-stu-id="89e87-146">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="89e87-147">Lync Server 2013 企业版</span><span class="sxs-lookup"><span data-stu-id="89e87-147">Lync Server 2013 Enterprise Edition</span></span>

  - <span data-ttu-id="89e87-148">使用或不使用企业语音</span><span class="sxs-lookup"><span data-stu-id="89e87-148">With or without Enterprise Voice</span></span>

<span data-ttu-id="89e87-149">可以在中心网站（而不是分支站点）中部署应用程序服务、会议助理应用程序和会议公告应用程序。</span><span class="sxs-lookup"><span data-stu-id="89e87-149">You can deploy Application service, Conferencing Attendant application, and Conferencing Announcement application in a central site, but not in a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="89e87-150">如果你部署电话拨入式会议，则必须在部署 Lync Server 2013 会议的每个池中部署它。</span><span class="sxs-lookup"><span data-stu-id="89e87-150">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="89e87-151">无需在每个池中分配访问号码，但必须在每个池中部署电话拨入式会议功能。</span><span class="sxs-lookup"><span data-stu-id="89e87-151">You do not need to assign access numbers in every pool, but you must deploy the dial-in conferencing feature in every pool.</span></span> <span data-ttu-id="89e87-152">当用户从一个池中调用访问号码以在其他池中加入 Lync Server 2013 会议时，此要求支持录制的名称功能。</span><span class="sxs-lookup"><span data-stu-id="89e87-152">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a><span data-ttu-id="89e87-153">Lync Server 2013 和 Office Web Apps 支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="89e87-153">Supported Topologies for Lync Server 2013 and Office Web Apps</span></span>

<span data-ttu-id="89e87-154">Lync Server 2013 提供了以下配置 Office Web Apps 服务器的方法。</span><span class="sxs-lookup"><span data-stu-id="89e87-154">Lync Server 2013 provides the following ways to configure Office Web Apps Server.</span></span> <span data-ttu-id="89e87-155">根据你的需要，你可以：</span><span class="sxs-lookup"><span data-stu-id="89e87-155">Depending on your needs you can:</span></span>

  - <span data-ttu-id="89e87-156">**在您的组织的防火墙后面和同一网络区域中安装 Lync Server 2013 和 Office Web Apps 本地服务器。**</span><span class="sxs-lookup"><span data-stu-id="89e87-156">**Install both Lync Server 2013 and Office Web Apps Server on-premises behind your organization’s firewall, and in the same network zone.**</span></span> <span data-ttu-id="89e87-157">使用此拓扑，将通过反向代理服务器提供对 Office Web Apps 的外部访问。</span><span class="sxs-lookup"><span data-stu-id="89e87-157">With this topology, external access to Office Web Apps Server will be provided through your reverse proxy server.</span></span> <span data-ttu-id="89e87-158">Lync Server 2013 和 Office Web Apps 服务器（或 Office Web Apps 服务器场）都在本地和组织的防火墙之后安装。</span><span class="sxs-lookup"><span data-stu-id="89e87-158">Both Lync Server 2013 and Office Web Apps Server (or an Office Web Apps Server farm) are installed on-premises and behind your organization's firewall.</span></span> <span data-ttu-id="89e87-159">理想情况下，你应在 Lync Server 所在的网络区域中安装 Office Web Apps 服务器。</span><span class="sxs-lookup"><span data-stu-id="89e87-159">Ideally, you should install Office Web Apps Server in the same network zone as Lync Server.</span></span>
    
    <span data-ttu-id="89e87-160">外部 Lync 客户端可以使用反向代理服务器连接到 Lync Server 2013 和 Office Web Apps 服务器，这是一个服务器，该服务器接受来自 Internet 的请求并将其转发到内部网络。</span><span class="sxs-lookup"><span data-stu-id="89e87-160">External Lync clients can connect to Lync Server 2013 and to Office Web Apps Server by using a reverse proxy server, which is a server that takes requests from the Internet and forwards them to the internal network.</span></span> <span data-ttu-id="89e87-161">（内部客户端不需要使用反向代理服务器，因为它们可以直接连接到 Office Web Apps 服务器。）如果你希望使用仅由 Lync Server 2013 使用的专用 Office Web Apps 服务器场，则此拓扑最适用。</span><span class="sxs-lookup"><span data-stu-id="89e87-161">(Internal clients do not need to use the reverse proxy server because they can connect to Office Web Apps Server directly.) This topology works best if you want to use a dedicated Office Web Apps Server farm that is only used by Lync Server 2013.</span></span>

  - <span data-ttu-id="89e87-162">**使用外部部署的 Office Web Apps 服务器**</span><span class="sxs-lookup"><span data-stu-id="89e87-162">**Using an externally deployed Office Web Apps Server**</span></span>
    
    <span data-ttu-id="89e87-163">在此拓扑中，将在本地部署 Lync Server 2013，并使用在 Lync Server 网络区域外部部署的 Office Web Apps 服务器。</span><span class="sxs-lookup"><span data-stu-id="89e87-163">In this topology, Lync Server 2013 is deployed on-premises, and uses an Office Web Apps Server that is deployed outside of Lync Server network zone.</span></span> <span data-ttu-id="89e87-164">当 Office Web Apps 服务器在公司中的多个应用程序之间共享并部署在需要 Lync 服务器才能使用 Office Web Apps 服务器的外部接口的网络中时，可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="89e87-164">This may happen when Office Web Apps Server is shared across multiple applications in the corporation and is deployed in a network requiring Lync Server to use the external interface of Office Web Apps Server and vice versa.</span></span>
    
    <span data-ttu-id="89e87-165">无需安装反向代理服务器;而是从 Office Web Apps 服务器到 Lync Server 2013 的所有请求都通过 Edge 服务器进行路由。</span><span class="sxs-lookup"><span data-stu-id="89e87-165">You do not need to install a reverse proxy server; instead, all the requests from the Office Web Apps Server to Lync Server 2013 are routed through your Edge Server.</span></span> <span data-ttu-id="89e87-166">内部和外部 Lync 客户端都使用外部 URL 连接到 Office Web Apps 服务器。</span><span class="sxs-lookup"><span data-stu-id="89e87-166">Both your internal and your external Lync clients connect to Office Web Apps Server using the external URL.</span></span>
    
    <span data-ttu-id="89e87-167">如果 Office Web Apps 服务器是在内部防火墙外部部署的，请选择 "Office Web Apps" 服务器在拓扑生成器中的**外部网络（即，周边/Internet）中部署**。</span><span class="sxs-lookup"><span data-stu-id="89e87-167">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** in Topology Builder.</span></span> <span data-ttu-id="89e87-168">有关更多详细信息，请参阅[配置与 Office Web Apps server 和 Lync server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="89e87-168">For more details see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="89e87-169">无论你选择什么拓扑，打开正确的防火墙端口至关重要。</span><span class="sxs-lookup"><span data-stu-id="89e87-169">Regardless of the topology you select, it is critical that the correct firewall ports be opened.</span></span> <span data-ttu-id="89e87-170">你必须确保 DNS 名称、IP 地址和端口未被 Office Web Apps 服务器、负载平衡器或 Lync Server 上的防火墙阻止。</span><span class="sxs-lookup"><span data-stu-id="89e87-170">You must make sure that DNS names, IP addresses, and ports are not blocked by firewalls on the Office Web Apps Server, the load balancer, or Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="89e87-171">用于提供对 Office Web Apps 服务器的外部访问的另一个选项是在外围网络中部署服务器。</span><span class="sxs-lookup"><span data-stu-id="89e87-171">Another option for providing external access to Office Web Apps Server is to deploy the server in the perimeter network.</span></span> <span data-ttu-id="89e87-172">如果你选择执行此操作，请记住 Office Web Apps 服务器安装要求服务器计算机是你的 Active Directory 域的成员。</span><span class="sxs-lookup"><span data-stu-id="89e87-172">If you elect to do this, keep in mind that Office Web Apps Server setup requires the server computer to be a member of your Active Directory domain.</span></span> <span data-ttu-id="89e87-173">除非你的网络策略允许外围网络中的计算机成为 Active Directory 域成员，否则建议你不要在外围网络中安装 Office Web Apps 服务器。</span><span class="sxs-lookup"><span data-stu-id="89e87-173">Unless your network policy allows computers in the perimeter network to be Active Directory domain members, it is recommended that you do not install Office Web Apps Server in the perimeter network.</span></span> <span data-ttu-id="89e87-174">相反，你应该在内部网络中安装 Office Web Apps 服务器，并通过反向代理服务器提供外部用户访问。</span><span class="sxs-lookup"><span data-stu-id="89e87-174">Instead, you should install Office Web Apps Server in the internal network and provide external user access through your reverse proxy server.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

