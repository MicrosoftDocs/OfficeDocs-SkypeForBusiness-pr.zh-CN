---
title: Skype for Business Server 2015 管理工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 478e18323bf44a5a4cd93c0ce1a51f6da7058174
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835102"
---
# <a name="skype-for-business-server-2015-management-tools"></a>Skype for Business Server 2015 管理工具
 
**摘要：** 了解 Skype for Business Server 2015 中的服务管理工具。
  
Skype for Business Server 2015 通信软件 (Lync Server) ，提供即时消息 (IM) 、状态、会议和电话解决方案，这些解决方案支持企业级协作要求。 用于管理服务的工具既灵活又强大。 
  
## <a name="skype-for-business-server-2015-tools"></a>Skype for Business Server 2015 工具

||**内容**|**说明**|
|:-----|:-----|:-----|
||[Microsoft 通话质量方法记分卡 v1.5](https://go.microsoft.com/fwlink/p/?LinkId=615208) (.zip 下载)  <br/> [适用于 Skype for Business 的 CQM 海报](https://go.microsoft.com/fwlink/p/?LinkID=617898) <br/> [Lync 2013 的 CQM 海报](https://go.microsoft.com/fwlink/p/?LinkId=391841) <br/> |适用于 Lync Server 和 Skype for Business Server 2015 (CQM) Microsoft 呼叫质量方法的更新版本。 您可以使用 CQM 记分卡实现呼叫质量方法，这是一种基于网络指南中概述的方法系统性地定义和断言呼叫质量的全面方法。 CQM 将 Lync/Skype for Business 实现划分为影响质量的十个离散区域，为每个区域定义目标和修正计划。 CQM 是解决通话质量问题的框架 - 你可以修改或扩展它以解决网络的特定条件  <br/> CQM 海报可帮助你了解 CQM，即 Lync 和 Skype for Business 的呼叫质量方法，可帮助你查找和消除影响 Lync/Skype for Business 实施（包括企业语音功能）的通话质量和用户体验的问题。  <br/>**注意：** 这些工具不会针对 Skype for Business Server 2019 进行更新。 |
|![仪表板图标](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[呼叫质量仪表板](https://go.microsoft.com/fwlink/p/?LinkId=534842) <br/> |呼叫质量仪表板 (CQD) 是一个 Web 门户，用于根据 Skype for Business 或 Lync 环境的用户体验质量 (QoE) 数据快速创建和组织报告。 CQD 部署 SSAS 多维数据集以聚合 QoEMetrics 数据库中的数据，这使用户能够创建和修改报告并实时查看报告更新。 此外，CQD 还公开了 Web API，这些 API 允许用户以编程方式访问多维数据集数据，以用于自定义仪表板。  <br/> |
|![KHI 图标](../media/8759b767-b689-4a95-94a5-5b27c5688688.png)|[KHI 资源](https://go.microsoft.com/fwlink/p/?LinkId=534843) <br/> |KHI (关键运行状况) 是具有建议阈值的性能计数器，旨在显示可能会影响用户体验的问题。 KHI 指南概述了维护正常部署的操作过程和修正步骤，并包括用于配置 KHI 数据收集器的示例 PowerShell 脚本以及可分析 KHI 性能数据的分析和定义工作簿。  <br/> |
|![仪表板图标](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[Skype for Business Server 2015 统计信息管理器](statistics-manager/statistics-manager.md) <br/> |StatsMan 是一个仪表板解决方案，用于实时查看 KHI 计算，以及跨基础结构聚合的图形性能计数器。 仪表板可用于精确定位正在进行的性能问题、查看计划环境更改的结果、跟踪中断的解决方法等。 它开箱即用 KHI 资源中的 KHI 阈值进行配置，可进行自定义以满足部署的独特需求。  <br/> |
|![仪表板图标](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[Skype for Business Server 2015 资源工具包工具](https://www.microsoft.com/download/details.aspx?id=52631) <br/> |Skype for Business Server 2015 资源工具包工具可帮助部署和管理 Skype for Business Server 2015 的 IT 管理员更轻松地执行一些常规任务。  <br/> |
|![网络图标](../media/c74d45da-b10f-43c9-aa80-b1935f45c3ee.png)|[网络指南](https://go.microsoft.com/fwlink/p/?LinkID=390677) <br/> |Microsoft Lync Server 2013 和 Skype for Business 2015 通信软件，支持对等音频和视频 (A/V) 呼叫、会议和协作，并依赖优化的可靠网络基础结构在客户端之间提供高质量的媒体会话。 网络指南提供了一个模型，用于管理 Skype for Business 和 Lync 的网络基础结构，包括三个阶段：规划、监视和疑难解答。 这些阶段可应用于新的 Lync 或 Skype for Business Server 部署或现有部署。 最近对网络指南的变更涵盖 Lync/Skype Wi-Fi服务质量策略的配置。  <br/> |
|![剪贴板图标](../media/2e0c9c21-cd2a-4db5-8cb7-d2c0b1b159b7.png)|[Skype for Business 2015 中的集中日志记录服务](centralized-logging-service/centralized-logging-service.md) <br/> |集中日志记录服务是一种强大的故障排除工具，可解决从根本原因分析到性能问题等大或小问题。 所有示例都使用 Skype for Business Server 命令行管理程序显示。 通过工具本身为命令行工具提供帮助，但可以从命令行执行一组有限的函数。 通过使用 Skype for Business Server 命令行管理程序，你可以访问更大且可配置更多的功能集，因此这应始终成为你的第一选择。  <br/> |
|![SCOM 图标](../media/3a7601cb-dd2f-4606-8a3b-07c7abdc091a.png)|[使用 SCOM 管理包管理 Skype for Business Server 2015](use-scom-management-pack/use-scom-management-pack.md) <br/> |通过使用 Skype for Business Server 2015 管理包，可以主动识别和解决潜在问题。 这样，Skype for Business Server 2015 管理包将扩展 System Center Operations Manager 的功能。  <br/> |
|![仪表板图标](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[Skype for Business Server 2015 规划工具](planning-tool/planning-tool.md) <br/> |Skype for Business 2015 规划工具提供了说明性指导，可指导你开始规划拓扑。  <br/> **注意：** 此工具不会针对 Skype for Business Server 2019 进行更新。 |
|![仪表板图标](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[Skype for Business Server 2015 容量规划计算器](capacity-planning-calculator.md) <br/> |Skype for Business Server 2015 容量规划计算器可帮助你为拓扑建模以满足组织的需求。  <br/> |
|![网络图标](../media/c74d45da-b10f-43c9-aa80-b1935f45c3ee.png)|[Skype for Business Server 2015 压力和性能工具](stress-and-performance-tool/stress-and-performance-tool.md) <br/> |此工具允许你使用 Skype for Business Server 2015 环境的用户负载执行各种与性能相关的测试。 该工具提供了示例脚本，可帮助满足您独特的环境需求。  <br/>**注意：** 此工具不会针对 Skype for Business Server 2019 进行更新。 |
   
## <a name="see-also"></a>另请参阅

[Lync Server 2013 工具](https://technet.microsoft.com/library/dn163598%28v=ocs.15%29.aspx)
  
[Lync Server 2010 工具](https://technet.microsoft.com/library/dn145002%28v=ocs.14%29.aspx)
