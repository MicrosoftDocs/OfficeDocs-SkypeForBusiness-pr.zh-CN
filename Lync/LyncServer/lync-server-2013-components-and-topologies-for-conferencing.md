---
title: 适用于会议的 Lync Server 2013 组件和拓扑
description: 适用于会议的 Lync Server 2013 组件和拓扑。
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
ms.openlocfilehash: 719fe81d0f634b1eab1e79c2e7e665e89b0a791a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576858"
---
# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="c8bd6-103">Lync Server 2013 中的会议的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="c8bd6-103">Components and topologies for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8bd6-104">_**上次修改的主题：** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="c8bd6-104">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="c8bd6-105">在拓扑生成器中选择 "会议" 时，会将会议作为前端服务器或 Standard Edition 服务器的一部分进行部署。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-105">When you select conferencing in Topology Builder, conferencing is deployed as part of the Front End Server or Standard Edition server.</span></span> <span data-ttu-id="c8bd6-106">电话拨入式会议和 PowerPoint 需要其他组件和配置。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-106">Dial-in conferencing and PowerPoint sharing requires additional components and configuration.</span></span> <span data-ttu-id="c8bd6-107">下面各部分介绍了支持 Web 会议、A/V 会议和电话拨入式会议的组件和拓扑。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-107">The following sections describe the supported components and topologies for web conferencing, A/V conferencing, and dial-in conferencing.</span></span>

<div>

## <a name="supported-components"></a><span data-ttu-id="c8bd6-108">支持的组件</span><span class="sxs-lookup"><span data-stu-id="c8bd6-108">Supported Components</span></span>

<span data-ttu-id="c8bd6-109">仅有的组件 web 会议和 A/V 会议需要您的组织的前端服务器或 Standard Edition 服务器。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-109">The only components web conferencing and A/V conferencing require are your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="c8bd6-110">有关前端服务器和 Standard Edition 服务器的硬件和软件要求的列表，请参阅 Lync Server 2013 中的 [支持的适用于 Lync server 2013](lync-server-2013-supported-hardware.md) 和 [服务器软件和基础结构支持](lync-server-2013-server-software-and-infrastructure-support.md)的硬件。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-110">For a list of hardware and software requirements for the Front End Servers and Standard Edition servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

<span data-ttu-id="c8bd6-111">Lync Server 2013 使用 Office Web Apps 和 Office Web Apps Server 处理 PowerPoint 演示文稿的共享和呈现。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-111">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="c8bd6-112">有关安装和配置 Office Web Apps Server 的详细信息，请参阅 [配置与 Office Web Apps server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-112">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="c8bd6-113">除了 web 会议和 A/V 会议的要求外，电话拨入式会议使用以下 Lync Server 2013 组件：</span><span class="sxs-lookup"><span data-stu-id="c8bd6-113">In addition to the requirements for web conferencing and A/V conferencing, dial-in conferencing uses the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="c8bd6-114">**应用程序服务**    应用程序服务提供了用于部署、托管和管理统一通信 (UC) 应用程序的平台。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-114">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications (UC) applications.</span></span> <span data-ttu-id="c8bd6-115">电话拨入式会议使用两个需要应用程序服务的 UC 应用程序：会议助理和会议通知。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-115">Dial-in conferencing uses two UC applications that require Application service: Conferencing Attendant and Conferencing Announcement.</span></span> <span data-ttu-id="c8bd6-116">在部署会议工作负载和选择 "电话拨入式会议" 选项时，默认情况下，应用程序服务在前端池的每台前端服务器上和每个 Standard Edition 服务器上的默认安装和激活。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-116">Application service is installed and activated by default on every Front End Server in a Front End pool and on every Standard Edition server when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="c8bd6-117">**会议助理应用程序**    会议助理应用程序是一个统一通信应用程序，它接受公开交换的电话网络 (PSTN) 呼叫、播放提示，并将呼叫加入 A/V 会议。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-117">**Conferencing Attendant application**   Conferencing Attendant application is a unified communications application that accepts public switched telephone network (PSTN) calls, plays prompts, and joins the calls to an A/V conference.</span></span> <span data-ttu-id="c8bd6-118">会议助理应用程序在您部署会议工作负荷并选择 "电话拨入式会议" 选项时默认情况下会安装和激活。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-118">Conferencing Attendant application is installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="c8bd6-119">**会议通知应用程序**    会议通知应用程序是一个统一通信应用程序，它在特定操作（如参与者加入会议或离开会议时）对 PSTN 参与者播放声音和提示，参与者是静音或 unmuted、某人进入了会议会议厅，或者会议已锁定或已解锁。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-119">**Conferencing Announcement application**   Conferencing Announcement application is a unified communications application that plays tones and prompts to PSTN participants on certain actions, such as when participants join or leave a conference, participants are muted or unmuted, someone enters the conference lobby, or the conference is locked or unlocked.</span></span> <span data-ttu-id="c8bd6-120">会议通知应用程序还支持电话键盘上的双音多频 (DTMF) 命令。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-120">Conferencing Announcement application also supports dual-tone multifrequency (DTMF) commands from the phone keypad.</span></span> <span data-ttu-id="c8bd6-121">会议通知应用程序在你部署会议工作负载和选择电话拨入式会议选项时，默认情况下会自动安装和激活。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-121">Conferencing Announcement application is automatically installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="c8bd6-122">**"电话拨入式会议设置" 页**    "电话拨入式会议设置" 页显示会议拨入号码，其中包含其可用语言、分配的会议信息 (即对于不需要安排) 的会议以及会议 DTMF 控制，并支持对个人标识号 (PIN) 和分配的会议信息的管理。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-122">**Dial-in Conferencing Settings page**   The Dial-in Conferencing Settings page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="c8bd6-123">"电话拨入式会议设置" 页将作为 Web 服务的一部分自动安装。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-123">The Dial-in Conferencing Settings page is automatically installed as part of Web Services.</span></span>

  - <span data-ttu-id="c8bd6-124">**Lync server 2013、中介服务器和 PSTN 网关**    电话拨入式会议要求中介服务器转换信号 (和媒体，在 Lync Server 2013 和 PSTN 网关之间的某些配置中) ，以及在中介服务器和 PSTN 网关之间转换信号和媒体的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-124">**Lync Server 2013, Mediation Server and PSTN gateway**   Dial-in conferencing requires a Mediation Server to translate signaling (and media, in some configurations) between Lync Server 2013 and the PSTN gateway, and a PSTN gateway to translate signaling and media between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="c8bd6-125">对于电话拨入式会议，必须至少部署一个中介服务器和以下至少一个：</span><span class="sxs-lookup"><span data-stu-id="c8bd6-125">For dial-in conferencing, you must deploy at least one Mediation Server and at least one of the following:</span></span>
    
      - <span data-ttu-id="c8bd6-126">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="c8bd6-126">PSTN gateway</span></span>
    
      - <span data-ttu-id="c8bd6-127">IP-PBX</span><span class="sxs-lookup"><span data-stu-id="c8bd6-127">IP-PBX</span></span>
    
      - <span data-ttu-id="c8bd6-128">会话边界控制器 (SBC)（用于通过配置 SIP 中继进行连接的 Internet 电话服务提供商）</span><span class="sxs-lookup"><span data-stu-id="c8bd6-128">Session Border Controller (SBC) (for an Internet telephony service provider to which you connect by configuring a SIP trunk)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8bd6-129">如果还部署企业语音，中介服务器和 PSTN 网关是企业语音部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-129">If you are also deploying Enterprise Voice, Mediation Server and PSTN gateways are part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="c8bd6-130">如果不部署企业语音，则需要为电话拨入式会议部署至少一台中介服务器，以及至少一个 PSTN 网关、IP-PBX 或 SBC。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-130">If you are not deploying Enterprise Voice, you need to deploy at least one Mediation Server and at least one PSTN gateway, IP-PBX, or SBC for dial-in conferencing.</span></span>

    
    </div>

  - <span data-ttu-id="c8bd6-131">**文件存储**    文件存储用于记录的名称音频文件。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-131">**File store**   File store is used for recorded name audio files.</span></span> <span data-ttu-id="c8bd6-132">文件存储是每个 Enterprise Edition 或 Standard Edition 部署中的一个标准组件。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-132">File Store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="c8bd6-133">**用户存储**    用户存储用于存储用户 Lync Server 2013 Pin。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-133">**User store**   User store is used to store user Lync Server 2013 PINs.</span></span> <span data-ttu-id="c8bd6-134">对 Pin 进行哈希处理。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-134">PINs are hashed.</span></span> <span data-ttu-id="c8bd6-135">用户存储是每个 Enterprise Edition 或 Standard Edition 部署中的标准组件。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-135">The User store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="c8bd6-136">**Lync Server 控制面板**    可以使用 Lync Server 控制面板配置一些拨入设置。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-136">**Lync Server Control Panel**   Some dial-in settings can be configured by using Lync Server Control Panel.</span></span>

  - <span data-ttu-id="c8bd6-137">**Lync Server 命令行**     管理程序可以使用 Lync Server 命令行管理程序 cmdlet 配置所有拨入设置。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-137">**Lync Server Management Shell**   All dial-in settings can be configured by using Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="c8bd6-138">Lync Server 命令行管理程序 cmdlet 可用于部署、配置、运行、监视会议助理应用程序和会议通知应用程序并对其进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-138">Lync Server Management Shell cmdlets are available for deploying, configuring, running, monitoring, and troubleshooting Conferencing Attendant application and Conferencing Announcement application.</span></span> <span data-ttu-id="c8bd6-139">有关特定 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-139">For details about specific cmdlets, see Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="c8bd6-140">支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="c8bd6-140">Supported Topologies</span></span>

<span data-ttu-id="c8bd6-141">在 Lync Server 2013 中，运行会议服务的服务器始终与前端服务器或 Standard Edition 服务器并置。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-141">In Lync Server 2013, the server running conferencing services is always collocated with the Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="c8bd6-142">在初始部署过程中，拓扑生成器将为您提供在拓扑中包括会议的选项。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-142">During your initial deployment, Topology Builder gives you the option to include conferencing in your topology.</span></span> <span data-ttu-id="c8bd6-143">还可以使用拓扑生成器向现有部署中添加会议。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-143">You can also use Topology Builder to add conferencing to an existing deployment.</span></span> <span data-ttu-id="c8bd6-144">有关详细信息，请参阅 [在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-144">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

<div>

## <a name="dial-in-conferencing-toplogies"></a><span data-ttu-id="c8bd6-145">电话拨入式会议拓扑</span><span class="sxs-lookup"><span data-stu-id="c8bd6-145">Dial in Conferencing Toplogies</span></span>

<span data-ttu-id="c8bd6-146">可以在以下拓扑和配置中部署电话拨入式会议：</span><span class="sxs-lookup"><span data-stu-id="c8bd6-146">You can deploy dial-in conferencing in the following topologies and configurations:</span></span>

  - <span data-ttu-id="c8bd6-147">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="c8bd6-147">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="c8bd6-148">Lync Server 2013 企业版</span><span class="sxs-lookup"><span data-stu-id="c8bd6-148">Lync Server 2013 Enterprise Edition</span></span>

  - <span data-ttu-id="c8bd6-149">有或没有企业语音</span><span class="sxs-lookup"><span data-stu-id="c8bd6-149">With or without Enterprise Voice</span></span>

<span data-ttu-id="c8bd6-150">您可以在中央站点中部署应用程序服务、会议助理应用程序和会议通知应用程序，但不能在分支站点中进行部署。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-150">You can deploy Application service, Conferencing Attendant application, and Conferencing Announcement application in a central site, but not in a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8bd6-151">如果要部署电话拨入式会议，则必须在部署 Lync Server 2013 会议的每个池中部署它。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-151">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="c8bd6-152">无需在每个池中分配访问号码，但必须在每个池中部署电话拨入式会议功能。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-152">You do not need to assign access numbers in every pool, but you must deploy the dial-in conferencing feature in every pool.</span></span> <span data-ttu-id="c8bd6-153">当用户从一个池中调用访问号码以在不同的池中加入 Lync Server 2013 会议时，此要求支持所记录的名称功能。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-153">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a><span data-ttu-id="c8bd6-154">Lync Server 2013 和 Office Web Apps 支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="c8bd6-154">Supported Topologies for Lync Server 2013 and Office Web Apps</span></span>

<span data-ttu-id="c8bd6-155">Lync Server 2013 提供了以下配置 Office Web Apps Server 的方法。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-155">Lync Server 2013 provides the following ways to configure Office Web Apps Server.</span></span> <span data-ttu-id="c8bd6-156">根据您的需要，可以：</span><span class="sxs-lookup"><span data-stu-id="c8bd6-156">Depending on your needs you can:</span></span>

  - <span data-ttu-id="c8bd6-157">**在组织的防火墙后面和同一网络区域中安装 Lync Server 2013 和 Office Web Apps Server 内部部署。**</span><span class="sxs-lookup"><span data-stu-id="c8bd6-157">**Install both Lync Server 2013 and Office Web Apps Server on-premises behind your organization’s firewall, and in the same network zone.**</span></span> <span data-ttu-id="c8bd6-158">使用此拓扑，将通过反向代理服务器提供对 Office Web Apps Server 的外部访问。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-158">With this topology, external access to Office Web Apps Server will be provided through your reverse proxy server.</span></span> <span data-ttu-id="c8bd6-159">同时在本地和组织的防火墙后面安装 Lync Server 2013 和 Office Web Apps Server (或 Office Web Apps Server 场) 。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-159">Both Lync Server 2013 and Office Web Apps Server (or an Office Web Apps Server farm) are installed on-premises and behind your organization's firewall.</span></span> <span data-ttu-id="c8bd6-160">理想情况下，应在与 Lync Server 相同的网络区域中安装 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-160">Ideally, you should install Office Web Apps Server in the same network zone as Lync Server.</span></span>
    
    <span data-ttu-id="c8bd6-161">外部 Lync 客户端可以使用反向代理服务器连接到 Lync Server 2013 和 Office Web Apps Server，这是一台接收来自 Internet 的请求并将其转发到内部网络的服务器。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-161">External Lync clients can connect to Lync Server 2013 and to Office Web Apps Server by using a reverse proxy server, which is a server that takes requests from the Internet and forwards them to the internal network.</span></span> <span data-ttu-id="c8bd6-162"> (内部客户端无需使用反向代理服务器，因为它们可直接连接到 Office Web Apps Server。如果要使用仅由 Lync Server 2013 使用的专用 Office Web Apps Server 场，则 ) 此拓扑最适用。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-162">(Internal clients do not need to use the reverse proxy server because they can connect to Office Web Apps Server directly.) This topology works best if you want to use a dedicated Office Web Apps Server farm that is only used by Lync Server 2013.</span></span>

  - <span data-ttu-id="c8bd6-163">**使用外部部署的 Office Web Apps Server**</span><span class="sxs-lookup"><span data-stu-id="c8bd6-163">**Using an externally deployed Office Web Apps Server**</span></span>
    
    <span data-ttu-id="c8bd6-164">在此拓扑中，Lync Server 2013 部署在本地，并使用在 Lync Server 网络区域外部部署的 Office Web Apps 服务器。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-164">In this topology, Lync Server 2013 is deployed on-premises, and uses an Office Web Apps Server that is deployed outside of Lync Server network zone.</span></span> <span data-ttu-id="c8bd6-165">如果 Office Web Apps Server 在公司中的多个应用程序之间共享，并且部署在要求 Lync Server 使用 Office Web Apps Server 外部接口的网络中，则可能会发生这种情况，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-165">This may happen when Office Web Apps Server is shared across multiple applications in the corporation and is deployed in a network requiring Lync Server to use the external interface of Office Web Apps Server and vice versa.</span></span>
    
    <span data-ttu-id="c8bd6-166">您无需安装反向代理服务器;相反，从 Office Web Apps Server 到 Lync Server 2013 的所有请求都将通过边缘服务器进行路由。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-166">You do not need to install a reverse proxy server; instead, all the requests from the Office Web Apps Server to Lync Server 2013 are routed through your Edge Server.</span></span> <span data-ttu-id="c8bd6-167">内部和外部 Lync 客户端都使用外部 URL 连接到 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-167">Both your internal and your external Lync clients connect to Office Web Apps Server using the external URL.</span></span>
    
    <span data-ttu-id="c8bd6-168">如果 Office Web Apps Server 部署在内部防火墙之外，则选择 " \*\*Office Web Apps server 部署在外部网络中 (即拓扑生成器中的" 外围/Internet) \*\* "。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-168">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** in Topology Builder.</span></span> <span data-ttu-id="c8bd6-169">有关更多详细信息，请参阅 [配置与 Office Web Apps server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-169">For more details see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="c8bd6-170">无论您选择什么拓扑，打开正确的防火墙端口至关重要。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-170">Regardless of the topology you select, it is critical that the correct firewall ports be opened.</span></span> <span data-ttu-id="c8bd6-171">必须确保 Office Web Apps Server、负载平衡器或 Lync Server 上的防火墙不会阻止 DNS 名称、IP 地址和端口。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-171">You must make sure that DNS names, IP addresses, and ports are not blocked by firewalls on the Office Web Apps Server, the load balancer, or Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8bd6-172">提供对 Office Web Apps Server 的外部访问权限的另一种方法是在外围网络中部署服务器。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-172">Another option for providing external access to Office Web Apps Server is to deploy the server in the perimeter network.</span></span> <span data-ttu-id="c8bd6-173">如果选择执行此操作，请注意 Office Web Apps Server 安装程序要求服务器计算机是 Active Directory 域的成员。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-173">If you elect to do this, keep in mind that Office Web Apps Server setup requires the server computer to be a member of your Active Directory domain.</span></span> <span data-ttu-id="c8bd6-174">除非您的网络策略允许外围网络中的计算机成为 Active Directory 域成员，否则建议您不要在外围网络中安装 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-174">Unless your network policy allows computers in the perimeter network to be Active Directory domain members, it is recommended that you do not install Office Web Apps Server in the perimeter network.</span></span> <span data-ttu-id="c8bd6-175">相反，应在内部网络中安装 Office Web Apps Server，并通过反向代理服务器提供外部用户访问权限。</span><span class="sxs-lookup"><span data-stu-id="c8bd6-175">Instead, you should install Office Web Apps Server in the internal network and provide external user access through your reverse proxy server.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

