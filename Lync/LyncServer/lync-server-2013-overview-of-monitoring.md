---
title: Lync Server 2013：监视概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27826948f9206c6053b166d901145ed6785a0189
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a><span data-ttu-id="89e54-102">Lync Server 2013 中的监视概述</span><span class="sxs-lookup"><span data-stu-id="89e54-102">Overview of monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89e54-103">_**主题上次修改时间：** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="89e54-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="89e54-104">在 Microsoft Lync Server 2013 中，"监视" 用于收集有关用户所涉及的通信会话的使用信息和体验质量（QoE）数据。</span><span class="sxs-lookup"><span data-stu-id="89e54-104">In Microsoft Lync Server 2013, monitoring is used to collect usage information and Quality of Experience (QoE) data about the communication sessions that your users are involved in.</span></span> <span data-ttu-id="89e54-105">会话是涵盖用户与的连接的常规术语：</span><span class="sxs-lookup"><span data-stu-id="89e54-105">A session is a generic term that covers a user’s connection to a:</span></span>

  - <span data-ttu-id="89e54-106">会议</span><span class="sxs-lookup"><span data-stu-id="89e54-106">Conference</span></span>

  - <span data-ttu-id="89e54-107">会议模态（如音频/视频或应用程序共享）</span><span class="sxs-lookup"><span data-stu-id="89e54-107">Conferencing modality (such as Audio/Video or Application Sharing)</span></span>

  - <span data-ttu-id="89e54-108">通过点对点对话（如即时消息或音频呼叫）的其他用户</span><span class="sxs-lookup"><span data-stu-id="89e54-108">Another user via a peer-to-peer conversation such as instant messaging or an audio call</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="89e54-109">Lync Server 2013 跟踪有关每个会话的信息：谁称为谁;会话中使用了哪些终结点;该会话持续多长时间;会话的感知质量是多少;依此类推。</span><span class="sxs-lookup"><span data-stu-id="89e54-109">Lync Server 2013 keeps track of information about each session: who called who; which endpoints were used in the session; how long did the session last; what was the perceived quality of the session; and so on.</span></span> <span data-ttu-id="89e54-110">但是，Lync 服务器不会记录和存储实际呼叫本身。</span><span class="sxs-lookup"><span data-stu-id="89e54-110">However, Lync Server does not record and store the actual call itself.</span></span> <span data-ttu-id="89e54-111">同时还包括即时消息会话：尽管 Lync 服务器记录有关即时消息会话的信息，但它不保留会话期间发送的每条即时消息的记录。</span><span class="sxs-lookup"><span data-stu-id="89e54-111">That includes instant messaging sessions as well: although Lync Server records information about instant messaging sessions, it does not maintain a record of each instant message that was sent during the session.</span></span>



</div>

<span data-ttu-id="89e54-112">Lync Server 收集的通话详细信息可用于任何数量的用途，包括：</span><span class="sxs-lookup"><span data-stu-id="89e54-112">The call detail information collected by Lync Server can be employed for any number of uses, including:</span></span>

  - <span data-ttu-id="89e54-113">**投资回报率（ROI）**。</span><span class="sxs-lookup"><span data-stu-id="89e54-113">**Return on Investment (ROI)**.</span></span> <span data-ttu-id="89e54-114">管理员可以将监视服务器收集的使用数据与为以前的电话系统收集的类似数据进行比较，以便显示成本节约并帮助论证 Lync 服务器的部署。</span><span class="sxs-lookup"><span data-stu-id="89e54-114">Administrators can compare the usage data collected by Monitoring Server to similar data collected for their previous telephony system in order to show cost savings and help justify the deployment of Lync Server.</span></span>

  - <span data-ttu-id="89e54-115">**设备库存管理**。</span><span class="sxs-lookup"><span data-stu-id="89e54-115">**Device Inventory Management**.</span></span> <span data-ttu-id="89e54-116">资产管理信息可帮助管理员识别仍在使用的旧设备，这些设备需要被替换，并确定不会经常使用的昂贵设备。</span><span class="sxs-lookup"><span data-stu-id="89e54-116">Asset management information helps administrators identify old devices still in use that need to be replaced, as well as identify expensive devices that do not appear to be getting used at all.</span></span>

  - <span data-ttu-id="89e54-117">技术支持。</span><span class="sxs-lookup"><span data-stu-id="89e54-117">Help Desk.</span></span> <span data-ttu-id="89e54-118">疑难解答数据使支持工程师能够确定用户调用失败的原因，以及执行此操作，而无需收集服务器或客户端日志。</span><span class="sxs-lookup"><span data-stu-id="89e54-118">Troubleshooting data enables support engineers to determine why a user’s call failed, and to do so without having to collect server or client side logs.</span></span> <span data-ttu-id="89e54-119">对 Microsoft Lync 2013 和 Lync Server 2013 没有深入技术知识的支持人员可以随时访问和理解此信息。</span><span class="sxs-lookup"><span data-stu-id="89e54-119">This information can be readily accessed and understood by support personnel who do not have a deep technical knowledge of Microsoft Lync 2013 and Lync Server 2013.</span></span>

  - <span data-ttu-id="89e54-p106">**系统故障排除**。使管理员能够检测可能阻止最终用户执行基本任务（如加入会议、建立呼叫或发送即时消息）的重大问题。</span><span class="sxs-lookup"><span data-stu-id="89e54-p106">**System Troubleshooting**. Enables administrators to detect major issues that might prevent end users from performing basic tasks like joining a conference, establishing a call, or sending an instant message.</span></span>

<span data-ttu-id="89e54-122">除了这种基本的呼叫信息外，监视服务器还提供允许 SIP 终结点（如 Lync 2013）提供服务器无权访问的故障排除信息的机制：</span><span class="sxs-lookup"><span data-stu-id="89e54-122">In addition to this basic call information, the Monitoring Server also provides a mechanism that allows SIP endpoints (such as Lync 2013) to provide troubleshooting information that the server would not otherwise have access to:</span></span>

  - <span data-ttu-id="89e54-123">**影响质量的媒体指标**。</span><span class="sxs-lookup"><span data-stu-id="89e54-123">**Media Metrics that Impact Quality**.</span></span> <span data-ttu-id="89e54-124">这些指标涉及呼叫本身的实际传输;也就是说，它们提供一种在网络上呼叫慷慨的旅行日志种类。</span><span class="sxs-lookup"><span data-stu-id="89e54-124">These metrics deal with the actual transmission of the call itself; that is, they provide a sort of travel log as the call journeys across the network.</span></span> <span data-ttu-id="89e54-125">这些指标（包括诸如数据包丢失、抖动和往返行程之类的内容）提供有关在呼叫离开终结点到到达其他人的终结点时所发生的情况的信息。</span><span class="sxs-lookup"><span data-stu-id="89e54-125">These metrics (which include such things as packet loss, jitter, and round trip times) provide information on what happened to the call from the time it left your endpoint to the time it arrived at the other person's endpoint.</span></span>

  - <span data-ttu-id="89e54-126">**报告给最终用户的问题**。</span><span class="sxs-lookup"><span data-stu-id="89e54-126">**Issues Reported to the End User**.</span></span> <span data-ttu-id="89e54-127">这些指标包括在以下情况下 Lync 2013 的质量较差通知： Lync 在以下情况下向最终用户提供的信号较差：计算机的声音太远、网络连接较差或质量较差，因为计算机上的其他程序占用可用的资源。</span><span class="sxs-lookup"><span data-stu-id="89e54-127">These metrics include poor quality notifications that Lync 2013 presents to end users in cases where they are too far from a microphone, speaking too softly, have a poor network connection, or are experiencing poor quality because another program on the computer is consuming the available resources.</span></span>

  - <span data-ttu-id="89e54-p109">**环境信息**。这些指标详细说明了呼叫质量因素，如所使用的麦克风和扬声器的类型、用户是否通过 VPN 连接进行连接以及用户是否使用无线连接。</span><span class="sxs-lookup"><span data-stu-id="89e54-p109">**Environment Information**. These metrics detail call quality factors such as the type of microphone and speakers being used, whether the user is connected through a VPN connection, and whether the user is on a wireless connection.</span></span>

<span data-ttu-id="89e54-130">在每次通话结束时，SIP 兼容终结点会自动将此信息传输到主持呼叫的前端服务器。</span><span class="sxs-lookup"><span data-stu-id="89e54-130">At the end of each call, SIP-compliant endpoints automatically transmit this information to the Front End server that facilitated the call.</span></span> <span data-ttu-id="89e54-131">你不必执行任何操作就能让终结点传输该信息；该行为内置于 SIP 协议中。</span><span class="sxs-lookup"><span data-stu-id="89e54-131">You don't have to do anything to get endpoints to transmit that information; that behavior is built into the SIP protocol.</span></span> <span data-ttu-id="89e54-132">但是，如果要收集和存储该信息，则需要安装和启用监控。</span><span class="sxs-lookup"><span data-stu-id="89e54-132">However, if you want to collect and store that information, then you need to install and enable monitoring.</span></span> <span data-ttu-id="89e54-133">如果确实安装并启用了监控，则呼叫信息将由前端服务器上运行的代理收集，并被中继到一对 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="89e54-133">If you do install and enable monitoring, then call information is gathered by agents running on the Front End server and relayed to a pair of SQL Server databases.</span></span>

<span data-ttu-id="89e54-134">请注意，在 Lync Server 2013 中，安装和配置监视的过程已得到简化。</span><span class="sxs-lookup"><span data-stu-id="89e54-134">Note that the process of installing and configuring monitoring has been simplified in Lync Server 2013.</span></span> <span data-ttu-id="89e54-135">在以前版本的软件中，监视需要一个单独的监视服务器角色，该角色通常表示将单独的计算机用作监视服务器。</span><span class="sxs-lookup"><span data-stu-id="89e54-135">In prior versions of the software, monitoring required a separate Monitoring Server role, which typically meant a separate computer set aside for use as the Monitoring Server.</span></span> <span data-ttu-id="89e54-136">但是，在 Lync Server 2013 中，已消除了监视服务器角色。</span><span class="sxs-lookup"><span data-stu-id="89e54-136">In Lync Server 2013, however, the Monitoring Server role has been eliminated.</span></span> <span data-ttu-id="89e54-137">相反，监视服务（以 "统一数据收集代理" 的形式）已 collocated 到所有前端服务器中。</span><span class="sxs-lookup"><span data-stu-id="89e54-137">Instead, the monitoring service (in the form of "unified data collection agents") has been collocated into all Front End servers.</span></span> <span data-ttu-id="89e54-138">这至少有两个主要优点。</span><span class="sxs-lookup"><span data-stu-id="89e54-138">This has at least two major benefits.</span></span> <span data-ttu-id="89e54-139">监视服务的 Collocation：</span><span class="sxs-lookup"><span data-stu-id="89e54-139">Collocation of the monitoring service:</span></span>

  - <span data-ttu-id="89e54-140">减少实现 Lync Server 2013 时所需的服务器角色数。</span><span class="sxs-lookup"><span data-stu-id="89e54-140">Decreases the number of server roles required when implementing Lync Server 2013.</span></span> <span data-ttu-id="89e54-141">通过减少监视服务器角色，还可以通过消除维护专用服务器的需要来帮助降低成本。</span><span class="sxs-lookup"><span data-stu-id="89e54-141">Decrementing the Monitoring Server role also helps reduce costs by eliminating the need to maintain dedicated servers for monitoring.</span></span>

  - <span data-ttu-id="89e54-142">降低了 Lync Server 2013 设置和管理的复杂性。</span><span class="sxs-lookup"><span data-stu-id="89e54-142">Reduces the complexity of Lync Server 2013 setup and administration.</span></span> <span data-ttu-id="89e54-143">通过 collocating 每个前端服务器上的监视服务，您不必再安装、配置和管理监视服务器角色。</span><span class="sxs-lookup"><span data-stu-id="89e54-143">By collocating the monitoring services on each Front End server you no longer have to install, configure, and manage the Monitoring Server role.</span></span>

<span data-ttu-id="89e54-144">有关详细信息，请参阅 Lync Server 2013 2013 部署指南中的在[Lync server 2013 中部署监视](lync-server-2013-deploying-monitoring.md)主题。</span><span class="sxs-lookup"><span data-stu-id="89e54-144">For more information see the topic [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md) in the Lync Server 2013 2013 deployment guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

