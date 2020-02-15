---
title: 查看 Microsoft SIP 处理语言（MSPL）服务器应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d0572ad17d5359cf082c6bd06ab722d8322180e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a><span data-ttu-id="36471-102">在 Lync Server 2013 中查看 Microsoft SIP 处理语言（MSPL）服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="36471-102">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36471-103">_**上次修改的主题：** 2014-09-26_</span><span class="sxs-lookup"><span data-stu-id="36471-103">_**Topic Last Modified:** 2014-09-26_</span></span>

<span data-ttu-id="36471-104">Microsoft SIP 处理语言（MSPL）服务器应用程序是一个仅脚本的应用程序，它使用脚本语言而不是 Microsoft Lync 2010 API。</span><span class="sxs-lookup"><span data-stu-id="36471-104">A Microsoft SIP Processing Language (MSPL) server application is a script-only application that uses a scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="36471-105">除提供将特定消息分派到基于事务的 SIP 应用程序的工具之外，MSPL 还提供了对筛选和代理行为的更精细控制。</span><span class="sxs-lookup"><span data-stu-id="36471-105">MSPL provides more granular control over filtering and proxy behaviors, in addition to a facility for dispatching specific messages to transaction-based SIP applications.</span></span> <span data-ttu-id="36471-106">MSPL 专门用于筛选和路由 SIP 消息。</span><span class="sxs-lookup"><span data-stu-id="36471-106">MSPL is used specifically for filtering and routing SIP messages.</span></span> <span data-ttu-id="36471-107">MSPL 应用程序在与 UserServices 模块相同的进程中运行，而基于 Lync 2010 API 的程序在单独的进程中运行。</span><span class="sxs-lookup"><span data-stu-id="36471-107">MSPL applications run in the same process as the UserServices module, while a program that is based on the Lync 2010 API runs in a separate process.</span></span>

<span data-ttu-id="36471-108">您可以使用 Lync Server 控制面板的**拓扑**组中的 "**服务器应用程序**" 页来查看在 Lync server 2013 环境中运行在前端服务器上的 MSPL 服务器应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="36471-108">You can use the **Server Application** page in the **Topology** group of Lync Server Control Panel to see a list of MSPL server applications that run on Front End Servers in your Lync Server 2013 environment.</span></span> <span data-ttu-id="36471-109">列表显示了可供每个池使用的脚本，以及它们是否处于已启用或关键状态。</span><span class="sxs-lookup"><span data-stu-id="36471-109">The list shows the scripts that are available for each pool, as well as whether they are enabled or critical.</span></span> <span data-ttu-id="36471-110">脚本按照所列的顺序运行。</span><span class="sxs-lookup"><span data-stu-id="36471-110">The scripts run in the order they are listed.</span></span>

<span data-ttu-id="36471-111">这些脚本包括：</span><span class="sxs-lookup"><span data-stu-id="36471-111">These scripts include the following:</span></span>

  - <span data-ttu-id="36471-p103">ClientVersionFilter，可供管理员用来指定某个池所支持的客户端版本。客户端版本筛选器检查客户端版本，并可以阻止客户端登录或向用户显示一个消息，指出他（或她）所使用的客户端不受支持。还可以对客户端版本筛选器进行配置，向用户显示包含客户端的最新可下载版本的 URL 的消息。</span><span class="sxs-lookup"><span data-stu-id="36471-p103">ClientVersionFilter provides the administrator with a way to specify the version of clients that are supported by a pool. The client version filter checks the client version and can either prevent the client from logging on or present the user with a message that indicates he or she is using a client that is not supported. The client version filter can also be configured to display a message to the user that contains the URL of the latest downloadable version of the client.</span></span>

  - <span data-ttu-id="36471-115">TranslationService，根据管理员定义的规范化规则将用户拨打的号码转换为一个 E.164 号码。</span><span class="sxs-lookup"><span data-stu-id="36471-115">TranslationService translates a number that a user dials to an E.164 number according to the normalization rules defined by the administrator.</span></span> <span data-ttu-id="36471-116">有关详细信息，请参阅[Lync Server 2013 中的转换规则](lync-server-2013-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="36471-116">For details, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md).</span></span>

  - <span data-ttu-id="36471-117">IncomingFederation 用于对从外部部署传入的租户间的消息强制执行租户级别的联盟验证。</span><span class="sxs-lookup"><span data-stu-id="36471-117">IncomingFederation enforces tenant-level federation validation for inter-tenant and incoming messages from external deployments.</span></span>

  - <span data-ttu-id="36471-p105">UserServices 是前端服务器的 SIP 注册器、状态指示和会议组件。它提供构建于 SIP 代理之上、紧密集成的 IM、状态指示和会议功能。</span><span class="sxs-lookup"><span data-stu-id="36471-p105">UserServices is the SIP Registrar, presence, and conferencing component of a Front End Server. It provides closely integrated IM, presence, and conferencing features built on top of the SIP Proxy.</span></span>

  - <span data-ttu-id="36471-120">InterClusterRouting 负责将呼叫路由至被叫方的主注册器池。</span><span class="sxs-lookup"><span data-stu-id="36471-120">InterClusterRouting is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="36471-121">有关详细信息，请参阅[前端服务器 VoIP 组件 For Lync Server 2013](lync-server-2013-front-end-server-voip-components.md)。</span><span class="sxs-lookup"><span data-stu-id="36471-121">For details, see [Front End Server VoIP components for Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span></span>

  - <span data-ttu-id="36471-122">IIMFilter（智能 IM 筛选器）阻止包含可单击的 URL 的消息，或阻止尝试启动文件传输的消息。</span><span class="sxs-lookup"><span data-stu-id="36471-122">IIMFilter (Intelligent IM Filter) blocks messages that contain clickable URLs or that attempt to initiate file transfers.</span></span> <span data-ttu-id="36471-123">IIMFilter 还代表服务器检查客户端版本。</span><span class="sxs-lookup"><span data-stu-id="36471-123">IIMFilter also checks the client version on behalf of the server.</span></span> <span data-ttu-id="36471-124">IIMFilter 影响使用 Lync Server 或 Communicator 启动的文件传输。</span><span class="sxs-lookup"><span data-stu-id="36471-124">IIMFilter affects file transfers that are initiated by using either Lync Server or Communicator.</span></span> <span data-ttu-id="36471-125">默认情况下，在可单击链接的第一个字符之前添加一个下划线可以禁用该链接。</span><span class="sxs-lookup"><span data-stu-id="36471-125">By default, clickable links are disabled by adding an underscore character before the first character of the link.</span></span> <span data-ttu-id="36471-126">管理员可以更改此行为以阻止该链接，此时，包含可单击的 URL 的消息或尝试启动文件传输的消息将被服务器阻止，无法到达预定的目的地。</span><span class="sxs-lookup"><span data-stu-id="36471-126">An administrator can change this behavior so that the link is blocked, in which case messages that contain clickable URLs or that attempt to initiate a file transfer are blocked by the server from reaching their intended destinations.</span></span> <span data-ttu-id="36471-127">IIMFilter 安装在代理服务器和存档服务器之外的所有运行 Lync Server 的服务器上。</span><span class="sxs-lookup"><span data-stu-id="36471-127">IIMFilter is installed on all servers running Lync Server except Proxy Servers and Archiving Servers.</span></span>

  - <span data-ttu-id="36471-128">UserPinService 用于验证电话拨入式会议的用户个人标识号 (PIN)。</span><span class="sxs-lookup"><span data-stu-id="36471-128">UserPinService is used to verify user personal identification numbers (PINs) for dial-in conferencing.</span></span>

  - <span data-ttu-id="36471-129">DefaultRouting 是运行 Lync Server 的服务器的默认路由应用程序。</span><span class="sxs-lookup"><span data-stu-id="36471-129">DefaultRouting is the default routing application for servers running Lync Server.</span></span> <span data-ttu-id="36471-130">默认情况下处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="36471-130">It is enabled by default.</span></span> <span data-ttu-id="36471-131">该路由应用程序安装在所有 Standard Edition Server 和 Enterprise Edition Server 上。</span><span class="sxs-lookup"><span data-stu-id="36471-131">The routing application is installed on all Standard Edition and Enterprise Edition servers.</span></span>

  - <span data-ttu-id="36471-p109">ExumRouting 将呼叫路由到 Exchange Server 统一消息 (UM)。当有新的语音邮件需要处理时，ExumRouting 会确定要将呼叫路由到的相应 Exchange UM 服务器。ExumRouting 还会处理 Exchange UM 集成的其他一些方面，包括路由到自动助理和订阅者访问。</span><span class="sxs-lookup"><span data-stu-id="36471-p109">ExumRouting routes calls to Exchange Server Unified Messaging (UM). ExumRouting determines the appropriate Exchange UM server to route the call to when there is a new voice mail message to deposit. ExumRouting also handles some other Exchange UM integration aspects, including routing to Auto Attendant and Subscriber Access.</span></span>

  - <span data-ttu-id="36471-p110">OutboundRouting 根据拨打的电话号码和用户的拨号权限来确定路由对该号码的呼叫的网关。如果网关无法处理呼叫，OutboundRouting 还会处理呼叫的重新路由。</span><span class="sxs-lookup"><span data-stu-id="36471-p110">OutboundRouting determines the gateway that routes a call to a phone number according to the dialed number and the user’s dialing authorization. OutboundRouting also handles rerouting of calls if a gateway cannot process a call.</span></span>

  - <span data-ttu-id="36471-137">QoEAgent 通过 SIP SERVICE 请求接收来自终结点的用户体验质量 (QoE) 数据报告，并通过 HTTP POST 将数据发送至监控服务器上的目标队列或第三方使用者。</span><span class="sxs-lookup"><span data-stu-id="36471-137">QoEAgent receives Quality of Experience (QoE) data reports from endpoints through SIP SERVICE requests, and sends the data to the destination queue on the Monitoring Server or to third-party consumers using HTTP POST.</span></span> <span data-ttu-id="36471-138">有关详细信息，请参阅[在 Lync Server 2013 中部署监控](lync-server-2013-deploying-monitoring.md)。</span><span class="sxs-lookup"><span data-stu-id="36471-138">For details, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

  - <span data-ttu-id="36471-139">OutgoingFederation 可对发送外部目标部署的消息强制执行租户级别的联盟验证。</span><span class="sxs-lookup"><span data-stu-id="36471-139">OutgoingFederation enforces tenant-level federation validation for messages going to a targeted external deployment.</span></span>

  - <span data-ttu-id="36471-140">AcpRouting 可将发往音频会议提供商的 INVITE 请求代理到音频会议提供商网关。</span><span class="sxs-lookup"><span data-stu-id="36471-140">AcpRouting proxies INVITE requests destined for the audio conferencing provider to the audio conferencing provider gateway.</span></span>

<span data-ttu-id="36471-141">在边缘服务器上运行的脚本包括：</span><span class="sxs-lookup"><span data-stu-id="36471-141">Scripts that run on Edge Servers include the following:</span></span>

  - <span data-ttu-id="36471-142">IIMFilter</span><span class="sxs-lookup"><span data-stu-id="36471-142">IIMFilter</span></span>

  - <span data-ttu-id="36471-143">OptionsHandler 可在包含 **200 OK** 的传入 OPTIONS 请求发往当前服务器时对其进行响应。</span><span class="sxs-lookup"><span data-stu-id="36471-143">OptionsHandler responds to incoming OPTIONS requests with **200 OK** if the request is destined for the current server.</span></span> <span data-ttu-id="36471-144">这可以用于验证拓扑。</span><span class="sxs-lookup"><span data-stu-id="36471-144">This is used for topology validation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="36471-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36471-145">See Also</span></span>


[<span data-ttu-id="36471-146">在 Lync Server 2013 中启用或禁用 Microsoft SIP 处理语言（MSPL）服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="36471-146">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[<span data-ttu-id="36471-147">在 Lync Server 2013 中将 Microsoft SIP 处理语言（MSPL）应用程序标记为关键或非关键</span><span class="sxs-lookup"><span data-stu-id="36471-147">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

