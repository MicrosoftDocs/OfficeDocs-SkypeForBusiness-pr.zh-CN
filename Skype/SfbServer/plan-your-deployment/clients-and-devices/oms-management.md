---
title: 使用 OMS 规划 Skype 会议室系统 v2 管理
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
description: 本文讨论使用操作管理套件管理 Skype 会议室系统 v2 设备中您 Skype 业务服务器实现的规划注意事项。
ms.openlocfilehash: 26cfe0fa000a92548c81b8bab80d1bdde5ee78b4
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531029"
---
# <a name="plan-skype-room-systems-v2-management-with-oms"></a><span data-ttu-id="29412-103">使用 OMS 规划 Skype 会议室系统 v2 管理</span><span class="sxs-lookup"><span data-stu-id="29412-103">Plan Skype Room Systems v2 management with OMS</span></span>
 
 <span data-ttu-id="29412-104">本文讨论使用操作管理套件管理 Skype 会议室系统 v2 设备中您 Skype 业务服务器实现的规划注意事项。</span><span class="sxs-lookup"><span data-stu-id="29412-104">This article discusses planning considerations for using Operations Management Suite to administer Skype Room Systems v2 devices in your Skype for Business Server implementation.</span></span>
  
<span data-ttu-id="29412-105">[操作管理套件](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)(OMS) 是旨在从开始在云中的管理服务的集合。</span><span class="sxs-lookup"><span data-stu-id="29412-105">[Operations Management Suite](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview) (OMS) is a collection of management services that were designed in the cloud from the start.</span></span> <span data-ttu-id="29412-106">OMS 组件并不部署和管理本地资源，而是完全托管在 Azure 中。</span><span class="sxs-lookup"><span data-stu-id="29412-106">Rather than deploying and managing on-premise resources, OMS components are entirely hosted in Azure.</span></span> <span data-ttu-id="29412-107">只需进行最少的配置，即可在几分钟内开机运行。</span><span class="sxs-lookup"><span data-stu-id="29412-107">Configuration is minimal, and you can be up and running literally in a matter of minutes.</span></span> <span data-ttu-id="29412-108">具有一些自定义工作，有助于在通过为单个会议室系统提供的系统运行状况或错误的实时通知管理 Skype 会议室系统 v2 会议系统和它可能可扩展到数千个 Skype 会议室系统管理v2 会议室。</span><span class="sxs-lookup"><span data-stu-id="29412-108">With some customization work, it can aid in managing Skype Room Systems v2 conferencing systems by providing real-time notifications of system health or faults for individual room systems, and it can potentially scale up to managing thousands of Skype Room Systems v2 conference rooms.</span></span>
  
<span data-ttu-id="29412-109">本文讨论的要求、 设计/体系结构和实现最佳实践需要实现 OMS 管理 Skype 会议室系统 v2 会议设备，并实现 OMS 提供详细的文章的链接Skype 会议室系统 v2 和关键的参考信息的持续 OMS 管理 Skype 会议室系统 v2 聊天室的管理。</span><span class="sxs-lookup"><span data-stu-id="29412-109">This article provides a discussion of the requirements, design/architecture, and implementation best practices needed to implement OMS management of Skype Room Systems v2 conference devices, and provides links to detailed articles on implementing OMS management for Skype Room Systems v2 and critical reference information for ongoing OMS management of Skype Room Systems v2 rooms.</span></span> 
  
## <a name="functional-overview"></a><span data-ttu-id="29412-110">功能概述</span><span class="sxs-lookup"><span data-stu-id="29412-110">Functional overview</span></span>

![使用 OMS 的 SRS 管理图表](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
<span data-ttu-id="29412-112">控制台设备上的 Skype 会议室系统 v2 应用程序将事件写入到其 Windows 事件日志。</span><span class="sxs-lookup"><span data-stu-id="29412-112">The Skype Room Systems v2 app on the console device writes events to its Windows Event Log.</span></span> <span data-ttu-id="29412-113">安装 OMS 代理后，该代理即可向 OMS 传递信息。</span><span class="sxs-lookup"><span data-stu-id="29412-113">An OMS agent, once installed, passes the information to OMS.</span></span> 
  
<span data-ttu-id="29412-114">一次正确配置，OMS 分析 JSON 负载事件中嵌入说明来描述每个 Skype 会议室系统 v2 系统如何工作和检测到哪些故障。</span><span class="sxs-lookup"><span data-stu-id="29412-114">Once properly configured, OMS parses the JSON payload embedded in the event descriptions to describe how each Skype Room Systems v2 system is functioning and what faults are detected.</span></span> 
  
<span data-ttu-id="29412-115">管理员使用 OMS 可以获取的已处于脱机状态的 Skype 会议室系统 v2 系统通知或是遇到应用程序、 连接或硬件故障，以及了解是否需要重新启动系统。</span><span class="sxs-lookup"><span data-stu-id="29412-115">An administrator using OMS can get notifications of Skype Room Systems v2 systems that are offline or are experiencing app, connectivity, or hardware failures as well as knowing if a system needs to be restarted.</span></span> <span data-ttu-id="29412-116">每个系统状态每五分钟更新一次，因此这些通知接近于实时更新。</span><span class="sxs-lookup"><span data-stu-id="29412-116">Each system status is updated every five minutes, so these notifications are close to real-time updates.</span></span>
  
## <a name="oms-requirements"></a><span data-ttu-id="29412-117">OMS 要求</span><span class="sxs-lookup"><span data-stu-id="29412-117">OMS requirements</span></span>

<span data-ttu-id="29412-118">必须具有 OMS 的有效订阅才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="29412-118">You must have a valid subscription for OMS to use this feature.</span></span> <span data-ttu-id="29412-119">请参阅 [Log Analytics 工作区入门](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started?toc=%2fazure%2foperations-management-suite%2ftoc.json)来为贵组织创建订阅。</span><span class="sxs-lookup"><span data-stu-id="29412-119">See [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started?toc=%2fazure%2foperations-management-suite%2ftoc.json) to create a subscription for your organization.</span></span>
  
<span data-ttu-id="29412-120">如有必要，应尽量使自己熟悉 OMS View Designer 的使用方法。</span><span class="sxs-lookup"><span data-stu-id="29412-120">You should familiarize yourself as necessary on how to use the OMS View Designer.</span></span> <span data-ttu-id="29412-121">有关详细信息，请参阅 [Operations anagement Suite (OMS) 管理解决方案中的视图](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-solutions-resources-views)。</span><span class="sxs-lookup"><span data-stu-id="29412-121">See [Views in Operations Management Suite (OMS) management solutions](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-solutions-resources-views) for those details.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="29412-122">相关任务</span><span class="sxs-lookup"><span data-stu-id="29412-122">Related Tasks</span></span>

1. <span data-ttu-id="29412-123">订阅 OMS 后, 创建自定义字段 （如[映射自定义字段](../../deploy/deploy-clients/with-oms.md#Custom_fields)中所述） 所需分析将从 Skype 会议室系统 v2 控制台发送的信息。</span><span class="sxs-lookup"><span data-stu-id="29412-123">Once subscribed to OMS, create custom fields (as described in [Map custom fields](../../deploy/deploy-clients/with-oms.md#Custom_fields)) needed to parse the information that will be sent from Skype Room Systems v2 consoles.</span></span> <span data-ttu-id="29412-124">这包括了解[了解日志条目](../../manage/skype-room-systems-v2/oms.md#understand-the-log-entries)中记录的 JSON 架构。</span><span class="sxs-lookup"><span data-stu-id="29412-124">This includes understanding the JSON schema documented in [Understand the log entries](../../manage/skype-room-systems-v2/oms.md#understand-the-log-entries).</span></span>
    
2. <span data-ttu-id="29412-125">开发中 OMS 的 Skype 会议室系统 v2 管理视图。</span><span class="sxs-lookup"><span data-stu-id="29412-125">Develop a Skype Room Systems v2 management view in OMS.</span></span> <span data-ttu-id="29412-126">您可以[创建使用的导入方法 Skype 会议室系统 v2 仪表板](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-by-using-the-import-method)任一） 或[手动创建 Skype 会议室系统 v2 仪表板](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-manually)。</span><span class="sxs-lookup"><span data-stu-id="29412-126">You can either [Create a Skype Room Systems v2 dashboard by using the import method](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-by-using-the-import-method) ) or [Create a Skype Room Systems v2 dashboard manually](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-manually).</span></span>
    
## <a name="individual-skype-room-systems-v2-console-requirements"></a><span data-ttu-id="29412-127">单个 Skype 会议室系统 v2 控制台要求</span><span class="sxs-lookup"><span data-stu-id="29412-127">Individual Skype Room Systems v2 Console requirements</span></span>

<span data-ttu-id="29412-128">每个 Skype 会议室系统 v2 控制台是以展台模式面 4 设备上运行的应用程序 （通常，它配置为仅可在设备上运行的应用程序）。</span><span class="sxs-lookup"><span data-stu-id="29412-128">Each Skype Room Systems v2 console is an app running on a Surface 4 device in kiosk mode (normally, it's configured to be the only app that can run on the device).</span></span> <span data-ttu-id="29412-129">与任何 Windows 应用程序，Skype 会议室系统 v2 应用程序到 Windows 事件日志中写入像启动和硬件故障的事件。</span><span class="sxs-lookup"><span data-stu-id="29412-129">As with any Windows app, the Skype Room Systems v2 app writes events like startup and hardware faults to the Windows Event Log.</span></span> <span data-ttu-id="29412-130">添加 Skype 会议室系统 v2 设备上的 OMS 代理允许根据 OMS 将收集这些事件。</span><span class="sxs-lookup"><span data-stu-id="29412-130">Adding an OMS agent on your Skype Room Systems v2 device allows these events to be collected by OMS.</span></span> <span data-ttu-id="29412-131">（请参阅[到 Azure 中的日志分析服务的连接的 Windows 计算机](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)详细信息。）</span><span class="sxs-lookup"><span data-stu-id="29412-131">(See [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents) for details.)</span></span>
  
## <a name="ongoing-management"></a><span data-ttu-id="29412-132">正在进行的管理</span><span class="sxs-lookup"><span data-stu-id="29412-132">Ongoing management</span></span>

<span data-ttu-id="29412-133">同时使用 OMS 管理 Skype 会议室系统 v2 会议设备，您需要了解由 OMS 的事件日志中包含的信息。</span><span class="sxs-lookup"><span data-stu-id="29412-133">While using OMS to manage your Skype Room Systems v2 conference devices, you'll need to understand the information contained in the event logs used by OMS.</span></span> <span data-ttu-id="29412-134">有关这些运行状况消息的详细信息，请参阅[了解日志条目](../../manage/skype-room-systems-v2/oms.md#understand-the-log-entries)。</span><span class="sxs-lookup"><span data-stu-id="29412-134">See [Understand the log entries](../../manage/skype-room-systems-v2/oms.md#understand-the-log-entries) for details on these health messages.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="29412-135">相关任务</span><span class="sxs-lookup"><span data-stu-id="29412-135">Related Tasks</span></span>

- <span data-ttu-id="29412-136">了解通知生成 Skype 会议室系统 v2 以及如何解决这些问题 （请参阅名为[了解日志条目](../../manage/skype-room-systems-v2/oms.md#understand-the-log-entries)的部分）</span><span class="sxs-lookup"><span data-stu-id="29412-136">Understand the Alerts generated by Skype Room Systems v2 and how to resolve them (see the section titled [Understand the log entries](../../manage/skype-room-systems-v2/oms.md#understand-the-log-entries))</span></span>
    
## <a name="see-also"></a><span data-ttu-id="29412-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29412-137">See also</span></span>

[<span data-ttu-id="29412-138">使用 OMS 部署 Skype 会议室系统 v2 管理</span><span class="sxs-lookup"><span data-stu-id="29412-138">Deploy Skype Room Systems v2 management with OMS</span></span>](../../deploy/deploy-clients/with-oms.md)
  
[<span data-ttu-id="29412-139">使用 OMS 管理 Skype 会议室系统 v2 设备</span><span class="sxs-lookup"><span data-stu-id="29412-139">Manage Skype Room Systems v2 devices with OMS</span></span>](../../manage/skype-room-systems-v2/oms.md)