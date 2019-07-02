---
title: Skype for Business Server 2019 中的弃用内容
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: '摘要: 已从 Skype for Business Server 2019 中删除这些功能。'
ms.openlocfilehash: 9fd6ddc28a3b75b8d4c411aa7909516d4b5c0ab8
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418359"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="0adbc-103">Skype for Business Server 2019 中的弃用内容</span><span class="sxs-lookup"><span data-stu-id="0adbc-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="0adbc-104">了解 Skype for Business Server 2019 中已弃用的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="0adbc-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="0adbc-105">有关 Skype for Business Server 2019 中的新增功能的信息, 请参阅[skype for Business server 2019 中的内容](whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="0adbc-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="0adbc-106">Skype for Business Server 2019 中提供了一些突出的功能, 可与以前的产品版本兼容。</span><span class="sxs-lookup"><span data-stu-id="0adbc-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="0adbc-107">Skype for Business Server 2019 中已弃用的功能</span><span class="sxs-lookup"><span data-stu-id="0adbc-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="0adbc-108">Skype for business Server 的 XMPP 网关</span><span class="sxs-lookup"><span data-stu-id="0adbc-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="0adbc-109">Skype for Business Server 2015 及其前置任务允许你在 Edge 服务器上配置可扩展消息和状态协议 (XMPP) 代理和前端服务器或前端池上的 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="0adbc-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="0adbc-110">Skype for Business Server 2019 不再提供此功能。</span><span class="sxs-lookup"><span data-stu-id="0adbc-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="0adbc-111">Skype for business 服务器的持久聊天</span><span class="sxs-lookup"><span data-stu-id="0adbc-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="0adbc-112">持久聊天服务器是一种可选角色, 允许组织中的多个用户参与不断保持的聊天室对话。</span><span class="sxs-lookup"><span data-stu-id="0adbc-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="0adbc-113">Skype for Business Server 2019 不能部署持久聊天。</span><span class="sxs-lookup"><span data-stu-id="0adbc-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="0adbc-114">此服务器角色将从拓扑生成器和代码中删除。</span><span class="sxs-lookup"><span data-stu-id="0adbc-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="0adbc-115">团队中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="0adbc-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="0adbc-116">有关详细信息, 请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。</span><span class="sxs-lookup"><span data-stu-id="0adbc-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="0adbc-117">Skype for business Server 的 SQL 镜像</span><span class="sxs-lookup"><span data-stu-id="0adbc-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="0adbc-118">无法通过 Skype for Business Server 2019 部署 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="0adbc-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="0adbc-119">提供高可用性和灾难恢复的其他选项仍受支持, 你应从这些选项中进行选择。</span><span class="sxs-lookup"><span data-stu-id="0adbc-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="0adbc-120">请参阅[在 Skype For Business 服务器中规划高可用性和灾难恢复](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)以查看选项。</span><span class="sxs-lookup"><span data-stu-id="0adbc-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="0adbc-121">就地升级</span><span class="sxs-lookup"><span data-stu-id="0adbc-121">In-place upgrades</span></span> 

<span data-ttu-id="0adbc-122">Skype for business Server 2015 中提供了就地升级, 但 Skype for business Server 2019 不再支持就地升级。</span><span class="sxs-lookup"><span data-stu-id="0adbc-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0adbc-123">支持并行升级和 coexistance, 有关详细信息, 请参阅[迁移到 Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) 。</span><span class="sxs-lookup"><span data-stu-id="0adbc-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="0adbc-124">移动服务 (Mcx)</span><span class="sxs-lookup"><span data-stu-id="0adbc-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="0adbc-125">旧版移动客户端使用的移动服务支持不再在 Skype for Business Server 2019 中可用。</span><span class="sxs-lookup"><span data-stu-id="0adbc-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="0adbc-126">这是以前在 Skype for Business Server 2015 中宣布的。</span><span class="sxs-lookup"><span data-stu-id="0adbc-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="0adbc-127">所有当前 Skype for business 移动客户端都已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="0adbc-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="0adbc-128">具有使用 Mcx 的旧客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="0adbc-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="0adbc-129">有关更多详细信息, 请参阅 Skype for business 适用于 skype for business Server 和[移动客户端功能比较](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)的[计划](../SfbServer/plan-your-deployment/mobility.md)。</span><span class="sxs-lookup"><span data-stu-id="0adbc-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="0adbc-130">工具</span><span class="sxs-lookup"><span data-stu-id="0adbc-130">Tools</span></span>

<span data-ttu-id="0adbc-131">Skype for business Server 2019 的初始版本中将不提供以下工具:</span><span class="sxs-lookup"><span data-stu-id="0adbc-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="0adbc-132">Skype for Business Server 容量计划计算器</span><span class="sxs-lookup"><span data-stu-id="0adbc-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="0adbc-133">Skype for Business 服务器调试工具</span><span class="sxs-lookup"><span data-stu-id="0adbc-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="0adbc-134">Skype for Business 服务器资源工具包工具 (某些工具将被删除)</span><span class="sxs-lookup"><span data-stu-id="0adbc-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="0adbc-135">呼叫寄存时间记录器</span><span class="sxs-lookup"><span data-stu-id="0adbc-135">Call Parkometer</span></span>
    - <span data-ttu-id="0adbc-136">查找用户控制台</span><span class="sxs-lookup"><span data-stu-id="0adbc-136">Lookup user console</span></span>
    - <span data-ttu-id="0adbc-137">未分配号码公告迁移</span><span class="sxs-lookup"><span data-stu-id="0adbc-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="0adbc-138">Skype for Business Server 2019 不支持以下工具:</span><span class="sxs-lookup"><span data-stu-id="0adbc-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="0adbc-139">通话质量方法 (但不是通话质量仪表板)</span><span class="sxs-lookup"><span data-stu-id="0adbc-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="0adbc-140">Microsoft 通话质量方法记分卡, v 1。5</span><span class="sxs-lookup"><span data-stu-id="0adbc-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="0adbc-141">Skype for Business Server 2015 规划工具</span><span class="sxs-lookup"><span data-stu-id="0adbc-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="0adbc-142">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="0adbc-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="0adbc-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0adbc-143">See also</span></span>

[<span data-ttu-id="0adbc-144">Skype for Business Server 2019 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="0adbc-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="0adbc-145">管理 XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="0adbc-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
