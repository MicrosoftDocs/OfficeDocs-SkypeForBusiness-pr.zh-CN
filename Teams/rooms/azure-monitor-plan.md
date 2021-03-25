---
title: 使用 Azure Monitor 规划 Microsoft Teams 会议室管理
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: 本文讨论在 Skype for Business 或 Teams 实现中使用 Azure Monitor 管理 Microsoft Teams 会议室设备的规划注意事项。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 56b22dddfc475efc83fb5bb3ef5734743b1eb0c9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117580"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a><span data-ttu-id="aa66e-103">使用 Azure Monitor 规划 Microsoft Teams 会议室管理</span><span class="sxs-lookup"><span data-stu-id="aa66e-103">Plan Microsoft Teams Rooms management with Azure Monitor</span></span>
 
 <span data-ttu-id="aa66e-104">本文讨论使用 Azure Monitor 管理 Microsoft Teams 或 Skype for Business 实现中的 Microsoft Teams 会议室设备的规划注意事项。</span><span class="sxs-lookup"><span data-stu-id="aa66e-104">This article discusses planning considerations for using Azure Monitor to administer Microsoft Teams Rooms devices in your Microsoft Teams or Skype for Business implementation.</span></span>
  
<span data-ttu-id="aa66e-105">[Azure Monitor](/azure/azure-monitor/overview) 是一系列从一开始在云中设计的管理服务。</span><span class="sxs-lookup"><span data-stu-id="aa66e-105">[Azure Monitor](/azure/azure-monitor/overview) is a collection of management services that were designed in the cloud from the start.</span></span> <span data-ttu-id="aa66e-106">Azure Monitor 组件完全托管在 Azure 中，而不是部署和管理本地资源。</span><span class="sxs-lookup"><span data-stu-id="aa66e-106">Rather than deploying and managing on-premise resources, Azure Monitor components are entirely hosted in Azure.</span></span> <span data-ttu-id="aa66e-107">只需进行最少的配置，即可在几分钟内开机运行。</span><span class="sxs-lookup"><span data-stu-id="aa66e-107">Configuration is minimal, and you can be up and running literally in a matter of minutes.</span></span> <span data-ttu-id="aa66e-108">通过一些自定义工作，它可以通过为各个会议室系统提供系统运行状况或故障实时通知，帮助管理 Microsoft Teams 会议室会议系统，并且它可能会扩展为管理数千个 Microsoft Teams 会议室。</span><span class="sxs-lookup"><span data-stu-id="aa66e-108">With some customization work, it can aid in managing Microsoft Teams Rooms conferencing systems by providing real-time notifications of system health or faults for individual room systems, and it can potentially scale up to managing thousands of Microsoft Teams Rooms conference rooms.</span></span>
  
<span data-ttu-id="aa66e-109">本文介绍实现基于 Azure Monitor 的 Microsoft Teams 会议室会议设备管理所需的要求、设计/体系结构和实施最佳做法，并提供指向有关实现用于 Microsoft Teams 会议室的 Azure Monitor 的详细文章的链接，以及持续监视 Microsoft Teams 会议室的关键参考信息。</span><span class="sxs-lookup"><span data-stu-id="aa66e-109">This article provides a discussion of the requirements, design/architecture, and implementation best practices needed to implement Azure Monitor based management of Microsoft Teams Rooms conference devices, and provides links to detailed articles on implementing Azure Monitor for Microsoft Teams Rooms and critical reference information for ongoing monitoring of Microsoft Teams Rooms rooms.</span></span> 
  
## <a name="functional-overview"></a><span data-ttu-id="aa66e-110">功能概述</span><span class="sxs-lookup"><span data-stu-id="aa66e-110">Functional overview</span></span>

![使用 Azure Monitor 管理 Microsoft Teams 会议室的示意图](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
<span data-ttu-id="aa66e-112">主机设备上 Microsoft Teams 会议室应用将事件写入其 Windows 事件日志。</span><span class="sxs-lookup"><span data-stu-id="aa66e-112">The Microsoft Teams Rooms app on the console device writes events to its Windows Event Log.</span></span> <span data-ttu-id="aa66e-113">安装 Microsoft Monitoring Agent 后，会将信息传递给 Azure Monitor 服务。</span><span class="sxs-lookup"><span data-stu-id="aa66e-113">A Microsoft Monitoring agent, once installed, passes the information to Azure Monitor service.</span></span> 
  
<span data-ttu-id="aa66e-114">正确配置后，Log Analytics 将分析事件说明中嵌入的 JSON 有效负载，以描述每个 Microsoft Teams 会议室系统如何工作，以及检测到哪些故障。</span><span class="sxs-lookup"><span data-stu-id="aa66e-114">Once properly configured, Log Analytics parses the JSON payload embedded in the event descriptions to describe how each Microsoft Teams Rooms system is functioning and what faults are detected.</span></span> 
  
<span data-ttu-id="aa66e-115">使用 Azure Monitor 的管理员可以接收脱机或遇到应用、连接或硬件故障的 Microsoft Teams 会议室系统的通知，以及知道系统是否需要重新启动。</span><span class="sxs-lookup"><span data-stu-id="aa66e-115">An administrator using Azure Monitor can get notifications of Microsoft Teams Rooms systems that are offline or are experiencing app, connectivity, or hardware failures as well as knowing if a system needs to be restarted.</span></span> <span data-ttu-id="aa66e-116">每个系统状态会经常更新，因此这些通知接近实时更新。</span><span class="sxs-lookup"><span data-stu-id="aa66e-116">Each system status is updated frequently, so these notifications are close to real-time updates.</span></span>
  
## <a name="azure-monitor-requirements"></a><span data-ttu-id="aa66e-117">Azure Monitor 要求</span><span class="sxs-lookup"><span data-stu-id="aa66e-117">Azure Monitor requirements</span></span>

<span data-ttu-id="aa66e-118">必须具有有效的 Azure 订阅，Azure Monitor 才能使用 Log Analytics 功能。</span><span class="sxs-lookup"><span data-stu-id="aa66e-118">You must have a valid Azure subscription for Azure Monitor to use Log Analytics feature.</span></span> <span data-ttu-id="aa66e-119">请参阅 [Log Analytics 工作区入门，](/azure/azure-monitor/learn/quick-create-workspace) 为组织创建订阅。</span><span class="sxs-lookup"><span data-stu-id="aa66e-119">See [Get started with a Log Analytics workspace](/azure/azure-monitor/learn/quick-create-workspace) to create a subscription for your organization.</span></span>
  
<span data-ttu-id="aa66e-120">你应在必要时熟悉如何使用 Log Analytics 视图设计器。</span><span class="sxs-lookup"><span data-stu-id="aa66e-120">You should familiarize yourself as necessary on how to use the Log Analytics View Designer.</span></span> <span data-ttu-id="aa66e-121">有关 [这些详细信息，请参阅 Log Analytics](/azure/azure-monitor/platform/view-designer) 中的视图。</span><span class="sxs-lookup"><span data-stu-id="aa66e-121">See [Views in Log Analytics](/azure/azure-monitor/platform/view-designer) for those details.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="aa66e-122">相关任务</span><span class="sxs-lookup"><span data-stu-id="aa66e-122">Related Tasks</span></span>

1. <span data-ttu-id="aa66e-123">订阅 Azure Monitor Log Analytics 后， (创建自定义 [字段，如](azure-monitor-deploy.md#Custom_fields) 映射自定义字段) 分析从 Microsoft Teams 会议室控制台发送的信息所需。</span><span class="sxs-lookup"><span data-stu-id="aa66e-123">Once subscribed to Azure Monitor Log Analytics, create custom fields (as described in [Map custom fields](azure-monitor-deploy.md#Custom_fields)) needed to parse the information that will be sent from Microsoft Teams Rooms consoles.</span></span> <span data-ttu-id="aa66e-124">这包括了解了解日志条目 中 [介绍的](azure-monitor-manage.md#understand-the-log-entries)JSON 架构。</span><span class="sxs-lookup"><span data-stu-id="aa66e-124">This includes understanding the JSON schema documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span>
    
2. <span data-ttu-id="aa66e-125">在 Log Analytics 中开发 Microsoft Teams 会议室管理视图。</span><span class="sxs-lookup"><span data-stu-id="aa66e-125">Develop a Microsoft Teams Rooms management view in Log Analytics.</span></span> <span data-ttu-id="aa66e-126">可以使用导入 [方法创建 Microsoft Teams 会议室](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) 仪表板或手动创建 [Microsoft Teams 会议室仪表板](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)。</span><span class="sxs-lookup"><span data-stu-id="aa66e-126">You can either [Create a Microsoft Teams Rooms dashboard by using the import method](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) or [Create a Microsoft Teams Rooms dashboard manually](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).</span></span>
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a><span data-ttu-id="aa66e-127">单个 Microsoft Teams 会议室主机要求</span><span class="sxs-lookup"><span data-stu-id="aa66e-127">Individual Microsoft Teams Rooms Console requirements</span></span>

<span data-ttu-id="aa66e-128">每个 Microsoft Teams 会议室控制台都是一个在 Surface Pro 设备上以展台模式运行的应用 (通常配置为可以在设备上运行的唯一) 。</span><span class="sxs-lookup"><span data-stu-id="aa66e-128">Each Microsoft Teams Rooms console is an app running on a Surface Pro device in kiosk mode (normally, it's configured to be the only app that can run on the device).</span></span> <span data-ttu-id="aa66e-129">与任何 Windows 应用一样，Microsoft Teams 会议室应用会将启动和硬件故障等事件写入 Windows 事件日志。</span><span class="sxs-lookup"><span data-stu-id="aa66e-129">As with any Windows app, the Microsoft Teams Rooms app writes events like startup and hardware faults to the Windows Event Log.</span></span> <span data-ttu-id="aa66e-130">在 Microsoft Teams 会议室设备上添加 Microsoft Monitor 代理可以收集这些事件。</span><span class="sxs-lookup"><span data-stu-id="aa66e-130">Adding an Microsoft Monitor agent on your Microsoft Teams Rooms device allows these events to be collected.</span></span> <span data-ttu-id="aa66e-131"> (有关详细信息，请参阅将 [Windows 计算机连接到 Azure](/azure/azure-monitor/platform/agent-windows) 中的 Log Analytics ) </span><span class="sxs-lookup"><span data-stu-id="aa66e-131">(See [Connect Windows computers to the Log Analytics service in Azure](/azure/azure-monitor/platform/agent-windows) for details.)</span></span>
  
## <a name="ongoing-management"></a><span data-ttu-id="aa66e-132">正在进行的管理</span><span class="sxs-lookup"><span data-stu-id="aa66e-132">Ongoing management</span></span>

<span data-ttu-id="aa66e-133">使用 Azure Monitor 管理 Microsoft Teams 会议室设备时，需要了解 Azure Monitor 使用的事件日志中包含的信息。</span><span class="sxs-lookup"><span data-stu-id="aa66e-133">While using Azure Monitor to manage your Microsoft Teams Rooms devices, you'll need to understand the information contained in the event logs used by Azure Monitor.</span></span> <span data-ttu-id="aa66e-134">有关 [这些运行状况消息的详细信息](azure-monitor-manage.md#understand-the-log-entries) ，请参阅了解日志条目。</span><span class="sxs-lookup"><span data-stu-id="aa66e-134">See [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries) for details on these health messages.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="aa66e-135">相关任务</span><span class="sxs-lookup"><span data-stu-id="aa66e-135">Related Tasks</span></span>

- <span data-ttu-id="aa66e-136">了解 Microsoft Teams 会议室生成的警报以及如何解决它们 (请参阅标题为"了解日志条目"部分) [](azure-monitor-manage.md#understand-the-log-entries)</span><span class="sxs-lookup"><span data-stu-id="aa66e-136">Understand the Alerts generated by Microsoft Teams Rooms and how to resolve them (see the section titled [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries))</span></span>
    
## <a name="see-also"></a><span data-ttu-id="aa66e-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa66e-137">See also</span></span>

[<span data-ttu-id="aa66e-138">使用 Azure Monitor 部署 Microsoft Teams 会议室管理</span><span class="sxs-lookup"><span data-stu-id="aa66e-138">Deploy Microsoft Teams Rooms management with Azure Monitor</span></span>](azure-monitor-deploy.md)
  
[<span data-ttu-id="aa66e-139">使用 Azure Monitor 管理 Microsoft Teams 会议室设备</span><span class="sxs-lookup"><span data-stu-id="aa66e-139">Manage Microsoft Teams Rooms devices with Azure Monitor</span></span>](azure-monitor-manage.md)