---
title: 规划Microsoft Teams 会议室 Azure Monitor 进行监视
ms.author: dstrome
author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection:
- M365-collaboration
description: 本文讨论使用 Azure Monitor 来监视Microsoft Teams 会议室或Skype for Business实现Teams注意事项。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 13c16234773792f9dc394723521224123c5e2141
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015202"
---
# <a name="plan-microsoft-teams-rooms-monitoring-with-azure-monitor"></a>规划Microsoft Teams 会议室 Azure Monitor 进行监视
 
 本文讨论使用 Azure Monitor 管理 Microsoft Teams 会议室 或 Skype for Business 实现中的Microsoft Teams注意事项。

> [!NOTE]
> 也可使用[管理中心设置](../alerts/device-health-status.md)Teams 会议室运行状况Teams监视。

[Azure Monitor](/azure/azure-monitor/overview) 是一系列从一开始在云中设计的监视服务。 Azure Monitor 组件完全托管在 Azure 中，而不是部署和管理本地资源。 配置极少，只需几分钟即可启动并运行。 通过一些自定义工作，它Microsoft Teams 会议室针对单个房间系统提供系统运行状况或故障通知，帮助监视数据，并可以扩展为管理数千个Microsoft Teams 会议室。
  
本文介绍实现基于 Azure Monitor 的监视环境所需的要求、设计/体系结构和Microsoft Teams 会议室。 它还提供了有关实现 Azure Monitor for Microsoft Teams 会议室 以及持续监视聊天室的关键参考信息的详细Microsoft Teams 会议室链接。
  
## <a name="functional-overview"></a>功能概述

![使用 Azure Monitor Microsoft Teams 会议室管理图表。](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
应用Microsoft Teams 会议室事件写入事件日志Windows日志。 安装 Microsoft Monitoring Agent 后，会将信息传递给 Azure Monitor 服务。
  
正确配置后，Log Analytics 将分析事件说明中嵌入的 JSON 有效负载，Microsoft Teams 会议室运行方式以及检测到哪些故障。
  
使用 Azure Monitor 的管理员Microsoft Teams 会议室处于脱机状态或遇到应用、连接或硬件故障，以及知道系统是否需要重启的通知。 每个系统状态会经常更新，因此这些通知接近实时更新。
  
## <a name="azure-monitor-requirements"></a>Azure Monitor 要求

必须具有有效的 Azure 订阅才能使用 Log Analytics 功能。 请参阅 [Log Analytics 工作区入门，](/azure/azure-monitor/learn/quick-create-workspace) 为组织创建订阅。
  
应该熟悉如何使用 Log Analytics 视图设计器。 有关 [这些详细信息，请参阅 Log Analytics](/azure/azure-monitor/platform/view-designer) 中的视图。
  
### <a name="related-tasks"></a>相关任务

1. 订阅 Azure Monitor Log Analytics 后， (创建自定义字段，如映射[](azure-monitor-deploy.md#Custom_fields)自定义字段) 分析从 Microsoft Teams 会议室 发送的信息所需的字段。 这包括了解了解日志条目 中 [介绍的](azure-monitor-manage.md#understand-the-log-entries)JSON 架构。
    
2. 在 Log Analytics Microsoft Teams 会议室管理视图。 可以[手动创建Microsoft Teams 会议室仪表板。](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)
    
## <a name="individual-microsoft-teams-rooms-requirements"></a>单个Microsoft Teams 会议室要求

Microsoft Teams 会议室是在展台模式下在计算设备上运行的应用。 与任何Windows一样，Microsoft Teams 会议室会将启动和硬件故障等事件写入Windows日志。 在客户端上添加 Microsoft Monitor Microsoft Teams 会议室可以收集这些事件。  (请参阅[连接 Windows计算机到 Azure 中的 Log Analytics](/azure/azure-monitor/platform/agent-windows)服务了解详细信息。) 
  
## <a name="ongoing-management"></a>正在进行的管理

使用 Azure Monitor 监视Microsoft Teams 会议室时，需要了解 Azure Monitor 使用的事件日志中包含的信息。 有关 [这些运行状况消息的详细信息](azure-monitor-manage.md#understand-the-log-entries) ，请参阅了解日志条目。
  
### <a name="related-tasks"></a>相关任务

- 了解警报生成的警报Microsoft Teams 会议室如何解决它们 (请参阅标题为"了解日志条目) [](azure-monitor-manage.md#understand-the-log-entries)
    
## <a name="see-also"></a>另请参阅

[使用 Azure Monitor Microsoft Teams 会议室管理](azure-monitor-deploy.md)
  
[使用 Azure Monitor Microsoft Teams 会议室设备](azure-monitor-manage.md)
