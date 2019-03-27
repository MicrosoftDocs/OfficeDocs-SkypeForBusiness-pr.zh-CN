---
title: 什么被弃用从 Skype 业务服务器 2019
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要： 这些功能已从 Skype 的业务服务器 2019年。
ms.openlocfilehash: bd7519e66632c005d81ff9fc110684f6c4854c41
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876653"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="e02dd-103">什么被弃用从 Skype 业务服务器 2019</span><span class="sxs-lookup"><span data-stu-id="e02dd-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="e02dd-104">了解如何为业务服务器 2019 Skype 中弃用的功能。</span><span class="sxs-lookup"><span data-stu-id="e02dd-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="e02dd-105">有关业务服务器 2019 Skype 中的新功能的信息，请参阅[What's 中的业务服务器 2019 Skype](whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="e02dd-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="e02dd-106">某些消除 emphasised 的功能中包含 Skype 的业务服务器 2019年与早期的产品版本的兼容性。</span><span class="sxs-lookup"><span data-stu-id="e02dd-106">Some de-emphasised features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="e02dd-107">为业务服务器 2019 Skype 中弃用的功能</span><span class="sxs-lookup"><span data-stu-id="e02dd-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="e02dd-108">XMPP 网关的 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="e02dd-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="e02dd-109">业务服务器 2015年和其前置任务的 Skype 允许您配置边缘服务器和前端服务器或前端池上的 XMPP 网关的可扩展消息传递和状态协议 (XMPP) 的代理。</span><span class="sxs-lookup"><span data-stu-id="e02dd-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="e02dd-110">此功能不再可用的业务服务器 2019 Skype 中。</span><span class="sxs-lookup"><span data-stu-id="e02dd-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="e02dd-111">持久聊天的 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="e02dd-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="e02dd-112">持久聊天服务器是一个可选角色，可让您的组织中的多个用户参与随着时间的推移保留的聊天室对话。</span><span class="sxs-lookup"><span data-stu-id="e02dd-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="e02dd-113">持久聊天不能与 Skype 部署业务服务器 2019年。</span><span class="sxs-lookup"><span data-stu-id="e02dd-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="e02dd-114">从拓扑生成器，以及从代码删除此服务器角色。</span><span class="sxs-lookup"><span data-stu-id="e02dd-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="e02dd-115">中团队提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="e02dd-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="e02dd-116">有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="e02dd-116">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="e02dd-117">SQL 镜像 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="e02dd-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="e02dd-118">SQL 镜像无法部署与 Skype 的业务服务器 2019年。</span><span class="sxs-lookup"><span data-stu-id="e02dd-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="e02dd-119">仍然支持用于提供高可用性和灾难恢复的其他选项，您应选择从它们。</span><span class="sxs-lookup"><span data-stu-id="e02dd-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="e02dd-120">请参阅[规划高可用性和灾难恢复 Skype 业务服务器中的](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)检查的选项。</span><span class="sxs-lookup"><span data-stu-id="e02dd-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="e02dd-121">就地升级</span><span class="sxs-lookup"><span data-stu-id="e02dd-121">In-place upgrades</span></span> 

<span data-ttu-id="e02dd-122">就地升级中的业务服务器 2015 Skype 可用，但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="e02dd-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e02dd-123">升级和 coexistance 都支持并排，详细信息，请参阅[迁移到业务服务器 2019年的 Skype](migration/migration-to-skype-for-business-server-2019.md) 。</span><span class="sxs-lookup"><span data-stu-id="e02dd-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="e02dd-124">Mobility Service (Mcx)</span><span class="sxs-lookup"><span data-stu-id="e02dd-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="e02dd-125">移动服务支持旧的移动客户端使用不再可用的业务服务器 2019 Skype 中。</span><span class="sxs-lookup"><span data-stu-id="e02dd-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="e02dd-126">这先前已的业务服务器 2015年宣布 Skype 中。</span><span class="sxs-lookup"><span data-stu-id="e02dd-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="e02dd-127">业务移动客户端的所有当前 Skype 已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、 状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="e02dd-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="e02dd-128">与使用 Mcx 的旧客户端的用户需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="e02dd-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="e02dd-129">有关详细信息，请参阅[规划 Mobility for Business Server 的 Skype](../SfbServer/plan-your-deployment/mobility.md)和[Skype for Business 的移动客户端功能比较](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)。</span><span class="sxs-lookup"><span data-stu-id="e02dd-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="e02dd-130">工具</span><span class="sxs-lookup"><span data-stu-id="e02dd-130">Tools</span></span>

<span data-ttu-id="e02dd-131">不将可用于在初始版本的 Skype 的业务服务器 2019年以下工具：</span><span class="sxs-lookup"><span data-stu-id="e02dd-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="e02dd-132">Skype for Business Server 容量计划计算器</span><span class="sxs-lookup"><span data-stu-id="e02dd-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="e02dd-133">Skype 业务 server 调试工具</span><span class="sxs-lookup"><span data-stu-id="e02dd-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="e02dd-134">Skype 的业务 Server 资源工具包工具 （一些工具将被删除）</span><span class="sxs-lookup"><span data-stu-id="e02dd-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="e02dd-135">呼叫寄存时间记录器</span><span class="sxs-lookup"><span data-stu-id="e02dd-135">Call Parkometer</span></span>
    - <span data-ttu-id="e02dd-136">查找用户控制台</span><span class="sxs-lookup"><span data-stu-id="e02dd-136">Lookup user console</span></span>
    - <span data-ttu-id="e02dd-137">未分配的号码通知迁移</span><span class="sxs-lookup"><span data-stu-id="e02dd-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="e02dd-138">以下工具不支持与 Skype 业务服务器 2019年:</span><span class="sxs-lookup"><span data-stu-id="e02dd-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="e02dd-139">呼叫质量方法 （但不是呼叫质量仪表板）</span><span class="sxs-lookup"><span data-stu-id="e02dd-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="e02dd-140">Microsoft 呼叫质量方法记分卡、 v1.5</span><span class="sxs-lookup"><span data-stu-id="e02dd-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="e02dd-141">Skype for Business Server 2015 规划工具</span><span class="sxs-lookup"><span data-stu-id="e02dd-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="e02dd-142">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="e02dd-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="e02dd-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e02dd-143">See also</span></span>

[<span data-ttu-id="e02dd-144">What's new in Business Server 2019 的 Skype</span><span class="sxs-lookup"><span data-stu-id="e02dd-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="e02dd-145">管理 XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="e02dd-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
