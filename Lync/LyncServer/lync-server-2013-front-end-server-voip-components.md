---
title: Lync Server 2013：前端服务器 VoIP 组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0be06c357fd3b02b2a44f4ba8f4aebfaab99f609
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="front-end-server-voip-components-for-lync-server-2013"></a><span data-ttu-id="68bb2-102">Lync Server 2013 的前端服务器 VoIP 组件</span><span class="sxs-lookup"><span data-stu-id="68bb2-102">Front End Server VoIP components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68bb2-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="68bb2-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="68bb2-104">位于前端服务器上的 VoIP 组件如下所示：</span><span class="sxs-lookup"><span data-stu-id="68bb2-104">The VoIP components located on Front End Servers are as follows:</span></span>

  - <span data-ttu-id="68bb2-105">转换服务</span><span class="sxs-lookup"><span data-stu-id="68bb2-105">Translation Service</span></span>

  - <span data-ttu-id="68bb2-106">入站路由组件</span><span class="sxs-lookup"><span data-stu-id="68bb2-106">Inbound Routing component</span></span>

  - <span data-ttu-id="68bb2-107">出站路由组件</span><span class="sxs-lookup"><span data-stu-id="68bb2-107">Outbound Routing component</span></span>

  - <span data-ttu-id="68bb2-108">Exchange UM 路由组件</span><span class="sxs-lookup"><span data-stu-id="68bb2-108">Exchange UM Routing component</span></span>

  - <span data-ttu-id="68bb2-109">群集间路由组件</span><span class="sxs-lookup"><span data-stu-id="68bb2-109">Intercluster Routing component</span></span>

  - [<span data-ttu-id="68bb2-110">Lync Server 2013 中的中介服务器组件</span><span class="sxs-lookup"><span data-stu-id="68bb2-110">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a><span data-ttu-id="68bb2-111">转换服务</span><span class="sxs-lookup"><span data-stu-id="68bb2-111">Translation Service</span></span>

<span data-ttu-id="68bb2-p101">转换服务是一个服务器组件，负责根据管理员定义的规范化规则将所拨打的号码转换为 E.164 格式或其他格式。如果组织使用专用编号系统或使用不支持 E.164 的网关或 PBX，则转换服务可以将号码转换为 E.164 以外的格式。</span><span class="sxs-lookup"><span data-stu-id="68bb2-p101">The Translation Service is the server component that is responsible for translating a dialed number into the E.164 format or another format, according to the normalization rules that are defined by the administrator. The Translation Service can translate to formats other than E.164 if your organization uses a private numbering system or uses a gateway or PBX that does not support E.164.</span></span>

</div>

<div>

## <a name="inbound-routing-component"></a><span data-ttu-id="68bb2-114">入站路由组件</span><span class="sxs-lookup"><span data-stu-id="68bb2-114">Inbound Routing Component</span></span>

<span data-ttu-id="68bb2-115">入站路由组件主要根据用户在其企业语音客户端上指定的首选项处理传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="68bb2-115">The Inbound Routing component handles incoming calls largely according to preferences that are specified by users on their Enterprise Voice clients.</span></span> <span data-ttu-id="68bb2-116">它还可以实现代理人响铃和同时响铃（如果用户已配置）。</span><span class="sxs-lookup"><span data-stu-id="68bb2-116">It also facilitates delegate ringing and simultaneous ringing, if configured by the user.</span></span> <span data-ttu-id="68bb2-117">例如，用户指定转接未应答的呼叫，还是仅做记录以通知用户。</span><span class="sxs-lookup"><span data-stu-id="68bb2-117">For example, users specify whether unanswered calls are forwarded or simply logged for notification.</span></span> <span data-ttu-id="68bb2-118">如果启用呼叫转接，用户可以指定是否应将无应答呼叫转发到另一个号码或已配置为提供呼叫应答的 Exchange UM 服务器。</span><span class="sxs-lookup"><span data-stu-id="68bb2-118">If call forwarding is enabled, users can specify whether unanswered calls should be forwarded to another number or to a Exchange UM server that has been configured to provide call answering.</span></span> <span data-ttu-id="68bb2-119">默认情况下，入站路由组件安装在所有 Standard Edition server 和前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="68bb2-119">The Inbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

</div>

<div>

## <a name="outbound-routing-component"></a><span data-ttu-id="68bb2-120">出站路由组件</span><span class="sxs-lookup"><span data-stu-id="68bb2-120">Outbound Routing Component</span></span>

<span data-ttu-id="68bb2-121">出站路由组件将呼叫路由到 PBX 或 PSTN 目标。</span><span class="sxs-lookup"><span data-stu-id="68bb2-121">The Outbound Routing component routes calls to PBX or PSTN destinations.</span></span> <span data-ttu-id="68bb2-122">它将呼叫授权规则（如用户的语音策略所定义）应用于呼叫者，并确定路由每个呼叫的最佳 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="68bb2-122">It applies call authorization rules, as defined by the user’s voice policy, to callers and determines the optimal PSTN gateway for routing each call.</span></span> <span data-ttu-id="68bb2-123">默认情况下，在所有 Standard Edition server 和前端服务器上安装出站路由组件。</span><span class="sxs-lookup"><span data-stu-id="68bb2-123">The Outbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

<span data-ttu-id="68bb2-124">出站路由组件使用的路由逻辑大体上是由网络或电话管理员根据其组织的要求来配置的。</span><span class="sxs-lookup"><span data-stu-id="68bb2-124">The routing logic that is used by the Outbound Routing component is in large measure configured by network or telephony administrators according to the requirements of their organizations.</span></span>

</div>

<div>

## <a name="exchange-um-routing-component"></a><span data-ttu-id="68bb2-125">Exchange UM 路由组件</span><span class="sxs-lookup"><span data-stu-id="68bb2-125">Exchange UM Routing Component</span></span>

<span data-ttu-id="68bb2-126">Exchange UM 路由组件处理 Lync Server 和运行 Exchange 统一消息（UM）的服务器之间的路由，以将 Lync Server 与统一消息功能集成。</span><span class="sxs-lookup"><span data-stu-id="68bb2-126">The Exchange UM routing component handles routing between Lync Server and servers running Exchange Unified Messaging (UM), to integrate Lync Server with Unified Messaging features.</span></span>

<span data-ttu-id="68bb2-127">如果 Exchange UM 服务器不可用，则 Exchange UM 路由组件还会通过 PSTN 处理语音邮件的重新路由。</span><span class="sxs-lookup"><span data-stu-id="68bb2-127">The Exchange UM routing component also handles rerouting of voice mail over the PSTN if Exchange UM servers are unavailable.</span></span> <span data-ttu-id="68bb2-128">如果您的企业语音用户在没有到中央站点的弹性 WAN 链接的分支站点上，则您在分支站点部署的 Survivable 分支设备在 WAN 中断期间为分支用户提供语音邮件留存。</span><span class="sxs-lookup"><span data-stu-id="68bb2-128">If you have Enterprise Voice users at branch sites that do not have a resilient WAN link to a central site, the Survivable Branch Appliance that you deploy at the branch site provides voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="68bb2-129">WAN 链路不可用时，Survivable 分支设备将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="68bb2-129">When the WAN link is unavailable, the Survivable Branch Appliance does the following:</span></span>

  - <span data-ttu-id="68bb2-130">通过 PSTN 将未应答的呼叫重新路由到中央站点上的 Exchange 统一消息服务器</span><span class="sxs-lookup"><span data-stu-id="68bb2-130">reroutes unanswered calls over the PSTN to the Exchange Unified Messaging server in the central site</span></span>

  - <span data-ttu-id="68bb2-131">为用户提供通过 PSTN 取回语音邮件消息的功能</span><span class="sxs-lookup"><span data-stu-id="68bb2-131">provides the ability for a user to retrieve voice mail messages over the PSTN</span></span>

  - <span data-ttu-id="68bb2-132">使错过的呼叫通知排队，然后在 WAN 链路还原时将其上载到 Exchange UM 服务器。</span><span class="sxs-lookup"><span data-stu-id="68bb2-132">queues missed call notifications, and then uploads them to the Exchange UM server when the WAN link is restored.</span></span>

<span data-ttu-id="68bb2-133">若要启用语音邮件重新路由，建议您的 Exchange 管理员将 Exchange UM 自动助理（AA）配置为仅接受邮件。</span><span class="sxs-lookup"><span data-stu-id="68bb2-133">To enable voice mail rerouting, we recommend that your Exchange administrator configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span>

<span data-ttu-id="68bb2-134">有关这些功能的详细信息，请参阅在 lync server [2013 中规划 Exchange 统一消息集成](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)和[在 lync Server 2013 中规划企业语音恢复](lync-server-2013-planning-for-enterprise-voice-resiliency.md)。</span><span class="sxs-lookup"><span data-stu-id="68bb2-134">For details about these features, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Planning for Enterprise Voice resiliency in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md), respectively.</span></span>

</div>

<div>

## <a name="intercluster-routing-component"></a><span data-ttu-id="68bb2-135">群集间路由组件</span><span class="sxs-lookup"><span data-stu-id="68bb2-135">Intercluster Routing Component</span></span>

<span data-ttu-id="68bb2-p105">群集间路由组件负责将呼叫路由至被叫方的主注册器池。如果该池不可用，则组件将呼叫路由至被叫方的备份注册器池。如果无法通过 IP 网络访问被叫方的主注册器池和备份注册器池，则群集间路由组件会通过 PSTN 将呼叫重新路由至用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="68bb2-p105">The Intercluster routing component is responsible for routing calls to the callee’s primary Registrar pool. If that is unavailable, the component routes the call to the callee’s backup Registrar pool. If the callee’s primary and backup Registrar pools are unreachable over the IP network, the Intercluster routing component reroutes the call over the PSTN to the user’s telephone number.</span></span>

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a><span data-ttu-id="68bb2-139">VoIP 所需的其他前端服务器组件</span><span class="sxs-lookup"><span data-stu-id="68bb2-139">Other Front End Server Components Required for VoIP</span></span>

<span data-ttu-id="68bb2-140">驻留在前端服务器上的其他组件或提供对 VoIP 的基本支持的其他组件，但不是其本身的 VoIP 组件，包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="68bb2-140">Other components residing on the Front End Server or Director that provide essential support for VoIP, but are not themselves VoIP components, include the following:</span></span>

  - <span data-ttu-id="68bb2-141">**用户服务。**</span><span class="sxs-lookup"><span data-stu-id="68bb2-141">**User Services.**</span></span> <span data-ttu-id="68bb2-142">对每个传入呼叫的目标电话号码执行反向号码查找，并将该号码与目标用户的 SIP URI 进行匹配。</span><span class="sxs-lookup"><span data-stu-id="68bb2-142">Perform reverse number lookup on the destination phone number of each incoming call and match that number to the SIP URI of the destination user.</span></span> <span data-ttu-id="68bb2-143">入站路由组件利用这一信息将呼叫分发到该用户的已注册 SIP 终结点。</span><span class="sxs-lookup"><span data-stu-id="68bb2-143">Using this information, the Inbound Routing component distributes the call to that user’s registered SIP endpoints.</span></span> <span data-ttu-id="68bb2-144">用户服务是所有前端服务器和控制器上的核心组件。</span><span class="sxs-lookup"><span data-stu-id="68bb2-144">User Services is a core component on all Front End Servers and Directors.</span></span>

  - <span data-ttu-id="68bb2-145">**用户复制程序。**</span><span class="sxs-lookup"><span data-stu-id="68bb2-145">**User Replicator.**</span></span> <span data-ttu-id="68bb2-146">从 Active Directory 域服务中提取用户电话号码，并将其写入到 RTC 数据库中的表中，用户服务和通讯簿服务器可使用这些号码。</span><span class="sxs-lookup"><span data-stu-id="68bb2-146">Extracts user phone numbers from Active Directory Domain Services and writes them to tables in the RTC database, where they are available to User Services and Address Book Server.</span></span> <span data-ttu-id="68bb2-147">用户复制程序是所有前端服务器上的核心组件。</span><span class="sxs-lookup"><span data-stu-id="68bb2-147">User Replicator is a core component on all Front End Servers.</span></span>

  - <span data-ttu-id="68bb2-148">**通讯簿服务器。**</span><span class="sxs-lookup"><span data-stu-id="68bb2-148">**Address Book Server.**</span></span> <span data-ttu-id="68bb2-149">提供从 Active Directory 域服务到 Lync Server 客户端的全局地址列表信息。</span><span class="sxs-lookup"><span data-stu-id="68bb2-149">Provides global address list information from Active Directory Domain Services to Lync Server clients.</span></span> <span data-ttu-id="68bb2-150">它还从 RTC 数据库中检索用户和联系人信息，并将信息写入通讯簿文件，然后将这些文件存储在由 Lync 客户端下载这些文件的共享文件夹中。</span><span class="sxs-lookup"><span data-stu-id="68bb2-150">It also retrieves user and contact information from the RTC database, writes the information to the Address Book files, and then stores the files on a shared folder where they are downloaded by Lync clients.</span></span> <span data-ttu-id="68bb2-151">通讯簿服务器将信息写入 RTCAb 数据库，通讯簿 Web 查询服务使用该数据库响应来自 Microsoft Lync 2010 Mobile 的用户搜索查询。</span><span class="sxs-lookup"><span data-stu-id="68bb2-151">The Address Book Server writes the information to the RTCAb database, which is used by the Address Book Web Query service to respond to user search queries from Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="68bb2-152">它还可以规范化为在 Lync 中预配用户联系人而写入 RTC 数据库的企业用户电话号码。</span><span class="sxs-lookup"><span data-stu-id="68bb2-152">It optionally normalizes enterprise user phone numbers that are written to the RTC database for the purpose of provisioning user contacts in Lync.</span></span> <span data-ttu-id="68bb2-153">默认情况下，通讯簿服务安装在所有前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="68bb2-153">The Address Book service is installed by default on all Front End Servers.</span></span> <span data-ttu-id="68bb2-154">默认情况下，会随每台前端服务器上的 Web 服务一起安装通讯簿 Web 查询服务。</span><span class="sxs-lookup"><span data-stu-id="68bb2-154">The Address Book Web Query service is installed by default with the Web services on each Front End Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

