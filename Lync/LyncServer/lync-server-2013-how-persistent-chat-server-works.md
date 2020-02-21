---
title: Lync Server 2013：持久聊天服务器的工作方式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a88bdad2a73022468297d73dd10bff0d26a3fee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a><span data-ttu-id="8b5df-102">Lync Server 2013 中持久聊天服务器的工作原理</span><span class="sxs-lookup"><span data-stu-id="8b5df-102">How Persistent Chat Server works in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b5df-103">_**上次修改的主题：** 2012-11-21_</span><span class="sxs-lookup"><span data-stu-id="8b5df-103">_**Topic Last Modified:** 2012-11-21_</span></span>

<span data-ttu-id="8b5df-104">Lync Server 2013、持久聊天服务器使您能够参与在一段时间内保持的基于主题的多个会话。</span><span class="sxs-lookup"><span data-stu-id="8b5df-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="8b5df-105">持久聊天服务器可帮助您的组织执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8b5df-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="8b5df-106">改善分散在不同地理位置的跨部门团队间的通信</span><span class="sxs-lookup"><span data-stu-id="8b5df-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="8b5df-107">扩大信息的知晓和参与范围</span><span class="sxs-lookup"><span data-stu-id="8b5df-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="8b5df-108">改善组织扩大后的通信</span><span class="sxs-lookup"><span data-stu-id="8b5df-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="8b5df-109">减少信息过载</span><span class="sxs-lookup"><span data-stu-id="8b5df-109">Reduce information overload</span></span>

  - <span data-ttu-id="8b5df-110">提高信息感知能力</span><span class="sxs-lookup"><span data-stu-id="8b5df-110">Improve information awareness</span></span>

  - <span data-ttu-id="8b5df-111">扩大重要知识和信息的传播范围</span><span class="sxs-lookup"><span data-stu-id="8b5df-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="8b5df-112">您可以将持久聊天服务器部署为 Lync Server 2013 的可选角色。</span><span class="sxs-lookup"><span data-stu-id="8b5df-112">You can deploy Persistent Chat Server as an optional role with Lync Server 2013.</span></span> <span data-ttu-id="8b5df-113">持久聊天服务在专用池上运行，持久聊天服务器池依赖于 Lync Server 池来将邮件路由到它。</span><span class="sxs-lookup"><span data-stu-id="8b5df-113">Persistent Chat services run on a dedicated pool, and a Persistent Chat Server pool depends on a Lync Server pool to route messages to it.</span></span> <span data-ttu-id="8b5df-114">客户端使用 eXtensible Chat Communication Over SIP (XCCOS)。</span><span class="sxs-lookup"><span data-stu-id="8b5df-114">Clients use eXtensible Chat Communication Over SIP (XCCOS).</span></span> <span data-ttu-id="8b5df-115">将 Lync Server 前端服务器配置为将流量路由到持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="8b5df-115">The Lync Server Front End Servers are configured to route the traffic to a Persistent Chat Server pool.</span></span>

<div>

## <a name="high-level-architecture"></a><span data-ttu-id="8b5df-116">高级体系结构</span><span class="sxs-lookup"><span data-stu-id="8b5df-116">High-Level Architecture</span></span>

<span data-ttu-id="8b5df-117">下面的关系图提供持久聊天服务器体系结构和服务的高级别角度。</span><span class="sxs-lookup"><span data-stu-id="8b5df-117">The following diagrams provide high-level perspectives of the Persistent Chat Server architecture and services.</span></span>

<span data-ttu-id="8b5df-118">**持久聊天服务器高级体系结构**</span><span class="sxs-lookup"><span data-stu-id="8b5df-118">**Persistent Chat Server High-Level Architecture**</span></span>

<span data-ttu-id="8b5df-119">![持久聊天服务器体系结构。](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "持久聊天服务器体系结构。")</span><span class="sxs-lookup"><span data-stu-id="8b5df-119">![Persistent Chat Server architecture.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Persistent Chat Server architecture.")</span></span>

<span data-ttu-id="8b5df-120">**持久聊天服务器高级服务**</span><span class="sxs-lookup"><span data-stu-id="8b5df-120">**Persistent Chat Server High-Level Services**</span></span>

<span data-ttu-id="8b5df-121">![持久聊天服务器组件。](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "持久聊天服务器组件。")</span><span class="sxs-lookup"><span data-stu-id="8b5df-121">![Persistent Chat Server components.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Persistent Chat Server components.")</span></span>

<span data-ttu-id="8b5df-122">在持久聊天服务器前端服务器上运行两个服务：</span><span class="sxs-lookup"><span data-stu-id="8b5df-122">Two services run on the Persistent Chat Server Front End Servers:</span></span>

  - <span data-ttu-id="8b5df-123">持久聊天（通道）</span><span class="sxs-lookup"><span data-stu-id="8b5df-123">Persistent Chat (Channel)</span></span>

  - <span data-ttu-id="8b5df-124">合规性</span><span class="sxs-lookup"><span data-stu-id="8b5df-124">Compliance</span></span>

<div>

## <a name="persistent-chat-channel-service"></a><span data-ttu-id="8b5df-125">持久聊天（通道）服务</span><span class="sxs-lookup"><span data-stu-id="8b5df-125">Persistent Chat (Channel) Service</span></span>

<span data-ttu-id="8b5df-126">持久聊天（频道）服务是负责持久聊天服务器的核心服务。</span><span class="sxs-lookup"><span data-stu-id="8b5df-126">The Persistent Chat (Channel) service is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="8b5df-127">此服务提供了以下功能：</span><span class="sxs-lookup"><span data-stu-id="8b5df-127">This service provides the following functions:</span></span>

  - <span data-ttu-id="8b5df-128">接受传入消息</span><span class="sxs-lookup"><span data-stu-id="8b5df-128">Accepts incoming messages</span></span>

  - <span data-ttu-id="8b5df-129">在持久聊天室中注册和列出在线参与者</span><span class="sxs-lookup"><span data-stu-id="8b5df-129">Registers and lists online participants within a Persistent Chat room</span></span>

  - <span data-ttu-id="8b5df-130">向其他通道订阅者重新传输消息</span><span class="sxs-lookup"><span data-stu-id="8b5df-130">Retransmits messages to other channel subscribers</span></span>

  - <span data-ttu-id="8b5df-131">实现通道管理、聊天室邀请、搜索和新内容通知的逻辑</span><span class="sxs-lookup"><span data-stu-id="8b5df-131">Implements logic for channel management, chat room invitation, search, and new content notifications</span></span>

<span data-ttu-id="8b5df-132">持久聊天（通道）服务使用持久聊天存储来存储和访问聊天室内容以及其他系统元数据（授权规则等）。</span><span class="sxs-lookup"><span data-stu-id="8b5df-132">The Persistent Chat (Channel) service stores and accesses chat room content and other system metadata (authorization rules, and so on) by using the Persistent Chat Store.</span></span> <span data-ttu-id="8b5df-133">此服务将上传到聊天室中的文件存储在持久聊天文件存储区中。</span><span class="sxs-lookup"><span data-stu-id="8b5df-133">This service stores files that are uploaded into chat rooms in the Persistent Chat File Store.</span></span>

</div>

<div>

## <a name="compliance-service"></a><span data-ttu-id="8b5df-134">合规性服务</span><span class="sxs-lookup"><span data-stu-id="8b5df-134">Compliance Service</span></span>

<span data-ttu-id="8b5df-135">合规性服务是持久聊天服务器的可选组件，负责将聊天内容和事件存档到持久聊天合规性存储。</span><span class="sxs-lookup"><span data-stu-id="8b5df-135">The Compliance service is an optional component of Persistent Chat Server and is responsible for archiving chat content and events to the Persistent Chat Compliance Store.</span></span> <span data-ttu-id="8b5df-136">如果您的组织具有要求存档持久聊天活动的法规，则可以部署可选的持久聊天合规性服务。</span><span class="sxs-lookup"><span data-stu-id="8b5df-136">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="8b5df-137">合规性服务安装在持久聊天池中的每台持久聊天服务器上。</span><span class="sxs-lookup"><span data-stu-id="8b5df-137">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> <span data-ttu-id="8b5df-138">配置后，持久聊天服务器合规性记录用户活动，如加入和离开聊天室，以及投递和阅读邮件。</span><span class="sxs-lookup"><span data-stu-id="8b5df-138">When configured, Persistent Chat Server compliance records user activity such as joining and leaving rooms, and posting and reading of messages.</span></span> <span data-ttu-id="8b5df-139">合规性服务存储需要存档在持久聊天合规性文件存储中的文件。</span><span class="sxs-lookup"><span data-stu-id="8b5df-139">The Compliance service stores files that need to be archived in the Persistent Chat Compliance File Store.</span></span>

</div>

<div>

## <a name="persistent-chat-web-services"></a><span data-ttu-id="8b5df-140">持久聊天 Web 服务</span><span class="sxs-lookup"><span data-stu-id="8b5df-140">Persistent Chat Web Services</span></span>

<span data-ttu-id="8b5df-141">在 Lync Server 前端服务器上，运行的两个服务依赖于 Internet 信息服务（IIS），并作为 web 组件实现：</span><span class="sxs-lookup"><span data-stu-id="8b5df-141">On the Lync Server Front End Servers, two services run that depend on Internet Information Services (IIS), and are implemented as web components:</span></span>

  - <span data-ttu-id="8b5df-142">**用于文件上载/下载的持久聊天 Web 服务**负责在聊天室中发布和检索文件。</span><span class="sxs-lookup"><span data-stu-id="8b5df-142">**Persistent Chat Web Services for File Upload/Download** Responsible for posting and retrieving files from chat rooms.</span></span>

  - <span data-ttu-id="8b5df-143">**聊天室管理的持久聊天 Web 服务**负责为用户提供管理其聊天室和创建新聊天室的功能。</span><span class="sxs-lookup"><span data-stu-id="8b5df-143">**Persistent Chat Web Services for Chat Room Management** Responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a><span data-ttu-id="8b5df-144">如何开始使用持久聊天服务器？</span><span class="sxs-lookup"><span data-stu-id="8b5df-144">How Do I Start Using Persistent Chat Server?</span></span>

<span data-ttu-id="8b5df-145">持久聊天服务器是 Lync Server 2013 基础结构中的可选服务器角色。</span><span class="sxs-lookup"><span data-stu-id="8b5df-145">Persistent Chat Server is an optional server role within the Lync Server 2013 infrastructure.</span></span> <span data-ttu-id="8b5df-146">如果安装持久聊天服务器角色，则由管理员通过策略启用的任何用户都可以与 Lync 2013 客户端一起使用持久聊天。</span><span class="sxs-lookup"><span data-stu-id="8b5df-146">If you install the Persistent Chat Server role, any users who have been enabled through policy by an administrator can use Persistent Chat with the Lync 2013 client.</span></span>

<span data-ttu-id="8b5df-147">有关如何部署持久聊天服务器并使用户能够利用策略功能的详细信息，请参阅[在 Lync server 2013 中部署持久聊天服务器](lync-server-2013-deploying-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="8b5df-147">For details about how to deploy Persistent Chat Server and enable users to leverage the capabilities by policy, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>

<span data-ttu-id="8b5df-148">有关如何在持久聊天服务器部署上配置设置的详细信息，请参阅[在 Lync server 2013 中部署持久聊天服务器](lync-server-2013-deploying-persistent-chat-server.md)和[管理 Lync Server 2013 的持久聊天服务器](managing-lync-server-2013-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="8b5df-148">For details about how to configure settings on your Persistent Chat Server deployment, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="8b5df-149">有关如何根据策略启用用户以在 Lync 2013 客户端中利用持久聊天功能的详细信息，请参阅[在 Lync server 2013 中部署持久聊天服务器](lync-server-2013-deploying-persistent-chat-server.md)和[管理 Lync Server 2013、持久聊天服务器](managing-lync-server-2013-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="8b5df-149">For details about how to enable users by policy such that they can leverage Persistent Chat functionality in Lync 2013 client, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="8b5df-150">如果已部署持久聊天合规性，请参阅[管理 Lync server 2013 和持久聊天服务器](managing-lync-server-2013-persistent-chat-server.md)，了解有关如何配置合规性设置的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8b5df-150">If you deployed Persistent Chat compliance, see [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) for details about how to configure settings for compliance.</span></span>

</div>

<div>

## <a name="persistent-chat-call-flows"></a><span data-ttu-id="8b5df-151">持久聊天呼叫流</span><span class="sxs-lookup"><span data-stu-id="8b5df-151">Persistent Chat Call Flows</span></span>

<span data-ttu-id="8b5df-152">持久聊天客户端通过使用 XCCOS 与持久聊天服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="8b5df-152">The Persistent Chat client communicates with the Persistent Chat service by using XCCOS.</span></span> <span data-ttu-id="8b5df-153">以下顺序说明了登录过程以及典型的聊天室订阅和消息发布方案。</span><span class="sxs-lookup"><span data-stu-id="8b5df-153">The following sequences describe the sign-in process and a typical room subscription and message post scenario.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="8b5df-154">登录</span><span class="sxs-lookup"><span data-stu-id="8b5df-154">Sign-in</span></span>

<span data-ttu-id="8b5df-155">下面的调用流程图和步骤介绍了登录过程。</span><span class="sxs-lookup"><span data-stu-id="8b5df-155">The following call flow diagram and steps describe the sign-in process.</span></span>

<span data-ttu-id="8b5df-156">**持久聊天客户端登录呼叫流**</span><span class="sxs-lookup"><span data-stu-id="8b5df-156">**Persistent Chat Client Sign-in Call Flow**</span></span>

<span data-ttu-id="8b5df-157">![持久聊天服务器呼叫流图表。](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "持久聊天服务器呼叫流图表。")</span><span class="sxs-lookup"><span data-stu-id="8b5df-157">![Persistent Chat Server call flow diagram.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Persistent Chat Server call flow diagram.")</span></span>

1.  <span data-ttu-id="8b5df-158">持久聊天客户端先发送 SIP 订阅，以从服务器检索带内设置文档。</span><span class="sxs-lookup"><span data-stu-id="8b5df-158">The Persistent Chat client first sends a SIP SUBSCRIBE to retrieve the in-band provisioning document from the server.</span></span> <span data-ttu-id="8b5df-159">本文档指明是否为用户启用或禁用持久聊天以及持久聊天服务器池的 SIP Uri 列表。</span><span class="sxs-lookup"><span data-stu-id="8b5df-159">This document indicates if Persistent Chat is enabled or disabled for the user and the list of SIP URIs for the Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="8b5df-160">持久聊天客户端将 SIP 邀请邮件发送到在上一步中获取的持久聊天服务器的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="8b5df-160">The Persistent Chat client sends a SIP INVITE message to the SIP URI of the Persistent Chat Server that it obtained in the previous step.</span></span> <span data-ttu-id="8b5df-161">邀请序列后跟 200 OK 和 ACK，持久聊天客户端现在已使用持久聊天服务器终结点打开了 SIP 会话。</span><span class="sxs-lookup"><span data-stu-id="8b5df-161">The INVITE sequence is followed by 200 OK and ACK, and the Persistent Chat client has now opened a SIP session with a Persistent Chat Server endpoint.</span></span> <span data-ttu-id="8b5df-162">因此，持久聊天客户端通过发送 SIP 信息消息（其中包含聊天消息或命令请求服务器执行操作）与持久聊天服务器进行通信。</span><span class="sxs-lookup"><span data-stu-id="8b5df-162">Consequently, the Persistent Chat client communicates with Persistent Chat Server by sending SIP INFO messages that contain either chat messages or commands requesting the server to take an action.</span></span> <span data-ttu-id="8b5df-163">所有这些消息都使用“200 - 确定”或“503 - 服务不可用”（即，在服务器负载过重的情况下）确认。</span><span class="sxs-lookup"><span data-stu-id="8b5df-163">All of these messages are acknowledged with either 200 OK or 503 Service Unavailable (that is, in the event of heavy server load).</span></span> <span data-ttu-id="8b5df-164">如果客户端收到 503 响应，则会重试消息。</span><span class="sxs-lookup"><span data-stu-id="8b5df-164">If the client receives a 503 response, it will retry the message.</span></span> <span data-ttu-id="8b5df-165">（此示例不包含503响应。）如果服务器接受消息或命令并发送 200 "确定"，则它会以单独的 SIP 信息消息的形式向客户端提供响应。</span><span class="sxs-lookup"><span data-stu-id="8b5df-165">(This example does not include a 503 response.) If the server accepts the message or command and sends 200 OK, it provides a response to the client in the form of a separate SIP INFO message.</span></span> <span data-ttu-id="8b5df-166">此响应包括对发出的命令的引用。</span><span class="sxs-lookup"><span data-stu-id="8b5df-166">This response includes a reference to the originating command.</span></span>

3.  <span data-ttu-id="8b5df-167">持久聊天客户端发送包含 XCCOS **getserverinfo**命令的 SIP 信息消息。</span><span class="sxs-lookup"><span data-stu-id="8b5df-167">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getserverinfo** command.</span></span> <span data-ttu-id="8b5df-168">持久聊天服务器使用新的 SIP 信息消息进行答复，其中包含有关持久聊天服务配置的信息。</span><span class="sxs-lookup"><span data-stu-id="8b5df-168">Persistent Chat Server replies with a new SIP INFO message that contains information about the Persistent Chat service configuration.</span></span>

4.  <span data-ttu-id="8b5df-169">持久聊天客户端发送包含 XCCOS **getassociations**命令的 SIP 信息消息。</span><span class="sxs-lookup"><span data-stu-id="8b5df-169">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getassociations** command.</span></span> <span data-ttu-id="8b5df-170">持久聊天服务器使用新的 SIP 信息消息进行答复，其中包含用户所属的聊天室的列表。</span><span class="sxs-lookup"><span data-stu-id="8b5df-170">Persistent Chat Server replies with a new SIP INFO message that contains the list of rooms of which the user is a member.</span></span> <span data-ttu-id="8b5df-171">持久聊天客户端将重复命令，以检索用户是其管理员的聊天室的列表。</span><span class="sxs-lookup"><span data-stu-id="8b5df-171">The Persistent Chat client repeats the command to retrieve the list of rooms of which the user is a manager.</span></span>

5.  <span data-ttu-id="8b5df-172">持久聊天客户端从 "状态" 文档中获取关注的聊天室列表，其中每个聊天室都由一个 "roomSetting" 类别表示。</span><span class="sxs-lookup"><span data-stu-id="8b5df-172">The Persistent Chat client gets the list of followed rooms from the "presence" document, where each followed room is represented by a "roomSetting" category.</span></span> <span data-ttu-id="8b5df-173">所有已关注的聊天室都通过一个包含 XCCOS **bjoin** 命令（包含聊天室 URI 列表）的 SIP INFO 消息联接。</span><span class="sxs-lookup"><span data-stu-id="8b5df-173">All followed rooms are joined by a single SIP INFO message that contains the XCCOS **bjoin** command that contains the list of room URIs.</span></span> <span data-ttu-id="8b5df-174">由于已关注的聊天室的列表保存在服务器上，因此任何计算机上的任何客户端都具有相同的指定用户 URI 的已关注聊天室列表。</span><span class="sxs-lookup"><span data-stu-id="8b5df-174">Because the list of followed rooms is kept on the server, any client on any computer has the same list of followed rooms for the specified user URI.</span></span> <span data-ttu-id="8b5df-175">持久聊天客户端还会在本地计算机注册表中保留打开的会议室（如果用户已启用此选项）的列表，并通过发送包含每个打开的聊天室的 XCCOS **join**命令的 SIP 信息消息，在登录时加入这些会议室。</span><span class="sxs-lookup"><span data-stu-id="8b5df-175">The Persistent Chat client also keeps the list of opened rooms (if this option is enabled by the user) in the local computer registry, and joins each of these rooms at sign-in by sending a SIP INFO message that contains the XCCOS **join** command for each opened room.</span></span> <span data-ttu-id="8b5df-176">由于此列表保留在注册表中，因此在不同计算机上运行的两台持久聊天客户端上可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="8b5df-176">Because this list is kept in the registry, it can be different on two Persistent Chat clients running on different computers.</span></span>

6.  <span data-ttu-id="8b5df-177">对于每个加入的会议室，持久聊天客户端发送包含 XCCOS **bccontext**命令的 SIP 信息消息。</span><span class="sxs-lookup"><span data-stu-id="8b5df-177">For each room joined, the Persistent Chat client sends a SIP INFO message that contains the XCCOS **bccontext** command.</span></span> <span data-ttu-id="8b5df-178">持久聊天服务器使用新的 SIP 信息消息进行答复，其中包含聊天室中最新的聊天消息。</span><span class="sxs-lookup"><span data-stu-id="8b5df-178">Persistent Chat Server replies with a new SIP INFO message that contains the most recent chat message in the room.</span></span>

7.  <span data-ttu-id="8b5df-179">持久聊天客户端发送包含 XCCOS **getinv** （即获取邀请）命令的 SIP 信息消息，以请求客户端尚未看到的任何新的聊天室邀请。</span><span class="sxs-lookup"><span data-stu-id="8b5df-179">The Persistent Chat client sends a SIP INFO message that contains a XCCOS **getinv** (that is, get invitation) command to request any new room invitations that the client has not yet seen.</span></span> <span data-ttu-id="8b5df-180">在单独的 SIP 信息消息中，持久聊天服务器返回这些聊天室的列表。</span><span class="sxs-lookup"><span data-stu-id="8b5df-180">In a separate SIP INFO message, Persistent Chat Server returns a list of those rooms.</span></span>

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a><span data-ttu-id="8b5df-181">订阅聊天室和发布消息</span><span class="sxs-lookup"><span data-stu-id="8b5df-181">Subscribe to a Room and Post a Message</span></span>

<span data-ttu-id="8b5df-182">下面的调用流程图和步骤介绍了典型的会议室订阅和邮件发布方案。</span><span class="sxs-lookup"><span data-stu-id="8b5df-182">The following call flow diagram and steps describe a typical room subscription and message post scenario.</span></span>

<span data-ttu-id="8b5df-183">**持久聊天客户端会议室订阅和邮件发布呼叫流**</span><span class="sxs-lookup"><span data-stu-id="8b5df-183">**Persistent Chat Client Room Subscription and Message Posting Call Flow**</span></span>

<span data-ttu-id="8b5df-184">![会议室订阅和邮件发布方案。](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "会议室订阅和邮件发布方案。")</span><span class="sxs-lookup"><span data-stu-id="8b5df-184">![Room subscription and message post scenario.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Room subscription and message post scenario.")</span></span>

1.  <span data-ttu-id="8b5df-185">在持久聊天客户端中，User1 单击 "**加入聊天室**"，单击 "**搜索**"，然后输入一些搜索条件。</span><span class="sxs-lookup"><span data-stu-id="8b5df-185">From the Persistent Chat client, User1 clicks **Join a Chat Room**, clicks **Search**, and then enters some search criteria.</span></span> <span data-ttu-id="8b5df-186">持久聊天客户端发送包含 XCCOS **chansrch** （聊天室搜索）命令的 SIP 信息消息以及搜索条件。</span><span class="sxs-lookup"><span data-stu-id="8b5df-186">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **chansrch** (room search) command, along with the search criteria.</span></span> <span data-ttu-id="8b5df-187">持久聊天服务器查询后端数据库，并在新的 SIP 信息消息中进行答复，其中包含满足搜索条件的可用聊天室的列表。</span><span class="sxs-lookup"><span data-stu-id="8b5df-187">Persistent Chat Server queries the back-end database and replies in a new SIP INFO message that contains a list of available rooms that meet the search criteria.</span></span>

2.  <span data-ttu-id="8b5df-188">User1 选择他/她要加入的聊天室，然后单击“关注此聊天室”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b5df-188">User1 selects the chat room that he or she wants to join, and then clicks **Follow this room**.</span></span> <span data-ttu-id="8b5df-189">持久聊天客户端向持久聊天服务器发送包含 XCCOS **join**命令的 SIP 信息消息和用户选择的聊天室的聊天室 ID。</span><span class="sxs-lookup"><span data-stu-id="8b5df-189">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **join** command and the room ID of the chat room that the user selected.</span></span> <span data-ttu-id="8b5df-190">持久聊天服务器使用包含预配数据的 SIP 信息消息进行答复。</span><span class="sxs-lookup"><span data-stu-id="8b5df-190">Persistent Chat Server replies with a SIP INFO message that contains the provisioning data.</span></span>

3.  <span data-ttu-id="8b5df-191">持久聊天客户端向持久聊天服务器发送包含 XCCOS **bccontext** （backchat 上下文）命令的 SIP 信息消息。</span><span class="sxs-lookup"><span data-stu-id="8b5df-191">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **bccontext** (backchat context) command.</span></span> <span data-ttu-id="8b5df-192">持久聊天服务器检索聊天历史记录，并在单独的 SIP 信息消息中将其返回到持久聊天客户端。</span><span class="sxs-lookup"><span data-stu-id="8b5df-192">Persistent Chat Server retrieves the chat history, and returns it to the Persistent Chat client in a separate SIP INFO message.</span></span> <span data-ttu-id="8b5df-193">此时，用户进入聊天室并准备好参与。</span><span class="sxs-lookup"><span data-stu-id="8b5df-193">At this point, the user enters the chat room and is ready to participate.</span></span>

4.  <span data-ttu-id="8b5df-194">User1 输入新消息，然后单击“发送”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b5df-194">User1 enters a new message, and then clicks **Send**.</span></span> <span data-ttu-id="8b5df-195">持久聊天客户端将邮件发送到 SIP INFO XCCOS **grpchat**命令中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="8b5df-195">The Persistent Chat client posts the message to the chat room in a SIP INFO XCCOS **grpchat** command.</span></span> <span data-ttu-id="8b5df-196">持久聊天服务器将此新邮件的副本存储在持久聊天后端数据库中。</span><span class="sxs-lookup"><span data-stu-id="8b5df-196">Persistent Chat Server stores a copy of this new message in the Persistent Chat back-end database.</span></span>

5.  <span data-ttu-id="8b5df-197">持久聊天服务器将 SIP 信息 XCCOS **grpchat**邮件的单独副本发送给使用商，他们已经进入聊天室。</span><span class="sxs-lookup"><span data-stu-id="8b5df-197">Persistent Chat Server sends a separate copy of the SIP INFO XCCOS **grpchat** message to User2, who has already entered the chat room.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a><span data-ttu-id="8b5df-198">持久聊天合规性呼叫流</span><span class="sxs-lookup"><span data-stu-id="8b5df-198">Persistent Chat Compliance Call Flows</span></span>

<span data-ttu-id="8b5df-199">持久聊天服务器使用消息队列（也称为 MSMQ）和其他合规性数据库（mgccomp）来处理合规性数据。</span><span class="sxs-lookup"><span data-stu-id="8b5df-199">Persistent Chat Server uses Message Queuing (also known as MSMQ) and an additional compliance database (mgccomp) to process compliance data.</span></span> <span data-ttu-id="8b5df-200">作为合规性事件处理方式的示例，以下事件顺序说明了如何处理消息发布事件。</span><span class="sxs-lookup"><span data-stu-id="8b5df-200">As an example of how compliance events are processed, the following sequence of events describes how a message post event is processed.</span></span>

1.  <span data-ttu-id="8b5df-201">用户向聊天室发布消息。</span><span class="sxs-lookup"><span data-stu-id="8b5df-201">A user posts a message to a room.</span></span>

2.  <span data-ttu-id="8b5df-202">持久聊天服务器将与事件相关的信息放在专用 "消息队列" 队列中。</span><span class="sxs-lookup"><span data-stu-id="8b5df-202">Persistent Chat Server places information pertaining to the event in a private Message Queuing queue.</span></span>

3.  <span data-ttu-id="8b5df-203">持久聊天合规性服务器从队列中读取此事件，并将其放入 mgccomp 数据库以供以后处理。</span><span class="sxs-lookup"><span data-stu-id="8b5df-203">Persistent Chat Compliance server reads this event from the queue, and places it into the mgccomp database for processing later.</span></span>

4.  <span data-ttu-id="8b5df-204">持久聊天合规性服务器会定期处理数据库中的一组事件，并将其发送到持久聊天合规性适配器以进行处理。</span><span class="sxs-lookup"><span data-stu-id="8b5df-204">Periodically, the Persistent Chat Compliance server processes a set of events in the database, and sends them to the Persistent Chat Compliance adapter for processing.</span></span>

5.  <span data-ttu-id="8b5df-205">如果适配器成功处理数据，则持久聊天合规性服务器将从 mgccomp 数据库中删除事件。</span><span class="sxs-lookup"><span data-stu-id="8b5df-205">If the adapter successfully processes the data, Persistent Chat Compliance server deletes the events from the mgccomp database.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

