---
title: 通过 Azure 监视器规划 Microsoft 团队聊天室管理
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: 本文介绍使用 Azure 监视器管理 Skype for Business 或团队实现中的 Microsoft 团队聊天室设备时的规划注意事项。
ms.openlocfilehash: 1e5c41866b02a74bee06b472623919f955691dd9
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675780"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a><span data-ttu-id="4ed21-103">通过 Azure 监视器规划 Microsoft 团队聊天室管理</span><span class="sxs-lookup"><span data-stu-id="4ed21-103">Plan Microsoft Teams Rooms management with Azure Monitor</span></span>
 
 <span data-ttu-id="4ed21-104">本文介绍使用 Azure 监视器管理 Microsoft 团队或 Skype for Business 实施中的 Microsoft 团队聊天室设备时的规划注意事项。</span><span class="sxs-lookup"><span data-stu-id="4ed21-104">This article discusses planning considerations for using Azure Monitor to administer Microsoft Teams Rooms devices in your Microsoft Teams or Skype for Business implementation.</span></span>
  
<span data-ttu-id="4ed21-105">[Azure 监视器](https://docs.microsoft.com/azure/azure-monitor/overview)是从开始就在云中设计的管理服务的集合。</span><span class="sxs-lookup"><span data-stu-id="4ed21-105">[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) is a collection of management services that were designed in the cloud from the start.</span></span> <span data-ttu-id="4ed21-106">Azure 监视器组件完全托管在 Azure 中，而不是部署和管理本地资源。</span><span class="sxs-lookup"><span data-stu-id="4ed21-106">Rather than deploying and managing on-premise resources, Azure Monitor components are entirely hosted in Azure.</span></span> <span data-ttu-id="4ed21-107">只需进行最少的配置，即可在几分钟内开机运行。</span><span class="sxs-lookup"><span data-stu-id="4ed21-107">Configuration is minimal, and you can be up and running literally in a matter of minutes.</span></span> <span data-ttu-id="4ed21-108">有了一些自定义工作，它可以帮助管理 Microsoft 团队会议室会议系统，方法是为单个房间系统提供系统运行状况或故障的实时通知，并且可能会扩展到管理数以千计的 Microsoft 团队会议室会议室。</span><span class="sxs-lookup"><span data-stu-id="4ed21-108">With some customization work, it can aid in managing Microsoft Teams Rooms conferencing systems by providing real-time notifications of system health or faults for individual room systems, and it can potentially scale up to managing thousands of Microsoft Teams Rooms conference rooms.</span></span>
  
<span data-ttu-id="4ed21-109">本文提供了有关实现 Microsoft 团队聊天室会议设备的基于 Azure 监视器的管理所需的要求、设计/体系结构和实施最佳做法的讨论，并提供了有关为 microsoft 团队聊天室实施 Azure 监视器的详细文章的链接，以及有关实时监视 Microsoft 团队会议室的关键参考信息。</span><span class="sxs-lookup"><span data-stu-id="4ed21-109">This article provides a discussion of the requirements, design/architecture, and implementation best practices needed to implement Azure Monitor based management of Microsoft Teams Rooms conference devices, and provides links to detailed articles on implementing Azure Monitor for Microsoft Teams Rooms and critical reference information for ongoing monitoring of Microsoft Teams Rooms rooms.</span></span> 
  
## <a name="functional-overview"></a><span data-ttu-id="4ed21-110">功能概述</span><span class="sxs-lookup"><span data-stu-id="4ed21-110">Functional overview</span></span>

![使用 Azure 监视器的 Microsoft 团队聊天室管理图](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
<span data-ttu-id="4ed21-112">控制台设备上的 Microsoft 团队聊天室应用将事件写入其 Windows 事件日志。</span><span class="sxs-lookup"><span data-stu-id="4ed21-112">The Microsoft Teams Rooms app on the console device writes events to its Windows Event Log.</span></span> <span data-ttu-id="4ed21-113">Microsoft Monitoring agent 一经安装，便会将信息传递给 Azure 监视器服务。</span><span class="sxs-lookup"><span data-stu-id="4ed21-113">A Microsoft Monitoring agent, once installed, passes the information to Azure Monitor service.</span></span> 
  
<span data-ttu-id="4ed21-114">配置正确后，日志分析将分析事件描述中嵌入的 JSON 负载，以描述每个 Microsoft 团队聊天室系统的工作方式以及检测到的错误。</span><span class="sxs-lookup"><span data-stu-id="4ed21-114">Once properly configured, Log Analytics parses the JSON payload embedded in the event descriptions to describe how each Microsoft Teams Rooms system is functioning and what faults are detected.</span></span> 
  
<span data-ttu-id="4ed21-115">使用 Azure 监视器的管理员可以获取脱机或遇到应用、连接或硬件故障以及知道系统是否需要重新启动的 Microsoft 团队聊天室系统的通知。</span><span class="sxs-lookup"><span data-stu-id="4ed21-115">An administrator using Azure Monitor can get notifications of Microsoft Teams Rooms systems that are offline or are experiencing app, connectivity, or hardware failures as well as knowing if a system needs to be restarted.</span></span> <span data-ttu-id="4ed21-116">每个系统状态都会频繁更新，因此这些通知接近于实时更新。</span><span class="sxs-lookup"><span data-stu-id="4ed21-116">Each system status is updated frequently, so these notifications are close to real-time updates.</span></span>
  
## <a name="azure-monitor-requirements"></a><span data-ttu-id="4ed21-117">Azure 监视器要求</span><span class="sxs-lookup"><span data-stu-id="4ed21-117">Azure Monitor requirements</span></span>

<span data-ttu-id="4ed21-118">你必须具有有效的 Azure 监视器 Azure 订阅才能使用日志分析功能。</span><span class="sxs-lookup"><span data-stu-id="4ed21-118">You must have a valid Azure subscription for Azure Monitor to use Log Analytics feature.</span></span> <span data-ttu-id="4ed21-119">请参阅[开始使用 Log Analytics 工作区](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)来为你的组织创建订阅。</span><span class="sxs-lookup"><span data-stu-id="4ed21-119">See [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) to create a subscription for your organization.</span></span>
  
<span data-ttu-id="4ed21-120">你应根据需要熟悉如何使用 Log Analytics 视图设计器。</span><span class="sxs-lookup"><span data-stu-id="4ed21-120">You should familiarize yourself as necessary on how to use the Log Analytics View Designer.</span></span> <span data-ttu-id="4ed21-121">有关这些详细信息，请参阅[日志分析中的视图](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)。</span><span class="sxs-lookup"><span data-stu-id="4ed21-121">See [Views in Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer) for those details.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="4ed21-122">相关任务</span><span class="sxs-lookup"><span data-stu-id="4ed21-122">Related Tasks</span></span>

1. <span data-ttu-id="4ed21-123">订阅 Azure 监视器日志分析后，创建自定义字段（如[映射自定义字段](azure-monitor-deploy.md#Custom_fields)中所述），以分析将从 Microsoft 团队聊天室控制台发送的信息。</span><span class="sxs-lookup"><span data-stu-id="4ed21-123">Once subscribed to Azure Monitor Log Analytics, create custom fields (as described in [Map custom fields](azure-monitor-deploy.md#Custom_fields)) needed to parse the information that will be sent from Microsoft Teams Rooms consoles.</span></span> <span data-ttu-id="4ed21-124">这包括理解[日志条目](azure-monitor-manage.md#understand-the-log-entries)中记录的 JSON 架构。</span><span class="sxs-lookup"><span data-stu-id="4ed21-124">This includes understanding the JSON schema documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span>
    
2. <span data-ttu-id="4ed21-125">在日志分析中开发 Microsoft 团队聊天室管理视图。</span><span class="sxs-lookup"><span data-stu-id="4ed21-125">Develop a Microsoft Teams Rooms management view in Log Analytics.</span></span> <span data-ttu-id="4ed21-126">你可以通过使用 import 方法或[手动创建 Microsoft 团队聊天室仪表板](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)[来创建 microsoft 团队聊天室仪表板](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method)。</span><span class="sxs-lookup"><span data-stu-id="4ed21-126">You can either [Create a Microsoft Teams Rooms dashboard by using the import method](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) or [Create a Microsoft Teams Rooms dashboard manually](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually).</span></span>
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a><span data-ttu-id="4ed21-127">单个 Microsoft 团队聊天室的控制台要求</span><span class="sxs-lookup"><span data-stu-id="4ed21-127">Individual Microsoft Teams Rooms Console requirements</span></span>

<span data-ttu-id="4ed21-128">每个 Microsoft 团队聊天室控制台都是在展台模式下（通常情况下，配置为可以在设备上运行的唯一应用）在 Surface Pro 设备上运行的应用。</span><span class="sxs-lookup"><span data-stu-id="4ed21-128">Each Microsoft Teams Rooms console is an app running on a Surface Pro device in kiosk mode (normally, it's configured to be the only app that can run on the device).</span></span> <span data-ttu-id="4ed21-129">与任何 Windows 应用一样，Microsoft 团队聊天室应用会将启动和硬件故障之类的事件写入 Windows 事件日志。</span><span class="sxs-lookup"><span data-stu-id="4ed21-129">As with any Windows app, the Microsoft Teams Rooms app writes events like startup and hardware faults to the Windows Event Log.</span></span> <span data-ttu-id="4ed21-130">在 Microsoft 团队聊天室设备上添加 Microsoft 监视器代理后，即可收集这些事件。</span><span class="sxs-lookup"><span data-stu-id="4ed21-130">Adding an Microsoft Monitor agent on your Microsoft Teams Rooms device allows these events to be collected.</span></span> <span data-ttu-id="4ed21-131">（有关详细信息，请参阅[将 Windows 计算机连接到 Azure 中的日志分析服务](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)。）</span><span class="sxs-lookup"><span data-stu-id="4ed21-131">(See [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows) for details.)</span></span>
  
## <a name="ongoing-management"></a><span data-ttu-id="4ed21-132">正在进行的管理</span><span class="sxs-lookup"><span data-stu-id="4ed21-132">Ongoing management</span></span>

<span data-ttu-id="4ed21-133">使用 Azure 监视器管理 Microsoft 团队聊天室设备时，你需要了解 Azure 监视器使用的事件日志中包含的信息。</span><span class="sxs-lookup"><span data-stu-id="4ed21-133">While using Azure Monitor to manage your Microsoft Teams Rooms devices, you'll need to understand the information contained in the event logs used by Azure Monitor.</span></span> <span data-ttu-id="4ed21-134">有关这些运行状况消息的详细信息，请参阅[了解日志条目](azure-monitor-manage.md#understand-the-log-entries)。</span><span class="sxs-lookup"><span data-stu-id="4ed21-134">See [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries) for details on these health messages.</span></span>
  
### <a name="related-tasks"></a><span data-ttu-id="4ed21-135">相关任务</span><span class="sxs-lookup"><span data-stu-id="4ed21-135">Related Tasks</span></span>

- <span data-ttu-id="4ed21-136">了解 Microsoft 团队聊天室生成的通知以及如何解决它们（请参阅标题为[了解日志条目](azure-monitor-manage.md#understand-the-log-entries)的部分）</span><span class="sxs-lookup"><span data-stu-id="4ed21-136">Understand the Alerts generated by Microsoft Teams Rooms and how to resolve them (see the section titled [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries))</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4ed21-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ed21-137">See also</span></span>

[<span data-ttu-id="4ed21-138">通过 Azure 监视器部署 Microsoft 团队聊天室管理</span><span class="sxs-lookup"><span data-stu-id="4ed21-138">Deploy Microsoft Teams Rooms management with Azure Monitor</span></span>](azure-monitor-deploy.md)
  
[<span data-ttu-id="4ed21-139">通过 Azure 监视器管理 Microsoft 团队聊天室设备</span><span class="sxs-lookup"><span data-stu-id="4ed21-139">Manage Microsoft Teams Rooms devices with Azure Monitor</span></span>](azure-monitor-manage.md)