---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: 在非生产环境或测试环境中进行容量规划和性能优化期间, 使用 Skype for Business Server 2015 应力和性能工具。
ms.openlocfilehash: d82d5ed33e6dca1303aed9f49150dd6b56fc4e1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299514"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="973c9-103">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="973c9-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="973c9-104">在非生产环境或测试环境中进行容量规划和性能优化期间, 使用 Skype for Business Server 2015 应力和性能工具。</span><span class="sxs-lookup"><span data-stu-id="973c9-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="973c9-105">Skype for Business Server 2015 应力和性能工具包括可简化 Skype for business Server 2015 的容量规划的工具。</span><span class="sxs-lookup"><span data-stu-id="973c9-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="973c9-106">Skype for Business Server 2015 应力和性能工具将帮助你:</span><span class="sxs-lookup"><span data-stu-id="973c9-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="973c9-107">简化 Skype for business 服务器的硬件规划</span><span class="sxs-lookup"><span data-stu-id="973c9-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="973c9-108">为您提供改进的性能优化知识和最佳做法</span><span class="sxs-lookup"><span data-stu-id="973c9-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="973c9-109">衡量 Skype for business 服务器部署的性能</span><span class="sxs-lookup"><span data-stu-id="973c9-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="973c9-110">在使用[skype For Business server 2015 规划工具](../../management-tools/planning-tool/planning-tool.md)设计拓扑并使用[Skype for Business Server 2015 容量规划计算器](../../management-tools/capacity-planning-calculator.md)优化拓扑时, 通常使用此工具。</span><span class="sxs-lookup"><span data-stu-id="973c9-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="973c9-111">此工具将不会针对 Skype for Business Server 2019 进行更新。</span><span class="sxs-lookup"><span data-stu-id="973c9-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="973c9-112">测试</span><span class="sxs-lookup"><span data-stu-id="973c9-112">Tests</span></span>

<span data-ttu-id="973c9-113">压力和性能工具可以模拟以下类型的用户负载:</span><span class="sxs-lookup"><span data-stu-id="973c9-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="973c9-114">即时消息 (IM) 和状态</span><span class="sxs-lookup"><span data-stu-id="973c9-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="973c9-115">音频会议</span><span class="sxs-lookup"><span data-stu-id="973c9-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="973c9-116">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="973c9-116">Application sharing</span></span>  <br/> |<span data-ttu-id="973c9-117">IP 语音 (VoIP), 包括公共交换电话网络 (PTSN) 模拟</span><span class="sxs-lookup"><span data-stu-id="973c9-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="973c9-118">Web Access 客户端会议</span><span class="sxs-lookup"><span data-stu-id="973c9-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="973c9-119">会议自动助理</span><span class="sxs-lookup"><span data-stu-id="973c9-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="973c9-120">响应组</span><span class="sxs-lookup"><span data-stu-id="973c9-120">Response Groups</span></span>  <br/> |<span data-ttu-id="973c9-121">通讯组列表扩展</span><span class="sxs-lookup"><span data-stu-id="973c9-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="973c9-122">通讯簿下载和通讯簿查询</span><span class="sxs-lookup"><span data-stu-id="973c9-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="973c9-123">增强的 911 (E911) 通话和位置配置文件 (拨号计划)</span><span class="sxs-lookup"><span data-stu-id="973c9-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="973c9-124">重视</span><span class="sxs-lookup"><span data-stu-id="973c9-124">MultiView</span></span>  <br/> |<span data-ttu-id="973c9-125">数据协作</span><span class="sxs-lookup"><span data-stu-id="973c9-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="973c9-126">移动性</span><span class="sxs-lookup"><span data-stu-id="973c9-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="973c9-127">Skype for Business Server 2015 中附带的应用程序和文件应力和性能工具</span><span class="sxs-lookup"><span data-stu-id="973c9-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="973c9-128">这些应用程序是 Skype for Business Server 压力和性能工具的一部分:</span><span class="sxs-lookup"><span data-stu-id="973c9-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="973c9-129">**工具**</span><span class="sxs-lookup"><span data-stu-id="973c9-129">**Tool**</span></span>|<span data-ttu-id="973c9-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="973c9-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="973c9-131">UserProvisioningTool</span><span class="sxs-lookup"><span data-stu-id="973c9-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="973c9-132">此工具用于创建用户和联系人。</span><span class="sxs-lookup"><span data-stu-id="973c9-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="973c9-133">UserProfileGenerator</span><span class="sxs-lookup"><span data-stu-id="973c9-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="973c9-134">用于配置要模拟的用户负载的特征。</span><span class="sxs-lookup"><span data-stu-id="973c9-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="973c9-135">LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="973c9-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="973c9-136">模拟用户负载的工具。</span><span class="sxs-lookup"><span data-stu-id="973c9-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="973c9-137">默认的 tmx</span><span class="sxs-lookup"><span data-stu-id="973c9-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="973c9-138">需要使用 Skype for Business Server 2015 日志记录工具。</span><span class="sxs-lookup"><span data-stu-id="973c9-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="973c9-139">预配脚本示例</span><span class="sxs-lookup"><span data-stu-id="973c9-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="973c9-140">用于根据特定方案配置用于运行负载测试的拓扑。</span><span class="sxs-lookup"><span data-stu-id="973c9-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="973c9-141">你可能需要对其进行修改以使其与你的特定环境相关。</span><span class="sxs-lookup"><span data-stu-id="973c9-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="973c9-142">本部分中的主题</span><span class="sxs-lookup"><span data-stu-id="973c9-142">Topics in this section</span></span>

<span data-ttu-id="973c9-143">如果需要了解详细信息, 请查看以下文章:</span><span class="sxs-lookup"><span data-stu-id="973c9-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="973c9-144">Skype for Business Stress and Performance Tool 的先决条件和设置</span><span class="sxs-lookup"><span data-stu-id="973c9-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="973c9-145">Skype for Business Server 2015 的性能方案应力和性能工具</span><span class="sxs-lookup"><span data-stu-id="973c9-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="973c9-146">预配拓扑以在压力和性能方案中运行负载</span><span class="sxs-lookup"><span data-stu-id="973c9-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="973c9-147">为 Skype for Business Server 2015 配置策略应力和性能工具</span><span class="sxs-lookup"><span data-stu-id="973c9-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="973c9-148">使用 Skype for Business Server 2015 应力和性能工具</span><span class="sxs-lookup"><span data-stu-id="973c9-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="973c9-149">Skype for Business Server 2015 的常见问题应力和性能工具</span><span class="sxs-lookup"><span data-stu-id="973c9-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

