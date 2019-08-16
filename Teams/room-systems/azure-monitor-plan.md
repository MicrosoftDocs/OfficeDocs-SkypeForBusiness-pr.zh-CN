---
title: 通过 Azure 监视器规划 Microsoft 团队聊天室管理
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection: M365-voice
description: 本文介绍使用 Azure 监视器管理 Skype for Business 或团队实现中的 Microsoft 团队聊天室设备时的规划注意事项。
ms.openlocfilehash: bdd028417ff8234a10173de7b5512faff8455629
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "36428085"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>通过 Azure 监视器规划 Microsoft 团队聊天室管理
 
 本文介绍使用 Azure 监视器管理 Microsoft 团队或 Skype for Business 实施中的 Microsoft 团队聊天室设备时的规划注意事项。
  
[Azure 监视器](https://docs.microsoft.com/azure/azure-monitor/overview)是从开始就在云中设计的管理服务的集合。 Azure 监视器组件完全托管在 Azure 中, 而不是部署和管理本地资源。 只需进行最少的配置，即可在几分钟内开机运行。 有了一些自定义工作, 它可以帮助管理 Microsoft 团队会议室会议系统, 方法是为单个房间系统提供系统运行状况或故障的实时通知, 并且可能会扩展到管理数以千计的 Microsoft 团队会议室会议室。
  
本文提供了有关实现 Microsoft 团队聊天室会议设备的基于 Azure 监视器的管理所需的要求、设计/体系结构和实施最佳做法的讨论, 并提供了有关的详细文章的链接为 Microsoft 团队聊天室实施 Azure 监视器和关键参考信息, 以便对 Microsoft 团队会议室的持续监控。 
  
## <a name="functional-overview"></a>功能概述

![使用 Azure 监视器的 Microsoft 团队聊天室管理图](../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
控制台设备上的 Microsoft 团队聊天室应用将事件写入其 Windows 事件日志。 Microsoft Monitoring agent 一经安装, 便会将信息传递给 Azure 监视器服务。 
  
配置正确后, 日志分析将分析事件描述中嵌入的 JSON 负载, 以描述每个 Microsoft 团队聊天室系统的工作方式以及检测到的错误。 
  
使用 Azure 监视器的管理员可以获取脱机或遇到应用、连接或硬件故障以及知道系统是否需要重新启动的 Microsoft 团队聊天室系统的通知。 每个系统状态都会频繁更新, 因此这些通知接近于实时更新。
  
## <a name="azure-monitor-requirements"></a>Azure 监视器要求

你必须具有有效的 Azure 监视器 Azure 订阅才能使用日志分析功能。 请参阅[开始使用 Log Analytics 工作区](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)来为你的组织创建订阅。
  
你应根据需要熟悉如何使用 Log Analytics 视图设计器。 有关这些详细信息, 请参阅[日志分析中的视图](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)。
  
### <a name="related-tasks"></a>相关任务

1. 订阅 Azure 监视器日志分析后, 创建自定义字段 (如[映射自定义字段](azure-monitor-deploy.md#Custom_fields)中所述), 以分析将从 Microsoft 团队聊天室控制台发送的信息。 这包括理解[日志条目](azure-monitor-manage.md#understand-the-log-entries)中记录的 JSON 架构。
    
2. 在日志分析中开发 Microsoft 团队聊天室管理视图。 你可以通过使用 import 方法或[手动创建 Microsoft 团队聊天室仪表板](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-manually)[来创建 microsoft 团队聊天室仪表板](azure-monitor-deploy.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method)。
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>单个 Microsoft 团队聊天室的控制台要求

每个 Microsoft 团队聊天室控制台都是在展台模式下 (通常情况下, 配置为可以在设备上运行的唯一应用) 在 Surface Pro 设备上运行的应用。 与任何 Windows 应用一样, Microsoft 团队聊天室应用会将启动和硬件故障之类的事件写入 Windows 事件日志。 在 Microsoft 团队聊天室设备上添加 Microsoft 监视器代理后, 即可收集这些事件。 (有关详细信息, 请参阅[将 Windows 计算机连接到 Azure 中的日志分析服务](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)。)
  
## <a name="ongoing-management"></a>正在进行的管理

使用 Azure 监视器管理 Microsoft 团队聊天室设备时, 你需要了解 Azure 监视器使用的事件日志中包含的信息。 有关这些运行状况消息的详细信息, 请参阅[了解日志条目](azure-monitor-manage.md#understand-the-log-entries)。
  
### <a name="related-tasks"></a>相关任务

- 了解 Microsoft 团队聊天室生成的通知以及如何解决它们 (请参阅标题为[了解日志条目](azure-monitor-manage.md#understand-the-log-entries)的部分)
    
## <a name="see-also"></a>另请参阅

[通过 Azure 监视器部署 Microsoft 团队聊天室管理](azure-monitor-deploy.md)
  
[通过 Azure 监视器管理 Microsoft 团队聊天室设备](azure-monitor-manage.md)