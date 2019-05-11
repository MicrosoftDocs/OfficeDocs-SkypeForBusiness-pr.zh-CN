---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: 容量规划和性能在非生产或测试环境中调整期间使用的业务服务器 2015年压力和性能工具 Skype。
ms.openlocfilehash: 7705e92c8389e0377e805bd7d8e09aee454d9160
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904571"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="8e7a2-103">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="8e7a2-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="8e7a2-104">容量规划和性能在非生产或测试环境中调整期间使用的业务服务器 2015年压力和性能工具 Skype。</span><span class="sxs-lookup"><span data-stu-id="8e7a2-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="8e7a2-105">为业务服务器 2015年压力和性能工具 Skype 包括将简化您的容量规划的 Skype 业务服务器 2015年的工具。</span><span class="sxs-lookup"><span data-stu-id="8e7a2-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="8e7a2-106">为业务服务器 2015年压力和性能工具 Skype 将帮助您完成：</span><span class="sxs-lookup"><span data-stu-id="8e7a2-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="8e7a2-107">简化您的 Skype 规划业务服务器的硬件</span><span class="sxs-lookup"><span data-stu-id="8e7a2-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="8e7a2-108">提高了您的知识和优化性能的最佳实践</span><span class="sxs-lookup"><span data-stu-id="8e7a2-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="8e7a2-109">测量业务服务器部署您 Skype 的性能</span><span class="sxs-lookup"><span data-stu-id="8e7a2-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="8e7a2-110">使用[Skype 业务 Server 2015 规划工具的](../../management-tools/planning-tool/planning-tool.md)设计拓扑，和优化具有[业务 Server 2015 容量规划计算器的 Skype](../../management-tools/capacity-planning-calculator.md)的拓扑后，您通常会使用此工具。</span><span class="sxs-lookup"><span data-stu-id="8e7a2-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="8e7a2-111">此工具不将 Skype 的业务服务器 2019年的更新。</span><span class="sxs-lookup"><span data-stu-id="8e7a2-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="8e7a2-112">测试</span><span class="sxs-lookup"><span data-stu-id="8e7a2-112">Tests</span></span>

<span data-ttu-id="8e7a2-113">压力和性能工具可以模拟这些类型的用户负载：</span><span class="sxs-lookup"><span data-stu-id="8e7a2-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8e7a2-114">即时消息 (IM) 和状态</span><span class="sxs-lookup"><span data-stu-id="8e7a2-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="8e7a2-115">音频会议</span><span class="sxs-lookup"><span data-stu-id="8e7a2-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="8e7a2-116">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="8e7a2-116">Application sharing</span></span>  <br/> |<span data-ttu-id="8e7a2-117">IP 电话 (VoIP)，包括公用电话交换网 (PTSN) 模拟语音</span><span class="sxs-lookup"><span data-stu-id="8e7a2-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="8e7a2-118">Web Access 客户端会议</span><span class="sxs-lookup"><span data-stu-id="8e7a2-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="8e7a2-119">会议自动助理</span><span class="sxs-lookup"><span data-stu-id="8e7a2-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="8e7a2-120">响应组</span><span class="sxs-lookup"><span data-stu-id="8e7a2-120">Response Groups</span></span>  <br/> |<span data-ttu-id="8e7a2-121">通讯组列表扩展</span><span class="sxs-lookup"><span data-stu-id="8e7a2-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="8e7a2-122">通讯簿下载和通讯簿查询</span><span class="sxs-lookup"><span data-stu-id="8e7a2-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="8e7a2-123">增强型 911 (E911) 呼叫和位置配置文件 （拨号计划）</span><span class="sxs-lookup"><span data-stu-id="8e7a2-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="8e7a2-124">多视图</span><span class="sxs-lookup"><span data-stu-id="8e7a2-124">MultiView</span></span>  <br/> |<span data-ttu-id="8e7a2-125">数据协作</span><span class="sxs-lookup"><span data-stu-id="8e7a2-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="8e7a2-126">移动性</span><span class="sxs-lookup"><span data-stu-id="8e7a2-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="8e7a2-127">应用程序和 Skype 的业务服务器 2015年压力和性能工具中包含的文件</span><span class="sxs-lookup"><span data-stu-id="8e7a2-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="8e7a2-128">这些应用程序是业务 Server 压力和性能工具 Skype 的一部分：</span><span class="sxs-lookup"><span data-stu-id="8e7a2-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="8e7a2-129">**工具**</span><span class="sxs-lookup"><span data-stu-id="8e7a2-129">**Tool**</span></span>|<span data-ttu-id="8e7a2-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="8e7a2-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8e7a2-131">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="8e7a2-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="8e7a2-132">此工具用于创建用户和联系人。</span><span class="sxs-lookup"><span data-stu-id="8e7a2-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="8e7a2-133">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="8e7a2-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="8e7a2-134">用于配置模拟的用户负载的特征。</span><span class="sxs-lookup"><span data-stu-id="8e7a2-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="8e7a2-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="8e7a2-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="8e7a2-136">用户负载模拟工具。</span><span class="sxs-lookup"><span data-stu-id="8e7a2-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="8e7a2-137">Default.tmx</span><span class="sxs-lookup"><span data-stu-id="8e7a2-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="8e7a2-138">需要 Skype 用于业务 Server 2015 日志记录工具。</span><span class="sxs-lookup"><span data-stu-id="8e7a2-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="8e7a2-139">设置脚本示例</span><span class="sxs-lookup"><span data-stu-id="8e7a2-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="8e7a2-140">用于配置运行负载测试，根据特定方案的拓扑。</span><span class="sxs-lookup"><span data-stu-id="8e7a2-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="8e7a2-141">您可能需要修改以使其与您的特定环境相关。</span><span class="sxs-lookup"><span data-stu-id="8e7a2-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="8e7a2-142">本节中的主题</span><span class="sxs-lookup"><span data-stu-id="8e7a2-142">Topics in this section</span></span>

<span data-ttu-id="8e7a2-143">如果您需要了解，您应查看以下文章：</span><span class="sxs-lookup"><span data-stu-id="8e7a2-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="8e7a2-144">Skype for Business Stress and Performance Tool 的先决条件和设置</span><span class="sxs-lookup"><span data-stu-id="8e7a2-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="8e7a2-145">为业务服务器 2015年压力和性能工具 Skype 的性能方案</span><span class="sxs-lookup"><span data-stu-id="8e7a2-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="8e7a2-146">设置要在压力和性能的情况下运行负载的拓扑</span><span class="sxs-lookup"><span data-stu-id="8e7a2-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="8e7a2-147">配置策略的 Skype 的业务服务器 2015年压力和性能工具</span><span class="sxs-lookup"><span data-stu-id="8e7a2-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="8e7a2-148">使用 Skype 业务服务器 2015年压力和性能工具</span><span class="sxs-lookup"><span data-stu-id="8e7a2-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="8e7a2-149">为业务服务器 2015年压力和性能工具 Skype 常见问题</span><span class="sxs-lookup"><span data-stu-id="8e7a2-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

