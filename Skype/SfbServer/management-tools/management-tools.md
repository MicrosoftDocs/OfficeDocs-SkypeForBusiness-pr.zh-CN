---
title: Skype for Business Server 2015 管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 4e956558-8cba-47d9-b96a-537d7f6ed938
description: 摘要：了解 Skype for Business Server 2015 中的服务管理工具。
ms.openlocfilehash: 58d6184f1fc68e87831b3d7d3177085c482784f5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031056"
---
# <a name="skype-for-business-server-2015-management-tools"></a>Skype for Business Server 2015 管理工具
 
**摘要：** 了解 Skype for Business Server 2015 中的服务管理工具。
  
Skype for Business Server 2015 通信软件（以前称为 Lync Server），提供支持企业级协作要求的即时消息（IM）、状态、会议和电话解决方案。 管理这些服务的工具既灵活又强大。 
  
## <a name="skype-for-business-server-2015-tools"></a>Skype for Business Server 2015 工具

||**内容**|**说明**|
|:-----|:-----|:-----|
||[Microsoft 呼叫质量方法记分卡，1.5](https://go.microsoft.com/fwlink/p/?LinkId=615208) （.zip 下载） <br/> [Skype for business 的 CQM 海报](https://go.microsoft.com/fwlink/p/?LinkID=617898) <br/> [Lync 2013 的 CQM 海报](https://go.microsoft.com/fwlink/p/?LinkId=391841) <br/> |Lync Server 和 Skype for business Server 2015 的 Microsoft 呼叫质量方法（CQM）记分卡的更新版本。 您可以使用 CQM 记分卡来实现呼叫质量方法，这是一种基于网络指南中所述的方法，系统地定义和断言呼叫质量的整体方式。 CQM 将 Lync/Skype for Business 实现划分为十个不连续的区域，这会影响质量，为每个区域定义目标和修补计划。 CQM 是一种解决呼叫质量问题的框架-您可以对其进行修改或扩展以解决网络中的特定情况  <br/> CQM 海报可帮助您了解 CQM、Lync 和 Skype for business 的呼叫质量方法，可帮助您查找并消除影响 Lync/Skype for Business 实现（包括企业语音功能）的呼叫质量和用户体验的问题。  <br/>**注意：** 这些工具不会更新为 Skype for business Server 2019。 |
|![仪表板图标](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[呼叫质量仪表板](https://go.microsoft.com/fwlink/p/?LinkId=534842) <br/> |呼叫质量仪表板（CQD）是一种 web 门户，用于根据 Skype for Business 或 Lync 环境中的用户体验质量（QoE）数据快速创建和组织报告。 CQD 部署 SSAS 多维数据集以聚合 QoEMetrics 数据库中的数据，从而使用户能够创建和修改报告，并实时查看更新。 此外，CQD 还公开了允许用户以编程方式访问多维数据集数据以在自定义仪表板中使用的 web Api。  <br/> |
|![KHI 图标](../media/8759b767-b689-4a95-94a5-5b27c5688688.png)|[KHI 资源](https://go.microsoft.com/fwlink/p/?LinkId=534843) <br/> |关键运行状况指示器（KHI）是性能计数器和建议的阈值，用于暴露可能影响用户体验的问题。 KHI 指南概述了维护正常部署的操作过程和修正步骤，并包含用于配置 KHI 数据收集器的示例 PowerShell 脚本，以及可分析 KHI 性能数据的分析和定义工作簿。  <br/> |
|![仪表板图标](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[Skype for business Server 2015 的统计信息管理器](statistics-manager/statistics-manager.md) <br/> |StatsMan 是一个仪表板解决方案，用于实时查看 KHI 计算以及跨整个基础结构聚合的图形性能计数器。 仪表板可用于确定持续的性能问题、查看规划的对环境的更改结果、跟踪中断的解决情况以及其他更多相关信息。 在此框中，它是从 KHI 资源中使用 KHI 阈值配置的，并且可以根据您的部署的独特需求进行自定义。  <br/> |
|![仪表板图标](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[Skype for Business Server 2015 资源工具包工具](https://www.microsoft.com/download/details.aspx?id=52631) <br/> |Skype for Business Server 2015 资源工具包工具旨在帮助您更轻松地为部署和管理 Skype for business Server 2015 的 IT 管理员提供一些日常任务。  <br/> |
|![网络图标](../media/c74d45da-b10f-43c9-aa80-b1935f45c3ee.png)|[网络指南](https://go.microsoft.com/fwlink/p/?LinkID=390677) <br/> |Microsoft Lync Server 2013 和 Skype for Business 2015 通信软件，可启用对等音频和视频（A/V）呼叫、会议和协作，并依靠经过优化且可靠的网络基础结构来提供客户端之间的高质量媒体会话。 《网络指南》提供了用于管理 Skype for Business 和 Lync 的网络基础结构的模型，其中包含三个阶段—规划、监控和故障排除。 这些阶段可应用于新的 Lync 或 Skype for Business Server 部署或现有部署。 最近对网络指南的更改覆盖了 Lync/Skype over Wi-fi 和服务质量策略的配置。  <br/> |
|![剪贴板图标](../media/2e0c9c21-cd2a-4db5-8cb7-d2c0b1b159b7.png)|[Skype for Business 2015 中的集中日志记录服务](centralized-logging-service/centralized-logging-service.md) <br/> |集中日志记录服务是一种功能强大的故障排除工具，可解决从根本原因分析到性能问题的大或小问题。 所有示例都是使用 Skype for Business Server 命令行管理程序显示的。 帮助是通过工具本身为命令行工具提供的，但您可以从命令行执行的一组有限的函数。 通过使用 Skype for Business Server 命令行管理程序，您可以访问更大和更多可配置的功能集，因此应始终为您的第一个选择。  <br/> |
|![SCOM 图标](../media/3a7601cb-dd2f-4606-8a3b-07c7abdc091a.png)|[使用 SCOM 管理包管理 Skype for Business Server 2015](use-scom-management-pack/use-scom-management-pack.md) <br/> |通过使用 Skype for Business Server 2015 管理包，可以主动识别和解决潜在问题。 通过这种方式，Skype for Business Server 2015 管理包扩展了 System Center Operations Manager 的功能。  <br/> |
|![仪表板图标](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[Skype for Business Server 2015 规划工具](planning-tool/planning-tool.md) <br/> |Skype for Business 2015 规划工具提供了说明性指导，可帮助你开始规划拓扑。  <br/> **注意：** 将不会为 Skype for business Server 2019 更新此工具。 |
|![仪表板图标](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[Skype for Business Server 2015 容量规划计算器](capacity-planning-calculator.md) <br/> |Skype for Business Server 2015 容量规划计算器可帮助您为组织的需求建模拓扑。  <br/> |
|![网络图标](../media/c74d45da-b10f-43c9-aa80-b1935f45c3ee.png)|[Skype for Business Server 2015 压力和性能工具](stress-and-performance-tool/stress-and-performance-tool.md) <br/> |此工具允许你使用 Skype for business Server 2015 环境的用户负载执行各种与性能相关的测试。 随工具一起提供了示例脚本，以帮助您满足您的独特环境需求。  <br/>**注意：** 将不会为 Skype for business Server 2019 更新此工具。 |
   
## <a name="see-also"></a>另请参阅

[Lync Server 2013 工具](https://technet.microsoft.com/library/dn163598%28v=ocs.15%29.aspx)
  
[Lync Server 2010 工具](https://technet.microsoft.com/library/dn145002%28v=ocs.14%29.aspx)
