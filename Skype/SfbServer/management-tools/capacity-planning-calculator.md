---
title: Skype for Business Server 容量计划计算器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/1/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bc4d93b1-0c38-4bf8-8b65-692ff3e2446d
description: 摘要：如何使用容量计算器工具。
ms.openlocfilehash: ca7266f5a18e21dbb964f18a791de9b8903a7f0c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802992"
---
# <a name="skype-for-business-server-capacity-planning-calculator"></a>Skype for Business Server 容量计划计算器
 
**摘要：** 如何使用容量计算器工具。

> [!NOTE]
> 本文引用 Skype for Business Server 2015 下载，但它适用于：
> - Skype for Business Server 2019。
> - Skype for Business Server 2015。
  
[Skype for Business Server 2015 容量](https://www.microsoft.com/download/details.aspx?id=51196)计算器和 Skype for Business Server [2019 容量](https://www.microsoft.com/download/details.aspx?id=57509)计算器分别扩充了 Skype for Business[规划](https://www.microsoft.com/download/details.aspx?id=50357)工具和部署文档 (Plan for your Skype for Business [Server 2015 deployment](../plan-your-deployment/plan-your-deployment.md) and Plan for your Skype for Business Server [2019 deployment](../../SfBServer2019/plan/plan-your-deployment-2019.md) respectively) . 查看指南并使用规划工具创建推荐的拓扑后，使用计算器。
  
Skype for Business Server 容量计算器可帮助你根据组织使用的用户数和通信工具确定服务器要求。 确定用户配置文件和要为用户启用的功能后，使用计算器确定所需的服务器数、内存和带宽。 此版本的计算器不提供磁盘 I/O 要求的指南。
  
如果你拥有有关特定用户配置文件的准确、详细信息，则可以从计算器中获益最多。 例如，启用语音的用户百分比、每个用户每小时的平均呼叫数、呼叫持续时间以及会议中的并发用户的百分比可能会对服务器要求产生巨大差异。 计算器创建的建议的准确性取决于您提供的信息的准确性。
  
使用规划工具和容量规划计算器后，应模拟建议和计划的负载，以确保充分预配 Skype for Business Server。 若要在模拟负载下执行压力测试，请使用 [Skype for Business Server](https://www.microsoft.com/download/details.aspx?id=50367) 压力和性能工具（在 Skype for Business Server 压力和性能工具 [中记录](https://technet.microsoft.com/library/mt631400.aspx)）。
  
## <a name="using-the-capacity-calculator"></a>使用容量计算器

计算器是 Microsoft Excel 电子表格。 输入单元格的颜色为橙色。 默认值在单元格 (For Skype for Business Server 2015 中输入，一个池中有 80，000 个用户具有 12 台前端服务器，而对于 Skype for Business Server 2019，一个池中有 106，000 个用户具有 16 个前端服务器) ，但应更改这些值以满足组织的需求。
  
使用模型包含以下部分。 若要计算容量要求，请按如下所述输入数据：从工作表顶部开始并按行向下工作： 
  
 **即时消息和状态**
  
- 在 **"用户数"** 下，键入将同时登录的用户数。 此数字通常是已设置用户总数的 80%。 在大多数情况下，将为 100% 的并发用户启用 IM 和状态。 Skype for Business Server 2015 的默认值为 80，000，Skype for Business Server 2019 的默认值为 106，000 个用户。
    
- **联系人列表中的平均联系人** 数指示我们用于验证系统要求的联系人数量。 此数字是固定的，不应更改。
    
  **企业语音**
  
- 在 **"启用企业语音** 中，键入为用户启用企业语音。 默认值为 60%。 
    
- 在 **每个用户** 每小时呼叫数 (峰值) 中，键入预计平均用户在高峰负载期间参与的每小时呼叫数。 默认值为 4。 
    
- 在 **"使用媒体旁路的** 呼叫百分比"中，键入将绕过中介服务器的用户所呼叫的百分比。 默认值为 65%，但如果分散在地理位置或拥有大量在家工作的用户，则可能会较低。
    
- 在 **UC-PSTN** 呼叫中涉及的语音用户的百分比中，键入组织的呼叫（即 UC-PSTN 电话呼叫）的百分比。 默认值为 60%。
    
- **UC-UC** 呼叫中涉及的语音用户的百分比显示为仅启用 UC-UC 呼叫企业语音的用户的百分比。 此号码是根据您为启用 **UC-PSTN** 呼叫的语音用户百分比输入的。 
    
  **会议**
  
- 在 **并发会议的用户百分比中**，键入将同时参与会议的用户百分比。 默认值为 5%。 
    
- 在 **仅包含组 IM** 的会议的百分比 (没有语音) ，请键入仅涉及即时消息且不包括音频的会议百分比。 默认值为 10%
    
- 在 **"使用电话拨入** 式会议的用户百分比"中，键入一次使用电话拨入式会议的会议参与者的百分比。 默认值为 15%。
    
- 在 **"使用语音的会议百分比"** 中，键入将包含音频的会议百分比。 
    
  - 如果 20% 的语音会议还将包含常规视频，请选中"包括视频 (**无** 多视图) 复选框。
    
  - 如果 20% 的会议还将包含多视图视频，请选中" **包括多视图"** 复选框。
    
  - 如果 50% 的语音会议还将包含应用程序共享，请选中" **包括应用程序共享"** 复选框。
    
  - 如果 20% 的语音会议包括数据上载（如 PowerPoint 演示文稿），请选中"包括 **Web 会议"** 复选框。
    
  **移动性**
  
- 在 **启用移动功能的用户的** 百分比中，键入将允许使用移动设备连接到 Skype for Business Server 的用户百分比。 默认值为 40%。 
    
输入所有必需信息后，容量计算器会估计您的要求。 黄色单元格根据 Skype for Business Server 性能实验室中执行的测试显示 CPU、内存和带宽要求的计算值。 这些数字作为指南提供，不是每个变体都经过测试和验证。 计算以下值： 
  
- **前端 CPU：** 如果整个负载由与测试中使用的服务器规格相同的一台前端服务器处理，则 CPU 使用率的百分比 (请参阅本文末尾的说明) 。
    
- **网络（以 Mbps** 表示）：相应工作负荷的带宽要求 (Mbps) 兆位。
    
- **内存（以 GB** 为单位）：对应工作负荷所需的内存 (GB) GB。
    
绿色单元格显示您输入的使用模型的建议。 
  
- 前端服务器总数：所需的物理服务器数量基于运行 Skype for Business Server 2015（具有双处理器、十六核、2，260 兆周）或 Skype for Business Server 2019（Intel Xeon E5-2673 v3、双处理器、十六核）的专用服务器。
    
    请注意，建议启用超线程，并且已证明为支持音频/视频的服务器提高性能。
    
- **边缘服务器**：所需的边缘服务器数量，基于通过边缘服务器进行通信的所有并发用户的 30%。 计算器中无法更改此百分比。 
    
- **存档/呼叫详细信息记录/用户体验** 质量服务存储：存档或监控功能所需的存储数量（如果在你的组织中已启用）。
    
- **后端数据库服务器 (池必需) ：** 支持所选工作负荷所需的后端数据库服务器的数量。
    
此外，在前端服务器总数旁边的行中，还提供了有关所有计划工作负荷组合在一起的服务器和网络负载详细信息。
  
- **平均 CPU 负载**：每个前端服务器的平均 CPU 使用率。
    
- **网络（以 Mbps** 表示）：支持您输入的使用模型所需的带宽分配。
    
- **内存（GB）：** 每个前端服务器所需的内存（以 GB 为单位）。
    
### <a name="adjusting-for-your-processors"></a>针对处理器进行调整

电子表格中所有 CPU 使用率数据都假定每个 Skype for Business Server 2015 服务器都有一个双处理器、2.26 GHz 的十六核、至少 32 GB 的内存以及 8 个或多个 10，000 RPM 硬盘驱动器，其中至少具有 72 GB 的可用磁盘空间。 对于每个 Skype for Business Server 2019 服务器，电子表格中所有 CPU 使用率数据都假设每个服务器都有一个双处理器、具有 Intel Xeon E5-2673 v3 的十六核、至少 64 GB 的内存以及 8 个或多个 10，000 RPM 硬盘驱动器，其中至少具有 72 GB 的可用磁盘空间。
  
如果您的服务器具有不同的处理器，您可以调整数字以匹配您的硬件。
  
