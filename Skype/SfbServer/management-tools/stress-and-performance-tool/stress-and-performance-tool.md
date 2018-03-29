---
title: Skype 业务服务器 2015年的压力和性能工具
ms.author: heidip
author: microsoftheidi
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: 在容量规划和性能调优不生产或测试环境中使用业务服务器 2015年的压力和性能工具 Skype。
ms.openlocfilehash: 0a0a5b17a6e45b2e8944e0e0dd4b3840fc62e102
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="d3683-103">Skype 业务服务器 2015年的压力和性能工具</span><span class="sxs-lookup"><span data-stu-id="d3683-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="d3683-104">在容量规划和性能调优不生产或测试环境中使用业务服务器 2015年的压力和性能工具 Skype。</span><span class="sxs-lookup"><span data-stu-id="d3683-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="d3683-105">为业务服务器 2015年压力和性能工具 Skype 包括可以简化您的容量规划的 Skype 的业务服务器 2015年的工具。</span><span class="sxs-lookup"><span data-stu-id="d3683-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="d3683-106">Skype 业务服务器 2015年的压力和性能工具将帮助您：</span><span class="sxs-lookup"><span data-stu-id="d3683-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="d3683-107">简化规划为 Skype 业务服务器硬件</span><span class="sxs-lookup"><span data-stu-id="d3683-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="d3683-108">提高了您的知识和最佳性能调整</span><span class="sxs-lookup"><span data-stu-id="d3683-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="d3683-109">测量的性能您 Skype 业务服务器部署</span><span class="sxs-lookup"><span data-stu-id="d3683-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="d3683-110">您通常使用此工具后使用[Skype 业务服务器 2015年计划工具](../../management-tools/planning-tool/planning-tool.md)来设计拓扑结构，并优化使用[Skype 业务服务器 2015年容量规划计算器](../../management-tools/capacity-planning-calculator.md)的拓扑。</span><span class="sxs-lookup"><span data-stu-id="d3683-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 
  
## <a name="tests"></a><span data-ttu-id="d3683-111">测试</span><span class="sxs-lookup"><span data-stu-id="d3683-111">Tests</span></span>

<span data-ttu-id="d3683-112">压力和性能工具可以模拟用户负载的这些类型：</span><span class="sxs-lookup"><span data-stu-id="d3683-112">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d3683-113">即时消息 (IM) 和在线状态</span><span class="sxs-lookup"><span data-stu-id="d3683-113">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="d3683-114">音频会议</span><span class="sxs-lookup"><span data-stu-id="d3683-114">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="d3683-115">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="d3683-115">Application sharing</span></span>  <br/> |<span data-ttu-id="d3683-116">IP 语音 (VoIP)，包括公用交换的电话网络 (PTSN) 模拟</span><span class="sxs-lookup"><span data-stu-id="d3683-116">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="d3683-117">Web 访问客户会议</span><span class="sxs-lookup"><span data-stu-id="d3683-117">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="d3683-118">会议自动助理</span><span class="sxs-lookup"><span data-stu-id="d3683-118">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="d3683-119">响应组</span><span class="sxs-lookup"><span data-stu-id="d3683-119">Response Groups</span></span>  <br/> |<span data-ttu-id="d3683-120">通讯组列表扩展</span><span class="sxs-lookup"><span data-stu-id="d3683-120">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="d3683-121">下载通讯簿和地址簿查询</span><span class="sxs-lookup"><span data-stu-id="d3683-121">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="d3683-122">增强的 911 (E911) 呼叫和位置配置文件 （拨号计划）</span><span class="sxs-lookup"><span data-stu-id="d3683-122">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="d3683-123">多视图</span><span class="sxs-lookup"><span data-stu-id="d3683-123">MultiView</span></span>  <br/> |<span data-ttu-id="d3683-124">数据协作</span><span class="sxs-lookup"><span data-stu-id="d3683-124">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="d3683-125">移动性</span><span class="sxs-lookup"><span data-stu-id="d3683-125">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="d3683-126">应用程序和 Skype 业务服务器 2015年的压力和性能工具中包含的文件</span><span class="sxs-lookup"><span data-stu-id="d3683-126">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="d3683-127">这些应用程序是业务服务器的压力和性能工具 Skype 的一部分：</span><span class="sxs-lookup"><span data-stu-id="d3683-127">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="d3683-128">**工具**</span><span class="sxs-lookup"><span data-stu-id="d3683-128">**Tool**</span></span>|<span data-ttu-id="d3683-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="d3683-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d3683-130">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="d3683-130">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="d3683-131">此工具用于创建用户和联系人。</span><span class="sxs-lookup"><span data-stu-id="d3683-131">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="d3683-132">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="d3683-132">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="d3683-133">用于配置要模拟的用户负载的特征。</span><span class="sxs-lookup"><span data-stu-id="d3683-133">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="d3683-134">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="d3683-134">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="d3683-135">该工具模拟用户负载。</span><span class="sxs-lookup"><span data-stu-id="d3683-135">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="d3683-136">Default.tmx</span><span class="sxs-lookup"><span data-stu-id="d3683-136">Default.tmx</span></span>  <br/> |<span data-ttu-id="d3683-137">需要使用 Skype 业务服务器 2015年日志记录工具。</span><span class="sxs-lookup"><span data-stu-id="d3683-137">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="d3683-138">自动配置脚本示例</span><span class="sxs-lookup"><span data-stu-id="d3683-138">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="d3683-139">用来配置运行负载测试，基于特定方案的拓扑。</span><span class="sxs-lookup"><span data-stu-id="d3683-139">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="d3683-140">您可能需要修改以使其适用于您的特定环境。</span><span class="sxs-lookup"><span data-stu-id="d3683-140">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="d3683-141">本节中的主题</span><span class="sxs-lookup"><span data-stu-id="d3683-141">Topics in this section</span></span>

<span data-ttu-id="d3683-142">如果您需要了解得越多，您应查看以下文章：</span><span class="sxs-lookup"><span data-stu-id="d3683-142">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="d3683-143">系统必备组件和业务压力和性能工具 Skype 的安装程序</span><span class="sxs-lookup"><span data-stu-id="d3683-143">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="d3683-144">为业务服务器 2015年的压力和性能工具 Skype 的性能情况</span><span class="sxs-lookup"><span data-stu-id="d3683-144">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="d3683-145">资源调配压力和性能的情况下运行负载的拓扑</span><span class="sxs-lookup"><span data-stu-id="d3683-145">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="d3683-146">配置策略的 Skype 业务服务器 2015年的压力和性能工具</span><span class="sxs-lookup"><span data-stu-id="d3683-146">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="d3683-147">使用 Skype 业务服务器 2015年的压力和性能工具</span><span class="sxs-lookup"><span data-stu-id="d3683-147">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="d3683-148">为业务服务器 2015年的压力和性能工具 Skype 的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="d3683-148">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

