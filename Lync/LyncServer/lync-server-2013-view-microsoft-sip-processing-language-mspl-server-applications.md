---
title: 查看 Microsoft SIP 处理语言 (MSPL) 服务器应用程序
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
ms.openlocfilehash: 63c1ce638e6bc9509c8faf46b39989b366f610a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a><span data-ttu-id="bdf24-102">在 Lync Server 2013 中查看 Microsoft SIP 处理语言 (MSPL) 服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="bdf24-102">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdf24-103">_**主题上次修改时间：** 2014-09-26_</span><span class="sxs-lookup"><span data-stu-id="bdf24-103">_**Topic Last Modified:** 2014-09-26_</span></span>

<span data-ttu-id="bdf24-104">Microsoft SIP 处理语言（MSPL）服务器应用程序是一个仅脚本的应用程序，该应用程序使用脚本语言而不是 Microsoft Lync 2010 API。</span><span class="sxs-lookup"><span data-stu-id="bdf24-104">A Microsoft SIP Processing Language (MSPL) server application is a script-only application that uses a scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="bdf24-105">MSPL 提供对筛选和代理行为的更精细的控制，以及用于向基于事务的 SIP 应用程序调度特定消息的功能。</span><span class="sxs-lookup"><span data-stu-id="bdf24-105">MSPL provides more granular control over filtering and proxy behaviors, in addition to a facility for dispatching specific messages to transaction-based SIP applications.</span></span> <span data-ttu-id="bdf24-106">MSPL 专门用于筛选和路由 SIP 消息。</span><span class="sxs-lookup"><span data-stu-id="bdf24-106">MSPL is used specifically for filtering and routing SIP messages.</span></span> <span data-ttu-id="bdf24-107">MSPL 应用程序在与 UserServices 模块相同的进程中运行，而基于 Lync 2010 API 的程序在单独的进程中运行。</span><span class="sxs-lookup"><span data-stu-id="bdf24-107">MSPL applications run in the same process as the UserServices module, while a program that is based on the Lync 2010 API runs in a separate process.</span></span>

<span data-ttu-id="bdf24-108">你可以使用 Lync Server 控制面板的 "**拓扑**" 组中的 "**服务器应用程序**" 页面查看在 Lync server 2013 环境中的前端服务器上运行的 MSPL 服务器应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="bdf24-108">You can use the **Server Application** page in the **Topology** group of Lync Server Control Panel to see a list of MSPL server applications that run on Front End Servers in your Lync Server 2013 environment.</span></span> <span data-ttu-id="bdf24-109">该列表显示了每个池可用的脚本以及它们是否已启用或关键。</span><span class="sxs-lookup"><span data-stu-id="bdf24-109">The list shows the scripts that are available for each pool, as well as whether they are enabled or critical.</span></span> <span data-ttu-id="bdf24-110">脚本将按照它们列出的顺序运行。</span><span class="sxs-lookup"><span data-stu-id="bdf24-110">The scripts run in the order they are listed.</span></span>

<span data-ttu-id="bdf24-111">这些脚本包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="bdf24-111">These scripts include the following:</span></span>

  - <span data-ttu-id="bdf24-112">ClientVersionFilter 向管理员提供一种方法来指定池支持的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="bdf24-112">ClientVersionFilter provides the administrator with a way to specify the version of clients that are supported by a pool.</span></span> <span data-ttu-id="bdf24-113">客户端版本筛选器检查客户端版本，并可阻止客户端登录或向用户显示一条消息，指示用户正在使用不受支持的客户端。</span><span class="sxs-lookup"><span data-stu-id="bdf24-113">The client version filter checks the client version and can either prevent the client from logging on or present the user with a message that indicates he or she is using a client that is not supported.</span></span> <span data-ttu-id="bdf24-114">客户端版本筛选器还可以配置为向用户显示一条消息，其中包含最新可下载版本的客户端的 URL。</span><span class="sxs-lookup"><span data-stu-id="bdf24-114">The client version filter can also be configured to display a message to the user that contains the URL of the latest downloadable version of the client.</span></span>

  - <span data-ttu-id="bdf24-115">TranslationService 将根据管理员定义的规范化规则转换用户拨打的电子号码为164的数字。</span><span class="sxs-lookup"><span data-stu-id="bdf24-115">TranslationService translates a number that a user dials to an E.164 number according to the normalization rules defined by the administrator.</span></span> <span data-ttu-id="bdf24-116">有关详细信息，请参阅[Lync Server 2013 中的翻译规则](lync-server-2013-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="bdf24-116">For details, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md).</span></span>

  - <span data-ttu-id="bdf24-117">IncomingFederation 强制实施租户级联合身份验证，用于租户内部部署和来自外部部署的传入消息。</span><span class="sxs-lookup"><span data-stu-id="bdf24-117">IncomingFederation enforces tenant-level federation validation for inter-tenant and incoming messages from external deployments.</span></span>

  - <span data-ttu-id="bdf24-118">UserServices 是前端服务器的 SIP 注册机构、状态和会议组件。</span><span class="sxs-lookup"><span data-stu-id="bdf24-118">UserServices is the SIP Registrar, presence, and conferencing component of a Front End Server.</span></span> <span data-ttu-id="bdf24-119">它提供了在 SIP 代理的基础上构建的紧密集成的 IM、状态和会议功能。</span><span class="sxs-lookup"><span data-stu-id="bdf24-119">It provides closely integrated IM, presence, and conferencing features built on top of the SIP Proxy.</span></span>

  - <span data-ttu-id="bdf24-120">InterClusterRouting 负责将呼叫路由到被调用方的主注册池。</span><span class="sxs-lookup"><span data-stu-id="bdf24-120">InterClusterRouting is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="bdf24-121">有关详细信息，请参阅[Lync server 2013 的前端服务器 VoIP 组件](lync-server-2013-front-end-server-voip-components.md)。</span><span class="sxs-lookup"><span data-stu-id="bdf24-121">For details, see [Front End Server VoIP components for Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span></span>

  - <span data-ttu-id="bdf24-122">IIMFilter （智能 IM 筛选器）阻止包含可单击的 Url 或尝试启动文件传输的邮件。</span><span class="sxs-lookup"><span data-stu-id="bdf24-122">IIMFilter (Intelligent IM Filter) blocks messages that contain clickable URLs or that attempt to initiate file transfers.</span></span> <span data-ttu-id="bdf24-123">IIMFilter 还会代表服务器检查客户端版本。</span><span class="sxs-lookup"><span data-stu-id="bdf24-123">IIMFilter also checks the client version on behalf of the server.</span></span> <span data-ttu-id="bdf24-124">IIMFilter 影响通过使用 Lync Server 或 Communicator 启动的文件传输。</span><span class="sxs-lookup"><span data-stu-id="bdf24-124">IIMFilter affects file transfers that are initiated by using either Lync Server or Communicator.</span></span> <span data-ttu-id="bdf24-125">默认情况下，通过在链接的第一个字符前面添加一个下划线字符来禁用可点击的链接。</span><span class="sxs-lookup"><span data-stu-id="bdf24-125">By default, clickable links are disabled by adding an underscore character before the first character of the link.</span></span> <span data-ttu-id="bdf24-126">管理员可以更改此行为，以便阻止链接，在这种情况下，包含可单击的 Url 的邮件或尝试启动文件传输的邮件将被服务器阻止到达其预定目的地。</span><span class="sxs-lookup"><span data-stu-id="bdf24-126">An administrator can change this behavior so that the link is blocked, in which case messages that contain clickable URLs or that attempt to initiate a file transfer are blocked by the server from reaching their intended destinations.</span></span> <span data-ttu-id="bdf24-127">IIMFilter 安装在代理服务器和存档服务器以外的所有运行 Lync Server 的服务器上。</span><span class="sxs-lookup"><span data-stu-id="bdf24-127">IIMFilter is installed on all servers running Lync Server except Proxy Servers and Archiving Servers.</span></span>

  - <span data-ttu-id="bdf24-128">UserPinService 用于验证电话拨入式会议的用户个人识别码（Pin）。</span><span class="sxs-lookup"><span data-stu-id="bdf24-128">UserPinService is used to verify user personal identification numbers (PINs) for dial-in conferencing.</span></span>

  - <span data-ttu-id="bdf24-129">DefaultRouting 是运行 Lync Server 的服务器的默认路由应用程序。</span><span class="sxs-lookup"><span data-stu-id="bdf24-129">DefaultRouting is the default routing application for servers running Lync Server.</span></span> <span data-ttu-id="bdf24-130">默认情况下，它处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="bdf24-130">It is enabled by default.</span></span> <span data-ttu-id="bdf24-131">路由应用程序安装在所有标准版和企业版服务器上。</span><span class="sxs-lookup"><span data-stu-id="bdf24-131">The routing application is installed on all Standard Edition and Enterprise Edition servers.</span></span>

  - <span data-ttu-id="bdf24-132">ExumRouting 路由到 Exchange Server 统一消息（UM）的呼叫。</span><span class="sxs-lookup"><span data-stu-id="bdf24-132">ExumRouting routes calls to Exchange Server Unified Messaging (UM).</span></span> <span data-ttu-id="bdf24-133">ExumRouting 确定要放入新的语音邮件时将呼叫路由到的相应 Exchange UM 服务器。</span><span class="sxs-lookup"><span data-stu-id="bdf24-133">ExumRouting determines the appropriate Exchange UM server to route the call to when there is a new voice mail message to deposit.</span></span> <span data-ttu-id="bdf24-134">ExumRouting 还处理其他一些 Exchange UM 集成方面，包括路由到自动助理和订阅者访问。</span><span class="sxs-lookup"><span data-stu-id="bdf24-134">ExumRouting also handles some other Exchange UM integration aspects, including routing to Auto Attendant and Subscriber Access.</span></span>

  - <span data-ttu-id="bdf24-135">OutboundRouting 确定根据所拨号码和用户的拨号授权将呼叫路由到电话号码的网关。</span><span class="sxs-lookup"><span data-stu-id="bdf24-135">OutboundRouting determines the gateway that routes a call to a phone number according to the dialed number and the user’s dialing authorization.</span></span> <span data-ttu-id="bdf24-136">如果网关无法处理呼叫，OutboundRouting 还会处理呼叫的重新路由。</span><span class="sxs-lookup"><span data-stu-id="bdf24-136">OutboundRouting also handles rerouting of calls if a gateway cannot process a call.</span></span>

  - <span data-ttu-id="bdf24-137">QoEAgent 通过 SIP 服务请求从终结点接收数据报表质量（QoE），并使用 HTTP POST 将数据发送到监视服务器或第三方使用者的目标队列。</span><span class="sxs-lookup"><span data-stu-id="bdf24-137">QoEAgent receives Quality of Experience (QoE) data reports from endpoints through SIP SERVICE requests, and sends the data to the destination queue on the Monitoring Server or to third-party consumers using HTTP POST.</span></span> <span data-ttu-id="bdf24-138">有关详细信息，请参阅[在 Lync Server 2013 中部署监视](lync-server-2013-deploying-monitoring.md)。</span><span class="sxs-lookup"><span data-stu-id="bdf24-138">For details, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

  - <span data-ttu-id="bdf24-139">OutgoingFederation 将为转到目标外部部署的邮件强制执行租户级别的联合身份验证验证。</span><span class="sxs-lookup"><span data-stu-id="bdf24-139">OutgoingFederation enforces tenant-level federation validation for messages going to a targeted external deployment.</span></span>

  - <span data-ttu-id="bdf24-140">AcpRouting 代理将邀请音频会议提供商的请求发送到音频会议提供商网关。</span><span class="sxs-lookup"><span data-stu-id="bdf24-140">AcpRouting proxies INVITE requests destined for the audio conferencing provider to the audio conferencing provider gateway.</span></span>

<span data-ttu-id="bdf24-141">在边缘服务器上运行的脚本包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="bdf24-141">Scripts that run on Edge Servers include the following:</span></span>

  - <span data-ttu-id="bdf24-142">IIMFilter</span><span class="sxs-lookup"><span data-stu-id="bdf24-142">IIMFilter</span></span>

  - <span data-ttu-id="bdf24-143">OptionsHandler 响应传入选项请求200如果请求是当前服务器的目标，则为**OK** 。</span><span class="sxs-lookup"><span data-stu-id="bdf24-143">OptionsHandler responds to incoming OPTIONS requests with **200 OK** if the request is destined for the current server.</span></span> <span data-ttu-id="bdf24-144">这用于拓扑验证。</span><span class="sxs-lookup"><span data-stu-id="bdf24-144">This is used for topology validation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="bdf24-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bdf24-145">See Also</span></span>


[<span data-ttu-id="bdf24-146">在 Lync Server 2013 中启用或禁用 Microsoft SIP 处理语言（MSPL）服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="bdf24-146">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[<span data-ttu-id="bdf24-147">在 Lync Server 2013 中将 Microsoft SIP 处理语言（MSPL）应用程序标记为关键或非关键应用程序</span><span class="sxs-lookup"><span data-stu-id="bdf24-147">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

