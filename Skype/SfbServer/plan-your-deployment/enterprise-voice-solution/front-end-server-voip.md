---
title: Skype for Business Server 的前端服务器 VoIP 组件
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 了解 Skype for Business Server 企业语音前端服务器上部署的组件，包括翻译服务和各种路由组件。
ms.openlocfilehash: fcf1e30c0f6bbe0a292de54e4cc4b264774f9c7f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825652"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a><span data-ttu-id="09094-103">Skype for Business Server 的前端服务器 VoIP 组件</span><span class="sxs-lookup"><span data-stu-id="09094-103">Front End Server VoIP components for Skype for Business Server</span></span>

<span data-ttu-id="09094-104">了解 Skype for Business Server 企业语音前端服务器上部署的组件，包括翻译服务和各种路由组件。</span><span class="sxs-lookup"><span data-stu-id="09094-104">Learn about the Enterprise Voice components that are located on Front End Servers in Skype for Business Server, including translation service and various routing components.</span></span>

<span data-ttu-id="09094-105">位于前端服务器的 VoIP 组件如下所示：</span><span class="sxs-lookup"><span data-stu-id="09094-105">The VoIP components located on Front End Servers are as follows:</span></span>

- <span data-ttu-id="09094-106">转换服务</span><span class="sxs-lookup"><span data-stu-id="09094-106">Translation Service</span></span>

- <span data-ttu-id="09094-107">入站路由组件</span><span class="sxs-lookup"><span data-stu-id="09094-107">Inbound Routing component</span></span>

- <span data-ttu-id="09094-108">出站路由组件</span><span class="sxs-lookup"><span data-stu-id="09094-108">Outbound Routing component</span></span>

- <span data-ttu-id="09094-109">Exchange UM 路由组件</span><span class="sxs-lookup"><span data-stu-id="09094-109">Exchange UM Routing component</span></span>

- <span data-ttu-id="09094-110">群集间路由组件</span><span class="sxs-lookup"><span data-stu-id="09094-110">Intercluster Routing component</span></span>

- [<span data-ttu-id="09094-111">Skype for Business Server 中的中介服务器组件</span><span class="sxs-lookup"><span data-stu-id="09094-111">Mediation Server component in Skype for Business Server</span></span>](mediation-server.md)

## <a name="translation-service"></a><span data-ttu-id="09094-112">转换服务</span><span class="sxs-lookup"><span data-stu-id="09094-112">Translation Service</span></span>

<span data-ttu-id="09094-p101">转换服务是一个服务器组件，负责根据管理员定义的规范化规则将所拨打的号码转换为 E.164 格式或其他格式。如果组织使用专用编号系统或使用不支持 E.164 的网关或 PBX，则转换服务可以将号码转换为 E.164 以外的格式。</span><span class="sxs-lookup"><span data-stu-id="09094-p101">The Translation Service is the server component that is responsible for translating a dialed number into the E.164 format or another format, according to the normalization rules that are defined by the administrator. The Translation Service can translate to formats other than E.164 if your organization uses a private numbering system or uses a gateway or PBX that does not support E.164.</span></span>

## <a name="inbound-routing-component"></a><span data-ttu-id="09094-115">入站路由组件</span><span class="sxs-lookup"><span data-stu-id="09094-115">Inbound Routing Component</span></span>

<span data-ttu-id="09094-116">入站路由组件主要根据用户在客户端上指定的首选项处理企业语音呼叫。</span><span class="sxs-lookup"><span data-stu-id="09094-116">The Inbound Routing component handles incoming calls largely according to preferences that are specified by users on their Enterprise Voice clients.</span></span> <span data-ttu-id="09094-117">它还可以实现代理人响铃和同时响铃（如果用户已配置）。</span><span class="sxs-lookup"><span data-stu-id="09094-117">It also facilitates delegate ringing and simultaneous ringing, if configured by the user.</span></span> <span data-ttu-id="09094-118">例如，用户指定转接未应答的呼叫，还是仅做记录以通知用户。</span><span class="sxs-lookup"><span data-stu-id="09094-118">For example, users specify whether unanswered calls are forwarded or simply logged for notification.</span></span> <span data-ttu-id="09094-119">如果启用了呼叫转发，则用户可以指定是应该将未应答的呼叫转发到另一个号码，还是应转发到配置为提供呼叫应答的 Exchange UM 服务器。</span><span class="sxs-lookup"><span data-stu-id="09094-119">If call forwarding is enabled, users can specify whether unanswered calls should be forwarded to another number or to a Exchange UM server that has been configured to provide call answering.</span></span> <span data-ttu-id="09094-120">默认情况下，入站路由组件安装在所有 Standard Edition Server 和前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="09094-120">The Inbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

## <a name="outbound-routing-component"></a><span data-ttu-id="09094-121">出站路由组件</span><span class="sxs-lookup"><span data-stu-id="09094-121">Outbound Routing Component</span></span>

<span data-ttu-id="09094-122">出站路由组件将呼叫路由到 PBX 或 PSTN 目标。</span><span class="sxs-lookup"><span data-stu-id="09094-122">The Outbound Routing component routes calls to PBX or PSTN destinations.</span></span> <span data-ttu-id="09094-123">它将用户语音策略定义的呼叫授权规则应用于呼叫者，并确定路由每个呼叫的最佳 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="09094-123">It applies call authorization rules, as defined by the user's voice policy, to callers and determines the optimal PSTN gateway for routing each call.</span></span> <span data-ttu-id="09094-124">默认情况下，出站路由组件安装在所有 Standard Edition Server 和前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="09094-124">The Outbound Routing component is installed by default on all Standard Edition server and Front End Servers.</span></span>

<span data-ttu-id="09094-125">出站路由组件使用的路由逻辑大体上是由网络或电话管理员根据其组织的要求来配置的。</span><span class="sxs-lookup"><span data-stu-id="09094-125">The routing logic that is used by the Outbound Routing component is in large measure configured by network or telephony administrators according to the requirements of their organizations.</span></span>

## <a name="exchange-um-routing-component"></a><span data-ttu-id="09094-126">Exchange UM 路由组件</span><span class="sxs-lookup"><span data-stu-id="09094-126">Exchange UM Routing Component</span></span>

<span data-ttu-id="09094-127">Exchange UM 路由组件处理 Skype for Business Server 与运行 Exchange 统一消息 (UM) 的服务器之间的路由，以将 Skype for Business Server 与统一消息功能集成。</span><span class="sxs-lookup"><span data-stu-id="09094-127">The Exchange UM routing component handles routing between Skype for Business Server and servers running Exchange Unified Messaging (UM), to integrate Skype for Business Server with Unified Messaging features.</span></span>

<span data-ttu-id="09094-128">Exchange UM 路由组件还处理 Exchange UM 服务器不可用时通过 PSTN 重新路由语音邮件。</span><span class="sxs-lookup"><span data-stu-id="09094-128">The Exchange UM routing component also handles rerouting of voice mail over the PSTN if Exchange UM servers are unavailable.</span></span> <span data-ttu-id="09094-129">如果分支站点企业语音没有到中央站点的可恢复 WAN 链接的邮箱用户，则分支站点上部署的 Survivable Branch Appliance 在 WAN 中断期间为分支用户提供语音邮件生存能力。</span><span class="sxs-lookup"><span data-stu-id="09094-129">If you have Enterprise Voice users at branch sites that do not have a resilient WAN link to a central site, the Survivable Branch Appliance that you deploy at the branch site provides voice mail survivability for branch users during a WAN outage.</span></span> <span data-ttu-id="09094-130">WAN 链路不可用时，Survivable Branch Appliance 将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="09094-130">When the WAN link is unavailable, the Survivable Branch Appliance does the following:</span></span>

- <span data-ttu-id="09094-131">通过 PSTN 将未应答的呼叫重新路由到中央站点上的 Exchange 统一消息服务器</span><span class="sxs-lookup"><span data-stu-id="09094-131">reroutes unanswered calls over the PSTN to the Exchange Unified Messaging server in the central site</span></span>

- <span data-ttu-id="09094-132">为用户提供通过 PSTN 取回语音邮件消息的功能</span><span class="sxs-lookup"><span data-stu-id="09094-132">provides the ability for a user to retrieve voice mail messages over the PSTN</span></span>

- <span data-ttu-id="09094-133">使错过的呼叫通知排队，然后在 WAN 链路还原时将其上载到 Exchange UM 服务器。</span><span class="sxs-lookup"><span data-stu-id="09094-133">queues missed call notifications, and then uploads them to the Exchange UM server when the WAN link is restored.</span></span>

<span data-ttu-id="09094-134">若要启用语音邮件重新路由，我们建议您的 Exchange 管理员将 Exchange UM 自动助理 (AA) 接受邮件。</span><span class="sxs-lookup"><span data-stu-id="09094-134">To enable voice mail rerouting, we recommend that your Exchange administrator configure Exchange UM Auto Attendant (AA) to accept messages only.</span></span>

<span data-ttu-id="09094-135">有关这些功能的详细信息，请分别参阅[On-Premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx)和[Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)。</span><span class="sxs-lookup"><span data-stu-id="09094-135">For details about these features, see [On-Premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx) and [Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx), respectively.</span></span>

## <a name="intercluster-routing-component"></a><span data-ttu-id="09094-136">群集间路由组件</span><span class="sxs-lookup"><span data-stu-id="09094-136">Intercluster Routing Component</span></span>

<span data-ttu-id="09094-137">群集间路由组件负责将呼叫路由到被叫方的主注册器池。</span><span class="sxs-lookup"><span data-stu-id="09094-137">The Intercluster routing component is responsible for routing calls to the callee's primary Registrar pool.</span></span> <span data-ttu-id="09094-138">如果不可用，组件将呼叫路由到被叫方备份注册器池。</span><span class="sxs-lookup"><span data-stu-id="09094-138">If that is unavailable, the component routes the call to the callee's backup Registrar pool.</span></span> <span data-ttu-id="09094-139">如果无法通过 IP 网络访问被叫方的主注册器池和备份注册器池，则群集间路由组件会通过 PSTN 将呼叫重新路由到用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="09094-139">If the callee's primary and backup Registrar pools are unreachable over the IP network, the Intercluster routing component reroutes the call over the PSTN to the user's telephone number.</span></span>

## <a name="other-front-end-server-components-required-for-voip"></a><span data-ttu-id="09094-140">VoIP 所需的其他前端服务器组件</span><span class="sxs-lookup"><span data-stu-id="09094-140">Other Front End Server Components Required for VoIP</span></span>

<span data-ttu-id="09094-141">驻留在前端服务器或控制器上、为 VoIP 提供必要支持但自身不是 VoIP 组件的其他组件包括：</span><span class="sxs-lookup"><span data-stu-id="09094-141">Other components residing on the Front End Server or Director that provide essential support for VoIP, but are not themselves VoIP components, include the following:</span></span>

- <span data-ttu-id="09094-142">**用户服务。**</span><span class="sxs-lookup"><span data-stu-id="09094-142">**User Services.**</span></span> <span data-ttu-id="09094-143">对每个传入呼叫的目标电话号码执行反向号码查找，并将该号码与目标用户的 SIP URI 进行匹配。</span><span class="sxs-lookup"><span data-stu-id="09094-143">Perform reverse number lookup on the destination phone number of each incoming call and match that number to the SIP URI of the destination user.</span></span> <span data-ttu-id="09094-144">入站路由组件使用此信息将呼叫分发给该用户注册的 SIP 终结点。</span><span class="sxs-lookup"><span data-stu-id="09094-144">Using this information, the Inbound Routing component distributes the call to that user's registered SIP endpoints.</span></span> <span data-ttu-id="09094-145">用户服务是所有前端服务器和控制器的核心组件。</span><span class="sxs-lookup"><span data-stu-id="09094-145">User Services is a core component on all Front End Servers and Directors.</span></span>

- <span data-ttu-id="09094-146">**用户复制程序。**</span><span class="sxs-lookup"><span data-stu-id="09094-146">**User Replicator.**</span></span> <span data-ttu-id="09094-147">从 Active Directory 域服务中提取用户电话号码，并写入 RTC 数据库中的表，这些表可供用户服务和通讯簿服务器使用。</span><span class="sxs-lookup"><span data-stu-id="09094-147">Extracts user phone numbers from Active Directory Domain Services and writes them to tables in the RTC database, where they are available to User Services and Address Book Server.</span></span> <span data-ttu-id="09094-148">用户复制程序是所有前端服务器上的核心组件。</span><span class="sxs-lookup"><span data-stu-id="09094-148">User Replicator is a core component on all Front End Servers.</span></span>

- <span data-ttu-id="09094-149">**通讯簿服务器。**</span><span class="sxs-lookup"><span data-stu-id="09094-149">**Address Book Server.**</span></span> <span data-ttu-id="09094-150">提供从 Active Directory 域服务到 Skype for Business Server 客户端的全局地址列表信息。</span><span class="sxs-lookup"><span data-stu-id="09094-150">Provides global address list information from Active Directory Domain Services to Skype for Business Server clients.</span></span> <span data-ttu-id="09094-151">它还从 RTC 数据库检索用户和联系人信息，将信息写入通讯簿文件，然后将文件存储在 Skype for Business 客户端下载文件的共享文件夹中。</span><span class="sxs-lookup"><span data-stu-id="09094-151">It also retrieves user and contact information from the RTC database, writes the information to the Address Book files, and then stores the files on a shared folder where they are downloaded by Skype for Business clients.</span></span> <span data-ttu-id="09094-152">通讯簿服务器将信息写入 RTCAb 数据库，通讯簿 Web 查询服务使用该数据库响应来自 Skype for Business 移动版的用户搜索查询。</span><span class="sxs-lookup"><span data-stu-id="09094-152">The Address Book Server writes the information to the RTCAb database, which is used by the Address Book Web Query service to respond to user search queries from Skype for Business mobile.</span></span> <span data-ttu-id="09094-153">它选择性地规范化写入 RTC 数据库的企业用户电话号码，以便预配 Skype for Business 中的用户联系人。</span><span class="sxs-lookup"><span data-stu-id="09094-153">It optionally normalizes enterprise user phone numbers that are written to the RTC database for the purpose of provisioning user contacts in Skype for Business.</span></span> <span data-ttu-id="09094-154">默认情况下，通讯簿服务安装在所有前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="09094-154">The Address Book service is installed by default on all Front End Servers.</span></span> <span data-ttu-id="09094-155">默认情况下，通讯簿 Web 查询服务随每台前端服务器的 Web 服务一起安装。</span><span class="sxs-lookup"><span data-stu-id="09094-155">The Address Book Web Query service is installed by default with the Web services on each Front End Servers.</span></span>


