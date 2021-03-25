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
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>使用 Azure Monitor 规划 Microsoft Teams 会议室管理
 
 本文讨论使用 Azure Monitor 管理 Microsoft Teams 或 Skype for Business 实现中的 Microsoft Teams 会议室设备的规划注意事项。
  
[Azure Monitor](/azure/azure-monitor/overview) 是一系列从一开始在云中设计的管理服务。 Azure Monitor 组件完全托管在 Azure 中，而不是部署和管理本地资源。 只需进行最少的配置，即可在几分钟内开机运行。 通过一些自定义工作，它可以通过为各个会议室系统提供系统运行状况或故障实时通知，帮助管理 Microsoft Teams 会议室会议系统，并且它可能会扩展为管理数千个 Microsoft Teams 会议室。
  
本文介绍实现基于 Azure Monitor 的 Microsoft Teams 会议室会议设备管理所需的要求、设计/体系结构和实施最佳做法，并提供指向有关实现用于 Microsoft Teams 会议室的 Azure Monitor 的详细文章的链接，以及持续监视 Microsoft Teams 会议室的关键参考信息。 
  
## <a name="functional-overview"></a>功能概述

![使用 Azure Monitor 管理 Microsoft Teams 会议室的示意图](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
主机设备上 Microsoft Teams 会议室应用将事件写入其 Windows 事件日志。 安装 Microsoft Monitoring Agent 后，会将信息传递给 Azure Monitor 服务。 
  
正确配置后，Log Analytics 将分析事件说明中嵌入的 JSON 有效负载，以描述每个 Microsoft Teams 会议室系统如何工作，以及检测到哪些故障。 
  
使用 Azure Monitor 的管理员可以接收脱机或遇到应用、连接或硬件故障的 Microsoft Teams 会议室系统的通知，以及知道系统是否需要重新启动。 每个系统状态会经常更新，因此这些通知接近实时更新。
  
## <a name="azure-monitor-requirements"></a>Azure Monitor 要求

必须具有有效的 Azure 订阅，Azure Monitor 才能使用 Log Analytics 功能。 请参阅 [Log Analytics 工作区入门，](/azure/azure-monitor/learn/quick-create-workspace) 为组织创建订阅。
  
你应在必要时熟悉如何使用 Log Analytics 视图设计器。 有关 [这些详细信息，请参阅 Log Analytics](/azure/azure-monitor/platform/view-designer) 中的视图。
  
### <a name="related-tasks"></a>相关任务

1. 订阅 Azure Monitor Log Analytics 后， (创建自定义 [字段，如](azure-monitor-deploy.md#Custom_fields) 映射自定义字段) 分析从 Microsoft Teams 会议室控制台发送的信息所需。 这包括了解了解日志条目 中 [介绍的](azure-monitor-manage.md#understand-the-log-entries)JSON 架构。
    
2. 在 Log Analytics 中开发 Microsoft Teams 会议室管理视图。 可以使用导入 [方法创建 Microsoft Teams 会议室](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method) 仪表板或手动创建 [Microsoft Teams 会议室仪表板](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)。
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>单个 Microsoft Teams 会议室主机要求

每个 Microsoft Teams 会议室控制台都是一个在 Surface Pro 设备上以展台模式运行的应用 (通常配置为可以在设备上运行的唯一) 。 与任何 Windows 应用一样，Microsoft Teams 会议室应用会将启动和硬件故障等事件写入 Windows 事件日志。 在 Microsoft Teams 会议室设备上添加 Microsoft Monitor 代理可以收集这些事件。  (有关详细信息，请参阅将 [Windows 计算机连接到 Azure](/azure/azure-monitor/platform/agent-windows) 中的 Log Analytics ) 
  
## <a name="ongoing-management"></a>正在进行的管理

使用 Azure Monitor 管理 Microsoft Teams 会议室设备时，需要了解 Azure Monitor 使用的事件日志中包含的信息。 有关 [这些运行状况消息的详细信息](azure-monitor-manage.md#understand-the-log-entries) ，请参阅了解日志条目。
  
### <a name="related-tasks"></a>相关任务

- 了解 Microsoft Teams 会议室生成的警报以及如何解决它们 (请参阅标题为"了解日志条目"部分) [](azure-monitor-manage.md#understand-the-log-entries)
    
## <a name="see-also"></a>另请参阅

[使用 Azure Monitor 部署 Microsoft Teams 会议室管理](azure-monitor-deploy.md)
  
[使用 Azure Monitor 管理 Microsoft Teams 会议室设备](azure-monitor-manage.md)