---
title: 使用 OMS 规划 Skype 会议室系统 v2 管理
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
description: 本文讨论使用 Operations Management Suite 管理你的 Skype for Business Server 2015 实现中的 Skype 会议室系统 v2 设备时的规划注意事项。
ms.openlocfilehash: e6409370da3597623526379581081e617f48dd81
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-skype-room-systems-v2-management-with-oms"></a><span data-ttu-id="ab1a1-103">使用 OMS 规划 Skype 会议室系统 v2 管理</span><span class="sxs-lookup"><span data-stu-id="ab1a1-103">Plan Skype Room Systems v2 management with OMS</span></span>
 
 <span data-ttu-id="ab1a1-104">本文讨论使用 Operations Management Suite 管理你的 Skype for Business Server 2015 实现中的 Skype 会议室系统 v2 设备时的规划注意事项。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-104">This article discusses planning considerations for using Operations Management Suite to administer Skype Room Systems v2 devices in your Skype for Business Server 2015 implementation.</span></span>
  
<span data-ttu-id="ab1a1-105">[操作管理套件](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview)(OMS) 是一套旨在在云从一开始的管理服务。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-105">[Operations Management Suite](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview) (OMS) is a collection of management services that were designed in the cloud from the start.</span></span> <span data-ttu-id="ab1a1-106">OMS 组件并不部署和管理本地资源，而是完全托管在 Azure 中。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-106">Rather than deploying and managing on-premise resources, OMS components are entirely hosted in Azure.</span></span> <span data-ttu-id="ab1a1-107">只需进行最少的配置，即可在几分钟内开机运行。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-107">Configuration is minimal, and you can be up and running literally in a matter of minutes.</span></span> <span data-ttu-id="ab1a1-108">某些自定义项的工作，它能够帮助管理通过为各个房间的系统，提供系统健康状况或故障的实时通知 Skype 的空间系统 v2 会议系统，它可以有可能扩展到管理数千个 Skype 的空间系统v2 会议室。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-108">With some customization work, it can aid in managing Skype Room Systems v2 conferencing systems by providing real-time notifications of system health or faults for individual room systems, and it can potentially scale up to managing thousands of Skype Room Systems v2 conference rooms.</span></span>
  
<span data-ttu-id="ab1a1-109">这篇文章提供的要求、 设计/体系结构和实现的 Skype 的空间系统 v2 会议设备，OMS 管理所需的最佳实现做法的讨论并提供有关实施 OMS 的详细的文章的链接Skype 的空间系统 v2 和日常 OMS Skype 的空间系统 v2 机房管理的重要参考信息的管理。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-109">This article provides a discussion of the requirements, design/architecture, and implementation best practices needed to implement OMS management of Skype Room Systems v2 conference devices, and provides links to detailed articles on implementing OMS management for Skype Room Systems v2 and critical reference information for ongoing OMS management of Skype Room Systems v2 rooms.</span></span> 
  
## <a name="functional-overview"></a><span data-ttu-id="ab1a1-110">功能概述</span><span class="sxs-lookup"><span data-stu-id="ab1a1-110">Functional overview</span></span>

![使用 OMS 的 SRS 管理图表](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
<span data-ttu-id="ab1a1-112">Skype 的空间系统 v2 应用程序在控制台设备会将事件写入到其 Windows 事件日志。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-112">The Skype Room Systems v2 app on the console device writes events to its Windows Event Log.</span></span> <span data-ttu-id="ab1a1-113">安装 OMS 代理后，该代理即可向 OMS 传递信息。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-113">An OMS agent, once installed, passes the information to OMS.</span></span> 
  
<span data-ttu-id="ab1a1-114">一次正确配置，OMS 的 JSON 负载事件中嵌入描述来描述每个 Skype 的空间系统 v2 系统如何工作和哪种故障检测的分析。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-114">Once properly configured, OMS parses the JSON payload embedded in the event descriptions to describe how each Skype Room Systems v2 system is functioning and what faults are detected.</span></span> 
  
<span data-ttu-id="ab1a1-115">管理员使用 OMS 可以获得通知的 Skype 的空间系统 v2 系统离线或会遇到应用程序、 连接或硬件故障以及知道是否需要重新启动系统。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-115">An administrator using OMS can get notifications of Skype Room Systems v2 systems that are offline or are experiencing app, connectivity, or hardware failures as well as knowing if a system needs to be restarted.</span></span> <span data-ttu-id="ab1a1-116">每个系统状态每五分钟更新一次，因此这些通知接近于实时更新。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-116">Each system status is updated every five minutes, so these notifications are close to real-time updates.</span></span>
  
## <a name="oms-requirements"></a><span data-ttu-id="ab1a1-117">OMS 要求</span><span class="sxs-lookup"><span data-stu-id="ab1a1-117">OMS requirements</span></span>

<span data-ttu-id="ab1a1-118">必须具有 OMS 的有效订阅才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-118">You must have a valid subscription for OMS to use this feature.</span></span> <span data-ttu-id="ab1a1-119">请参阅[日志分析区开始](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started?toc=%2fazure%2foperations-management-suite%2ftoc.json)为您的组织创建预订。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-119">See [Get started with a Log Analytics workspace](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started?toc=%2fazure%2foperations-management-suite%2ftoc.json) to create a subscription for your organization.</span></span>
  
<span data-ttu-id="ab1a1-120">如有必要，应尽量使自己熟悉 OMS View Designer 的使用方法。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-120">You should familiarize yourself as necessary on how to use the OMS View Designer.</span></span> <span data-ttu-id="ab1a1-121">这些详细信息，请参阅[操作管理套件 (OMS) 管理解决方案中的视图](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-solutions-resources-views)。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-121">See [Views in Operations Management Suite (OMS) management solutions](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-solutions-resources-views) for those details.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="ab1a1-122">相关任务</span><span class="sxs-lookup"><span data-stu-id="ab1a1-122">Related Tasks</span></span>

1. <span data-ttu-id="ab1a1-123">一旦订阅了 OMS，创建 （[映射自定义字段](../../deploy/deploy-clients/with-oms.md#Custom_fields)中所述） 的分析将从 Skype 的空间系统 v2 控制台发送信息所需的自定义字段。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-123">Once subscribed to OMS, create custom fields (described in [Map custom fields](../../deploy/deploy-clients/with-oms.md#Custom_fields)) needed to parse the information that will be sent from Skype Room Systems v2 consoles.</span></span> <span data-ttu-id="ab1a1-124">这包括了解[了解日志条目](../../manage/skype-room-systems-v2/oms.md#Telemetry)中记录的 JSON 架构。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-124">This includes understanding the JSON schema documented in [Understand the log entries](../../manage/skype-room-systems-v2/oms.md#Telemetry).</span></span>
    
2. <span data-ttu-id="ab1a1-125">开发 Skype 的空间系统 v2 管理视图在 OMS （请参见[定义 SRS v2 中 OMS 的视图](../../deploy/deploy-clients/with-oms.md#Views)） 中使用视图设计器前面提到。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-125">Develop a Skype Room Systems v2 management view in OMS (see [Define the SRS v2 views in OMS](../../deploy/deploy-clients/with-oms.md#Views)) using the View Designer mentioned earlier.</span></span>
    
## <a name="individual-skype-room-systems-v2-console-requirements"></a><span data-ttu-id="ab1a1-126">单个的 Skype 的空间系统 v2 控制台要求</span><span class="sxs-lookup"><span data-stu-id="ab1a1-126">Individual Skype Room Systems v2 Console requirements</span></span>

<span data-ttu-id="ab1a1-127">每个 Skype 的空间系统 v2 控制台是在 kiosk 模式下表面 4 设备上运行的应用程序 （通常情况下，其配置为只可以在设备上运行的应用程序）。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-127">Each Skype Room Systems v2 console is an app running on a Surface 4 device in kiosk mode (normally, it's configured to be the only app that can run on the device).</span></span> <span data-ttu-id="ab1a1-128">与任何 Windows 应用程序中，Skype 的空间系统 v2 应用程序写入启动和硬件故障这样的事件记录到 Windows 事件日志。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-128">As with any Windows app, the Skype Room Systems v2 app writes events like startup and hardware faults to the Windows Event Log.</span></span> <span data-ttu-id="ab1a1-129">Skype 的空间系统 v2 设备上添加 OMS 代理允许通过 OMS 收集这些事件。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-129">Adding an OMS agent on your Skype Room Systems v2 device allows these events to be collected by OMS.</span></span> <span data-ttu-id="ab1a1-130">（请参阅[连接 Windows Azure 中的日志分析服务的计算机](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)的详细信息）。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-130">(See [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents) for details.)</span></span>
  
## <a name="ongoing-management"></a><span data-ttu-id="ab1a1-131">正在进行的管理</span><span class="sxs-lookup"><span data-stu-id="ab1a1-131">Ongoing management</span></span>

<span data-ttu-id="ab1a1-132">同时使用 OMS 来管理您的 Skype 的空间系统 v2 会议设备，您需要了解使用 OMS 的事件日志中包含的信息。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-132">While using OMS to manage your Skype Room Systems v2 conference devices, you'll need to understand the information contained in the event logs used by OMS.</span></span> <span data-ttu-id="ab1a1-133">这些健康消息的详细信息，请参阅[了解日志条目](../../manage/skype-room-systems-v2/oms.md#Telemetry)。</span><span class="sxs-lookup"><span data-stu-id="ab1a1-133">See [Understand the log entries](../../manage/skype-room-systems-v2/oms.md#Telemetry) for details on these health messages.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="ab1a1-134">相关任务</span><span class="sxs-lookup"><span data-stu-id="ab1a1-134">Related Tasks</span></span>

- <span data-ttu-id="ab1a1-135">了解通过 Skype 的空间系统 v2 和如何解决这些问题 （请参见一节[了解日志条目](../../manage/skype-room-systems-v2/oms.md#Telemetry)） 生成的警报</span><span class="sxs-lookup"><span data-stu-id="ab1a1-135">Understand the Alerts generated by Skype Room Systems v2 and how to resolve them (see the section titled [Understand the log entries](../../manage/skype-room-systems-v2/oms.md#Telemetry))</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ab1a1-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab1a1-136">See also</span></span>

#### 

[<span data-ttu-id="ab1a1-137">部署与 OMS 的 Skype 的空间系统 v2 管理</span><span class="sxs-lookup"><span data-stu-id="ab1a1-137">Deploy Skype Room Systems v2 management with OMS</span></span>](../../deploy/deploy-clients/with-oms.md)
  
[<span data-ttu-id="ab1a1-138">管理与 OMS 的 Skype 的空间系统 v2 设备</span><span class="sxs-lookup"><span data-stu-id="ab1a1-138">Manage Skype Room Systems v2 devices with OMS</span></span>](../../manage/skype-room-systems-v2/oms.md)

