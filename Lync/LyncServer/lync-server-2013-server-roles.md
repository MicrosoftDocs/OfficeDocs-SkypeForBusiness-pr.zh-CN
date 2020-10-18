---
title: Lync Server 2013 服务器角色
description: Lync Server 2013 服务器角色。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ee4636e602e5bfb8ce6eacdccb3d190f5728d1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580188"
---
# <a name="server-roles-in-lync-server-2013"></a><span data-ttu-id="d04a7-103">Lync Server 2013 中的服务器角色</span><span class="sxs-lookup"><span data-stu-id="d04a7-103">Server roles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d04a7-104">_**上次修改的主题：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="d04a7-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="d04a7-105">运行 Lync Server 的每台服务器都运行一个或多个 *服务器角色*。</span><span class="sxs-lookup"><span data-stu-id="d04a7-105">Each server running Lync Server runs one or more *server roles*.</span></span> <span data-ttu-id="d04a7-106">服务器角色是由该服务器提供的一组已定义的 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="d04a7-106">A server role is a defined set of Lync Server functionalities provided by that server.</span></span> <span data-ttu-id="d04a7-107">无需在网络中部署所有可用服务器角色。</span><span class="sxs-lookup"><span data-stu-id="d04a7-107">You do not need to deploy all available server roles in your network.</span></span> <span data-ttu-id="d04a7-108">只安装包含您想要的功能的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="d04a7-108">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="d04a7-109">即使您不熟悉 Lync Server 中的服务器角色，规划工具也可以根据您所需的功能，为您提供针对您需要部署的服务器的最佳解决方案。</span><span class="sxs-lookup"><span data-stu-id="d04a7-109">Even if you are not familiar with server roles in Lync Server, the Planning Tool can guide you to the best solution for the servers that you need to deploy, based on the features that you want.</span></span> <span data-ttu-id="d04a7-110">本节简要概述了服务器角色及其提供的常规功能：</span><span class="sxs-lookup"><span data-stu-id="d04a7-110">This section provides a brief overview of the server roles and the general features that they provide:</span></span>

  - <span data-ttu-id="d04a7-111">Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="d04a7-111">Standard Edition Server</span></span>

  - <span data-ttu-id="d04a7-112">前端服务器和后端服务器</span><span class="sxs-lookup"><span data-stu-id="d04a7-112">Front End Server and Back End Server</span></span>

  - <span data-ttu-id="d04a7-113">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="d04a7-113">Edge Server</span></span>

  - <span data-ttu-id="d04a7-114">中介服务器</span><span class="sxs-lookup"><span data-stu-id="d04a7-114">Mediation Server</span></span>

  - <span data-ttu-id="d04a7-115">控制器</span><span class="sxs-lookup"><span data-stu-id="d04a7-115">Director</span></span>

  - <span data-ttu-id="d04a7-116">持久聊天前端服务器</span><span class="sxs-lookup"><span data-stu-id="d04a7-116">Persistent Chat Front End Server</span></span>

  - <span data-ttu-id="d04a7-117">持久聊天存储（持久聊天后端服务器）</span><span class="sxs-lookup"><span data-stu-id="d04a7-117">Persistent Chat Store (Persistent Chat Back End Server)</span></span>

  - <span data-ttu-id="d04a7-118">持久聊天合规性存储（持久聊天合规性后端服务器）</span><span class="sxs-lookup"><span data-stu-id="d04a7-118">Persistent Chat Compliance Store (Persistent Chat Compliance Back End Server)</span></span>

<span data-ttu-id="d04a7-119">对于大多数的服务器角色，要获得可伸缩性和高可用性，可部署全部运行同一服务器角色的多台服务器的“池”\*\*。</span><span class="sxs-lookup"><span data-stu-id="d04a7-119">For most server roles, for scalability and high availability you can deploy *pools* of multiple servers all running the same server role.</span></span> <span data-ttu-id="d04a7-120">池中的每台服务器必须运行一个或多个相同的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="d04a7-120">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="d04a7-121">对于 Lync Server 中的大多数类型的池，您必须部署负载平衡器，以在池中的各个服务器之间传播流量。</span><span class="sxs-lookup"><span data-stu-id="d04a7-121">For most types of pools in Lync Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="d04a7-122">Lync Server 同时支持域名系统 (DNS) 负载平衡和硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="d04a7-122">Lync Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

<div>

## <a name="standard-edition-server"></a><span data-ttu-id="d04a7-123">Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="d04a7-123">Standard Edition Server</span></span>

<span data-ttu-id="d04a7-124">Standard Edition Server 是为小型组织以及大型组织的试验项目而设计的。</span><span class="sxs-lookup"><span data-stu-id="d04a7-124">The Standard Edition server is designed for small organizations, and for pilot projects of large organizations.</span></span> <span data-ttu-id="d04a7-125">它启用了 Lync Server 的许多功能，包括所需的数据库，以在单台服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="d04a7-125">It enables many of the features of Lync Server, including the necessary databases, to run on a single server.</span></span> <span data-ttu-id="d04a7-126">这使您能够以更低的成本实现 Lync Server 功能，但不提供真正的高可用性解决方案。</span><span class="sxs-lookup"><span data-stu-id="d04a7-126">This enables you to have Lync Server functionality for a lower cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="d04a7-127">通过 Standard Edition server，您可以使用即时消息 (IM) 、状态、会议和企业语音，所有运行在一台服务器上。</span><span class="sxs-lookup"><span data-stu-id="d04a7-127">Standard Edition server enables you to use instant messaging (IM), presence, conferencing, and Enterprise Voice, all running on one server.</span></span>

<span data-ttu-id="d04a7-128">对于高可用性解决方案，请使用 Lync Server Enterprise Edition。</span><span class="sxs-lookup"><span data-stu-id="d04a7-128">For a high-availability solution, use Lync Server Enterprise Edition.</span></span>

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="d04a7-129">前端服务器和后端服务器</span><span class="sxs-lookup"><span data-stu-id="d04a7-129">Front End Server and Back End Server</span></span>

<span data-ttu-id="d04a7-130">在 Lync Server Enterprise Edition 中，前端服务器是核心服务器角色，并运行许多基本的 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="d04a7-130">In Lync Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Lync Server functions.</span></span> <span data-ttu-id="d04a7-131">前端服务器和后端服务器是在任何 Lync Server Enterprise Edition 部署中唯一需要的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="d04a7-131">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Lync Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="d04a7-p106">“前端池”\*\* 是一组配置相同的前端服务器，其协同工作为公用组用户提供服务。由多个运行同一角色的服务器构成的池提供可伸缩性和故障转移功能。</span><span class="sxs-lookup"><span data-stu-id="d04a7-p106">A *Front End pool* is a set of Front End Servers, configured identically, that work together to provide services for a common group of users. A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="d04a7-134">前端服务器包括以下功能：</span><span class="sxs-lookup"><span data-stu-id="d04a7-134">The Front End Server includes the following:</span></span>

  - <span data-ttu-id="d04a7-135">用户身份验证和注册</span><span class="sxs-lookup"><span data-stu-id="d04a7-135">User authentication and registration</span></span>

  - <span data-ttu-id="d04a7-136">状态信息和联系人卡片交换</span><span class="sxs-lookup"><span data-stu-id="d04a7-136">Presence information and contact card exchange</span></span>

  - <span data-ttu-id="d04a7-137">通讯簿服务和通讯组列表扩展</span><span class="sxs-lookup"><span data-stu-id="d04a7-137">Address book services and distribution list expansion</span></span>

  - <span data-ttu-id="d04a7-138">IM 功能，包括多方 IM 会议</span><span class="sxs-lookup"><span data-stu-id="d04a7-138">IM functionality, including multiparty IM conferences</span></span>

  - <span data-ttu-id="d04a7-139">Web 会议、PSTN 电话拨入式会议和 A/V 会议（如果部署）</span><span class="sxs-lookup"><span data-stu-id="d04a7-139">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed)</span></span>

  - <span data-ttu-id="d04a7-140">应用程序托管，对于 Lync Server (附带的两个应用程序，例如会议助理和响应组应用程序) 和第三方应用程序</span><span class="sxs-lookup"><span data-stu-id="d04a7-140">Application hosting, for both applications included with Lync Server (for example, Conferencing Attendant and Response Group application), and third-party applications</span></span>

  - <span data-ttu-id="d04a7-141">（可选）监控功能，用于以呼叫详细记录 (CDR) 和呼叫错误记录 (CER) 形式收集使用信息。</span><span class="sxs-lookup"><span data-stu-id="d04a7-141">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="d04a7-142">此信息提供了有关媒体质量 (音频和视频) 对企业语音呼叫和 A/V 会议进行网络连接的指标。</span><span class="sxs-lookup"><span data-stu-id="d04a7-142">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

  - <span data-ttu-id="d04a7-143">用于支持基于 Web 的任务的 Web 组件，如 Web 计划程序和联接启动器。</span><span class="sxs-lookup"><span data-stu-id="d04a7-143">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

  - <span data-ttu-id="d04a7-144">（可选）存档功能，用于存档 IM 通信和会议内容（出于合规性考虑）。</span><span class="sxs-lookup"><span data-stu-id="d04a7-144">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="d04a7-145">有关详细信息，请参阅规划文档中的在 [Lync Server 2013 中规划存档](lync-server-2013-planning-for-archiving.md) 。</span><span class="sxs-lookup"><span data-stu-id="d04a7-145">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>
    
    <span data-ttu-id="d04a7-146">在 Lync Server 2010 和早期版本中，监视和存档是独立的服务器角色，而不是前端服务器上的并置。</span><span class="sxs-lookup"><span data-stu-id="d04a7-146">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

  - <span data-ttu-id="d04a7-147">（可选）如果启用持久聊天，则包括用于聊天室管理的持久聊天 Web 服务和用于文件上载/下载的持久聊天 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="d04a7-147">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="d04a7-p109">前端池还是用户和会议数据的主存储。每个用户的相关信息将在池中的三个前端服务器之间复制，并将在后端服务器上进行备份。</span><span class="sxs-lookup"><span data-stu-id="d04a7-p109">Front End Pools are also the primary store for user and conference data. Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="d04a7-150">此外，部署中的一个前端池还运行 *中央管理服务器*，该服务器管理基本配置数据并将其部署到运行 Lync Server 的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="d04a7-150">Additionally, one Front End pool in the deployment also runs the *Central Management Server*, which manages and deploys basic configuration data to all servers running Lync Server.</span></span> <span data-ttu-id="d04a7-151">中央管理服务器还提供 Lync Server 命令行管理程序和文件传输功能。</span><span class="sxs-lookup"><span data-stu-id="d04a7-151">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="d04a7-152">后端服务器是运行 Microsoft SQL Server 的数据库服务器，可为前端池提供数据库服务。</span><span class="sxs-lookup"><span data-stu-id="d04a7-152">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="d04a7-153">后端服务器既可用作池的用户和会议数据的备份存储，又可用作其他数据库（如响应组数据库）的主存储。</span><span class="sxs-lookup"><span data-stu-id="d04a7-153">The Back End Servers serve as backup stores for the pool’s user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="d04a7-154">可以拥有一台后端服务器，但建议使用 SQL Server 镜像的解决方案进行故障转移。</span><span class="sxs-lookup"><span data-stu-id="d04a7-154">You can have a single Back End Server, but a solution that uses SQL Server mirroring is recommended for failover.</span></span> <span data-ttu-id="d04a7-155">后端服务器不运行任何 Lync Server 软件。</span><span class="sxs-lookup"><span data-stu-id="d04a7-155">Back End Servers do not run any Lync Server software.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d04a7-156">我们不建议将并置 Lync Server 数据库与其他数据库一起使用。</span><span class="sxs-lookup"><span data-stu-id="d04a7-156">We do not recommend collocating Lync Server databases with other databases.</span></span> <span data-ttu-id="d04a7-157">如果您这样做，可能会影响可用性和性能。</span><span class="sxs-lookup"><span data-stu-id="d04a7-157">If you do so, availability and performance may be affected.</span></span>



</div>

<span data-ttu-id="d04a7-158">存储在后端服务器数据库中的信息包括状态信息、用户的联系人列表、包含所有当前会议状态相关的永久数据的会议数据，以及会议安排数据。</span><span class="sxs-lookup"><span data-stu-id="d04a7-158">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="d04a7-159">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="d04a7-159">Edge Server</span></span>

<span data-ttu-id="d04a7-160">边缘服务器使您的用户能够与组织的防火墙之外的用户进行通信和协作。</span><span class="sxs-lookup"><span data-stu-id="d04a7-160">Edge Server enables your users to communicate and collaborate with users outside the organization’s firewalls.</span></span> <span data-ttu-id="d04a7-161">这些外部用户可以包括当前在异地工作的组织自己的用户、来自联盟合作伙伴组织的用户以及已被邀请加入托管在 Lync Server 部署中的会议的外部用户。</span><span class="sxs-lookup"><span data-stu-id="d04a7-161">These external users can include the organization’s own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Lync Server deployment.</span></span> <span data-ttu-id="d04a7-162">边缘服务器还支持与公共 IM 连接服务（包括 Windows Live、AOL、Yahoo \! 和 Google 谈话）的连接。</span><span class="sxs-lookup"><span data-stu-id="d04a7-162">Edge Server also enables connectivity to public IM connectivity services, including Windows Live, AOL, Yahoo\!, and Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="d04a7-163">从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证 ( "PIC USL" ) 不再可用于购买新的或更新的协议。</span><span class="sxs-lookup"><span data-stu-id="d04a7-163">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="d04a7-164">拥有主动许可证的客户将能够继续与 Yahoo！联合联合</span><span class="sxs-lookup"><span data-stu-id="d04a7-164">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="d04a7-165">信使，直到服务关闭日期。</span><span class="sxs-lookup"><span data-stu-id="d04a7-165">Messenger until the service shut down date.</span></span> <span data-ttu-id="d04a7-166">AOL 和 Yahoo！的生命周期结束日期为2014年6月</span><span class="sxs-lookup"><span data-stu-id="d04a7-166">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="d04a7-167">已宣布。</span><span class="sxs-lookup"><span data-stu-id="d04a7-167">has been announced.</span></span> <span data-ttu-id="d04a7-168">有关详细信息，请参阅 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</span><span class="sxs-lookup"><span data-stu-id="d04a7-168">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="d04a7-169">PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。</span><span class="sxs-lookup"><span data-stu-id="d04a7-169">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="d04a7-170">Messenger.</span><span class="sxs-lookup"><span data-stu-id="d04a7-170">Messenger.</span></span> <span data-ttu-id="d04a7-171">Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</span><span class="sxs-lookup"><span data-stu-id="d04a7-171">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="d04a7-172">Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。</span><span class="sxs-lookup"><span data-stu-id="d04a7-172">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="d04a7-173">与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。</span><span class="sxs-lookup"><span data-stu-id="d04a7-173">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="d04a7-174">Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</span><span class="sxs-lookup"><span data-stu-id="d04a7-174">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="d04a7-175">部署边缘服务器还将启用移动服务，此服务支持移动设备上的 Lync 功能。</span><span class="sxs-lookup"><span data-stu-id="d04a7-175">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="d04a7-176">用户可以使用受支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备来执行发送和接收即时消息、查看联系人和查看状态等活动。</span><span class="sxs-lookup"><span data-stu-id="d04a7-176">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="d04a7-177">此外，移动设备还支持某些企业语音功能，例如，“单击加入会议”、“单位电话呼叫”、“一号通”、“语音邮件”和“错过的呼叫”。</span><span class="sxs-lookup"><span data-stu-id="d04a7-177">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="d04a7-178">移动功能还支持针对不支持在后台运行的应用程序的移动设备的*推送通知*。</span><span class="sxs-lookup"><span data-stu-id="d04a7-178">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="d04a7-179">推送通知是一类发送给移动设备的有关当移动设备处于不活动状态时发生的事件的通知。</span><span class="sxs-lookup"><span data-stu-id="d04a7-179">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="d04a7-180">边缘服务器还包括完全集成的可扩展消息传递和状态协议 (XMPP) 代理，以及前端服务器上包含的 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="d04a7-180">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="d04a7-181">您可以配置这些 XMPP 组件以使 Lync Server 2013 用户能够添加来自基于 XMPP 的合作伙伴的联系人 (例如，Google 谈话) 用于即时消息和状态。</span><span class="sxs-lookup"><span data-stu-id="d04a7-181">You can configure these XMPP components to enable your Lync Server 2013 users to add contacts from XMPP-based partners (such as Google Talk) for instant messaging and presence.</span></span>

<span data-ttu-id="d04a7-182">有关详细信息，请参阅规划文档中的在 [Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md) 。</span><span class="sxs-lookup"><span data-stu-id="d04a7-182">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="d04a7-183">中介服务器</span><span class="sxs-lookup"><span data-stu-id="d04a7-183">Mediation Server</span></span>

<span data-ttu-id="d04a7-184">中介服务器是实施企业语音和电话拨入式会议所必需的组件。</span><span class="sxs-lookup"><span data-stu-id="d04a7-184">Mediation Server is a necessary component for implementing Enterprise Voice and dial-in conferencing.</span></span> <span data-ttu-id="d04a7-185">中介服务器转换信号，在某些配置中，内部 Lync 服务器基础结构和公共交换电话网络之间的媒体 (PSTN) 网关、ip-pbx 或会话初始协议 (SIP) 中继。</span><span class="sxs-lookup"><span data-stu-id="d04a7-185">Mediation Server translates signaling, and, in some configurations, media between your internal Lync Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="d04a7-186">您可以运行在前端服务器所在的服务器上并置的中介服务器，也可以运行分隔到单独的中介服务器池中的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="d04a7-186">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="d04a7-187">有关详细信息，请参阅规划文档中的 " [在 Lync server 2013 中中介服务器组件](lync-server-2013-mediation-server-component.md) "。</span><span class="sxs-lookup"><span data-stu-id="d04a7-187">For details, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="d04a7-188">控制器</span><span class="sxs-lookup"><span data-stu-id="d04a7-188">Director</span></span>

<span data-ttu-id="d04a7-189">控制器可以对 Lync Server 用户请求进行身份验证，但他们不会在家用户帐户或提供状态或会议服务。</span><span class="sxs-lookup"><span data-stu-id="d04a7-189">Directors can authenticate Lync Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="d04a7-190">控制器对于增强支持外部用户访问的部署中的安全性最有用。</span><span class="sxs-lookup"><span data-stu-id="d04a7-190">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="d04a7-191">控制器可在将请求发送到内部服务器之前对请求进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="d04a7-191">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="d04a7-192">对于拒绝服务攻击，此攻击将终止于控制器且无法到达前端服务器。</span><span class="sxs-lookup"><span data-stu-id="d04a7-192">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span> <span data-ttu-id="d04a7-193">有关详细信息，请参阅规划文档中的 [Lync Server 2013 中的 Director 方案](lync-server-2013-scenarios-for-the-director.md) 。</span><span class="sxs-lookup"><span data-stu-id="d04a7-193">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-roles"></a><span data-ttu-id="d04a7-194">持久聊天服务器角色</span><span class="sxs-lookup"><span data-stu-id="d04a7-194">Persistent Chat Server Roles</span></span>

<span data-ttu-id="d04a7-p121">利用持久聊天，用户可以参加持续进行的、基于主题的多方对话。持久聊天前端服务器可运行持久聊天服务。持久聊天后端服务器可存储聊天历史记录数据以及有关类别和聊天室的信息。可选持久聊天合规性后端服务器可存储聊天内容和合规性事件以实现合规性。</span><span class="sxs-lookup"><span data-stu-id="d04a7-p121">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time. The Persistent Chat Front End Server runs the persistent chat service. The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms. The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="d04a7-199">运行 Lync Server Standard Edition 的服务器也可以在同一台服务器上运行持久聊天并置。</span><span class="sxs-lookup"><span data-stu-id="d04a7-199">Servers running Lync Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="d04a7-200">您不能并置持久聊天前端服务器与 Enterprise Edition 前端服务器。</span><span class="sxs-lookup"><span data-stu-id="d04a7-200">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="d04a7-201">有关详细信息，请参阅 [在 Lync server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="d04a7-201">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d04a7-202">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d04a7-202">See Also</span></span>


[<span data-ttu-id="d04a7-203">Lync Server 2013 中的中介服务器组件</span><span class="sxs-lookup"><span data-stu-id="d04a7-203">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  


[<span data-ttu-id="d04a7-204">在 Lync Server 2013 中规划存档</span><span class="sxs-lookup"><span data-stu-id="d04a7-204">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
[<span data-ttu-id="d04a7-205">在 Lync Server 2013 中规划外部用户访问</span><span class="sxs-lookup"><span data-stu-id="d04a7-205">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="d04a7-206">Lync Server 2013 中的控制器方案</span><span class="sxs-lookup"><span data-stu-id="d04a7-206">Scenarios for the Director in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-the-director.md)  
[<span data-ttu-id="d04a7-207">在 Lync Server 2013 中规划持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="d04a7-207">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

