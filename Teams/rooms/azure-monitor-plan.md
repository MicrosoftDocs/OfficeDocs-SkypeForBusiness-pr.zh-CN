---
title: 使用 Azure Monitor Microsoft Teams 会议室计划管理
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
description: 本文讨论使用 Azure Monitor 管理 Microsoft Teams 会议室 或 Skype for Business 或 Teams 设备的规划注意事项。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1cd848b6ccf963e7b21083ac65c0332f74542967
ms.sourcegitcommit: 81f1a113a33c7ea8d2256144544d0e34cd64d576
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2021
ms.locfileid: "58505410"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>使用 Azure Monitor Microsoft Teams 会议室计划管理
 
 本文讨论使用 Azure Monitor 管理Microsoft Teams 会议室或云Microsoft Teams中的Skype for Business注意事项。
  
[Azure Monitor](/azure/azure-monitor/overview) 是一系列从一开始在云中设计的管理服务。 Azure Monitor 组件完全托管在 Azure 中，而不是部署和管理本地资源。 只需进行最少的配置，即可在几分钟内开机运行。 通过一些自定义工作，它可以通过为各个会议室系统提供系统运行状况或故障实时通知，帮助管理 Microsoft Teams 会议室 会议系统，并且它可能会扩展为管理数千个 Microsoft Teams 会议室 会议室。
  
本文介绍实现基于 Azure Monitor 的 Microsoft Teams 会议室 会议设备管理所需的要求、设计/体系结构和实施最佳做法，并提供指向有关实现适用于 Microsoft Teams 会议室 的 Azure Monitor 的详细文章的链接，以及用于持续监视 Microsoft Teams 会议室 会议室的关键参考信息。 
  
## <a name="functional-overview"></a>功能概述

![使用 Azure monitor Microsoft Teams 会议室管理图表](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
主机Microsoft Teams 会议室应用将事件写入其事件Windows日志。 安装 Microsoft Monitoring Agent 后，会将信息传递给 Azure Monitor 服务。 
  
正确配置后，Log Analytics 将分析事件说明中嵌入的 JSON 有效负载，Microsoft Teams 会议室系统的运行方式以及检测到哪些故障。 
  
使用 Azure Monitor 的管理员可以Microsoft Teams 会议室处于脱机状态或遇到应用、连接或硬件故障的系统的通知，并知道系统是否需要重启。 每个系统状态会经常更新，因此这些通知接近实时更新。
  
## <a name="azure-monitor-requirements"></a>Azure Monitor 要求

必须具有有效的 Azure 订阅，Azure Monitor 才能使用 Log Analytics 功能。 请参阅 [Log Analytics 工作区入门，](/azure/azure-monitor/learn/quick-create-workspace) 为组织创建订阅。
  
你应在必要时熟悉如何使用 Log Analytics 视图设计器。 有关 [这些详细信息，请参阅 Log Analytics](/azure/azure-monitor/platform/view-designer) 中的视图。
  
### <a name="related-tasks"></a>相关任务

1. 订阅 Azure Monitor Log Analytics 后， (创建自定义字段，如映射自定义字段[) 分析](azure-monitor-deploy.md#Custom_fields)从 Microsoft Teams 会议室 控制台发送的信息所需的字段。 这包括了解了解日志条目 中 [介绍的](azure-monitor-manage.md#understand-the-log-entries)JSON 架构。
    
2. 在 Log Analytics Microsoft Teams 会议室管理视图。 可以[手动创建Microsoft Teams 会议室仪表板。](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>单个Microsoft Teams 会议室主机要求

每个 Microsoft Teams 会议室 主机都是一个在 Surface Pro 设备上以展台模式运行的应用 (通常配置为可以在设备上运行的唯一) 。 与任何Windows一样，Microsoft Teams 会议室应用会将启动和硬件故障等事件写入Windows日志。 在设备上添加 Microsoft Monitor Microsoft Teams 会议室可以收集这些事件。  (请参阅连接 Windows [Azure 中的 Log Analytics](/azure/azure-monitor/platform/agent-windows)服务获取详细信息。) 
  
## <a name="ongoing-management"></a>正在进行的管理

使用 Azure Monitor 管理Microsoft Teams 会议室时，需要了解 Azure Monitor 使用的事件日志中包含的信息。 有关 [这些运行状况消息的详细信息](azure-monitor-manage.md#understand-the-log-entries) ，请参阅了解日志条目。
  
### <a name="related-tasks"></a>相关任务

- 请参阅标题为"了解Microsoft Teams 会议室日志条目"部分 (警报及其) [](azure-monitor-manage.md#understand-the-log-entries)
    
## <a name="see-also"></a>另请参阅

[使用 Azure monitor Microsoft Teams 会议室管理](azure-monitor-deploy.md)
  
[使用 Azure Monitor Microsoft Teams 会议室设备](azure-monitor-manage.md)
