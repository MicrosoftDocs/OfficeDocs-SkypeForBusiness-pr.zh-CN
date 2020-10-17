---
title: Lync Server 2013：新的持久聊天服务器功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd9288fea9105be27428ac94d992de6e147f4900
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534179"
---
# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a><span data-ttu-id="ed5ea-102">Lync Server 2013 中新的持久聊天服务器功能</span><span class="sxs-lookup"><span data-stu-id="ed5ea-102">New Persistent Chat Server features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed5ea-103">_**上次修改的主题：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="ed5ea-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="ed5ea-104">Lync Server 2013、持久聊天服务器使您能够参与在一段时间内保持的基于主题的多个会话。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="ed5ea-105">持久聊天服务器可帮助您的组织执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ed5ea-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="ed5ea-106">改善分散在不同地理位置的跨部门团队间的通信</span><span class="sxs-lookup"><span data-stu-id="ed5ea-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="ed5ea-107">扩大信息的知晓和参与范围</span><span class="sxs-lookup"><span data-stu-id="ed5ea-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="ed5ea-108">改善组织扩大后的通信</span><span class="sxs-lookup"><span data-stu-id="ed5ea-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="ed5ea-109">减少信息过载</span><span class="sxs-lookup"><span data-stu-id="ed5ea-109">Reduce information overload</span></span>

  - <span data-ttu-id="ed5ea-110">提高信息感知能力</span><span class="sxs-lookup"><span data-stu-id="ed5ea-110">Improve information awareness</span></span>

  - <span data-ttu-id="ed5ea-111">扩大重要知识和信息的传播范围</span><span class="sxs-lookup"><span data-stu-id="ed5ea-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="ed5ea-112">Lync Server 2013、持久聊天服务器在 Microsoft 365 或 Office 365 中不可用。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-112">Lync Server 2013, Persistent Chat Server is not available in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="ed5ea-113">目前，它仅适用于本地 Lync 2013 客户。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-113">At this time, it is available only to on-premise Lync 2013 customers.</span></span>

<span data-ttu-id="ed5ea-114">在 Lync 2013 中，持久聊天功能集成到 Lync 2013 客户端中。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-114">In Lync 2013, Persistent Chat functionality is integrated into the Lync 2013 client.</span></span> <span data-ttu-id="ed5ea-115">因此，用户可以访问 Lync 2013 客户端中的即时消息/状态、音频/视频、会议和持久聊天。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-115">As a result, users have access to Instant Messaging/Presence, Audio/Video, Conferencing, and Persistent Chat all in the Lync 2013 client.</span></span> <span data-ttu-id="ed5ea-116">有关 Lync 2013 客户端的详细信息，请参阅 <https://go.microsoft.com/fwlink/p/?linkid=270877> 。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-116">For more information about the Lync 2013 client, see <https://go.microsoft.com/fwlink/p/?linkid=270877>.</span></span>

<span data-ttu-id="ed5ea-117">本主题介绍新版本的 Lync Server 2013、持久聊天服务器和早期版本 (Microsoft Lync Server 2010，Group Chat) 之间的功能更改，其中包括：</span><span class="sxs-lookup"><span data-stu-id="ed5ea-117">This topic describes feature changes between the new version of Lync Server 2013, Persistent Chat Server and the previous version (Microsoft Lync Server 2010, Group Chat), including:</span></span>

  - <span data-ttu-id="ed5ea-118">在 Lync Server 控制面板中提供管理体验，并消除组聊天管理工具</span><span class="sxs-lookup"><span data-stu-id="ed5ea-118">Provide an administrative experience in Lync Server Control Panel, and eliminate the Group Chat Admin Tool</span></span>

  - <span data-ttu-id="ed5ea-119">通过消除组聊天配置工具将持久聊天服务器的配置设置集成到拓扑生成器中</span><span class="sxs-lookup"><span data-stu-id="ed5ea-119">Integrate configuration settings for Persistent Chat Server into Topology Builder by eliminating the Group Chat Configuration tool</span></span>

  - <span data-ttu-id="ed5ea-120">从以前版本的持久聊天服务器中轻松迁移和升级</span><span class="sxs-lookup"><span data-stu-id="ed5ea-120">Ease migration and upgrade from previous versions of Persistent Chat Server</span></span>

  - <span data-ttu-id="ed5ea-121">提供高可用性和灾难恢复解决方案</span><span class="sxs-lookup"><span data-stu-id="ed5ea-121">Provide high availability and disaster recovery solutions</span></span>

<span data-ttu-id="ed5ea-122">有关持久聊天服务器的最新版本的其他详细信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="ed5ea-122">For additional details about the latest version of Persistent Chat Server, see the following:</span></span>

  - <span data-ttu-id="ed5ea-123">持续聊天帮助提供了 <https://go.microsoft.com/fwlink/p/?linkid=270945> 持久聊天功能的详细列表，以及它们的工作方式，以及如何在运行持久聊天服务器的情况下使用它们。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-123">The Persistent Chat Help at <https://go.microsoft.com/fwlink/p/?linkid=270945> which provides a detailed list of Persistent Chat features, how they work, and how to use them while running Persistent Chat Server.</span></span>

  - <span data-ttu-id="ed5ea-124">在规划文档中 [规划 Lync server 2013 中的持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md) ，在 [lync Server 2013 中部署持久聊天服务器](lync-server-2013-deploying-persistent-chat-server.md) 在部署文档中， [从 Lync server 2010、组聊天版或 Office 通信服务器迁移到 Lync Server 2013、持久聊天服务器在](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) 迁移文档中2007以及在操作文档中 [管理 lync server 2013、持久聊天服务器](managing-lync-server-2013-persistent-chat-server.md) ，所有这些操作均提供有关设置持久聊天服务器的说明。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-124">The [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation, [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in the Migration documentation, and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) in the Operations documentation, all of which provide instructions for setting up Persistent Chat Server.</span></span>

  - <span data-ttu-id="ed5ea-125">持久聊天服务器 Documentation.msi 文件 (Windows Installer 文件) 允许用户访问有关持久聊天服务器的全面脱机文档。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-125">The Persistent Chat Server Documentation.msi file (Windows Installer file) lets users access comprehensive offline documentation about Persistent Chat Server.</span></span>

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a><span data-ttu-id="ed5ea-126">持久聊天服务器的关键拓扑更改</span><span class="sxs-lookup"><span data-stu-id="ed5ea-126">Key Topology Changes for Persistent Chat Server</span></span>

<span data-ttu-id="ed5ea-127">持久聊天服务器的以下高级别更改包括：</span><span class="sxs-lookup"><span data-stu-id="ed5ea-127">The following high-level changes for Persistent Chat Server include:</span></span>

<span data-ttu-id="ed5ea-128">持久聊天服务器现在是一个服务器角色。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-128">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="ed5ea-129">在 Microsoft Lync Server 2010 中，组聊天服务器是 Microsoft Lync Server 2010 的第三方受信任应用程序。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-129">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="ed5ea-130">可以使用拓扑生成器将持久聊天添加到 Lync Server 2013 拓扑。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-130">Persistent Chat can be added to your Lync Server 2013 topology by using Topology Builder.</span></span> <span data-ttu-id="ed5ea-131">在 Lync Server 2013 中，持久聊天服务器功能是通过使用三个新的服务器角色来实现的：</span><span class="sxs-lookup"><span data-stu-id="ed5ea-131">In Lync Server 2013, Persistent Chat Server functionality is implemented by using three new server roles:</span></span>

  - <span data-ttu-id="ed5ea-132">**PersistentChatService：** 这是持续聊天的前端角色。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-132">**PersistentChatService:** This is the front end role for Persistent Chat.</span></span> <span data-ttu-id="ed5ea-133">在标准版部署中，持久聊天服务器服务角色是由引导程序部署的 Standard Edition 服务器上的并置，与任何其他 Lync Server 角色一样。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-133">In Standard Edition deployments, Persistent Chat Server Service Role is collocated on the Standard Edition server deployed by Bootstrapper, like any other Lync Server role.</span></span> <span data-ttu-id="ed5ea-134">在企业版部署中，持久聊天服务角色是按引导程序在独立计算机上部署的，与任何其他 Lync Server 角色一样。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-134">In Enterprise Edition deployments, Persistent Chat Service Role is deployed on stand-alone computers by Bootstrapper, like any other Lync Server role.</span></span>

  - <span data-ttu-id="ed5ea-135">**PersistentChatStore：** 与持久聊天内容数据库对应的后端服务器，其中存储了所有聊天内容。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-135">**PersistentChatStore:** Back End Server that corresponds to the Persistent Chat content database, where all the chat content is stored.</span></span>

  - <span data-ttu-id="ed5ea-136">**PersistentChatComplianceStore：** 与持久聊天合规性数据库相对应的后端服务器角色，其中存储了所有合规性事件。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-136">**PersistentChatComplianceStore:** Back End Server role that corresponds to the Persistent Chat Compliance database, where all compliance events are stored.</span></span>

<span data-ttu-id="ed5ea-137">这些持久聊天服务器角色是可选的，仅供需要全面持久聊天服务器功能的客户安装。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-137">These Persistent Chat Server roles are optional, and are installed only by customers who want comprehensive Persistent Chat Server functionality.</span></span> <span data-ttu-id="ed5ea-138">仅当您选择部署持久聊天合规性时，才需要 **PersistentChatComplianceStore** 角色。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-138">The **PersistentChatComplianceStore** role is needed only if you choose to deploy Persistent Chat Compliance.</span></span>

<span data-ttu-id="ed5ea-139">**PersistentChatService**角色运行两项服务：</span><span class="sxs-lookup"><span data-stu-id="ed5ea-139">The **PersistentChatService** role runs two services:</span></span>

  - <span data-ttu-id="ed5ea-140">持久聊天服务</span><span class="sxs-lookup"><span data-stu-id="ed5ea-140">Persistent Chat service</span></span>

  - <span data-ttu-id="ed5ea-141">持久聊天合规性服务</span><span class="sxs-lookup"><span data-stu-id="ed5ea-141">Persistent Chat Compliance service</span></span>

<span data-ttu-id="ed5ea-142">在每台持久聊天服务器上运行这些服务，可为多服务器持久聊天服务器池中的这些服务提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-142">Having these services run on each Persistent Chat Server provides high availability for these services in a multiserver Persistent Chat Server pool.</span></span>

<span data-ttu-id="ed5ea-143">此外，为了支持在持久聊天聊天室中使用文件上载和下载，持久聊天服务器包含 web 服务。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-143">Additionally, to support the file upload and download in Persistent Chat rooms, Persistent Chat Server includes a web service.</span></span> <span data-ttu-id="ed5ea-144">以前，在持久聊天服务器、前端服务器和所需的 Internet 信息服务 (IIS) 将此服务作为必备组件安装在并置中。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-144">Previously, this service was collocated on the Persistent Chat Server, Front End Server and required Internet Information Services (IIS) to be installed as a prerequisite.</span></span> <span data-ttu-id="ed5ea-145">在 Lync Server 2013 持久聊天服务器中，文件上传/下载 web 服务与 Lync Server 2013 前端服务器并置。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-145">In Lync Server 2013 Persistent Chat Server, the File Upload/Download web service is collocated with the Lync Server 2013 Front End Server.</span></span> <span data-ttu-id="ed5ea-146">这一副作用，Internet 信息服务 (IIS) 不再是持久聊天服务器的先决条件。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-146">As a side effect, Internet Information Services (IIS) is no longer a prerequisite for Persistent Chat Server.</span></span> <span data-ttu-id="ed5ea-147">在 Internet 信息服务 (IIS) 管理器中，文件上载/下载 web 服务被标识为 **PersistentChat** 。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-147">The File Upload/Download web service is identified as **PersistentChat** in the Internet Information Services (IIS) Manager.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ed5ea-148"><STRONG>PersistentChatService</STRONG> &nbsp; 仅当该前端服务器是 Standard Edition 前端服务器时，PersistentChatService 角色才能在与 Lync Server 2013 前端服务器相同的服务器上运行 &nbsp; 。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-148">The <STRONG>PersistentChatService</STRONG> role can run on the same server as a Lync Server 2013&nbsp;Front End Server only if that Front End Server is a Standard Edition&nbsp;Front End Server.</span></span> <span data-ttu-id="ed5ea-149"><STRONG>PersistentChatService</STRONG>角色无法独立于 Lync server 2013 &nbsp; 前端服务器运行。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-149">The <STRONG>PersistentChatService</STRONG> role cannot run independently of a Lync Server 2013&nbsp;Front End Server.</span></span> <span data-ttu-id="ed5ea-150">它只能在 Lync Server 2013 部署的上下文中进行安装。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-150">It can be installed only in the context of a Lync Server 2013 deployment.</span></span>



</div>

<span data-ttu-id="ed5ea-151">在持久聊天服务器中，已消除了查找服务。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-151">In Persistent Chat Server, Lookup service has been eliminated.</span></span> <span data-ttu-id="ed5ea-152">在 Lync Server 2010 中，"组聊天" 中，查找服务在每个组聊天服务器前端服务器上运行，并执行到其中一个通道服务器的路由。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-152">In Lync Server 2010, Group Chat, the Lookup service ran on every Group Chat Server Front End Server, and performed routing to one of the Channel Servers.</span></span> <span data-ttu-id="ed5ea-153">Lync Server 2013 依靠 contact 对象进行路由，其中每个持久聊天服务器池都由 Lync Server 前端服务器使用的 contact 对象表示并将请求路由到相应的持久聊天服务器池，以及在池中运行持久聊天服务器的一台计算机。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-153">Lync Server 2013 relies on routing by using contact objects, where each Persistent Chat Server pool is represented by a contact object that is used by the Lync Server Front End Servers to identify and route requests to an appropriate Persistent Chat Server pool, and to one of the computers running Persistent Chat Server in the pool.</span></span>

<span data-ttu-id="ed5ea-154">在 Lync Server 2013 中，存在合规性服务修改：</span><span class="sxs-lookup"><span data-stu-id="ed5ea-154">In Lync Server 2013, there are Compliance service modifications:</span></span>

  - <span data-ttu-id="ed5ea-155">在 Lync Server 2010 中，合规性服务独立 (非并置) 运行，并且仅在一台服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-155">In Lync Server 2010, the Compliance service ran stand-alone (non-collocated), and only on a single server.</span></span> <span data-ttu-id="ed5ea-156">合规性服务现在在所有持久聊天服务器前端服务器上运行，并在持久聊天服务的旁边运行，因此在多服务器持久聊天服务器池中提供了高可用性。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-156">The Compliance service now runs on all the Persistent Chat Server Front End Servers, alongside the Persistent Chat service, and thereby provides high availability in a multiserver Persistent Chat Server pool.</span></span> <span data-ttu-id="ed5ea-157">可以将单个合规性适配器配置为将数据从合规性数据库和其他系统中的一个系统中提取到另一个系统中 (XML 文件、Exchange 托管的存档，等等) 。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-157">A single compliance adapter can be configured to extract data from the compliance database and into one of the other systems (XML file, Exchange-hosted archives, and so on).</span></span> <span data-ttu-id="ed5ea-158">持久聊天服务器包括 XML 适配器。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-158">Persistent Chat Server includes an XML adapter.</span></span>

  - <span data-ttu-id="ed5ea-159">消息队列 (也称为持续聊天服务共享的 MSMQ) 队列，而每台持久聊天服务器前端服务器上的合规性服务现在是仅由两个服务共享的专用队列。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-159">The Message Queuing (also known as MSMQ) queue that is shared by the Persistent Chat service and the Compliance service on each Persistent Chat Server Front End Server is now a private queue shared only by the two services.</span></span> <span data-ttu-id="ed5ea-160">所有合规性服务均写入相同的合规性后端数据库。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-160">All compliance services write to the same Compliance Back End database.</span></span> <span data-ttu-id="ed5ea-161">它们也会从该数据库中读取，目的是将数据发送到其适配器实例。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-161">They also all read from that database, for the purpose of sending the data to their instance of the adapter.</span></span> <span data-ttu-id="ed5ea-162">合规性后端服务器表示为新的后端服务器角色。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-162">The Compliance Back End Server is represented as a new Back End Server role.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ed5ea-163">与在以前的版本中一样，所有合规性数据只处理一次。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-163">As in previous versions, all compliance data is processed only once.</span></span> <span data-ttu-id="ed5ea-164">数据可能由在各种 Lync Server 2013、持久聊天服务器计算机上运行的合规性服务调用的任何适配器实例进行处理。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-164">The data may be processed by any of the adapter instances invoked by the compliance service running on the various Lync Server 2013, Persistent Chat Server computers.</span></span> <span data-ttu-id="ed5ea-165">在持久聊天服务器中，任何一个适配器实例都可以处理数据。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-165">In Persistent Chat Server, any one of the adapter instances could process the data.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ed5ea-166">有关安装消息队列的信息，请参阅部署文档中的在 <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">服务器上安装操作系统和必备软件（Lync Server 2013</A> ）。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-166">For information about installing Message Queuing, see <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Install operating systems and prerequisite software on servers for Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="ed5ea-167">在 Lync Server 2013 中，高可用性和灾难恢复都有改进：</span><span class="sxs-lookup"><span data-stu-id="ed5ea-167">In Lync Server 2013, there are improvements in both high availability and disaster recovery:</span></span>

  - <span data-ttu-id="ed5ea-168">高可用性改进： SQL Server 镜像用于在数据中心 (的站点内) 中为持久聊天服务器内容数据库和持久聊天合规性数据库提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-168">High availability improvements: SQL Server mirroring is used to provide high availability for the Persistent Chat Server content database and Persistent Chat compliance database within a data center (in-site).</span></span>

  - <span data-ttu-id="ed5ea-169">灾难恢复改进：持久聊天服务器支持扩展池体系结构，使单个持久聊天服务器池能够在两个站点之间扩展 (即拓扑中的单个逻辑池，且池中的服务器物理上位于两个站点) 。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-169">Disaster recovery improvements: Persistent Chat Server supports a stretched pool architecture that enables a single Persistent Chat Server pool to be stretched across two sites (that is, a single logical pool in the topology, with servers in the pool physically located across two sites).</span></span> <span data-ttu-id="ed5ea-170">SQL Server 日志传送用于跨站点灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-170">SQL Server Log Shipping is used for cross-site disaster recovery.</span></span>

<span data-ttu-id="ed5ea-171">有关高可用性和灾难恢复的详细信息，请参阅部署文档中的在 [Lync server 2013 中配置持久聊天服务器以实现高可用性和灾难恢复](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) 。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-171">For more information about high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a><span data-ttu-id="ed5ea-172">持久聊天服务器的关键管理和管理更改</span><span class="sxs-lookup"><span data-stu-id="ed5ea-172">Key Administration and Management Changes for Persistent Chat Server</span></span>

<span data-ttu-id="ed5ea-173">Lync Server 2013 通过提供以下功能使您更易于管理和管理持久聊天服务器：</span><span class="sxs-lookup"><span data-stu-id="ed5ea-173">Lync Server 2013 has made it easier to administer and manage Persistent Chat Server by providing:</span></span>

  - <span data-ttu-id="ed5ea-174">统一的管理和管理。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-174">Unified administration and management.</span></span> <span data-ttu-id="ed5ea-175">通过使用 Lync 管理员熟悉的工具，Lync Server 2013 可以更轻松地管理持久聊天服务器并对其进行管理。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-175">Lync Server 2013 makes it easier to manage and administer Persistent Chat Server by using tools that are already familiar to Lync administrators.</span></span> <span data-ttu-id="ed5ea-176">持久聊天服务器包括与 Lync Server 控制面板集成的管理用户界面体验，可解决早期版本的组聊天服务器用户界面的性能问题。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-176">Persistent Chat Server includes an administrative user interface experience that is integrated with the Lync Server Control Panel, which addresses performance issues with the previous versions of the Group Chat Server user interface.</span></span> <span data-ttu-id="ed5ea-177">此外，持久聊天服务器还包括用于管理和管理持久聊天服务器类别的 Windows PowerShell cmdlet 的集合、持久聊天服务器聊天室 (包括删除聊天室和清除过时内容) 和外接程序。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-177">Also, Persistent Chat Server includes a collection of Windows PowerShell cmdlets to administer and manage Persistent Chat Server categories, Persistent Chat Server rooms (including deleting rooms and purging obsolete content), and add-ins.</span></span>

  - <span data-ttu-id="ed5ea-178">简化了管理模型。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-178">Simplified administration model.</span></span> <span data-ttu-id="ed5ea-179">Lync Server 2013 通过解决以下关键客户要求来更改和简化了持久聊天服务器模型：</span><span class="sxs-lookup"><span data-stu-id="ed5ea-179">Lync Server 2013 has changed and simplified the Persistent Chat Server model by addressing the following key customer requirements:</span></span>
    
      - <span data-ttu-id="ed5ea-180">删除作用域和类别的复杂嵌套层次结构。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-180">Remove the complex nested hierarchies of scopes and categories.</span></span>
    
      - <span data-ttu-id="ed5ea-181">支持定义拒绝列表，以及为正在计划迁移到持久聊天服务器的当前 MindAlign 客户提供的允许的列表 (作用域) 。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-181">Support to define deny lists as well as allowed lists (scopes) for current MindAlign customers who are planning to migrate to Persistent Chat Server.</span></span>

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a><span data-ttu-id="ed5ea-182">来自以前的组聊天服务器版本的用户角色有何不同？</span><span class="sxs-lookup"><span data-stu-id="ed5ea-182">What’s Different about User Roles from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="ed5ea-183">Lync Server 2010，组聊天具有用户管理员角色、聊天室管理员角色和可管理外接程序的 Lync Server 管理员角色。持久聊天服务器只提供与其他基于 Lync Server 角色的访问控制 (RBAC) 角色) 类似的持久聊天管理员角色 (。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-183">Lync Server 2010, Group Chat had a user administrator role, a chat room administrator role and a Lync Server administrator role that could manage add-ins. Persistent Chat Server simply provides a Persistent Chat Administrator role (which is similar to other Lync Server role-based access control (RBAC) roles).</span></span> <span data-ttu-id="ed5ea-184">此 RBAC 角色的成员的任何人都可以管理聊天室、外接程序和类别 (，因此可以获取这些类别的用户访问权限) 以及持久聊天服务器池的配置。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-184">Anyone who is a member of this RBAC role can manage chat rooms, add-ins, and categories (and therefore gain user access for these categories), and configuration of the Persistent Chat Server pool.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a><span data-ttu-id="ed5ea-185">来自以前的组聊天服务器版本的聊天室类别有何不同？</span><span class="sxs-lookup"><span data-stu-id="ed5ea-185">What’s Different about Chat Room Categories from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="ed5ea-186">聊天室类别无法再嵌套，并且无法再修改根类别。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-186">Chat room categories can no longer be nested, and the root category can no longer be modified.</span></span> <span data-ttu-id="ed5ea-187">AllowedMembers/DeniedMembers 包含了在旧版组聊天服务器版本中使用的作用域，不同之处在于它不支持 (指定拒绝列表) 。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-187">AllowedMembers/DeniedMembers comprise what a scope used to be in legacy Group Chat Server versions (except that it didn’t support specifying a Denied list).</span></span> <span data-ttu-id="ed5ea-188">由于没有嵌套的类别，无法再覆盖作用域。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-188">Scopes can no longer be overridden, because there are no nested categories.</span></span> <span data-ttu-id="ed5ea-189">Lync Server 2013 中的持久聊天管理员可以创建和管理聊天室类别。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-189">A Persistent Chat Administrator in Lync Server 2013 can create and manage chat room categories.</span></span> <span data-ttu-id="ed5ea-190">在创建和管理聊天室类别的过程中，持久聊天管理员可以配置 (Active Directory 组/容器/用户) 的主体，这些用户有权访问特定类别的聊天室的成员/创建者。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-190">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="ed5ea-191">持久聊天管理员还可以将 DeniedMembers 添加到类别中，并将其显式排除在允许列表中。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-191">A Persistent Chat Administrator can also add DeniedMembers to a category, and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="ed5ea-192">DeniedMembers 将覆盖 AllowedMembers 中的成员。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-192">DeniedMembers override what’s in AllowedMembers.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a><span data-ttu-id="ed5ea-193">从以前的组聊天服务器版本中聊天室属性的区别是什么？</span><span class="sxs-lookup"><span data-stu-id="ed5ea-193">What’s Different about Chat Room Properties from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="ed5ea-194">Lync Server 2013、持久聊天服务器中存在开放式聊天室的新概念。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-194">A new concept of open chat rooms exists in Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="ed5ea-195">所有允许的成员都可以加入聊天室，而无需独占成员资格。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-195">All allowed members can join the chat room, without exclusive membership.</span></span>

<span data-ttu-id="ed5ea-196">已消除持久聊天服务器的早期版本中所包含的以下聊天室属性：</span><span class="sxs-lookup"><span data-stu-id="ed5ea-196">The following chat room properties that were included in previous versions of Persistent Chat Server have been eliminated:</span></span>

  - <span data-ttu-id="ed5ea-197">主题：聊天室现在仅有说明。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-197">Topic: A Room now only has a Description.</span></span>

  - <span data-ttu-id="ed5ea-198">创建新成员列表：在持久聊天服务器中，所有聊天室都将从空的成员资格开始 (，并且可以最大限度地 equaling 允许的成员) 的成员身份。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-198">Create New Member list: In Persistent Chat Server, all chat rooms start with empty membership (and can maximize to a membership equaling the Allowed Members).</span></span>

  - <span data-ttu-id="ed5ea-199">文件上传：用于控制是否允许文件上载/下载的每个聊天室的设置。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-199">File Upload: Used to be a setting per chat room to control whether file upload/downloads were allowed.</span></span> <span data-ttu-id="ed5ea-200">现在，这仅设置了类别级别，并适用于该类别中的所有聊天室。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-200">This is now set only the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="ed5ea-201">聊天历史记录：用于在聊天室中控制是否启用聊天历史记录，但现在仅在类别级别设置，并适用于该类别中的所有聊天室的设置。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-201">Chat History: Used to be a setting per chat room to control if Chat History was enabled, but is now set only at the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="ed5ea-202">邀请：会议室始终继承类别的 "邀请" 设置;也可以在聊天室上关闭它。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-202">Invites: A room always inherits the Invites setting for the category; or it can be turned off on the room.</span></span> <span data-ttu-id="ed5ea-203">如果以前将类别设置为 "邀请关闭"，会议室将无法启用邀请。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-203">A room cannot turn on Invites if the category was previously set to Invites off.</span></span>

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a><span data-ttu-id="ed5ea-204">来自以前的组聊天服务器版本的策略有何不同？</span><span class="sxs-lookup"><span data-stu-id="ed5ea-204">What’s Different about Policies from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="ed5ea-205">持久聊天服务器启用了一个新的 Lync 策略，其中包含持续聊天、每用户/池/站点/全局设置。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-205">Persistent Chat Server has a new Lync policy enabled with Persistent Chat, per user/pool/site/global settings.</span></span> <span data-ttu-id="ed5ea-206">在 Lync 2013 客户端中，持久聊天环境仅适用于通过直接或通过 "池/站点/全局设置") 启用的持久聊天 (的用户。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-206">In the Lync 2013 client, the Persistent Chat environment is available only for users who are enabled by policy for Persistent Chat (either directly or through the pool/site/global setting).</span></span>

<span data-ttu-id="ed5ea-207">早期版本的组聊天服务器没有集成到 Lync Server 策略中的任何策略。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-207">Previous versions of Group Chat Server did not have any policies integrated into the Lync Server policies.</span></span> <span data-ttu-id="ed5ea-208">在每用户和每个类别/房间的基础上，通过使用 "可按用户 **上传文件** " 功能，可以让用户成为用户管理员、聊天室管理员或配置用户上传文件的能力。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-208">On a per user and per category/room basis, by using the **Can Upload Files** per user feature, you could make the user a User administrator, a chat room administrator, or configure the user’s ability to upload files.</span></span> <span data-ttu-id="ed5ea-209">持久聊天服务器 **文件上载** 功能仅在每个类别中。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-209">The Persistent Chat Server **File Upload** feature is just per category.</span></span>

</div>

<div>

## <a name="logging"></a><span data-ttu-id="ed5ea-210">日志记录</span><span class="sxs-lookup"><span data-stu-id="ed5ea-210">Logging</span></span>

<span data-ttu-id="ed5ea-211">持久聊天服务器和 System Center Operations Manager 的日志记录集成到 Lync Server 2013 跟踪日志记录中。</span><span class="sxs-lookup"><span data-stu-id="ed5ea-211">Logging for Persistent Chat Server and System Center Operations Manager is integrated into the Lync Server 2013 trace logging.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ed5ea-212">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed5ea-212">See Also</span></span>


[<span data-ttu-id="ed5ea-213">在 Lync Server 2013 中规划持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="ed5ea-213">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
