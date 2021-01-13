---
title: Skype for Business Server 2019 弃用内容
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：这些功能已从 Skype for Business Server 2019 中删除。
ms.openlocfilehash: 5c5914493d7e2f4da4fd72d6acf7ff2b979d8e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808722"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="de35b-103">Skype for Business Server 2019 弃用内容</span><span class="sxs-lookup"><span data-stu-id="de35b-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="de35b-104">了解 Skype for Business Server 2019 中弃用的特性和功能。</span><span class="sxs-lookup"><span data-stu-id="de35b-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="de35b-105">有关 Skype for Business Server 2019 中的新功能的信息，请参阅 [Skype for Business Server 2019](whats-new.md)中的功能。</span><span class="sxs-lookup"><span data-stu-id="de35b-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="de35b-106">为了与以前的产品版本兼容，Skype for Business Server 2019 中包含一些不着重强调的功能。</span><span class="sxs-lookup"><span data-stu-id="de35b-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="de35b-107">Skype for Business Server 2019 中弃用的功能</span><span class="sxs-lookup"><span data-stu-id="de35b-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="de35b-108">适用于 Skype for Business Server 的 XMPP 网关</span><span class="sxs-lookup"><span data-stu-id="de35b-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="de35b-109">Skype for Business Server 2015 及其前置任务允许在边缘服务器上配置可扩展消息传递和状态协议 (XMPP) 代理，在前端服务器或前端池上配置 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="de35b-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="de35b-110">Skype for Business Server 2019 中不再提供此功能。</span><span class="sxs-lookup"><span data-stu-id="de35b-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="de35b-111">Skype for Business Server 持久聊天</span><span class="sxs-lookup"><span data-stu-id="de35b-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="de35b-112">持久聊天服务器是一个可选角色，可让贵组织中多个用户参与持续一段时间的聊天室对话。</span><span class="sxs-lookup"><span data-stu-id="de35b-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="de35b-113">无法通过 Skype for Business Server 2019 部署持久聊天。</span><span class="sxs-lookup"><span data-stu-id="de35b-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="de35b-114">此服务器角色从拓扑生成器和代码中删除。</span><span class="sxs-lookup"><span data-stu-id="de35b-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="de35b-115">Teams 中也提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="de35b-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="de35b-116">有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。</span><span class="sxs-lookup"><span data-stu-id="de35b-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="de35b-117">SQL Skype for Business Server 的镜像</span><span class="sxs-lookup"><span data-stu-id="de35b-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="de35b-118">SQL镜像无法与 Skype for Business Server 2019 一起部署。</span><span class="sxs-lookup"><span data-stu-id="de35b-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="de35b-119">提供高可用性和灾难恢复的其他选项仍受支持，您应从中进行选择。</span><span class="sxs-lookup"><span data-stu-id="de35b-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="de35b-120">请参阅 [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span><span class="sxs-lookup"><span data-stu-id="de35b-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="de35b-121">就地升级</span><span class="sxs-lookup"><span data-stu-id="de35b-121">In-place upgrades</span></span> 

<span data-ttu-id="de35b-122">就地升级在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="de35b-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="de35b-123">支持并行升级和共存，有关详细信息，请参阅迁移到[Skype for Business Server 2019。](migration/migration-to-skype-for-business-server-2019.md)</span><span class="sxs-lookup"><span data-stu-id="de35b-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="de35b-124">Mobility Service (Mcx) </span><span class="sxs-lookup"><span data-stu-id="de35b-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="de35b-125">旧版移动客户端使用的移动服务支持在 Skype for Business Server 2019 中不再可用。</span><span class="sxs-lookup"><span data-stu-id="de35b-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="de35b-126">这之前在 Skype for Business Server 2015 中公布。</span><span class="sxs-lookup"><span data-stu-id="de35b-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="de35b-127">所有当前的 Skype for Business 移动客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="de35b-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="de35b-128">使用 Mcx 的旧客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="de35b-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="de35b-129">有关详细信息，请参阅[Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and Mobile client feature comparison for Skype for [Business。](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="de35b-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="de35b-130">工具</span><span class="sxs-lookup"><span data-stu-id="de35b-130">Tools</span></span>

<span data-ttu-id="de35b-131">以下工具在 Skype for Business Server 2019 的初始版本中不可用：</span><span class="sxs-lookup"><span data-stu-id="de35b-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="de35b-132">Skype for Business Server 容量计划计算器</span><span class="sxs-lookup"><span data-stu-id="de35b-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="de35b-133">Skype for Business Server 调试工具</span><span class="sxs-lookup"><span data-stu-id="de35b-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="de35b-134">Skype for Business Server 资源工具包 (某些工具将被删除) </span><span class="sxs-lookup"><span data-stu-id="de35b-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="de35b-135">呼叫 Parkometer</span><span class="sxs-lookup"><span data-stu-id="de35b-135">Call Parkometer</span></span>
    - <span data-ttu-id="de35b-136">查找用户控制台</span><span class="sxs-lookup"><span data-stu-id="de35b-136">Lookup user console</span></span>
    - <span data-ttu-id="de35b-137">未分配号码通知迁移</span><span class="sxs-lookup"><span data-stu-id="de35b-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="de35b-138">Skype for Business Server 2019 不支持以下工具：</span><span class="sxs-lookup"><span data-stu-id="de35b-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="de35b-139">通话质量方法 (而不是通话质量仪表板) </span><span class="sxs-lookup"><span data-stu-id="de35b-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="de35b-140">Microsoft 通话质量方法记分卡 v1.5</span><span class="sxs-lookup"><span data-stu-id="de35b-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="de35b-141">Skype for Business Server 2015 规划工具</span><span class="sxs-lookup"><span data-stu-id="de35b-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="de35b-142">Skype for Business Server 2015 压力和性能工具</span><span class="sxs-lookup"><span data-stu-id="de35b-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="de35b-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de35b-143">See also</span></span>

[<span data-ttu-id="de35b-144">Skype for Business Server 2019 的新增功能</span><span class="sxs-lookup"><span data-stu-id="de35b-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="de35b-145">管理 XMPP 联盟</span><span class="sxs-lookup"><span data-stu-id="de35b-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
