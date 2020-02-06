---
title: Skype for business 服务器的前端服务器 VoIP 组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: 了解 Skype for Business 服务器的前端服务器上的企业语音组件，包括翻译服务和各种路由组件。
ms.openlocfilehash: eae2f389720a6c359f442a7a163d5b4b5aef6e26
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802962"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a><span data-ttu-id="d1f7f-103">Skype for business 服务器的前端服务器 VoIP 组件</span><span class="sxs-lookup"><span data-stu-id="d1f7f-103">Front End Server VoIP components for Skype for Business Server</span></span>

<span data-ttu-id="d1f7f-104">了解 Skype for Business 服务器的前端服务器上的企业语音组件，包括翻译服务和各种路由组件。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-104">Learn about the Enterprise Voice components that are located on Front End Servers in Skype for Business Server, including translation service and various routing components.</span></span>

<span data-ttu-id="d1f7f-105">位于前端服务器上的 VoIP 组件如下所示：</span><span class="sxs-lookup"><span data-stu-id="d1f7f-105">The VoIP components located on Front End Servers are as follows:</span></span>

- <span data-ttu-id="d1f7f-106">转换服务</span><span class="sxs-lookup"><span data-stu-id="d1f7f-106">Translation Service</span></span>

- <span data-ttu-id="d1f7f-107">入站路由组件</span><span class="sxs-lookup"><span data-stu-id="d1f7f-107">Inbound Routing component</span></span>

- <span data-ttu-id="d1f7f-108">出站路由组件</span><span class="sxs-lookup"><span data-stu-id="d1f7f-108">Outbound Routing component</span></span>

- <span data-ttu-id="d1f7f-109">Exchange UM 路由组件</span><span class="sxs-lookup"><span data-stu-id="d1f7f-109">Exchange UM Routing component</span></span>

- <span data-ttu-id="d1f7f-110">群集间路由组件</span><span class="sxs-lookup"><span data-stu-id="d1f7f-110">Intercluster Routing component</span></span>

- [<span data-ttu-id="d1f7f-111">Skype for Business 服务器中的中介服务器组件</span><span class="sxs-lookup"><span data-stu-id="d1f7f-111">Mediation Server component in Skype for Business Server</span></span>](mediation-server.md)

## <a name="translation-service"></a><span data-ttu-id="d1f7f-112">转换服务</span><span class="sxs-lookup"><span data-stu-id="d1f7f-112">Translation Service</span></span>

<span data-ttu-id="d1f7f-p101">转换服务是一个服务器组件，负责根据管理员定义的规范化规则将所拨打的号码转换为 E.164 格式或其他格式。如果组织使用专用编号系统或使用不支持 E.164 的网关或 PBX，则转换服务可以将号码转换为 E.164 以外的格式。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-p101">The Translation Service is the server component that is responsible for translating a dialed number into the E.164 format or another format, according to the normalization rules that are defined by the administrator. The Translation Service can translate to formats other than E.164 if your organization uses a private numbering system or uses a gateway or PBX that does not support E.164.</span></span>

## <a name="inbound-routing-component"></a><span data-ttu-id="d1f7f-115">入站路由组件</span><span class="sxs-lookup"><span data-stu-id="d1f7f-115">Inbound Routing Component</span></span>

<span data-ttu-id="d1f7f-116">入站路由组件根据用户在其企业语音客户端指定的首选项处理传入的呼叫。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-116">The Inbound Routing component handles incoming calls largely according to preferences that are specified by users on their Enterprise Voice clients.</span></span> <span data-ttu-id="d1f7f-117">它还可以实现代理人响铃和同时响铃（如果用户已配置）。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-117">It also facilitates delegate ringing and simultaneous ringing, if configured by the user.</span></span> <span data-ttu-id="d1f7f-118">例如，用户指定转接未应答的呼叫，还是仅做记录以通知用户。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-118">For example, users specify whether unanswered calls are forwarded or simply logged for notification.</span></span> <span data-ttu-id="d1f7f-119">如果启用了呼叫转移，用户可以指定是否应将未应答的呼叫转发到另一个号码或已配置为提供呼叫应答的 Exchange UM 服务器。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-119">If call forwarding is enabled, users can specify whether unanswered calls should be forwarded to another number or to a Exchange UM server that has been configured to provide call answering.</span></span> <span data-ttu-id="d1f7f-120">入站路由组件默认情况下在所有标准版服务器和前端服务器上安装。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-120">The Inbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

## <a name="outbound-routing-component"></a><span data-ttu-id="d1f7f-121">出站路由组件</span><span class="sxs-lookup"><span data-stu-id="d1f7f-121">Outbound Routing Component</span></span>

<span data-ttu-id="d1f7f-122">出站路由组件将呼叫路由到 PBX 或 PSTN 目标。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-122">The Outbound Routing component routes calls to PBX or PSTN destinations.</span></span> <span data-ttu-id="d1f7f-123">它将呼叫授权规则（由用户的语音策略定义）应用于呼叫方，并确定用于路由每个呼叫的最佳 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-123">It applies call authorization rules, as defined by the user's voice policy, to callers and determines the optimal PSTN gateway for routing each call.</span></span> <span data-ttu-id="d1f7f-124">默认情况下，在所有标准版服务器和前端服务器上安装出站路由组件。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-124">The Outbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

<span data-ttu-id="d1f7f-125">出站路由组件使用的路由逻辑大体上是由网络或电话管理员根据其组织的要求来配置的。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-125">The routing logic that is used by the Outbound Routing component is in large measure configured by network or telephony administrators according to the requirements of their organizations.</span></span>

## <a name="exchange-um-routing-component"></a><span data-ttu-id="d1f7f-126">Exchange UM 路由组件</span><span class="sxs-lookup"><span data-stu-id="d1f7f-126">Exchange UM Routing Component</span></span>

<span data-ttu-id="d1f7f-127">Exchange UM 路由组件处理 Skype for business 服务器与运行 Exchange 统一消息（UM）的服务器之间的路由，以便将 Skype for Business 服务器与统一消息功能集成。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-127">The Exchange UM routing component handles routing between Skype for Business Server and servers running Exchange Unified Messaging (UM), to integrate Skype for Business Server with Unified Messaging features.</span></span>

<span data-ttu-id="d1f7f-128">如果 Exchange UM 服务器不可用，Exchange UM 路由组件还会通过 PSTN 处理语音邮件的重新路由。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-128">The Exchange UM routing component also handles rerouting of voice mail over the PSTN if Exchange UM servers are unavailable.</span></span> <span data-ttu-id="d1f7f-129">如果在没有指向中心网站的弹性 WAN 链接的分支站点上有企业语音用户，则在分支站点上部署的 Survivable 分支装置将在 WAN 中断期间为分支用户提供语音邮件留存。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-129">If you have Enterprise Voice users at branch sites that do not have a resilient WAN link to a central site, the Survivable Branch Appliance that you deploy at the branch site provides voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="d1f7f-130">当 WAN 链接不可用时，Survivable 分支装置将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d1f7f-130">When the WAN link is unavailable, the Survivable Branch Appliance does the following:</span></span>

- <span data-ttu-id="d1f7f-131">通过 PSTN 将未应答的呼叫重新路由到中央站点上的 Exchange 统一消息服务器</span><span class="sxs-lookup"><span data-stu-id="d1f7f-131">reroutes unanswered calls over the PSTN to the Exchange Unified Messaging server in the central site</span></span>

- <span data-ttu-id="d1f7f-132">为用户提供通过 PSTN 取回语音邮件消息的功能</span><span class="sxs-lookup"><span data-stu-id="d1f7f-132">provides the ability for a user to retrieve voice mail messages over the PSTN</span></span>

- <span data-ttu-id="d1f7f-133">使错过的呼叫通知排队，然后在 WAN 链路还原时将其上载到 Exchange UM 服务器。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-133">queues missed call notifications, and then uploads them to the Exchange UM server when the WAN link is restored.</span></span>

<span data-ttu-id="d1f7f-134">为了启用语音邮件重新路由，我们建议你的 Exchange 管理员将 Exchange UM 自动助理（AA）配置为仅接受邮件。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-134">To enable voice mail rerouting, we recommend that your Exchange administrator configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span>

<span data-ttu-id="d1f7f-135">有关这些功能的详细信息，请分别参阅 [On-Premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) 和 [Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-135">For details about these features, see [On-Premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) and [Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx), respectively.</span></span>

## <a name="intercluster-routing-component"></a><span data-ttu-id="d1f7f-136">群集间路由组件</span><span class="sxs-lookup"><span data-stu-id="d1f7f-136">Intercluster Routing Component</span></span>

<span data-ttu-id="d1f7f-137">Intercluster 路由组件负责将呼叫路由到被调用方的主注册池。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-137">The Intercluster routing component is responsible for routing calls to the callee's primary Registrar pool.</span></span> <span data-ttu-id="d1f7f-138">如果该功能不可用，则该组件将呼叫路由到被呼叫方的备份注册机构池。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-138">If that is unavailable, the component routes the call to the callee's backup Registrar pool.</span></span> <span data-ttu-id="d1f7f-139">如果被调用方的主和备份注册器池在 IP 网络上不可访问，则 Intercluster 路由组件将通过 PSTN 将呼叫重置为用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-139">If the callee's primary and backup Registrar pools are unreachable over the IP network, the Intercluster routing component reroutes the call over the PSTN to the user's telephone number.</span></span>

## <a name="other-front-end-server-components-required-for-voip"></a><span data-ttu-id="d1f7f-140">VoIP 所需的其他前端服务器组件</span><span class="sxs-lookup"><span data-stu-id="d1f7f-140">Other Front End Server Components Required for VoIP</span></span>

<span data-ttu-id="d1f7f-141">驻留在前端服务器或控制器上的其他组件，可提供对 VoIP 的重要支持，但不是自身的 VoIP 组件，包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="d1f7f-141">Other components residing on the Front End Server or Director that provide essential support for VoIP, but are not themselves VoIP components, include the following:</span></span>

- <span data-ttu-id="d1f7f-142">**用户服务。**</span><span class="sxs-lookup"><span data-stu-id="d1f7f-142">**User Services.**</span></span> <span data-ttu-id="d1f7f-143">对每个传入呼叫的目标电话号码执行反向号码查找，并将该号码与目标用户的 SIP URI 进行匹配。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-143">Perform reverse number lookup on the destination phone number of each incoming call and match that number to the SIP URI of the destination user.</span></span> <span data-ttu-id="d1f7f-144">使用此信息，入站路由组件将呼叫分发到该用户的已注册 SIP 终结点。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-144">Using this information, the Inbound Routing component distributes the call to that user's registered SIP endpoints.</span></span> <span data-ttu-id="d1f7f-145">用户服务是所有前端服务器和控制器上的核心组件。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-145">User Services is a core component on all Front End Servers and Directors.</span></span>

- <span data-ttu-id="d1f7f-146">**用户复制程序。**</span><span class="sxs-lookup"><span data-stu-id="d1f7f-146">**User Replicator.**</span></span> <span data-ttu-id="d1f7f-147">从 Active Directory 域服务中提取用户电话号码，并将其写入到 RTC 数据库中的表中，用户服务和通讯簿服务器可使用这些号码。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-147">Extracts user phone numbers from Active Directory Domain Services and writes them to tables in the RTC database, where they are available to User Services and Address Book Server.</span></span> <span data-ttu-id="d1f7f-148">用户复制程序是所有前端服务器上的核心组件。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-148">User Replicator is a core component on all Front End Servers.</span></span>

- <span data-ttu-id="d1f7f-149">**通讯簿服务器。**</span><span class="sxs-lookup"><span data-stu-id="d1f7f-149">**Address Book Server.**</span></span> <span data-ttu-id="d1f7f-150">将 Active Directory 域服务中的全局地址列表信息提供给 Skype for business 服务器客户端。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-150">Provides global address list information from Active Directory Domain Services to Skype for Business Server clients.</span></span> <span data-ttu-id="d1f7f-151">它还从 RTC 数据库中检索用户和联系人信息，将信息写入通讯簿文件，然后将文件存储在由 Skype for Business 客户端下载的共享文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-151">It also retrieves user and contact information from the RTC database, writes the information to the Address Book files, and then stores the files on a shared folder where they are downloaded by Skype for Business clients.</span></span> <span data-ttu-id="d1f7f-152">通讯簿服务器将信息写入 RTCAb 数据库，通讯簿 Web 查询服务使用该数据库响应来自 Skype for Business mobile 的用户搜索查询。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-152">The Address Book Server writes the information to the RTCAb database, which is used by the Address Book Web Query service to respond to user search queries from Skype for Business mobile.</span></span> <span data-ttu-id="d1f7f-153">它还可以对写入 RTC 数据库的企业用户电话号码进行标准化，以便在 Skype for Business 中预配用户联系人。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-153">It optionally normalizes enterprise user phone numbers that are written to the RTC database for the purpose of provisioning user contacts in Skype for Business.</span></span> <span data-ttu-id="d1f7f-154">默认情况下，通讯簿服务在所有前端服务器上安装。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-154">The Address Book service is installed by default on all Front End Servers.</span></span> <span data-ttu-id="d1f7f-155">默认情况下，通讯簿 Web 查询服务与每个前端服务器上的 Web 服务一起安装。</span><span class="sxs-lookup"><span data-stu-id="d1f7f-155">The Address Book Web Query service is installed by default with the Web services on each Front End Servers.</span></span>


