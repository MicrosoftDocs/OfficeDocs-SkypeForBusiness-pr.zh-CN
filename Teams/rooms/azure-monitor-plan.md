---
title: 使用 Azure Monitor 规划Microsoft Teams 会议室监视
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
- Teams_ITAdmin_Rooms
description: 本文讨论使用 Azure Monitor 监视Skype for Business或 Teams 实现中的Microsoft Teams 会议室的规划注意事项。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac3ac3af4e4f162238af0e9bf38c45569302fdfb
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269567"
---
# <a name="plan-microsoft-teams-rooms-monitoring-with-azure-monitor"></a>使用 Azure Monitor 规划Microsoft Teams 会议室监视
 
 本文讨论使用 Azure Monitor 管理 Microsoft Teams 中的Microsoft Teams 会议室设备或Skype for Business实现的规划注意事项。

> [!NOTE]
> 还可以使用 Teams 管理中心[设置Teams 会议室运行状况监视](../alerts/device-health-status.md)。

[Azure Monitor](/azure/azure-monitor/overview) 是从一开始就在云中设计的监视服务的集合。 Azure Monitor 组件完全托管在 Azure 中，而不是部署和管理本地资源。 配置最少，可以在几分钟内启动并运行。 通过一些自定义工作，它可以通过为各个会议室系统提供系统运行状况或故障通知来帮助监视Microsoft Teams 会议室，并且它可以扩展到管理数千个Microsoft Teams 会议室。
  
本文介绍实现基于 Azure Monitor 的Microsoft Teams 会议室监视所需的要求、设计/体系结构和实现最佳做法。 它还提供了有关实现用于Microsoft Teams 会议室的 Azure Monitor 的详细文章的链接，以及持续监视Microsoft Teams 会议室会议室的关键参考信息。
  
## <a name="functional-overview"></a>功能概述

![使用 Azure Monitor 进行Microsoft Teams 会议室管理的示意图。](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
Microsoft Teams 会议室应用将事件写入 Windows 事件日志。 安装后，Microsoft Monitoring 代理会将信息传递给 Azure Monitor 服务。
  
正确配置后，Log Analytics 会分析事件说明中嵌入的 JSON 有效负载，以描述Microsoft Teams 会议室的工作原理以及检测到哪些错误。
  
使用 Azure Monitor 的管理员可以获取脱机或遇到应用、连接或硬件故障的Microsoft Teams 会议室的通知，并知道是否需要重启系统。 每个系统状态都会频繁更新，因此这些通知接近实时更新。
  
## <a name="azure-monitor-requirements"></a>Azure Monitor 要求

必须拥有有效的 Azure 订阅才能使用 Log Analytics 功能。 请参阅 [Log Analytics 工作区入](/azure/azure-monitor/learn/quick-create-workspace) 门，为组织创建订阅。
  
应熟悉如何使用 Log Analytics 视图设计器。 有关这些详细信息 [，请参阅 Log Analytics 中的视图](/azure/azure-monitor/platform/view-designer) 。
  
### <a name="related-tasks"></a>相关任务

1. 订阅 Azure Monitor Log Analytics 后，根据[映射自定义字段](azure-monitor-deploy.md#Custom_fields)中所述创建自定义字段 () 分析将从Microsoft Teams 会议室发送的信息所需。 这包括了解在 [“了解日志条目](azure-monitor-manage.md#understand-the-log-entries)”中记录的 JSON 架构。
    
2. 在 Log Analytics 中开发Microsoft Teams 会议室管理视图。 可以[手动创建Microsoft Teams 会议室仪表板](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)。
    
## <a name="individual-microsoft-teams-rooms-requirements"></a>单个Microsoft Teams 会议室要求

Microsoft Teams 会议室是在展台模式下的计算设备上运行的应用。 与任何 Windows 应用一样，Microsoft Teams 会议室应用会将启动和硬件故障等事件写入 Windows 事件日志。 在 Microsoft Teams 会议室 上添加 Microsoft Monitor 代理可收集这些事件。  (有关详细信息，请参阅 [将 Windows 计算机连接到 Azure 中的 Log Analytics 服务](/azure/azure-monitor/platform/agent-windows) 。) 
  
## <a name="ongoing-management"></a>正在进行的管理

使用 Azure Monitor 监视Microsoft Teams 会议室时，需要了解 Azure Monitor 使用的事件日志中包含的信息。 有关这些运行状况消息的详细信息，请参阅 [“了解日志条目](azure-monitor-manage.md#understand-the-log-entries) ”。
  
### <a name="related-tasks"></a>相关任务

- 了解Microsoft Teams 会议室生成的警报以及如何解决它们 (请参阅标题为[“了解日志条目](azure-monitor-manage.md#understand-the-log-entries)) 
    
## <a name="see-also"></a>另请参阅

[使用 Azure Monitor 部署Microsoft Teams 会议室管理](azure-monitor-deploy.md)
  
[使用 Azure Monitor 管理Microsoft Teams 会议室设备](azure-monitor-manage.md)
