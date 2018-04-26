---
title: 使用 OMS 规划 Skype 会议室系统 v2 管理
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fd16866-27eb-47a9-b335-2f6bc9044a80
description: 本文讨论使用 Operations Management Suite 管理你的 Skype for Business Server 2015 实现中的 Skype 会议室系统 v2 设备时的规划注意事项。
ms.openlocfilehash: b117b243b638c9e06b21901f14515b51d6931d23
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="plan-skype-room-systems-v2-management-with-oms"></a>使用 OMS 规划 Skype 会议室系统 v2 管理
 
 本文讨论使用 Operations Management Suite 管理你的 Skype for Business Server 2015 实现中的 Skype 会议室系统 v2 设备时的规划注意事项。
  
[操作管理套件](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview)(OMS) 是一套旨在在云从一开始的管理服务。 OMS 组件并不部署和管理本地资源，而是完全托管在 Azure 中。 只需进行最少的配置，即可在几分钟内开机运行。 某些自定义项的工作，它能够帮助管理通过为各个房间的系统，提供系统健康状况或故障的实时通知 Skype 的空间系统 v2 会议系统，它可以有可能扩展到管理数千个 Skype 的空间系统v2 会议室。
  
这篇文章提供的要求、 设计/体系结构和实现的 Skype 的空间系统 v2 会议设备，OMS 管理所需的最佳实现做法的讨论并提供有关实施 OMS 的详细的文章的链接Skype 的空间系统 v2 和日常 OMS Skype 的空间系统 v2 机房管理的重要参考信息的管理。 
  
## <a name="functional-overview"></a>功能概述

![使用 OMS 的 SRS 管理图表](../../media/3f2ae1b8-61ea-4cd6-afb4-4bd75ccc746a.png)
  
Skype 的空间系统 v2 应用程序在控制台设备会将事件写入到其 Windows 事件日志。 安装 OMS 代理后，该代理即可向 OMS 传递信息。 
  
一次正确配置，OMS 的 JSON 负载事件中嵌入描述来描述每个 Skype 的空间系统 v2 系统如何工作和哪种故障检测的分析。 
  
管理员使用 OMS 可以获得通知的 Skype 的空间系统 v2 系统离线或会遇到应用程序、 连接或硬件故障以及知道是否需要重新启动系统。 每个系统状态每五分钟更新一次，因此这些通知接近于实时更新。
  
## <a name="oms-requirements"></a>OMS 要求

必须具有 OMS 的有效订阅才能使用此功能。 请参阅[日志分析区开始](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started?toc=%2fazure%2foperations-management-suite%2ftoc.json)为您的组织创建预订。
  
如有必要，应尽量使自己熟悉 OMS View Designer 的使用方法。 这些详细信息，请参阅[操作管理套件 (OMS) 管理解决方案中的视图](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-solutions-resources-views)。
  
### <a name="related-tasks"></a>相关任务

1. 一旦订阅了 OMS，创建自定义字段 （如[映射自定义字段](../../deploy/deploy-clients/with-oms.md#Custom_fields)中所述） 所需分析将从 Skype 的空间系统 v2 控制台发送的信息。 这包括了解[了解日志条目](../../manage/skype-room-systems-v2/oms.md#Telemetry)中记录的 JSON 架构。
    
2. 开发中 OMS 的 Skype 的空间系统 v2 管理视图。 您可以[创建使用的导入方法的 Skype 的空间系统 v2 仪表板](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-by-using-the-import-method)） 或[手动创建 Skype 的空间系统 v2 仪表板](../../deploy/deploy-clients/with-oms.md#create-a-skype-room-systems-v2-dashboard-manually)。
    
## <a name="individual-skype-room-systems-v2-console-requirements"></a>单个的 Skype 的空间系统 v2 控制台要求

每个 Skype 的空间系统 v2 控制台是在 kiosk 模式下表面 4 设备上运行的应用程序 （通常情况下，其配置为只可以在设备上运行的应用程序）。 与任何 Windows 应用程序中，Skype 的空间系统 v2 应用程序写入启动和硬件故障这样的事件记录到 Windows 事件日志。 Skype 的空间系统 v2 设备上添加 OMS 代理允许通过 OMS 收集这些事件。 （请参阅[连接 Windows Azure 中的日志分析服务的计算机](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)的详细信息）。
  
## <a name="ongoing-management"></a>正在进行的管理

同时使用 OMS 来管理您的 Skype 的空间系统 v2 会议设备，您需要了解使用 OMS 的事件日志中包含的信息。 这些健康消息的详细信息，请参阅[了解日志条目](../../manage/skype-room-systems-v2/oms.md#Telemetry)。
  
### <a name="related-tasks"></a>相关任务

- 了解通过 Skype 的空间系统 v2 和如何解决这些问题 （请参见一节[了解日志条目](../../manage/skype-room-systems-v2/oms.md#Telemetry)） 生成的警报
    
## <a name="see-also"></a>另请参阅

#### 

[部署与 OMS 的 Skype 的空间系统 v2 管理](../../deploy/deploy-clients/with-oms.md)
  
[管理与 OMS 的 Skype 的空间系统 v2 设备](../../manage/skype-room-systems-v2/oms.md)

