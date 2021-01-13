---
title: Skype for Business Server 2015 压力和性能工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.
ms.openlocfilehash: 551e4e5f985fc18439a4f277685034e86c7cdfb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814922"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="084a2-103">Skype for Business Server 2015 压力和性能工具</span><span class="sxs-lookup"><span data-stu-id="084a2-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="084a2-104">Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span><span class="sxs-lookup"><span data-stu-id="084a2-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="084a2-105">Skype for Business Server 2015 压力和性能工具包括可简化 Skype for Business Server 2015 容量规划的工具。</span><span class="sxs-lookup"><span data-stu-id="084a2-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="084a2-106">Skype for Business Server 2015 压力和性能工具将帮助你：</span><span class="sxs-lookup"><span data-stu-id="084a2-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="084a2-107">简化 Skype for Business Server 的硬件规划</span><span class="sxs-lookup"><span data-stu-id="084a2-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="084a2-108">为性能调整提供增强的知识和最佳做法</span><span class="sxs-lookup"><span data-stu-id="084a2-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="084a2-109">测量 Skype for Business Server 部署的性能</span><span class="sxs-lookup"><span data-stu-id="084a2-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="084a2-110">通常，使用 [Skype for Business Server 2015](../../management-tools/planning-tool/planning-tool.md) 规划工具设计拓扑，并使用 Skype for Business Server [2015](../../management-tools/capacity-planning-calculator.md)容量规划计算器优化拓扑后，通常使用此工具。</span><span class="sxs-lookup"><span data-stu-id="084a2-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="084a2-111">此工具不会针对 Skype for Business Server 2019 进行更新。</span><span class="sxs-lookup"><span data-stu-id="084a2-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="084a2-112">测试</span><span class="sxs-lookup"><span data-stu-id="084a2-112">Tests</span></span>

<span data-ttu-id="084a2-113">压力和性能工具可以模拟以下类型的用户负载：</span><span class="sxs-lookup"><span data-stu-id="084a2-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="084a2-114">即时消息 (IM) 和状态</span><span class="sxs-lookup"><span data-stu-id="084a2-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="084a2-115">音频会议</span><span class="sxs-lookup"><span data-stu-id="084a2-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="084a2-116">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="084a2-116">Application sharing</span></span>  <br/> |<span data-ttu-id="084a2-117">IP 语音 (VoIP) ，包括公用电话交换网 (PTSN) 模拟</span><span class="sxs-lookup"><span data-stu-id="084a2-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="084a2-118">Web Access 客户端会议</span><span class="sxs-lookup"><span data-stu-id="084a2-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="084a2-119">会议自动助理</span><span class="sxs-lookup"><span data-stu-id="084a2-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="084a2-120">响应组</span><span class="sxs-lookup"><span data-stu-id="084a2-120">Response Groups</span></span>  <br/> |<span data-ttu-id="084a2-121">通讯组列表扩展</span><span class="sxs-lookup"><span data-stu-id="084a2-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="084a2-122">通讯簿下载和通讯簿查询</span><span class="sxs-lookup"><span data-stu-id="084a2-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="084a2-123">增强型 911 (E911) 呼叫和位置配置文件 (拨号计划) </span><span class="sxs-lookup"><span data-stu-id="084a2-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="084a2-124">MultiView</span><span class="sxs-lookup"><span data-stu-id="084a2-124">MultiView</span></span>  <br/> |<span data-ttu-id="084a2-125">数据协作</span><span class="sxs-lookup"><span data-stu-id="084a2-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="084a2-126">移动性</span><span class="sxs-lookup"><span data-stu-id="084a2-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="084a2-127">Skype for Business Server 2015 压力和性能工具中包含的应用程序和文件</span><span class="sxs-lookup"><span data-stu-id="084a2-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="084a2-128">这些应用程序是 Skype for Business Server 压力和性能工具的一部分：</span><span class="sxs-lookup"><span data-stu-id="084a2-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="084a2-129">**工具**</span><span class="sxs-lookup"><span data-stu-id="084a2-129">**Tool**</span></span>|<span data-ttu-id="084a2-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="084a2-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="084a2-131">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="084a2-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="084a2-132">此工具用于创建用户和联系人。</span><span class="sxs-lookup"><span data-stu-id="084a2-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="084a2-133">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="084a2-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="084a2-134">用于配置要模拟的用户负载的特征。</span><span class="sxs-lookup"><span data-stu-id="084a2-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="084a2-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="084a2-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="084a2-136">模拟用户负载的工具。</span><span class="sxs-lookup"><span data-stu-id="084a2-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="084a2-137">Default.tmx</span><span class="sxs-lookup"><span data-stu-id="084a2-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="084a2-138">需要使用 Skype for Business Server 2015 日志记录工具。</span><span class="sxs-lookup"><span data-stu-id="084a2-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="084a2-139">预配脚本示例</span><span class="sxs-lookup"><span data-stu-id="084a2-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="084a2-140">用于根据特定方案配置用于运行负载测试的拓扑。</span><span class="sxs-lookup"><span data-stu-id="084a2-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="084a2-141">你可能需要修改它们，使其与特定环境相关。</span><span class="sxs-lookup"><span data-stu-id="084a2-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="084a2-142">本节中的主题</span><span class="sxs-lookup"><span data-stu-id="084a2-142">Topics in this section</span></span>

<span data-ttu-id="084a2-143">如果需要了解更多信息，应查看以下文章：</span><span class="sxs-lookup"><span data-stu-id="084a2-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="084a2-144">Skype for Busines 压力和性能工具的先决条件和设置</span><span class="sxs-lookup"><span data-stu-id="084a2-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="084a2-145">Skype for Business Server 2015 压力和性能工具的性能方案</span><span class="sxs-lookup"><span data-stu-id="084a2-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="084a2-146">设置拓扑以在压力和性能方案中运行负载</span><span class="sxs-lookup"><span data-stu-id="084a2-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="084a2-147">为 Skype for Business Server 2015 压力和性能工具配置策略</span><span class="sxs-lookup"><span data-stu-id="084a2-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="084a2-148">使用 Skype for Business Server 2015 压力和性能工具</span><span class="sxs-lookup"><span data-stu-id="084a2-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="084a2-149">Skype for Business Server 2015 压力和性能工具常见问题解答</span><span class="sxs-lookup"><span data-stu-id="084a2-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

