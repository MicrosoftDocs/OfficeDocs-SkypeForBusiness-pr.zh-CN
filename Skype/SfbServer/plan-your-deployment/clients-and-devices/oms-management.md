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
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839355"
---
# <a name="plan-skype-room-systems-v2-management-with-oms"></a>使用 OMS 规划 Skype 会议室系统 v2 管理
 
 本文讨论使用操作管理套件管理 Skype 会议室系统 v2 设备中您 Skype 业务服务器实现的规划注意事项。
  
[操作管理套件](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)(OMS) 是旨在从开始在云中的管理服务的集合。 OMS 组件并不部署和管理本地资源，而是完全托管在 Azure 中。 只需进行最少的配置，即可在几分钟内开机运行。 具有一些自定义工作，有助于在通过为单个会议室系统提供的系统运行状况或错误的实时通知管理 Skype 会议室系统 v2 会议系统和它可能可扩展到数千个 Skype 会议室系统管理v2 会议室。
  
本文讨论的要求、 设计/体系结构和实现最佳实践需要实现 OMS 管理 Skype 会议室系统 v2 会议设备，并实现 OMS 提供详细的文章的链接Skype 会议室系统 v2 和关键的参考信息的持续 OMS 管理 Skype 会议室系统 v2 聊天室的管理。 
  
## <a name="functional-overview"></a>功能概述

![使用 OMS 的 SRS 管理图表](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
控制台设备上的 Skype 会议室系统 v2 应用程序将事件写入到其 Windows 事件日志。 安装 OMS 代理后，该代理即可向 OMS 传递信息。 
  
一次正确配置，OMS 分析 JSON 负载事件中嵌入说明来描述每个 Skype 会议室系统 v2 系统如何工作和检测到哪些故障。 
  
管理员使用 OMS 可以获取的已处于脱机状态的 Skype 会议室系统 v2 系统通知或是遇到应用程序、 连接或硬件故障，以及了解是否需要重新启动系统。 每个系统状态每五分钟更新一次，因此这些通知接近于实时更新。
  
## <a name="oms-requirements"></a>OMS 要求

必须具有 OMS 的有效订阅才能使用此功能。 请参阅 [Log Analytics 工作区入门](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started?toc=%2fazure%2foperations-management-suite%2ftoc.json)来为贵组织创建订阅。
  
如有必要，应尽量使自己熟悉 OMS View Designer 的使用方法。 有关详细信息，请参阅 [Operations anagement Suite (OMS) 管理解决方案中的视图](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-solutions-resources-views)。
  
### <a name="related-tasks"></a>相关任务

1. 订阅 OMS 后, 创建自定义字段 （如[映射自定义字段](../../deploy/deploy-clients/with-oms.md#Custom_fields)中所述） 所需分析将从 Skype 会议室系统 v2 控制台发送的信息。 这包括了解[了解日志条目](../../manage/skype-room-systems-v2/oms.md#understand-the-log-entries)中记录的 JSON 架构。
    
2. 开发中 OMS 的 Skype 会议室系统 v2 管理视图。 您可以[创建使用的导入方法 Skype 会议室系统 v2 仪表板](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-by-using-the-import-method)任一） 或[手动创建 Skype 会议室系统 v2 仪表板](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-manually)。
    
## <a name="individual-skype-room-systems-v2-console-requirements"></a>单个 Skype 会议室系统 v2 控制台要求

每个 Skype 会议室系统 v2 控制台是以展台模式面 4 设备上运行的应用程序 （通常，它配置为仅可在设备上运行的应用程序）。 与任何 Windows 应用程序，Skype 会议室系统 v2 应用程序到 Windows 事件日志中写入像启动和硬件故障的事件。 添加 Skype 会议室系统 v2 设备上的 OMS 代理允许根据 OMS 将收集这些事件。 （请参阅[到 Azure 中的日志分析服务的连接的 Windows 计算机](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)详细信息。）
  
## <a name="ongoing-management"></a>正在进行的管理

同时使用 OMS 管理 Skype 会议室系统 v2 会议设备，您需要了解由 OMS 的事件日志中包含的信息。 有关这些运行状况消息的详细信息，请参阅[了解日志条目](../../manage/skype-room-systems-v2/oms.md#understand-the-log-entries)。
  
### <a name="related-tasks"></a>相关任务

- 了解通知生成 Skype 会议室系统 v2 以及如何解决这些问题 （请参阅名为[了解日志条目](../../manage/skype-room-systems-v2/oms.md#understand-the-log-entries)的部分）
    
## <a name="see-also"></a>另请参阅

[使用 OMS 部署 Skype 会议室系统 v2 管理](../../deploy/deploy-clients/with-oms.md)
  
[使用 OMS 管理 Skype 会议室系统 v2 设备](../../manage/skype-room-systems-v2/oms.md)