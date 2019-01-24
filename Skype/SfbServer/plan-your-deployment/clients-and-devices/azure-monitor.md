---
title: 规划 Skype 会议室系统 v2 管理使用 Azure 监视器
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
description: 本文讨论了使用 Azure 监视器管理 Skype 会议室系统 v2 设备中您 Skype 业务或团队实现的规划注意事项。
ms.openlocfilehash: 53f77f1353668e4887a6ff41efd040dc8f418c7e
ms.sourcegitcommit: 09fcd68e30e7f83110f98172382c74f970b339a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2019
ms.locfileid: "29448438"
---
# <a name="plan-skype-room-systems-v2-management-with-azure-monitor"></a><span data-ttu-id="17089-103">规划 Skype 会议室系统 v2 管理使用 Azure 监视器</span><span class="sxs-lookup"><span data-stu-id="17089-103">Plan Skype Room Systems v2 management with Azure Monitor</span></span>
 
 <span data-ttu-id="17089-104">本文讨论了使用 Azure 监视器管理 Skype 会议室系统 v2 设备中您 Skype 业务服务器实现的规划注意事项。</span><span class="sxs-lookup"><span data-stu-id="17089-104">This article discusses planning considerations for using Azure Monitor to administer Skype Room Systems v2 devices in your Skype for Business Server implementation.</span></span>
  
<span data-ttu-id="17089-105">[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview)处于旨在从开始在云中的管理服务的集合。</span><span class="sxs-lookup"><span data-stu-id="17089-105">[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) is a collection of management services that were designed in the cloud from the start.</span></span> <span data-ttu-id="17089-106">而不是部署和管理内部资源，完全 Azure 中承载 Azure 监视器组件。</span><span class="sxs-lookup"><span data-stu-id="17089-106">Rather than deploying and managing on-premise resources, Azure Monitor components are entirely hosted in Azure.</span></span> <span data-ttu-id="17089-107">只需进行最少的配置，即可在几分钟内开机运行。</span><span class="sxs-lookup"><span data-stu-id="17089-107">Configuration is minimal, and you can be up and running literally in a matter of minutes.</span></span> <span data-ttu-id="17089-108">具有一些自定义工作，有助于在通过为单个会议室系统提供的系统运行状况或错误的实时通知管理 Skype 会议室系统 v2 会议系统和它可能可扩展到数千个 Skype 会议室系统管理v2 会议室。</span><span class="sxs-lookup"><span data-stu-id="17089-108">With some customization work, it can aid in managing Skype Room Systems v2 conferencing systems by providing real-time notifications of system health or faults for individual room systems, and it can potentially scale up to managing thousands of Skype Room Systems v2 conference rooms.</span></span>
  
<span data-ttu-id="17089-109">本文讨论的要求、 / 体系结构、 设计和实现最佳实践需要实现的 Skype 会议室系统 v2 会议设备，基于 Azure 监视器管理，并提供了详细的文章的链接实现 Azure 监视器的 Skype 会议室系统 v2 和关键的参考信息的 Skype 会议室系统 v2 聊天室的正在进行监控。</span><span class="sxs-lookup"><span data-stu-id="17089-109">This article provides a discussion of the requirements, design/architecture, and implementation best practices needed to implement Azure Monitor based management of Skype Room Systems v2 conference devices, and provides links to detailed articles on implementing Azure Monitor for Skype Room Systems v2 and critical reference information for ongoing monitoring of Skype Room Systems v2 rooms.</span></span> 
  
## <a name="functional-overview"></a><span data-ttu-id="17089-110">功能概述</span><span class="sxs-lookup"><span data-stu-id="17089-110">Functional overview</span></span>

![SR 管理使用 Azure 监视器的关系图](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
<span data-ttu-id="17089-112">控制台设备上的 Skype 会议室系统 v2 应用程序将事件写入到其 Windows 事件日志。</span><span class="sxs-lookup"><span data-stu-id="17089-112">The Skype Room Systems v2 app on the console device writes events to its Windows Event Log.</span></span> <span data-ttu-id="17089-113">Microsoft 监控代理，安装后，会将信息传递到 Azure 监视器服务。</span><span class="sxs-lookup"><span data-stu-id="17089-113">A Microsoft Monitoring agent, once installed, passes the information to Azure Monitor service.</span></span> 
  
<span data-ttu-id="17089-114">一次正确配置，日志分析分析 JSON 负载事件中嵌入说明来描述每个 Skype 会议室系统 v2 系统如何工作和检测到哪些故障。</span><span class="sxs-lookup"><span data-stu-id="17089-114">Once properly configured, Log Analytics parses the JSON payload embedded in the event descriptions to describe how each Skype Room Systems v2 system is functioning and what faults are detected.</span></span> 
  
<span data-ttu-id="17089-115">使用 Azure 监视器管理员可以获取的已处于脱机状态的 Skype 会议室系统 v2 系统通知或是遇到应用程序、 连接或硬件故障，以及了解是否需要重新启动系统。</span><span class="sxs-lookup"><span data-stu-id="17089-115">An administrator using Azure Monitor can get notifications of Skype Room Systems v2 systems that are offline or are experiencing app, connectivity, or hardware failures as well as knowing if a system needs to be restarted.</span></span> <span data-ttu-id="17089-116">每个系统状态是频繁更新，因此这些通知接近实时更新。</span><span class="sxs-lookup"><span data-stu-id="17089-116">Each system status is updated frequently, so these notifications are close to real-time updates.</span></span>
  
## <a name="azure-monitor-requirements"></a><span data-ttu-id="17089-117">Azure 监视器要求</span><span class="sxs-lookup"><span data-stu-id="17089-117">Azure Monitor requirements</span></span>

<span data-ttu-id="17089-118">您必须具有有效的 Azure 订阅 Azure 监视程序才能使用日志分析功能。</span><span class="sxs-lookup"><span data-stu-id="17089-118">You must have a valid Azure subscription for Azure Monitor to use Log Analytics feature.</span></span> <span data-ttu-id="17089-119">请参阅 Log Analytics 工作区入门来为贵组织创建订阅。</span><span class="sxs-lookup"><span data-stu-id="17089-119">See [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) to create a subscription for your organization.</span></span>
  
<span data-ttu-id="17089-120">您应熟悉根据需要有关如何使用日志分析视图设计器。</span><span class="sxs-lookup"><span data-stu-id="17089-120">You should familiarize yourself as necessary on how to use the Log Analytics View Designer.</span></span> <span data-ttu-id="17089-121">有关详细信息，请参阅[日志分析中的视图](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)。</span><span class="sxs-lookup"><span data-stu-id="17089-121">See [Views in Log Analytics ](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) for those details.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="17089-122">相关任务</span><span class="sxs-lookup"><span data-stu-id="17089-122">Related Tasks</span></span>

1. <span data-ttu-id="17089-123">订阅 Azure 监视器日志分析后, 创建自定义字段 （如[映射自定义字段](../../deploy/deploy-clients/azure-monitor.md#Custom_fields)中所述） 所需分析将从 Skype 会议室系统 v2 控制台发送的信息。</span><span class="sxs-lookup"><span data-stu-id="17089-123">Once subscribed to Azure Monitor Log Analytics, create custom fields (as described in [Map custom fields](../../deploy/deploy-clients/azure-monitor.md#Custom_fields)) needed to parse the information that will be sent from Skype Room Systems v2 consoles.</span></span> <span data-ttu-id="17089-124">这包括了解[了解日志条目](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries)中记录的 JSON 架构。</span><span class="sxs-lookup"><span data-stu-id="17089-124">This includes understanding the JSON schema documented in [Understand the log entries](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries).</span></span>
    
2. <span data-ttu-id="17089-125">开发日志分析中的 Skype 会议室系统 v2 管理视图。</span><span class="sxs-lookup"><span data-stu-id="17089-125">Develop a Skype Room Systems v2 management view in Log Analytics.</span></span> <span data-ttu-id="17089-126">您可以[创建使用的导入方法 Skype 会议室系统 v2 仪表板](../../deploy/deploy-clients/azure-monitor.md#create-a-skype-room-systems-v2-dashboard-by-using-the-import-method)任一） 或[手动创建 Skype 会议室系统 v2 仪表板](../../deploy/deploy-clients/azure-monitor.md#create-a-skype-room-systems-v2-dashboard-manually)。</span><span class="sxs-lookup"><span data-stu-id="17089-126">You can either [Create a Skype Room Systems v2 dashboard by using the import method](../../deploy/deploy-clients/azure-monitor.md#create-a-skype-room-systems-v2-dashboard-by-using-the-import-method) ) or [Create a Skype Room Systems v2 dashboard manually](../../deploy/deploy-clients/azure-monitor.md#create-a-skype-room-systems-v2-dashboard-manually).</span></span>
    
## <a name="individual-skype-room-systems-v2-console-requirements"></a><span data-ttu-id="17089-127">单个 Skype 会议室系统 v2 控制台要求</span><span class="sxs-lookup"><span data-stu-id="17089-127">Individual Skype Room Systems v2 Console requirements</span></span>

<span data-ttu-id="17089-128">每个 Skype 会议室系统 v2 控制台是以展台模式 Surface Pro 设备上运行的应用程序 （通常，它配置为仅可在设备上运行的应用程序）。</span><span class="sxs-lookup"><span data-stu-id="17089-128">Each Skype Room Systems v2 console is an app running on a Surface Pro device in kiosk mode (normally, it's configured to be the only app that can run on the device).</span></span> <span data-ttu-id="17089-129">与任何 Windows 应用程序，Skype 会议室系统 v2 应用程序到 Windows 事件日志中写入像启动和硬件故障的事件。</span><span class="sxs-lookup"><span data-stu-id="17089-129">As with any Windows app, the Skype Room Systems v2 app writes events like startup and hardware faults to the Windows Event Log.</span></span> <span data-ttu-id="17089-130">添加 Skype 会议室系统 v2 设备上的 Microsoft 监视器代理允许待收集这些事件。</span><span class="sxs-lookup"><span data-stu-id="17089-130">Adding an Microsoft Monitor agent on your Skype Room Systems v2 device allows these events to be collected.</span></span> <span data-ttu-id="17089-131">（请参阅[到 Azure 中的日志分析服务的连接的 Windows 计算机](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)详细信息。）</span><span class="sxs-lookup"><span data-stu-id="17089-131">(See [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) for details.)</span></span>
  
## <a name="ongoing-management"></a><span data-ttu-id="17089-132">正在进行的管理</span><span class="sxs-lookup"><span data-stu-id="17089-132">Ongoing management</span></span>

<span data-ttu-id="17089-133">同时使用 Azure 监视器管理 Skype 会议室系统 v2 设备，您需要了解 Azure 监视器使用事件日志中包含的信息。</span><span class="sxs-lookup"><span data-stu-id="17089-133">While using Azure Monitor to manage your Skype Room Systems v2 devices, you'll need to understand the information contained in the event logs used by Azure Monitor.</span></span> <span data-ttu-id="17089-134">有关这些运行状况消息的详细信息，请参阅[了解日志条目](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries)。</span><span class="sxs-lookup"><span data-stu-id="17089-134">See [Understand the log entries](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries) for details on these health messages.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="17089-135">相关任务</span><span class="sxs-lookup"><span data-stu-id="17089-135">Related Tasks</span></span>

- <span data-ttu-id="17089-136">了解通知生成 Skype 会议室系统 v2 以及如何解决这些问题 （请参阅名为[了解日志条目](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries)的部分）</span><span class="sxs-lookup"><span data-stu-id="17089-136">Understand the Alerts generated by Skype Room Systems v2 and how to resolve them (see the section titled [Understand the log entries](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries))</span></span>
    
## <a name="see-also"></a><span data-ttu-id="17089-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17089-137">See also</span></span>

[<span data-ttu-id="17089-138">部署 Skype 会议室系统 v2 管理使用 Azure 监视器</span><span class="sxs-lookup"><span data-stu-id="17089-138">Deploy Skype Room Systems v2 management with Azure Monitor</span></span>](../../deploy/deploy-clients/azure-monitor.md)
  
[<span data-ttu-id="17089-139">管理使用 Azure 监视器的 Skype 会议室系统 v2 设备</span><span class="sxs-lookup"><span data-stu-id="17089-139">Manage Skype Room Systems v2 devices with Azure Monitor</span></span>](../../manage/skype-room-systems-v2/azure-monitor.md)