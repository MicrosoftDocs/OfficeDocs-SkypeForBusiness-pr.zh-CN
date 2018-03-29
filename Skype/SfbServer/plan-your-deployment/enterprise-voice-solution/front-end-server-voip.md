---
title: Skype for Business Server 2015 的前端服务器 VoIP 组件
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: 了解有关企业语音组件的业务服务器，包括翻译服务和各种路由组件位于前端服务器在 Skype。
ms.openlocfilehash: eca9a83943d045c48b2b811e6370e54fc41f1714
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="front-end-server-voip-components-for-skype-for-business-server-2015"></a><span data-ttu-id="09195-103">Skype for Business Server 2015 的前端服务器 VoIP 组件</span><span class="sxs-lookup"><span data-stu-id="09195-103">Front End Server VoIP components for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="09195-104">了解有关企业语音组件的业务服务器，包括翻译服务和各种路由组件位于前端服务器在 Skype。</span><span class="sxs-lookup"><span data-stu-id="09195-104">Learn about the Enterprise Voice components that are located on Front End Servers in Skype for Business Server, including translation service and various routing components.</span></span>
  
<span data-ttu-id="09195-105">在前端服务器上的 VoIP 组件如下所示：</span><span class="sxs-lookup"><span data-stu-id="09195-105">The VoIP components located on Front End Servers are as follows:</span></span>
  
- <span data-ttu-id="09195-106">转换服务</span><span class="sxs-lookup"><span data-stu-id="09195-106">Translation Service</span></span>
    
- <span data-ttu-id="09195-107">入站路由组件</span><span class="sxs-lookup"><span data-stu-id="09195-107">Inbound Routing component</span></span>
    
- <span data-ttu-id="09195-108">出站路由组件</span><span class="sxs-lookup"><span data-stu-id="09195-108">Outbound Routing component</span></span>
    
- <span data-ttu-id="09195-109">Exchange UM 路由组件</span><span class="sxs-lookup"><span data-stu-id="09195-109">Exchange UM Routing component</span></span>
    
- <span data-ttu-id="09195-110">群集间路由组件</span><span class="sxs-lookup"><span data-stu-id="09195-110">Intercluster Routing component</span></span>
    
- [<span data-ttu-id="09195-111">在业务服务器 2015年的 Skype 的中介服务器组件</span><span class="sxs-lookup"><span data-stu-id="09195-111">Mediation Server component in Skype for Business Server 2015</span></span>](mediation-server.md)
    
## <a name="translation-service"></a><span data-ttu-id="09195-112">转换服务</span><span class="sxs-lookup"><span data-stu-id="09195-112">Translation Service</span></span>

<span data-ttu-id="09195-p101">转换服务是一个服务器组件，负责根据管理员定义的规范化规则将所拨打的号码转换为 E.164 格式或其他格式。如果组织使用专用编号系统或使用不支持 E.164 的网关或 PBX，则转换服务可以将号码转换为 E.164 以外的格式。</span><span class="sxs-lookup"><span data-stu-id="09195-p101">The Translation Service is the server component that is responsible for translating a dialed number into the E.164 format or another format, according to the normalization rules that are defined by the administrator. The Translation Service can translate to formats other than E.164 if your organization uses a private numbering system or uses a gateway or PBX that does not support E.164.</span></span>
  
## <a name="inbound-routing-component"></a><span data-ttu-id="09195-115">入站路由组件</span><span class="sxs-lookup"><span data-stu-id="09195-115">Inbound Routing Component</span></span>

<span data-ttu-id="09195-116">入站路由组件处理很大程度上根据首选项所指定的企业语音客户端上的用户的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="09195-116">The Inbound Routing component handles incoming calls largely according to preferences that are specified by users on their Enterprise Voice clients.</span></span> <span data-ttu-id="09195-117">它还可以实现代理人响铃和同时响铃（如果用户已配置）。</span><span class="sxs-lookup"><span data-stu-id="09195-117">It also facilitates delegate ringing and simultaneous ringing, if configured by the user.</span></span> <span data-ttu-id="09195-118">例如，用户指定转接未应答的呼叫，还是仅做记录以通知用户。</span><span class="sxs-lookup"><span data-stu-id="09195-118">For example, users specify whether unanswered calls are forwarded or simply logged for notification.</span></span> <span data-ttu-id="09195-119">如果启用呼叫转移，则用户可以指定无人应答的呼叫应转发到另一个号码或 Exchange UM 服务器已被配置为提供呼叫应答。</span><span class="sxs-lookup"><span data-stu-id="09195-119">If call forwarding is enabled, users can specify whether unanswered calls should be forwarded to another number or to a Exchange UM server that has been configured to provide call answering.</span></span> <span data-ttu-id="09195-120">入站路由组件是默认安装的所有标准版服务器和前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="09195-120">The Inbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span> 
  
## <a name="outbound-routing-component"></a><span data-ttu-id="09195-121">出站路由组件</span><span class="sxs-lookup"><span data-stu-id="09195-121">Outbound Routing Component</span></span>

<span data-ttu-id="09195-122">出站路由组件将呼叫路由到 PBX 或 PSTN 目标。</span><span class="sxs-lookup"><span data-stu-id="09195-122">The Outbound Routing component routes calls to PBX or PSTN destinations.</span></span> <span data-ttu-id="09195-123">它应用调用授权规则，按照用户的语音策略，向调用方的定义，并确定最佳的 PSTN 网关路由选择的每个调用。</span><span class="sxs-lookup"><span data-stu-id="09195-123">It applies call authorization rules, as defined by the user's voice policy, to callers and determines the optimal PSTN gateway for routing each call.</span></span> <span data-ttu-id="09195-124">出站路由组件是默认安装的所有标准版服务器和前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="09195-124">The Outbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>
  
<span data-ttu-id="09195-125">出站路由组件使用的路由逻辑大体上是由网络或电话管理员根据其组织的要求来配置的。</span><span class="sxs-lookup"><span data-stu-id="09195-125">The routing logic that is used by the Outbound Routing component is in large measure configured by network or telephony administrators according to the requirements of their organizations.</span></span> 
  
## <a name="exchange-um-routing-component"></a><span data-ttu-id="09195-126">Exchange UM 路由组件</span><span class="sxs-lookup"><span data-stu-id="09195-126">Exchange UM Routing Component</span></span>

<span data-ttu-id="09195-127">该 UM Exchange 路由组件处理 Skype 业务服务器和运行 Exchange 统一消息 (UM)，服务器将 Skype 与统一消息功能集成业务服务器之间路由。</span><span class="sxs-lookup"><span data-stu-id="09195-127">The Exchange UM routing component handles routing between Skype for Business Server and servers running Exchange Unified Messaging (UM), to integrate Skype for Business Server with Unified Messaging features.</span></span> 
  
<span data-ttu-id="09195-128">该 UM Exchange 路由组件还可以处理通过 PSTN 重排的语音邮件，如果 Exchange UM 服务器都不可用。</span><span class="sxs-lookup"><span data-stu-id="09195-128">The Exchange UM routing component also handles rerouting of voice mail over the PSTN if Exchange UM servers are unavailable.</span></span> <span data-ttu-id="09195-129">如果您需要在企业语音用户没有弹性的 WAN 链接到中心站点，在分支站点部署高存活力分支装置的分支站点提供语音邮件留存能力对分支用户 WAN 中断。</span><span class="sxs-lookup"><span data-stu-id="09195-129">If you have Enterprise Voice users at branch sites that do not have a resilient WAN link to a central site, the Survivable Branch Appliance that you deploy at the branch site provides voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="09195-130">WAN 链接不可用时，高存活力的分支装置执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="09195-130">When the WAN link is unavailable, the Survivable Branch Appliance does the following:</span></span>
  
- <span data-ttu-id="09195-131">通过 PSTN 将未应答的呼叫重新路由到中央站点上的 Exchange 统一消息服务器</span><span class="sxs-lookup"><span data-stu-id="09195-131">reroutes unanswered calls over the PSTN to the Exchange Unified Messaging server in the central site</span></span>
    
- <span data-ttu-id="09195-132">为用户提供通过 PSTN 取回语音邮件消息的功能</span><span class="sxs-lookup"><span data-stu-id="09195-132">provides the ability for a user to retrieve voice mail messages over the PSTN</span></span>
    
- <span data-ttu-id="09195-133">使错过的呼叫通知排队，然后在 WAN 链路还原时将其上载到 Exchange UM 服务器。</span><span class="sxs-lookup"><span data-stu-id="09195-133">queues missed call notifications, and then uploads them to the Exchange UM server when the WAN link is restored.</span></span>
    
<span data-ttu-id="09195-134">若要启用语音邮件重新路由，我们建议您的 Exchange 管理员配置 Exchange UM 自动助理 (AA) 只接受消息。</span><span class="sxs-lookup"><span data-stu-id="09195-134">To enable voice mail rerouting, we recommend that your Exchange administrator configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span>
  
<span data-ttu-id="09195-135">有关这些功能的详细信息，请参阅[内部 Exchange 统一消息传递集成](http://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx)和[企业语音复原规划](http://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)，分别。</span><span class="sxs-lookup"><span data-stu-id="09195-135">For details about these features, see [On-Premises Exchange Unified Messaging Integration](http://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) and [Planning for Enterprise Voice Resiliency](http://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx), respectively.</span></span>
  
## <a name="intercluster-routing-component"></a><span data-ttu-id="09195-136">群集间路由组件</span><span class="sxs-lookup"><span data-stu-id="09195-136">Intercluster Routing Component</span></span>

<span data-ttu-id="09195-137">Intercluster 的路由组件负责传送调用方的主注册器池。</span><span class="sxs-lookup"><span data-stu-id="09195-137">The Intercluster routing component is responsible for routing calls to the callee's primary Registrar pool.</span></span> <span data-ttu-id="09195-138">如果它不可用，该组件将路由调用被调用方的备份注册器池。</span><span class="sxs-lookup"><span data-stu-id="09195-138">If that is unavailable, the component routes the call to the callee's backup Registrar pool.</span></span> <span data-ttu-id="09195-139">如果被调用方的主要和备份注册器池将通过 IP 网络不可访问，则 Intercluster 路由组件重排通过 PSTN 到用户的电话号码呼叫。</span><span class="sxs-lookup"><span data-stu-id="09195-139">If the callee's primary and backup Registrar pools are unreachable over the IP network, the Intercluster routing component reroutes the call over the PSTN to the user's telephone number.</span></span>
  
## <a name="other-front-end-server-components-required-for-voip"></a><span data-ttu-id="09195-140">VoIP 所需的其他前端服务器组件</span><span class="sxs-lookup"><span data-stu-id="09195-140">Other Front End Server Components Required for VoIP</span></span>

<span data-ttu-id="09195-141">其他组件驻留在前端服务器或控制器上，提供基本支持 VoIP，但不是自己的 VoIP 组件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="09195-141">Other components residing on the Front End Server or Director that provide essential support for VoIP, but are not themselves VoIP components, include the following:</span></span>
  
- <span data-ttu-id="09195-142">**用户服务。**</span><span class="sxs-lookup"><span data-stu-id="09195-142">**User Services.**</span></span> <span data-ttu-id="09195-143">对每个传入呼叫的目标电话号码执行反向号码查找，并将该号码与目标用户的 SIP URI 进行匹配。</span><span class="sxs-lookup"><span data-stu-id="09195-143">Perform reverse number lookup on the destination phone number of each incoming call and match that number to the SIP URI of the destination user.</span></span> <span data-ttu-id="09195-144">使用此信息，该入站路由组件分布到该用户的注册 SIP 终结点的调用。</span><span class="sxs-lookup"><span data-stu-id="09195-144">Using this information, the Inbound Routing component distributes the call to that user's registered SIP endpoints.</span></span> <span data-ttu-id="09195-145">用户服务是核心组件，在所有前端服务器和董事。</span><span class="sxs-lookup"><span data-stu-id="09195-145">User Services is a core component on all Front End Servers and Directors.</span></span>
    
- <span data-ttu-id="09195-146">**用户复制程序。**</span><span class="sxs-lookup"><span data-stu-id="09195-146">**User Replicator.**</span></span> <span data-ttu-id="09195-147">从 Active Directory 域服务中提取用户的电话号码并将其写入到 RTC 数据库，它们是供用户服务和通讯簿服务器中的表。</span><span class="sxs-lookup"><span data-stu-id="09195-147">Extracts user phone numbers from Active Directory Domain Services and writes them to tables in the RTC database, where they are available to User Services and Address Book Server.</span></span> <span data-ttu-id="09195-148">用户复制程序将所有前端服务器上的一个核心组件。</span><span class="sxs-lookup"><span data-stu-id="09195-148">User Replicator is a core component on all Front End Servers.</span></span>
    
- <span data-ttu-id="09195-149">**通讯簿服务器。**</span><span class="sxs-lookup"><span data-stu-id="09195-149">**Address Book Server.**</span></span> <span data-ttu-id="09195-150">提供全局地址列表信息从 Active Directory 域服务到 Skype 业务服务器的客户端。</span><span class="sxs-lookup"><span data-stu-id="09195-150">Provides global address list information from Active Directory Domain Services to Skype for Business Server clients.</span></span> <span data-ttu-id="09195-151">它还从 RTC 数据库中检索用户和联系人信息、 将信息写入到通讯簿文件中，并将存储在它们的业务客户端下载通过 Skype 的共享文件夹中的文件。</span><span class="sxs-lookup"><span data-stu-id="09195-151">It also retrieves user and contact information from the RTC database, writes the information to the Address Book files, and then stores the files on a shared folder where they are downloaded by Skype for Business clients.</span></span> <span data-ttu-id="09195-152">通讯簿服务器写入 RTCAb 数据库，地址簿 Web 查询服务用于响应来自移动业务的 Skype 用户搜索查询的信息。</span><span class="sxs-lookup"><span data-stu-id="09195-152">The Address Book Server writes the information to the RTCAb database, which is used by the Address Book Web Query service to respond to user search queries from Skype for Business mobile.</span></span> <span data-ttu-id="09195-153">它还可以标准化写入 RTC 数据库，目的是提供在业务的 Skype 用户联系人的企业用户电话号码。</span><span class="sxs-lookup"><span data-stu-id="09195-153">It optionally normalizes enterprise user phone numbers that are written to the RTC database for the purpose of provisioning user contacts in Skype for Business.</span></span> <span data-ttu-id="09195-154">默认情况下，在所有前端服务器上安装通讯簿服务。</span><span class="sxs-lookup"><span data-stu-id="09195-154">The Address Book service is installed by default on all Front End Servers.</span></span> <span data-ttu-id="09195-155">默认情况下，Web 服务在每个前端服务器上安装了地址簿 Web 查询服务。</span><span class="sxs-lookup"><span data-stu-id="09195-155">The Address Book Web Query service is installed by default with the Web services on each Front End Servers.</span></span>
    

