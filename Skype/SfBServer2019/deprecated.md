---
title: Skype for Business Server 2019 中弃用的内容
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：这些功能已从 Skype for Business Server 2019 中删除。
ms.openlocfilehash: 40a202f802ec8ac1a0f880f92ad9cf59ce68a627
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42125215"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="93e08-103">Skype for Business Server 2019 中弃用的内容</span><span class="sxs-lookup"><span data-stu-id="93e08-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="93e08-104">了解 Skype for Business Server 2019 中弃用的特性和功能。</span><span class="sxs-lookup"><span data-stu-id="93e08-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="93e08-105">有关 Skype for business Server 2019 中的新功能的信息，请参阅[skype For Business server 2019 中的内容](whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="93e08-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="93e08-106">Skype for Business Server 2019 中包含一些突出的功能，以与以前的产品版本兼容。</span><span class="sxs-lookup"><span data-stu-id="93e08-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="93e08-107">Skype for Business Server 2019 中弃用的功能</span><span class="sxs-lookup"><span data-stu-id="93e08-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="93e08-108">Skype for business Server 的 XMPP 网关</span><span class="sxs-lookup"><span data-stu-id="93e08-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="93e08-109">Skype for Business Server 2015 及其前置任务允许您在边缘服务器上配置可扩展消息和状态协议（XMPP）代理，并在前端服务器或前端池上配置 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="93e08-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="93e08-110">Skype for Business Server 2019 不再提供此功能。</span><span class="sxs-lookup"><span data-stu-id="93e08-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="93e08-111">Skype for business Server 的持久聊天</span><span class="sxs-lookup"><span data-stu-id="93e08-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="93e08-112">持久聊天服务器是一个可选角色，允许组织中的多个用户参与随时间推移而保留的聊天室对话。</span><span class="sxs-lookup"><span data-stu-id="93e08-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="93e08-113">不能使用 Skype for Business Server 2019 部署持久聊天。</span><span class="sxs-lookup"><span data-stu-id="93e08-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="93e08-114">此服务器角色将从拓扑生成器和代码中删除。</span><span class="sxs-lookup"><span data-stu-id="93e08-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="93e08-115">团队中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="93e08-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="93e08-116">有关详细信息，请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。</span><span class="sxs-lookup"><span data-stu-id="93e08-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="93e08-117">Skype for business Server 的 SQL 镜像</span><span class="sxs-lookup"><span data-stu-id="93e08-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="93e08-118">无法使用 Skype for Business Server 2019 部署 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="93e08-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="93e08-119">仍支持其他提供高可用性和灾难恢复的选项，您应从这些选项中进行选择。</span><span class="sxs-lookup"><span data-stu-id="93e08-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="93e08-120">请参阅[在 Skype For Business Server 中规划高可用性和灾难恢复](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)以查看选项。</span><span class="sxs-lookup"><span data-stu-id="93e08-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="93e08-121">就地升级</span><span class="sxs-lookup"><span data-stu-id="93e08-121">In-place upgrades</span></span> 

<span data-ttu-id="93e08-122">Skype for Business Server 2015 中提供了就地升级，但 Skype for Business Server 2019 不再支持就地升级。</span><span class="sxs-lookup"><span data-stu-id="93e08-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="93e08-123">并行升级和共存受支持，有关详细信息，请参阅[迁移到 Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) 。</span><span class="sxs-lookup"><span data-stu-id="93e08-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="93e08-124">移动服务（Mcx）</span><span class="sxs-lookup"><span data-stu-id="93e08-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="93e08-125">旧版移动客户端使用的移动服务支持不再在 Skype for Business Server 2019 中可用。</span><span class="sxs-lookup"><span data-stu-id="93e08-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="93e08-126">这是以前在 Skype for Business Server 2015 中宣布的。</span><span class="sxs-lookup"><span data-stu-id="93e08-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="93e08-127">所有当前 Skype for Business 移动客户端都已使用统一通信 Web API （UCWA）来支持即时消息（IM）、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="93e08-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="93e08-128">具有使用 Mcx 的旧版客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="93e08-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="93e08-129">有关更多详细信息，请参阅[Plan For skype for Business Server 的移动性](../SfbServer/plan-your-deployment/mobility.md)和[skype For business 的移动客户端功能比较](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)。</span><span class="sxs-lookup"><span data-stu-id="93e08-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="93e08-130">工具</span><span class="sxs-lookup"><span data-stu-id="93e08-130">Tools</span></span>

<span data-ttu-id="93e08-131">以下工具在最初发布的 Skype for Business Server 2019 中将不可用：</span><span class="sxs-lookup"><span data-stu-id="93e08-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="93e08-132">Skype for Business Server 容量规划计算器</span><span class="sxs-lookup"><span data-stu-id="93e08-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="93e08-133">Skype for Business Server 调试工具</span><span class="sxs-lookup"><span data-stu-id="93e08-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="93e08-134">Skype for Business Server 资源工具包工具（某些工具将被删除）</span><span class="sxs-lookup"><span data-stu-id="93e08-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="93e08-135">调用寄存时间记录器</span><span class="sxs-lookup"><span data-stu-id="93e08-135">Call Parkometer</span></span>
    - <span data-ttu-id="93e08-136">查找用户控制台</span><span class="sxs-lookup"><span data-stu-id="93e08-136">Lookup user console</span></span>
    - <span data-ttu-id="93e08-137">未分配号码通知迁移</span><span class="sxs-lookup"><span data-stu-id="93e08-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="93e08-138">Skype for Business Server 2019 不支持以下工具：</span><span class="sxs-lookup"><span data-stu-id="93e08-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="93e08-139">呼叫质量方法（但不是呼叫质量仪表板）</span><span class="sxs-lookup"><span data-stu-id="93e08-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="93e08-140">Microsoft 呼叫质量方法记分卡，1。5</span><span class="sxs-lookup"><span data-stu-id="93e08-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="93e08-141">Skype for Business Server 2015 规划工具</span><span class="sxs-lookup"><span data-stu-id="93e08-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="93e08-142">Skype for Business Server 2015 压力和性能工具</span><span class="sxs-lookup"><span data-stu-id="93e08-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="93e08-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93e08-143">See also</span></span>

[<span data-ttu-id="93e08-144">Skype for Business Server 2019 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="93e08-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="93e08-145">迁移 XMPP 联合</span><span class="sxs-lookup"><span data-stu-id="93e08-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
