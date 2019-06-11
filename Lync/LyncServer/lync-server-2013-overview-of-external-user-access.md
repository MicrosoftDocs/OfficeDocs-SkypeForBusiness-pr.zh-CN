---
title: Lync Server 2013：外部用户访问概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of external user access
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398775(v=OCS.15)
ms:contentKeyID: 48184934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a527df5a3bc7b296d17860c7a02876dbc31fbc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-external-user-access-in-lync-server-2013"></a><span data-ttu-id="ab23c-102">Lync Server 2013 中的外部用户访问概述</span><span class="sxs-lookup"><span data-stu-id="ab23c-102">Overview of external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab23c-103">_**主题上次修改时间:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="ab23c-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="ab23c-104">在本文档中, 我们使用术语 "*外部用户*" 定义从防火墙外与 lync Server 2013 和 lync 2013 用户通信的大型用户类别。</span><span class="sxs-lookup"><span data-stu-id="ab23c-104">In this documentation, we use the term *external user* to define a large category of users who communicate with your Lync Server 2013 and Lync 2013 users from outside the firewall.</span></span> <span data-ttu-id="ab23c-105">你可以授权与内部用户 (即从防火墙内登录 Lync Server 的用户) 将 Lync Server 2013 与之通信的外部用户可能包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="ab23c-105">External users that you can authorize to communicate Lync Server 2013 with internal users (that is, users who sign in to Lync Server from inside the firewall) can include the following:</span></span>

  - <span data-ttu-id="ab23c-106">\*\*\*\*   从防火墙外登录到 Lync Server 的组织的远程用户。</span><span class="sxs-lookup"><span data-stu-id="ab23c-106">**Remote users**   Users of your organization who sign in to Lync Server from outside the firewall.</span></span>

  - <span data-ttu-id="ab23c-107">**联合用户**   拥有具有受信任客户或合作伙伴组织的帐户的用户, 如 lync server 2010、lync server 2013 或 Office 通信服务器 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="ab23c-107">**Federated users**   Users who have an account with a trusted customer or partner organization, such as Lync Server 2010, Lync Server 2013 or Office Communications Server 2007 R2.</span></span> <span data-ttu-id="ab23c-108">联盟用户也可以是使用可扩展消息和状态协议 (XMPP) 的已定义合作伙伴组织的成员, 方法是通过在 Edge 服务器上的 XMPP 代理和前端服务器或池中的 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="ab23c-108">Federated users can also be members of defined partner organizations using extensible messaging and presence protocol (XMPP) by way of the XMPP proxy on the Edge Server and XMPP gateway on the Front End Server or pool.</span></span> <span data-ttu-id="ab23c-109">已定义的信任关系 (称为联合) 与 Active Directory 域服务信任关系无关或依赖于 Active Directory 域服务信任关系。</span><span class="sxs-lookup"><span data-stu-id="ab23c-109">A defined trust relationship, called a federation, is not related to or dependent upon an Active Directory Domain Services trust relationship.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ab23c-110">AOL 和 Yahoo! 的有效期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="ab23c-110">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="ab23c-111">已宣布。</span><span class="sxs-lookup"><span data-stu-id="ab23c-111">has been announced.</span></span> <span data-ttu-id="ab23c-112">有关详细信息, 请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</span><span class="sxs-lookup"><span data-stu-id="ab23c-112">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="ab23c-113">**公共即时消息连接用户**   通过公共即时消息连接服务 (Windows Live、Yahoo) 建立的联系人\!</span><span class="sxs-lookup"><span data-stu-id="ab23c-113">**Public Instant Messaging Connectivity users**   Contacts that your users establish through public instant messaging connectivity services (Windows Live, Yahoo\!</span></span> <span data-ttu-id="ab23c-114">和 AOL)。</span><span class="sxs-lookup"><span data-stu-id="ab23c-114">and AOL).</span></span>

  - <span data-ttu-id="ab23c-115">**移动用户**   是指您的组织中使用智能手机或平板电脑的用户登录到内部部署, 并且可以与其他用户类别进行通信。</span><span class="sxs-lookup"><span data-stu-id="ab23c-115">**Mobile users**   Users that are members of your organization that use a smart phone or tablet running a Lync Mobile client sign in to your internal deployment and are able to communicate with the other classes of users.</span></span> <span data-ttu-id="ab23c-116">移动用户使用通过反向代理发布的移动服务来访问内部部署。</span><span class="sxs-lookup"><span data-stu-id="ab23c-116">The mobile user uses mobility services that are published through the reverse proxy to access the internal deployment.</span></span> <span data-ttu-id="ab23c-117">有关 Lync Mobile 可用的功能和功能的详细信息, 请参阅中的移动客户[http://go.microsoft.com/fwlink/p/?LinkID=234777](http://go.microsoft.com/fwlink/p/?linkid=234777)端比较表。</span><span class="sxs-lookup"><span data-stu-id="ab23c-117">For details on features and capabilities available to Lync Mobile , see the Mobile Client Comparison Tables at [http://go.microsoft.com/fwlink/p/?LinkID=234777](http://go.microsoft.com/fwlink/p/?linkid=234777).</span></span>

  - <span data-ttu-id="ab23c-118">\*\*\*\*   在组织的 Active Directory 域服务或受支持的联盟域中没有用户帐户的匿名用户用户, 但收到了在本地会议中远程参与远程会议的邀请。</span><span class="sxs-lookup"><span data-stu-id="ab23c-118">**Anonymous users**   Users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but who have received invitations to participate remotely in an on-premises conference.</span></span>

<span data-ttu-id="ab23c-119">你的 edge 部署为以下类型的通信提供外部访问:</span><span class="sxs-lookup"><span data-stu-id="ab23c-119">Your edge deployment provides external access for the following types of communication:</span></span>

  - <span data-ttu-id="ab23c-120">**Im 和状态**   已授权的外部用户可以参与 IM 对话和会议, 并且他们可以获取有关其他人的状态的信息。</span><span class="sxs-lookup"><span data-stu-id="ab23c-120">**IM and presence**   Authorized external users can participate in IM conversations and conferences, and they can get information about one another’s presence status.</span></span> <span data-ttu-id="ab23c-121">公共 IM 服务提供商的用户可以与组织中的单个 Lync 服务器用户参与 IM 对话并访问状态信息, 但不能使用 Lync Server 参与 IM 多方会议。</span><span class="sxs-lookup"><span data-stu-id="ab23c-121">Users of public IM service providers can participate in IM conversations with individual Lync Server users in your organization and access presence information, but they cannot participate in IM multiparty conferences using Lync Server.</span></span> <span data-ttu-id="ab23c-122">它是严格的对等通信。</span><span class="sxs-lookup"><span data-stu-id="ab23c-122">It is strictly peer-to-peer communication.</span></span> <span data-ttu-id="ab23c-123">公用 IM 服务提供商的用户不支持文件传输, 并且 Windows Messenger 2011 用户 (而不是公共 IM 服务提供商的其他用户) 支持对等通信中的音频/视频。</span><span class="sxs-lookup"><span data-stu-id="ab23c-123">File transfer is not supported for users of public IM service providers, and audio/video in peer-to-peer communications is supported for Windows Messenger 2011 users, but not other users of public IM service providers.</span></span>
    
    <span data-ttu-id="ab23c-124">SIP 和 XMPP 协议均受支持。</span><span class="sxs-lookup"><span data-stu-id="ab23c-124">Both SIP and XMPP protocols are supported.</span></span> <span data-ttu-id="ab23c-125">若要为 XMPP 提供服务, 请参阅[Lync Server 2013 中的 "规划 SIP"、"XMPP 联盟" 和 "公共即时消息](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)"。</span><span class="sxs-lookup"><span data-stu-id="ab23c-125">To provide services for XMPP, see [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="ab23c-126">\*\*\*\*   授权外部用户的网络会议可参与 Lync Server 部署上托管的会议。</span><span class="sxs-lookup"><span data-stu-id="ab23c-126">**Web conferencing**   Authorized external users can participate in conferences that are hosted on your Lync Server deployment.</span></span> <span data-ttu-id="ab23c-127">可以为远程用户、联盟用户和匿名用户启用网络会议, 但公共 IM 用户不能参与会议。</span><span class="sxs-lookup"><span data-stu-id="ab23c-127">Remote users, federated users, and anonymous users can be enabled for participation in web conferencing, but public IM users cannot participate in conferences.</span></span> <span data-ttu-id="ab23c-128">根据你选择的选项, 启用网络会议的用户可以参与桌面和应用程序共享, 并且可以充当会议组织者或演示者。</span><span class="sxs-lookup"><span data-stu-id="ab23c-128">Depending on the options that you select, web conferencing-enabled users can participate in desktop and application sharing and can act as meeting organizers or presenters.</span></span>

  - <span data-ttu-id="ab23c-129">**A/V 会议**   授权的外部用户可以参与 Lync Server 部署托管的音频和视频会议。</span><span class="sxs-lookup"><span data-stu-id="ab23c-129">**A/V conferencing**   Authorized external users can participate in audio and video conferences that your Lync Server deployment hosts.</span></span> <span data-ttu-id="ab23c-130">对等通信中的音频/视频支持 Windows Messenger 2011 用户, 但不适用于公共 IM 服务提供商的其他用户。</span><span class="sxs-lookup"><span data-stu-id="ab23c-130">Audio/video in peer-to-peer communications is supported for Windows Messenger 2011 users, but not for other users of public IM service providers.</span></span>

<span data-ttu-id="ab23c-131">为了控制通信, 你可以配置一个或多个策略来定义你的组织内部和外部的用户之间的通信方式。</span><span class="sxs-lookup"><span data-stu-id="ab23c-131">In order to control communications, you can configure one or more policies that define how users inside and outside your organization communicate with each other.</span></span> <span data-ttu-id="ab23c-132">你还可以为单个内部用户或特定类型的外部用户配置设置和应用策略, 以控制与外部用户的通信。</span><span class="sxs-lookup"><span data-stu-id="ab23c-132">You can also configure settings and apply policies for individual internal users or for specific types of external users to control communications with external users.</span></span>

<span data-ttu-id="ab23c-133">Lync Server 2013 用于提供外部访问的角色:</span><span class="sxs-lookup"><span data-stu-id="ab23c-133">Lync Server 2013 roles that are used to provide external access:</span></span>

<span data-ttu-id="ab23c-134">**边缘服务器**   edge 服务器是一台服务器或服务器池, 运行允许外部访问 IM 和状态、会议、音频/视频和其他媒体 (例如, 文件传输) 服务的服务。</span><span class="sxs-lookup"><span data-stu-id="ab23c-134">**Edge Server**   The Edge Server is a server or a pool of servers that run the services that allow external access to IM and presence, conferencing, audio/video, and other media (for example, file transfer) services.</span></span> <span data-ttu-id="ab23c-135">或者, 你可以将 Edge 服务器配置为与其他 Lync Server 或 Office 通信服务器 2007 R2 部署以及其他 XMPP 部署进行联盟。</span><span class="sxs-lookup"><span data-stu-id="ab23c-135">Optionally, you can configure the Edge Server to federate with other Lync Server or Office Communications Server 2007 R2 deployments, and other XMPP deployments.</span></span> <span data-ttu-id="ab23c-136">通过 Edge 服务器启用和配置可选的公共 IM 连接功能。</span><span class="sxs-lookup"><span data-stu-id="ab23c-136">The optional public IM connectivity feature is enabled and configured through the Edge Server.</span></span>

<span data-ttu-id="ab23c-137">**导演**   控制器是运行 Lync server 2013 Director 角色的可选服务器或服务器池, 它预身份验证用户请求并将请求路由到用户的主前端服务器或前端池, 但不会在家任何用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ab23c-137">**Director**   The Director is an optional server or server pool running the Lync Server 2013 Director role that pre-authenticates user requests and routes requests to the users’ home Front End Server or Front End pool, but does not home any user accounts.</span></span>

<span data-ttu-id="ab23c-138">**反向代理**   反向代理是专用服务器的常规术语, 用于发布内部网络上可用的资源, 并从已发布的资源检索客户端的信息。</span><span class="sxs-lookup"><span data-stu-id="ab23c-138">**Reverse Proxy**   A reverse proxy is a general term for specialized servers that publish resources available on the internal network and retrieve information for clients from the published resource.</span></span> <span data-ttu-id="ab23c-139">Lync Server 2013 使用反向代理来发布许多功能, 例如会议会议、会议加入位置、通讯簿、通讯组列表扩展、下载会议内容、设备更新、移动服务等。</span><span class="sxs-lookup"><span data-stu-id="ab23c-139">Lync Server 2013 uses the reverse proxy to publish a number of features, such as conferencing meetings, conference join locations, the address book, distribution list expansion, downloading meeting content, device updates, Mobility services, and more.</span></span> <span data-ttu-id="ab23c-140">可以使用任何可满足发布必要资源位置要求的反向代理。</span><span class="sxs-lookup"><span data-stu-id="ab23c-140">Any reverse proxy that can meet the requirements for publishing the necessary resource locations can be used.</span></span> <span data-ttu-id="ab23c-141">Microsoft Forefront 威胁管理网关 (TMG) 2010 用作演示必要的发布规则的示例, 但不需要 Forefront TMG 2010。</span><span class="sxs-lookup"><span data-stu-id="ab23c-141">Microsoft Forefront Threat Management Gateway (TMG) 2010 is used as an example for the purposes of illustrating the publishing rules necessary, but Forefront TMG 2010 is not required.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ab23c-142">Lync Server 2013 支持 IPv4 和 IPv6。</span><span class="sxs-lookup"><span data-stu-id="ab23c-142">Lync Server 2013 supports both IPv4 and IPv6.</span></span> <span data-ttu-id="ab23c-143">Windows Server&nbsp;2008&nbsp;r2、Windows Server 2012 和 windows server 2012 R2 使用可以同时使用 IPv4 和 IPv6 的双重堆栈。</span><span class="sxs-lookup"><span data-stu-id="ab23c-143">Windows Server&nbsp;2008&nbsp;R2, Windows Server 2012, and Windows Server 2012 R2 use a dual stack that can use both IPv4 and IPv6 concurrently.</span></span> <span data-ttu-id="ab23c-144">这一点很重要, 因为部署从 IPv4 迁移到 IPv6 的过渡性质。</span><span class="sxs-lookup"><span data-stu-id="ab23c-144">This is important because of the transitional nature of a deployment moving from IPv4 to IPv6.</span></span> <span data-ttu-id="ab23c-145">在某些区域中, 可以支持 IPv4, 在部署的其他区域中, 可以使用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="ab23c-145">IPv4 can be supported in some areas, where in other areas of the deployment, IPv6 can be used.</span></span> <span data-ttu-id="ab23c-146">这在 Internet 和内部部署关注的地方尤其重要。</span><span class="sxs-lookup"><span data-stu-id="ab23c-146">This is especially important where the Internet and internal deployments are concerned.</span></span> <span data-ttu-id="ab23c-147">外部客户端必须通过反向代理进行通信才能使用诸如移动、会议、通讯簿下载等服务。</span><span class="sxs-lookup"><span data-stu-id="ab23c-147">External clients must communicate through the reverse proxy to use services such as mobility, meetings, address book download, and others.</span></span> <span data-ttu-id="ab23c-148">目前, Forefront 威胁管理网关2010和 Internet 安全性和加速服务器2006不支持 IPv6 寻址, 无论它们的部署操作系统版本如何。</span><span class="sxs-lookup"><span data-stu-id="ab23c-148">Currently, Forefront Threat Management Gateway 2010 and Internet Security and Acceleration Server 2006 do not support IPv6 addressing, regardless of the operating system version that they are deployed on.</span></span> <span data-ttu-id="ab23c-149">你必须相对于使用 IPv6 和 IPv4 做出相应的计划, 因为它们与外部客户端相关。</span><span class="sxs-lookup"><span data-stu-id="ab23c-149">You must plan accordingly in relation to your use of IPv6 and IPv4 as they relate to external clients.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

