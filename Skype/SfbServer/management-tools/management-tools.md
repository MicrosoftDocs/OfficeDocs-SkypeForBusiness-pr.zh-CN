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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 4e956558-8cba-47d9-b96a-537d7f6ed938
description: 摘要：了解 Skype for Business Server 2015 中的服务管理工具。
ms.openlocfilehash: 775f8221fe29cc306e0bcdef5855652c47681c76
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014966"
---
# <a name="skype-for-business-server-2015-management-tools"></a>Skype for Business Server 2015 管理工具
 
**摘要：** 了解 Skype for Business Server 2015 中的服务管理工具。
  
Skype for Business Server 2015 通信软件 (Lync Server) ，提供支持企业级协作要求的即时消息 (IM) 、状态、会议和电话解决方案。 用于管理这些服务的工具既灵活又强大。 
  
## <a name="skype-for-business-server-2015-tools"></a>Skype for Business Server 2015 工具

|&nbsp;|内容|说明|
|:-----|:-----|:-----|
||[Microsoft 呼叫质量方法记分卡 v1.5](https://go.microsoft.com/fwlink/p/?LinkId=615208) (.zip下载)  <br/> [CQM 海报Skype for Business](https://go.microsoft.com/fwlink/p/?LinkID=617898) <br/> [Lync 2013 的 CQM 海报](https://go.microsoft.com/fwlink/p/?LinkId=391841)  |Lync Server 和 Skype for Business Server 2015 的 Microsoft 呼叫质量方法更新 (CQM) 记分卡。 您可以使用 CQM 记分卡实施呼叫质量方法，这是一种基于网络指南中列出的方法系统地定义和断言呼叫质量的整体方法。 CQM 将 Lync / Skype for Business实施划分为影响质量的十个离散区域，并定义每个区域的目标及修正计划。 CQM 是解决通话质量问题的框架 -可以修改或扩展它，以解决网络的特定状况。  <br/> CQM 海报可帮助您了解 CQM，即 Lync 和 Skype for Business 的呼叫质量方法，可帮助您查找并消除影响 Lync/Skype for Business 实施（包括企业语音功能）的呼叫质量和用户体验的问题。  <br/>**注意：** 这些工具不会在 2019 Skype for Business Server更新。 |
|![仪表板图标。](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[通话质量仪表板](./call-quality-dashboard/call-quality-dashboard.md)  |呼叫质量仪表板 (CQD) 是一个 Web 门户，用于根据来自 Skype for Business 或 Lync 环境的用户体验质量 (QoE) 数据快速创建和组织报告。 CQD 部署 SSAS 多维数据集以聚合 QoEMetrics 数据库中的数据，这使用户能够创建和修改报告并实时查看报告更新。 此外，CQD 还公开 Web API，这些 API 允许用户以编程方式访问多维数据集数据，以用于自定义仪表板。   |
|![KHI 图标。](../media/8759b767-b689-4a95-94a5-5b27c5688688.png)|[KHI 资源](https://go.microsoft.com/fwlink/p/?LinkId=534843)  |KHI (关键) 是具有建议阈值的性能计数器，旨在发现可能会影响用户体验的问题。 KHI 指南概述了维护正常部署的操作过程和修正步骤，并包括用于配置 KHI 数据收集器的示例 PowerShell 脚本和可分析 KHI 性能数据的分析和定义工作簿。   |
|![仪表板图标。](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[2015 Skype for Business Server统计信息管理器](statistics-manager/statistics-manager.md)  |StatsMan 是一个仪表板解决方案，用于实时查看 KHI 计算，以及跨基础结构聚合的图形性能计数器。 仪表板可用于精确定位正在进行的性能问题、查看环境计划更改的结果、跟踪中断的解决等等。 它开箱即用，使用 KHI 资源的 KHI 阈值进行配置，并可以自定义以满足部署的独特需求。   |
|![仪表板图标。](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[Skype for Business Server 2015 资源工具包工具](https://www.microsoft.com/download/details.aspx?id=52631)  |Skype for Business Server 2015 资源工具包工具可帮助部署和管理 2015 年 2015 年 Skype for Business Server任务。   |
|![网络图标。](../media/c74d45da-b10f-43c9-aa80-b1935f45c3ee.png)|[网络指南](https://go.microsoft.com/fwlink/p/?LinkID=390677)  |支持对等音频和视频 (A/V) 呼叫、会议和协作的 Microsoft Lync Server 2013 和 Skype for Business 2015 通信软件，依靠优化的可靠网络基础结构在客户端之间提供高质量的媒体会话。 网络指南提供了一个模型，用于管理 Skype for Business 和 Lync 的网络基础结构，其中包括三个阶段：规划、监视和疑难解答。 这些阶段可应用于新的 Lync 或 Skype for Business Server 部署或现有部署。 最近对网络指南的变更涵盖 Lync/Skype与Wi-Fi策略的配置有关的内容。   |
|![剪贴板图标。](../media/2e0c9c21-cd2a-4db5-8cb7-d2c0b1b159b7.png)|[Skype for Business 2015 中的集中日志记录服务](centralized-logging-service/centralized-logging-service.md)  |集中日志记录服务是解决从根本原因分析到性能问题等大问题或小问题的强大故障排除工具。 所有示例都使用命令行管理程序Skype for Business Server显示。 通过工具本身为命令行工具提供了帮助，但可以从命令行执行的功能集有限。 通过使用 Skype for Business Server命令行管理程序，您可以访问更大且可配置性高很多的功能集，因此这应始终成为您的第一选择。   |
|![SCOM 图标。](../media/3a7601cb-dd2f-4606-8a3b-07c7abdc091a.png)|[使用 SCOM Skype for Business Server包管理 2015](use-scom-management-pack/use-scom-management-pack.md)  |通过使用 Skype for Business Server 2015 管理包，您可以主动识别和解决潜在问题。 这样，Skype for Business Server 2015 管理包将扩展 operations Manager System Center功能。   |
|![仪表板图标。](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[Skype for Business Server 2015 规划工具](planning-tool/planning-tool.md)  |Skype for Business 2015 规划工具提供了说明性指导，可指导您开始规划拓扑。  <br/> **注意：** 此工具不会在 2019 Skype for Business Server更新。 |
|![仪表板图标。](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[Skype for Business Server 2015 容量规划计算器](capacity-planning-calculator.md)  |The Skype for Business Server 2015 Capacity Planning Calculator helps you model a topology for your organization's needs.   |
|![网络图标。](../media/c74d45da-b10f-43c9-aa80-b1935f45c3ee.png)|[Skype for Business Server 2015 压力和性能工具](stress-and-performance-tool/stress-and-performance-tool.md)  |此工具允许您针对您的 Skype for Business Server 2015 环境执行各种与性能相关的测试。 该工具提供了示例脚本，可帮助满足您独特的环境需求。  <br/>**注意：** 此工具不会在 2019 Skype for Business Server更新。 |
   
## <a name="see-also"></a>另请参阅

[Lync Server 2013 工具](/previous-versions/office/lync-server-2013/lync-server-2013-tools)
  
[Lync Server 2010 工具](/previous-versions/office/lync-server-2010-tools/dn145002(v=ocs.14))