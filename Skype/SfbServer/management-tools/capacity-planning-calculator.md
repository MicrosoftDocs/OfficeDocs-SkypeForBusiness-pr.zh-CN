---
title: Skype for Business Server 容量计划计算器
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 摘要：如何使用容量计算器工具。
ms.openlocfilehash: bfceeb643f9043053c70670f19cbc91b325acbb4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745918"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Skype for Business Server 容量计划计算器
 
**摘要：** 如何使用容量计算器工具。

> [!NOTE]
> 本文引用Skype for Business Server 2015 下载，但它适用于：
> - Skype for Business Server 2019 年 10 月。
> - Skype for Business Server 2015 年 10 月。
  
Skype for Business Server [2015](https://www.microsoft.com/download/details.aspx?id=51196)容量计算器和[Skype for Business Server 2019](https://www.microsoft.com/download/details.aspx?id=57509)容量计算器分别扩充[了 Skype for Business 规划](https://www.microsoft.com/download/details.aspx?id=50357)工具和部署文档 (Plan for your Skype for Business Server [2015 deployment](../plan-your-deployment/plan-your-deployment.md)和[Plan for your Skype for Business Server 2019 deployment](../../SfBServer2019/plan/plan-your-deployment-2019.md)) 。 查看指南并使用规划工具创建推荐的拓扑后，使用计算器。
  
容量Skype for Business Server计算器可帮助您根据组织使用的用户数和通信工具来确定服务器要求。 确定用户配置文件和要为用户启用的功能后，使用计算器确定所需的服务器数、内存和带宽。 此版本的计算器不提供磁盘 I/O 要求的指南。
  
如果你拥有有关特定用户配置文件的准确、详细信息，可以从计算器中获益最大。 例如，启用语音的用户百分比、每个用户每小时的平均呼叫数、呼叫持续时间以及会议中的并发用户百分比可能会对服务器要求造成巨大差异。 计算器创建的建议的准确性取决于您提供的信息的准确性。
  
使用规划工具和容量规划计算器后，应模拟建议和计划负载，以确保Skype for Business Server充分预配负载。 若要在模拟负载下执行压力测试，请使用 Skype for Business Server [Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367)上Skype for Business Server[压力和性能工具](./stress-and-performance-tool/stress-and-performance-tool.md)。
  
## <a name="using-the-capacity-calculator"></a>使用容量计算器

计算器是一个Microsoft Excel电子表格。 输入单元格的颜色为橙色。 默认值输入单元格 (对于 Skype for Business Server 2015，一个池中有 80，000 个用户具有 12 台前端服务器，而对于 Skype for Business Server 2019，106，000 个用户位于具有 16 个前端服务器的一个池中) ，但您应该更改这些值以满足组织的需求。
  
使用模型包含以下部分。 若要计算容量要求，请按如下所述输入数据：从工作表顶部开始并按行向下工作： 
  
 **即时消息和状态**
  
- 在 **"用户数**"下，键入将一次登录的用户数。 此数字通常是已设置用户总数的 80%。 在大多数情况下，将为 100% 的并发用户启用 IM 和状态。 对于 2015 年，默认值为 80，000，Skype for Business Server 2019 的默认值为 106，000 Skype for Business Server用户。
    
- **联系人列表中的联系人平均** 数量指示我们用于验证系统要求的联系人数量。 此数字是固定的，不应更改。
    
  **企业语音**
  
- 在 **"为用户启用企业语音"** 中，键入为用户启用企业语音。 默认值为 60%。 
    
- 在"每个用户每小时的平均呼叫数 (**峰值) "** 中，键入预计平均用户在高峰负载期间每小时参与的呼叫数。 默认值为 4。 
    
- 在 **"使用媒体旁路的** 呼叫百分比"中，键入将绕过中介服务器的用户所呼叫的百分比。 默认值为 65%，但如果地理位置分散或在家工作的用户比例较大，则可能会较低。
    
- 在 **"UC-PSTN** 呼叫涉及的语音用户的百分比"中，键入组织的呼叫（即 UC-PSTN 电话呼叫）的百分比。 默认值为 60%。
    
- **UC-UC 呼叫中涉及** 的语音用户的百分比显示启用呼叫的用户企业语音将仅启用 UC-UC 呼叫的用户的百分比。 此号码基于您为启用 **UC-PSTN 呼叫的语音用户百分比输入的值计算**。 
    
  **会议**
  
- 在 **"并发会议的用户百分比"** 中，键入将同时参与会议的用户百分比。 默认值为 5%。 
    
- 在 **"仅具有组 IM** 的会议百分比 (没有) "中，键入仅涉及即时消息且不包含音频的会议百分比。 默认值为 10%
    
- 在 **"使用电话拨入** 式会议的用户百分比"中，键入一次使用电话拨入式会议的会议的参与者百分比。 默认值为 15%。
    
- 在 **"使用语音的会议百分比"** 中，键入将包含音频的会议百分比。 
    
  - 如果 20% 的语音会议还将包含常规视频，请选中"包括视频 (**多** 视图) 复选框。
    
  - 如果 20% 的会议还将包含多视图视频，请选中" **包括多视图** "复选框。
    
  - 如果 50% 的语音会议还将包含应用程序共享，请选中" **包括应用程序共享** "复选框。
    
  - 如果 20% 的语音会议包括数据上载，PowerPoint演示文稿，请选中"包括 **Web** 会议"复选框。
    
  **行动能力**
  
- 在 **"启用移动** 功能的用户百分比"中，键入将允许使用移动设备Skype for Business Server用户的百分比。 默认值为 40%。 
    
输入所有必需信息后，容量计算器将估计您的要求。 黄色单元格根据在性能实验室中执行的测试显示 CPU、内存和带宽Skype for Business Server值。 这些数字是作为指南提供的，不是每个变体都经过测试和验证。 计算以下值： 
  
- **前端 CPU：** 如果整个负载由与测试中使用的服务器规格相同的一台前端服务器处理，则 CPU 使用率的百分比 (请参阅本文末尾的说明) 。
    
- **网络单位：** 相应工作负荷的带宽要求（以兆位 (Mbps) Mbps）。
    
- **内存（以 GB** 为单位）：对应 (所需的内存) GB。
    
绿色单元格显示您输入的使用模型的建议。 
  
- 前端服务器总数：所需的物理服务器数量基于运行 Skype for Business Server 2015 双处理器、十六核、2，260 兆周或 Skype for Business Server 2019（Intel Xeon E5-2673 v3、双处理器、六核）的专用服务器。
    
    请注意，建议启用超线程，并且已证明可改进支持音频/视频的服务器的性能。
    
- **边缘服务器**：需要的边缘服务器数量，基于通过边缘服务器进行通信的所有并发用户的 30%。 此百分比在计算器中无法更改。 
    
- **存档/呼叫详细记录/** 用户体验质量服务存储：存档或监控功能所需的存储数量（如果在你的组织中已启用）。
    
- **后端数据库服务器 (池** 必需) ：支持所选工作负荷所需的后端数据库服务器的数量。
    
此外，在"前端服务器总数"旁边的行中，还提供了有关所有计划工作负载组合在一起的服务器和网络负载详细信息。
  
- **平均 CPU 负载**：每个前端服务器的平均 CPU 使用率。
    
- **网络 （Mbps）：** 支持您输入的使用模型所需的带宽分配。
    
- **内存（GB）：** 每个前端服务器所需的内存（以 GB 为单位）。
    
### <a name="adjusting-for-your-processors"></a>针对处理器进行调整

电子表格中所有 CPU 使用率数字都假设每个 Skype for Business Server 2015 服务器都有一个双处理器、具有 2.26 GHz 的十六核、至少 32 GB 的内存以及 8 个或多个 10，000 RPM 硬盘驱动器（至少具有 72 GB 的可用磁盘空间）。 对于每个 Skype for Business Server 2019 服务器，电子表格中所有 CPU 使用率数据均假设每个服务器具有双处理器、具有 Intel Xeon E5-2673 v3 的十六核处理器、至少 64 GB 的内存以及 8 个或 80，000 RPM 的硬盘驱动器（至少具有 72 GB 的可用磁盘空间）。
  
如果您的服务器具有不同的处理器，您可以调整数字以匹配硬件。
