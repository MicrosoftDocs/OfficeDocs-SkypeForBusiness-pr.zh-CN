---
title: 规划 Microsoft 团队聊天室管理使用 Azure 监视器
ms.author: jambirk
author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
ms.collection: M365-voice
description: 本文讨论了使用 Azure 监视器管理在您 Skype 业务或团队实现的 Microsoft 团队聊天室设备的规划注意事项。
ms.openlocfilehash: dfa65435da63eb9783422e1e7ee10e66ba33b891
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012985"
---
# <a name="plan-microsoft-teams-rooms-management-with-azure-monitor"></a>规划 Microsoft 团队聊天室管理使用 Azure 监视器
 
 本文讨论了使用 Azure 监视器管理在您 Skype Business Server 实现的 Microsoft 团队聊天室设备的规划注意事项。
  
[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview)处于旨在从开始在云中的管理服务的集合。 而不是部署和管理内部资源，完全 Azure 中承载 Azure 监视器组件。 只需进行最少的配置，即可在几分钟内开机运行。 具有一些自定义工作，它可帮助管理 Microsoft 团队聊天室会议系统通过为单个会议室系统提供的系统运行状况或错误的实时通知和它可能可扩展到管理数以千计的 Microsoft 团队聊天室会议室。
  
本文讨论的要求、 设计/体系结构和需要实现基于 Azure 监视器管理的 Microsoft 团队聊天室会议设备实现最佳实践，并提供了详细的文章的链接实现 Azure 监视器的 Microsoft 团队聊天室和关键的参考信息的 Microsoft 团队聊天室聊天室的正在进行监控。 
  
## <a name="functional-overview"></a>功能概述

![使用 Azure 监视器的 Microsoft 团队聊天室管理的关系图](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
控制台设备上的 Microsoft 团队聊天室应用程序将事件写入到其 Windows 事件日志。 Microsoft 监控代理，安装后，会将信息传递到 Azure 监视器服务。 
  
一次正确配置，日志分析分析 JSON 负载事件中嵌入说明来描述每个聊天室 Microsoft 团队系统如何工作和检测到哪些故障。 
  
使用 Azure 监视器管理员可以获取的已处于脱机状态的 Microsoft 团队聊天室系统通知或是遇到应用程序、 连接或硬件故障，以及了解是否需要重新启动系统。 每个系统状态是频繁更新，因此这些通知接近实时更新。
  
## <a name="azure-monitor-requirements"></a>Azure 监视器要求

您必须具有有效的 Azure 订阅 Azure 监视程序才能使用日志分析功能。 请参阅[开始使用日志分析工作区](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)创建您的组织订阅。
  
您应熟悉根据需要有关如何使用日志分析视图设计器。 有关详细信息，请参阅[日志分析中的视图](https://docs.microsoft.com/azure/azure-monitor/platform/view-designer)。
  
### <a name="related-tasks"></a>相关任务

1. 订阅 Azure 监视器日志分析后, 创建自定义字段 （如[映射自定义字段](../../deploy/deploy-clients/azure-monitor.md#Custom_fields)中所述） 所需分析来自 Microsoft 团队聊天室控制台的信息。 这包括了解[了解日志条目](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries)中记录的 JSON 架构。
    
2. 开发日志分析中的 Microsoft 团队聊天室管理视图。 您可以[创建 Microsoft 团队聊天室仪表板使用的导入方法](../../deploy/deploy-clients/azure-monitor.md#create-a-microsoft-teams-rooms-dashboard-by-using-the-import-method)或[手动创建 Microsoft 团队聊天室仪表板](../../deploy/deploy-clients/azure-monitor.md#create-a-microsoft-teams-rooms-dashboard-manually)。
    
## <a name="individual-microsoft-teams-rooms-console-requirements"></a>单个 Microsoft 团队聊天室控制台要求

每个 Microsoft 团队聊天室控制台是以展台模式 Surface Pro 设备上运行的应用程序 （通常，它配置为仅可在设备上运行的应用程序）。 与任何 Windows 应用程序中，Microsoft 团队聊天室应用程序到 Windows 事件日志中写入像启动和硬件故障的事件。 添加了 Microsoft 监视器代理 Microsoft 团队聊天室设备上允许待收集这些事件。 （请参阅[到 Azure 中的日志分析服务的连接的 Windows 计算机](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows)详细信息。）
  
## <a name="ongoing-management"></a>正在进行的管理

同时使用 Azure 监视器来管理您的 Microsoft 团队聊天室设备，您需要了解 Azure 监视器使用事件日志中包含的信息。 有关这些运行状况消息的详细信息，请参阅[了解日志条目](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries)。
  
### <a name="related-tasks"></a>相关任务

- 了解由 Microsoft 团队聊天室以及如何解决这些问题 （请参阅名为[了解日志条目](../../manage/skype-room-systems-v2/azure-monitor.md#understand-the-log-entries)的部分） 生成的警报
    
## <a name="see-also"></a>另请参阅

[部署 Microsoft 团队聊天室管理使用 Azure 监视器](../../deploy/deploy-clients/azure-monitor.md)
  
[管理使用 Azure 监视器的 Microsoft 团队聊天室设备](../../manage/skype-room-systems-v2/azure-monitor.md)